---
title: MED-V 作業的安全性最佳做法
description: MED-V 作業的安全性最佳做法
author: dansimp
ms.assetid: 231e2b9a-8b49-42fe-93b5-2ef12fe17bac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4353a15c756dba8cf44f530c2077546e3f9288cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811132"
---
# MED-V 作業的安全性最佳做法


身為授權的管理員，您有責任在部署 MED-V 工作區期間和之後，保護使用者的資訊並維持組織的安全性。 具體說來，請考慮下列問題。

**在 med-v 工作區中自訂 Internet Explorer**。 較舊版本的 Windows 作業系統和 Internet Explorer 與目前版本不一樣安全。 因此，MED-V 工作區中的 Internet Explorer 會設定為防止流覽及其他可能帶來安全性風險的活動。 此外，MED-V 工作區中 Internet Explorer 的 [網際網路安全性區域] 設定會設定為最高等級。 根據預設，當您建立 MED-V 工作區套件時，會在 MED-V 工作區包裝程式中設定這兩個設定。

透過使用 Internet Explorer 管理工具組（IEAK）或變更 MED-V 工作區包裝程式中的預設值，您可以在 MED-V 工作區中自訂 Internet Explorer。 不過，請注意，如果您在 MED-V 工作區中自訂 Internet Explorer 的方式是不安全，您可以將貴組織暴露給舊版 Internet Explorer 中存在的安全性風險。

從安全性的觀點來看，在 MED-V 工作區中管理 Internet Explorer 的最佳做法如下：

-   建立 MED-V 工作區套件時，請保留預設設定，以便將 MED-V 工作區中的 Internet Explorer 設定為可避免流覽及其他可能帶來安全性風險的活動。

-   建立 MED-V 工作區套件時，請保留預設設定，讓網際網路安全區域的安全性設定保持在最高等級。

-   設定您的企業 proxy 或 Internet Explorer 內容審查程式，以封鎖您公司內部網路以外的網域。

**針對共用電腦上的所有使用者設定 MED-V 工作區。** 在將 MED-V 工作區設定為可供共用電腦上的所有使用者存取時，請注意，系統會將來賓虛擬機器（VHD）放在一個位置，以提供對該系統上所有使用者的讀取和寫入存取權。

**針對加入網域的伺服器設定 proxy 帳戶。** 當您設定將虛擬機器加入網域的 proxy 帳戶時，您必須知道最終使用者可以取得 proxy 帳號憑證。 因此，必須採取必要的預防措施（例如限制帳戶的使用者權利），避免使用者使用認證來造成損害。

**Sysprep 設定。** 雖然 Sysprep .inf 檔案預設是經過加密，但其內容可以由任何已確定的最終使用者解密並讀取，任何人都可以成功登入虛擬機器。 這會引發安全性問題，因為除了 Windows 產品金鑰之外，Sysprep.inf 檔案也可以包含認證。

您可以設定一個受限制的帳戶來將虛擬電腦加入網域，並在設定 Sysprep 時指定該帳戶的認證，以減輕此風險。 或者，您也可以設定 Sysprep 和第一次設定在**有人參與**模式下執行，並要求使用者提供其認證，才能將虛擬機器加入到網域。

MED-V 最佳做法是將 FtsCompletion.exe 指定為在可讓使用者透過遠端桌面連線（RDC）用戶端連線至來賓的帳戶下執行。

**最終使用者驗證。** 啟用終端使用者認證的快取可為 MED-V 提供最佳的使用者體驗，但卻帶來了某人可以取得使用者認證存取權的可能性。 減少此風險的唯一方式，就是在**Med-v 工作區包裝**程式上指定不會儲存終端使用者認證。 如需使用者驗證的詳細資訊，請參閱[Med-v 端使用者驗證](authentication-of-med-v-end-users.md)。

## 相關主題


[作業疑難排解](operations-troubleshooting-medv2.md)

[Microsoft 企業版桌面虛擬化2。0](index.md)

 

 





