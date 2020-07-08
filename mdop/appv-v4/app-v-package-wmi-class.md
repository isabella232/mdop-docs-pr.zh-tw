---
title: App-V 封裝 WMI 類別
description: App-V 封裝 WMI 類別
author: dansimp
ms.assetid: 0fc26c3b-9706-4804-be2d-645771dc33ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa452afaaeb2f490c179a928b24de47207d6dc63
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802361"
---
# App-V 封裝 WMI 類別


在應用程式虛擬化（App-v）用戶端中， **Package**類別是代表用戶端上所有虛擬套件的 Windows 管理規範（WMI）類別。 虛擬套件可以包含許多虛擬應用程式。

## 語法


``` syntax
class Package
{
      string Name;
      string Version;
      string PackageGUID;
      string SftPath;
      uint64 TotalSize;
      uint64 CachedSize;
      uint64 LaunchSize;
      uint64 CachedLaunchSize;
      boolean InUse;
      boolean Locked;
      uint16 CachedPercentage;
      string VersionGUID;
 };
```

## 屬性


<a href="" id="name"></a>**名稱**  
資料類型：**字串**

Access 類型：唯讀

限定詞：無

虛擬套件的方便使用名稱。

<a href="" id="version"></a>**版本**  
資料類型：**字串**

Access 類型：唯讀

限定詞：無

虛擬套件的版本。

<a href="" id="packageguid"></a>**PackageGUID**  
資料類型：**字串**

Access 類型：唯讀

限定詞：金鑰

套件配置和來源檔案的 GUID 識別碼。

<a href="" id="sftpath"></a>**SftPath**  
資料類型：**字串**

Access 類型：唯讀

限定詞：無

SFT 檔案的檔案路徑。

<a href="" id="totalsize"></a>**TotalSize**  
資料類型： **UInt64**

Access 類型：唯讀

限定詞：無

虛擬套件的總大小（以 kb 為單位）。

<a href="" id="cachedsize"></a>**CachedSize**  
資料類型： **UInt64**

Access 類型：唯讀

限定詞：無

虛擬套件的快取總大小（以 kb 為單位）。

<a href="" id="launchsize"></a>**LaunchSize**  
資料類型： **UInt64**

Access 類型：唯讀

限定詞：無

虛擬套件主要功能區塊的總大小（以 kb 為單位）。

<a href="" id="cachedlaunchsize"></a>**CachedLaunchSize**  
資料類型： **UInt64**

Access 類型：唯讀

限定詞：無

已快取的虛擬套件主要功能區塊總大小（以 kb 為單位）。

<a href="" id="inuse"></a>**InUse**  
資料類型：**布林值**

Access 類型：唯讀

限定詞：無

如果虛擬套件中的任何虛擬應用程式正在執行，**則為 true** ;否則**為 false**。

<a href="" id="locked"></a>**已鎖定**  
資料類型：**布林值**

Access 類型：唯讀

限定詞：無

如果虛擬套件已鎖定，**則為 true** ;否則**為 false**。

<a href="" id="cachedpercentage"></a>**CachedPercentage**  
資料類型： **UInt16**

Access 類型：唯讀

限定詞：無

快取檔案的百分比。 根據下列公式： CachedSize/TotalSize ×100。

<a href="" id="versionguid"></a>**VersionGUID**  
資料類型：**字串**

Access 類型：唯讀

限定詞：無

套件版本的 GUID 識別碼。

 

 





