---
title: Microsoft User Experience Virtualization (UE-V) 1.0 版本資訊
description: Microsoft User Experience Virtualization (UE-V) 1.0 版本資訊
author: dansimp
ms.assetid: 920f3fae-e9b5-4b94-beda-32c19d31e94b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9f9942eef7ea84cf7010a0c0173427827a512216
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800106"
---
# Microsoft User Experience Virtualization (UE-V) 1.0 版本資訊


若要搜尋 Microsoft 使用者體驗虛擬化（UE-V）版本資訊，請按 Ctrl + F。

您必須先閱讀這些版本資訊，才能安裝 UE-V。 版本資訊包含成功安裝使用者體驗虛擬化所需的資訊，並包含產品檔中不提供的其他資訊。 如果這些版本資訊與其他 UE-V 檔之間有差異，最新的變更應該視為權威性。 這些版本資訊取代本產品隨附的內容。

## 提供意見反應


向我們提供您的意見反應與意見反應，告訴我們您對 MDOP 檔的想法。 將您的檔意見反應傳送給[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)。

## UE-V 已知問題


本節包含適用于使用者體驗虛擬化的版本資訊。

### 在同一部電腦上的 App-v 與原生應用程式之間，登錄設定無法同步處理

當電腦擁有可透過應用程式虛擬化（App-v）應用程式及原生安裝應用程式（以 .msi 檔案安裝）的應用程式時，以註冊表為基礎的設定不會在技術之間同步處理。

因應措施：若要解決此問題，請選取其中一種技術來執行應用程式，但不能同時選取兩者。

### Windows 8 設定同步處理失敗，出現錯誤：「提升：： filesystem：：存在：：不正確的使用者名稱或密碼」

Windows®8作業系統設定同步處理失敗，並出現下列錯誤訊息：**提升：： filesystem：：存在：：不正確的使用者名稱或密碼**。 若要檢查作業記錄事件，請開啟**事件檢視器**，然後流覽到**應用程式和服務記錄**  /  **Microsoft**  /  **使用者體驗虛擬化**  /  **記錄**作業  /  **運作**。 UE-V 設定儲存位置所用的網路共用應該位於與使用者相同的 Active Directory 網域中。 否則，可能會發生下列錯誤：「使用者名稱或密碼不正確」。

因應措施：使用與使用者相同的 Active Directory 網域中的網路共用。 .

### Outlook 2010 的電子郵件簽名漫遊

UE-V 會在裝置之間漫遊 Outlook 2010 簽名檔案。 不過，新郵件和回復/轉寄的預設簽章選項都不行。這兩個設定會儲存在 Outlook 設定檔中，Vdoes 不會漫遊。

因應措施：無。

### 在低速連結模式下執行時，同步處理設定不會根據預期的間隔進行同步處理

在 [標準條件] 下，設定儲存位置應該可在快速連結網路連線時使用。 在低速連結模式中，同步處理將只能定期進行。 根據預設，低速連結模式同步處理排程會設定為每360分鐘。

因應措施：若要變更低速連結模式中電腦背景同步處理的頻率，您可以針對**離線**檔案設定背景同步處理原則的群組原則。

### 特殊字元不同步處理

某些字元（例如貨幣符號）不會在執行 UE-V agent 的 Windows 7 和 Windows 8 電腦之間進行同步處理。

因應措施：無。

### UE-V 不支援32位與64位版本的 Microsoft Office 之間的漫遊設定

我們建議您為32位和64位作業系統安裝32位版本的 Microsoft Office。 若要選擇您需要的 Microsoft Office 版本，請按一下這裡。 ([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)). UE-V 支援相同架構版本的 Office 間的漫遊設定。 例如，32位的 Office 設定將會在所有32位的 Office 實例之間漫遊。 UE-V 不支援32位與64位版本的 Office 之間的漫遊設定。

因應措施：無

### 與設定儲存位置有關之共用的其他資料夾在慢速連線模式中無法使用

[設定儲存區共用] 不應該位於用於其他必須使用之資料夾的網路共用位置。 當承載設定儲存位置的網路共用移至慢速連線模式時，唯一可用的資料夾是 [設定儲存位置] 資料夾。 [共用] 上的其他資料夾無法在 [緩慢連接] 模式中使用。

因應措施：無

### 與 Internet Explorer 9 [我的最愛] 相關聯的 Favicons 不會漫遊

與 Internet Explorer 9 [我的最愛] 相關聯的 favicons 不會受到使用者體驗虛擬化的漫遊，而且在新電腦上出現 [我的最愛] 時不會出現。

因應措施：當您使用書簽並將其放入 Internet Explorer 9 瀏覽器中後，就會顯示 Favicons 的相關連絡人。

### 檔案設定路徑儲存在註冊表中

某些應用程式設定會將其設定和設定檔案的路徑儲存為註冊表中的值。 當設定在電腦之間漫遊時，必須同步處理在登錄中作為路徑所參照的檔案。

因應措施：使用 [資料夾重新導向] 或其他技術，以確保任何被參照為檔案設定路徑的檔案都存在並放在 [設定] 漫遊之所有電腦上的相同位置。

### 不支援超過260個字元的路徑

不支援超過260個字元的設定儲存路徑。 將 UE-V 設定套件複製到設定儲存路徑超過260個字元後，將會失敗，並會在 UE-V 作業事件日誌中產生以下例外訊息： **\ [加強：： filesystem：：複製 \ _file：系統找不到指定的路徑 \]**。 若要檢查作業記錄事件，請開啟**事件檢視器**，然後流覽到**應用程式和服務記錄**  /  **Microsoft**  /  **使用者體驗虛擬化**  /  **記錄**作業  /  **運作**。

目前不支援超過260個字元的檔案設定路徑。 在 UE-V 設定位置範本中參照的檔案設定無法位於超過260個字元的目錄路徑中。

因應措施：無。

### UE-V agent 在登入或登入時延遲

如果在離線檔案已確定低速連結已在適當位置之前登入或登出，可能會延遲登入或登入。 [離線檔案] 功能可能需要最多三分鐘的時間來偵測目前的網路狀態。 如果您在 [離線檔案] 確定電腦已連線至低速連結之後進行登入或關閉，則 UE-V 設定套件會傳送到伺服器而不是本機快取。

因應措施：無。

### 嘗試在 Windows 8 上漫遊作業系統設定時的設定衝突

在 Windows 8 上，如果已啟用 Microsoft 帳戶同步處理，並在作業系統設定中使用 UE-V，則所套用的設定可能不一致。

解決方法：執行下列其中一項操作：

-   如果您使用 UE-V 來漫遊作業系統設定，請停用 Microsoft 帳戶同步處理

-   停用 UE-V 以進行作業系統設定

### 某些作業系統設定只會在相似的作業系統版本之間漫遊

朗讀程式的作業系統設定和地區專用的貨幣字元將只會隨著作業系統版本的 Windows 進行漫遊。 例如，貨幣字元只會從 Windows 7 漫遊至 Windows 7。

因應措施：無

### Internet Explorer 書簽不會出現在 Internet Explorer smartbar

當 Internet Explorer 書簽從一部電腦漫遊至另一部電腦時，第二部電腦上的索引無法更新，因此當您在網址列中輸入時，最愛在電腦2上的搜尋結果不會顯示。

因應措施：無

 

 





