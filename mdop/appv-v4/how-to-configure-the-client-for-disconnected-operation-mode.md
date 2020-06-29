---
title: 如何設定中斷連線的操作模式的用戶端
description: 如何設定中斷連線的操作模式的用戶端
author: dansimp
ms.assetid: 3b48464a-b8b4-494b-93e3-9a6d9bd74652
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1c917d87996a26b330551deb04b1828c31fd3c73
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801569"
---
# <span data-ttu-id="d5cdf-103">如何設定中斷連線的操作模式的用戶端</span><span class="sxs-lookup"><span data-stu-id="d5cdf-103">How to Configure the Client for Disconnected Operation Mode</span></span>


<span data-ttu-id="d5cdf-104">[已中斷式作業] 模式可讓應用程式虛擬化（App-v）桌面用戶端或應用程式虛擬化（舊稱終端服務）用戶端在用戶端無法連線到 App V 管理伺服器時，執行儲存在用戶端檔案系統快取中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5cdf-104">The disconnected operation mode enables the Application Virtualization (App-V) Desktop Client or the Application Virtualization (App-V) Client for Remote Desktop Services (formerly Terminal Services) to run applications that are stored in the file system cache of the client when the client cannot connect to the App-V Management Server.</span></span>

<span data-ttu-id="d5cdf-105">**重要** 在大型組織中，在多個遠端桌面工作階段主機（RD 度工作階段主機）伺服器（先前的終端伺服器）都連結在伺服器陣列中，以支援許多使用者，使用單一 App-v 管理伺服器來支援多個使用者，就能代表單一故障點。</span><span class="sxs-lookup"><span data-stu-id="d5cdf-105">**Important** In a large organization where multiple Remote Desktop Session Host (RD°Session Host) servers (formerly Terminal Servers) are linked in a farm to support many users, using a single App-V Management Server to support the farm represents a single point of failure.</span></span> <span data-ttu-id="d5cdf-106">若要提供高可用性以支援 RDSession 主機場，請考慮連結兩個以上的 App-v 管理伺服器來使用相同的資料庫。</span><span class="sxs-lookup"><span data-stu-id="d5cdf-106">To provide high availability to support the RDSession Host farm, consider linking two or more App-V Management Servers to use the same database.</span></span>

 

**<span data-ttu-id="d5cdf-107">啟用中斷線上作業模式</span><span class="sxs-lookup"><span data-stu-id="d5cdf-107">To enable disconnected operation mode</span></span>**

-   <span data-ttu-id="d5cdf-108">將下列登錄機碼值設定為1，以啟用中斷操作模式：</span><span class="sxs-lookup"><span data-stu-id="d5cdf-108">Set the following registry key value equal to 1 to enable disconnected operation mode:</span></span>

    <span data-ttu-id="d5cdf-109">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="d5cdf-109">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span></span>

**<span data-ttu-id="d5cdf-110">若要設定中斷式作業模式使用的時間限制</span><span class="sxs-lookup"><span data-stu-id="d5cdf-110">To set a time limit on disconnected operation mode use</span></span>**

1.  <span data-ttu-id="d5cdf-111">將下列登錄機碼值設定為1：</span><span class="sxs-lookup"><span data-stu-id="d5cdf-111">Set the following registry key value to 1:</span></span>

    <span data-ttu-id="d5cdf-112">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="d5cdf-112">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span></span>

2.  <span data-ttu-id="d5cdf-113">將下列登錄機碼的值設定為您要限制斷開連接操作模式的分鐘數。</span><span class="sxs-lookup"><span data-stu-id="d5cdf-113">Set the following registry key value to the number of minutes you want to limit disconnected operation mode.</span></span> <span data-ttu-id="d5cdf-114">有效的值範圍為1到999999。</span><span class="sxs-lookup"><span data-stu-id="d5cdf-114">The valid range of values is 1–999999.</span></span> <span data-ttu-id="d5cdf-115">預設值為90天或129600分鐘。</span><span class="sxs-lookup"><span data-stu-id="d5cdf-115">The default value is 90 days or 129,600 minutes.</span></span>

    <span data-ttu-id="d5cdf-116">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\DOTimeoutMinutes</span><span class="sxs-lookup"><span data-stu-id="d5cdf-116">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\DOTimeoutMinutes</span></span>

**<span data-ttu-id="d5cdf-117">針對中斷線上作業模式設定遠端桌面服務的用戶端</span><span class="sxs-lookup"><span data-stu-id="d5cdf-117">To configure the Client for Remote Desktop Services for disconnected operation mode</span></span>**

1.  <span data-ttu-id="d5cdf-118">將下列登錄機碼值設定為1，以啟用中斷式操作模式：</span><span class="sxs-lookup"><span data-stu-id="d5cdf-118">Set the following registry key value to 1 to enable disconnected operation mode:</span></span>

    <span data-ttu-id="d5cdf-119">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="d5cdf-119">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation</span></span>

2.  <span data-ttu-id="d5cdf-120">將下列登錄機碼的值設定為0（零），以允許不限制中斷式操作模式的使用：</span><span class="sxs-lookup"><span data-stu-id="d5cdf-120">Set the following registry key value to 0 (zero) to allow unlimited use of disconnected operation mode:</span></span>

    <span data-ttu-id="d5cdf-121">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="d5cdf-121">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation</span></span>

3.  <span data-ttu-id="d5cdf-122">確定所有套件都預先載入到快取中，以提升效能。</span><span class="sxs-lookup"><span data-stu-id="d5cdf-122">Ensure that all packages are preloaded into the cache to improve performance.</span></span>

## <span data-ttu-id="d5cdf-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="d5cdf-123">Related topics</span></span>


[<span data-ttu-id="d5cdf-124">中斷連線的操作模式</span><span class="sxs-lookup"><span data-stu-id="d5cdf-124">Disconnected Operation Mode</span></span>](disconnected-operation-mode.md)

[<span data-ttu-id="d5cdf-125">如何使用命令列設定 App-V 用戶端登錄設定</span><span class="sxs-lookup"><span data-stu-id="d5cdf-125">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





