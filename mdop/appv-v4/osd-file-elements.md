---
title: OSD 檔案元素
description: OSD 檔案元素
author: dansimp
ms.assetid: 8211b562-7549-4331-8321-144f52574e99
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a8e3ebcf53ff39ecd2ef7ad0feec0bbbcae199db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800953"
---
# OSD 檔案元素


Sequencer 安裝目錄包含 XML 架構檔案**Softricity （xsd**），該檔案定義開放式軟體描述項（OSD）檔案的有效結構。 以下是一些較頻繁使用的 OSD 元素。

<a href="" id="softpkg"></a>SOFTPKG  
OSD 檔案的根項目，內含定義軟體套件的所有元素。

<a href="" id="codebase"></a>基  
此套件的 sft 檔案相關資訊，包括 HREF、FILENAME 及 GUID 屬性。 如果您變更這個特定套件的發佈點，就可以編輯 HREF 屬性。

<a href="" id="os"></a>作業系統  
根據最初在順序嚮導中設定的值，定義此應用程式可以執行的作業系統。 這個值只能包含**Softricity**中定義的值。

<a href="" id="local-interaction-allowed"></a>本機 \ _INTERACTION \ _ALLOWED  
如果設定為 TRUE，則可在全域命名空間中建立命名物件（事件、mutex、信號燈、檔案對應及 mailslots）和 COM 物件，而不是隔離在特定的虛擬環境中，這可讓虛擬應用程式與主機作業系統的應用程式互動。

範例： &lt; SOFTPKG &gt; &lt; 實現&gt;

&lt;VIRTUALENV &gt; &lt; 原則&gt;

&lt;本機 \ _INTERACTION \ _ALLOWED &gt; TRUE

&lt;/LOCAL\ _INTERACTION \ _ALLOWED&gt;

&lt;/POLICIES &gt; &lt; /VIRTUALENV&gt;

&lt;/IMPLEMENTATION &gt; &lt; /SOFTPKG&gt;

<a href="" id="dependencies"></a>因素  
使用來自另一個套件的 CODEBASE 標記，定義動態套件組合（其他套件的相依性）。

範例：相依性 &lt; &gt; &lt; CODEBASE] HREF = "rtsps：//server/package.sft" GUID = "7579F4DF-2461-4219-BD43-494E1FDC69E3" SYSGUARDFILE = "installer.pkg. 1 \\ osguard. cp" SIZE = "6572748" 強制性 = "FALSE"/ &gt; &lt; /DEPENDENCIES&gt;

<a href="" id="package-name"></a>套件名稱  
在 [排序] 嚮導的 [**資訊**] 頁面中輸入之套件的通用名稱，可讓您指定單一名稱，以用於包含多個應用程式的順序化應用程式。

<a href="" id="title"></a>職稱  
您正在排序之應用程式的選用描述名稱。

<a href="" id="abstract"></a>概要  
在排序嚮導**封裝資訊**頁面的 [**批註**] 欄位中輸入之軟體套件的簡短描述。 最佳做法是指定諸如作業系統與服務套件層級、Sequencer 版本及排序工程工程名稱等資訊。

<a href="" id="script"></a>腳本  
定義啟動、關閉或資料流程期間發生的特定腳本事件。

<a href="" id="mgmt-shortcutlist"></a>管理 \ _SHORTCUTLIST  
在嚮導中定義的所有快速鍵清單。

<a href="" id="mgmt-fileassociations"></a>管理 \ _FILEASSOCIATIONS  
在嚮導中指定的檔案類型清單。

## 相關主題


[關於 OSD 索引標籤](about-the-osd-tab.md)

 

 





