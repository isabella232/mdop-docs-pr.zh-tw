---
title: 如何手動部署 MED-V 工作區
description: 如何手動部署 MED-V 工作區
author: dansimp
ms.assetid: 94bfb209-2230-49b6-bb40-9c6ab088dbf4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f13d06e2232681f87df7a71b9a3ef3269b4f9ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812260"
---
# 如何手動部署 MED-V 工作區


在某些情況下，您可能會想手動部署 MED-V 工作區，例如，如果您的公司不使用電子軟體發佈系統來部署應用程式。

本節說明如何手動部署 MED-V 工作區。

**若要手動部署 MED-V 工作區**

1.  將所有必備應用程式和 MED-V 工作區套件檔案複製到共用的磁片磁碟機或 DVD 中。 下列是所需的應用程式和檔案清單。

    -   **Windows 虛擬電腦**。 如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。

    -   **Windows 虛擬電腦新增和更新**。 如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。

    -   **Med-v 主機代理安裝**檔案–安裝主機代理程式（med-v \ _HostAgent \ _Setup 安裝檔案）。

        **警告**  
        在安裝 MED-V 主機代理程式前關閉 Internet Explorer，否則可能會在 URL 重新導向之後發生衝突。 您也可以在發佈期間指定電腦重新開機來執行此動作。



~~~
-   **MED-V Workspace Installer, VHD, and Setup Executable** – created with the **MED-V Workspace Packager**. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).

    **Important**  
    The compressed VHD file (.medv) and the Setup executable program (setup.exe) must be in the same folder as the MED-V workspace installer.
~~~



2. 依所列順序安裝下列。 最終使用者可以手動執行此工作，也可以建立腳本來安裝下列專案：

   -   Windows 虛擬電腦和 Windows 虛擬電腦的新增和更新。 需要重新開機電腦。

   -   MED-V 主機代理程式。

       **注意**  
       如果它正在執行，則必須重新開機 Internet Explorer，才能安裝 MED-V 主機代理程式。



~~~
-   The MED-V workspace package.

    Install the MED-V workspace by running the setup.exe program that is included in the MED-V workspace package files.
~~~

3. 第一次完成設定。

   安裝 MED-V 工作區之後，您可以選擇啟動 MED-V。 這會啟動 MED-V 主機代理程式。 您可以在該時間啟動 MED-V，或稍後啟動 MED-V 主機代理程式，以完成第一次設定。

   若要啟動 MED-V 主機代理程式，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 企業版桌面虛擬化**]，然後按一下 [ **med-v 主機代理程式**]。

## 相關主題


[如何透過電子軟體發佈系統來部署 MED-V 工作區](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

[如何在 Windows 7 映像中部署 MED-V 工作區](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)

[部署 MED-V 工作區套件](deploying-the-med-v-workspace-package.md)









