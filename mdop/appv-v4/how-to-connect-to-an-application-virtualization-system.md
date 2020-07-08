---
title: 如何連接至 Application Virtualization 系統
description: 如何連接至 Application Virtualization 系統
author: dansimp
ms.assetid: ac38216c-5464-4c0b-a4d3-3949ba6358ac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 30d60e187e1b7595fd0dce6641fa027a1df68f3d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801526"
---
# 如何連接至 Application Virtualization 系統


您必須先將應用程式虛擬化伺服器管理主控台連線到應用程式虛擬化系統，才能使用管理主控台來管理應用程式、檔案類型關聯、套件、應用程式授權、伺服器群組、提供者原則和管理員。 下列程式概述將主機連線到應用程式虛擬化系統時必須遵循的步驟。

**連接到應用程式虛擬化系統**

1. 以滑鼠右鍵按一下 [**範圍**] 窗格中的 [應用程式虛擬化系統] 節點，然後從快顯功能表中選取 **[連線至應用程式虛擬化系統]** 。

   **注意**  
   應用程式虛擬化伺服器管理有三個元件：應用程式虛擬化管理主控台、管理 Web 服務，以及 SQL 資料存儲。 如果這些元件分佈在不同的物理電腦中，您必須正確設定安全性，才能讓元件在整個系統中通訊。 如需詳細資訊，請參閱下列手冊及文章：

   [如何將伺服器設定為信任委派](https://go.microsoft.com/fwlink/?LinkID=166682)（https://go.microsoft.com/fwlink/?LinkID=166682)

   [應用程式虛擬化系統的規劃與部署指南](https://go.microsoft.com/fwlink/?LinkID=122063)（https://go.microsoft.com/fwlink/?LinkID=122063)

   [應用程式虛擬化系統的操作指南](https://go.microsoft.com/fwlink/?LinkID=133129)（https://go.microsoft.com/fwlink/?LinkID=133129)

   Microsoft 知識庫中的[文章 930472](https://go.microsoft.com/fwlink/?LinkId=114647) （https://go.microsoft.com/fwlink/?LinkId=114647)

   Microsoft 知識庫中的[文章 930565](https://go.microsoft.com/fwlink/?LinkId=114648) （https://go.microsoft.com/fwlink/?LinkId=114648)

     

2. 完成 [連線**至應用程式虛擬化系統**] 對話方塊中的欄位：

   1. [ **Web 服務主機名稱**]-輸入您想要連線的應用程式虛擬化系統名稱，或輸入**localhost**以連線到本機伺服器。

   2. [**使用安全**連線]-如果您想要以安全連線連線到伺服器，請選取此核取方塊。

   3. **Port （埠**）-輸入您想要用於連線的埠號碼。 **80**是預設的一般埠號， **443**是安全埠號碼。

   4. [**使用目前的 Windows 帳戶**]：選取此選項按鈕以使用目前的 windows 帳號憑證。

   5. [**指定 Windows 帳戶**]：如果您要以不同的使用者身分連線至伺服器，請選取此選項按鈕。

   6. **Name （名稱**）：使用*DOMAIN\\username*或 username@domain 格式，輸入新使用者的名稱 <em> </em> 。

   7. **密碼**：輸入與新使用者相對應的密碼。

3. 按一下 **\[確定\]**。

## 相關主題


[如何在 Application Virtualization 伺服器管理主控台中執行系統管理工作](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





