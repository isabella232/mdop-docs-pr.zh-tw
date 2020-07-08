---
title: Microsoft 進階群組原則管理 4.0 版本資訊
description: Microsoft 進階群組原則管理 4.0 版本資訊
author: dansimp
ms.assetid: 44c19e61-c8e8-48aa-a2c2-20396d14d5bb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c4a279893d4da4121e422af99e7c1708a0126b4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802598"
---
# Microsoft 進階群組原則管理 4.0 版本資訊


2009 年 10 月

## 關於 Microsoft 高級群組原則管理4。0


Microsoft 高級群組原則管理（AGPM）4.0 延伸了群組原則管理主控台（GPMC）的功能。 AGPM 可提供全面的變更控制及改良的群組原則物件（Gpo）管理。

下列檔可協助您開始使用 AGPM 4.0。

-   如需 AGPM 的功能概覽，請參閱[Microsoft 高級群組原則管理](https://go.microsoft.com/fwlink/?LinkID=162671)（）的概覽 https://go.microsoft.com/fwlink/?LinkID=162671) 。

-   如需 AGPM 4.0 與 AGPM 3.0 有何不同之相關資訊，請參閱[agpm 4.0 的新增功能](https://go.microsoft.com/fwlink/?LinkId=160058)（ https://go.microsoft.com/fwlink/?LinkId=160058) 。

-   有關如何判斷是否適合您的環境的 AGPM 4.0、AGPM 3.0 或 AGPM 2.5，請參閱[選擇要安裝的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=145981)（ https://go.microsoft.com/fwlink/?LinkId=145981) 。

-   如需有關如何安裝 AGPM 的基本指導方針，以及使用 AGPM 的範例案例，請參閱[Microsoft 高級群組原則管理 4.0](https://go.microsoft.com/fwlink/?LinkID=153505) （）的逐步指南 https://go.microsoft.com/fwlink/?LinkID=153505) 。 本指南主要是用來協助評估者和初次使用者。

-   如需有關如何從舊版 AGPM 升級的資訊，或是如何規劃您組織中的 AGPM 部署的詳細指導方針，請參閱[Microsoft 高級群組原則管理4.0 的規劃指南](https://go.microsoft.com/fwlink/?LinkID=156883)（ https://go.microsoft.com/fwlink/?LinkID=156883) 。

-   如需如何使用 AGPM 來執行特定工作的相關資訊，請參閱「高級群組原則管理」4.0 說明，這也會在 TechNet 上提供供[AGPM 4.0 的操作指南](https://go.microsoft.com/fwlink/?LinkId=159872)（ https://go.microsoft.com/fwlink/?LinkId=159872) 。

## 詳細資訊


如需有關 AGPM 的詳細資訊，請參閱下列內容：

-   [高級群組原則管理 TechNet 文件庫](https://go.microsoft.com/fwlink/?LinkID=146846)（https://go.microsoft.com/fwlink/?LinkID=146846)

-   [Microsoft 桌面優化套件技術中心](https://go.microsoft.com/fwlink/?LinkId=159870)（https://www.microsoft.com/technet/mdop)

-   [群組原則技術中心](https://go.microsoft.com/fwlink/?LinkId=145531)（https://www.microsoft.com/gp)

## 提供意見反應


您可以將有關 AGPM 的意見反應或問題張貼到 [[群組原則] 論壇](https://go.microsoft.com/fwlink/?LinkId=145532)（ https://go.microsoft.com/fwlink/?LinkId=145532) 。

## AGPM 4.0 的已知問題


### [從生產中匯入] 命令不會將設定匯入已取出的 GPO

如果您在生產環境中編輯 GPO，您必須從生產中匯入 GPO，以更新離線封存中的 GPO。 匯**入生產**命令的目的是讓您在完成編輯之前先執行最終的生產備份，以便在必要時回滾到生產備份。

如果當您執行匯**入生產**命令時，gpo 已取出，則不會將生產變更併入 GPO 的取出版本。 不過，即使該版本不能進行編輯，也會將此 GPO 的匯入版本新增到 GPO 的歷程記錄中。 GPO 簽入時，該版本會取代封存中的匯入版本，但會在 GPO 的歷程記錄中提供這兩者。

因應措施 **：** 在從生產中匯入 GPO 前，請務必先將它取出。 如果未在您匯入 GPO 前將其檢入，您可以使用 [**復原取出**] 命令來放棄變更，並回滾到您從生產匯入的 gpo 版本。

### 在使用多個網站 Active Directory 拓朴的環境中，已取出的 Gpo 無法針對數分鐘進行編輯

AGPM 使用用戶端/伺服器模型。 AGPM 服務器和 AGPM 用戶端都會針對群組原則作業決定自己最近的網網域控制站。 當您使用 AGPM 用戶端取出 GPO 時，該伺服器實際上是從離線封存檢查 GPO 的 AGPM 服務器，以在 SYSVOL 資料夾中的暫存檔案夾中。

如果 AGPM 服務器與 AGPM 用戶端位於不同的網站，則暫時取出的 GPO 可能不會出現在本機網站的網網域控制站上，長達幾分鐘，或長達30分鐘，因為 SYSVOL 複製延隔時間。 在這種情況下，您無法使用在 AGPM 用戶端上的 GPMC 來編輯已取出的 GPO，直到已取出的 GPO 發生 SYSVOL 複製為止。

因應措施 **：** 最佳做法是，您應該將 AGPM 用戶端放在與與其連接的 AGPM 服務器相同的網站中，這樣您就不需要等到進行 SYSVOL 複製，就可以編輯已取出的 GPO。

### 如果您的帳戶沒有封存的許可權，則 AGPM 無法讀取備份限制

在 AGPM 用戶端上，如果您使用尚未委派給 AGPM 封存之許可權的帳戶登入，請啟動群組原則管理主控台（GPMC），然後按一下 [**變更控制權**]，您會收到下列錯誤訊息。

``` syntax
Failed to read backup purge limit for this domain. 

The following error occurred: 
You do not have sufficient permissions to perform this operation. 
Microsoft.Agpm.AccessDeniedException (80070005)
```

因應措施 **：** 請與 AGPM 系統管理員（完全控制）聯繫，並要求他們針對您的帳戶委派對 AGPM 的存取權。 如果您是 AGPM 系統管理員，請使用指派了 AGPM 系統管理員角色的帳戶登入，這樣您就可以委派其他帳戶的存取權。 如需詳細資訊，請參閱在 AGPM 說明中的「委派網域層級的檔案存取」。

## 版本資訊版權資訊


本檔中的資訊（包括 URL 及其他網際網路網站參考）可能會變更，恕不另行通知，且僅提供提供資訊的資訊。 本檔的使用或後果的全部風險，由使用者自行提供，而且 Microsoft Corporation 不提供任何明示或暗示的保證。 本文中所述的範例公司、組織、產品、人員和事件純屬虛構。 決不意指任何真實的公司、組織、產品、人員或事件。 遵守所有適用的著作權法是使用者的責任。 在不限制版權所依據的權利的情況下，本檔的任何部分都不會以任何形式或任何方式（電子、機械、複製、錄製或其他）來複製、儲存或引進至檢索系統，或以任何形式傳送（無論是出於 Microsoft Corporation 的明確書面許可權）。

Microsoft 可能具有專利、專利申請、商標、版權或其他智慧財產權，涵蓋本檔中的相關主題。 除了 Microsoft 的任何書面授權合約中明確提供之外，提供這份檔並不代表擁有這些專利、商標、版權或其他智慧財產權的授權。



Microsoft、MS-DOS、Windows、WindowsServer 和 Windows Vista 是 U.S.A. 和/或其他國家或地區的 MicrosoftCorporation 注冊商標或商標。

此處所提及之實際公司和產品的名稱可能是其各自擁有者的商標。

 

 





