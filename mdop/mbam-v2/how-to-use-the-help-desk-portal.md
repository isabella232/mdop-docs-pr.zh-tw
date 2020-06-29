---
title: 如何使用技術支援入口網站
description: 如何使用技術支援入口網站
author: dansimp
ms.assetid: c27f7737-10c8-4164-9de8-57987292c89c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8813fbe9a7b6980b656ecc673ac4ed618c4cf7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811690"
---
# 如何使用技術支援入口網站


MBAM 管理和監控網站（也稱為 [技術支援中心] 入口網站）是一種系統管理介面，可作為 Microsoft BitLocker 管理與監控（MBAM）伺服器基礎結構的一部分安裝的 BitLocker 磁碟機加密。 下列各節說明您可以如何使用此網站來查看報告、復原使用者的磁片磁碟機，以及管理使用者的 TPMs。

## <a href="" id="bkmk-reports"></a>報告


MBAM 會從 Active Directory 和用戶端電腦收集資訊，這可讓您執行不同的報告，以監控 BitLocker 使用量與合規性。 您可以使用 [管理] 和 [監控] 網站的 [**報告**] 區段來產生有關企業合規性、個別電腦及金鑰復原活動的報告。 如需每個報告的描述，請參閱[瞭解 MBAM 報告](understanding-mbam-reports-mbam-2.md)。

**存取報表**

1.  開啟網頁瀏覽器並流覽至 MBAM 管理和監控網站。

2.  選取左窗格中的 [**報表**]。

3.  從上方的功能表列中，選取您要產生的報表類型。 若要儲存報表，請按一下 [報表] 功能表列上的 [**匯出**] 按鈕。

如需如何執行 MBAM 報告的其他資訊，請參閱[如何產生 MBAM 報告](how-to-generate-mbam-reports-mbam-2.md)。

## <a href="" id="bkmk-drirec"></a>磁片磁碟機恢復


[管理與監視] 網站的 [**磁碟機**復原] 功能可讓擁有特定管理員角色（例如，技術支援人員使用者）存取已由 MBAM 用戶端收集的復原金鑰資料的使用者。 此資料可用於在 BitLocker 進入復原模式時存取受 BitLocker 保護的磁片磁碟機。 如需如何復原復原模式中磁片磁碟機的指示，請參閱[如何在復原模式中復原磁片磁碟機](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)。

您也可以復原已移動或損毀的磁片磁碟機：

-   [如何修復已移動的磁碟機](how-to-recover-a-moved-drive-mbam-2.md)

-   [如何修復損毀的磁碟機](how-to-recover-a-corrupted-drive-mbam-2.md)

如需有關如何復原受 BitLocker 保護的磁碟機的其他資訊，請參閱[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)。

## <a href="" id="bkmk-manatpm"></a>管理 TPM


管理和監控網站的 [管理 TPM] 功能可為使用者提供特定的系統管理員角色（例如，「MBAM 技術支援人員」）存取已由 MBAM 用戶端收集的 TPM 資料。 在 TPM 封鎖中，系統管理員可以使用 [管理] 和 [監視] 網站來取得解除鎖定 TPM 所需的密碼檔。 如需如何在 TPM 封鎖之後重設 TPM 的指示，請參閱[如何重設 Tpm 封鎖](how-to-reset-a-tpm-lockout-mbam-2.md)。

## <a href="" id="bkmk-helpdesk"></a> MBAM 技術支援中心任務


您可以使用管理和監控網站進行許多管理工作，例如管理受 BitLocker 保護的硬體、恢復磁片磁碟機，以及執行報告。 根據預設，管理和監控網站的 URL 是 HTTP:// &lt; *MBAMAdministrationServername* &gt; ，不過您可以在安裝程式期間對它進行自訂。

**記事** 若要存取 [管理] 和 [監視] 網站提供的各種功能，您必須擁有與您的使用者帳戶相關聯的適當角色。 如需瞭解使用者角色的詳細資訊，請參閱[如何管理 MBAM 系統管理員角色](how-to-manage-mbam-administrator-roles-mbam-2.md)。

 

使用下列連結，以尋找您可以使用 [管理和監控] 網站執行的工作相關資訊：

-   [如何重設 TPM 鎖定](how-to-reset-a-tpm-lockout-mbam-2.md)

-   [如何修復處於修復模式的磁碟機](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

-   [如何修復已移動的磁碟機](how-to-recover-a-moved-drive-mbam-2.md)

-   [如何修復損毀的磁碟機](how-to-recover-a-corrupted-drive-mbam-2.md)

-   [如何判斷遺失的電腦之 BitLocker 加密狀態](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

 

 





