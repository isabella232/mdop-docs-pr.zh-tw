---
title: 如何設定映像預先設置
description: 如何設定映像預先設置
author: dansimp
ms.assetid: 92781b5a-208f-45a4-a078-ee90cf9efd9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38ddb7a69845aa4dbcb9cbd16b84dedc04438732
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811738"
---
# 如何設定映像預先設置


**記事** 影像預暫存只適用于初始影像下載。 影像更新不支援此功能。

 

## 如何設定映像預先設置


**若要設定影像預暫存**

1.  在用戶端電腦上的 [影像存放區目錄] 底下，建立預先暫存映射的資料夾，並將其命名為*Med-v 影像*。

    **記事** 這個資料夾必須稱為*Med-v 影像*。

     

2.  在 MED-V 影像資料夾中，建立子資料夾，並將其命名為*PrestagedImages*。

    **記事** 此資料夾必須呼叫*PrestagedImages*。

     

3.  若要將存取控制清單（ACL）安全性套用至*Med-v 圖像*資料夾，請設定下列 ACL：

    **NT AUTHORITY\\Authenticated 使用者：（OI）（CI）（特殊存取權）**

                                             **READ\_CONTROL**

                                    **SYNCHRONIZE**

                                    **FILE\_GENERIC\_READ**

                                    **FILE\_READ\_DATA**

    **                                 檔案 \ _APPEND \ _DATA**

                                    **FILE\_READ\_EA**

                                    **FILE\_READ\_ATTRIBUTES**

    **NT AUTHORITY\\SYSTEM：（OI）（CI） F**

    **BUILTIN\\Administrators：（OI）（CI） F**

    **記事** 建議將 ACL 安全性套用至*Med-v 影像*資料夾。

     

4.  若要將 ACL 安全性套用至*PrestagedImages*資料夾，請設定下列 ACL：

    **NT AUTHORITY\\Authenticated 使用者：（OI）（CI）（特殊存取權）**

    **READ \ _CONTROL**

    **試**

    **檔案 \ _GENERIC \ _READ**

    **檔案 \ _READ \ _DATA**

    **檔案 \ _READ \ _EA**

    **檔案 \ _READ \ _ATTRIBUTES**

    **NT AUTHORITY\\SYSTEM：（OI）（CI） F**

    **BUILTIN\\Administrators：（OI）（CI） F**

    **記事** 建議將 ACL 安全性套用至*PrestagedImages*資料夾。

     

5.  將圖像檔案（CKM 和索引檔案）推入 [ *PrestagedImages* ] 資料夾。

    **記事** 在圖像檔案推到前階段資料夾之後，建議您執行資料完整性檢查，並將檔案標示為唯讀。

     

6.  在 MED-V 用戶端安裝中包含下列參數： *Client.MSI VMSFOLDER = "C:\\MED-V 影像"*。

## 如何更新前階段位置


**更新前階段位置**

1.  登錄機碼（ *PrestagedImagesPath*）指向預設的影像位置。 它位於下列目錄中：

    -   在 x86 `KEY_LOCAL_MACHINE\SOFTWARE\Kidaro`

    -   在 x64 `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432node`

2.  如果圖像位於不同的位置，請變更路徑。

 

 





