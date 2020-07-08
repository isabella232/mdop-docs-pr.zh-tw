---
title: 使用 SQL 指令碼建立 APP-V 4.5 資料庫
description: 使用 SQL 指令碼建立 APP-V 4.5 資料庫
author: dansimp
ms.assetid: 6cd0b180-163e-463f-a658-939ab9a7cfa1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9ab2c102a43701bfdeaac49359b4ca3c4a063fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811480"
---
# 使用 SQL 指令碼建立 APP-V 4.5 資料庫


**此解決方案的目的是誰？** 管理應用程式虛擬化（App-v）4.5 資料庫的資訊技術專業人員。

**本指南會如何協助您？** 本方案說明如何在管理員安裝沒有 SQL Server 的「系統管理員」許可權的情況下，說明如何安裝 Microsoft Application Virtualization 伺服器的步驟。

## 概觀


安裝 Microsoft Application Virtualization 4.5 （App-v）的其中一個難題是，安裝程式假設安裝伺服器功能的使用者不僅是本機電腦系統管理員，還要擁有將裝載資料存放區之 SQL 伺服器的 SQL 系統管理員許可權。 這個需求是以資料庫及適當的角色和許可權，在安裝時建立的事實所依據。 不過，在大部分的企業中，SQL server 會與將要安裝 App-v 的基礎結構小組分開管理。 這些安全需求將使 SQL 系統管理員難以取得安裝 app-v 的應用程式許可權;同樣地，SQL 系統管理員將沒有安裝產品以供基礎結構小組使用所需的許可權。

目前，試圖安裝 App-v 的管理員必須具備 SQL 「sysadmin」許可權。 在早期版本的產品中，SQL 系統管理員允許您建立暫時的「sysadmin」帳戶或在安裝期間出現，以提供「sysadmin」許可權的認證。 在這個版本中，在發行的產品中提供腳本，供所有系統管理員在實施其基礎結構時使用。

本白皮書將討論安裝需要劃分成兩個不同工作的案例：建立 SQL 資料庫，並安裝 App-v server 功能。 SQL 系統管理員可以審查 SQL 腳本並進行修改，以解決與其他資料庫的任何衝突，或支援與其他工具的整合。 腳本的結果是允許 SQL 系統管理員準備資料庫，讓基礎結構系統管理員不需要授與 SQL server 的任何高級許可權。 在安全性原則會禁止此情況的環境中，這是很重要的。

### SQL 資料庫建立程式

SQL 腳本可讓 SQL 系統管理員建立必要的資料庫，同時也為 App-v 管理員設定許可權，以成功安裝及管理環境。 本檔稍後會列出完成這些工作的步驟。

這個程式會將資料庫建立與設定動作從實際的 App-v 安裝中分離。

**要提供給 SQL 系統管理員的資訊**

-   要成為應用程式 V 管理員的 AD 群組名稱

-   將安裝 App-v 管理伺服器的伺服器名稱

**要傳回給基礎結構管理員的資訊**

-   資料庫伺服器或實例的名稱與 App-v 資料庫的名稱

資料庫準備就緒之後，App-v 管理員就可以執行 App-v 安裝，而不需要 SQL 系統管理員許可權。

### 使用 SQL 安裝程式腳本

**需求**

以下是使用位於選取的解壓位置根目錄之 support\\createdb 資料夾中的腳本需求清單。

-   必須將腳本複製到電腦上要執行的可寫位置（請務必在複製這些腳本後移除其唯讀屬性），而且必須在該電腦上載入 SQL 用戶端工具（osql 只需要在本機電腦上執行範例批次處理檔案）。

-   SQL Server 必須支援 Windows 驗證。

-   確認 SQL Server 實例與 SQL 代理服務正在執行。

-   以 SQL 系統管理員（sysadmin）的網域帳戶登入，這些腳本將會在該電腦上完成。

腳本會在已登入的使用者網域認證下執行。

**使用 SQL 腳本建立資料庫**

**由 SQL 系統管理員執行的工作：**

1.  將 support\\createdb 資料夾中包含的腳本，從選取的解壓位置根目錄複寫到將執行腳本的電腦。 以下是腳本正常執行所需的檔案，且必須依下列順序進行呼叫。

    -   database .sql

    -   roles. sql

    -   表格 \ _CODES .sql

    -   函數 \ _before \ _tables .sql

    -   tables. sql

    -   函數 .sql

    -   views .sql

    -   程式 sql

    -   trigger. sql

    -   資料 \ _codes .sql

    -   資料 \ _messages .sql

    -   資料 \ _defaults .sql

    -   [警示] \ _jobs

    -   dbversion

2.  視需要查看並修改檔案 `database.sql` 。 預設設定會將 [APPVIRTDB] 命名為 [資料庫]。

    -   如有必要， `APPVIRTDB` 請將使用的範例取代為 `database name` 。

    -   `FILENAME`在腳本中修改要建立資料庫之 SQL Server 的適當路徑的屬性。

3.  如有需要，請 `database name [APPVIRTDB]` 在資料庫 .sql 檔案中使用的檔案中查看和修改 `roles.sql` 。

****

### 如何使用批次處理檔案自動化處理常式的範例

如果使用的話，提供的兩個範例批次檔案會以下列方式執行 SQL 腳本：

1.  **Create\_schema.bat （1）**

    -   database .sql

    -   roles. sql

2.  **Create\_tables.bat （2）**

    -   表格 \ _CODES .sql

    -   函數 \ _before \ _tables .sql

    -   tables. sql

    -   函數 .sql

    -   views .sql

    -   程式 sql

    -   trigger. sql

    -   資料 \ _codes .sql

    -   資料 \ _messages .sql

    -   資料 \ _defaults .sql

    -   [警示] \ _jobs

    -   dbversion

**注意**  
請謹慎考慮修改腳本時必須採取的做法，且只能由具備適當知識的人來完成。 此外，只提供下列範例檔案應該會變更： **create\_schema.bat**、 **create\_tables.bat**、 **.sql**以及**roles .sql**。 所有其他檔案不應以任何方式修改，因為這可能導致資料庫無法正確建立，這會導致安裝 App-v 服務失敗。



兩個範例批次檔案必須放在電腦上複製的其餘 SQL 腳本所在的同一個目錄中。

1.  執行範例**create\_schema.bat**檔案以建立資料庫。 此腳本需要幾秒鐘的時間才能完成，不應該中斷。

    -   從複製檔案的目錄執行 [建立 schema.bat 檔案]。 語法為： "Create\_schema.bat `SQLSERVERNAME` "

        ![AppV46SQLcreatebat](images/appv46sqlcreatebat.bmp)

    -   如果此腳本在建立新的「APPVIRTDB」資料庫時失敗，請視指示查看記錄來修正問題。 您必須刪除由部分執行腳本所建立的資料庫，以確保後續的嘗試將能正常運作。

2.  執行檔案 `create_tables.bat` 以建立資料庫中的資料表。 此腳本需要幾秒鐘的時間才能完成，不應該中斷。

    -   從複製檔案的目錄執行 create\_tables.bat 檔案。 語法為： "create\_tables.bat `SQLSERVERNAME DBNAME` "

        ![app-v 4.6 sql create\-table.bat](images/appv46sqlcreate-tablebat.gif)

        如果在建立資料表期間腳本失敗，請視指示查看記錄來修正問題。 您必須先刪除資料庫並執行 create\_schema.bat，才能嘗試在所有後續嘗試上執行 create\_tables.bat 檔案。

### 在 App-v 資料庫上設定許可權

您必須在 SQL server 上建立下列帳戶，並將特定許可權和角色新增至新資料庫，以進行 App V 環境的安裝、部署及持續管理。

-   在 SQL Server 上建立 app-v 系統管理員群組的登入，並將 [domain\\App-V 系統管理員] 的 APPVIRTDB 資料庫（其中，"domain" 和 "App-v administrator"）新增至 [SFTAdmin] 和 SFTEveryone 資料庫角色。

    ![app-v 4.6 sql 腳本設定許可權和角色](images/appv46sqlscriptsetpermsroles.gif)

-   在全域層級授與此群組「查看任何定義」許可權（這可讓 Microsoft Application Virtualization 管理伺服器設定處理常式驗證管理伺服器登入已存在）。 在 MS-SQL 2005 和更新版本中，已新增對 master 中所含中繼資料的存取限制。 在上一個步驟中建立的使用者，預設不會擁有伺服器安裝所需的許可權。 開啟先前建立的 [登入屬性] 的屬性- &gt; Securables。 針對 [查看任何定義]，新增資料庫實例並啟用「授與」，如下列螢幕擷取畫面所示。

    ![app-v 4.6 sql 腳本授與 perm 以查看任何定義](images/appv46sqlscriptviewanydef.gif)

-   在上一個步驟中建立的登入角色 \ _ASSIGNMENTS 表格中，將角色新增到 [允許 App-v 管理員存取應用程式虛擬化管理主控台]，角色 = "管理員" 和群組 \ _ref = "domain\\App-V 系統管理員" （其中，"domain" 和 "App-v 系統管理員" 將會變更，以反映您自己的環境）。

    ![app-v 4.6 sql 腳本角色指派](images/appv46sqlscriptroleassign.gif)

-   針對管理伺服器建立 SQL Server 和 App-v 資料庫的登入。 這個帳戶是由 Microsoft 應用程式虛擬化管理伺服器用來連線到資料存放區，且負責為流程式應用程式服務用戶端要求。 根據 SQL Server 和管理伺服器的安裝位置，有兩個選項：

    1.  如果管理伺服器與 SQL Server 將要安裝在同一部電腦上，請為 NT AUTHORITY\\NETWORK SERVICE 新增登入，並將其新增至 SFTUser 和 SFTEveryone 資料庫角色。

    2.  如果要在不同的電腦上安裝管理伺服器與 SQL Server，請在 [domain\\App-V Server Name $] （其中，"App-v Server Name" 是安裝 App-v 管理伺服器的伺服器名稱）上新增 [登入]，然後將它新增到 SFTUser 和 SFTEveryone 資料庫角色。

-   開啟 SQL 視窗中的 [查詢] 視窗，然後執行下列 SQL：

    ``` syntax
    USE APPVIRTDB
    GRANT ALTER ON ROLE::SFTuser TO “domain\App-V Admins”
    ```

    在上一個步驟中，APPVIRTDB 是在 SQL Server 上建立的應用程式 V 資料庫的名稱，而要執行 App-v 伺服器安裝的使用者必須是「domain\\App-V 系統管理員」的成員（其中，"domain" 和 "App-v 系統管理員" 將會變更，以反映您自己的環境）。

### 結構管理員要執行的工作

1.  [App-v 管理員] 群組中的系統管理員應該安裝 App-v。

    使用 SQL 系統管理員的資訊來選取在上述步驟中建立的 SQL Server 和資料庫。

2.  [App-v Admins] 群組中的系統管理員會登入應用程式虛擬化管理主控台，然後從管理主控台刪除下列物件。

    **警告**  
    這是必要的，因為傳統的安裝程式會在您針對現有的資料庫執行安裝時，填入資料庫中未填入的特定記錄。 刪除下列物件：

    -   在 [伺服器群組] 下，"預設伺服器群組，" 刪除 [Application Virtualization 管理伺服器]

    -   在 [伺服器群組] 下，刪除 [預設伺服器群組]

    -   [提供者原則] 底下的 [刪除「預設提供者」



3.  然後，應用程式 V 管理員群組中的系統管理員會建立：

    -   在 [提供者原則] 底下，建立新的提供者原則

    -   建立「預設伺服器群組」

        **注意**  
        您必須建立 [預設伺服器] 群組，即使您將不會使用。 伺服器安裝程式在嘗試新增伺服器時，只會尋找「預設伺服器群組」。  如果沒有「預設伺服器群組」，則安裝將會失敗。 如果您打算使用不正確的預設伺服器群組，只要將後續的 App-v 管理伺服器新增到您的基礎結構，就必須保留「預設伺服器群組」。



~~~
-   Assign the App-V Users Group to the New Provider Policy created above

-   Under “Server Groups,” create a New Server Group, specifying the New Provider Policy

-   Under the New Server group, create a New Application Virtualization Management Server

    **Important**  
    Do not restart the service before completing all of the above steps!



-   Administrator restarts the Application Virtualization Management Server service.
~~~

## 總結


總之，本檔中的資訊可讓管理員與 SQL 系統管理員共同作業，以開發適用于組織中安全性與管理部門的部署路徑。 閱讀此檔並測試已記錄的工作之後，系統管理員應該準備好在此類型的環境中實現其 App-v 基礎結構。









