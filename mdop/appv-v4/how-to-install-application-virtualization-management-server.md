---
title: 如何安裝 Application Virtualization Management Server
description: 如何安裝 Application Virtualization Management Server
author: dansimp
ms.assetid: 8184be79-8c27-4328-a3c1-183791b5556c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfd06ee1d2448990d5a740f3d59b0e5e4b45be4d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801386"
---
# 如何安裝 Application Virtualization Management Server


應用程式虛擬化管理伺服器會將其應用程式發佈給用戶端。 在負載平衡環境（通常是大型部署）中，伺服器群組中的所有伺服器應該串流相同的應用程式。 如果應用程式虛擬化管理伺服器要發佈不同的應用程式，請將伺服器指派給不同的伺服器群組。 在這種情況下，您也可能需要增加伺服器群組的容量。

如果您已在網路上指定目的電腦，且有具有本機系統管理員許可權的登入帳戶，您可以使用下列程式來安裝應用程式虛擬化管理伺服器，並將它指派給適當的伺服器群組。

**注意**  
安裝精靈可以建立一個伺服器群組記錄（如果沒有的話），以及應用程式虛擬化管理伺服器在此群組中的成員資格記錄。



完成安裝程式後，請重新開機伺服器。

**安裝應用程式虛擬化管理伺服器**

1.  驗證並視需要卸載已安裝在目的電腦上的舊版應用程式虛擬化管理伺服器。

2.  若要開啟**Microsoft Application Virtualization 管理伺服器安裝**嚮導，請流覽至網路上應用程式虛擬化系統**setup.exe**程式的位置，或者從網路執行此程式，或將其目錄複寫到目的電腦，然後按兩下**Setup.exe**檔案。

3.  在 [**歡迎**] 頁面上，按一下 **[下一步]**。

4.  在 [**授權協定**] 頁面上，閱讀 [授權協定]，然後選取 [接受授權合約]，選取 **[我接受授權條款及條件**]。 按 **\[下一步\]**。

5.  在 [**註冊資訊**] 頁面上，您必須輸入使用者名稱和**組織**。 按 **\[下一步\]**。

6.  在 [**安裝類型**] 頁面上，選取 [**自訂**]。 按 **\[下一步\]**。 在 [**自訂安裝**] 頁面上，取消選取 [除了**應用程式虛擬化伺服器**以外的所有應用程式虛擬化系統元件]，然後按一下 **[**

    **警告**  
    如果電腦上已安裝元件，當您在 [**自訂設定**] 視窗中取消選取該元件時，系統會自動卸載該元件。



7.  在 [設定**資料庫**] 頁面上，從可用伺服器清單中選取資料庫伺服器，或選取 [**使用下列主機名稱**] 並指定**伺服器名稱**和**埠號碼**資料來新增伺服器。 按 **\[下一步\]**。

    **注意**  
    應用程式虛擬化管理伺服器不支援區分大小寫的 SQL。



~~~
If a database is available, click the radio button, select the database from the list, and then click **Next**. Setup will upgrade it to this newer version. If the name does not appear in the list, enter the name in the space provided.

**Note**  
When naming a server, do not use the backslash character (/) in the server name.

If you need to install a database, see [How to Install a Database](how-to-install-a-database.md). If you would like to create a new database for this version, select **Create a new database** and specify the name that will be assigned to the new database. You can also specify a new location for the database by selecting the check box and entering the path.
~~~



8. 在 [連線**安全模式]** 頁面上，從下拉式清單中選取所要的憑證。 按 **\[下一步\]**。

   **注意**  
   [**安全連線模式]** 設定需要伺服器從公開金鑰基礎結構將伺服器憑證提供給它。 如果伺服器上沒有安裝伺服器憑證，則此選項無法使用且無法選取。 您必須授與網路服務帳戶對正在使用之憑證的讀取存取權。



9. 在 [ **TCP 埠**設定] 頁面上，若要使用預設埠（554），請選取 [**使用預設埠（554）**]。 若要指定自訂埠，請選取 [**使用自訂埠**]，然後指定將使用的埠號碼。 按 **\[下一步\]**。

   **注意**  
   當您在非安全的環境中安裝伺服器時，您可以使用預設埠（554），或者您可以定義自訂埠。



10. 在 [**管理員群組**] 頁面上，指定在 [**組名**] 中授權管理此伺服器的安全性群組名稱。 按 **\[下一步\]**。 確認指定的群組，然後按一下 **[下一步]**。

11. 在 [**預設提供者群組**] 頁面上，指定預設提供者群組的名稱，然後按 **[下一步]**。

12. 在 [**內容路徑**] 頁面上，指定要儲存 SFT 檔案之目的電腦上的位置，然後按 **[下一步]**。

   **注意**  
   如果管理伺服器的 HTTP 或 RTSP 埠已被指派，系統會提示您選擇新的埠。 選取想要的埠，然後按 **[下一步]**。



13. 在 [**準備好安裝程式**] 頁面上，若要安裝應用程式虛擬化管理伺服器，請按一下 [**安裝**]。

   **注意**  
   如果您在嘗試完成此步驟時顯示錯誤25120，您必須啟用 IIS**管理腳本和工具**。 若要啟用此 Windows 功能，請開啟 [**程式和功能**] 控制台，選取 [**開啟或關閉 Windows 功能**]，然後流覽至 [**網際網路資訊服務]。**

   在 [ **Web 管理工具**] 底下，啟用 [ **IIS 管理腳本與工具**]。



14. 在 [**安裝精靈完成]** 畫面上，若要關閉嚮導，請按一下 **[完成**]。

   **重要**  
   安裝可能需要幾分鐘的時間才能完成。 狀態訊息會在 Windows 桌面通知區域上方閃爍，指出安裝已成功完成。

   出現提示時，不需要重新開機電腦。 不過，若要優化系統效能，建議您重新開機。



## 相關主題


[如何安裝伺服器和系統元件](how-to-install-the-servers-and-system-components.md)









