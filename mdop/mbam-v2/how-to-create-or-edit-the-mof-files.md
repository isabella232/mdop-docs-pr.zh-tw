---
title: 如何建立或編輯 mof 檔案
description: 如何建立或編輯 mof 檔案
author: dansimp
ms.assetid: 4d19d707-b90f-4057-a6e9-e4221a607190
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5f59e9133dd25ecf45d16a5cb704d6ea00923d9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811085"
---
# 如何建立或編輯 mof 檔案


在使用 Configuration Manager 安裝 Microsoft BitLocker 管理及監視（MBAM）之前，您必須先編輯 Configuration mof 檔案。 您也需要編輯或建立 Sms \ _def 的 mof 檔案，視您所使用的 Configuration Manager 版本而定。

## 編輯 Configuration.mof 檔案


若要讓用戶端電腦透過 MBAM Configuration Manager 報告來報告 BitLocker 合規性詳細資料，您必須編輯 Microsoft System Center Configuration Manager 2007 和 SystemCenter2012 ConfigurationManager 的 mof 檔案。

[編輯 Configuration.mof 檔案](edit-the-configurationmof-file.md)

## <a href="" id="create-or-edit-the-sms-def-mof-file"></a>建立或編輯 Sms \ _def 的 mof 檔案


若要讓用戶端電腦在 MBAM Configuration Manager 報告中報告 BitLocker 相容性詳細資料，您必須建立或編輯 Sms \ _def. mof 檔案。 在 Configuration Manager 2007 中，檔案已經存在，因此您必須編輯現有的檔案，但不需要覆寫該檔案。 如果您使用的是 SystemCenter2012 ConfigurationManager，則必須建立檔案。

[建立或編輯 Sms \ _def 的 mof 檔案](create-or-edit-the-sms-defmof-file.md)

## 相關主題


[使用設定管理員來部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





