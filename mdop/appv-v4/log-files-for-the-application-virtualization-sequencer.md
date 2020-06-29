---
title: Application Virtualization Sequencer 的記錄檔
description: Application Virtualization Sequencer 的記錄檔
author: dansimp
ms.assetid: 1a296544-eab4-46f9-82ce-3136f8b578af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8cdf9dbc78ccdd03df5903ef4d42990099a2c53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800975"
---
# <span data-ttu-id="316dd-103">Application Virtualization Sequencer 的記錄檔</span><span class="sxs-lookup"><span data-stu-id="316dd-103">Log Files for the Application Virtualization Sequencer</span></span>


<span data-ttu-id="316dd-104">應用程式虛擬化（App-v） Sequencer 的記錄檔提供排序應用程式的詳細資訊，當您驗證功能時，或當您要解決問題時，這些檔案就會很有説明。</span><span class="sxs-lookup"><span data-stu-id="316dd-104">The log files for the Application Virtualization (App-V) Sequencer provide detailed information about sequencing applications, and they can be helpful when you are verifying functionality or when you are troubleshooting issues.</span></span>

<span data-ttu-id="316dd-105">下表提供在使用排序器時所建立的記錄檔和預設位置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="316dd-105">The following table provides information about the log files and their default locations, which are created when using the Sequencer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="316dd-106">記錄檔案名</span><span class="sxs-lookup"><span data-stu-id="316dd-106">Log File Name</span></span></th>
<th align="left"><span data-ttu-id="316dd-107">描述</span><span class="sxs-lookup"><span data-stu-id="316dd-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="316dd-108">sft-seq-log.txt</span><span class="sxs-lookup"><span data-stu-id="316dd-108">sft-seq-log.txt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="316dd-109">提供對應用程式排序的一般資訊。</span><span class="sxs-lookup"><span data-stu-id="316dd-109">Provides general information about sequencing an application.</span></span> <span data-ttu-id="316dd-110">使用此記錄做為疑難排解 Sequencer 錯誤的起點。</span><span class="sxs-lookup"><span data-stu-id="316dd-110">Use this log as a starting point for troubleshooting Sequencer errors.</span></span></p>
<p><span data-ttu-id="316dd-111">記錄檔位置： <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</span><span class="sxs-lookup"><span data-stu-id="316dd-111">Log file location: <em>%windir%\Microsoft Application Virtualization Sequencer\Logs</span></span></em></p>
<p><span data-ttu-id="316dd-112">[範本標記值]App-V 4.6 記錄檔案位置： <em> %Windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs </em> [Template 權杖值]</span><span class="sxs-lookup"><span data-stu-id="316dd-112">[Template Token Value] App-V4.6 log file location: <em>%windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs</em>[Template Token Value]</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="316dd-113">sftbt.txt</span><span class="sxs-lookup"><span data-stu-id="316dd-113">sftbt.txt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="316dd-114">提供在排序器模擬重新開機期間發生的電腦重新開機工作的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="316dd-114">Provides information about computer restart tasks that occur during the Sequencer’s simulated restart.</span></span></p>
<p><span data-ttu-id="316dd-115">記錄檔位置： <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</span><span class="sxs-lookup"><span data-stu-id="316dd-115">Log file location: <em>%windir%\Microsoft Application Virtualization Sequencer\Logs</span></span></em></p>
<p><span data-ttu-id="316dd-116">[範本標記值]App-V 4.6 記錄檔案位置： <em> %Windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs </em> [Template 權杖值]</span><span class="sxs-lookup"><span data-stu-id="316dd-116">[Template Token Value] App-V4.6 log file location: <em>%windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs</em>[Template Token Value]</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="316dd-117">SftCallBack.txt</span><span class="sxs-lookup"><span data-stu-id="316dd-117">SftCallBack.txt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="316dd-118">提供在排序期間使用之進程的一般資訊。</span><span class="sxs-lookup"><span data-stu-id="316dd-118">Provides general information about processes used during sequencing.</span></span></p>
<p><span data-ttu-id="316dd-119">記錄檔位置： <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</span><span class="sxs-lookup"><span data-stu-id="316dd-119">Log file location: <em>%windir%\Microsoft Application Virtualization Sequencer\Logs</span></span></em></p>
<p><span data-ttu-id="316dd-120">[範本標記值]App-V 4.6 記錄檔案位置： <em> %Windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs </em> [Template 權杖值]</span><span class="sxs-lookup"><span data-stu-id="316dd-120">[Template Token Value] App-V4.6 log file location: <em>%windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs</em>[Template Token Value]</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="316dd-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="316dd-121">Related topics</span></span>


[<span data-ttu-id="316dd-122">Application Virtualization Sequencer 參考資料</span><span class="sxs-lookup"><span data-stu-id="316dd-122">Application Virtualization Sequencer Reference</span></span>](application-virtualization-sequencer-reference.md)

 

 





