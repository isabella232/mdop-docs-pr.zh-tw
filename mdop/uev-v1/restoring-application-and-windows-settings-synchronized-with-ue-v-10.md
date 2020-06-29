---
title: 還原與 UE-V 1.0 同步的應用程式和 Windows 設定
description: 還原與 UE-V 1.0 同步的應用程式和 Windows 設定
author: dansimp
ms.assetid: 254a16b1-f186-44a4-8e22-49a4ee87c734
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31ae83e0a44f98b66a9930f8c5db2231992a4700
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800078"
---
# <span data-ttu-id="41eb4-103">還原與 UE-V 1.0 同步的應用程式和 Windows 設定</span><span class="sxs-lookup"><span data-stu-id="41eb4-103">Restoring Application and Windows Settings Synchronized with UE-V 1.0</span></span>


<span data-ttu-id="41eb4-104">Microsoft 使用者體驗虛擬化（UE-V）的 WMI 和 PowerShell 功能可讓您還原設定套件。</span><span class="sxs-lookup"><span data-stu-id="41eb4-104">WMI and PowerShell features of Microsoft User Experience Virtualization (UE-V) provide the ability to restore settings packages.</span></span> <span data-ttu-id="41eb4-105">WMI 和 PowerShell 命令可讓您將應用程式和 Windows 設定還原為在安裝 UE-V Agent 之後第一次啟動應用程式時電腦上的設定值。</span><span class="sxs-lookup"><span data-stu-id="41eb4-105">WMI and PowerShell commands allow you to restore application and Windows settings to the settings values that were on the computer the first time the application launched after the UE-V Agent was installed.</span></span> <span data-ttu-id="41eb4-106">此還原動作是在每個應用程式或 Windows 設定基礎上執行。</span><span class="sxs-lookup"><span data-stu-id="41eb4-106">This restoring action is performed on a per-application or Windows settings basis.</span></span> <span data-ttu-id="41eb4-107">下次執行應用程式時，或當使用者登入作業系統時，就會還原這些設定。</span><span class="sxs-lookup"><span data-stu-id="41eb4-107">The settings are restored the next time that the application is run or when the user logs on to the operating system.</span></span>

**<span data-ttu-id="41eb4-108">使用 PowerShell 還原應用程式設定和 Windows 設定</span><span class="sxs-lookup"><span data-stu-id="41eb4-108">To restore application settings and Windows settings with PowerShell</span></span>**

1.  <span data-ttu-id="41eb4-109">開啟 [Windows PowerShell] 視窗。</span><span class="sxs-lookup"><span data-stu-id="41eb4-109">Open the Windows PowerShell window.</span></span> <span data-ttu-id="41eb4-110">若要匯入 Microsoft UE-V PowerShell 模組，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="41eb4-110">To import the Microsoft UE-V PowerShell module, enter the following command:</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="41eb4-111">輸入下列 PowerShell Cmdlet 來還原應用程式設定和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="41eb4-111">Enter the following PowerShell cmdlet to restore the application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="41eb4-112">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="41eb4-112">PowerShell cmdlet</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="41eb4-113">描述</span><span class="sxs-lookup"><span data-stu-id="41eb4-113">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="41eb4-114">Restore-UevUserSetting</span><span class="sxs-lookup"><span data-stu-id="41eb4-114">Restore-UevUserSetting</span></span></p></td>
    <td align="left"><p><span data-ttu-id="41eb4-115">還原應用程式的使用者設定或還原一組 Windows 設定</span><span class="sxs-lookup"><span data-stu-id="41eb4-115">Restores the user settings for an application or restores a group of Windows settings</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="41eb4-116">使用 WMI 來還原應用程式設定和 Windows 設定</span><span class="sxs-lookup"><span data-stu-id="41eb4-116">To restore application settings and Windows settings with WMI</span></span>**

1.  <span data-ttu-id="41eb4-117">開啟 PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="41eb4-117">Open a PowerShell window.</span></span>

2.  <span data-ttu-id="41eb4-118">輸入下列 WMI 命令來還原應用程式設定和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="41eb4-118">Enter the following WMI command to restore application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="41eb4-119">WMI 命令</span><span class="sxs-lookup"><span data-stu-id="41eb4-119">WMI command</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="41eb4-120">描述</span><span class="sxs-lookup"><span data-stu-id="41eb4-120">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="41eb4-121">WmiMethod-命名空間 root\Microsoft\UEV-Class UserSettings-Name RestoreByTemplateId-ArgumentList &lt; template_ID&gt;</span><span class="sxs-lookup"><span data-stu-id="41eb4-121">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name RestoreByTemplateId -ArgumentList &lt;template_ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="41eb4-122">還原應用程式的使用者設定或還原一組 Windows 設定</span><span class="sxs-lookup"><span data-stu-id="41eb4-122">Restores the user settings for an application or restores a group of Windows settings</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

## <span data-ttu-id="41eb4-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="41eb4-123">Related topics</span></span>


[<span data-ttu-id="41eb4-124">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="41eb4-124">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="41eb4-125">UE-V 1.0 作業</span><span class="sxs-lookup"><span data-stu-id="41eb4-125">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





