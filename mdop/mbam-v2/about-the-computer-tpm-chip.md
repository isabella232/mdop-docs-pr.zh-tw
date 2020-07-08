---
title: 關於電腦 TPM 晶片
description: 關於電腦 TPM 晶片
author: dansimp
ms.assetid: 6f1cf18c-277a-4932-886d-14202ca8d175
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6df54dc8085c398bacc508fdbbb79a30b0e4204
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810011"
---
# 關於電腦 TPM 晶片


BitLocker 在與受信任的平臺模組（TPM）晶片搭配使用時，提供額外的保護。 TPM 晶片是電腦製造商在許多較新的電腦上安裝的硬體元件。 Microsoft BitLocker 管理和監控（MBAM）除了 TPM 晶片之外，還會使用 BitLocker，以協助提供額外的資料保護，並確保您的電腦未被篡改。

## 如何設定您的 TPM


當您在電腦上啟動 BitLocker 磁片磁碟機加密嚮導時，如果您的組織已將 BitLocker 設定為使用 TPM 晶片，BitLocker 會檢查 TPM 晶片。 如果 BitLocker 找到相容的 TPM 晶片，系統可能會提示您重新開機電腦，以啟用 TPM 晶片以供使用。 重新開機電腦之後，請依照指示在 BIOS 中設定 TPM 晶片（BIOS 是電腦軟體的 Windows 層）。

設定 BitLocker 之後，您可以在 Windows [控制台] 中開啟 [BitLocker 加密選項] 工具，然後選取 [ **TPM 管理**]，以存取 TPM 晶片的其他相關資訊。

**記事** 您必須具備電腦的系統管理認證，才能存取此工具。

 

在 TPM 失敗、BIOS 中的變更或特定的 Windows 更新，BitLocker 會鎖定您的電腦，並要求您與技術支援人員解除鎖定電腦。 您必須提供電腦的名稱以及電腦的網域。 [技術支援中心] 可提供密碼檔案，可用於解除鎖定電腦。

## 疑難排解 TPM 問題


如果 TPM 失敗、在 BIOS 中變更，或發生某些 Windows 更新，BitLocker 會鎖定您的電腦，並要求您與技術支援人員解除鎖定。 您必須提供電腦的名稱以及電腦的網域。 技術支援中心可提供密碼檔案，您可以用來解除鎖定電腦。

## 相關主題


[協助使用者管理 BitLocker](helping-end-users-manage-bitlocker.md)

[使用您的 PIN 碼或密碼](using-your-pin-or-password.md)

 

 





