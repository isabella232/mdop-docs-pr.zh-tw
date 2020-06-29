---
title: 如何編輯 MBAM 1.0 GPO 設定
description: 如何編輯 MBAM 1.0 GPO 設定
author: dansimp
ms.assetid: 03d12fbc-4302-43fc-9b38-440607d778a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 824fbc2fe0d8f2b00c32de177733e4e327cf4d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810461"
---
# 如何編輯 MBAM 1.0 GPO 設定


若要成功部署 Microsoft BitLocker 管理和監控（MBAM），您必須先決定您要在實施 Microsoft BitLocker 管理和監控時使用的群組原則。 如需各種可用原則的詳細資訊，請參閱[規劃 MBAM 1.0 群組原則需求](planning-for-mbam-10-group-policy-requirements.md)。 在您決定要使用的原則之後，您必須修改包含 MBAM 原則設定的一個或多個群組原則物件（GPO）。

下列步驟說明如何設定基本的建議群組原則物件（GPO）設定，以讓 MBAM 管理貴組織用戶端電腦的 BitLocker 加密。

**編輯 MBAM 用戶端 GPO 設定**

1.  在已安裝 MBAM 群組原則範本的電腦上，請確定已啟用 MBAM 服務。

2.  使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM） MDOP 產品進行下列動作：選取 [電腦設定]，選擇 [**原則**]，按一下 [**系統****管理範本**]，選取 [ **Windows 元件**]，然後按一下 **[MDOP MBAM （BitLocker Management）**]。

3.  編輯在用戶端電腦上啟用 MBAM 用戶端服務所需的群組原則物件設定。 針對後面的資料表中的每個原則，選取 [**原則群組**]，按一下**原則**，然後設定**設定**。

    原則群組

    原則

    設定

    用戶端管理

    設定 MBAM 服務

    啟用。 設定**MBAM 復原與硬體服務端點**，然後**選取要儲存的 BitLocker 復原資訊**。

    設定**MBAM 合規性服務端點**，並**在（分鐘）中輸入狀態報表頻率**。

    允許硬體相容性檢查

    已停用。 預設會啟用此原則，但基本 MBAM 實現不需要此原則。

    作業系統磁片磁碟機

    作業系統磁片磁碟機加密設定

    啟用。 **針對作業系統磁片磁碟機設定 [選取保護**器]。 若要將作業系統磁片磁碟機資料儲存至 MBAM 金鑰復原伺服器，必須這麼做。

    抽取式磁碟磁碟機

    在抽取式磁碟磁碟機上控制 BitLocker 的使用

    啟用。 如果 MBAM 會將抽取式磁碟磁碟機資料儲存到 MBAM 金鑰復原伺服器，就是必要的。

    固定磁片磁碟機

    在固定磁片磁碟機上控制 BitLocker 的使用

    啟用。 如果 MBAM 會將固定磁片磁碟機資料儲存至 MBAM 金鑰復原伺服器，則需要這麼做。

    您**可以選擇如何復原受 BitLocker 保護的磁碟機**，以及**允許資料修復代理程式**。



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## 相關主題


[部署 MBAM 1.0 群組原則物件](deploying-mbam-10-group-policy-objects.md)









