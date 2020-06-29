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
# <span data-ttu-id="d33d9-103">如何連接至 Application Virtualization 系統</span><span class="sxs-lookup"><span data-stu-id="d33d9-103">How to Connect to an Application Virtualization System</span></span>


<span data-ttu-id="d33d9-104">您必須先將應用程式虛擬化伺服器管理主控台連線到應用程式虛擬化系統，才能使用管理主控台來管理應用程式、檔案類型關聯、套件、應用程式授權、伺服器群組、提供者原則和管理員。</span><span class="sxs-lookup"><span data-stu-id="d33d9-104">You must connect the Application Virtualization Server Management Console to an Application Virtualization System before you can use the management console to manage applications, file type associations, packages, application licenses, server groups, provider policies and administrators.</span></span> <span data-ttu-id="d33d9-105">下列程式概述將主機連線到應用程式虛擬化系統時必須遵循的步驟。</span><span class="sxs-lookup"><span data-stu-id="d33d9-105">The following procedure outlines the steps you must follow to connect the console to an Application Virtualization System.</span></span>

**<span data-ttu-id="d33d9-106">連接到應用程式虛擬化系統</span><span class="sxs-lookup"><span data-stu-id="d33d9-106">To connect to an Application Virtualization System</span></span>**

1. <span data-ttu-id="d33d9-107">以滑鼠右鍵按一下 [**範圍**] 窗格中的 [應用程式虛擬化系統] 節點，然後從快顯功能表中選取 **[連線至應用程式虛擬化系統]** 。</span><span class="sxs-lookup"><span data-stu-id="d33d9-107">Right-click the Application Virtualization System node in the **Scope** pane, and select **Connect to Application Virtualization System** from the pop-up menu.</span></span>

   **<span data-ttu-id="d33d9-108">注意</span><span class="sxs-lookup"><span data-stu-id="d33d9-108">Note</span></span>**  
   <span data-ttu-id="d33d9-109">應用程式虛擬化伺服器管理有三個元件：應用程式虛擬化管理主控台、管理 Web 服務，以及 SQL 資料存儲。</span><span class="sxs-lookup"><span data-stu-id="d33d9-109">There are three components to Application Virtualization server management: the Application Virtualization Management Console, the Management Web Service, and the SQL Datastore.</span></span> <span data-ttu-id="d33d9-110">如果這些元件分佈在不同的物理電腦中，您必須正確設定安全性，才能讓元件在整個系統中通訊。</span><span class="sxs-lookup"><span data-stu-id="d33d9-110">If these components are distributed across different physical machines, you must configure security properly for the components to communicate across the system.</span></span> <span data-ttu-id="d33d9-111">如需詳細資訊，請參閱下列手冊及文章：</span><span class="sxs-lookup"><span data-stu-id="d33d9-111">For more information, see the following manuals and articles:</span></span>

   <span data-ttu-id="d33d9-112">[如何將伺服器設定為信任委派](https://go.microsoft.com/fwlink/?LinkID=166682)（https://go.microsoft.com/fwlink/?LinkID=166682)</span><span class="sxs-lookup"><span data-stu-id="d33d9-112">[How to Configure the Server to be Trusted for Delegation](https://go.microsoft.com/fwlink/?LinkID=166682) (https://go.microsoft.com/fwlink/?LinkID=166682)</span></span>

   <span data-ttu-id="d33d9-113">[應用程式虛擬化系統的規劃與部署指南](https://go.microsoft.com/fwlink/?LinkID=122063)（https://go.microsoft.com/fwlink/?LinkID=122063)</span><span class="sxs-lookup"><span data-stu-id="d33d9-113">[Planning and Deployment Guide for the Application Virtualization System](https://go.microsoft.com/fwlink/?LinkID=122063) (https://go.microsoft.com/fwlink/?LinkID=122063)</span></span>

   <span data-ttu-id="d33d9-114">[應用程式虛擬化系統的操作指南](https://go.microsoft.com/fwlink/?LinkID=133129)（https://go.microsoft.com/fwlink/?LinkID=133129)</span><span class="sxs-lookup"><span data-stu-id="d33d9-114">[Operations Guide for the Application Virtualization System](https://go.microsoft.com/fwlink/?LinkID=133129) (https://go.microsoft.com/fwlink/?LinkID=133129)</span></span>

   <span data-ttu-id="d33d9-115">Microsoft 知識庫中的[文章 930472](https://go.microsoft.com/fwlink/?LinkId=114647) （https://go.microsoft.com/fwlink/?LinkId=114647)</span><span class="sxs-lookup"><span data-stu-id="d33d9-115">[Article 930472](https://go.microsoft.com/fwlink/?LinkId=114647) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=114647)</span></span>

   <span data-ttu-id="d33d9-116">Microsoft 知識庫中的[文章 930565](https://go.microsoft.com/fwlink/?LinkId=114648) （https://go.microsoft.com/fwlink/?LinkId=114648)</span><span class="sxs-lookup"><span data-stu-id="d33d9-116">[Article 930565](https://go.microsoft.com/fwlink/?LinkId=114648) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=114648)</span></span>

     

2. <span data-ttu-id="d33d9-117">完成 [連線**至應用程式虛擬化系統**] 對話方塊中的欄位：</span><span class="sxs-lookup"><span data-stu-id="d33d9-117">Complete the fields in the **Connect to Application Virtualization System** dialog box:</span></span>

   1. <span data-ttu-id="d33d9-118">[ **Web 服務主機名稱**]-輸入您想要連線的應用程式虛擬化系統名稱，或輸入**localhost**以連線到本機伺服器。</span><span class="sxs-lookup"><span data-stu-id="d33d9-118">**Web Service Host Name**—Enter the name of the Application Virtualization System to which you want to connect, or enter **localhost** to connect to the local server.</span></span>

   2. <span data-ttu-id="d33d9-119">[**使用安全**連線]-如果您想要以安全連線連線到伺服器，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d33d9-119">**Use Secure Connection**—Select this check box if you want to connect to the server with a secure connection.</span></span>

   3. <span data-ttu-id="d33d9-120">**Port （埠**）-輸入您想要用於連線的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="d33d9-120">**Port**—Enter the port number you want to use for the connection.</span></span> <span data-ttu-id="d33d9-121">**80**是預設的一般埠號， **443**是安全埠號碼。</span><span class="sxs-lookup"><span data-stu-id="d33d9-121">**80** is the default regular port number, and **443** is the secure-port number.</span></span>

   4. <span data-ttu-id="d33d9-122">[**使用目前的 Windows 帳戶**]：選取此選項按鈕以使用目前的 windows 帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="d33d9-122">**Use Current Windows Account**—Select this radio button to use the current Windows account credentials.</span></span>

   5. <span data-ttu-id="d33d9-123">[**指定 Windows 帳戶**]：如果您要以不同的使用者身分連線至伺服器，請選取此選項按鈕。</span><span class="sxs-lookup"><span data-stu-id="d33d9-123">**Specify Windows Account**—Select this radio button when you want to connect to the server as a different user.</span></span>

   6. <span data-ttu-id="d33d9-124">**Name （名稱**）：使用*DOMAIN\\username*或 username@domain 格式，輸入新使用者的名稱 <em> </em> 。</span><span class="sxs-lookup"><span data-stu-id="d33d9-124">**Name**—Enter the name of the new user by using either the *DOMAIN\\username* or the <em>username@domain</em> format.</span></span>

   7. <span data-ttu-id="d33d9-125">**密碼**：輸入與新使用者相對應的密碼。</span><span class="sxs-lookup"><span data-stu-id="d33d9-125">**Password**—Enter the password that corresponds to the new user.</span></span>

3. <span data-ttu-id="d33d9-126">按一下 **\[確定\]**。</span><span class="sxs-lookup"><span data-stu-id="d33d9-126">Click **OK**.</span></span>

## <span data-ttu-id="d33d9-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="d33d9-127">Related topics</span></span>


[<span data-ttu-id="d33d9-128">如何在 Application Virtualization 伺服器管理主控台中執行系統管理工作</span><span class="sxs-lookup"><span data-stu-id="d33d9-128">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





