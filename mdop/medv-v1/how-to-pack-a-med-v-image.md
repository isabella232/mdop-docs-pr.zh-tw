---
title: 如何封裝 MED-V 映像
description: 如何封裝 MED-V 映像
author: dansimp
ms.assetid: e1ce2307-0f1b-4bf8-b146-e4012dc138d2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a330b8feca922239691bed083767c3acc57105d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810700"
---
# <span data-ttu-id="b1139-103">如何封裝 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="b1139-103">How to Pack a MED-V Image</span></span>


<span data-ttu-id="b1139-104">必須先將 MED-V 影像打包，然後才能將它新增到部署套件或上傳到伺服器。</span><span class="sxs-lookup"><span data-stu-id="b1139-104">A MED-V image must be packed before it can be added to a deployment package or uploaded to the server.</span></span>

**<span data-ttu-id="b1139-105">建立打包的 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="b1139-105">To create a packed MED-V image</span></span>**

1.  <span data-ttu-id="b1139-106">按一下 [**影像**管理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="b1139-106">Click the **Images** management button.</span></span>

2.  <span data-ttu-id="b1139-107">在 [**影像**] 模組中，按一下 [**本機打包影像**] 窗格中的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="b1139-107">In the **Images** module, in the **Local Packed Images** pane, click **New**.</span></span>

3.  <span data-ttu-id="b1139-108">在 [**打包影像建立**] 對話方塊中，執行下列其中一項動作來選取虛擬機器影像：</span><span class="sxs-lookup"><span data-stu-id="b1139-108">In the **Packed Image Creation** dialog box, select the virtual machine image by doing one of the following:</span></span>

    -   <span data-ttu-id="b1139-109">在 [**基底圖像**檔案] 欄位中，輸入為 med-v 準備的 MICROSOFT Virtual 電腦影像準備的目錄完整路徑。</span><span class="sxs-lookup"><span data-stu-id="b1139-109">In the **Base image file** field, type the full path to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

    -   <span data-ttu-id="b1139-110">按一下 **[流覽**]，流覽至準備 Med-v-V 的 MICROSOFT Virtual 電腦影像所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="b1139-110">Click **Browse** to browse to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

4.  <span data-ttu-id="b1139-111">您可以執行下列其中一項動作，以指定新影像的名稱：</span><span class="sxs-lookup"><span data-stu-id="b1139-111">Specify the name of the new image by doing one of the following:</span></span>

    -   <span data-ttu-id="b1139-112">在 [**影像名稱**] 欄位中，輸入想要的名稱。</span><span class="sxs-lookup"><span data-stu-id="b1139-112">In the **Image name** field, type the desired name.</span></span>

        **<span data-ttu-id="b1139-113">注意</span><span class="sxs-lookup"><span data-stu-id="b1139-113">Note</span></span>**  
        <span data-ttu-id="b1139-114">下列字元不能包含在影像名稱中： space " &lt; &gt; |\\ / : \* ?</span><span class="sxs-lookup"><span data-stu-id="b1139-114">The following characters cannot be included in the image name: space " &lt; &gt; | \\ / : \* ?</span></span>



~~~
    A new packed image will be created.

-   From the drop-down list, select an existing name.

    A new version of the existing image will be created.
~~~

5. <span data-ttu-id="b1139-115">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b1139-115">Click **OK**.</span></span>

   <span data-ttu-id="b1139-116">您的主機電腦上會建立新的 MED-V 封裝影像，其屬性在下表中定義。</span><span class="sxs-lookup"><span data-stu-id="b1139-116">A new MED-V packed image is created on your host computer with the properties defined in the following table.</span></span>

**<span data-ttu-id="b1139-117">注意</span><span class="sxs-lookup"><span data-stu-id="b1139-117">Note</span></span>**  
<span data-ttu-id="b1139-118">在**本機打包的影像**和**伺服器窗格上打包的影像**中，每個影像的最新版本都會顯示為父節點。</span><span class="sxs-lookup"><span data-stu-id="b1139-118">In the **Local Packed Images** and **Packed Images on Server** panes, the most recent version of each image is displayed as the parent node.</span></span> <span data-ttu-id="b1139-119">按一下父節點，以查看所有其他現有的圖像版本。</span><span class="sxs-lookup"><span data-stu-id="b1139-119">Click the parent node to view all other existing versions of the image.</span></span>



**<span data-ttu-id="b1139-120">本機打包的影像屬性</span><span class="sxs-lookup"><span data-stu-id="b1139-120">Local Packed Images Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b1139-121">屬性</span><span class="sxs-lookup"><span data-stu-id="b1139-121">Property</span></span></th>
<th align="left"><span data-ttu-id="b1139-122">描述</span><span class="sxs-lookup"><span data-stu-id="b1139-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b1139-123">圖像名稱</span><span class="sxs-lookup"><span data-stu-id="b1139-123">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="b1139-124">在管理員建立影像時所定義之打包影像的名稱。</span><span class="sxs-lookup"><span data-stu-id="b1139-124">The name of the packed image as it was defined when the administrator created the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b1139-125">版本</span><span class="sxs-lookup"><span data-stu-id="b1139-125">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="b1139-126">所顯示影像的版本。</span><span class="sxs-lookup"><span data-stu-id="b1139-126">The version of the displayed image.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b1139-127">注意</span><span class="sxs-lookup"><span data-stu-id="b1139-127">Note</span></span></strong><br/><p><span data-ttu-id="b1139-128">除非刪除，否則所有先前的版本都會保留。</span><span class="sxs-lookup"><span data-stu-id="b1139-128">All previous versions are kept unless deleted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b1139-129">檔案大小（壓縮）</span><span class="sxs-lookup"><span data-stu-id="b1139-129">File Size (compressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b1139-130">影像的實際壓縮大小。</span><span class="sxs-lookup"><span data-stu-id="b1139-130">The physical compressed size of the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b1139-131">影像大小（未壓縮）</span><span class="sxs-lookup"><span data-stu-id="b1139-131">Image Size (uncompressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b1139-132">影像的實際未壓縮大小。</span><span class="sxs-lookup"><span data-stu-id="b1139-132">The physical uncompressed size of the image.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="b1139-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="b1139-133">Related topics</span></span>


[<span data-ttu-id="b1139-134">如何安裝 MED-V 用戶端及 MED-V 管理主控台</span><span class="sxs-lookup"><span data-stu-id="b1139-134">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

[<span data-ttu-id="b1139-135">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="b1139-135">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="b1139-136">建立 MED-V 的虛擬電腦映像</span><span class="sxs-lookup"><span data-stu-id="b1139-136">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)









