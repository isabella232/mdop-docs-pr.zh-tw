---
title: 設定 App-V 伺服器所需的防火牆
description: 設定 App-V 伺服器所需的防火牆
author: dansimp
ms.assetid: f779c450-6c6f-46a8-ac66-5e82e0689d55
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92db727eb060546ab71f2c647f2d89b662be5c64
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808984"
---
# 設定 App-V 伺服器所需的防火牆


安裝 Microsoft Application Virtualization （App-v）管理伺服器或流式處理伺服器並將其設定為使用 RTSP 或 RTSPS 通訊協定後，您必須建立 App-v 程式的防火牆例外狀況。

## 設定應用程式虛擬化管理伺服器的防火牆例外狀況


針對**sghwdsptr.exe**和**sghwsvr.exe**建立防火牆例外狀況。 這些程式可在32位作業系統上的 [C:\\program files Files\\Microsoft System Center App Virt 管理 Server\\App Virt Management Server\\bin] 中找到。 如果您使用的是64位作業系統版本，則資料夾位於 [C:\\program files Files （x86）] \\Microsoft System Center App Virt 管理 Server\\App Virt Management Server\\bin。

## 設定應用程式虛擬化流程伺服器的防火牆例外狀況


針對**sglwdsptr.exe**和**sglwsvr.exe**建立防火牆例外狀況。 這些程式位於32位作業系統上的 [C:\\program files Files\\Microsoft System Center] App Virt 資料流程 Server\\App Virt 資料流程 Server\\bin。 如果您使用的是64位作業系統版本，則資料夾位於 [C:\\program files Files （x86）] \\Microsoft System Center App Virt 串流 Server\\App Virt 串流 Server\\bin。

## 相關主題


[如何針對以伺服器為基礎的部署設定伺服器](how-to-configure-servers-for-server-based-deployment.md)

[如何安裝和設定 Default Application](how-to-install-and-configure-the-default-application.md)

 

 





