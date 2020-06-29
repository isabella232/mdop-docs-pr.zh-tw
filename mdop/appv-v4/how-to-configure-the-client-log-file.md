---
title: 如何設定用戶端記錄檔
description: 如何設定用戶端記錄檔
author: dansimp
ms.assetid: dd79f8ce-61e2-4dc8-af03-2a353554a1b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 729089d683c5d102eb7eb45314583023d3362639
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801561"
---
# <span data-ttu-id="a586b-103">如何設定用戶端記錄檔</span><span class="sxs-lookup"><span data-stu-id="a586b-103">How to Configure the Client Log File</span></span>


<span data-ttu-id="a586b-104">您可以使用下列程式來設定應用程式虛擬化（App-v）用戶端記錄檔。</span><span class="sxs-lookup"><span data-stu-id="a586b-104">You can use the following procedures to configure the Application Virtualization (App-V) Client log file.</span></span>

**<span data-ttu-id="a586b-105">變更記錄檔的位置</span><span class="sxs-lookup"><span data-stu-id="a586b-105">To change the log file location</span></span>**

-   <span data-ttu-id="a586b-106">編輯下列登錄機碼值，以指定記錄檔的新路徑。</span><span class="sxs-lookup"><span data-stu-id="a586b-106">Edit the following registry key value to specify the new path for the log file.</span></span> <span data-ttu-id="a586b-107">變更這個值之後，您必須重新開機**sftlist**服務。</span><span class="sxs-lookup"><span data-stu-id="a586b-107">You must restart the **sftlist** service after changing this value.</span></span> <span data-ttu-id="a586b-108">您也可以在安裝後以互動方式變更這個位置。</span><span class="sxs-lookup"><span data-stu-id="a586b-108">This location can also be changed interactively after installation.</span></span>

    <span data-ttu-id="a586b-109">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogFileName</span><span class="sxs-lookup"><span data-stu-id="a586b-109">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogFileName</span></span>

**<span data-ttu-id="a586b-110">變更記錄報告層級</span><span class="sxs-lookup"><span data-stu-id="a586b-110">To change the log reporting level</span></span>**

-   <span data-ttu-id="a586b-111">根據預設，寫入記錄的訊息類型包括嚴重等級4（資訊）或更高的所有事件。</span><span class="sxs-lookup"><span data-stu-id="a586b-111">By default, the type of messages that are written to the log include all events of severity level 4 (Informational) or higher.</span></span> <span data-ttu-id="a586b-112">嚴重度等級會儲存在下列金鑰值中。</span><span class="sxs-lookup"><span data-stu-id="a586b-112">The severity level is stored in the following key value.</span></span> <span data-ttu-id="a586b-113">將此金鑰值設為5，即可啟用詳細記錄。</span><span class="sxs-lookup"><span data-stu-id="a586b-113">Set this key value to 5 to enable verbose logging.</span></span> <span data-ttu-id="a586b-114">在疑難排解期間，只要使用詳細記錄，就會產生大量的訊息，並導致記錄快速填入。</span><span class="sxs-lookup"><span data-stu-id="a586b-114">Use verbose logging only for short periods during troubleshooting because it will generate a very large volume of messages and cause the log to fill up quickly.</span></span>

    <span data-ttu-id="a586b-115">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMinSeverity</span><span class="sxs-lookup"><span data-stu-id="a586b-115">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMinSeverity</span></span>

**<span data-ttu-id="a586b-116">變更記錄大小</span><span class="sxs-lookup"><span data-stu-id="a586b-116">To change the log size</span></span>**

-   <span data-ttu-id="a586b-117">在應用程式虛擬化（App-v）4.5 中，記錄大小由下列登錄機碼值所控制。</span><span class="sxs-lookup"><span data-stu-id="a586b-117">In Application Virtualization (App-V) 4.5, the log size is controlled by the following registry key value.</span></span> <span data-ttu-id="a586b-118">此值預設為256MB，會定義在重設前，該記錄可能會增長的最大大小（以 MB 為單位）。</span><span class="sxs-lookup"><span data-stu-id="a586b-118">This value defaults to 256MB and defines the maximum size, in MB, that the log can grow to before being reset.</span></span>

    <span data-ttu-id="a586b-119">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMaxSize</span><span class="sxs-lookup"><span data-stu-id="a586b-119">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMaxSize</span></span>

    <span data-ttu-id="a586b-120">**小心** 此登錄機碼的值必須設定為大於零的值，才能確保記錄檔已重設。</span><span class="sxs-lookup"><span data-stu-id="a586b-120">**Caution** This registry key value must be set to a value greater than zero to ensure the log file does get reset.</span></span>

     

**<span data-ttu-id="a586b-121">變更備份份數</span><span class="sxs-lookup"><span data-stu-id="a586b-121">To change the number of backup copies</span></span>**

-   <span data-ttu-id="a586b-122">當記錄檔案達到最大大小時，當下次寫入記錄時，就會強制執行重設。</span><span class="sxs-lookup"><span data-stu-id="a586b-122">When the log file reaches the maximum size, a reset is forced when the next write to the log occurs.</span></span> <span data-ttu-id="a586b-123">[重設] 會建立新的記錄檔案，而舊的檔案會重新命名為 [備份]。</span><span class="sxs-lookup"><span data-stu-id="a586b-123">A reset causes a new log file to be created, and the old file is renamed as a backup.</span></span> <span data-ttu-id="a586b-124">下列登錄設定會控制當檔案重設時所保留的記錄檔備份複本數。</span><span class="sxs-lookup"><span data-stu-id="a586b-124">The following registry setting controls the number of backup copies of the log file that are kept when the file is reset.</span></span> <span data-ttu-id="a586b-125">預設值為4。</span><span class="sxs-lookup"><span data-stu-id="a586b-125">The default value is 4.</span></span>

    <span data-ttu-id="a586b-126">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogRolloverCount</span><span class="sxs-lookup"><span data-stu-id="a586b-126">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogRolloverCount</span></span>

    <span data-ttu-id="a586b-127">備份記錄檔案名的格式為： **sftlog\_YYYYMMDD\_hhmmss-uuu.txt** ，且以通用協調時間（UTC）為基礎，以重設時間為基礎。</span><span class="sxs-lookup"><span data-stu-id="a586b-127">The format of the backup log file names is: **sftlog\_YYYYMMDD\_hhmmss-uuu.txt** and is based on the reset time, in Universal Coordinated Time (UTC).</span></span> <span data-ttu-id="a586b-128">下表列出建立檔案名及其描述時所使用的符號。</span><span class="sxs-lookup"><span data-stu-id="a586b-128">The following table lists the symbols used in creating the file names and their descriptions.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="a586b-129">符號</span><span class="sxs-lookup"><span data-stu-id="a586b-129">Symbol</span></span></th>
    <th align="left"><span data-ttu-id="a586b-130">描述</span><span class="sxs-lookup"><span data-stu-id="a586b-130">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a586b-131">年</span><span class="sxs-lookup"><span data-stu-id="a586b-131">YYYY</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a586b-132">4位數年份</span><span class="sxs-lookup"><span data-stu-id="a586b-132">4-digit year</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a586b-133">年</span><span class="sxs-lookup"><span data-stu-id="a586b-133">MM</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a586b-134">2位數的月份（01-12）</span><span class="sxs-lookup"><span data-stu-id="a586b-134">2-digit month (01–12)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a586b-135">DD</span><span class="sxs-lookup"><span data-stu-id="a586b-135">DD</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a586b-136">月份中的第幾天（01到31）</span><span class="sxs-lookup"><span data-stu-id="a586b-136">2-digit day of the month (01–31)</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a586b-137">hh</span><span class="sxs-lookup"><span data-stu-id="a586b-137">hh</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a586b-138">小時（00–23）</span><span class="sxs-lookup"><span data-stu-id="a586b-138">hour (00–23)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a586b-139">年</span><span class="sxs-lookup"><span data-stu-id="a586b-139">mm</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a586b-140">分鐘（00–59）</span><span class="sxs-lookup"><span data-stu-id="a586b-140">minutes (00–59)</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a586b-141">ss</span><span class="sxs-lookup"><span data-stu-id="a586b-141">ss</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a586b-142">秒（00–59）</span><span class="sxs-lookup"><span data-stu-id="a586b-142">seconds (00–59)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a586b-143">uuu</span><span class="sxs-lookup"><span data-stu-id="a586b-143">uuu</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a586b-144">毫秒（000至999）</span><span class="sxs-lookup"><span data-stu-id="a586b-144">milliseconds (000–999)</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

## <span data-ttu-id="a586b-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="a586b-145">Related topics</span></span>


[<span data-ttu-id="a586b-146">如何使用命令列設定 App-V 用戶端登錄設定</span><span class="sxs-lookup"><span data-stu-id="a586b-146">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





