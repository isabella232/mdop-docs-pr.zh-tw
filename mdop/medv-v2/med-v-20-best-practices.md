---
title: MED-V 2.0 最佳做法
description: MED-V 2.0 最佳做法
author: dansimp
ms.assetid: 47ba2dd1-6c6e-4d6e-8e18-b42291f8e02a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7b664d33b403b821ce6bc9c045d937380ab4f91b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811559"
---
# MED-V 2.0 最佳做法


當您在企業中規劃、部署及管理 MED-V 時，您可能會發現最佳做法建議非常有用。

### 將第一次設定設定為以無人值守的方式執行

雖然您可以指定任何您想要的設定，但 MED-V 是建立 Sysprep.inf 檔案，讓第一次設定可以在**無人參與**模式下執行。 這需要您在繼續執行 [**安裝管理員**] 嚮導時提供所有必要的設定資訊。 如需如何設定 MED-V 影像的詳細資訊，請參閱設定[med-v 的 Windows 虛擬電腦影像](configuring-a-windows-virtual-pc-image-for-med-v.md)。

### 停用虛擬機器上的還原點

在您建立 MED-V 工作區套件之前，我們建議您停用虛擬機器上的還原點，以避免差異磁片無限增加。 如需詳細資訊，請參閱[如何在 WINDOWS XP 中關閉及開啟系統還原](https://go.microsoft.com/fwlink/?LinkId=195927)（ https://go.microsoft.com/fwlink/?LinkId=195927) 。

### 將 MED-V 影像設定為使用本機設定檔

我們建議您只在適用于 Windows XP 的應用程式相容性環境中，套用那些對您有意義的原則。 例如，桌面自訂原則通常不需要套用，而且應該停用。 如需如何只允許使用本機設定檔的詳細資訊，請參閱[漫遊使用者設定檔的群組原則設定](https://go.microsoft.com/fwlink/?LinkId=205072)（ https://go.microsoft.com/fwlink/?LinkId=205072) 。

### 設定群組原則效能更新

根據預設，群群組原則一次會下載到電腦一個位元組。 當 MED-V 加入網域時，這會造成延遲。 若要提高群組原則的效能，建議您將下列登錄機碼值設定為 registry：

登錄子機碼： HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon

專案： BufferPolicyReads

類型： DWORD

值：1

### 透過群組原則（而非 MED-V）來散佈法律通知

如果您想要讓使用者在存取 MED-V 之前看到服務等級協定（SLA），建議您稍後透過群組原則強制執行 SLA，以便在第一次完成設定之後向最終使用者顯示 SLA。

**小心** 雖然最佳做法是在**無人參與**模式下執行第一次安裝，但如果您決定要將本機原則或登錄專案設定為在您的影像（虛擬硬碟）中包含 SLA，您也必須指定第一次安裝程式在**有人參與**的模式下執行，或第一次設定可能失敗。

 

### 壓縮虛擬硬碟

我們建議您壓縮虛擬硬碟以回收空白磁碟空間，並減少虛擬硬碟的大小。 如需如何壓縮虛擬硬碟的詳細資訊，請參閱[壓縮 Med-v 虛擬硬碟](compacting-the-med-v-virtual-hard-disk.md)。

### 將虛擬機器設定為在藍屏系統崩潰時重新開機

我們建議您將 MED-V 工作區虛擬機器設定為在遇到藍色螢幕損毀時自動重新開機。 若要在來賓中設定此設定，請將 HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\Control\\CrashControl 鍵中的 AutoReboot 值設為 "1"。

您也可以按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**系統**]，來設定此設定。 接著，在 [**高級**] 索引標籤的 [**啟動及修復**] 區域中，按一下 [**設定**]。 選取 [**自動重新開機**] 核取方塊，然後按一下 **[確定]**。

### 在封裝 MED-V 圖像之前先進行備份

我們建議您先建立 MED-V 影像的備份複本，然後再將其密封。 如需有關密封 MED-V 影像的詳細資訊，請參閱設定[med-v 的 Windows 虛擬電腦影像](configuring-a-windows-virtual-pc-image-for-med-v.md)。

### 從批次檔案安裝時，最後安裝 Windows Virtual 電腦

當您使用批次檔案安裝 MED-V 元件時，請指定是在 MED-V 主機代理程式和 MED-V 工作區套件檔案之後，再安裝 Windows 虛擬電腦和 Windows 虛擬電腦熱修復程式。 這可確保 Windows 更新不會因需要重新開機而對安裝程式造成任何干擾。

### 從本機資料夾安裝 MED-V 工作區

由於您從網路位置安裝 MED-V 時可能會發生的問題，因此建議您在本機複製 MED-V 工作區設定檔案，然後執行 setup.exe。

### <a href="" id="manage-printer-redirection-in-one-manner-only-"></a>僅以一種方式管理印表機重定向

如果您在 MED-V 來賓虛擬機器上手動安裝印表機，且在主機電腦上安裝相同的印表機，則結果是在來賓中安裝了兩次。 為了避免這種情況，我們建議您以單一方式管理印表機重新導向的 MED-V 最佳做法：停用來賓的重新導向及手動安裝印表機，或啟用重新導向，並不要在來賓上手動安裝印表機。

### <a href="" id="configure-settings-for-med-v-guest-patching-"></a>設定 MED-V 訪客修補程式的設定

您可以在 registry 中定義相關的設定值，以控制 MED-V 虛擬機器 awakens 接收自動更新的時間和時間。 MED-V 最佳做法是設定喚醒間隔，以符合您針對 MED-V 虛擬機器排程定期更新的時間。 此外，建議您將這些設定設定為類似主機電腦的行為。

如需有關如何設定 MED-V 訪客修補程式設定的詳細資訊，請參閱[管理 Med-v 工作區的自動更新](managing-automatic-updates-for-med-v-workspaces.md)。

### 設定防毒軟體/備份軟體

若要防止防病毒活動影響虛擬桌面的效能，建議您在可以時將下列虛擬機器檔案類型排除在由 MED-V 主機電腦上執行的任何防毒軟體或備份程式中：

-   \*.VMC

-   \*.VUD

-   \*.VSV

-   \*.VHD

## 相關主題


[MED-V 的安全性與保護](security-and-protection-for-med-v.md)

 

 





