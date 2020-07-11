---
title: App-V 與 Windows AppLocker 的互通性
description: App-V 與 Windows AppLocker 的互通性
author: dansimp
ms.assetid: 9a488034-607d-411c-b495-ff184c726f49
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6f67bb87c0a4474acee3c4982b65c930e86c4917
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809279"
---
# <span data-ttu-id="b5011-103">App-V 與 Windows AppLocker 的互通性</span><span class="sxs-lookup"><span data-stu-id="b5011-103">App-V Interoperability with Windows AppLocker</span></span>


<span data-ttu-id="b5011-104">Microsoft Application Virtualization (的 4.5 SP1 版本，app-v) 用戶端支援 Windows 7 的 AppLocker 功能。</span><span class="sxs-lookup"><span data-stu-id="b5011-104">Version 4.5 SP1 of the Microsoft Application Virtualization (App-V) client supports the AppLocker feature of Windows 7.</span></span> <span data-ttu-id="b5011-105">AppLocker 功能可讓 IT 系統管理員指定哪些應用程式受到限制，無法在電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="b5011-105">The AppLocker feature enables IT administrators to specify which applications are restricted from running on computers.</span></span> <span data-ttu-id="b5011-106">本檔說明如何設定 AppLocker 規則，以搭配使用 App-v 虛擬環境和虛擬化應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5011-106">This document describes how to configure the AppLocker rules to work with the App-V virtual environment and virtualized applications.</span></span>

<span data-ttu-id="b5011-107">**記事** 必須先啟用 Windows AppLocker，才能為虛擬應用程式設定 Windows AppLocker 規則。</span><span class="sxs-lookup"><span data-stu-id="b5011-107">**Note** Windows AppLocker must first be enabled before configuring Windows AppLocker rules for virtual applications.</span></span> <span data-ttu-id="b5011-108">如需啟用 Windows AppLocker 的詳細資訊，請參閱[Windows applocker](https://go.microsoft.com/fwlink/?LinkId=156732) (https://go.microsoft.com/fwlink/?LinkId=156732) 。</span><span class="sxs-lookup"><span data-stu-id="b5011-108">For more information about enabling Windows AppLocker, [Windows AppLocker](https://go.microsoft.com/fwlink/?LinkId=156732) (https://go.microsoft.com/fwlink/?LinkId=156732).</span></span>

 

## <span data-ttu-id="b5011-109">針對虛擬應用程式設定 Windows AppLocker 規則</span><span class="sxs-lookup"><span data-stu-id="b5011-109">Configuring Windows AppLocker Rules for Virtual Applications</span></span>


<span data-ttu-id="b5011-110">本機管理員可以建立 Windows AppLocker 規則，限制執行程式的可執行檔 ( .exe 檔案) 、Windows Installer 檔案 ( .msi 與 .msp 檔案) ，以及腳本 ( .ps、.bat、.cmd、.vbs 和 .js 檔案) 。</span><span class="sxs-lookup"><span data-stu-id="b5011-110">Local administrators can create Windows AppLocker rules that restrict the running of program executables (.exe files), Windows Installer files (.msi and .msp files), and scripts (.ps, .bat, .cmd, .vbs and .js files).</span></span> <span data-ttu-id="b5011-111">系統管理員會使用已安裝 App-v 用戶端且已將所有相關虛擬應用程式流入用戶端快取的參考電腦來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b5011-111">The administrator does this by using a reference computer that has the App-V client installed and that has all the relevant virtual applications streamed to the client cache.</span></span> <span data-ttu-id="b5011-112">然後，系統管理員會使用本機安全性原則的 Windows AppLocker 區段 Microsoft 管理主控台 (MMC) 在參考電腦上的管理單元來建立規則。</span><span class="sxs-lookup"><span data-stu-id="b5011-112">The administrator then uses the Windows AppLocker section of the Local Security Policy Microsoft Management Console (MMC) snap-in on the reference computer to create the rules.</span></span>

<span data-ttu-id="b5011-113">當您流覽以尋找您要為其建立規則的目錄路徑或特定檔案時，您可以使用隱藏共用的路徑來存取 app-v 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="b5011-113">When you browse to find a directory path or specific file for which you want to create a rule, you can access the App-V drive by using the path to the hidden share.</span></span> <span data-ttu-id="b5011-114">例如，您可以流覽至 \\\\localhost\\Q $，其中 App-v 磁片磁碟機是磁碟機 Q。不過，若要建立規則，您必須編輯路徑，移除 \\\\localhost\\Q $ 的參照，然後改為使用 Q:\\。</span><span class="sxs-lookup"><span data-stu-id="b5011-114">For example, you can browse to \\\\localhost\\Q$, where the App-V drive is drive Q. However, to create the rule, you must edit the path to remove the reference to \\\\localhost\\Q$ and use Q:\\ instead.</span></span> <span data-ttu-id="b5011-115">您必須啟動參考電腦上的每個應用程式，才能存取應用程式的檔案，且需要系統管理許可權才能流覽至 \\\\localhost\\Q $。</span><span class="sxs-lookup"><span data-stu-id="b5011-115">You must start each application on the reference computer to access the application’s files, and administrative rights are required to browse to \\\\localhost\\Q$.</span></span>

 

 





