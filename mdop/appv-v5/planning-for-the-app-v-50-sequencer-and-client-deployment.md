---
title: 為 App-V 5.0 Sequencer 與 Client 部署進行規劃
description: 為 App-V 5.0 Sequencer 與 Client 部署進行規劃
author: dansimp
ms.assetid: 57a604ad-90e1-4d32-86bb-eafff59aa43a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 8c6f7c4d717acad014f079e51a7013a57766d9ca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800350"
---
# 為 App-V 5.0 Sequencer 與 Client 部署進行規劃


在您開始使用 Microsoft Application Virtualization （App-v）5.0 之前，您必須安裝 App-v 5.0 排序器、App-v 5.0 用戶端，以及（選擇性） app-v 5.0 共用內容儲存區。 下列各節將針對這些安裝進行規劃。

## 規劃 app-v 5.0 sequencer 部署


App-V 5.0 使用名為「排序」的程式來建立虛擬化應用程式和應用程式套件。 排序需要使用執行 App-v 5.0 排序器的電腦。

**記事** 如需 App-v 5.0 排序器新功能的相關資訊，請參閱[app-v 5.0 中新](whats-new-in-app-v-50.md)功能的**sequencer 章節變更**。

 

執行 App-v 5.0 sequencer 的電腦必須符合最低系統需求。 如需這些需求的清單，請參閱[App-V 5.0 支援的](app-v-50-supported-configurations.md)設定。

在理想的情況下，您應該在執行為虛擬機器的電腦上安裝排序器。 這可讓您更輕鬆地將執行 sequencer 的電腦還原為「乾淨」狀態，然後再將另一個應用程式排序。 當您使用虛擬機器安裝排序器時，請執行下列步驟：

1.  安裝所有關聯的排序器必備元件。

2.  安裝排序器。

3.  拍攝環境的「快照」。

**重要** 您應該讓貴公司的安全小組審查並核准連續處理程式規劃。 出於安全性考慮，您應該將 sequencer 作業保持在與生產環境不同的實驗中。 根據您的業務需求，分隔相片順序可以簡單或完整地進行。 先後順序電腦必須能夠連線到公司網路，才能將完成的套件複製到生產伺服器。 不過，因為先後順序電腦通常不使用防防毒保護，所以不能在未受保護的商業網路上運作。 例如，您可能可以在防火牆之後或在隔離的網段上運作。 您也可以使用被設定為共用隔離虛擬網路的虛擬機器。 依照您的公司安全性原則來安全地解決這些問題。

 

[如何安裝 Sequencer](how-to-install-the-sequencer-beta-gb18030.md)

## 規劃 App-v 5.0 用戶端部署


若要在目的電腦上執行虛擬化套件，您必須在目的電腦上安裝 App-v 5.0 用戶端。 App-V 5.0 用戶端是在目的電腦上執行虛擬化應用程式的元件。 用戶端可讓使用者與圖示和特定檔案類型互動，以啟動虛擬化的應用程式。 用戶端也可協助從管理伺服器取得應用程式內容，並在用戶端啟動應用程式之前，先緩存內容。 以下是兩種不同的用戶端類型：遠端桌面服務的用戶端，在遠端桌面工作階段主機（RD 工作階段主機）伺服器系統和應用程式-V 5.0 用戶端（適用于所有其他電腦）上使用。

App-V 5.0 用戶端應該使用安裝程式命令列，或在安裝完成後使用 PowerShell 腳本進行設定。

您必須小心地定義這些設定，才能加速 App-V 5.0 用戶端軟體的部署。 當您的電腦位於不同的辦公室，且用戶端必須設定為使用不同的來源位置時，這一點尤為重要。

您也必須決定將如何部署用戶端軟體。 雖然您可以在每個電腦上手動部署用戶端，但大多陣列織想要透過自動化程式來部署用戶端。 較大型的組織可能有一個可操作的電子軟體發佈（ESD）系統，這是理想的用戶端部署系統。 如果不存在 ESD 系統，您可以使用貴組織的標準安裝軟體方法。 可能的方法包括群組原則或各種腳本技術。 根據用戶端電腦的數量和不同位置而定，此部署程式可能會很複雜。 您必須使用結構化的方法，以確保所有電腦都能以正確的設定來取得已安裝的用戶端。

如需用戶端最低需求的清單，請參閱[App-V 5.0 先決條件](app-v-50-prerequisites.md)。

[如何部署 App-V 用戶端](how-to-deploy-the-app-v-client-gb18030.md)

## <a href="" id="bkmk-client-coexist"></a>規劃 App-v 用戶端共存


您可以並排部署 app-v 5.0 用戶端與 App-v 4.6 用戶端。 用戶端共存需要您使用部署設定檔或使用者設定檔來新增或發佈虛擬化的應用程式，因為這些設定檔案中必須設定 App-V 5.0 才能與 App-v 4.6 用戶端搭配使用的特定設定。 使用用戶端或伺服器升級套件時，套件必須重新提交設定檔。 對於任何有對應設定檔的套件而言，這是正確的，因此它不是用戶端共存所特有的。 不過，如果您在套件升級期間沒有提交設定檔案，則在共存案例中，封裝狀態將無法如期運作。

App-v 5.0 動態配置檔案自訂特定使用者的套件。 您必須先建立動態使用者配置（.xml）檔案或動態部署設定檔，才能使用它們。 若要建立檔案，需要執行高級手動操作。

使用動態使用者設定檔案時，不會使用資訊清單檔案中的任何應用程式-V 5.0 資訊。 這表示動態使用者設定檔案必須包含在資訊清單檔案中與 App-v 5.0 專用之延伸的所有內容，以及您想要進行的變更，例如刪除和更新。 如需如何建立自訂設定檔的詳細資訊，請參閱[如何使用 app-v 5.0 管理主控台來建立自訂的設定檔](how-to-create-a-custom-configuration-file-by-using-the-app-v-50-management-console.md)。

[如何在同一部電腦上部署 app-v 4.6 和 App-v 5.0 用戶端](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)

## <a href="" id="bkmk-plan-for-scs"></a>規劃 app-v 5.0 共用內容存放區（SCS）


App-V 5.0 的 [共用內容存放區] 模式可讓執行 App-v 5.0 用戶端的電腦執行虛擬化的應用程式，而不會將任何套件內容儲存在執行 App-v 5.0 用戶端的電腦上。 只有在用戶端要求時，才會將虛擬應用程式流式處理至目的電腦。

下列清單顯示使用 App-v 5.0 共用內容存放區的一些優點：

-   減少 app 對應用程式和多使用者應用程式的衝突，因而減少迴歸測試的需求

-   減少部署風險，加速應用程式部署

-   簡化的設定檔管理

[如何安裝 App-V 5.0 用戶端以使用共用內容存放區模式](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)






## <a href="" id="other-resources-for-the-app-v-5-0-deployment-"></a>App-V 5.0 部署的其他資源


[規劃部署 App-V](planning-to-deploy-app-v.md)

 

 





