---
title: 如何手動安裝 MED-V 主機代理程式
description: 如何手動安裝 MED-V 主機代理程式
author: dansimp
ms.assetid: 4becc90b-6481-4e1f-a4d3-aec74c8821ec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a7fb44b23a390cf394af2331152955afc2d8eba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800208"
---
# 如何手動安裝 MED-V 主機代理程式


Microsoft 企業版桌面虛擬化（MED-V）2.0 解決方案有兩個不同但相關的元件： MED-V 主機代理程式和來賓代理程式。 主機代理程式位於主機電腦（執行 Windows 7 的使用者電腦）上，並提供通道來與 MED-V 來賓（在主機電腦中執行的 MED-V 虛擬機器）進行通訊。 它也會提供某些與 MED-V 相關的功能，例如應用程式發佈。

通常，您可以使用公司的喜好預配軟體方法來部署並安裝 MED-V 主機代理程式。 不過，在整個企業中部署 MED-V 之前，您可能比較想要在本機安裝主機代理程式來進行測試。 本節提供手動安裝 MED-V 主機代理程式的逐步指示。

**記事** MED-V 來賓代理程式會在第一次設定期間自動安裝。

 

**重要** 在安裝 MED-V 主機代理程式前關閉 Internet Explorer，否則可能會在 URL 重新導向之後發生衝突。 您也可以在發佈期間指定電腦重新開機來執行此動作。

 

**安裝 MED-V 主機代理程式**

1.  找出您在軟體下載中收到的 MED-V 安裝檔案。

2.  按兩下 MED-V \ _HostAgent \ _Setup 安裝檔。

    [ **Microsoft 企業桌面虛擬化（med-v）主機代理程式設定**] 嚮導隨即開啟。 按 \[**下一步**\] 繼續。

3.  接受 Microsoft 軟體授權條款，然後按一下 **[下一步]**。

4.  選取要安裝 MED-V 主機代理程式的目的地資料夾。 按 **\[下一步\]**。

5.  若要開始安裝主機代理程式，請按一下 [**安裝**]。

6.  成功完成安裝後，請按一下 **[完成**] 以關閉嚮導。

    若要確認主機代理程式已成功安裝，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 企業版桌面虛擬化**]，然後按一下 [ **med-v 主機代理程式**]。

**記事** 除非已安裝 MED-V 工作區，否則 MED-V 主機代理程式可以啟動並執行，但不提供任何功能。

 

## 相關主題


[如何透過電子軟體發佈系統來部署 MED-V 元件](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md)

[如何安裝 MED-V 工作區封裝工具](how-to-install-the-med-v-workspace-packager.md)

[如何解除安裝 MED-V 元件](how-to-uninstall-the-med-v-components.md)

 

 





