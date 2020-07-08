---
title: UE-V 2.1 SP1 的新功能
description: UE-V 2.1 SP1 的新功能
author: dansimp
ms.assetid: 9a40c737-ad9a-4ec1-b42b-31bfabe0f170
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1f4b6210d95795c352a7ef1402b0353c6f52774b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812350"
---
# UE-V 2.1 SP1 的新功能


使用者體驗虛擬化 2.1 SP1 與 UE-V 2.1 相比，提供這些新功能和功能。 [Microsoft 使用者體驗虛擬化（ue-v） 2.1 Sp1 版本資訊](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)提供關於 UE-V 2.1 SP1 發行的詳細資訊。

## Windows 10 支援


UE-V 2.1 SP1 會新增 Windows 10 支援，以及舊版 UE-V 所支援的相同軟體。

### 與 Microsoft Azure 的相容性

Windows 10 可讓企業使用者將 Windows 應用程式設定和 Windows 作業系統設定同步處理至 Azure，而非 OneDrive。 您可以在僅限內部部署網域的電腦上，搭配使用 Windows 10 企業版同步處理功能與 UE-V。 若要啟用 Windows 10 與 UE-V 之間的共存，您必須在每一個用戶端或群組原則上使用任一 PowerShell 來停用下列 UE-V 範本。

在 [群組原則] 中的 [Microsoft 使用者體驗虛擬化] 節點下，設定以下原則設定：

-   啟用「不要同步處理 Windows 應用程式」

-   停用「同步處理 Windows 設定」

### Windows 10 支援的設定同步處理行為已變更

UE-V 2.1 SP1 會在 Windows 10 裝置之間漫遊工作列設定。 不過，UE-V 不會在執行舊版作業系統的 Windows 10 裝置與裝置之間同步處理工作列設定。

此外，UE-V 2.1 SP1 不會同步處理 Windows 10 中的 Microsoft 計算機與舊版作業系統中的 Microsoft 計算機之間的設定。

## 針對漫遊網路印表機新增的支援


UE-V 2.1 SP1 可讓網路印表機在裝置之間漫遊，讓使用者在登入網路上的任何裝置時都能存取其網路印表機。 這包括將其設為預設值的印表機漫遊。

UE-V 中的印表機漫遊需要下列其中一種情況：

-   列印伺服器可以在漫遊至新裝置時下載所需的驅動程式。

-   漫遊網路印表機的驅動程式已預先安裝在任何需要存取該網路印表機的裝置上。

-   您可以從 Windows Update 取得印表機驅動程式。

**記事** UE-V 印表機漫遊**功能不會漫遊印表機**設定或喜好設定，例如雙面列印。

 

## Office 2013 設定位置範本


UE-V 2.1 和 2.1 SP1 包含 Microsoft Office 2013 設定位置範本，以及改良的 Outlook 簽名支援。 我們已新增新、回復和轉寄電子郵件的預設簽名設定同步處理。 客戶不需要再選擇預設的簽名設定。

**記事** 您必須為使用者要同步處理其 Outlook 簽名的任何裝置建立 Outlook 設定檔。 如果尚未建立設定檔，使用者可以建立一個，然後重新開機該裝置上的 Outlook，以啟用簽名同步處理。

 

先前的 UE-V 包含 Microsoft Office 2010 設定位置範本，這些範本是透過 UE-V Agent 自動分發及註冊。 UE-V 2.1 可與 Office 365 搭配使用，以判斷 office 2013 設定是否由 Office 365 所漫遊。 如果設定是由 Office 365 漫遊，就不會透過 UE-V 漫遊。 [Office 2013 的使用者和漫遊設定概覽](https://go.microsoft.com/fwlink/p/?LinkID=391220)提供詳細資訊。

若要使用 UE-V 2.1 啟用設定同步處理，請執行下列其中一項操作：

-   使用群組原則來停用 Office 365 同步處理

-   在安裝 Office 2013 期間，請勿啟用 Office 365 同步處理體驗

UE-V 2.1 隨附[office 2013 和 office 2010 範本](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。 此版本會移除 Office 2007 範本。 使用者仍然可以使用 UE-V 2.0 或較舊版本的 Office 2007 範本，但仍可在[此處](https://go.microsoft.com/fwlink/p/?LinkID=246589)取得 ue-v 範本庫的範本。






## 相關主題


[UE-V 2.x 入門](get-started-with-ue-v-2x-new-uevv2.md)

[準備 UE-V a.x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[Microsoft User Experience Virtualization (UE-V) 2.1 SP1 版本資訊](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

 

 





