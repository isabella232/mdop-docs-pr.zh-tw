---
title: 如何新增或移除已部署 MED-V 工作區中的 URL 重新導向資訊
description: 如何新增或移除已部署 MED-V 工作區中的 URL 重新導向資訊
author: dansimp
ms.assetid: bf55848d-bf77-452e-aaa5-4dd4868ff5bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: f0892b16bfc10e6b3f28fe99c51c2c5cedb73d7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811757"
---
# 如何新增或移除已部署 MED-V 工作區中的 URL 重新導向資訊


若要在已部署的 MED-V 工作區中編輯 URL 重新導向資訊，建議您使用 [群組原則] 來更新系統註冊。 雖然我們不建議這樣做，但您也可以使用更新的 URL 重新導向資訊來重建並重新部署 MED-V 工作區。

登錄機碼通常位於：

Computer\\HKEY\ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience

必須存在下列多字串值： `RedirectUrls`

[值資料] `RedirectUrls` 是您在使用**Med-v 工作區包裝**程式建立 med-v 工作區套件時，為重新導向所指定的所有 url 清單。 如需詳細資訊，請參閱[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)。

您可以執行下列其中一項工作來新增和移除 URL 重新導向資訊：

-   [編輯 URL 重新導向登錄機碼，並使用群組原則進行部署](#bkmk-editreg)

-   [編輯 URL 重新導向文字檔並重建 MED-V-V 工作區](#bkmk-edittext)

<a href="" id="bkmk-editreg"></a>**使用群組原則更新 URL 重新導向資訊**

1.  編輯名為的 [登錄金鑰多重字串] 值 `RedirectUrls` 。 此值通常位於：

    Computer\\HKEY\ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience

    如果您要新增 Url 至登錄機碼，請在您建立 MED-V 工作區套件時，每行輸入一個 Url。 如需詳細資訊，請參閱[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)。

2.  使用 [群組原則] 部署更新的登錄機碼。 如需如何使用群組原則的詳細資訊，請參閱[群群組原則軟體安裝](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。

**記事** 這個編輯 URL 重新導向資訊的方法是 MED-V 最佳做法。

 

<a href="" id="bkmk-edittext"></a>**使用更新的 URL 文字檔重建 MED-V 工作區**

-   從重新導向清單中新增及移除 Url 的另一種方法是更新 URL 重新導向文字檔，然後使用它來建立新的 MED-V 工作區。 接著，您可以使用部署的標準程式（例如 ESD 系統），預先重新部署 MED-V 工作區。

    **重要** 我們不建議您編輯 URL 重新導向資訊的方法。 此外，您可以隨時將 MED-V 工作區重新部署到您的企業，第一次必須再次執行安裝程式，而且儲存在虛擬機器中的任何資料都會遺失。

     

## 相關主題


[如何測試 URL 重新導向](how-to-test-url-redirection.md)

[管理部署到 MED-V 工作區的應用程式](managing-applications-deployed-to-med-v-workspaces.md)

[建立 MED-V 工作區套件](create-a-med-v-workspace-package.md)

 

 





