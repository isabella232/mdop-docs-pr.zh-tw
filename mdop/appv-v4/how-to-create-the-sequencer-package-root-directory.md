---
title: 如何建立排序器封裝根目錄
description: 如何建立排序器封裝根目錄
author: dansimp
ms.assetid: 23fe28f1-c284-43ee-b8b7-1dfbed94eea5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5150e87915202794624b6c51510e56454d2c7d36
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801489"
---
# 如何建立排序器封裝根目錄


[套件根目錄] 是電腦上執行 App-v 排序器之檔案的目錄，其中安裝已排序之應用程式的檔案。 這個目錄也會在您的電腦上以資料流程的方式存在。 您應該先建立套件根目錄，然後再監視安裝新的應用程式。

建立套件根目錄之後，您就可以開始順序應用程式。 如需針對新的應用程式排序的詳細資訊，請參閱[如何為應用程式](how-to-sequence-an-application.md)排序。

**建立套件根目錄**

1.  若要在執行 App-v 排序器的電腦上建立套件根目錄，請將 Q:\\ 磁片磁碟機對應至指定的網路位置。 您指定的位置應該有足夠的空間來儲存您正在排序的應用程式。

2.  若要建立可用於新虛擬應用程式的目錄，請在 Q:\\ 磁片磁碟機上建立一個資料夾，並為它指派名稱。

    **重要** 您指派給將儲存在套件根目錄中之虛擬應用程式檔案的名稱，應該使用8.3 命名格式。 檔案名不應長於8個字元，且具有三個字元的副檔名。

     

## 相關主題


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

[如何修改記錄檔目錄位置](how-to-modify-the-log-directory-location.md)

[如何修改臨時目錄位置](how-to-modify-the-scratch-directory-location.md)

 

 





