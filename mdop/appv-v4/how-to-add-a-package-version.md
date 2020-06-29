---
title: 如何新增封裝版本
description: 如何新增封裝版本
author: dansimp
ms.assetid: dbb829c1-e5cb-4a2f-bc17-9a9bb50c671c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a60252e8b43af61ad548df30a93d8fbc9bae0cb7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808733"
---
# 如何新增封裝版本


在應用程式虛擬化伺服器管理主控台中，當您 resequence 套件時，可以使用下列程式，將新版本新增到您的伺服器以進行流式處理。

**記事** 當您使用新版本升級套件時，您可以將現有版本保留不動，或將它刪除，只保留最新版本。 您可能會想要保留舊版本，以便與舊版檔相容，或讓您在將新版本提供給所有使用者之前先進行測試。

 

**新增套件版本**

1.  將新的 SFT 檔案複製到應用程式伺服器的 [內容] 資料夾。 如果 resequencing 未將變更新增到開啟的軟體描述項（OSD）、圖示（.ICO）或 Sequencer 專案（SPRJ）檔案，您就不需要複製這些檔案。 如果您想要所有檔案都顯示相同的日期，您可以包含這些檔案。

2.  在應用程式虛擬化伺服器管理主控台的左窗格中，展開 [**套件**] 節點。

3.  以滑鼠右鍵按一下您要升級的套件，然後選擇 [**新增版本**]。

4.  在 [**新增套件版本**] 對話方塊中，流覽或輸入新應用程式檔案的路徑名稱（位於 [**套件檔案的完整路徑**] 欄位中）。 這必須是 SFT 檔案。

5.  按 **\[下一步\]**。

6.  [**摘要**] 對話方塊會顯示檔案位置，並提示您在其中複製檔案（如果您尚未這麼做）。 驗證資訊之後，按一下 **[完成]** 。

    新版本現在已完成，且準備好進行資料流程。

## 相關主題


[如何刪除封裝](how-to-delete-a-packageserver.md)

[如何在伺服器管理主控台中管理封裝](how-to-manage-packages-in-the-server-management-console.md)

 

 





