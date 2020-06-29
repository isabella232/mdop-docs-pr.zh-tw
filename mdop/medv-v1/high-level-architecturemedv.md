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
# <span data-ttu-id="6b59d-103">高階架構</span><span class="sxs-lookup"><span data-stu-id="6b59d-103">High-Level Architecture</span></span>


<span data-ttu-id="6b59d-104">MED-V 方案包含下列元素：</span><span class="sxs-lookup"><span data-stu-id="6b59d-104">The MED-V solution comprises the following elements:</span></span>

-   <span data-ttu-id="6b59d-105">**系統管理員定義的虛擬機器**—封裝完整的桌面環境，包括作業系統、應用程式，以及選用的管理和安全性工具。</span><span class="sxs-lookup"><span data-stu-id="6b59d-105">**Administrator-defined virtual machine**—Encapsulates a full desktop environment, including an operating system, applications, and optional management and security tools.</span></span>

-   <span data-ttu-id="6b59d-106">[**圖像知識庫**]：將所有虛擬影像儲存在標準的 IIS 伺服器上，並透過修剪傳輸技術啟用虛擬影像版本管理、用戶端驗證的影像檢索，以及高效下載（新影像或更新）。</span><span class="sxs-lookup"><span data-stu-id="6b59d-106">**Image repository**—Stores all virtual images on a standard IIS server and enables virtual images version management, client-authenticated image retrieval, and efficient download (of a new image or updates) via Trim Transfer technology.</span></span>

-   <span data-ttu-id="6b59d-107">**管理伺服器**-將影像儲存庫中的虛擬影像與系統管理員使用原則關聯至 Active Directory®使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="6b59d-107">**Management server**—Associates virtual images from the image repository along with administrator usage policies to Active Directory® users or groups.</span></span> <span data-ttu-id="6b59d-108">管理伺服器也會匯總用戶端的事件，並將它們儲存在外部資料庫（Microsoft SQL Server®）中，以供監視及報告之用。</span><span class="sxs-lookup"><span data-stu-id="6b59d-108">The management server also aggregates clients' events and stores them in an external database (Microsoft SQL Server®) for monitoring and reporting purposes.</span></span>

-   <span data-ttu-id="6b59d-109">**管理主控台**-可讓系統管理員控制管理伺服器與影像存放庫。</span><span class="sxs-lookup"><span data-stu-id="6b59d-109">**Management console**—Enables administrators to control the management server and the image repository.</span></span>

-   **<span data-ttu-id="6b59d-110">最終使用者用戶端</span><span class="sxs-lookup"><span data-stu-id="6b59d-110">End-user client</span></span>**

    1.  <span data-ttu-id="6b59d-111">虛擬影像生命週期-驗證、影像檢索，以及強制使用原則。</span><span class="sxs-lookup"><span data-stu-id="6b59d-111">Virtual image life-cycle—Authentication, image retrieval, enforcement of usage policies.</span></span>

    2.  <span data-ttu-id="6b59d-112">虛擬機器會話管理：啟動、停止、鎖定虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="6b59d-112">Virtual machine session management—Start, stop, lock the virtual machine.</span></span>

    3.  <span data-ttu-id="6b59d-113">單一桌面體驗：透過標準桌面 [開始] 功能表並與使用者桌上型電腦上的其他應用程式整合的方式，可在虛擬機器中順利安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="6b59d-113">Single desktop experience—Applications installed in the virtual machine seamlessly available through the standard desktop Start menu and integrated with other applications on the user desktop.</span></span>

<span data-ttu-id="6b59d-114">用戶端與伺服器之間的所有通訊（管理伺服器與影像儲存庫）都是在標準的 HTTP 或 HTTPS 通道上傳送。</span><span class="sxs-lookup"><span data-stu-id="6b59d-114">All communication between the client and the servers (management server and image repository) is carried on top of a standard HTTP or HTTPS channel.</span></span>

![](images/506f54d0-38fa-446a-8070-17ae26da5355.gif)

 

 





