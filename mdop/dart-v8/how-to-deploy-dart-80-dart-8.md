---
title: 如何部署 DaRT 8.0
description: 如何部署 DaRT 8.0
author: dansimp
ms.assetid: ab772e7a-c02f-4847-acdf-8bd362769a77
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e7d64297f7687ebc0a23add3aa749ee4719beee4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810472"
---
# 如何部署 DaRT 8.0


下列指示說明如何在您的環境中部署 Microsoft Diagnostics 和恢復工具集（DaRT）8.0。 若要取得 DaRT 軟體，請參閱[如何取得 MDOP](https://go.microsoft.com/fwlink/?LinkId=322049)。 假設您要在一部系統管理員電腦上安裝所有功能。 如果您需要在多部電腦上部署或卸載 DaRT 8.0 （例如，使用電子軟體發佈系統），可能會比較容易使用命令列安裝選項。 此區段提供可用命令列選項的描述及範例。

**重要** 安裝 DaRT 之前，請參閱[DaRT 8.0 支援](dart-80-supported-configurations-dart-8.md)的設定，以確保您已安裝所有必備軟體，且電腦符合最低系統需求。 您在其上安裝 DaRT 的電腦必須執行 Windows 8 或 Windows Server 2012。

 

您可以使用以下兩種不同的設定之一來安裝 DaRT：

-   在系統管理員電腦上安裝 DaRT 和所有的 DaRT 工具。

-   在系統管理員電腦上，只安裝您要建立 DaRT 復原影像所需的工具，然後再安裝**遠端連線檢視器**，以及在技術支援部電腦上的**故障分析**程式（選擇性）。

您可以在32位和64位版本中使用 DaRT 安裝檔。 安裝符合您執行 DaRT 復原映射嚮導之電腦之體系結構的版本，而不是您所建立之復原影像的電腦架構。

您可以使用任一版本的 DaRT 安裝檔來建立32位或64位電腦的復原影像，但是您無法為兩個32位電腦和64電腦版建立一個復原影像。

**在系統管理員電腦上安裝 DaRT 和所有 DaRT 工具**

1.  下載32位或64位版本的 DaRT 8.0 安裝程式檔案。 選擇與您要安裝 DaRT 的電腦相符的架構，並執行 DaRT 復原影像嚮導。

2.  從您下載 DaRT 8.0 的資料夾中，執行與您的系統需求相對應的**MSDaRT80.msi**安裝檔。

3.  在 [**歡迎使用 Microsoft DaRT 8.0 安裝精靈]** 頁面上，按一下 **[下一步]**。

4.  接受 Microsoft 軟體授權條款，然後按一下 **[下一步]**。

5.  在 [ **Microsoft update** ] 頁面上，選取 [**當我檢查更新時使用 Microsoft Update**]，然後按 **[下一步]**。

6.  在 [**選取安裝資料夾**] 頁面上，選取一個資料夾，或按一下 **[下一步]** ，以在預設安裝位置安裝 DaRT。

7.  在 [**安裝選項**] 頁面上，選取您要安裝的 dart 功能，或按一下 **[下一步]** 以安裝 dart 與所有功能。

8.  若要開始安裝，請按一下 [**安裝**]。

9.  成功完成安裝後，請按一下 **[完成**] 結束嚮導。

## 使用命令提示字元在系統管理員電腦上安裝 DaRT 和所有 DaRT 工具


當您安裝或卸載 DaRT 時，您可以選擇在命令提示字元執行安裝檔。 本節說明您可以在命令提示字元中安裝或卸載 DaRT 時指定的幾個不同選項範例。

下列範例顯示如何安裝所有的 DaRT 功能。

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles, DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
```

下列範例顯示如何只安裝 DaRT 復原影像嚮導。

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles, ,DaRTRecoveryImage
```

下列範例顯示如何只安裝 [損毀分析器] 和 [DaRT 遠端連線檢視器]。

``` syntax
msiexec /i MSDaRT80.msi ADDLOCAL=CommonFiles,CrashAnalyzer,RemoteViewer 
```

下列範例會建立 Windows 安裝程式的安裝記錄。 這對於調試很有用。

``` syntax
msiexec.exe /i MSDaRT80.msi /l*v log.txt 
```

**記事** 您可以新增/qn 或/qb 來執行緘默安裝。

 

**驗證 DaRT 安裝**

1.  按一下 [**開始**]，然後選取 [**診斷及損毀修復工具**組]。

    隨即會開啟 [**診斷與修復工具集**] 視窗。

2.  檢查您已成功安裝您所選取的所有 DaRT 工具。

## 相關主題


[部署 DaRT 8.0 到系統管理員電腦](deploying-dart-80-to-administrator-computers-dart-8.md)

 

 





