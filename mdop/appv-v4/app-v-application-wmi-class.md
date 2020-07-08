---
title: App-V 應用程式 WMI 類別
description: App-V 應用程式 WMI 類別
author: dansimp
ms.assetid: b79b0d5a-ba57-442f-8bb4-d7154fc056f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a4e1e49e35b231ddb2a480a06c46e364121ac2d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809285"
---
# App-V 應用程式 WMI 類別


在應用程式虛擬化（App-v）用戶端中，**應用程式**類別是代表用戶端上所有虛擬應用程式的 Windows 管理工具（WMI）類別。

您可從 Managed 物件格式（MOF）程式碼簡化下列語法。 程式碼包含所有繼承的屬性。

## 語法


``` syntax
class Application
{
      string Name;
      string Version;
      string PackageGUID;
      datetime LastLaunchOnSystem;
      uint32 GlobalRunningCount;
      boolean Loading;
      string OriginalOsdPath;
      string CachedOsdPath;
};
```

## 需求


## 屬性


<a href="" id="name"></a>**名稱**  
資料類型：**字串**

Access 類型：唯讀

限定詞：金鑰

虛擬應用程式的顯示名稱。

<a href="" id="version"></a>**版本**  
資料類型：**字串**

Access 類型：唯讀

限定詞：金鑰

虛擬應用程式的版本。

<a href="" id="packageguid"></a>**PackageGUID**  
資料類型：**字串**

Access 類型：唯讀

限定詞：無

與虛擬應用程式相關聯之套件的 GUID。

<a href="" id="lastlaunchonsystem"></a>**LastLaunchOnSystem**  
資料類型： **DateTime**

Access 類型：唯讀

限定詞：無

啟動虛擬應用程式的最後日期和時間。

<a href="" id="globalrunningcount"></a>**GlobalRunningCount**  
資料類型： **UInt32**

Access 類型：唯讀

限定詞：無

直接啟動之虛擬應用程式的執行實例數。

<a href="" id="loading"></a>**正在載入**  
資料類型：**布林值**

Access 類型：唯讀

限定詞：無

如果正在啟動虛擬應用程式，**則為 true** ;否則**為 false**。

<a href="" id="originalosdpath"></a>**OriginalOsdPath**  
資料類型：**字串**

Access 類型：唯讀

限定詞：無

在 App-V 用戶端註冊之 OSD 檔案的原始檔案路徑。

<a href="" id="cachedosdpath"></a>**CachedOsdPath**  
資料類型：**字串**

Access 類型：唯讀

限定詞：無

如果 App-v 檔案已在本機緩存 OSD 檔案，則為 OSD 檔案的檔案路徑。

 

 





