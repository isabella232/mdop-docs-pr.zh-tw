---
title: 在 Windows 虛擬電腦映像上安裝應用程式
description: 在 Windows 虛擬電腦映像上安裝應用程式
author: dansimp
ms.assetid: 32651eff-e3c6-4ef4-947d-2beddc695eac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9bf73fec0b33b37c2553dfe6f923917aa926b8e8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811991"
---
# 在 Windows 虛擬電腦映像上安裝應用程式


在您建立 Windows 虛擬電腦映射以搭配 Microsoft 企業桌面虛擬化（MED-V）2.0 之後，您可以在執行 MED-V （例如電子軟體發佈（ESD）系統和防毒軟體）時，安裝其他有用的元件。

下列各節提供的資訊可協助您在 MED-V 影像上安裝軟體。

**小心** 若要在部署之後輕鬆使用 MED-V 工作區管理，我們建議您將在 MED-V 影像上安裝的元件數量限制為所需的元件，或使用 MED-V 的實用程式。 例如，雖然不需要執行 MED-V，但您可以安裝 ESD 系統來供日後安裝應用程式到 MED-V 工作區，以及在影像上進行安全性的防毒軟體。

 

**在 MED-V 影像上安裝軟體**

1.  如果目前沒有執行，請開啟您的 MED-V 虛擬機器。

    1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，然後按一下 [ **windows 虛擬電腦**]。

    2.  按兩下您的 MED-V 虛擬機器。

2.  從虛擬機器作業系統內，找出您要安裝之軟體的安裝檔案。

3.  依照軟體廠商提供的安裝指示進行。

    **記事** 安裝完成後，您可能必須關閉虛擬機器，然後再重新開機。

     

針對您想要在 MED-V 影像上安裝的任何軟體或應用程式，重複這些步驟。 我們建議您限制您在影像上預先安裝的應用程式數量。 在影像上安裝應用程式和其他軟體的建議程式是立即預先安裝 ESD 系統，稍後再使用它來將軟體部署至影像。 或者，您也可以使用群組原則或 App-v 在 MED-V 工作區上新增或移除應用程式。 如需詳細資訊，請參閱[管理部署至 Med-v 工作區的應用程式](managing-applications-deployed-to-med-v-workspaces.md)。

如需如何在虛擬影像上安裝軟體的詳細資訊，請參閱下列文章：

-   [發佈並使用虛擬應用程式](https://go.microsoft.com/fwlink/?LinkId=195926)（ https://go.microsoft.com/fwlink/?LinkId=195926) 。

-   [Windows 虛擬電腦](https://go.microsoft.com/fwlink/?LinkId=182378)說明（ https://go.microsoft.com/fwlink/?LinkId=182378) 。

在 MED-V 影像上安裝完所有您想要的軟體之後，您的影像就可以打包了。

## 相關主題


[設定 MED-V 的 Windows 虛擬電腦映像](configuring-a-windows-virtual-pc-image-for-med-v.md)

[準備 MED-V 映像](prepare-a-med-v-image.md)

 

 





