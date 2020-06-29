---
title: 關於內容索引標籤
description: 關於內容索引標籤
author: dansimp
ms.assetid: a6cf6f51-3778-4c8d-9632-3af4005775d2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4b2d6c3e01dde48fdd6701984f66610ea0333b74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802410"
---
# 關於內容索引標籤


使用 [**屬性**] 索引標籤來查看已排序之應用程式套件的基本統計資訊。 除非另有說明，否則系統會自動產生資訊。 此索引標籤包含下列元素。

## 封裝資訊


<a href="" id="package-name"></a>**套件名稱**  
可能包含一或多個應用程式之已排序之應用程式套件的單一名稱（例如，Microsoft Office 可以用來標示已排序的應用程式套件），其中包含在相同虛擬環境中執行的 Microsoft Word 和 Microsoft Excel 應用程式。

<a href="" id="comments"></a>**註解**  
顯示將出現在開放式軟體描述項（OSD）檔摘要元素中的軟體套件簡短描述。 這個專案是選擇性的。

<a href="" id="package-version"></a>**套件版本**  
已排序的應用程式套件版本。

<a href="" id="package-guid"></a>**封裝 GUID**  
系統會自動將全域唯一識別碼（GUID）指派給排序的應用程式套件，以將它與可能在已排序之應用程式套件流入的電腦上執行的其他順序式應用程式套件區分開來。

<a href="" id="package-version-guid"></a>**套件版本 GUID**  
已排序的應用程式套件版本 GUID。

<a href="" id="root-directory"></a>**根目錄**  
順序電腦上安裝排序後應用程式套件之檔案的目錄。 此目錄也會在已排序的應用程式套件將流入的電腦上建立。 建議向後相容性為 Q 磁碟機根目錄的8.3 格式目錄名稱，例如 Q:\\MyApp.1\\。

<a href="" id="created"></a>**新建**  
已排序之應用程式套件的建立日期和時間。

<a href="" id="modified"></a>**修改日期**  
上次修改排序之應用程式套件的日期和時間。

<a href="" id="package-size"></a>**套件大小**  
套件的大小（以 mb 為單位）。

<a href="" id="launch-size"></a>**啟動大小**  
啟動應用程式所需的 SFT 檔案部分大小（以 mb 為單位）。

## 先後順序參數


<a href="" id="block-size"></a>**區塊大小**  
指定主要和次要功能區塊的大小，以便將 SFT 檔案分割成多個網路上的資料流程。 所有區塊都等於指定大小;不過，最後一個區塊可能小於指定的大小。 您會看到下列其中一個值：

-   4 KB

-   16 KB

-   32 KB

-   64 KB

**記事** 建立初始套件之後，組塊大小值就不會改變。

 

## 相關主題


[如何變更封裝內容](how-to-change-package-properties.md)

[排序器主控台](sequencer-console.md)

 

 





