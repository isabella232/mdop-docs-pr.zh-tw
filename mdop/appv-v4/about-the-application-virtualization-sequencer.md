---
title: 關於 Application Virtualization Sequencer
description: 關於 Application Virtualization Sequencer
author: dansimp
ms.assetid: bee193ca-58bd-40c9-b41a-310435633895
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 83709bcceabe3312fba34512b47d28a24b4dc52c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802441"
---
# 關於 Application Virtualization Sequencer


Microsoft Application Virtualization （App-v） Sequencer 會監視及記錄應用程式的所有安裝與設定處理常式，並建立下列檔案： **.ico**、 **OSD**、 **SFT**及**SPRJ**。 這些檔案包含有關應用程式的所有必要資訊，讓應用程式可以在目的電腦上的虛擬環境中執行。 您可以使用 Microsoft Application Virtualization （App-v） Sequencer 來建立虛擬應用程式。 當您將應用程式排序之後，就可以將它流式處理至目的電腦，或讓目的電腦下載虛擬應用程式套件的內容，並在本機執行應用程式，以執行虛擬應用程式。

**重要** 若要執行虛擬應用程式套件，目的電腦必須執行適當版本的 App-V 用戶端。

 

虛擬應用程式套件是在目的電腦上執行，而不與目的電腦上的基礎作業系統互動，因為每個應用程式都是在虛擬環境中執行，且獨立于在目的電腦上安裝或執行的其他應用程式。 這個隔離可以減少應用程式衝突，並有助於減少所需的應用程式預先部署測試數量。

## 排序器術語


<a href="" id="application-virtualization-drive"></a>Application Virtualization 磁片磁碟機  
應用程式虛擬化磁片磁碟機是執行順序應用程式的目的電腦上的預設磁片磁碟機（Q:\）。

<a href="" id="ico-file"></a>.ICO 檔案  
用戶端桌面上的圖示檔案，用來啟動已排序的應用程式。

<a href="" id="installation-directory"></a>安裝目錄  
排序器在安裝期間用來放置安裝盤案的目錄。

<a href="" id="open-software-descriptor--osd--file"></a>開啟軟體描述項（OSD）檔案  
程式化的 XML 檔案，會指示 App-v 用戶端如何從 App-v 流式處理伺服器中檢索已排序的應用程式，以及如何在虛擬環境中執行已排序的應用程式。

<a href="" id="package-root-directory"></a>套件根目錄  
排序電腦上已安裝排序後之應用程式套件之檔案的目錄。 這個目錄也會在您的電腦上以資料流程的方式存在。

<a href="" id="sequenced-application"></a>順序應用程式  
由 sequencer 監視的應用程式，分解成主要和次要功能區塊，資料流程傳送到執行 App-v 用戶端 t 的目的電腦，並執行虛擬環境。

<a href="" id="sequenced-application-package"></a>已排序的應用程式套件  
組成虛擬應用程式的檔案，並允許虛擬應用程式執行。 這些檔案是在進行排序之後建立，特別包含 **.osd**、 **sft**、 **sprj**及 **.ico**檔案。

<a href="" id="sequencing"></a>序列  
使用 App-v 排序器建立應用程式套件的程式。 在這個程式中，系統會監視應用程式、設定其快速鍵，並建立順序化的應用程式套件。

<a href="" id="sequencing-computer"></a>順序電腦  
用來對應用程式進行排序的電腦。

<a href="" id="virtual-application"></a>虛擬應用程式  
由排序器封裝的應用程式，以在自包含的虛擬環境中執行。 虛擬環境包含在用戶端上執行應用程式所需的資訊，而不需要在本機安裝應用程式。

<a href="" id="primary-feature-block"></a>主要功能區塊  
應用程式在目的電腦上執行時所需的虛擬應用程式套件中的最小內容。 主要功能區塊中的內容是在排序的應用程式階段中識別，通常是由最常用的應用程式功能的內容所組成。

## <a href="" id="sequencing-applications-"></a>排序應用程式


有兩種方法可以在您的環境中建立及修改虛擬應用程式套件。 第一種方法是使用 [**順序**] 嚮導。 [**順序**] 嚮導可讓您建立新的虛擬應用程式套件或修改現有的虛擬應用程式套件。 如需使用 [**排序**嚮導] 的詳細資訊，請參閱[如何為新的應用程式排序](how-to-sequence-a-new-application.md)。 第二種方法是使用命令列。 命令列可讓您使用命令提示字元建立新的或修改現有的虛擬應用程式套件。 如需有關使用命令列的詳細資訊，請參閱[如何使用命令列管理虛擬應用程式](how-to-manage-virtual-applications-using-the-command-line.md)。

[**順序**] 嚮導會提供下列函數來建立虛擬應用程式套件：

1.  **套件**設定： [**順序**] 嚮導會提示完成開啟軟體描述項（OSD）檔案所需的封裝設定資訊，這是啟動順序應用程式套件所需的檔案。

2.  **應用程式安裝**： [**順序**] 嚮導會收集應用程式安裝與啟動設定的相關資訊。 它會監視及記錄與應用程式相關聯的安裝與啟動資訊，以建立虛擬應用程式套件所需的檔案。

3.  **應用程式啟動**： [**排序**] 嚮導會收集編譯及排序所需程式碼區塊的資訊，以便在目的電腦上執行已排序之應用程式套件的初始啟動。 程式碼區塊的編譯稱為主要功能區塊。

## 應用程式虛擬化 Sequencer 的安全性考慮


App-v 排序器會執行使用本機系統帳戶在先後順序時間檢測到的所有服務，但不會在服務控制要求上強制執行安全性描述項。 如果服務是使用不同的使用者帳戶安裝，或者如果安全描述項是要授與使用者群組特定的服務許可權，請仔細考慮是否應該將服務虛擬化。 在某些情況下，您應該在本機安裝該服務，以確保所需的服務安全性得以保留。

**重要** 您應該總是將虛擬應用程式套件儲存在安全的位置。

 

## 相關主題


[Application Virtualization Sequencer 概觀](application-virtualization-sequencer-overview.md)

 

 





