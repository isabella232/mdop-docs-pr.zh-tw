---
title: 如何為 App-V 設定 Windows Server 2008 防火牆
description: 如何為 App-V 設定 Windows Server 2008 防火牆
author: dansimp
ms.assetid: 57f4ed17-0651-4a3c-be1e-29d9520c6aeb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 19e4cda9ac3b908f68e4f69b9663033d8a21ae41
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801529"
---
# 如何為 App-V 設定 Windows Server 2008 防火牆


隨著 Windows Server2008 的推出，防火牆和 IPsec 元件會合並成一個服務，而這項服務的功能也得到加強。 新的防火牆服務支援傳入及傳出狀態檢查。 此外，您也可以透過 [群組原則] 設定特定的防火牆規則及 IPsec 原則。 如需 Windows Server2008 中 Windows 防火牆的其他相關資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=151980> 。

下列程式不包含透過 SMB 或 HTTP/HTTPS 新增 .ICO 和 OSD 發佈例外狀況。 這些例外狀況會根據安裝在 Windows Server 2008 防火牆的網路設定檔和角色來自動新增。

**記事** 如果管理伺服器已設定為使用 RTSP，請重複此程式以新增 `sghwsvr.exe` 程式作為例外狀況。

App-v 流式處理伺服器需要程式例外狀況 `sglwdsptr.exe` 才能進行 RTSPS 通信。 使用 RTSP 通訊的 App-v 流式處理伺服器也需要程式例外狀況 `sglwsvr.exe` 。

 

**若要設定 App-V 的 Windows Server2008 防火牆**

1.  透過 [控制台] 或在 [執行] 行上輸入 **，以開啟 [高級安全**管理] 主控台的 Windows 防火牆 `wf.msc` 。

2.  建立新的入站規則，然後選取 [**程式**]。

3.  選取程式路徑，然後流覽至 `sghwdsptr.exe` ，其預設位於中 `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` 。

4.  按 **\[下一步\]**。

5.  在 [**動作**] 頁面上，選取 [**允許**連線]，然後按一下 **[下一步]**。

6.  選取要套用至入站規則的適當**設定檔**。

7.  提供規則的名稱和描述，然後按一下 **[完成]**。

## 相關主題


[如何為 App-V 設定 Windows Server 2003 防火牆](how-to-configure-windows-server-2003-firewall-for-app-v.md)

 

 





