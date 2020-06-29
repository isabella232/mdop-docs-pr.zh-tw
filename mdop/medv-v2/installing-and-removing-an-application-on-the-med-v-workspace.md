---
title: 安裝和移除 MED-V 工作區上的應用程式
description: 安裝和移除 MED-V 工作區上的應用程式
author: dansimp
ms.assetid: 24f32720-51ab-4385-adfe-4f5a65e45fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 22cb98c167b53b1b206b8b5be2ba18fc0fba4f06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812224"
---
# 安裝和移除 MED-V 工作區上的應用程式


與主機作業系統不相容的應用程式可以在 med-v 工作區中執行，並在 MED-V 工作區中開啟，就與從主機電腦（在 [**開始**] 功能表上，或使用 localhost 快捷方式）中開啟的方式相同。

在您部署 MED-V 工作區之後，您有幾種不同的選項可供您在 MED-V 工作區中安裝及移除應用程式。 這些選項包括下列各項：

-   [使用群組原則](#bkmk-grouppolicy)

-   [使用電子軟體發佈系統](#bkmk-esd)

-   [使用應用程式虛擬化（APP-V）](#bkmk-appv)

-   [更新核心影像](#bkmk-coreimage)

**重要** 若要確保已安裝的應用程式會自動發佈到主機，請在虛擬機器上為**所有使用者**安裝應用程式。 如需應用程式發佈的詳細資訊，請參閱[如何在 Med-v 工作區發佈及取消發佈應用程式](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)。

 

**秘訣** MED-V 不支援進行內容處理的來賓對主機重新導向，例如在 MED-V 工作區中按兩下 Internet Explorer 中的 Microsoft Word 檔。 因此，必須在 MED-V 工作區中安裝所需的應用程式（例如 Microsoft Word），才能提供最終使用者可能預期的預設內容處理功能。

 

## <a href="" id="bkmk-grouppolicy"></a> 使用群組原則新增及移除應用程式


您可以使用群組原則和群組原則物件，將應用程式指派或發佈至企業中的所有或一些 MED-V 工作區。 針對指派的應用程式，當使用者登入其電腦時，應用程式就會出現在 [**開始**] 功能表上。 當他們第一次選取新的應用程式時，應用程式就會安裝並準備好使用。 針對已發佈的應用程式，應用程式不會出現在 [**開始**] 功能表上。 只有在使用者使用 [**控制台**] 中的 [**新增或移除程式**] 或開啟與應用程式相關聯的檔案時，才能安裝它。

您也可以使用群組原則與群組原則物件，從 MED-V 工作區移除應用程式。

如需如何使用 [群組原則] 新增及移除應用程式的詳細資訊，請參閱[群群組原則軟體安裝](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。

## <a href="" id="bkmk-esd"></a> 使用 ESD 系統新增及移除應用程式


電子軟體發佈（ESD）系統設計為透過網路連線將軟體及其他資訊高效部署到許多不同的電腦。 如果您的組織使用 ESD 系統來部署軟體，您就可以使用它來新增和移除 MED-V 工作區上的應用程式，就像您在物理電腦上新增及移除應用程式一樣。

## <a href="" id="bkmk-appv"></a> 使用 APP-V 新增及移除應用程式


Microsoft Application Virtualization （App-v）提供系統管理功能，可讓使用者在不需直接在那些電腦上安裝應用程式的情況下，就能將應用程式提供給終端使用者的電腦。 例如，如果您的組織有您在 Windows XP 中以 App-v 排序的應用程式，而您想要將它重新排序，則您可能會想要使用 MED-V 與 app-v，這樣就會延遲您的遷移到 Windows 7。

您可以搭配 App-v 搭配使用 MED-V，在已部署的 MED-V 工作區上新增和移除虛擬應用程式。 若要以這種方式管理應用程式，您必須先在 MED-V 客體作業系統上安裝 App-v 代理程式。 接著，您可以在 MED-V 工作區中使用 App-v 來新增和移除虛擬應用程式。

如需如何安裝及使用 App-v 的相關資訊，請參閱[應用程式虛擬化](https://go.microsoft.com/fwlink/?LinkId=122939)（ https://go.microsoft.com/fwlink/?LinkId=122939) 。

**重要** 您發佈到 MED-V 工作區的 app-v 應用程式具有無法從主機電腦重新導向至來賓虛擬機器的檔案類型關聯性。 不過，使用者仍然可以按一下 [檔案 **]，然後按一下 [** 在已發佈的 app-v 應用程式上**開啟**] 來存取這些檔案類型。

若要強制重新導向這些檔案類型關聯，請在來賓虛擬機器的命令提示字元中輸入下列內容，以在來賓虛擬機器中的命令提示字元中輸入下列內容： **sftmime/QUERY OBJ： type**。 然後，在主機電腦中對應這些檔案類型關聯。

 

## <a href="" id="bkmk-coreimage"></a> 在核心影像上新增及移除應用程式


雖然不會被視為 MED-V 最佳做法，但您可以直接在核心影像上新增及移除應用程式。 在您新增或移除應用程式之後，您就可以將 MED-V 工作區重新部署到您的企業，就像當初部署它一樣。

如需如何在核心影像上新增或移除應用程式的詳細資訊，請參閱[在 Windows 虛擬電腦映射上安裝應用程式](installing-applications-on-a-windows-virtual-pc-image.md)。

**重要** 我們不建議這個管理應用程式的方法。 如果您新增或移除核心影像上的應用程式，然後重新部署 MED-V 工作區至您的企業，第一次必須再次執行安裝程式，而且儲存在虛擬機器上的任何資料都會遺失。

 

**記事** 即使應用程式已安裝在 MED-V 工作區中，您也可能還必須先發佈應用程式，才能供使用者使用。 例如，如果安裝沒有在 [**開始**] 功能表上自動建立快捷方式，您可能必須發佈已安裝的應用程式。 同樣地，若要取消發佈應用程式，您可能必須手動移除 [**開始**] 功能表的快捷方式。

根據預設，大部分的應用程式會在安裝時發佈，在自動建立及啟用快捷方式時發佈。

 

## 相關主題


[如何測試應用程式發佈](how-to-test-application-publishing.md)

[如何發佈與取消發佈 MED-V 工作區上的應用程式](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





