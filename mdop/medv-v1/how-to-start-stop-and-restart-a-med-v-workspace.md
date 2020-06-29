---
title: 如何開始、停止及重新啟動 MED-V 工作區
description: 如何開始、停止及重新啟動 MED-V 工作區
author: dansimp
ms.assetid: 54ce139c-8f32-499e-944b-72f123ebfd2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2739ace085a4d57d333daf7872e01a7712a7fbd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811325"
---
# 如何開始、停止及重新啟動 MED-V 工作區


**啟動 MED-V 工作區**

1.  在通知區域中，以滑鼠右鍵按一下 MED-V 圖示。

2.  在子功能表上，按一下 [**啟動工作區**]。

    -   如果在電腦上執行多個 MED-V 工作區，則會出現 [**工作區選取範圍**] 視窗。

        1.  選取 MED-V 工作區。

        2.  選取 [**啟動選取的工作區但不要求我**] 核取方塊，以在下次啟動用戶端時跳過此視窗，並自動開啟選取的 med-v 工作區。

        3.  按一下 \[確定\] ****。

    隨即會出現 [**啟動工作區驗證**] 視窗。

    -   如果電腦上有數個 MED-V 工作區，而且您選擇要使用指定的 MED-V 工作區，則會出現如下圖所示的視窗。

        ![](images/medv-logon.gif)

    -   如果電腦上只有一個 MED-V 工作區，則 [啟動上次使用的工作區] 選項無法使用。

3.  輸入您的網域使用者認證。

    **記事** 第一次啟動 med-v 工作區時，使用者名稱應該是下列格式： &lt; 功能變數名稱 &gt; \\ &lt; 使用者名稱 &gt; 。

     

4.  選取 [**儲存我的密碼**]，在會話之間儲存密碼。

    **記事** 若要啟用 [儲存密碼] 功能，在 ClientSettings.xml 檔案中必須將 EnableSavePassword 屬性設為 True。 檔案可以在 [ *Servers\\Configuration Server\\* ] 資料夾中找到。

     

5.  清除 [**啟動上次使用的工作區**] 核取方塊，選擇不同的 med-v 工作區。

6.  按一下 \[確定\] ****。

    視 MED-V 工作區設定而定，會出現幾個狀態畫面。

    [**啟動工作區**] 畫面隨即出現。

**重新開機 MED-V 工作區**

1.  當用戶端正在執行時，請在通知區域中，以滑鼠右鍵按一下 MED-V 圖示。

2.  在子功能表上，按一下 [**重新開機工作區**]。

    隨後便會重新開機 MED-V 工作區。

    -   在持久的 MED-V 工作區中，虛擬機器會關閉並重新啟動。

    -   在 revertible MED-V 工作區中，虛擬機器實際上不會關閉;相反地，它會回到原始狀態。

**停止 MED-V 工作區**

1.  在通知區域中，以滑鼠右鍵按一下 MED-V 圖示。

2.  在子功能表上，按一下 [**停止工作區**]。

    MED-V 工作區已停止。

## 相關主題


[如何開始和結束 MED-V 用戶端](how-to-start-and-exit-the-med-v-client.md)

 

 





