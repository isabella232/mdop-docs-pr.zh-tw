---
title: 如何安裝 App-v 資料庫，以及如何使用 PowerShell 轉換關聯的安全性識別碼
description: 如何安裝 App-v 資料庫，以及如何使用 PowerShell 轉換關聯的安全性識別碼
author: dansimp
ms.assetid: 2be6fb72-f3a6-4550-bba1-6defa78ca08a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 39651df4d62971e39c4228ffce665386d5c9769d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800493"
---
# 如何安裝 App-v 資料庫，以及如何使用 PowerShell 轉換關聯的安全性識別碼

使用下列 PowerShell 程式程式在執行 SQL 腳本時，將任何數目的 Active Directory 網域服務（AD DS）使用者或電腦帳戶轉換成格式安全識別碼（Sid），並以 Microsoft SQL Server 所使用的十六進位格式表示。

在嘗試此程式之前，您應該閱讀並瞭解以下清單中顯示的資訊和範例：

- **.輸入**–用來轉換為 SID 格式的帳戶或帳戶。 這可以是單一帳戶名稱或帳戶名稱的陣列。

- **.輸出**-具有標準及十六進位格式之對應 SID 的帳戶名稱清單。

- **示例** -

    **.\\ConvertToSID.ps1 DOMAIN\\user\ _account1 DOMAIN\\machine\ _account1 $ DOMAIN\\user\ _account2 |[格式]-清單**。

    **$accountsArray = @ （"DOMAIN\\user\ _account1"，"DOMAIN\\machine\ _account1 $"，"DOMAIN \ _user \ _account2"）**

    **.\\ConvertToSID.ps1 $accountsArray |寫入輸出-FilePath .\\SIDs.txt 寬度200**

## 將任何數目的 Active Directory 網域服務（AD DS）使用者或電腦帳戶轉換成格式化的安全識別碼（Sid）

1. 將下列腳本複製到文字編輯器中，並將其儲存為 PowerShell 腳本檔案，例如**ConvertToSIDs.ps1**。
1. 若要開啟 PowerShell 主控台，請按一下 [**開始**]，然後輸入**powershell**。 以滑鼠右鍵按一下 **Windows PowerShell**，並選取 **\[以系統管理員身分執行\]**。

   ```powershell
   <#
   .SYNOPSIS
   This PowerShell script will take an array of account names and try to convert each of them to the corresponding SID in standard and hexadecimal formats.
   .DESCRIPTION
   This is a PowerShell script that converts any number of Active Directory (AD) user or machine accounts into formatted Security Identifiers (SIDs) both in the standard format and in the hexadecimal format used by SQL server when running SQL scripts.
   .INPUTS
   The account(s) to convert to SID format. This can be a single account name or an array of account names. Please see examples below.
   .OUTPUTS
   A list of account names with the corresponding SID in standard and hexadecimal formats
   .EXAMPLE
   .\ConvertToSID.ps1 DOMAIN\user_account1 DOMAIN\machine_account1$ DOMAIN\user_account2 | Format-List
   .EXAMPLE
   $accountsArray = @("DOMAIN\user_account1", "DOMAIN\machine_account1$", "DOMAIN_user_account2")
   .\ConvertToSID.ps1 $accountsArray | Write-Output -FilePath .\SIDs.txt -Width 200
   #>

   function ConvertSIDToHexFormat
   {

      param([System.Security.Principal.SecurityIdentifier]$sidToConvert)

      $sb = New-Object System.Text.StringBuilder
      [int] $binLength = $sidToConvert.BinaryLength
      [Byte[]] $byteArray = New-Object Byte[] $binLength
      $sidToConvert.GetBinaryForm($byteArray, 0)
      foreach($byte in $byteArray)
      {
          $sb.Append($byte.ToString("X2")) |Out-Null
      }
      return $sb.ToString()
   }
    [string[]]$myArgs = $args
   if(($myArgs.Length -lt 1) -or ($myArgs[0].CompareTo("/?") -eq 0))
   {

    [string]::Format("{0}====== Description ======{0}{0}" +
                  "  Converts any number of user or machine account names to string and hexadecimal SIDs.{0}" +
                  "  Pass the account(s) as space separated command line parameters. (For example 'ConvertToSID.ps1 DOMAIN\Account1 DOMAIN\Account2 ...'){0}" +
                  "  The output is written to the console in the format 'Account name    SID as string   SID as hexadecimal'{0}" +
                  "  And can be written out to a file using standard PowerShell redirection{0}" +
                  "  Please specify user accounts in the format 'DOMAIN\username'{0}" +
                  "  Please specify machine accounts in the format 'DOMAIN\machinename$'{0}" +
                  "  For more help content, please run 'Get-Help ConvertToSID.ps1'{0}" +
                  "{0}====== Arguments ======{0}" +
                  "{0}  /?    Show this help message", [Environment]::NewLine)
   }
   else
   {
       #If an array was passed in, try to split it
       if($myArgs.Length -eq 1)
       {
           $myArgs = $myArgs.Split(' ')
       }

       #Parse the arguments for account names
       foreach($accountName in $myArgs)
       {
           [string[]] $splitString = $accountName.Split('\')  # We're looking for the format "DOMAIN\Account" so anything that does not match, we reject
           if($splitString.Length -ne 2)
           {
               $message = [string]::Format("{0} is not a valid account name. Expected format 'Domain\username' for user accounts or 'DOMAIN\machinename$' for machine accounts.", $accountName)
               Write-Error -Message $message
               continue
           }

           #Convert any account names to SIDs
           try
           {
               [System.Security.Principal.NTAccount] $account = New-Object System.Security.Principal.NTAccount($splitString[0], $splitString[1])
               [System.Security.Principal.SecurityIdentifier] $SID = [System.Security.Principal.SecurityIdentifier]($account.Translate([System.Security.Principal.SecurityIdentifier]))
           }
           catch [System.Security.Principal.IdentityNotMappedException]
           {
               $message = [string]::Format("Failed to translate account object '{0}' to a SID. Please verify that this is a valid user or machine account.", $account.ToString())
               Write-Error -Message $message
               continue
           }

           #Convert regular SID to binary format used by SQL
           $hexSIDString = ConvertSIDToHexFormat $SID

           $SIDs = New-Object PSObject
           $SIDs | Add-Member NoteProperty Account $accountName
           $SIDs | Add-Member NoteProperty SID $SID.ToString()
           $SIDs | Add-Member NoteProperty Hexadecimal $hexSIDString

           Write-Output $SIDs
       }
   }
   ```

1. 執行您在這個程式步驟中儲存的腳本，傳遞要轉換為引數的帳戶。

   例如，

   **.\\ConvertToSID.ps1 DOMAIN\\user\ _account1 DOMAIN\\machine\ _account1 $ DOMAIN\\user\ _account2 |[格式]-清單**
   
   或
   
   **$accountsArray = @ （"DOMAIN\\user\ _account1"，"DOMAIN\\machine\ _account1 $"，"DOMAIN \ _user \ _account2"）** 
    **.\\ConvertToSID.ps1 $accountsArray |寫入輸出-FilePath .\\SIDs.txt 寬度 200**

**有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題

[使用 PowerShell 管理 App-V 5.1](administering-app-v-51-by-using-powershell.md)
