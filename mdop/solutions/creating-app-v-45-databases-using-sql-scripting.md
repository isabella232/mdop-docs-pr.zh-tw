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
ms.openlocfilehash: c119f1d43a70cce04dd6151697318f7cf6a8d1f2
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910588"
---
# <a name="creating-app-v-45-databases-using-sql-scripting"></a>使用 SQL 指令碼建立 APP-V 4.5 資料庫


**神秘此解決方案是否適用于？** 管理 App-V (App-V) 4.5 資料庫的資訊技術專業人員。

**本指南如何説明您？** 此解決方案說明當系統管理員安裝沒有「sysadmin」許可權時，安裝 Microsoft Application 虛擬化伺服器的程式，並SQL Server。

## <a name="overview"></a>概觀


安裝 Microsoft Application Virtualization 4.5 (App-V) 的其中一項挑戰是安裝程式假設安裝伺服器功能的使用者不僅是本地電腦系統管理員，而且擁有 SQL 伺服器上託管資料存放區之 SQL 系統管理員許可權。 此需求是根據資料庫，以及適當的角色和許可權，是建立為安裝一部分。 不過，在大多數企業中，SQL伺服器會與安裝 App-V 的基礎結構小組分開管理。 這些安全性需求會使系統管理員難以SQL安裝 App-V 的基礎結構系統管理員適當許可權;同樣地，SQL系統管理員將沒有安裝基礎結構小組產品所需的許可權。

目前，嘗試安裝 App-V 的系統管理員必須SQL"sysadmin"許可權。 在先前版本的產品中，SQL 系統管理員允許他們建立暫時的「sysadmin」帳戶，或在安裝期間出席，以提供「sysadmin」許可權的認證。 在此版本中，已發行產品提供腳本，供所有系統管理員在執行其基礎結構時使用。

本白皮書討論需要將安裝分成兩個不同的工作的情況：建立 SQL 資料庫，以及安裝 App-V 伺服器功能。 系統管理員SQL可以審查SQL腳本，並進行修改以解決與其他資料庫的任何衝突，或支援與其他工具的整合。 腳本的結果是允許系統管理員SQL資料庫，讓基礎結構系統管理員不需要在 SQL 伺服器上獲得任何進SQL許可權。 在安全性原則會禁止這樣做的環境中，這一點非常重要。

### <a name="sql-database-creation-process"></a>SQL Database建立程式

這些SQL腳本SQL系統管理員建立所需的資料庫，並設定 App-V 系統管理員成功安裝及管理環境的許可權。 本文稍後會列出完成這些工作的步驟。

此程式會將資料庫建立和組組動作與實際的 App-V 安裝區分開。

**提供給系統管理員的資訊SQL管理員**

-   成為 App-V 系統管理員之 AD 群組的名稱

-   安裝 App-V 管理伺服器的伺服器名稱

**要退回給基礎結構系統管理員的資訊**

-   資料庫伺服器或實例的名稱，以及 App-V 資料庫的名稱

資料庫準備好之後，App-V 系統管理員就可以執行 App-V 安裝，SQL許可權。

### <a name="using-the-sql-setup-scripts"></a>使用 SQL腳本

**需求**

以下是使用腳本的需求清單，這些腳本位於所選解壓縮位置根目錄的支援\\createdb 資料夾中。

-   腳本必須複製到執行腳本的電腦上可寫入的位置 (請務必在複製腳本之後，從這些腳本移除唯讀屬性) 而 SQL 用戶端工具必須載入至該電腦 (osql，才能在本地電腦上執行範例批次處理檔案) 。

-   驗證SQL Server必須支援Windows驗證。

-   確保已SQL Server實例SQL代理服務。

-   使用網域帳戶登入，SQL系統管理員 (sysadmin) 將執行腳本的電腦上。

腳本在登入使用者的網域認證下執行。

**使用腳本建立SQL資料庫**

**由系統管理員執行SQL工作：**

1.  將支援\\\createdb 資料夾中所含的腳本從所選解壓縮位置的根目錄複寫到執行腳本的電腦。 腳本必須下列檔案才能正確執行，而且必須以下列順序進行調用。

    -   database.sql

    -   roles.sql

    -   table\_CODES.sql

    -   函數\_before\_tables.sql

    -   tables.sql

    -   函數.sql

    -   views.sql

    -   procedures.sql

    -   triggers.sql

    -   data\_codes.sql

    -   data\_messages.sql

    -   data\_defaults.sql

    -   通知\_jobs.sql

    -   dbversion.sql

2.  如有需要，請閱閱及修改 `database.sql` 檔案。 預設設定會為資料庫命名「APPVIRTDB」。

    -   如有需要，請將 實例 `APPVIRTDB` 取代為 `database name` 將會使用的 。

    -   使用要建立資料庫之資料庫之SQL Server腳本中的屬性 `FILENAME` 。

3.  如有需要，請檢查及修改資料庫中所使用的 `database name [APPVIRTDB]` `roles.sql` 檔案。sql 檔案。

****

### <a name="example-of-how-to-automate-the-process-using-batch-files"></a>如何使用批次處理檔案自動化程式範例

如果使用，提供的兩個範例批次處理檔案會SQL腳本執行下列方式：

1.  **Create\_schema.bat (1) **

    -   database.sql

    -   roles.sql

2.  **Create\_tables.bat (2) **

    -   table\_CODES.sql

    -   函數\_before\_tables.sql

    -   tables.sql

    -   函數.sql

    -   views.sql

    -   procedures.sql

    -   triggers.sql

    -   data\_codes.sql

    -   data\_messages.sql

    -   data\_defaults.sql

    -   通知\_jobs.sql

    -   dbversion.sql

**注意**  
修改腳本時必須謹慎考慮，而且必須由具備適當知識的人執行。 此外，只應變更下列範例檔案：create\_schema.bat、create\_tables.bat、database.sql**和** **roles.sql**。 **** **** 不應以任何方式修改所有其他檔案，因為這可能導致資料庫建立不正確，導致 App-V 服務的安裝失敗。



這兩個範例批次檔案必須放在同一個目錄中，SQL腳本複製到電腦上。

1.  執行 ** 範例create\_schema.bat** 建立資料庫。 此腳本需要幾秒鐘才能完成，而且不應中斷。

    -   從複製schema.bat目錄執行建立檔案。 語法為 `SQLSERVERNAME` ：「Create\_schema.bat」

        ![AppV46SQLcreatebat。](images/appv46sqlcreatebat.bmp)

    -   如果此腳本在建立新 "APPVIRTDB" 資料庫期間失敗，請檢查記錄，如指示以修正問題。 必須刪除部分執行腳本所建立的資料庫，以確保後續的嘗試能夠正常運作。

2.  執行 `create_tables.bat` 檔案以在資料庫中建立資料表。 此腳本需要幾秒鐘才能完成，而且不應中斷。

    -   從create\_tables.bat目錄執行該檔案。 語法為 `SQLSERVERNAME DBNAME` ：「create\_tables.bat」

        ![app-v 4.6 sql create\-table.bat。](images/appv46sqlcreate-tablebat.gif)

        如果腳本在建立資料表期間失敗，請檢查所指示的記錄以修正問題。 在嘗試執行所有後續嘗試時，create\_schema.bat刪除資料庫並執行create\_tables.bat檔案。

### <a name="setting-permissions-on-the-app-v-database"></a>在 App-V 資料庫上設定許可權

下列帳戶必須建立于 SQL 伺服器上，並擁有新資料庫的特定許可權和角色，才能安裝、部署及持續管理 App-V 環境。

-   為 SQL Server 上的 App-V 系統管理員群組和 APPVIRTDB 資料庫建立登入，以「網域\\App-V 系統管理員」 (其中「網域」和「App-V 系統管理員」會變更以反映您自己的環境) ，並新增到 SFTAdmin 和 SFTEveryone 資料庫角色。

    ![app-v 4.6 sql 腳本集許可權和角色。](images/appv46sqlscriptsetpermsroles.gif)

-   在全域層級授予此群組的 「VIEW ANY DEFINITION」許可權 (這可讓 Microsoft Application 虛擬化管理伺服器設定程式驗證管理伺服器登入已存在) 。 在 MS-SQL 2005 及以上，已新增 master.db 中所含中繼資料的存取限制。 根據預設，在上一個步驟中建立的使用者不會擁有伺服器安裝所需的許可權。 開啟先前建立登入的登入屬性，登入屬性- &gt; 安全保護。 新增資料庫實例，並針對 「查看任何定義」啟用 「GRANT」，如以下螢幕擷取畫面所示。

    ![app-v 4.6 sql 腳本授權 perm 以用於查看任何 def。](images/appv46sqlscriptviewanydef.gif)

-   新增角色至 ROLE\_ASSIGNMENTS 資料表，以允許 App-V 系統管理員存取應用程式虛擬化管理主控台，角色 = "ADMIN" 和 group\_ref = "domain\\App-V 系統管理員" (其中會變更「網域」和「App-V 系統管理員」以反映您自己的環境) 。

    ![app-v 4.6 sql 腳本角色指派。](images/appv46sqlscriptroleassign.gif)

-   為管理伺服器SQL Server應用程式與 V 資料庫建立登入。 Microsoft Application 虛擬化管理伺服器會使用這個帳戶來連接到資料存放區，並負責維護串流應用程式的用戶端要求。 根據安裝伺服器和管理伺服器SQL Server兩個選項：

    1.  如果管理伺服器SQL Server安裝在同一部電腦上，請新增 NT AUTHORITY\\NETWORK Service 的登入，並新增到 SFTUser 和 SFTEveryone 資料庫角色。

    2.  如果要在不同電腦上安裝管理伺服器和 SQL Server，請新增 「domain\\App-V Server Name$" (的登入，其中「App-V 伺服器名稱」是安裝 App-V 管理伺服器) 的伺服器名稱，並新增到 SFTUser 和 SFTEveryone 資料庫角色。

-   開啟查詢視窗上的SQL，然後執行下列SQL：

    ``` syntax
    USE APPVIRTDB
    GRANT ALTER ON ROLE::SFTuser TO “domain\App-V Admins”
    ```

    其中 APPVIRTDB 是上一個步驟中 SQL Server 上所建立之 App-V 資料庫的名稱，而要安裝 App-v 伺服器的使用者必須是「網域\\App-V 系統管理員」的成員 (其中「網域」和「App-V 系統管理員」將會變更以反映您自己的環境) 。

### <a name="tasks-to-be-performed-by-the-infrastructure-administrators"></a>基礎結構系統管理員要執行的工作

1.  「App-V 系統管理員」群組中的系統管理員應安裝 App-V。

    使用系統管理員SQL的資訊，選取SQL Server步驟中建立的資料庫和資料庫。

2.  「App-V 系統管理員」群組中的系統管理員會登錄至應用程式虛擬化管理主控台，然後從管理主控台刪除下列物件。

    **警告**  
    這是必要的，因為傳統設定會填入資料庫中未填入的某些記錄，如果您針對現有的資料庫執行安裝。 刪除下列物件：

    -   在 「伺服器群組」、「預設伺服器群組」下，刪除「應用程式虛擬化管理伺服器」

    -   在 「伺服器群組」下，刪除「預設伺服器群組」

    -   在 「提供者政策」下，刪除「預設提供者」



3.  然後，App-V 系統管理員群組中的系統管理員應建立：

    -   在 「提供者政策」下，建立新提供者政策

    -   建立 「預設伺服器群組」

        **注意**  
        即使您不會使用，您也必須建立「預設伺服器」群組。 伺服器安裝程式只會在嘗試新增伺服器時尋找「預設伺服器群組」。  如果沒有「預設伺服器群組」，安裝將會失敗。 如果您打算使用預設為正常的伺服器群組，如果您打算新增後續的 App-V 管理伺服器至您的基礎結構，則只需要保留 「預設伺服器群組」。



~~~
-   Assign the App-V Users Group to the New Provider Policy created above

-   Under “Server Groups,” create a New Server Group, specifying the New Provider Policy

-   Under the New Server group, create a New Application Virtualization Management Server

    **Important**  
    Do not restart the service before completing all of the above steps!



-   Administrator restarts the Application Virtualization Management Server service.
~~~

## <a name="conclusion"></a>總結


最後，本檔的資訊可讓系統管理員與 SQL 管理員合作，開發適用于組織安全性與系統管理部門之部署路徑。 在閱讀這份檔並測試記錄的工作之後，系統管理員應該可以準備在這類環境中執行其 App-V 基礎結構。









