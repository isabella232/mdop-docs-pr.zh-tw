---
title: 如何將 MBAM 用戶端部署為 Windows 部署的一部分
description: 如何將 MBAM 用戶端部署為 Windows 部署的一部分
author: dansimp
ms.assetid: 67387de7-8b02-4412-9850-3b8d8e5c18af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d75e5748167d2d4866f98e9d3611584067ecd418
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810665"
---
# 如何將 MBAM 用戶端部署為 Windows 部署的一部分


Microsoft BitLocker 管理和監控（MBAM）用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。 如果有受信任的平臺模組（TPM）晶片的電腦，則可在用戶端電腦上啟用 BitLocker 管理和加密等，將 BitLocker 用戶端整合到組織中。

**注意**  
若要查看 Microsoft BitLocker 管理及監視用戶端系統需求，請參閱[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。



在 Windows 部署的初始影像階段中使用 BitLocker 加密用戶端電腦，可以降低在組織中執行 MBAM 所需的管理負荷。 它也可確保已部署的每個電腦都已執行 BitLocker 且設定正確。

**注意**  
本主題中的程式說明如何修改 Windows 註冊。 無法正確使用登錄編輯程式，可能會導致嚴重問題，可能需要重新安裝 Windows。 Microsoft 無法保證無法正確使用登錄編輯程式所造成的問題，因此無法解決。 使用登錄編輯程式的風險由您自負。



**若要將電腦加密為 Windows 部署的一部分**

1.  如果您的組織打算在 BitLocker 中使用受信任的平臺模組（TPM）保護器或 TPM + PIN 保護器選項，您必須先啟動 TPM 晶片，然後才能開始部署 MBAM。 當您啟用 TPM 晶片時，您會在稍後的程式中避免重新開機，並確保根據貴組織的需求正確地設定 TPM 晶片。 您必須在電腦的 BIOS 中手動啟用 TPM 晶片。

    **注意**  
    某些廠商提供的工具可在作業系統中從 BIOS 開啟及啟動 TPM 晶片。 如需有關如何設定 TPM 晶片的詳細資訊，請參閱製造商檔。



2.  安裝 Microsoft BitLocker 管理及監視用戶端代理程式。

3.  將電腦加入網域（建議使用）。

    -   如果電腦未加入網域，則無法將恢復密碼儲存在 MBAM 金鑰復原服務中。 根據預設，除非能儲存復原金鑰，否則 MBAM 不允許進行加密。

    -   如果電腦在修復金鑰儲存在 MBAM 伺服器上之前以 [復原] 模式啟動，電腦必須是 reimaged。 沒有可用的恢復方法。

4.  以系統管理員身分執行命令提示字元、停止 MBAM 服務，然後將服務設定為 [**手動**] 或 [**按需**]，然後輸入下列命令：

    **net stop mbamagent**

    **sc config mbamagent start = 要求**

5.  將 MBAM agent 的登錄設定設為 [忽略群組原則]，並執行電腦版 TPM，**只**需執行**Regedit**，然後從 c:\\program files Files\\Microsoft\\MDOP 匯入登錄機碼範本 MBAM\\MBAMDeploymentKeyTemplate.reg。

6.  在 regedit 中，移至 HKLM\\SOFTWARE\\Microsoft\\MBAM，並設定下表所列的設定。

    登錄專案

    組態設定

    DeploymentTime

    0 = 關閉

    1 = 使用部署時間原則設定（預設）

    UseKeyRecoveryService

    0 = 不使用金鑰保管（這種情況下，不需要接下來的兩個登錄專案）

    1 = 在金鑰還原系統中使用金鑰委託（預設）

    建議：電腦必須能夠與金鑰復原服務進行通訊。 繼續進行之前，請先確認電腦可以與服務進行通訊。

    KeyRecoveryOptions

    0 = 僅限上傳復原金鑰

    1 = 上傳復原金鑰和金鑰復原套件（預設）

    KeyRecoveryServiceEndPoint

    將此值設定為金鑰復原網頁伺服器的 URL，例如，HTTP://[ &lt; 電腦名稱稱] &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。



~~~
**Note**  
MBAM policy or registry values can be set here to override previously set values.
~~~



7. MBAM agent 會在 MBAM 用戶端部署期間重新開機系統。 當您準備好進行此重新開機時，請以系統管理員的命令提示字元執行下列命令：

   **net start mbamagent**

8. 當電腦重新開機且 BIOS 提示您接受 TPM 變更時，請接受變更。

9. 在 Windows 用戶端作業系統影像程式期間，當您準備好要開始加密時，請重新開機 MBAM agent 服務，並將命令提示字元設為系統管理員，然後輸入下列命令，以將 [開始] 設定為 [**自動**]：

   **sc config mbamagent start = auto**

   **net start mbamagent**

10. 執行 Regedit 並移至 HKLM\\SOFTWARE\\Microsoft 登錄專案，以移除旁路登錄值。 若要刪除**MBAM**節點，請以滑鼠右鍵按一下節點，然後按一下 [**刪除**]。

## 相關主題


[部署 MBAM 2.0 用戶端](deploying-the-mbam-20-client-mbam-2.md)









