---
title: 如何在 Windows 7 映像中部署 MED-V 工作區
description: 如何在 Windows 7 映像中部署 MED-V 工作區
author: dansimp
ms.assetid: a83aba4e-8681-4906-9872-f431c0bb15f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 49dd796d6f6af425b9000b595a0d828c3cb0035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812261"
---
# 如何在 Windows 7 映像中部署 MED-V 工作區


您可以將所有的 MED-V 元件，安裝在您整個企業中發佈的 Windows 7 映射，就像您在安裝任何新的 Windows 7 中一樣。 然後，使用者按一下您設定以啟動 MED-V-V 的 [**開始**] 功能表快捷方式，即可完成 med-v 工作區的安裝。 第一次設定開始，而最終使用者遵循指示完成設定。

下列章節提供資訊與指示，協助您使用 Windows 7 影像在整個企業中部署 MED-V 工作區。

**在 Windows 7 影像中部署 MED-V 工作區**

1.  建立 Windows 7 的標準影像。 如需詳細資訊，請參閱[建立 Windows 7 的標準影像：逐步指南](https://go.microsoft.com/fwlink/?LinkId=204843)（ https://go.microsoft.com/fwlink/?LinkId=204843) 。

2.  在 Windows 7 映射中，安裝 Windows 虛擬電腦和 Windows 虛擬電腦更新。 如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。

3.  使用 MED-V \ _HostAgent \ _Setup 安裝檔來安裝 MED-V 主機代理程式。 如需詳細資訊，請參閱[如何手動安裝 Med-v 主機代理程式](how-to-manually-install-the-med-v-host-agent.md)。

    **警告** 您必須先關閉 Internet Explorer，才能安裝 MED-V 主機代理程式，否則可能會在 URL 重新導向後發生衝突。 您也可以在發佈期間指定電腦重新開機來執行此動作。

     

4.  將 MED-V 工作區套件檔案複製到 Windows 7 影像。 MED-V 工作區套件檔案是 MED-V 的工作區安裝程式、medv 檔案，以及您使用**Med-v 工作區包裝**程式建立的 setup.exe 檔案。

    **重要** Medv 和 setup.exe 檔案必須與 MED-V 工作區安裝程式位於相同的資料夾中。 然後，透過執行 setup.exe 來安裝 MED-V 工作區。

     

5.  在 [**開始**] 功能表上設定快速鍵，以開啟 med-v 工作區套件安裝。

    建立 [**開始**] 功能表的快捷方式至 setup.exe 檔案，讓最終使用者根據需要啟動 med-v 安裝。

6.  使用貴公司的標準影像部署程式，將 Windows 7 影像發佈到企業中需要 MED-V 的電腦。

當使用者必須存取在 MED-V 工作區中發佈的應用程式時，他們可以按一下 [**開始**] 功能表的快捷方式來安裝 med-v 工作區。 這會在第一次設定開始時自動啟動，並完成 MED-V 的配置。 第一次完成設定之後，使用者就可以在 [**開始**] 功能表上存取 med-v 應用程式。

## 相關主題


[MED-V 2.0 部署概觀](med-v-20-deployment-overview.md)

[如何透過電子軟體發佈系統來部署 MED-V 工作區](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

 

 





