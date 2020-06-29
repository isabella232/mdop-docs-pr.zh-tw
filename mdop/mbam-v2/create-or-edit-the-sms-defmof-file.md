---
title: 建立或編輯 Sms \ _def 的 mof 檔案
description: 建立或編輯 Sms \ _def 的 mof 檔案
author: dansimp
ms.assetid: d1747e43-484e-4031-a63b-6342fe588aa2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/04/2017
ms.openlocfilehash: 15f1d1a1c19cb9b19b7d83534e035d5410720ce9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809999"
---
# <span data-ttu-id="b801a-103">建立或編輯 Sms \ _def 的 mof 檔案</span><span class="sxs-lookup"><span data-stu-id="b801a-103">Create or Edit the Sms\_def.mof File</span></span>


<span data-ttu-id="b801a-104">若要讓用戶端電腦透過 MBAM Configuration Manager 報告來報告 BitLocker 相容性詳細資料，您必須建立或編輯 Sms \ _def. mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="b801a-104">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager reports, you have to create or edit the Sms\_def.mof file.</span></span>

<span data-ttu-id="b801a-105">如果您使用的是 SystemCenter2012 ConfigurationManager，則必須建立檔案。</span><span class="sxs-lookup"><span data-stu-id="b801a-105">If you are using SystemCenter2012 ConfigurationManager, you must create the file.</span></span>

<span data-ttu-id="b801a-106">在 Configuration Manager 2007 中，該檔案已存在，因此您只需要進行編輯。</span><span class="sxs-lookup"><span data-stu-id="b801a-106">In Configuration Manager 2007, the file already exists, so you only have to edit it.</span></span> <span data-ttu-id="b801a-107">**不要覆寫現有**的檔案。</span><span class="sxs-lookup"><span data-stu-id="b801a-107">**Do not overwrite the existing file**.</span></span>

<span data-ttu-id="b801a-108">在下列各節中，完成與您所使用之 Configuration Manager 版本相對應的指示。</span><span class="sxs-lookup"><span data-stu-id="b801a-108">In the following sections, complete the instructions that correspond to the version of Configuration Manager that you are using.</span></span>

**<span data-ttu-id="b801a-109">若要建立 Sms \ _def SystemCenter2012 ConfigurationManager 的 mof 檔案</span><span class="sxs-lookup"><span data-stu-id="b801a-109">To create the Sms\_def.mof file for SystemCenter2012 ConfigurationManager</span></span>**

1.  <span data-ttu-id="b801a-110">在 Configuration Manager 伺服器上，流覽至您必須建立 Sms \ _def mof 檔案（例如桌面）的位置。</span><span class="sxs-lookup"><span data-stu-id="b801a-110">On the Configuration Manager Server, browse to the location where you have to create the Sms\_def.mof file, for example, the Desktop.</span></span>

2.  <span data-ttu-id="b801a-111">建立名為**Sms \ _def**的文字檔，然後複製下列程式碼，以使用下列 Sms \ _def 填入檔案。 mof MBAM 類別：</span><span class="sxs-lookup"><span data-stu-id="b801a-111">Create a text file called **Sms\_def.mof** and copy the following code to populate the file with the following Sms\_def.mof MBAM classes:</span></span>

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL)
    [ SMS_Report (TRUE),
      SMS_Group_Name ("BitLocker Encryption Details"),
      SMS_Class_ID ("MICROSOFT|BITLOCKER_DETAILS|1.0")]
    class Win32_BitLockerEncryptionDetails : SMS_Class_Template
    {
        [ SMS_Report (TRUE), key ]
        String     DeviceId;
        [ SMS_Report (TRUE) ]
        String     BitlockerPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        String     MbamPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        SInt32     MbamVolumeType;
        [ SMS_Report (TRUE) ]
        String     DriveLetter;
        [ SMS_Report (TRUE) ]
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        SInt32     Compliant;
        [ SMS_Report (TRUE) ]
        SInt32     ReasonsForNonCompliance[];
        [ SMS_Report (TRUE) ]
        SInt32     KeyProtectorTypes[];
        [ SMS_Report (TRUE) ]
        SInt32     EncryptionMethod;
        [ SMS_Report (TRUE) ]
        SInt32     ConversionStatus;
        [ SMS_Report (TRUE) ]
        SInt32     ProtectionStatus;
        [ SMS_Report (TRUE) ]
        Boolean     IsAutoUnlockEnabled;
    };
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")

    #pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
    [ SMS_Report(TRUE),
      SMS_Group_Name("BitLocker Policy"),
      SMS_Class_ID("MICROSOFT|MBAM_POLICY|1.0")]

    Class Win32Reg_MBAMPolicy: SMS_Class_Template
    {
        [SMS_Report(TRUE),key]
        string KeyName;

        //General encryption requirements
        [SMS_Report(TRUE)]
        UInt32    OsDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    EncryptionMethod;

        //Required protectors properties
        [ SMS_Report (TRUE) ]
        UInt32    OsDriveProtector;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveAutoUnlock;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        //Policy not enforced (0), enforced (1), pending user exemption request (2) or exempted user (3)
        [SMS_Report(TRUE)]
        Uint32    MBAMPolicyEnforced;
        [SMS_Report(TRUE)]
        string    LastConsoleUser;
        //Date of the exemption request of the last logged on user,
        //or the first date the exemption was granted to him on this machine.
        [SMS_Report(TRUE)]
        datetime  UserExemptionDate;
        //Errors encountered by MBAM agent.
        [ SMS_Report (TRUE) ]
        UInt32    MBAMMachineError;
        [ SMS_Report (TRUE) ]
        string    EncodedComputerName;
    };

    //Read Win32_OperatingSystem.SKU WMI property in a new class - because SKU is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Operating System Ex"),
      SMS_Class_ID   ("MICROSOFT|OPERATING_SYSTEM_EXT|1.0") ]
    class CCM_OperatingSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
            string     Name;
        [SMS_Report (TRUE) ]
            uint32     SKU;
    };

    //Read Win32_ComputerSystem.PCSystemType WMI property in a new class - because PCSystemType is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Computer System Ex"),
      SMS_Class_ID   ("MICROSOFT|COMPUTER_SYSTEM_EXT|1.0") ]
    class CCM_ComputerSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
        string     Name;
        [SMS_Report (TRUE) ]
        uint16     PCSystemType;
    };
    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================
    ```

3.  <span data-ttu-id="b801a-112">執行下列動作，匯入**Sms \ _def 的 mof**檔案：</span><span class="sxs-lookup"><span data-stu-id="b801a-112">Import the **Sms\_def.mof** file by doing the following:</span></span>

    1.  <span data-ttu-id="b801a-113">開啟 [ **SystemCenter2012 ConfigurationManager] 主控台**，然後選取 [**管理**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b801a-113">Open the **SystemCenter2012 ConfigurationManager console** and select the **Administration** tab.</span></span>

    2.  <span data-ttu-id="b801a-114">在 [**管理**] 索引標籤上，選取 [**用戶端設定**]。</span><span class="sxs-lookup"><span data-stu-id="b801a-114">On the **Administration** tab, select **Client Settings**.</span></span>

    3.  <span data-ttu-id="b801a-115">以滑鼠右鍵按一下 [**預設用戶端設定**]，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="b801a-115">Right-click **Default Client Settings**, and then select **Properties**.</span></span>

    4.  <span data-ttu-id="b801a-116">在 [**預設設定**] 視窗中，選取 [**硬體清點**]。</span><span class="sxs-lookup"><span data-stu-id="b801a-116">In the **Default Settings** window, select **Hardware Inventory**.</span></span>

    5.  <span data-ttu-id="b801a-117">按一下 [**設定類別**]，然後按一下 [匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="b801a-117">Click **Set Classes**, and then click **Import**.</span></span>

    6.  <span data-ttu-id="b801a-118">在開啟的瀏覽器中，選取您**的 mof**檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="b801a-118">In the browser that opens, select your **.mof** file, and then click **Open**.</span></span> <span data-ttu-id="b801a-119">隨即會開啟 [匯**入摘要**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="b801a-119">The **Import Summary** window opens.</span></span>

    7.  <span data-ttu-id="b801a-120">在 [匯**入摘要**] 視窗中，確認已選取 [匯入硬體清單類別和類別設定] 的選項，然後按一下 [匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="b801a-120">In the **Import Summary** window, ensure that the option to import both hardware inventory classes and class settings is selected, and then click **Import**.</span></span>

    8.  <span data-ttu-id="b801a-121">在 [**硬體清查類別**] 視窗和 [**預設設定**] 視窗中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b801a-121">In both the **Hardware Inventory Classes** window and the **Default Settings** window, click **OK**.</span></span>

4.  <span data-ttu-id="b801a-122">啟用**Win32 \ _Tpm**類別，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b801a-122">Enable the **Win32\_Tpm** class as follows:</span></span>

    1.  <span data-ttu-id="b801a-123">開啟 [ **SystemCenter2012 ConfigurationManager] 主控台**，然後選取 [**管理**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b801a-123">Open the **SystemCenter2012 ConfigurationManager console** and select the **Administration** tab.</span></span>

    2.  <span data-ttu-id="b801a-124">在 [**管理**] 索引標籤上，選取 [**用戶端設定**]。</span><span class="sxs-lookup"><span data-stu-id="b801a-124">On the **Administration** tab, select **Client Settings**.</span></span>

    3.  <span data-ttu-id="b801a-125">以滑鼠右鍵按一下 [**預設用戶端設定**]，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="b801a-125">Right-click **Default Client Settings**, and then select **Properties**.</span></span>

    4.  <span data-ttu-id="b801a-126">在 [**預設設定**] 視窗中，選取 [**硬體清點**]。</span><span class="sxs-lookup"><span data-stu-id="b801a-126">In the **Default Settings** window, select **Hardware Inventory**.</span></span>

    5.  <span data-ttu-id="b801a-127">按一下 [**設定班級**]。</span><span class="sxs-lookup"><span data-stu-id="b801a-127">Click **Set Classes**.</span></span>

    6.  <span data-ttu-id="b801a-128">在主視窗中向下滾動，然後選取 [ **TPM （Win32 \ _Tpm）** ] 類別。</span><span class="sxs-lookup"><span data-stu-id="b801a-128">In the main window, scroll down, and then select the **TPM (Win32\_Tpm)** class.</span></span>

    7.  <span data-ttu-id="b801a-129">在 [ **TPM**] 底下，確認已選取 [ **SpecVersion** ] 屬性。</span><span class="sxs-lookup"><span data-stu-id="b801a-129">Under **TPM**, ensure that the **SpecVersion** property is selected.</span></span>

    8.  <span data-ttu-id="b801a-130">在 [**硬體清查類別**] 視窗和 [**預設設定**] 視窗中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b801a-130">In both the **Hardware Inventory Classes** window and the **Default Settings** window, click **OK**.</span></span>

**<span data-ttu-id="b801a-131">若要編輯 Configuration Manager 2007 的 sms \ _def mof 檔案</span><span class="sxs-lookup"><span data-stu-id="b801a-131">To edit the sms\_def.mof file for Configuration Manager 2007</span></span>**

1.  <span data-ttu-id="b801a-132">在 Configuration Manager 伺服器上，流覽至**sms \ _def mof**檔案的位置：</span><span class="sxs-lookup"><span data-stu-id="b801a-132">On the Configuration Manager Server, browse to the location of the **sms\_def.mof** file:</span></span>

    <span data-ttu-id="b801a-133">&lt;CMInstallLocation &gt; \\Inboxes\\clifiles.src\\hinv</span><span class="sxs-lookup"><span data-stu-id="b801a-133">&lt;CMInstallLocation&gt;\\Inboxes\\clifiles.src\\hinv</span></span>\\

    <span data-ttu-id="b801a-134">在預設安裝中，安裝位置是% systemdrive% \\Program Files （x86） \\Microsoft Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="b801a-134">On a default installation, the installation location is %systemdrive% \\Program Files (x86)\\Microsoft Configuration Manager.</span></span>

2.  <span data-ttu-id="b801a-135">複製下列程式碼，然後將它附加到**Sms \ _def 的 mof**檔案中，將下列必要的 MBAM 類別新增到檔案中：</span><span class="sxs-lookup"><span data-stu-id="b801a-135">Copy the following code, and then append it to **Sms\_def.mof** file to add the following required MBAM classes to the file:</span></span>

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL)
    [ SMS_Report (TRUE),
      SMS_Group_Name ("BitLocker Encryption Details"),
      SMS_Class_ID ("MICROSOFT|BITLOCKER_DETAILS|1.0")]
    class Win32_BitLockerEncryptionDetails : SMS_Class_Template
    {
        [ SMS_Report (TRUE), key ]
        String     DeviceId;
        [ SMS_Report (TRUE) ]
        String     BitlockerPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        String     MbamPersistentVolumeId;
        [ SMS_Report (TRUE) ]
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        SInt32     MbamVolumeType;
        [ SMS_Report (TRUE) ]
        String     DriveLetter;
        [ SMS_Report (TRUE) ]
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        SInt32     Compliant;
        [ SMS_Report (TRUE) ]
        SInt32     ReasonsForNonCompliance[];
        [ SMS_Report (TRUE) ]
        SInt32     KeyProtectorTypes[];
        [ SMS_Report (TRUE) ]
        SInt32     EncryptionMethod;
        [ SMS_Report (TRUE) ]
        SInt32     ConversionStatus;
        [ SMS_Report (TRUE) ]
        SInt32     ProtectionStatus;
        [ SMS_Report (TRUE) ]
        Boolean     IsAutoUnlockEnabled;
    };

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
    [ SMS_Report(TRUE),
      SMS_Group_Name("BitLocker Policy"),
      SMS_Class_ID("MICROSOFT|MBAM_POLICY|1.0"),
      SMS_Context_1("__ProviderArchitecture=32|uint32"),
      SMS_Context_2("__RequiredArchitecture=true|boolean")]
    Class Win32Reg_MBAMPolicy: SMS_Class_Template
    {
        [SMS_Report(TRUE),key]
        string KeyName;

        //General encryption requirements
        [SMS_Report(TRUE)]
        UInt32    OsDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    EncryptionMethod;

        //Required protectors properties
        [ SMS_Report (TRUE) ]
        UInt32    OsDriveProtector;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveAutoUnlock;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDrivePassphrase;

        //MBAM Agent fields
        //Policy not enforced (0), enforced (1), pending user exemption request (2) or exempted user (3)
        [SMS_Report(TRUE)]
        Uint32    MBAMPolicyEnforced;
        [SMS_Report(TRUE)]
        string    LastConsoleUser;
        //Date of the exemption request of the last logged on user,
        //or the first date the exemption was granted to him on this machine.
        [SMS_Report(TRUE)]
        datetime  UserExemptionDate;
        //Errors encountered by MBAM agent.
        [ SMS_Report (TRUE) ]
        UInt32    MBAMMachineError;
        // Encoded Computer Name
        [ SMS_Report (TRUE) ]
        string    EncodedComputerName;
    };

    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("Win32Reg_MBAMPolicy_64", NOFAIL)
    [ SMS_Report(TRUE),
      SMS_Group_Name("BitLocker Policy"),
      SMS_Class_ID("MICROSOFT|MBAM_POLICY|1.0"),
      SMS_Context_1("__ProviderArchitecture=64|uint32"),
      SMS_Context_2("__RequiredArchitecture=true|boolean")]
    Class Win32Reg_MBAMPolicy_64: SMS_Class_Template
    {
        [SMS_Report(TRUE),key]
        string KeyName;

        //General encryption requirements
        [SMS_Report(TRUE)]
        UInt32    OsDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveEncryption;
        [ SMS_Report (TRUE) ]
        UInt32    EncryptionMethod;

        //Required protectors properties
        [ SMS_Report (TRUE) ]
        UInt32    OsDriveProtector;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDriveAutoUnlock;
        [ SMS_Report (TRUE) ]
        UInt32    FixedDataDrivePassphrase;

        //MBAM Agent fields
        //Policy not enforced (0), enforced (1), pending user exemption request (2) or exempted user (3)
        [SMS_Report(TRUE)]
        Uint32    MBAMPolicyEnforced;
        [SMS_Report(TRUE)]
        string    LastConsoleUser;
        //Date of the exemption request of the last logged on user,
        //or the first date the exemption was granted to him on this machine.
        [SMS_Report(TRUE)]
        datetime  UserExemptionDate;
        //Errors encountered by MBAM agent.
        [ SMS_Report (TRUE) ]
        UInt32    MBAMMachineError;
        // Encoded Computer Name
        [ SMS_Report (TRUE) ]
        string    EncodedComputerName;
    };

    //Read Win32_OperatingSystem.SKU WMI property in a new class - because SKU is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Operating System Ex"),
      SMS_Class_ID   ("MICROSOFT|OPERATING_SYSTEM_EXT|1.0") ]
    class CCM_OperatingSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
            string     Name;
        [SMS_Report (TRUE) ]
            uint32     SKU;
    };

    //Read Win32_ComputerSystem.PCSystemType WMI property in a new class - because PCSystemType is not available before Vista.
    #pragma namespace ("\\\\.\\root\\cimv2\\SMS")
    #pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [ SMS_Report     (TRUE),
      SMS_Group_Name ("Computer System Ex"),
      SMS_Class_ID   ("MICROSOFT|COMPUTER_SYSTEM_EXT|1.0") ]
    class CCM_ComputerSystemExtended : SMS_Class_Template
    {
        [SMS_Report (TRUE), key ]
        string     Name;
        [SMS_Report (TRUE) ]
        uint16     PCSystemType;
    };

    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================
    ```

3.  <span data-ttu-id="b801a-136">修改**Win32 \ _Tpm**類別，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b801a-136">Modify the **Win32\_Tpm** class as follows:</span></span>

    -   <span data-ttu-id="b801a-137">在類別屬性中將**SMS \ _REPORT**設定為**TRUE** 。</span><span class="sxs-lookup"><span data-stu-id="b801a-137">Set **SMS\_REPORT** to **TRUE** in the class attributes.</span></span>

    -   <span data-ttu-id="b801a-138">在**SpecVersion**屬性屬性中將**SMS \ _REPORT**設定為**TRUE** 。</span><span class="sxs-lookup"><span data-stu-id="b801a-138">Set **SMS\_REPORT** to **TRUE** in the **SpecVersion** property attribute.</span></span>

## <span data-ttu-id="b801a-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="b801a-139">Related topics</span></span>


[<span data-ttu-id="b801a-140">如何建立或編輯 mof 檔案</span><span class="sxs-lookup"><span data-stu-id="b801a-140">How to Create or Edit the mof Files</span></span>](how-to-create-or-edit-the-mof-files.md)

[<span data-ttu-id="b801a-141">使用設定管理員來部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="b801a-141">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





