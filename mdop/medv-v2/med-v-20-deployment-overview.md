---
title: MED-V 2.0 部署概觀
description: MED-V 2.0 部署概觀
author: dansimp
ms.assetid: 0b8998ea-c46f-4c81-a304-f380b2ed7cf8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ec2a5f86ac7d63295bd7c550bcb0a90004987e42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811558"
---
# MED-V 2.0 部署概觀


本節提供有關如何安裝及部署 Microsoft Enterprise 桌面虛擬化（MED-V）2.0 的一般資訊與指示。

## 概觀


MED-V 2.0 是以應用程式模型為基礎，您用來部署應用程式的方法可以用來部署和管理 MED-V。 已部署的 MED-V 解決方案包含兩個元件： MED-V 主機代理程式和來賓代理程式。 MED-V 主機代理程式已安裝在 Windows 7 電腦版，而 MED-V 來賓代理程式則安裝在 MED-V 工作區內的 Windows XP 中。 MED-V 也包含 MED-V 工作區包裝程式，可提供建立及設定 MED-V 工作區所需的資訊和工具。

**重要**  
MED-V 只支援安裝 MED-V 工作區包裝程式、MED-V 主機代理程式，以及所有使用者的 MED-V 工作區。 只有選取**ALLUSERS = ""** ，才能為目前的使用者安裝 med-v，導致安裝元件與安裝 med-v 工作區時失敗。



### MED-V 安裝檔案

MED-V 包含執行 MED-V 所需的下列安裝檔：

**MED-V 主機代理程式安裝檔**

主機代理程式安裝檔案命名為 [MED-V\_HostAgent\_Setup.exe]。 此檔案是在與企業範圍內的 MED-V 部署中，在每個相關的最終使用者電腦上發佈並安裝。

**MED-V 工作區包裝程式安裝檔**

MED-V 工作區包裝程式安裝檔命名為 MED-V\_WorkspacePackager\_Setup.exe。 使用此檔案在您擁有管理員許可權和許可權的電腦上安裝 MED-V 工作區包裝程式。 桌面系統管理員使用 MED-V 工作區包裝程式來建立及管理 MED-V 工作區。

**注意**  
MED-V 來賓代理程式會在第一次設定期間自動安裝。



### MED-V 部署程式

以下是 MED-V 安裝與部署程式的高層概覽：

1.  在您擁有管理認證且將用來建立 MED-V 工作區套件的電腦上安裝 MED-V 工作區包裝程式。 如需詳細資訊，請參閱[如何安裝 Med-v 工作區包裝程式](how-to-install-the-med-v-workspace-packager.md)。

2.  使用 MED-V 工作區包裝程式來準備 MED-V 影像，並建立 MED-V 工作區套件。 如需詳細資訊，請參閱[med-v 的操作](operations-for-med-v.md)。

3.  在整個企業中部署所需的 MED-V 元件。 MED-V 的必要元件是 Windows Virtual PC、MED-V 主機代理程式，以及 MED-V 工作區。

**重要**  
安裝 MED-V 元件需要管理認證。 如果使用者正在安裝 MED-V，系統會提示他們輸入管理認證。 或者，如果您是使用電子軟體發佈（ESD）系統進行安裝，就可以在內容中提供管理認證。



### MED-V 元件

您在整個企業部署的 MED-V 元件包含下列各項：

**Windows 虛擬電腦**

Windows 虛擬電腦影像內的 MED-V 函數用於相容性方案。 Windows 虛擬電腦和 Windows 7 的更新（KB977206）是必要的。 如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。

**MED-V 主機代理程式安裝檔**

MED-V\_HostAgent\_Setup.exe]。

**MED-V 工作區安裝檔案**

當您建立由下列專案組成的 MED-V 工作區套件時，就會建立 MED-V 工作區安裝檔案：

執行 MED-V 工作區安裝的 setup.exe 可執行程式

&lt;Med-v \ _workspace \ _name &gt; .msi 安裝程式

&lt;VHD \ _filename &gt; medv 檔案，該檔案是壓縮的虛擬硬碟

[配置設定] 的檔案（ &lt; 工作區 \ _name &gt; .reg 和 &lt; 工作區 \ _name &gt; ps1）

若要部署 MED-V，請將所有所需的安裝檔案複製到主機電腦或主機電腦可存取的共用位置。 針對 Windows Virtual PC、MED-V 主機代理程式和 MED-V 工作區執行元件安裝檔案。 然後啟動 MED-V 主機代理程式，以在第一次安裝 MED-V 時完成。

您可以手動執行安裝。 不過，我們建議您使用電子軟體發佈方法來自動部署元件。 如需詳細資訊，請參閱[如何透過電子軟體發佈系統部署 Med-v 工作區](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)。

**注意**  
如需控制安裝選項之可用命令列引數的相關資訊，請參閱[Med-v 安裝檔的命令列選項](command-line-options-for-med-v-installation-files.md)。



## 部署步驟


當您在整個企業中部署 MED-V 時，主要需要考慮的事項：安裝與第一次設定。

### 安裝

1.  **Windows 虛擬電腦**-在安裝期間，Med-v 檢查 WINDOWS 虛擬電腦及其必要的 windows 7 更新（KB977206）。 如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。

    在安裝 MED-V 之前，您可以將它們安裝為 Windows 7 安裝的一部分，或者您可以將它們安裝為 MED-V 發佈的一部分。 不過，MED-V 不包含適用于其部署的機制;必須使用電子軟體發佈（ESD）系統或 Windows 7 影像的一部分來部署它們。

    **重要**  
    當您使用批次檔案安裝 MED-V 元件時，最佳做法是在 MED-V 主機代理和 MED-V 工作區套件檔案之後，指定 Windows 虛擬電腦和 Windows 虛擬電腦熱修復程式已安裝。 這表示 Windows 更新不會對安裝程式造成任何干擾，只要需要重新開機即可。



~~~
**Note**  
After you install Windows Virtual PC, the computer must be restarted.
~~~



2. **Med-v 主機代理程式**-在將執行 Med-v 的 Windows 7 電腦上安裝 Med-v 主機代理程式。 在安裝 MED-V 工作區之前，必須先安裝此功能，然後檢查以確認已安裝 Windows 虛擬電腦。

3. **Med-v 工作區**-您可以使用 Med-v 工作區包裝程式來建立此安裝所需的檔案： setup.exe、medv 和 .msi 檔案。 若要安裝 MED-V 工作區，請執行 setup.exe;這會根據需要觸發其他檔案。 安裝會將登錄中的專案放在本機電腦執行機碼底下，以啟動 MED-V 主機代理程式（在 Windows 啟動時，這會一直執行 MED-V）。

   **重要**  
   MED-V 工作區的安裝可由最終使用者以互動方式執行，或透過電子軟體發佈系統以無提示的方式執行。 安裝 MED-V 工作區需要管理認證，因此使用者必須是其電腦的系統管理員，才能安裝 MED-V 工作區。 或者，電子軟體發佈系統通常會在系統內容中執行，且具有足夠的許可權。



~~~
**Tip**  
Because of problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.
~~~



### 第一次設定

安裝 MED-V 並安裝其必備元件之後，就必須對 MED-V 進行設定。 MED-V 的配置稱為第一次設定。 透過使用**Med-v 工作區包裝**程式，您可以將第一次設定設定為以安靜或互動方式執行。 第一次安裝 MED-V 需要使用者輸入其密碼才能向 MED-V 工作區驗證，但對使用者幾乎看不到。 通知會顯示在通知區域中，例如當您第一次設定完成且應用程式準備就緒時。 下列是第一次設定 MED-V 時所發生的動作：

1.  必須設定虛擬硬碟。 [最小化安裝] 會執行，並展開 Windows XP 影像。 這個問題通常會發生在隱藏視窗中，但 MED-V 可以設定為在此設定期間顯示。

2.  [最小化安裝] 完成後，您可以執行其他設定所需的命令，例如安裝 ESD 軟體或其他應用程式，或配置影像。 這些可以在 Sysprep.inf 檔案中呼叫，但在此不是必要的。 如需詳細資訊，請參閱設定[med-v 的 Windows 虛擬電腦影像](configuring-a-windows-virtual-pc-image-for-med-v.md)。

3.  Ftscompletion.exe 是作為 [設定] 中的最後一個步驟執行。 這個程式會完成 MED-V 設定，將使用者新增至 RDP 群組，讓其存取 MED-V 工作區、複製記錄、通知 MED-V-v 工作區已就緒，然後重新開機 MED-V 工作區。 此程式也可以將使用者新增為 MED-V 工作區的管理員（如果這是在建立 MED-V 工作區時設定的）。 Ftscompletion.exe 通常是透過 Sysprep、inf 檔案呼叫，但是也可以透過另一個方法（例如腳本）執行。 不過，Ftscompletion.exe 必須是設定工作站時所執行的最後一個動作。 如需詳細資訊，請參閱設定[med-v 的 Windows 虛擬電腦影像](configuring-a-windows-virtual-pc-image-for-med-v.md)。

4.  Ftscompletion.exe 將 MED-V 工作區重新開機之後，使用者就會登入。 如果他們在第一次設定期間未儲存其密碼，系統會再次提示他們。 接著啟動並設定使用者的 MED-V 工作區。 配置包括套用群組原則。

    我們建議您只在適用于 Windows XP 的應用程式相容性環境中，套用那些對您有意義的原則。 例如，桌面個人化原則通常不需要套用，而且應該停用。 如需如何只允許使用本機設定檔的詳細資訊，請參閱[漫遊使用者設定檔的群組原則設定](https://go.microsoft.com/fwlink/?LinkId=205072)（ https://go.microsoft.com/fwlink/?LinkId=205072) 。

第一次設定完成後，系統會通知使用者已發佈的應用程式已就緒。 接著他們就能從其 [**開始**] 功能表存取在 med-v 工作區所安裝的應用程式。

## 相關主題


[準備 MED-V 的部署環境](prepare-the-deployment-environment-for-med-v.md)

[MED-V 部署](deployment-of-med-v.md)









