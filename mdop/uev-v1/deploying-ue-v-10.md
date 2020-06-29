---
title: 部署 UE-V 1.0
description: 部署 UE-V 1.0
author: dansimp
ms.assetid: 519598bb-8c81-4af7-bee7-357696bff880
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a1c515f9be950d8ca7b0a199344d34f7852073d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812182"
---
# 部署 UE-V 1.0


Microsoft 使用者體驗虛擬化（UE-V）支援多種不同的部署設定。 本節包含一般資訊和逐步程式，可協助您成功執行必須在部署的不同階段完成的工作。

## UE-V 的部署資訊


UE-V 部署需要網路共用上的設定儲存位置，以及在同步處理設定的每台電腦上安裝 UE-V agent。 UE-V 群組原則範本可用於管理 UE-V 設定。 下列主題說明如何部署這些功能。

[部署適用於 UE-V 1.0 的設定儲存位置](deploying-the-settings-storage-location-for-ue-v-10.md)

所有 UE-V 部署都需要設定儲存位置，其中包含同步處理設定值的設定套件位於其中。

[部署 UE-V 代理程式](deploying-the-ue-v-agent.md)

若要使用 UE-V 同步處理設定，電腦必須已安裝並執行 UE-V Agent。

[安裝 UE-V 群組原則 ADMX 範本](installing-the-ue-v-group-policy-admx-templates.md)

在部署 UE-V Agent 及標準 UE-V 設定之前，您可以使用群組原則來預先配置 UE-V 設定。

## 自訂範本部署的部署資訊


如果您打算針對包含在 UE-V 中的 Microsoft 應用程式以外的應用程式建立自訂設定位置範本（例如商務線應用程式），您可以部署設定範本目錄，而且您必須安裝 UE-V 發生器來建立這些範本。 如需詳細資訊，請參閱[規劃 ue-v 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)。

[安裝 UE-V 產生器](installing-the-ue-v-generator.md)

使用 UE-V 發生器來建立、編輯及驗證自訂設定位置範本，協助同步處理應用程式（而非預設應用程式）的設定。

[部署適用於 UE-V 1.0 的設定範本類別目錄](deploying-the-settings-template-catalog-for-ue-v-10.md)

如果您需要將自訂設定位置範本部署成支援 UE-V Agent 中預設應用程式以外的應用程式，您必須設定設定範本目錄來儲存。

[部署適用於 UE-V 1.0 的 UE-V 設定位置範本](deploying-ue-v-settings-location-templates-for-ue-v-10.md)

如果您需要同步處理 UE-V Agent 中的預設應用程式以外的應用程式，則可將使用 UE-V 發生器建立的自訂設定位置範本發佈到 UE-V 設定範本目錄。

**記事** 部署自訂範本需要設定範本目錄。 預設的 Microsoft 應用程式範本是與 UE-V Agent 一起部署。

 

## 此產品的主題


[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[開始使用 User Experience Virtualization 1.0](getting-started-with-user-experience-virtualization-10.md)

[為 UE-V 1.0 進行規劃](planning-for-ue-v-10.md)

[UE-V 1.0 作業](operations-for-ue-v-10.md)

[疑難排解 UE-V 1.0](troubleshooting-ue-v-10.md)

 

 





