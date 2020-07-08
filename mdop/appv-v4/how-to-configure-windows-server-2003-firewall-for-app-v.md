---
title: 如何為 App-V 設定 Windows Server 2003 防火牆
description: 如何為 App-V 設定 Windows Server 2003 防火牆
author: dansimp
ms.assetid: 2c0e80f8-41e9-4164-ac83-b23b132b489a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af75479504b454851ee2efc7ca2638d2daf45053
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801533"
---
# 如何為 App-V 設定 Windows Server 2003 防火牆


使用下列程式來設定 App-v 的 WindowsServer 2003 防火牆。

**若要設定 WindowsServer 2003 的 App-V 防火牆**

1.  在 [**控制台**] 中，開啟 [ **Windows 防火牆**]。

    **記事** 如果伺服器尚未設定為在執行此步驟之前執行防火牆服務，系統會提示您啟動防火牆服務。

     

2.  如果 .ICO 和 OSD 檔案是透過 SMB 發佈，請確定 [**例外**] 索引標籤上的 [檔案**及印表機共用**] 已啟用。

    **記事** 如果 .ICO 和 OSD 檔案是透過管理伺服器上的 HTTP/HTTPS 發佈，您可能需要新增 HTTP 或 HTTPS 例外狀況。 如果裝載 .ICO 和 OSD 檔案的 IIS 伺服器裝載在與管理伺服器不同的電腦上，您需要將例外狀況新增到該電腦。 若要最大化效能，建議您將 .ICO 和 OSD 檔案託管在與管理伺服器不同的伺服器上。

     

3.  新增的程式例外狀況 `sghwdsptr.exe` ，也就是管理伺服器服務的可執行檔。 此可執行檔的預設路徑是 `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` 。

    **記事** 如果管理伺服器使用 RTSP 進行通訊，您也必須新增程式例外狀況 `sghwsvr.exe` 。

    App-v 流式處理伺服器需要程式例外狀況 `sglwdsptr.exe` 才能進行 RTSPS 通信。 使用 RTSP 通訊的 App-v 流式處理伺服器也需要程式例外狀況 `sglwsvr.exe` 。

     

4.  確保針對每個例外設定適當的範圍。 若要降低風險，請移除任何電腦，並嚴格限制伺服器將回應的 IP 位址。

## 相關主題


[如何為 App-V 設定 Windows Server 2008 防火牆](how-to-configure-windows-server-2008-firewall-for-app-v.md)

 

 





