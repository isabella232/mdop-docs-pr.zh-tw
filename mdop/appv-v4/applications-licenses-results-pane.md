---
title: 應用程式授權結果窗格
description: 應用程式授權結果窗格
author: dansimp
ms.assetid: 8b519715-b2fe-451e-ad9b-e9b73f454961
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e5a86c22e67e061ec873317c455958536fae75b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802245"
---
# 應用程式授權結果窗格


應用程式虛擬化伺服器管理主控台中的 [**應用程式授權結果**] 窗格會顯示可用的應用程式授權群組和應用程式授權清單。

以滑鼠右鍵按一下任何應用程式授權群組，以顯示包含下列元素的快顯功能表。

<a href="" id="new-unlimited-license"></a>**新的無限制授權**  
顯示 [新增無限制授權] 嚮導。 只有在授權群組沒有授權時，才能使用此選項。 此嚮導包含三個頁面：

1.  在 [**應用程式授權] 群組**的 [名稱] 欄位中輸入群組名稱，在 [**授權到期警告**] 欄位中輸入一個值（以分鐘為單位）。 （您可以輸入從0到100的任何值）。您也可以使用向上鍵和向下鍵來選取分鐘數。

2.  在 [**授權描述**] 欄位中輸入簡短的描述文字，然後選取 [**啟用**] 核取方塊。 您也可以使用 [**到期日**] 欄位來指定授權的到期日。 您可以選取 [預設值] 核取方塊，或使用 [行事曆] 實用程式流覽至想要的到期日。

3.  按一下 **[完成]** 以新增新的授權。

<a href="" id="new-concurrent-license"></a>**新的並行授權**  
顯示 [新增併發授權] 嚮導。 只有在授權群組沒有無限制的授權時，才能使用此選項。 此嚮導包含下列頁面，與新的 [無限制授權] 嚮導幾乎完全相同：

1.  在 [**應用程式授權] 群組**的 [名稱] 欄位中輸入群組名稱，在 [**授權到期警告**] 欄位中輸入一個值（以分鐘為單位）。 （您可以輸入從0到100的任何值）。您也可以使用向上鍵和向下鍵來選取分鐘數。

2.  在 [**授權描述**] 欄位中輸入簡短的描述文字，然後在 [**併發授權數量**] 欄位中輸入值。 您也可以使用向上鍵和向下鍵來指定併發授權的數量。 選取 [**已啟用**] 核取方塊以啟用授權。 您也可以使用 [**到期日**] 欄位來選取授權的到期日。 您可以選取核取方塊以使用顯示的到期日，或者您可以使用 [行事曆] 實用程式流覽至想要的到期日。

3.  按一下 **[完成]** 以新增新的授權。

<a href="" id="new-named-license"></a>**新的命名授權**  
顯示新的 [命名授權] 嚮導。 只有在授權群組沒有無限制的授權時，才能使用此選項。 此嚮導包含下列頁面：

1.  在 [**應用程式授權] 群組**的 [名稱] 欄位中輸入群組名稱，在 [**授權到期警告**] 欄位中輸入一個值（以分鐘為單位）。 （您可以輸入從0到100的任何值）。您也可以使用向上鍵和向下鍵來選取分鐘數。

2.  在**授權描述**中輸入簡短的描述文字，然後選取 [**啟用**] 核取方塊。 您也可以使用 [**到期日**] 欄位來指定授權的到期日。 您可以選取核取方塊以使用顯示的到期日，或使用行事曆實用程式流覽至想要的到期日。

3.  按一下 [**新增**]、[**編輯**] 或 [**移除**已命名的使用者]。

4.  按一下 **[完成]** 以新增新的授權。

<a href="" id="new-window-from-here"></a>**從這裡新增視窗**  
開啟新的管理主控台，並將選取的節點做為根節點。

<a href="" id="delete"></a>**刪除**  
從清單中刪除 [授權] 群組。

<a href="" id="rename"></a>**重新命名**  
變更應用程式授權群組的名稱。

<a href="" id="properties"></a>**屬性**  
顯示所選應用程式授權群組的 [**屬性**] 對話方塊。 此對話方塊具有下列索引標籤：

-   **[一般**] 索引標籤-顯示授權群組的一般資訊。 在此索引標籤上，您可以變更 [**授權到期警告**] 欄位中的時間值（以分鐘為單位）。 您可以輸入0到100之間的任何值。

-   [**應用程式**] 索引標籤-顯示與授權群組相關聯的應用程式清單。

<a href="" id="help"></a>**說明**  
顯示應用程式虛擬化伺服器管理主控台說明系統。

當 [**結果**] 窗格顯示應用程式授權群組時，請以滑鼠右鍵按一下 [**結果**] 窗格中的任何位置（除了授權群組之外），以顯示包含下列元素的快顯功能表。

<a href="" id="refresh"></a>**重新整理**  
刷新伺服器的視圖。

<a href="" id="export-list"></a>**匯出清單**  
建立包含 [**結果**] 窗格內容的定位字元分隔文字檔。 此專案會顯示 [標準檔案**儲存**] 對話方塊，您可以在此指定您要建立之文字檔的位置。

<a href="" id="view"></a>**View**  
變更 [**結果**] 窗格的外觀和內容。

<a href="" id="arrange-line-up-icons"></a>**[排布]/[對齊] 圖示**  
變更 [**結果**] 窗格中圖示的顯示方式。

<a href="" id="help"></a>**說明**  
顯示應用程式虛擬化伺服器管理主控台的說明系統。

當 [**結果**] 窗格顯示授權時，以滑鼠右鍵按一下任何應用程式授權，即可顯示包含下列元素的快顯功能表。

<a href="" id="delete"></a>**刪除**  
從清單中刪除授權。

<a href="" id="rename"></a>**重新命名**  
變更授權的名稱。

<a href="" id="properties"></a>**屬性**  
顯示所選應用程式授權的 [**屬性**] 對話方塊。

[**屬性**] 對話方塊的 [**一般**] 索引標籤會顯示授權的相關資訊，並可讓您變更啟用狀態、授權到期日及授權金鑰資訊。

<a href="" id="help"></a>**說明**  
顯示伺服器管理主控台說明系統。

當 [**結果**] 窗格顯示授權時，請以滑鼠右鍵按一下 [**結果**] 窗格中的任何位置（除了授權之外），以顯示包含下列元素的快顯功能表。

<a href="" id="export-list"></a>**匯出清單**  
建立包含 [**結果**] 窗格內容的定位字元分隔文字檔。 此專案會顯示 [標準檔案**儲存**] 對話方塊，您可以在此指定您要建立之文字檔的位置。

<a href="" id="view"></a>**View**  
變更 [**結果**] 窗格的外觀和內容。

<a href="" id="arrange-line-up-icons"></a>**[排布]/[對齊] 圖示**  
變更 [**結果**] 窗格中圖示的顯示方式。

<a href="" id="properties"></a>**屬性**  
顯示所選授權的 [**屬性**] 對話方塊。

[**屬性**] 對話方塊的 [**一般**] 索引標籤會顯示授權的相關資訊，並可讓您變更啟用狀態、授權到期日及授權金鑰資訊。

<a href="" id="help"></a>**說明**  
顯示應用程式虛擬化伺服器管理主控台的說明系統。

## 相關主題


[關於應用程式授權](about-application-licensing.md)

[如何在伺服器管理主控台中管理應用程式授權](how-to-manage-application-licenses-in-the-server-management-console.md)

[伺服器管理主控台：應用程式授權節點](server-management-console-application-licenses-node.md)

 

 




