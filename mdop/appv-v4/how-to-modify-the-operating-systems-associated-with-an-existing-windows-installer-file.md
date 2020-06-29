---
title: 如何修改與現有 Windows Installer 檔案關聯的作業系統
description: 如何修改與現有 Windows Installer 檔案關聯的作業系統
author: dansimp
ms.assetid: 0633f7e2-aebf-4e00-be02-35bc59dec420
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63184852f996cbe09b476f456f7c2b509549f4fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801222"
---
# 如何修改與現有 Windows Installer 檔案關聯的作業系統


使用下列程式來修改與使用 App-v 排序器所建立之現有 Windows Installer （**MSI**）檔案相關聯的作業系統版本。

**修改現有 Windows 安裝程式檔案的作業系統**

1.  在您的環境中，將 App-v 排序器安裝到只安裝作業系統的電腦上。 或者，您也可以在執行虛擬環境的電腦（例如 Microsoft Virtual PC）上安裝 Sequencer。 這個方法很實用，因為您可以更輕鬆地維護乾淨的順序環境，讓您可以使用最低的額外設定重複使用。 如需安裝 App-v 排序器的詳細資訊，請參閱[如何安裝排序](how-to-install-the-sequencer.md)器。

2.  將包含要修改之 Windows 安裝程式檔案的整個虛擬應用程式套件複製到執行排序器的電腦上。

3.  若要修改 Windows 安裝程式檔案，請開啟 Sequencer 視窗，選取 [**套件**  /  **開啟**]，然後流覽至儲存與 Windows 安裝程式檔案關聯之虛擬應用程式套件的位置。

4.  若要新增或移除作業系統，請選取 Sequencer 主控台中的 [**部署**] 索引標籤。 若要指定將與 Windows 安裝程式檔案相關聯的其他作業系統，請選取所需的作業系統，然後按一下指向**所選**作業系統清單控制項的箭號。

    若要移除作業系統關聯，請選取您要移除的作業系統，然後按一下指向**可用**作業系統清單控制項的箭號。

5.  若要建立將與虛擬應用程式套件相關聯的新 Windows 安裝程式，請選取 [**產生 Microsoft Windows installer （MSI）套件**]。 或者，您也可以選取 [**工具**]  /  **建立 MSI**。

    **記事** 如果您選取 [**工具** / **建立 MSI** ] 來建立新的 Windows 安裝程式檔案，您可以跳過這個程式的**步驟 6** 。

     

6.  若要儲存虛擬應用程式套件，請選取 [**封裝**  /  **儲存**]。

## 相關主題


[Application Virtualization Sequencer 的工作](tasks-for-the-application-virtualization-sequencer.md)

 

 





