---
title: 疑難排解 Application Virtualization Sequencer 問題
description: 疑難排解 Application Virtualization Sequencer 問題
author: dansimp
ms.assetid: 2712094b-a0bc-4643-aced-5415535f3fec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8b84f37217f29ff2c08a2254d7f54ce74348d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800780"
---
# 疑難排解 Application Virtualization Sequencer 問題


本主題包含一些資訊，您可以用來協助對應用程式虛擬化（App-v）排序器的一般問題進行疑難排解。

## 使用 App-v 排序器建立 SFTD 檔案時，會意外增加版本號碼


使用命令列來產生新的 sft 檔案。 若要使用命令列來建立 sft 檔案，請在命令提示字元中輸入下列內容：

**mkdiffpkg.exe &lt; 基 sft 檔案名 &gt; &lt; 差異 sft 檔案名&gt;**

## <a href="" id="file-name-in-osd-file-is-not-correct-after-package-upgrade-"></a>在封裝升級後，OSD 檔案中的檔案名不正確


當您開啟要升級的套件時，您應該指定根 Q:\\ 磁片磁碟機做為套件的輸出位置。 請勿將相關聯的檔案名指定為輸出位置。

## 當資料流程傳送至用戶端時，Microsoft Word2003 預設安裝會產生錯誤


當您將 Microsoft Word2003 串流到用戶端時，會傳回錯誤，但 Microsoft Word 會繼續執行。

**解決方案**

Resequence 虛擬應用程式套件，然後選取 [**完整安裝**]。

## 當您建立相依的套件時，無法使用 [活動升級]


當您使用 [作用中升級] 並新增 [登錄] 專案來建立相依的套件時，它看起來會正常運作，但無法使用更新的登錄機碼目。

**解決方案**

登錄設定總是與原始版本的套件儲存在一起，所以除非您修復原始套件，否則不會顯示套件更新。

## 使用 [屬性] 頁面不會顯示 Microsoft Office2007 檔的詳細資訊


當您嘗試使用 [屬性] 頁面來查看與 Microsoft Office2007 檔相關聯的詳細資訊時，系統不會顯示詳細資訊。

**解決方案**

App-v 不支援這些屬性頁所需的命令介面延伸。

## 當您順序16位的應用程式時，不會捕獲某些登錄機碼


在 App-V 4.5 中，已從核心模式將登錄掛鉤移至 [使用者模式]。 如果您想要為使用16位安裝程式的16位應用程式或應用程式排序，您必須先設定 sequencer 電腦，讓該進程在自己的 Windows NT 虛擬 DOS 電腦（NTVDM）複本中執行。

**解決方案**

在排序應用程式之前，請在先後順序電腦上將下列全域 REGSZ 登錄機碼的值設定為「是」：

HKLM\\SYSTEM\\CurrentControlSet\\Control\\WOW\\DefaultSeparateVDM

您必須先重新開機電腦，才會生效。

## 相關主題


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

 

 





