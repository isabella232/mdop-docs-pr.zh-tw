---
title: 部署 MBAM 2.5 群組原則物件
description: 部署 MBAM 2.5 群組原則物件
author: dansimp
ms.assetid: 4b835054-6846-463d-af58-8ac4639a1188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9624b94e9d4808a35e1199290f4cd90a8122f767
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810526"
---
# 部署 MBAM 2.5 群組原則物件


若要部署 MBAM，您必須設定定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的 [組原則] 設定。 若要完成這項工作，您必須將 MBAM 群組原則範本複製到能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的伺服器或工作站，然後編輯設定。

**重要** 請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定，否則 MBAM 將無法正常運作。 當您在**MDOP MBAM （BitLocker 管理）** 節點中設定群組原則設定時，MBAM 會自動為您設定**BitLocker 磁片磁碟機加密**設定。

 

## 複製 MBAM 2.5 群組原則範本


在您安裝 MBAM 用戶端之前，您必須將 MBAM 專用的群組原則物件（Gpo）複製到管理工作站。 這些 Gpo 定義 BitLocker 磁片磁碟機加密的 MBAM 實現設定。 您可以將群組原則範本複製到任何支援 Windows server 或用戶端電腦的伺服器或工作站，且能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）。

[複製 MBAM 2.5 群組原則範本](copying-the-mbam-25-group-policy-templates.md)

## 編輯 MBAM 2.0 GPO 設定


在您建立必要的 Gpo 之後，您必須將 MBAM 群組原則設定部署到貴組織的用戶端電腦。 若要查看和建立 Gpo，您必須已安裝群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）。

[編輯 MBAM 2.5 群組原則設定](editing-the-mbam-25-group-policy-settings.md)

## 顯示或隱藏 Windows [控制台] 中的 [MBAM] 控制台


因為 MBAM 提供自訂的 MBAM 控制台，可以取代預設的 Windows BitLocker [控制台]，您也可以選擇使用 [群組原則] 設定來顯示或隱藏最終使用者的預設 BitLocker 控制台。

[隱藏控制台中預設的 BitLocker 磁碟機加密項目](hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md)

## 部署 MBAM 2.0 群組原則物件的其他資源


[部署 MBAM 2.5](deploying-mbam-25.md)

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。

 

 





