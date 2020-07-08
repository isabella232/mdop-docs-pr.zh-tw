---
title: 如何安裝和設定 Default Application
description: 如何安裝和設定 Default Application
author: dansimp
ms.assetid: 5c5d5ad1-af40-4f83-8234-39e972f2c29a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1083de7a8ebf94bce0b41c0d3c3edf350a9aff38
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801389"
---
# 如何安裝和設定 Default Application


預設的應用程式是在安裝過程中提供，而且會在安裝期間自動複製到 Microsoft Application Virtualization （App-v）管理伺服器。 它是用來確認管理伺服器已正確安裝及設定，但必須發佈至 Microsoft Application Virtualization （App-v）用戶端，才能讓使用者存取。

使用下列程式發佈預設的應用程式，並將它資料流。

**發佈預設應用程式**

1.  使用安裝期間指定的 App-v 系統管理員群組成員的帳戶登入 App-v Management 伺服器。

2.  在 App-v Management Server 上，按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [**應用程式虛擬化管理主控台**]。

3.  在應用程式 V 管理主控台中，按一下 [**動作**]，然後按一下 **[連線至應用程式虛擬化系統]**。

4.  在 [**設定**連線] 頁面上，清除 [**使用安全**連線] 核取方塊。

5.  在 [ **Web 服務主機名稱**] 方塊中，輸入 App V 管理伺服器的完整功能變數名稱（FQDN），然後按一下 **[確定]**。

    **記事** 如果您的 Web 服務主機名稱已安裝在管理伺服器上，您也可以使用**localhost**作為它。

     

6.  在 App-v 管理主控台中，以滑鼠右鍵按一下 [**伺服器**] 節點，然後按一下 [**系統選項**]。

7.  在 [**一般**] 索引標籤的 [**預設內容路徑**] 方塊中，輸入您在安裝期間在伺服器上建立之內容資料夾的通用命名慣例（UNC）路徑;例如，\\ &lt; 伺服器名稱 &gt; \\Content，然後按一下 **[確定]**。

    **重要** 使用伺服器名稱的 FQDN，即可讓用戶端正確解析名稱。

     

8.  在 App-V 管理主控台的 [功能窗格] 中，展開 [**伺服器**] 節點，然後按一下 [**應用程式**]。

9.  在主題窗格中，按一下 [**預設應用程式**]，然後在 [**動作**] 窗格中按一下 [**屬性**]。

10. 在 [**屬性**] 對話方塊中，按一下 [ **OSD 路徑**] 方塊旁的 **[流覽]**。

11. 在 [**開啟**舊檔] 對話方塊中，輸入您在安裝期間在伺服器上建立之內容資料夾的 UNC 路徑;例如，\\ &lt; Server Name &gt; \\Content，然後按 enter。 您必須使用實際的伺服器名稱，且無法在這裡使用**localhost** 。

    **重要** 確認**OSD 路徑**和**圖示路徑**方塊中的值都是 UNC 格式（例如，\\ &lt; Server Name &gt; \\Content\\DefaultApp.ico），並指向您在安裝伺服器時所建立的內容資料夾。 請勿使用**localhost**或包含磁片磁碟機盤符的檔案路徑（例如 c:\\program files Files\\..）\\..內容.

     

12. 選取 [DefaultApp] 檔案，然後按一下 [**開啟**]。

13. 重複上述步驟來設定圖示路徑。

14. 按一下 [**存取許可權**] 索引標籤，確認 app-v 使用者群組擁有應用程式的存取許可權。

15. 按一下 [**快速鍵**] 索引標籤，然後按一下 [**發佈至使用者的桌面**]。 按一下 \[確定\] ****。

16. 開啟 [Windows 資源管理器]，然後找到 [內容目錄]。

17. 按兩下 DefaultApp 的 .osd 檔案，然後使用記事本開啟該檔案。

18. 找出包含**HREF**標記的那一行，然後將它變更為下列程式碼：

         `CODEBASEHREF=”RTSP://<FQDN of your server>:554/DefaultApp.sft”`

    或者，如果您使用的是 RTSPS：

         `CODEBASEHREF=”RTSPS://<FQDN of your server>:322/DefaultApp.sft”`

19. 關閉 DefaultApp 檔案，然後儲存變更。

**若要將預設的應用程式串流**

1.  在已安裝應用程式 V 用戶端的電腦上，請以在安裝伺服器期間指定的應用程式虛擬使用者群組成員的使用者身分登入。

2.  在桌上型電腦上，會出現**預設的應用程式虛擬化應用程式**快捷方式。 按兩下快捷方式以啟動應用程式。

3.  在 Windows 通知區域上方顯示的狀態列，會報告應用程式正在啟動。 如果應用程式啟動成功，則會顯示預設應用程式的標題畫面。 按一下 **[確定**] 以關閉對話方塊。 您現在已確認 App-V 系統正在正常運作。

## 相關主題


[如何針對以伺服器為基礎的部署設定伺服器](how-to-configure-servers-for-server-based-deployment.md)

 

 





