---
title: 如何安裝 MBAM 1.0 群組原則範本
description: 如何安裝 MBAM 1.0 群組原則範本
author: dansimp
ms.assetid: 451a50b0-939c-47ad-9248-a138deade550
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a055c84fb6b1645592b53d957daf157a6055880
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811096"
---
# 如何安裝 MBAM 1.0 群組原則範本


除了 Microsoft BitLocker 管理和監控（MBAM）的伺服器相關功能之外，伺服器安裝應用程式還包含 MBAM 群組原則範本。 您可以在任何能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上安裝此範本。

下列步驟說明如何安裝 MBAM 群組原則範本。

**記事** 請務必在32位伺服器上使用32位設定，以及在64位伺服器上進行64位設定。

 

**若要安裝 MBAM 群組原則範本**

1.  啟動 MBAM 安裝精靈;然後，按一下 [歡迎] 頁面上的 [**安裝**]。

2.  閱讀並接受 Microsoft 軟體授權條款，然後按一下 **[下一步]** 繼續安裝。

3.  根據預設，所有的 MBAM 功能都已選取 [安裝]。 清除 [**原則範本**] 以外的所有功能選項，然後按 **[下一步]** 繼續安裝。

    **記事** 安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。 如果符合所有先決條件，安裝會繼續進行。 如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後**再次按一下 [檢查先決條件**]。 一旦符合所有先決條件，就會繼續安裝。

     

4.  在 MBAM 安裝精靈顯示所選功能的安裝頁面之後，按一下 **[完成]** 以關閉 MBAM 設定。

## 相關主題


[部署 MBAM 1.0 群組原則物件](deploying-mbam-10-group-policy-objects.md)

 

 





