---
title: 如何部署 DaRT 7.0
description: 如何部署 DaRT 7.0
author: dansimp
ms.assetid: 30522441-40cb-4eca-99b4-dff758f5c647
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2059b64e5f3ae7af8926bc00e5965598ede4288
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800246"
---
# 如何部署 DaRT 7.0


本主題提供在您的環境中部署 Microsoft Diagnostics 與修復工具集（DaRT）7的指示。 本主題中的第一個程式假設您要在一部系統管理員電腦上安裝所有功能。 如果您需要在多部電腦上部署或卸載 DaRT （例如，使用電子軟體發佈系統），可能會比較容易使用命令列安裝選項。 這些選項是在本主題的第二個程式中定義的，提供可用命令列選項的範例用法。

**重要** 在您安裝 DaRT 前，請確定電腦符合[DaRT 7.0 支援](dart-70-supported-configurations-dart-7.md)的設定中所列的最低系統需求。

 

**在管理員電腦上安裝 DaRT**

1.  找出您在軟體下載中收到的 DaRT 安裝檔案。

2.  按兩下與您的系統需求相對應的 DaRT 安裝檔案（32位或64位）。 DaRT 安裝檔案命名為 [ **MSDaRT70.msi**]。

3.  接受 Microsoft 軟體授權條款，然後按一下 **[下一步]**。

4.  選取要安裝 DaRT 的目的地資料夾，選取是要為所有使用者安裝 DaRT，還是只針對目前的使用者安裝 DaRT，然後按 **[下一步]**。

5.  選取安裝應該是**一般**、**自訂**或**完成**，然後按 **[下一步]**。

    -   **一般**會安裝最常使用的工具。 建議針對大多數使用者使用這個方法。

    -   [**自訂**] 可讓您選取已安裝的工具以及安裝位置。 對於高級使用者，尤其是當您在不同的技術支援電腦上安裝不同的 DaRT 工具時，尤其需要這麼做。

    -   **完整**安裝所有的 DaRT 工具，且需要最大的磁碟空間。

    選取您的安裝方法之後，請按 **[下一步]**。

6.  若要開始安裝，請按一下 [**安裝**]。

7.  成功完成安裝後，請按一下 **[完成**] 結束嚮導。

**在命令提示字元中安裝 DaRT**

1.  下列範例顯示如何安裝所有的 DaRT 功能。

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
    ```

2.  下列範例顯示如何只安裝**DaRT 復原影像嚮導**。

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage
    ```

3.  下列範例顯示如何只安裝 [損毀分析器] 和 [DaRT 遠端連線檢視器]。

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,CrashAnalyzer,RemoteViewer 
    ```

4.  下列範例會建立 Windows 安裝程式的安裝記錄。 這對於調試很有用。

    ``` syntax
    msiexec.exe /i MSDaRT70.msi /l*v log.txt 
    ```

**記事** 您可以將/qn 或/qb 新增至任何 DaRT 安裝命令提示字元選項，以執行緘默安裝。

 

## 相關主題


[部署 DaRT 7.0 到系統管理員電腦](deploying-dart-70-to-administrator-computers-dart-7.md)

 

 





