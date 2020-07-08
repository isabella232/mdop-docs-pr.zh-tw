---
title: 如何升級封裝
description: 如何升級封裝
author: dansimp
ms.assetid: 831c7556-6f6c-4b3a-aefb-26889094dc1a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a9b3eca2c996337d79e551784818a421f495316
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801042"
---
# 如何升級封裝


自動升級的程式與在應用程式虛擬化伺服器管理主控台中新增套件版本的程式相同。 當您在現有的套件中 resequence 應用程式時，會執行自動升級。 接著，您可以將這個新版本新增到您的伺服器以進行流式處理。

當您使用新版本升級套件時，您可以將現有版本保留不動，或將它刪除，只保留最新版本。 您可能會想要保留舊版本，以便與舊版檔相容，或讓您在將新版本提供給所有使用者之前先進行測試。

**自動升級套件**

1.  將新的 SFT 檔案複製到 Application Virtualization 伺服器的 [內容] 資料夾。

    **記事** 如果 resequencing 未新增已變更開啟軟體描述項（OSD）、圖示（.ICO）或 Sequencer 專案（SPRJ）檔案的功能，您就不需要複製這些檔案。 如果您想要所有這些檔案都顯示相同的日期，您可以包含這些檔案。

     

2.  在應用程式虛擬化伺服器管理主控台的左窗格中，展開 [**套件**]。

3.  以滑鼠右鍵按一下您要升級的套件，然後選取 [**新增版本**]。

4.  在 [**新增套件版本**] 對話方塊中，流覽或輸入新應用程式版本在 [檔案] 欄位的**完整路徑**中的完整路徑名稱。 這必須是 SFT 檔案。

5.  按 **\[下一步\]**。

6.  [**摘要**] 對話方塊會顯示檔案位置，並提示您在其中複製檔案（如果您尚未這麼做）。 驗證資訊之後，按一下 **[完成]** 。

    新版本現在已完成，且準備好進行資料流程。

## 相關主題


[如何在伺服器管理主控台中管理封裝](how-to-manage-packages-in-the-server-management-console.md)

 

 





