---
title: 如何使用命令列安裝用戶端
description: 如何使用命令列安裝用戶端
author: dansimp
ms.assetid: ed372403-64ff-48ff-a3cd-a46cad04a4d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca594e1399b4ca4f680f68efffcd011fdc5f042
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801370"
---
# 如何使用命令列安裝用戶端


本節中的主題包含使用 setup.exe 或 setup.msi，將應用程式虛擬化（app-v）桌面用戶端或 App-v 用戶端安裝至遠端桌面服務（舊稱終端服務）的程式。 必須具備系統管理許可權，才能執行其中一個安裝程式。

您可以在安裝期間，使用選用的命令列參數，將特定的設定設定套用到 App-v 用戶端。 如需使用參數的詳細資訊，請參閱[應用程式虛擬化用戶端安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)。 如果您在部署用戶端之前已將登錄設定套用至電腦（例如使用群組原則），這些設定就會保留，並會套用任何其他的命令列參數。 命令列參數值將會取代任何現有的相同設定值。

**記事** 當您安裝 App-V 用戶端以搭配唯讀快取（例如使用 VDI 伺服器實現）時，您必須將*AUTOLOADTARGET*參數設定為 NONE，以免用戶端在快取為唯讀時嘗試更新應用程式。

 

如需在安裝後設定這些參數值的詳細資訊，請參閱[如何使用命令列](https://go.microsoft.com/fwlink/?LinkId=169355)（ https://go.microsoft.com/fwlink/?LinkId=169355) 在應用程式虛擬化（App-v）操作指南中）來設定 app-v 用戶端的註冊表設定。

**記事** 如果使用者電腦上的設定是由用戶端安裝路徑所決定，請注意應用程式虛擬化（App-v）4.5 用戶端會將安裝檔案複製到與先前版本不同的資料夾。 根據預設，App-V 4.5 用戶端的新安裝會將其安裝檔案複製到 \\Program Files\\Microsoft 應用程式虛擬化用戶端資料夾。 如果已安裝較舊版本的用戶端，執行 App-v 4.5 用戶端安裝程式將會使用現有的安裝資料夾來升級現有的用戶端。

 

\ [範本標記值 \]

**記事** 針對 App-v 及更新版本，安裝 app-v 用戶端時，SFTLDR.DLL 會複製到 Windows\\system32 目錄。 如果 App-v 用戶端安裝在64位系統上，SFTLDR\_WOW64.DLL 會複製到 Windows\\SysWOW64 目錄。

 

\ [範本標記值 \]

## 本節內容


下列主題說明如何使用 setup.exe 或 setup.msi 來安裝應用程式虛擬化（app-v）桌面用戶端或 App-V 用戶端（以前稱為 [終端服務]）。

<a href="" id="how-to-install-the-app-v-client-by-using-setup-exe"></a>[如何使用 Setup.exe 安裝 App-V Client](how-to-install-the-app-v-client-by-using-setupexe-new.md)  
提供使用 setup.exe 程式來安裝 App-v 用戶端的逐步程式。

<a href="" id="how-to-install-the-app-v-client-by-using-setup-msi"></a>[如何使用 Setup.msi 安裝 App-V Client](how-to-install-the-app-v-client-by-using-setupmsi-new.md)  
提供使用 setup.msi 程式來安裝任何必備軟體和 App-v 用戶端的逐步程式。

## 相關主題


[Application Virtualization Client 安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)

[如何手動安裝 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)

[如何在用戶端上發佈虛擬應用程式](how-to-publish-a-virtual-application-on-the-client.md)

[如何解除安裝 App-V Client](how-to-uninstall-the-app-v-client.md)

 

 





