---
title: 部署 UE-V 代理程式
description: 部署 UE-V 代理程式
author: dansimp
ms.assetid: ec1c16c4-4be0-41ff-93bc-3e2b1afb5832
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 19f3b798ad7d3a43b0a274a25dd97b651435de51
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812201"
---
# 部署 UE-V 代理程式


Microsoft 使用者體驗虛擬化（UE-V） agent 必須在每一個使用 UE-V 的電腦上執行，以便漫遊應用程式和 Windows 設定。 AgentSetup.exe 的單一安裝程式檔案，會在32位和64位作業系統上安裝 UE-V agent。 UE-V Agent 的命令列參數如下所示：

**AgentSetup.exe 命令列參數**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>命令列參數</strong></th>
<th align="left"><strong>定義</strong></th>
<th align="left"><strong>附註</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/help 或/h 或/？</p></td>
<td align="left"><p>顯示 [AgentSetup.exe 用法] 對話方塊。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>SettingsStoragePath</p></td>
<td align="left"><p>指示定義儲存位置設定的通用命名慣例（UNC）路徑。</p></td>
<td align="left"><p>已接受% username% 或% computername% 環境變數。 腳本可能需要轉義變數。</p>
<p><strong>預設值 </strong> ： &lt; 無 &gt; （Active Directory 使用者家用版）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SettingsTemplateCatalogPath</p></td>
<td align="left"><p>表示通用命名慣例（UNC）路徑，該路徑定義已針對新設定位置範本檢查的位置。</p></td>
<td align="left"><p>只需要自訂設定位置範本</p></td>
</tr>
<tr class="even">
<td align="left"><p>RegisterMSTemplates</p></td>
<td align="left"><p>指定是否應在安裝期間註冊預設的 Microsoft 範本。</p></td>
<td align="left"><p>True |虛假</p>
<p><strong>預設值 </strong> ： True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SyncMethod</p></td>
<td align="left"><p>指定應該使用哪一種同步處理方法。</p></td>
<td align="left"><p>OfflineFiles |所有</p>
<p><strong>預設值 </strong> ： OfflineFiles</p></td>
</tr>
<tr class="even">
<td align="left"><p>SyncTimeoutInMilliseconds</p></td>
<td align="left"><p>指定在從設定儲存位置中檢索使用者設定時，電腦在超時前等待的毫秒數。</p></td>
<td align="left"><p><strong>預設值 </strong> ：2000毫秒</p>
<p>（等待最長2秒）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SyncEnabled</p></td>
<td align="left"><p>指定是啟用還是停用 UE-V 同步處理。</p></td>
<td align="left"><p>True |虛假</p>
<p><strong>預設值 </strong> ： True</p></td>
</tr>
<tr class="even">
<td align="left"><p>MaxPackageSizeInBytes</p></td>
<td align="left"><p>在 UE-V agent 報告檔案超過閾值時，指定設定套件檔案大小（以位元組為單位）。</p></td>
<td align="left"><p>&lt;大小&gt;</p>
<p><strong>預設值 </strong> ：無（無警告閾值）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>CEIPEnabled</p></td>
<td align="left"><p>指定參與客戶經驗改進計畫的設定。 如果設定為 true，則會將安裝程式資訊上傳到 Microsoft 客戶經驗改進計畫網站。 如果設定為 false，則不會上傳任何資訊。</p></td>
<td align="left"><p>True |虛假</p>
<p><strong>預設值 </strong> ： False</p>
<p><strong>在 Windows 7 上 </strong> ： True</p></td>
</tr>
</tbody>
</table>

 

在安裝期間，SettingsStoragePath 命令列參數會指定設定值的設定儲存位置。 您可以在部署 UE-V Agent 之前，先定義設定儲存位置。 如果未定義任何設定儲存位置，則 UE-V 會使用 Active Directory 使用者主目錄作為設定儲存位置。 當您在安裝期間指定 SettingsStoragePath 設定並使用% username% 作為值的一部分時，這會在使用者登入的所有電腦或會話上漫遊相同的使用者設定體驗。 如果您指定%username%\\%computername% 變數作為 SettingsStoragePath 值的一部分，這將會保留每個電腦的設定體驗。

除了結合32位和64位安裝程式之外，還提供 UE-V agent 安裝的體系結構專用 Windows 安裝程式（.msi）檔案。 AgentSetupx86.msi 或 AgentSetupx64.msi 安裝檔小於 AgentSetup.exe 檔案，可能會簡化代理程式部署。 Windows Installer （.msi）安裝支援 AgentSetup.exe 安裝程式的命令列參數。

**記事** 在 UE-V agent 安裝或卸載期間，您可以使用 AgentSetup.exe 檔案或 AgentSetup 的 .msi 檔案 &lt; &gt; ，但不能同時使用這兩個檔案。 您必須使用相同的檔案才能卸載 UE-V Agent，就像它是用來安裝 UE-V Agent 一樣。

 

安裝 UE-V agent 時，請務必使用正確的變數格式。 下表提供使用 AgentSetup.exe 或 Windows Installer （.msi）安裝檔案之部署選項的範例。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>部署類型</strong></th>
<th align="left"><strong>部署描述</strong></th>
<th align="left"><strong>範例</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>命令提示字元</p></td>
<td align="left"><p>當您從命令提示字元安裝 UE-V agent 時，請使用% ^ username% 變數格式。 如果由於設定儲存路徑中有空格而需要引號，請使用批次腳本檔案進行部署。</p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>批次處理腳本</p></td>
<td align="left"><p>當您從批次腳本檔案安裝 UE-V Agent 時，請使用%% username%% 變數格式。 如果您使用這個安裝方法，您必須使用%% 字元來轉義變數。 如果沒有此字元，腳本會在安裝時（而不是在執行時間）擴充使用者名稱變數，導致 UE-V 針對所有使用者使用單一的設定儲存位置。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p>當您從 PowerShell 提示或 PowerShell 腳本安裝 UE-V agent 時，請使用% username% 變數格式。</p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>電子軟體發佈，例如部署 Configuration Manager 軟體部署）</p></td>
<td align="left"><p>當您使用 Configuration Manager 安裝 UE-V Agent 時，請使用 ^% username ^% 變數格式。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>

 

**記事** 安裝 U EV 代理程式需要系統管理員許可權，而且電腦必須先重新開機，才能執行 UE-V Agent。

 

## 從網路共用的 UE-V Agent 部署方法


您可以使用下列方法來部署 UE-V agent：

-   可安裝 Windows 安裝程式（.msi）檔案的電子軟體發佈（ESD）方案。

-   參照在共用中集中儲存的 Windows Installer （.msi）檔案的安裝腳本。

-   在電腦上手動執行安裝程式。

若要從網路共用部署 UE-V agent，請使用下列步驟：

**從網路共用安裝並設定 UE-V Agent**

1.  在使用者擁有「讀取」許可權的網路共用上，暫存 UE-V agent 安裝檔（AgentSetup.exe）。

2.  將腳本部署到安裝 UE-V agent 的使用者電腦。 此腳本應指定設定儲存位置。

**更新 UE-V Agent**

UE-V agent 軟體的更新將透過 Microsoft Update 提供。 在 UE-V agent 升級期間，可能會更新常見 Microsoft 應用程式和 Windows 設定的預設設定位置範本組。 UE-V agent 更新可以使用企業軟體發佈（ESD）基礎結構來部署。

## 相關主題


[部署 UE-V 1.0](deploying-ue-v-10.md)

[UE-V 1.0 支援的組態](supported-configurations-for-ue-v-10.md)

[部署適用於 UE-V 1.0 的設定儲存位置](deploying-the-settings-storage-location-for-ue-v-10.md)

[安裝 UE-V 產生器](installing-the-ue-v-generator.md)

部署使用者體驗虛擬化代理程式
 

 





