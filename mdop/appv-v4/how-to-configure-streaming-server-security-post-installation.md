---
title: 如何設定安裝後續串流伺服器安全性
description: 如何設定安裝後續串流伺服器安全性
author: dansimp
ms.assetid: 9bde3677-d1aa-4dcc-904e-bb49a268d748
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e1945b38da5dd50c0bd2fb0c741bd92012e78586
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801602"
---
# 如何設定安裝後續串流伺服器安全性


透過登錄設定 [App-v 流式處理伺服器] 以增強安全性。 就像應用程式 V 管理伺服器一樣，必須在完成下列安裝後程式之後，使用伺服器驗證的正確 EKU 識別碼正確地提供憑證。

**在安裝後設定流式伺服器安全性**

1.  建立 MMC，新增 [**憑證**] 管理單元，然後選取 [**本機電腦憑證存放區**]。

2.  開啟電腦的**個人**憑證，然後開啟為 app-v 預配的憑證。

3.  在 [**詳細資料**] 索引標籤上，向下滾動至 [指紋]，然後在詳細資料窗格中複製雜湊。

4.  開啟 [登錄編輯程式]，然後流覽至 `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server` 。

5.  編輯 `X509CertHash` 值，在 [值] 欄位中貼上指紋雜湊，並移除所有空格。 按一下 **[確定]** 接受編輯。

6.  在 [登錄編輯程式] 中，流覽至 `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server\RtspsPorts` 。

7.  建立名為 "322" 的新**DWORD**值，然後將十進位值輸入為322或十六進位值做為142。

8.  重新開機流式處理服務。

## 相關主題


[如何設定安裝後續管理伺服器安全性](how-to-configure-management-server-security-post-installation.md)

[疑難排解憑證權限問題](troubleshooting-certificate-permission-issues.md)

 

 





