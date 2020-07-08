---
title: 管理 MED-V 工作區的軟體更新
description: 管理 MED-V 工作區的軟體更新
author: dansimp
ms.assetid: a28d6dcd-cb9f-46ba-8dac-1d990837a3a3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 696238a2f5ad9b7e5120f75f6cd09d890d12519b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810779"
---
# 管理 MED-V 工作區的軟體更新


您有幾種不同的選項可供您在已部署的 MED-V 工作區中提供應用程式的軟體更新。

**記事** 如需如何指定配置設定以定義 MED-V 如何接收自動更新的相關資訊，請參閱[管理 Med-v 工作區的自動更新](managing-automatic-updates-for-med-v-workspaces.md)。

 

**更新 MED-V 工作區中的軟體**

1.  **使用電子軟體發佈系統**

    如果您的組織使用電子軟體發佈系統（ESD）系統來部署軟體，您就可以使用它來提供在 MED-V 工作區上應用程式的軟體更新，就像您在物理電腦上提供應用程式的更新一樣。

2.  **使用群組原則**

    如果您的組織使用 [群組原則] 部署軟體，您就可以使用它來提供 MED-V 工作區上應用程式的軟體更新，就像您在物理電腦上提供應用程式的更新一樣。

3.  **使用應用程式虛擬化（APP-V）**

    如果您使用 MED-V 搭配 App-v，您可以在 MED-V 工作區中提供應用程式的軟體更新，方法是執行更新軟體所需的 app-v 工作區中的相關步驟。 如需詳細資訊，請參閱[應用程式虛擬化](https://go.microsoft.com/fwlink/?LinkId=122939)（ https://go.microsoft.com/fwlink/?LinkId=122939) 。

4.  **更新核心影像中的軟體**

    雖然不會被視為 MED-V 最佳做法，但您可以將軟體更新安裝至核心影像上的應用程式。 安裝更新之後，您就可以將 MED-V 工作區重新部署到您的企業，就像當初部署它一樣。

    **重要** 我們不建議這個管理軟體更新的方法。 此外，如果您更新核心影像中的軟體，並重新部署 MED-V 工作區到您的企業，第一次必須再次執行安裝程式，而且儲存在虛擬機器中的任何資料都會遺失。

     

## 相關主題


[管理 MED-V 工作區的自動更新](managing-automatic-updates-for-med-v-workspaces.md)

[如何測試應用程式發佈](how-to-test-application-publishing.md)

[如何發佈與取消發佈 MED-V 工作區上的應用程式](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





