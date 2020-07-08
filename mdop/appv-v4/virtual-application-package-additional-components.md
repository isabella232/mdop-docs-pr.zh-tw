---
title: 虛擬應用程式封裝其他元件
description: 虛擬應用程式封裝其他元件
author: dansimp
ms.assetid: 476b0f40-ebd6-4296-92fa-61fa9495c03c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d30c2c6561b0d2c08fd75e0c977bf4590d7e6688
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800747"
---
# 虛擬應用程式封裝其他元件


App-v 排序器檢測到一個目錄，其中包含64位和32位的可執行檔，以及/或動態連結程式庫（.dll）檔案，而這些檔案是由同一個並行元件所組成。 通常，Sequencer 會針對封裝所使用的所有公用元件建立私有並行元件;不過，無法在同一個目錄中建立32位與64位版本的私人程式集。

如果 Sequencer 檢測到單一衝突，則會執行下列動作：

-   移除整個套件中所有現有的64位私用程式集（無論該目錄是否有衝突）。

-   只建立32位的私人並行元件版本。

您應該在執行排序器的電腦和所有 App-v 用戶端電腦上，本機安裝所有必要64位元件的公開版本。

若要找出所需的現有公用元件，請開啟套件的儲存目錄，並在**VFS**資料夾中尋找。 例如，如果套件根目錄是**Q:\\MyApp**，當您將應用程式排序時，請參閱**Q:\\MyApp\\VFS\\CSIDL\ _Windows \\winsxs\\manifests** ，並找出所有現有的公用元件。 這些檔案的64位版本永遠會以下列文字從資訊清單名稱開頭開始： **amd64 ...** 您可以在相關聯的資訊清單檔案中找到該元件的確切名稱和版本。

使用下列任何一個連結，下載並安裝正確的必要必備元件版本：

-   [Microsoft Visual c + + 2005 可再發行套件（x64）](https://go.microsoft.com/fwlink/?LinkId=152697)

-   [Microsoft Visual c + + 2005 SP1 可再發行套件（x64）](https://go.microsoft.com/fwlink/?LinkId=152698)

-   [Microsoft Visual c + + 2008 可再發行套件（x64）](https://go.microsoft.com/fwlink/?LinkId=152699)

-   [Microsoft Visual c + + 2008 SP1 可再發行套件（x64）](https://go.microsoft.com/fwlink/?LinkId=152700)

 

 





