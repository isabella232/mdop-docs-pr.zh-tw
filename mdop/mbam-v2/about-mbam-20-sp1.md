---
title: 關於 MBAM 2.0 SP1
description: 關於 MBAM 2.0 SP1
author: dansimp
ms.assetid: 5ba89ed8-bb6e-407b-82c2-e2e36dd1078e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 73b92cd852d4f75f63f3dcba9f18167012b61401
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810023"
---
# 關於 MBAM 2.0 SP1

本主題描述 Microsoft BitLocker 管理和監控（MBAM） 2.0 Service Pack 1 （SP1）中的變更。 如需 MBAM 的一般描述，請參閱[MBAM 2.0 快速入門](getting-started-with-mbam-20-mbam-2.md)。

## <a href="" id="what-s-new-in-mbam-2-0-sp1"></a>MBAM 2.0 SP1 的新功能

這個版本的 MBAM 會提供下列新功能和功能。

### Windows 8.1、Windows Server 2012 R2 和 System Center 2012 R2 Configuration Manager 支援

Microsoft BitLocker 管理與監控（MBAM） 2.0 Service Pack 1 （SP1）新增 Windows 8.1、Windows Server 2012 R2 和 System Center 2012 R2 建構管理員的支援。

### Microsoft SQL Server 2008 R2 SP2 支援

Microsoft BitLocker 管理與監控（MBAM） 2.0 Service Pack 1 （SP1）為 Microsoft SQL Server 2008 R2 SP2 新增支援。 如果您正在執行 Microsoft System Center Configuration Manager 2007 R2，您必須使用 Microsoft SQL Server 2008 R2 或更新版本。

### 客戶意見反應匯總

MBAM 2.0 SP1 包含一個修正程式，以解決從 Microsoft BitLocker 管理和監控（MBAM）2.0 發行後發現的問題。 在這些變更中，[電腦名稱稱] 欄位現在會出現在 [BitLocker 電腦合規性] 和 [BitLocker Enterprise 合規性詳細資料] 中，當您使用 Microsoft System Center Configuration Manager 2007 執行 MBAM 時就會顯示。

### 您必須在自助服務入口網站和 [管理與監控] 網站的埠上設定防火牆例外狀況

當您設定自助入口網站和管理和監控網站時，您必須設定防火牆例外狀況，才能透過指定的埠進行通訊。 之前，MBAM 伺服器安裝會自動在 Windows 防火牆中開啟埠。

### MBAM 報表的位置在 Configuration Manager 中已變更

您現在可以在 [MBAM] 節點中的子資料夾下取得 Configuration Manager 整合拓撲的 MBAM 報告。 子資料夾名稱代表子資料夾中報表的語言。

### 當您使用 Configuration Manager 安裝 MBAM 時，在主要網站伺服器上安裝 MBAM 的能力

當您使用 Configuration Manager 整合拓朴安裝 MBAM 時，您可以在主要的網站伺服器或管理中心網站伺服器上安裝 MBAM。 之前，您必須在管理中心網站伺服器上安裝 MBAM。

**重要**  
您在其上安裝 MBAM 的伺服器必須是階層中的最上層伺服器。



MBAM 安裝的運作方式適用于 Microsoft System Center Configuration Manager 2007 和 Microsoft System Center 2012 Configuration Manager，如下所示：

-   **Configuration Manager 2007** ：如果您在屬於較大型 Configuration manager 階層的主要網站伺服器上安裝 MBAM，且擁有中央網站父伺服器，則 MBAM 會解析中心網站的父伺服器，並在該父伺服器上執行所有安裝動作。 安裝動作包括檢查先決條件及安裝 Configuration Manager 物件和報告。 例如，如果您在主要網站伺服器上安裝 MBAM，而該伺服器是中央網站父伺服器的子網站，MBAM 會在父伺服器上安裝所有 Configuration Manager 物件和報告。 如果您在父伺服器上安裝 MBAM，MBAM 會在該父伺服器上執行所有安裝動作。

-   **System Center 2012 Configuration Manager** ：如果您在主要的網站伺服器或管理中心伺服器上安裝 MBAM，MBAM 會在該網站伺服器上執行所有安裝動作。

### <a href="" id="-------------configuration-manager-console-must-be-installed-on-the--computer-on-which-you-install-the-mbam-server"></a> Configuration Manager 主控台必須安裝在您安裝 MBAM Server 的電腦上

當您使用 Configuration Manager 整合拓朴安裝 MBAM 時，您必須在安裝 MBAM 的同一部電腦上安裝 Configuration Manager 主控台。 如果您使用的是 [[開始使用 MBAM 搭配 Configuration manager](getting-started---using-mbam-with-configuration-manager.md)] 中所述的建議結構，您可以在 Configuration Manager 主要網站伺服器上安裝 MBAM。

### Configuration Manager 整合拓朴的新設定命令列參數

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令列參數</th>
<th align="left">描述</th>
<th align="left">範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CM_SSRS_REMOTE_SERVER_NAME</p></td>
<td align="left"><p>可讓您在遠端 SQL Server Reporting Services （SSRS）伺服器上安裝 Configuration Manager 報告，該伺服器屬於安裝 MBAM 的相同 Configuration Manager 網站。 您可以將值設定為遠端 SSRS 點角色服務器的完整功能變數名稱。</p></td>
<td align="left"><p>MbamSetup.exe CM_SSRS_REMOTE_SERVER_NAME = ssrsServer</p></td>
</tr>
<tr class="even">
<td align="left"><p>CM_REPORTS_ONLY</p></td>
<td align="left"><p>可讓您只安裝 Configuration Manager 報表，而不需要其他 Configuration Manager 物件，例如比較基準、集合及設定專案。</p>
<div class="alert">
<strong>注意</strong><br/><p>您必須將此參數與 CM_REPORTS_COLLECTION_ID 參數結合。</p>
</div>
<div>

</div>
<p>有效的參數值：</p>
<ul>
<li><p>True</p></li>
<li><p>False</p></li>
</ul>
<p>如果您想要將報表只安裝至遠端 SSRS 點角色服務器，您可以將此參數與 CM_SSRS_REMOTE_SERVER_NAME 參數結合。</p>
<p>如果您沒有設定參數，或者如果您將它設為 False，MBAM 安裝程式會安裝所有 Configuration Manager 物件，包括報告。</p></td>
<td align="left"><p>MbamSetup.exe CM_REPORTS_ONLY = True</p>
<p>CM_REPORTS_COLLECTION_ID = SMS00001</p></td>
</tr>
<tr class="odd">
<td align="left"><p>CM_REPORTS_COLLECTION_ID</p></td>
<td align="left"><p>現有的集合識別碼，可識別要顯示其報告合規性資料的集合。 您可以指定任何集合 ID。 您不需要使用「MBAM 支援的電腦」集合 ID。</p></td>
<td align="left"><p>MbamSetup.exe CM_REPORTS_ONLY = True</p>
<p>CM_REPORTS_COLLECTION_ID = SMS00001</p></td>
</tr>
</tbody>
</table>



### 開啟或關閉自助入口網站通知文字的功能

MBAM 2.0 SP1 可讓您在自助服務入口網站上關閉通知文字。 之前，預設會顯示通知文字，您無法將它關閉。

**若要關閉通知文字**

1.  在您安裝自助入口網站的伺服器上，開啟 [網際網路資訊服務（IIS）]，然後流覽至 [**網站 &gt; Microsoft BitLocker 管理及監視 &gt; SelfService &gt; 應用程式設定**]。

2.  從 [ **Name** ] （名稱）欄選取 [ **DisplayNotice**]，然後將值設定為**false**。

### 能夠當地語系化將使用者指向更多自助入口網站資訊的 HelpdeskText 語句

您可以設定當地語系化版本的自助入口 "HelpdeskText" 語句，這會告訴使用者當他們使用自助入口網站時，如何取得其他協助。 如果您為語句設定當地語系化的文字，如下列指示所述，MBAM 將會顯示當地語系化版本。 如果 MBAM 找不到已當地語系化的版本，則會顯示**HelpdeskText**參數中的值。

**顯示 HelpdeskText 語句的當地語系化版本**

1.  在您安裝自助入口網站的伺服器上，開啟 [IIS]，然後流覽至 [**網站 &gt; Microsoft BitLocker 管理及監視 &gt; SelfService &gt; 應用程式設定**]。

2.  在 [**動作**] 窗格中，按一下 [**新增**] 以開啟 [**新增應用程式設定**] 對話方塊。

3.  在 [ **Name** ] （名稱）欄位中，輸入**HelpdeskText**\ _ &lt; *語言* &gt; ，其中 [ &lt; *語言*] &gt; 是該文字的適當語言代碼。 例如，若要在西班牙文中建立當地語系化的 HelpdeskText 語句，您可以將參數命名為 HelpdeskText \ _es。 如需您可以使用之有效語言代碼的清單，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)。

4.  在 [**值**] 欄位中，輸入您要顯示給最終使用者的當地語系化文字。

### 當地語系化自助入口 HelpdeskURL 的能力

您可以設定當地語系化版本的自助入口網站 HelpdeskURL，預設會顯示給使用者。 如果您建立當地語系化版本，請參閱下列指示中的 MBAM 找出並顯示當地語系化版本。 如果 MBAM 找不到當地語系化版本，則會顯示針對 HelpDeskURL 參數設定的 URL。

**若要顯示當地語系化的 HelpdeskURL**

1.  在您安裝自助入口網站的伺服器上，開啟 [IIS]，然後流覽至 [**網站 &gt; Microsoft BitLocker 管理及監視 &gt; SelfService &gt; 應用程式設定**]。

2.  在 [**動作**] 窗格中，按一下 [**新增**] 以開啟 [**新增應用程式設定**] 對話方塊。

3.  在 [ **Name** ] （名稱）欄位中，輸入**HelpdeskURL**\ _ &lt; *語言* &gt; ，其中 &lt; [*語言*] &gt; 是 URL 的適當語言代碼。 例如，若要在西班牙文中建立當地語系化的 HelpdeskURL，您將會將參數命名為 HelpdeskURL \ _es。 如需您可以使用的有效語言代碼清單，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)。

4.  在 [**值**] 欄位中，輸入您要顯示給最終使用者的當地語系化 HelpdeskURL。

### 能夠當地語系化自助入口網站注意事項文字

您可以設定在自助入口網站中預設顯示給使用者的當地語系化通知文字。 顯示通知文字的 notice.txt 檔案位於下列根目錄中：

&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\

若要顯示當地語系化的聲明文字，您需要建立當地語系化的 notice.txt 檔案，並將它儲存在下列目錄中的特定語言資料夾中：

&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\

MBAM 會根據下列規則顯示通知文字：

-   如果您在適當的語言資料夾中建立當地語系化的 notice.txt 檔案，MBAM 會顯示當地語系化的聲明文字。

-   如果 MBAM 找不到 notice.txt 檔案的當地語系化版本，則會顯示預設 notice.txt 檔案中的文字。

-   如果 MBAM 找不到預設的 notice.txt 檔案，它會在自助入口網站中顯示預設文字。

**注意**  
如果最終使用者的瀏覽器設定為沒有對應的語言子資料夾或 notice.txt 的語言，則會顯示位於下列根目錄中 notice.txt 檔案中的文字：

&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\



**建立當地語系化的 notice.txt 檔案**

1.  在您安裝自助入口網站的伺服器上，于 &lt; *language* &gt; 下列目錄中建立語言資料夾，其中的 &lt; *語言* &gt; 代表當地語系化語言的名稱：

    &lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\

    **注意**  
    某些語言資料夾已經存在，因此您可能不需要建立一個。 如果您需要建立語言資料夾，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)，瞭解您可以用於 [語言] 資料夾的有效名稱清單 &lt; *language* &gt; 。



2.  建立包含當地語系化通知文字的 notice.txt 檔案。

3.  將 notice.txt 檔案儲存于 [ &lt; *語言*] &gt; 資料夾中。 例如，若要在西班牙文中建立當地語系化的 notice.txt 檔案，您可以將當地語系化的 notice.txt 檔案儲存在下列資料夾中：

    &lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\es-es

## 升級至 MBAM 2.0 SP1


您可以從任何舊版的 MBAM 升級至 MBAM 2.0 SP1。

### 升級 MBAM 基礎結構

您可以將 MBAM 伺服器基礎結構升級為 MBAM 2.0 SP1，如下所示：

**手動就地伺服器取代**：您必須手動卸載現有的 MBAM 伺服器基礎結構，然後再安裝 MBAM 2.0 SP1 server 基礎結構。 您不需要移除資料庫即可進行升級。 相反地，您會選取先前版本的 MBAM 所建立的現有資料庫。 MBAM 2.0 SP1 升級安裝，然後將現有的資料庫移轉至 MBAM 2.0 SP1。

**分散式用戶端升級**：如果您使用的是獨立 MBAM 拓朴，您可以在安裝 MBAM 2.0 SP1 伺服器基礎結構之後，逐漸升級 MBAM 用戶端。

在您升級 MBAM 伺服器基礎結構之後，MBAM 1.0 或2.0 用戶端會成功向 MBAM 2.0 SP1 伺服器報告並儲存修復資料，但合規性將根據目前已安裝的 MBAM 用戶端版本所提供的原則而定。 若要針對 MBAM 2.0 SP1 原則啟用報告功能，您必須將用戶端電腦升級為 MBAM 2.0 SP1。 您可以將用戶端電腦升級至 MBAM 2.0 SP1 用戶端，而不卸載先前的用戶端，而且用戶端將根據 MBAM 2.0 SP1 原則，開始套用並報告。

如需升級 MBAM 伺服器的詳細資訊，請參閱[從先前版本的 MBAM 升級](upgrading-from-previous-versions-of-mbam.md)。

### 將 MBAM 用戶端升級為 MBAM 2.0 SP1

若要將使用者電腦升級至 MBAM 2.0 SP1 用戶端，請在每個用戶端電腦上執行**MbamClientSetup.exe** 。 安裝程式會自動將用戶端更新至 MBAM 2.0 SP1 用戶端。 安裝之後，用戶端電腦不需要重新開機，且 MBAM 2.0 SP1 用戶端就會開始套用 MBAM 2.0 SP1 原則，並針對其進行報告。

如果您使用的是 Configuration Manager 的 MBAM，您必須將 MBAM 用戶端電腦升級至 MBAM 2.0 SP1。

如需升級 MBAM 用戶端電腦的詳細資訊，請參閱[從先前版本的 MBAM 升級](upgrading-from-previous-versions-of-mbam.md)。

## 使用 Configuration Manager 安裝或升級至 MBAM 2.0 SP1


本節說明當您安裝 MBAM 2.0 SP1 做為新安裝或升級到舊版 MBAM 2.0 SP1 時的需求。

### 如果您使用 MBAM 與 Configuration Manager，請安裝 MBAM 2.0 SP1 所需的檔案

如果您是第一次安裝 MBAM，而您是使用 MBAM 2.0 SP1 搭配 System Center Configuration Manager，您必須建立或編輯 mof 檔案，讓 MBAM 能夠正確地使用 Configuration Manager。

-   **configuration mof 檔案**

    -   如果您使用的是 Configuration Manager 2007，您必須編輯 configuration （mof 檔案）：**如果您升級至 MBAM 2.0 SP1，且您將 MBAM 與 Configuration Manager 2007 結合使用**（遵循此專案），則必須先更新 configuration （mof）檔。

    -   如果您使用的是系統中心 2012 Configuration Manager，請按照[編輯 configuration. mof](edit-the-configurationmof-file.md)檔案中的指示編輯 configuration mof 檔案。

-   **sms \ _def 的 mof**檔案-依照[建立或編輯 sms \ _def mof](create-or-edit-the-sms-defmof-file.md)檔案中的指示進行。

### 如果您升級至 MBAM 2.0 SP1，且您將 MBAM 與 Configuration Manager 2007 結合使用，請更新 configuration mof 檔案

如果您要升級至 MBAM 2.0 SP1，且您是使用 MBAM 搭配 Configuration Manager 2007，則您必須更新 configuration mof 檔案，以確保 MBAM 2.0 SP1 正常運作。

**更新 configuration （mof）檔：**

1.  在 Configuration Manager 伺服器上，流覽至 Configuration （mof）檔案的位置：

    &lt;CMInstallLocation &gt; \\Inboxes\\clifiles.src\\hinv\\

    在預設安裝中，安裝位置是%systemdrive%\\Program Files （x86） \\Microsoft Configuration Manager。

2.  查看您在 configuration. mof 檔案中附加的程式碼區塊，然後將它刪除。 程式碼區塊會與下列步驟中所示類似。

3.  複製下列程式碼塊，然後將它附加到 configuration. mof 檔案中，將下列所需的 MBAM 類別新增到檔案中：

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL) 

    [Union, ViewSources{"select DeviceId, BitlockerPersistentVolumeId, BitLockerManagementPersistentVolumeId, BitLockerManagementVolumeType, DriveLetter, Compliant, ReasonsForNonCompliance, KeyProtectorTypes, EncryptionMethod, ConversionStatus, ProtectionStatus, IsAutoUnlockEnabled from Mbam_Volume"}, ViewSpaces{"\\\\.\\root\\microsoft\\mbam"}, dynamic, Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class Win32_BitLockerEncryptionDetails
    {
        [PropertySources{"DeviceId"},key]
        String     DeviceId;
        [PropertySources{"BitlockerPersistentVolumeId"}]
        String     BitlockerPersistentVolumeId;
        [PropertySources{"BitLockerManagementPersistentVolumeId"}]
        String     MbamPersistentVolumeId;
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        [PropertySources{"BitLockerManagementVolumeType"}]
        SInt32     MbamVolumeType;
        [PropertySources{"DriveLetter"}]
        String     DriveLetter;
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        [PropertySources{"Compliant"}]
        SInt32     Compliant;
        [PropertySources{"ReasonsForNonCompliance"}]
        SInt32     ReasonsForNonCompliance[];
        [PropertySources{"KeyProtectorTypes"}]
        SInt32     KeyProtectorTypes[];
        [PropertySources{"EncryptionMethod"}]
        SInt32     EncryptionMethod;
        [PropertySources{"ConversionStatus"}]
        SInt32     ConversionStatus;
        [PropertySources{"ProtectionStatus"}]
        SInt32     ProtectionStatus;
        [PropertySources{"IsAutoUnlockEnabled"}]
        Boolean     IsAutoUnlockEnabled;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
     [DYNPROPS]
    Class Win32Reg_MBAMPolicy
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate;
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

     [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy
    {
        KeyName="BitLocker policy";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy_64", NOFAIL)
    [DYNPROPS]
    Class Win32Reg_MBAMPolicy_64
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

    [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy_64
    {
        KeyName="BitLocker policy 64";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
         [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,OperatingSystemSKU from Win32_OperatingSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_OperatingSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"OperatingSystemSKU"}]
        uint32     SKU;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,PCSystemType from Win32_ComputerSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_ComputerSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"PCSystemType"}]
        uint16     PCSystemType;
    };

    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================

    ```

### MBAM 2.0 SP1 的翻譯

MBAM 2.0 SP1 現已提供下列語言：

-   英文（美國） en
-   法文（法國） fr-fr
-   義大利文（義大利） it
-   德國（德國） de
-   西班牙文，國際排序（西班牙） es
-   韓文（韓國） ko-KR
-   日文（日本） ja-jp
-   葡萄牙文（巴西） pt-BR
-   俄文（俄羅斯） ru-RU
-   繁體中文 zh-cn&platform-幼圓
-   簡體中文 zh-cn&platform-CN

## 如何取得 MDOP 技術

MBAM 2.0 SP1 是 Microsoft 桌面優化套件（MDOP）的一部分。 MDOP 是 Microsoft 軟體保證的一部分。 如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 相關主題

[MBAM 2.0 SP1 版本資訊](release-notes-for-mbam-20-sp1.md)









