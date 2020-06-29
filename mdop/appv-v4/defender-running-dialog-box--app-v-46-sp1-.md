---
title: Defender 正在執行對話方塊 (App-V 4.6 SP1)
description: Defender 正在執行對話方塊 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 716ec7f9-ddad-45dd-a3c7-4a9d81cfcfd0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e33d48c089d7bf903c65da804e6cf5aa1bd2065
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808955"
---
# Defender 正在執行對話方塊 (App-V 4.6 SP1)


Microsoft Windows Defender 正在執行。 您應該先停止 Windows Defender，然後再繼續安裝。 Windows Defender 會存取必須新增至虛擬應用程式套件的檔案，或是在虛擬應用程式套件中新增無關資料，來干擾建立套件。

使用下列程式來避免 Microsoft Windows Defender 在排序期間執行。

1.  在執行 App-v 排序器的電腦上，按一下 [**開始**]，以滑鼠右鍵按一下 [**電腦**]，然後按一下 [**管理**]。

2.  在 [**電腦管理**] 主控台中，按兩下 [**服務與應用程式**]，然後按兩下 [**服務**] 以展開 [**服務**]。

3.  在清單中找到該檔案。 以滑鼠右鍵按一下 [Windows Defender]，按一下 [**停止**] 停止 Microsoft Windows defender，然後按一下 **[確定]**。

## 相關主題


[對話方塊 (AppV 4.6 SP1)](dialog-boxes--appv-46-sp1-.md)

 

 





