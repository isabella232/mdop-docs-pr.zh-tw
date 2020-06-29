---
title: 高階架構
description: 高階架構
author: dansimp
ms.assetid: a78e12ad-5aa6-40e0-ae8b-51acaf005712
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 00df29c751653645ab4bee9762af57576a40092a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811613"
---
# 高階架構


MED-V 方案包含下列元素：

-   **系統管理員定義的虛擬機器**—封裝完整的桌面環境，包括作業系統、應用程式，以及選用的管理和安全性工具。

-   [**圖像知識庫**]：將所有虛擬影像儲存在標準的 IIS 伺服器上，並透過修剪傳輸技術啟用虛擬影像版本管理、用戶端驗證的影像檢索，以及高效下載（新影像或更新）。

-   **管理伺服器**-將影像儲存庫中的虛擬影像與系統管理員使用原則關聯至 Active Directory®使用者或群組。 管理伺服器也會匯總用戶端的事件，並將它們儲存在外部資料庫（Microsoft SQL Server®）中，以供監視及報告之用。

-   **管理主控台**-可讓系統管理員控制管理伺服器與影像存放庫。

-   **最終使用者用戶端**

    1.  虛擬影像生命週期-驗證、影像檢索，以及強制使用原則。

    2.  虛擬機器會話管理：啟動、停止、鎖定虛擬機器。

    3.  單一桌面體驗：透過標準桌面 [開始] 功能表並與使用者桌上型電腦上的其他應用程式整合的方式，可在虛擬機器中順利安裝應用程式。

用戶端與伺服器之間的所有通訊（管理伺服器與影像儲存庫）都是在標準的 HTTP 或 HTTPS 通道上傳送。

![](images/506f54d0-38fa-446a-8070-17ae26da5355.gif)

 

 





