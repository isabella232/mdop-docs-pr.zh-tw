---
title: 疑難排解 Application Virtualization Sequencer
description: 疑難排解 Application Virtualization Sequencer
author: dansimp
ms.assetid: 12ea8367-0b84-44e1-a885-e0539486556b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60c47b853c74d90afc21e9ca172c0eec2a2c7a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800768"
---
# 疑難排解 Application Virtualization Sequencer


本主題包含一些資訊，您可以用來協助對應用程式虛擬化（App-v）排序器的一般問題進行疑難排解。

## 使用 App-v 排序器建立 SFTD 檔案時，會意外增加版本號碼


與 SFTD 檔案相關聯的版本號碼會意外增加。

**解決方案**

使用命令列來產生新的 sft 檔案。 若要使用命令列來建立 sft 檔案，請在命令提示字元中輸入下列內容：

**mkdiffpkg.exe &lt; 基 sft 檔案名 &gt; &lt; 差異 sft 檔案名&gt;**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a>在封裝升級後，OSD 檔案中的檔案名不正確


在您升級現有的套件後，檔案名不正確。

**解決方案**

當您開啟要升級的套件時，您應該指定根 Q:\\ 磁片磁碟機做為套件的輸出位置。 請勿將相關聯的檔案名指定為輸出位置。

## 當資料流程傳送至用戶端時，Microsoft Word2003 預設安裝會產生錯誤


當您將 Microsoft Word2003 串流到用戶端時，會傳回錯誤，但 Microsoft Word 會繼續執行。

**解決方案**

Resequence 虛擬應用程式套件，然後選取 [**完整安裝**]。

## 建立相依套件時，套件升級無法運作


當您使用套件升級建立相依套件並新增登錄專案時，它看起來會正常運作，但無法使用更新的登錄專案。

**解決方案**

登錄設定總是與原始版本的套件儲存在一起，所以除非您修復原始套件，否則不會顯示套件更新。

## 嘗試順序的錯誤。NET 2。0


當您對需要的套件進行排序時。NET 2.0，您會收到錯誤訊息。

**解決方案**

需要的排序套件順序。不支援 NET 2.0。

## 相關主題


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

 

 





