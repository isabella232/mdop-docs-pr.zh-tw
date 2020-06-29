---
title: 部署 MBAM 1.0 語言版本更新
description: 部署 MBAM 1.0 語言版本更新
author: dansimp
ms.assetid: 9dbd85c3-e470-4752-a90f-25754dd46dab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a819be81594efd9349e3f6c0f6559c2b810bdc9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800190"
---
# 部署 MBAM 1.0 語言版本更新


Microsoft BitLocker 管理和監控（MBAM）1.0 語言發行是 MBAM 的更新，包含新語言的支援。 新的語言為：

-   英文（zh-cn）

-   法文（fr）

-   義大利文（it）

-   德文（de）

-   西班牙文（es）

-   朝鮮文（ko）

-   日文（ja）

-   巴西葡萄牙文（pt-br）

-   俄文（ru）

-   繁體中文（zh-cn&platform-幼圓）

-   簡體中文（zh-cn&platform-cn）

MBAM 1.0 語言更新會將版本號碼從 MBAM 1.0.1237.1 變更為 MBAM 1.0.2001。

您不需要重新安裝所有的 MBAM 功能，就能新增這些其他語言。 本主題定義新增新支援之語言所需的步驟。

## 部署 MBAM 國際發行版本以 MBAM 伺服器功能


若要開始，您必須更新下列 MBAM 伺服器功能：

-   合規性與審查報告

-   管理和監控伺服器

-   原則範本

接著，您必須執行**MbamSetup.exe** ，升級在同一台伺服器上執行的 MBAM 功能。

[如何在單一伺服器上安裝 MBAM 語言更新](how-to-install-the-mbam-language-update-on-a-single-server-mbam-1.md)

[如何在分散式伺服器上安裝 MBAM 語言更新](how-to-install-the-mbam-language-update-on-distributed-servers-mbam-1.md)

## 安裝群組原則的 MBAM 語言更新


您可以在每個管理工作站上安裝 MBAM 群組原則範本，或將其複製到 [群組原則中央存放區]，讓所有群組原則管理員都能使用這些範本。 原則範本無法直接安裝在網網域控制站上。 如果您不使用群組原則中央存放區，則必須將原則手動複製到管理 MBAM 群組原則的每個網網域控制站。

若要新增 MBAM 語言原則範本，請將群組原則語言檔案從安裝「原則範本」角色的電腦上的%SystemRoot%\\PolicyDefinitions 複製到工作站電腦上的相同位置。 以下是群組原則檔案的一些範例：

-   BitLockerManagement admx

-   BitLockerUserManagement admx

-   en-us\\BitLockerManagement.adml

-   en-us\\BitLockerUserManagement.adml

-   fr-fr\\ BitLockerManagement adml

-   fr-fr\\ BitLockerUserManagement adml

-   （同樣適用于每個支援的語言）

## MBAM 國際版中的已知問題


本主題包含 Microsoft BitLocker 管理和監控國際發行的已知問題。

[MBAM 國際版本的已知問題](known-issues-in-the-mbam-international-release-mbam-1.md)

## 部署 MBAM 1.0 語言更新的其他資源


[部署 MBAM 1.0](deploying-mbam-10.md)

 

 





