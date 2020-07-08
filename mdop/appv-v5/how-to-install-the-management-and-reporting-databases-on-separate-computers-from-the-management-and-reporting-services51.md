---
title: 如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫
description: 如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫
author: dansimp
ms.assetid: 2a67402e-3119-40ea-a247-24d166af1ced
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2332f674f10a9b60aa1cee814c6eac4ddbe4f5af
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800492"
---
# 如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫

使用下列程式在不同的電腦上安裝資料庫伺服器與管理伺服器。 您計畫在其上安裝資料庫伺服器的電腦必須執行 Microsoft SQL 支援的版本，否則安裝將會失敗。

> [!NOTE]
> 完成部署之後，系統會要求安裝服務的**MICROSOFT SQL Server 名稱**、**實例名稱**和**資料庫名稱**，才能連線至這些資料庫。

## 在不同的電腦上安裝管理資料庫和管理伺服器

1. 將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。 若要啟動 App-v 5.1 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。 按一下 **\[安裝\]**。
1. 在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。
1. 在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。** 若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。 按 **\[下一步\]**。
1. 在 [**功能選取**] 頁面上，選取您要安裝的元件，方法是選取 [**管理伺服器資料庫**] 核取方塊，然後按一下 **[下一步]**。
1. 在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。
1. 在 [**建立新的管理伺服器資料庫] 頁面**上，接受預設選項（如果適用的話），然後按 **[下一步]**。

    如果您使用的是自訂 SQL Server 實例，請選取 [**使用自訂實例**]，然後輸入實例的名稱。
    如果您使用的是自訂資料庫名稱，請選取 [**自訂**設定]，然後輸入資料庫的名稱。

1. 在 [**建立新的管理伺服器資料庫**] 頁面上，選取 [**使用遠端電腦**]，然後使用下列格式輸入遠端電腦帳戶： **Domain\\MachineAccount**。

    > [!NOTE]
    > 如果您打算在同一部電腦上部署管理伺服器，您必須選取 [**使用本機電腦**]。

1. 使用下列格式指定管理伺服器的使用者名稱**安裝系統管理員**： **Domain\\AdministratorLoginName**。 按 **\[下一步\]**。
1. 若要開始安裝，請按一下 [**安裝**]。

## 在不同的電腦上安裝報表資料庫和報表伺服器

1. 將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。 若要啟動 App-v 5.1 伺服器安裝，請以滑鼠右鍵按一下，然後以系統管理員身分執行**appv\_server\_setup.exe** 。 按一下 **\[安裝\]**。
1. 在 [**快速入門**] 頁面上，查看並接受授權條款，然後按 **[下一步]**。
1. 在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 Microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。** 若要停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。 按 **\[下一步\]**。
1. 在 [**功能選取**] 頁面上，選取您要安裝的元件，方法是選取 [**報表伺服器資料庫**] 核取方塊，然後按一下 **[下一步]**。
1. 在 [**安裝位置**] 頁面上，接受預設位置，然後按一下 **[下一步]**。
1. 在 [**建立新的報表伺服器資料庫**] 頁面上，接受預設選項（如果適用的話），然後按 **[下一步]**。

    如果您使用的是自訂 SQL Server 實例，請選取 [**使用自訂實例**]，然後輸入實例的名稱。
    如果您使用的是自訂資料庫名稱，請選取 [**自訂**設定]，然後輸入資料庫的名稱。

1. 在 [下一次**建立新報表伺服器資料庫**] 頁面上，選取 [**使用遠端電腦**]，然後使用下列格式輸入遠端電腦帳戶： **Domain\\MachineAccount**。

    > [!NOTE]
    > 如果您打算在同一部電腦上部署報表伺服器，您必須選取 [**使用本機電腦**]。

1. 使用下列格式指定 reporting server**安裝系統管理員**的使用者名稱： **Domain\\AdministratorLoginName**。 按 **\[下一步\]**。
1. 若要開始安裝，請按一下 [**安裝**]。

## 使用 App-v 5.1 資料庫腳本安裝管理和報告資料庫

1. 將 App-v 5.1 server 安裝檔案複製到您要安裝它的電腦上。
1. 若要解壓縮 App-v 5.1 資料庫腳本，請開啟命令提示字元，並指定儲存安裝盤案的位置，然後執行下列命令：

    **appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR = "InstallationExtractionLocation"**。

1. 解壓縮完成後，若要存取 App-v 5.1 資料庫腳本與指示讀我檔案，請執行下列動作：

    - App-V 5.1 管理資料庫腳本與指示讀我檔案位於下列資料夾： **InstallationExtractionLocation**  \\  **資料庫腳本**  \\  **管理資料庫**。
    - App-v 5.1 報告資料庫腳本與指示讀我檔案位於下列資料夾： **InstallationExtractionLocation**  \\  **資料庫腳本**  \\  **報告資料庫**。

1. 針對每個資料庫，將腳本複製到共用，然後依照讀我檔案中的指示進行修改。

    > [!NOTE]
    > 如需修改腳本中所需的 Sid 的詳細資訊，請參閱[如何安裝 App-v 資料庫，以及如何使用 PowerShell 轉換關聯的安全性識別碼](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md)。

1. 在執行 Microsoft SQL Server 的電腦上執行腳本。

**有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題

[部署 App-V 5.1](deploying-app-v-51.md)
