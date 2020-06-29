---
title: 管理連線群組
description: 管理連線群組
author: dansimp
ms.assetid: 1a9c8f26-f421-4b70-b7e2-da8118e8198c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2e57b9dbe56072e6049e8fabef5705c374d022c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800379"
---
# <span data-ttu-id="f56ea-103">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="f56ea-103">Managing Connection Groups</span></span>


<span data-ttu-id="f56ea-104">[連線群組] 可讓套件內的應用程式在虛擬環境中彼此互動，並與系統其餘部分隔離。</span><span class="sxs-lookup"><span data-stu-id="f56ea-104">Connection groups enable the applications within a package to interact with each other in the virtual environment, while remaining isolated from the rest of the system.</span></span> <span data-ttu-id="f56ea-105">透過使用連線群組，管理員可以獨立管理套件，而且可以避免不得不將相同的應用程式多次新增到用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="f56ea-105">By using connection groups, administrators can manage packages independently and can avoid having to add the same application multiple times to a client computer.</span></span>

<span data-ttu-id="f56ea-106">**記事** 在舊版 App-V 5.0 中，連線群組稱為「動態套件組合」。</span><span class="sxs-lookup"><span data-stu-id="f56ea-106">**Note** In previous versions of App-V 5.0, connection groups were referred to as Dynamic Suite Composition.</span></span>

 

**<span data-ttu-id="f56ea-107">本主題內容如下：</span><span class="sxs-lookup"><span data-stu-id="f56ea-107">In this topic:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><a href="about-the-connection-group-virtual-environment.md" data-raw-source="[About the Connection Group Virtual Environment](about-the-connection-group-virtual-environment.md)"><span data-ttu-id="f56ea-108">關於連線群組虛擬環境</span><span class="sxs-lookup"><span data-stu-id="f56ea-108">About the Connection Group Virtual Environment</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="f56ea-109">描述連線群組虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="f56ea-109">Describes the connection group virtual environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="about-the-connection-group-file.md" data-raw-source="[About the Connection Group File](about-the-connection-group-file.md)"><span data-ttu-id="f56ea-110">關於連線群組檔案</span><span class="sxs-lookup"><span data-stu-id="f56ea-110">About the Connection Group File</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="f56ea-111">描述連線群組檔案。</span><span class="sxs-lookup"><span data-stu-id="f56ea-111">Describes the connection group file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-create-a-connection-group.md" data-raw-source="[How to Create a Connection Group](how-to-create-a-connection-group.md)"><span data-ttu-id="f56ea-112">如何建立連線群組</span><span class="sxs-lookup"><span data-stu-id="f56ea-112">How to Create a Connection Group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="f56ea-113">說明如何建立新的連線群組。</span><span class="sxs-lookup"><span data-stu-id="f56ea-113">Explains how to create a new connection group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md" data-raw-source="[How to Create a Connection Group with User-Published and Globally Published Packages](how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md)"><span data-ttu-id="f56ea-114">如何以使用者發佈的套件與全域發佈的套件建立連線群組</span><span class="sxs-lookup"><span data-stu-id="f56ea-114">How to Create a Connection Group with User-Published and Globally Published Packages</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="f56ea-115">說明如何建立新的連線群組，其中包含發佈給使用者並全域發佈的套件組合。</span><span class="sxs-lookup"><span data-stu-id="f56ea-115">Explains how to create a new connection group that contains a mix of packages that are published to the user and published globally.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-delete-a-connection-group.md" data-raw-source="[How to Delete a Connection Group](how-to-delete-a-connection-group.md)"><span data-ttu-id="f56ea-116">如何刪除連線群組</span><span class="sxs-lookup"><span data-stu-id="f56ea-116">How to Delete a Connection Group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="f56ea-117">說明如何刪除連接群組。</span><span class="sxs-lookup"><span data-stu-id="f56ea-117">Explains how to delete a connection group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-publish-a-connection-group.md" data-raw-source="[How to Publish a Connection Group](how-to-publish-a-connection-group.md)"><span data-ttu-id="f56ea-118">如何發佈連線群組</span><span class="sxs-lookup"><span data-stu-id="f56ea-118">How to Publish a Connection Group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="f56ea-119">說明如何發佈連線群組。</span><span class="sxs-lookup"><span data-stu-id="f56ea-119">Explains how to publish a connection group.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="f56ea-120">App-V 5.0 連線群組的其他資源</span><span class="sxs-lookup"><span data-stu-id="f56ea-120">Other resources for App-V 5.0 connection groups</span></span>


-   [<span data-ttu-id="f56ea-121">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="f56ea-121">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





