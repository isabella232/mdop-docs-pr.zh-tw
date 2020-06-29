---
title: Microsoft Application Virtualization 管理系統版本資訊
description: Microsoft Application Virtualization 管理系統版本資訊
author: dansimp
ms.assetid: e1a4d5ee-53c7-4b48-814c-a34ce0e698dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c34abab9a49bd69f760a9b531d0950cc581253c1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800964"
---
# Microsoft Application Virtualization 管理系統版本資訊


若要搜尋這些版本筆記，請按 CTRL + F。

**重要** 在安裝應用程式虛擬化管理系統之前，請先閱讀這些版本資訊。 這些版本資訊包含成功安裝應用程式虛擬化管理系統所需的資訊。 此檔包含產品檔中不提供的資訊。 如果這些版本資訊與其他應用程式虛擬化管理系統檔的差異不一樣，最新的變更應該視為權威性。 這些版本資訊取代本產品隨附的內容。

 

如需已知問題的更新資訊，請流覽 Microsoft TechNet 文件庫 <https://go.microsoft.com/fwlink/?LinkId=122918> 。

## 關於 Microsoft Application Virtualization 4.5 累計更新1


這些版本資訊已更新，以反映 Microsoft Application Virtualization 4.5 累加 Update1 （App-v 4.5 CU1）所引進的變更，這些變更提供應用程式虛擬化（app-v）4.5 的最新更新。 此累積更新包含下列變更：

-   支援 Windows7 Beta 版和 Windows Server2008R2 Beta： App-v 4.5 CU1 解決 Windows7 Beta 與 Windows Server2008R2 Beta 版的相容性問題。 支援將提供給封鎖問題，避免在 RTM 版本的 Windows7 中在測試環境中執行 App-v 4.5 CU1。 這將有助於確保您的虛擬應用程式能在測試環境中順利執行，在此情況下，需要 App-v 4.5 用戶端與 Windows7 Beta 之間的相容性。

    **重要** 不支援在即時操作環境中的任何 Windows7 或 Windows Server2008R2 上執行 App-v 4.5 CU1。

     

-   改良對 .NET Framework 排序的支援： App-v 4.5 CU1 解決先前在 WindowsXP （SP2 或更新版本）中排序 .NET Framework 3.5 及更舊版本的問題。 如需新功能的詳細資訊，請參閱 TechNet 文章 <https://go.microsoft.com/fwlink/?LinkId=123412> 。

-   客戶意見反應與修復程式匯總： App-v 4.5 CU1 也包含自 App-v 4.5 RTM 版本以來發現問題的修正程式。 這包括由我們內部團隊、合作夥伴和使用 App-v 4.5 的客戶提供的已知問題與客戶意見反應的結合。 如需隨附更新的完整清單，請參閱中的知識庫文章 <https://go.microsoft.com/fwlink/?LinkId=141258> 。

## 關於產品檔


應用程式虛擬化（app-v）的綜合檔可在應用程式虛擬化（app-v）技術中心的 Microsoft TechNet 上取得 <https://go.microsoft.com/fwlink/?LinkId=122939> 。 TechNet 檔包含應用程式虛擬化排序器、應用程式虛擬化用戶端和應用程式虛擬化伺服器的線上說明。 它也包含應用程式虛擬化規劃與部署指南，以及應用程式虛擬化操作指南。

## 防範安全性漏洞與病毒


若要協助防範安全性漏洞和病毒，請務必為任何要安裝的新軟體安裝最新的可用安全更新。 如需詳細資訊，請參閱 Microsoft 安全性網站 <https://go.microsoft.com/fwlink/?LinkId=3482> 。

## 提供意見反應


您可以透過 Microsoft Application Virtualization 技術中心（）上的社區論壇，提供意見反應，提出建議，或報告 Microsoft Application Virtualization （App-v）管理系統的問題 <https://go.microsoft.com/fwlink/?LinkId=122917> 。

您也可以將檔的意見反應直接提供給 App-v 檔小組。 將您的檔意見反應傳送給 appvdocs@microsoft.com。

## Application Virtualization 4.5 CU1 的已知問題


本節提供有關 Microsoft Application Virtualization （App-v） 4.5 CU1 問題的最新資訊。 這些問題不會出現在產品檔中，某些情況下，可能會矛盾現有的產品檔。 只要有可能，這些問題就會在後續版本中解決。

### 使用 setup.msi 將用戶端安裝或升級至 App-v 4.5 CU1 的指導方針

當您使用 setup.msi 將 App-V 用戶端安裝或升級到 App V 4.5 CU1 時，系統不會自動安裝先決條件。

WORKAROUNDYou 必須先手動安裝必備元件，才能安裝或將 App-v 用戶端升級到 4.5 CU1。 如需安裝系統必備與 App-v 用戶端的詳細程式，請參閱 <https://go.microsoft.com/fwlink/?LinkId=144106> 。

完成此操作後，請使用具有提升許可權的 setup.msi 來安裝 App-v 4.5 CU1 用戶端。 此檔案可在 Installers\\Client 資料夾中的 App-V 4.5 CU1 發行媒體中取得。

安裝 Microsoft 應用程式錯誤報表時，如果您要安裝或升級至 App-v 4.5 CU1 桌面用戶端，請使用下列命令：

    msiexec /i dw20shared.msi APPGUID={FE495DBC-6D42-4698-B61F-86E655E0796D}  allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

或者，如果您要安裝或升級至 App-v 4.5 CU1 終端服務用戶端，請使用下列命令：

    msiexec /i dw20shared.msi APPGUID={8A97C241-D92A-47DC-B360-E716C1AAA929} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

**記事** APPGUID 參數會參照您安裝或升級的 App-v 用戶端的產品代碼。 每個 setup.msi 的產品代碼都是唯一的。 您可以使用 Orca 資料庫編輯器或類似的工具來檢查 Windows 安裝程式檔案，並判斷產品代碼。 此步驟是 App-V 4.5 CU1 的所有安裝或升級所需的步驟。

 

### <a href="" id="some-applications-might-fail-to-install-during-the-monitoring-phase-when-sequencing-on-windows-7-beta--"></a>當您在 Windows7 Beta 上排序時，某些應用程式可能無法在監視階段進行安裝

當您在 Windows7 Beta 或 Windows 安裝程式5.0 電腦上進行排序時，某些應用程式可能無法在監視階段進行安裝。

WORKAROUNDYou 必須手動將 [所有人] 群組的 [完全控制] 許可權授與下列登錄機碼：

    HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\SystemGuard

**重要** 您必須使用 [**高級**] 按鈕來設定「包括從該物件的父項繼承的許可權」選項。

 

### 在 Windows7 Beta 上排序時無法儲存套件

當排序 Windows7 Beta 版時，您可能無法儲存已排序的套件，因為發生共用衝突。

WORKAROUNDAs 指定于 Microsoft Application Virtualization 4.5 排序指南（請參閱）的 [最佳做法] 區段中 <https://go.microsoft.com/fwlink/?LinkId=144108> ，您必須先關閉並停用下列軟體程式，然後再開始進行排序：

-   Windows Defender

-   防毒軟體

-   磁片磁碟重組軟體

-   Windows Search

-   任何開啟的 Windows 資源管理器會話

此外，如果您在順序站上執行 Microsoft 更新，以便在套件更新程式期間捕獲更新，您必須在開始排序前，在 VFS 排除中新增「C:\\Windows\\SoftwareDistribution」。

### 改善排序 .NET 架構時的效能

當您將 .NET Framework 排序時，您可能會遇到較低的系統效能，因為 Microsoft .NET Framework NGEN 服務會嘗試將程式集預編譯為背景工作。

WORKAROUNDWhen 排序 .NET Framework 時，請在完成監視階段後停用 Microsoft .NET Framework NGEN 服務（mscorsvw.exe）。 您必須使用 Sequencer 中的 [**虛擬服務**] 索引標籤，並將 [啟動類型] 變更為 [停用]。

### Windows7 工作列的互通性問題

當您在 Windows7 上執行應用程式虛擬化用戶端時，Windows7 工作列不會將虛擬應用程式的多個實例折迭到單一工作列按鈕。 此外，當您以滑鼠右鍵按一下虛擬應用程式的工作列按鈕時，不會顯示 [跳轉清單]，除非應用程式已釘選到 Windows7 工作列。

### 當您卸載 Microsoft Application Virtualization 用戶端時，會刪除與執行卸載之使用者相關聯的使用者設定

當您卸載 Microsoft Application Virtualization 用戶端時，Windows 安裝程式會從目前使用者的設定檔中移除應用程式虛擬化設定。 如果您的電腦使用漫遊設定檔，請不要使用您的個人網路帳戶來卸載用戶端，因為它會移除您所有電腦上的虛擬應用程式設定。

WORKAROUNDYou 應該使用不是用來執行虛擬應用程式的系統管理帳戶來執行 App-v 用戶端卸載。

### 在虛擬檔案系統和虛擬機器索引標籤上所做的編輯，必須在執行順序嚮導時儲存

如果您開啟套件以執行升級，或已執行排序嚮導（含新的套件），且您在虛擬檔案系統或虛擬機器索引標籤中變更了套件，則這些變更不會自動儲存。

在重新執行嚮導前 WORKAROUNDSave 變更，以確保它們反映在嚮導的虛擬環境中。

### 必須從提升許可權的命令提示字元執行命令列排序器

當您使用命令列排序器時，它不會提示提升。

使用提升許可權的命令提示字元 WORKAROUNDRun 命令列排序器。

### 分散式環境中的伺服器管理主控台設定

如果您需要將管理元件安裝在主應用程式虛擬化發行與流式處理伺服器以外的系統上，伺服器安裝支援在不同的伺服器上安裝管理主控台和 Web 服務（在您設定適當的主應用程式虛擬化伺服器時）。

若要在多個伺服器上散佈管理元件，必須在安裝 Web 服務的伺服器上啟用 Kerberos 委派。

### OSD 檔案中的短路徑變數名稱可能會導致錯誤

如果您收到錯誤 450478-1F702339-0000010B 在用戶端啟動虛擬應用程式時，「目錄名無效」，可能是 OSD 中的變數設定不正確。 如果應用程式的安裝程式在排序期間設定短路徑名稱，可能會發生這種情況。

WORKAROUNDRemove 位於 OSD 檔案中的任何 CSIDL 變數的尾部波形符。

### <a href="" id="correct-syntax-for-decodepath-parameter-for-command-line-sequencer-"></a>命令列排序器的 DECODEPATH 參數的正確語法

在命令列排序器中，開啟要升級的套件並將它解碼至 Q 磁片磁碟機根目錄時， *DECODEPATH*參數的語法不應該包含尾部斜線。

WORKAROUNDYou 可以使用**Q：** 而不是**Q:\\** （省略尾部 "\ \" 字元）。

### <a href="" id="when-upgrading-4-2-packages--you-encounter-problems-caused-by-windows-installer-files-in-the-virtual-file-system-"></a>升級4.2 個套件時，您會遇到 Windows 安裝程式檔案在虛擬檔案系統中造成的問題

從4.2 升級套件時，您可能會遇到與 Windows 安裝程式系統檔案不相符的問題，這些檔案預設是4.2 中所包含的 windows Installer 系統檔案，以及本機安裝在您順序工作站上的 Windows 安裝程式文件庫。 下列檔案位於 CSIDL \ _SYSTEM \\：

cabinet.dll

msi.dll

msiexec.exe

msihnd.dll

msimsg.dlll

從套件中 WORKAROUNDDelete 前面的所有檔案。 刪除 [ **VFS** ] 索引標籤上的對應，以及您解碼路徑中 CSIDL \ _SYSTEM 資料夾中的實際檔案。

### <a href="" id="on-windows-xp--client-install-logging-is-not-enabled-by-default-"></a>在 WindowsXP 上，預設不會啟用用戶端安裝記錄

安裝用戶端時，若要確保捕獲任何安裝錯誤以進行疑難排解，您應該使用命令列來啟用記錄。

WORKAROUNDAdd 參數 */l\ * vx！ log.txt*到命令列，如下列範例所示：

setup.exe/s/v "/qn/l\ * vx！ log.txt "

msiexec.exe/i setup.msi/qn/l\ * vx！ log.txt

或者，您也可以將登錄機碼設定為下列值：

\ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] 「記錄」 = "voicewarmupx！"

### 若要讓 Kerberos 驗證正常運作，必須為 IIS 註冊服務主體名稱（Spn）

針對圖示或 OSD 檔案檢索及套件資料流程使用 IIS 6.0 或7.0 時，必須先將 Spn 登記如下：

-   在 IIS 伺服器上，使用 SETSPN.EXE 資源套件工具] 執行下列命令。 必須使用伺服器完全合格的功能變數名稱（FQDN）。

    Setspn-r SOFTGRID/ &lt; 伺服器 FQDN&gt;

    Setspn-r HTTP/ &lt; 伺服器 FQDN&gt;

如需詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=131407>。

### 從 RC 升級時，用戶端記錄上的預設許可權不允許非系統管理員使用者存取記錄以進行疑難排解及支援

應用程式 VirtualizationRC 用戶端的用戶端記錄上的預設許可權不允許對記錄檔進行非系統管理員存取，而且當用戶端重新開機時，這些記錄許可權的手動變更就會還原。 此功能已在 RTM 版本中針對新的用戶端安裝修正，但在從 RC 升級之後，不會重設現有記錄檔上的自訂許可權。 不過，當您建立任何新的記錄或重新設定記錄之後，這些檔案將會有新的預設許可權。

WORKAROUNDAfter [升級]、[重設現有的用戶端記錄] 或 [手動變更其許可權]。

### .NET 相容性變更

Microsoft Application Virtualization 累加 Update1 支援在 WindowsXP （SP2 或更新版本）上排序 .NET Framework。 針對在 SoftGrid 4.2 寫入的 .NET 應用程式的排序常式，可能需要在與 App-v 4.5 排序器搭配使用時進行更新。 如需詳細資訊及因應措施，請參閱知識庫文章 <https://go.microsoft.com/fwlink/?LinkId=123412> 。

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a>用戶端從 App-v 4.2 升級之後，某些應用程式不會顯示

在記錄中檢查下列錯誤：「應用程式虛擬化用戶端無法分析 OSD 檔案」。 Microsoft Application Virtualization 4.5 用戶端會篩選出內含包含空白 OS 標記（ &lt; os &gt; &lt; /OS）的 OSD 檔案的應用程式 &gt; 。

WORKAROUNDDelete OSD 檔案中的空白 OS 標籤。

### App-v server 在其防火牆中需要免除特定進程的免除

若要讓伺服器正確地流式處理應用程式，伺服器的核心程式（包括 dispatcher）需要透過防火牆存取。

針對下列進程，在伺服器防火牆中 WORKAROUNDSet [免除]： sghwsvr.exe 和 sghwdsptr.exe。 這適用于 App-v Management Server 和 App-v 流式處理伺服器。

### 需要新 Visual Basic 執行時間的排序套件可能失敗

如果您在已安裝舊版 VBruntime 的系統上將使用新版 Visual Basic （VB）執行時間的套件排序，當您嘗試使用您的套件時，可能會看到當機或其他意外的行為。 例如，如果您嘗試將 Microsoft Money2007 （使用 VBruntime 的版本6.00.9782）用於6.00.9690 版本 VBruntime 的 WindowsXP 系統，您可能會在發票設計工具中看到當您嘗試在另一個有該舊版 WindowsXP 的 VBruntime 系統上執行該工具時發生當機。

WORKAROUNDAfter 在先後順序的電腦上安裝應用程式，但仍在監視時，將正確（較新的） VBruntime 複製到套件中從可執行檔開始的目錄。 這可讓已排序的應用程式在啟動時找到預期版本的 VBruntime。

**重要** 這個問題已于 Microsoft Application Virtualization 4.5 累加 Update1 中修正。

 

### 當伺服器安裝程式在安靜模式下執行時，它不會正確檢查 MSXML6

App-v 管理伺服器會依 MSXML6 而定。 不過，如果您在安靜模式下執行安裝程式，例如，在尚未安裝 MSXML6 的系統上使用「msiexec-i setup.msi/qn」命令，安裝程式就不會注意到缺少的相依性，也不會安裝。 最常見的結果是當用戶端嘗試從 App-v 管理伺服器重新整理髮布資訊時，會看到失敗。

WORKAROUNDVerify 該 MSXML6 已安裝在系統上，然後嘗試安裝 App-v 管理伺服器。

### 嘗試連線到應用程式虛擬化管理主控台時的錯誤碼000C800

應用程式虛擬化管理服務伺服器上不是本機系統管理員的 Application Virtualization 管理員在嘗試連線到應用程式虛擬化管理主控台時，會收到錯誤（錯誤碼：000C800），而 sftmmc 專案會指出對 SftMgmt 的存取權遭到拒絕。 若要成功連線到應用程式虛擬化管理主控台，在應用程式虛擬化管理服務伺服器上不是本機管理員的應用程式虛擬化管理員，必須至少具備 SftMgmt 檔案的讀取和執行存取權。

應用程式虛擬化管理員必須在 [%systemdrive%\\Program Files\\Microsoft System Center] App Virt 管理 Server\\App Virt 管理服務的 SftMgmt 檔案中，提供讀取和執行許可權。

### 與 KEEPCURRENTSETTINGS = 1 搭配使用時，會忽略用戶端安裝程式命令列參數

與 KEEPCURRENTSETTINGS = 1 搭配使用時，系統會忽略下列用戶端安裝程式命令列參數： SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTRIGGERS、SWIUSERDATA、REQUIRESECURECONNECTION、、、、、、、、

WORKAROUNDIf 您有想要保留的設定，請使用 KEEPCURRENTSETTINGS = 1，然後在部署之後設定其他參數。 App-v ADM 範本可用於設定下列用戶端設定： APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTRIGGERS、DOTIMEOUTMINUTES 和 ALLOWINDEPENDENTFILESTREAMING。 您可以在此找到 ADM 範本 <https://go.microsoft.com/fwlink/?LinkId=121835> 。

### 使用 Symantec Endpoint Protection 初始化虛擬應用程式時發生錯誤

在啟用應用程式和裝置控制功能的情況下使用 Symantec Endpoint Protection 時，虛擬應用程式可能無法啟動，並出現「應用程式無法正確初始化（0xc000007b）」錯誤。 如需詳細資訊及因應措施，請參閱知識庫文章 <https://go.microsoft.com/fwlink/?LinkId=125851> 。

**重要** 這個問題已于 Microsoft Application Virtualization 4.5 累加 Update1 中修正。

 

## 版本資訊版權資訊


本檔中的資訊（包括 URL 及其他網際網路網站參考）可能會變更，恕不另行通知，且僅提供提供資訊的資訊。 本檔的使用或後果的全部風險，由使用者自行提供，而且 Microsoft Corporation 不提供任何明示或暗示的保證。 本文中所述的範例公司、組織、產品、人員和事件純屬虛構。 決不意指任何真實的公司、組織、產品、人員或事件。 遵守所有適用的著作權法是使用者的責任。 在不限制版權所依據的權利的情況下，本檔的任何部分都不會以任何形式或任何方式（電子、機械、複製、錄製或其他）來複製、儲存或引進至檢索系統，或以任何形式傳送（無論是出於 Microsoft Corporation 的明確書面許可權）。

Microsoft 可能具有專利、專利申請、商標、版權或其他智慧財產權，涵蓋本檔中的相關主題。 除了 Microsoft 的任何書面授權合約中明確提供之外，提供這份檔並不代表擁有這些專利、商標、版權或其他智慧財產權的授權。



Microsoft、MS-DOS、Windows、WindowsServer、Windows Vista、Active Directory 和 ActiveSync 是 U.S.A. 和/或其他國家或地區的 MicrosoftCorporation 注冊商標或商標。

此處所提及之實際公司和產品的名稱可能是其各自擁有者的商標。

 

 





