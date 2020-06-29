---
title: 建立 MED-V 工作區套件
description: 建立 MED-V 工作區套件
author: dansimp
ms.assetid: 3f75fe73-41ac-4389-ae21-5efb2d437f4d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e20cf4cc9394c4a5e90178fff4fc36ed83c12d60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809849"
---
# 建立 MED-V 工作區套件


MED-V 工作區是 Windows XP 桌上型電腦環境，使用者可以在其中與 MED-V 提供的虛擬機器進行互動。 系統管理員會建立和自訂 MED-V 工作區。 工作區由一個影像以及定義 MED-V 工作區之規則與功能的群組原則所組成。

您可以建立多個 MED-V 工作區，每個都有自訂的配置、設定及規則。 使用者、群組或多個使用者或群組可以與每個 MED-V 工作區建立關聯。 自訂專案會使 MED-V 工作區只可供該使用者或群組使用。

使用**Med-v 工作區包裝**程式來建立 med-v 工作區。 **Med-v 工作區包裝**程式分為兩個主要區段：

-   主要面板包含三個按鈕，您可以用來建立和管理 MED-V 工作區。 [**建立 Med-v 工作區套件**] 按鈕會開啟您用來建立 med-v 工作區的 [**建立 Med-v-v 工作區套件] 嚮導**。

-   視窗右側的 [**説明中心**]，提供資訊與指導方針，以協助您建立、測試及管理您的 med-v 工作區。

**重要**  
在您可以使用**Med-v 工作區包裝程式**之前，您必須先確定 Windows PowerShell 執行原則設定為 [無限制]。

`Set-ExecutionPolicy Unrestricted`

此外，在執行**Med-v 工作區包裝**程式的電腦上，必須將其 SAN 原則設定為 [全部線上]。 若要檢查 SAN 原則的設定，請在命令提示字元中使用管理認證執行下列命令：

`diskpart.exe`

`DISKPART> san`

`DISKPART> exit`

如有需要，請在命令提示字元中輸入下列命令，以管理認證，將 SAN 原則變更為 [全部線上]：

`diskpart.exe`

`DISKPART> san policy=onlineall`

`DISKPART> exit`



**重要**  
如果您所用的電腦上安裝了自動磁片加密軟體，且已建立 MED-V 工作區套件，您必須先停用本軟體，然後才能開始進行。 否則，您無法在任何其他電腦上使用 MED-V 工作區。



我們在這裡提供的資訊可協助您建立 MED-V 工作區部署套件。

## <a href="" id="bkmk-prereq"></a>必要條件


開始建立您的 MED-V 工作區部署套件之前，請確認您有下列專案的存取權：

-   **已準備好的 Windows XP 映射**

    如需如何建立 Windows XP 映射以搭配 MED-V 使用的詳細資訊，請參閱[準備 Med-v 影像](prepare-a-med-v-image.md)。

-   **包含 URL 重新導向資訊的文字檔或清單**

    您的 URL 重新導向文字檔或清單包含您要從主機電腦重新導向到 MED-V 工作區中的 [Internet Explorer] 的 Url。 當您使用打包嚮導建立 MED-V 工作區時，您可以匯入、輸入或複製並貼上此重新導向資訊做為套件建立程式中的其中一個步驟。

    **注意**  
    MED-V 中的 URL 重新導向只支援 HTTP 和 HTTPS 協定。 MED-V 不提供 FTP 或任何其他協定的支援。



~~~
Enter each web address on a single line, for example:

http://www.contoso.com/webapps/webapp1

http://www.contoso.com/webapps/webapp2

http://\*.contoso.com

http://www.contoso.com/webapps/\*

**Important**  
If you import a text file that includes a URL that uses special characters (such as ~ ! @ \# and so on), make sure that you specify UTF-8 encoding when you save the text file. Special characters do not import correctly into the MED-V Workspace Packager if the text file was saved using the default ANSI encoding.
~~~



## 針對 MED-V 工作區包裝電腦語言以外的語言封裝 MED-V-V 工作區


根據預設，MED-V 工作區支援電腦語言和英文的字元。 若要為電腦上安裝的其他語言建立 MED-V 工作區，請在位於 MED-V 工作區名稱後的 PowerShell 腳本（. ps1）中，指定**loc \ [locale \]** 。

若要在 MED-V 工作區包裝電腦的預設語言以外的語言中建立 MED-V 工作區套件，請執行 MED-V 工作區包裝程式，然後根據您的地區設定所需的方式來修改輸出腳本，以預設語言產生腳本。 此腳本位於在封裝期間指定的 MED-V 工作區輸出目錄中。 地區設定的名稱位於中。WXL 下列目錄中的檔案：

C:\\program files Files\\Microsoft Enterprise Desktop Virtualization\\WindowsPowerShell\\Modules\\Microsoft.Medv.Administration.Commands.WorkspacePackager\\locale

## 建立 MED-V 工作區套件


若要建立 MED-V 工作區套件，請遵循下列步驟：

****

1.  若要開啟**Med-v 工作區包裝**程式，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 企業版桌面虛擬化**]，然後按一下 [ **med-v 工作區包裝程式**]。

2.  在**Med-v 工作區包裝**程式主版面板上，按一下 [**建立 Med-v-v 工作區套件**]。

    隨即會出現 MED-V [**建立 med-v-v 工作區套件] 嚮導**。 此嚮導包含下列頁面：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>封裝資訊</strong></p></td>
    <td align="left"><p>指定 MED-V 工作區的名稱，然後選取一個儲存 MED-V 工作區套件檔案的資料夾。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>選取 [Windows XP 影像]</strong></p></td>
    <td align="left"><p>指定您準備好的 Windows XP 虛擬電腦影像。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>第一次設定</strong></p></td>
    <td align="left"><p>指定第一次設定過程中的 MED-V 所遵循的安裝程式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>MED-V 訊息</strong></p></td>
    <td align="left"><p>針對最終使用者第一次設定時所看到的說明資訊，指定郵件和選擇性 URL。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>命名電腦</strong></p></td>
    <td align="left"><p>指定 MED-V 虛擬機器的命名方式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>從主機複製設定</strong></p></td>
    <td align="left"><p>指定如何定義 MED-V 工作區的設定。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>啟動和網路</strong></p></td>
    <td align="left"><p>指定啟動 MED-V 工作區、網路和使用者認證的設定。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>Web 重新導向</strong></p></td>
    <td align="left"><p>指定要在 MED-V 工作區中重新導向至 Internet Explorer 的文字檔或 Url 清單。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>摘要</strong></p></td>
    <td align="left"><p>驗證 MED-V 工作區設定，並開始建立您的 MED-V 工作區部署套件。</p></td>
    </tr>
    </tbody>
    </table>



3.  在 [**套件資訊**] 頁面上，輸入 med-v 工作區的名稱，然後選取一個儲存 med-v 工作區套件檔案的資料夾。

    **警告**  
    您必須命名 MED-V 工作區，然後指定要繼續的資料夾。



~~~
After you have finished, click **Next**.
~~~

4. 在 [**選取 WINDOWS XP 映射**] 頁面上，指定準備的 MED-V Windows XP 虛擬電腦映射（.vhd 檔案）的位置。

   **警告**  
   您必須指定 Windows XP VHD 映射才能繼續。



~~~
After you have finished, click **Next**.
~~~

5. 在 [**第一次設定**] 頁面上，選取您是否要在值守或無人值守時執行第一次安裝，以及是否要讓共用電腦上的所有使用者都能使用 med-v 工作區。

   如果您選取**無人參與的安裝程式，且沒有任何通知**，就不會在第一次執行安裝程式之前通知使用者，且在第一次設定期間不會向最終使用者顯示該虛擬機器。 此外，嚮導的 [ **med-v-V 訊息**] 頁面是隱藏的，因為第一次安裝程式在完全無人模式下執行時，不需要任何訊息。

   如果您選取 [**無操作安裝]，但在第一次安裝開始之前通知使用者**，則會在第一次執行安裝程式之前通知使用者。 不過，在第一次設定期間，不會向最終使用者顯示虛擬機器。

   如果使用者在第一次設定時必須輸入資訊，請選取 [**有人參與設定**]。

   預設行為是**無人參與的設定，但在第一次安裝開始前通知最終使用者**。

   **警告**  
   如果您建立了 Sysprep.inf 檔案，讓迷你安裝程式需要使用者輸入才能完成，您必須選取 [**有人參與設定**] 或 [初次設定時可能會出現問題]。



~~~
You can also specify how a MED-V workspace is used on computers that are shared by multiple end users. You can decide that you want to create a unique MED-V workspace for each end user or that you want the MED-V workspace made available to all end users who share the computer. The default is that the MED-V workspace is unique for each end user.

**Important**  
We recommend that you disable the fast user switching feature in Windows if you configure the MED-V workspace to be accessed by all users on a shared computer. Problems can occur if an end user logs on by using the fast user switching feature in Windows when another user is still logged on.



**Tip**  
When you create a name mask for the MED-V workspace on the **Naming Computers** page, make sure that each virtual machine on a shared computer has a unique computer name.



You can also specify whether the MED-V workspace is added to the Administrators group or administrator credentials are managed outside MED-V. By default, the MED-V workspace is not automatically added to the Administrators group.

After you have finished, click **Next**.
~~~

6. 在**Med-v 郵件**頁面上，指定最終使用者在第一次設定時所看到的下列訊息：

   -   使用者第一次啟動時所看到的訊息。

   -   當您第一次設定失敗或發生錯誤時，最終使用者會看到的訊息。

   **注意**  
   如果您選取了 [**無人參與設定]，** 則會隱藏嚮導的 [ **Med-v-V 訊息**] 頁面，而不會在**第一次設定**頁面上顯示任何通知。



~~~
You can also specify an optional URL location for help information that is provided to the end user when first time setup is running.

For example, the URL can point to an internal IT webpage with answers to questions such as "How long will this take and how will I know when it has completed?" or "What do you do if you get an error message?"

**Note**  
If you specify a URL, a link is shown during first time setup that points the end user to this help information. If you do not specify a URL, no link is provided.



After you have finished, click **Next**.
~~~

7. 在 [**命名電腦**] 頁面上，您可以指定是由 med-v 或系統管理工具（例如 Sysprep）來管理電腦命名。 預設值是由系統管理工具管理電腦命名。

   如果您指定電腦命名是由 MED-V 管理，請從下拉式清單中選取預先定義的電腦命名慣例（遮罩）。 範例電腦名稱稱的預覽會根據您用來建立 MED-V-V 工作區套件的電腦而定。

   如果您選取其中一個自訂命名慣例，您可以指定的欄位僅限於下列字元：

   -   [首碼] 和 [尾碼] 欄位僅限於字元 A-z、a-z、0-9 及特殊字元！ @ \ # $% ^ & （）-\ _ ' {}。 和 ~。

   -   [主機名稱] 和 [使用者名稱] 欄位的位數限制為0到9。

   **重要**  
   電腦名稱稱必須是唯一的，而且最多隻能有15個字元。 當您決定您的電腦命名方法時，請考慮擁有多部電腦或共用電腦的使用者，並避免使用電腦名稱稱遮罩，在網路上造成衝突。



~~~
**Caution**  
The computer name settings that you specify on this page override those specified in the Sysprep.inf answer file.



After you have finished, click **Next**.
~~~

8. 在 [**從主機複製設定**] 頁面上，您可以選取下列設定來指定 med-v 工作區的設定方式：

   **警告**  
   您在此頁面上指定的將從主機電腦複製到 MED-V 工作區的設定會覆寫在 Sysprep.inf 答案檔案中指定的設定。



~~~
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Copy regional settings</strong></p></td>
<td align="left"><p>Select this check box to copy the regional settings from the host computer to the MED-V workspace.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>If you select this check box, the following settings are set in the Sysprep.inf file:</p>
<pre class="syntax" space="preserve"><code>[RegionalSettings]
Language
SystemLocale
UserLocale
UserLocale_DefaultUser
InputLocale
InputLocale_DefaultUser
</code></pre></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy user settings</strong></p></td>
<td align="left"><p>Select this check box to copy certain user settings, such as user name and company name, from the host to the MED-V workspace.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>If you select this check box, the following settings are set in the Sysprep.inf file:</p>
<pre class="syntax" space="preserve"><code>[UserData]
OrgName
FullName</code></pre>
<div class="alert">
<strong>Note</strong>  
<p>Personal settings, such as Internet browsing history, are not copied over to the MED-V workspace.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy domain name</strong></p></td>
<td align="left"><p>Select this check box to let the guest join the same domain as the host.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><div class="alert">
<strong>Important</strong>  
<p>The MED-V guest must be configured to join a domain that lets users log on by using the credentials that they use to log on to the MED-V host.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy domain organizational unit</strong></p></td>
<td align="left"><p>Select this check box to copy the domain organizational unit from the host computer to the MED-V workspace. This check box is only enabled if you select to copy the domain name from the host computer.</p></td>
</tr>
</tbody>
</table>



After you have finished, click **Next**.
~~~

9. 在 [**啟動和網路**] 頁面上，您可以變更下列設定的預設行為：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>開始 MED-V-V 工作區</strong></p></td>
   <td align="left"><p>選擇是否要在使用者登入時、第一次使用時啟動 MED-V 工作區，或是讓最終使用者決定 MED-V 工作區何時開始。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>MED-V 工作區會以下列其中一種方式開始：當使用者登入，或者當他們第一次啟動需要 MED-V 的動作（例如開啟已發佈的應用程式，或輸入需要重新導向的 URL）時，請使用這兩種方法。</p>
   <p>您可以為最終使用者定義此設定，或讓使用者控制 MED-V 的啟動方式。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>如果您指定最終使用者決定，其體驗的預設行為就是 MED-V 工作區在登入時就會啟動。 您可以在通知區域中，以滑鼠右鍵按一下 MED-V 圖示，然後選取 [Med-v 使用者設定] 來變更預設值 <strong> </strong> 。 如果您為最終使用者定義此設定，就無法變更 MED-V 的啟動方式。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>網路</strong></p></td>
   <td align="left"><p><strong> </strong> <strong> </strong> 針對您的網路設定選取 [共用] 或 [橋接]。 預設值為 [ <strong> 共用] </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><strong>已共用 </strong> - med-v 工作區使用網路位址轉譯（NAT）來共用主機&#39;s IP 以進行外寄通訊。</p>
   <p><strong>已橋接 </strong> - med-v 工作區有自己的網路位址，通常是透過 DHCP 取得的。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>儲存身分認證</strong></p></td>
   <td align="left"><p>選擇是否要儲存使用者認證。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>預設行為是已停用認證儲存，因此使用者必須在每次登入時對其進行驗證。</p>
   <div class="alert">
   <strong>重要</strong><br/><p>雖然快取使用者的認證會提供最佳的使用者體驗，但是您應該知道所涉及的風險。</p>
   <p>在 Windows 認證管理員中，使用者的網域認證會以可逆的格式儲存。 因此，攻擊者可以撰寫可檢索密碼的程式，並取得使用者認證的存取權。 您只需要停用終端使用者認證，就能降低此風險。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



~~~
After you have finished, click **Next**.
~~~

10. 在 [ **Web**重新導向] 頁面上，您可以在 med-v 工作區中輸入、貼上或匯入已重新導向至 Internet Explorer 的 url 清單。 如需如何設定 URL 重新導向資訊的詳細資訊，請參閱[先決條件](#bkmk-prereq)。

   您也可以指定如何為使用者設定 MED-V 工作區中的 Internet Explorer。 根據預設，網際網路區域安全層級會設定為 [高]。 此外，某些預設的流覽功能（例如位址列）會被移除。 在 MED-V 工作區中，這是 Internet Explorer 的預設設定，可為使用者提供更安全的流覽環境。

   **警告**  
   透過變更預設設定，您可以在 MED-V 工作區中自訂 Internet Explorer。 不過，請注意，如果您變更預設設定，以使其安全性較低，您就可以將貴組織暴露在舊版 Internet Explorer 中的安全性風險。 如需詳細資訊，請參閱[Med-v 運算的安全性最佳作法](security-best-practices-for-med-v-operations.md)。



~~~
After you have finished, click **Next**.
~~~

11. 您可以在 [**摘要**] 頁面上查看此 med-v 工作區的封裝設定。 如果您想要變更任何設定，請按一下 [**上一個**] 按鈕，返回相關的頁面。 完成查看設定之後，按一下 [**建立**]。

   隨即會開啟 [**建立 Med-v 工作區套件] 嚮導**的**完成**頁面，以顯示套件建立的進度。

   **注意**  
   MED-V 工作區套件建立程式可能需要幾分鐘的時間才能完成，視指定的 VHD 大小而定。



~~~
If the MED-V workspace package is created successfully, the **Completion** page displays a list of the files that you created and their respective locations. The following is a list of the files that are created and their descriptions:

-   **setup.exe**—an installation program that you deploy and run on end-user computers to install the MED-V workspaces.

-   **&lt;*workspace\_name*&gt;.msi**—an installer file that you deploy to the end-user computers. The setup.exe file will run this file to install the MED-V workspaces.

-   **&lt;*vhd\_name*&gt;.medv**—a compressed VHD file that you deploy to the end-user computers. The setup.exe file uses it when it installs the MED-V workspaces.

-   **&lt;*workspace\_name*&gt;.reg**—the configuration settings that are installed when the setup.exe, &lt;*workspace\_name*&gt;.msi, and &lt;*vhd\_name*&gt;.medv files are deployed and setup.exe is run.

-   **&lt;*workspace\_name*&gt;.ps1**—a Windows PowerShell script that you can use to rebuild the registry file and re-build the MED-V workspace package.

    **Important**  
    Before deployment, you can edit configuration settings by updating the .ps1 file that has your preferred method of script editing, such as Windows PowerShell. After you change the .ps1 file, use that file to rebuild the MED-V workspace package that you deploy to your enterprise. For more information, see [Configuring Advanced Settings by Using Windows PowerShell](configuring-advanced-settings-by-using-windows-powershell.md).

    However, after the MED-V workspace is deployed, you must edit configuration settings through the registry. For a list and description of the configuration settings, see [Managing MED-V Workspace Configuration Settings](managing-med-v-workspace-configuration-settings.md).
~~~



12. 按一下 [**關閉**] 以關閉打包嚮導並返回**Med-v 工作區包裝**程式。

您的 MED-V 工作區套件現已準備好在部署前進行測試。

## 相關主題


[使用 Windows PowerShell 設定進階設定](configuring-advanced-settings-by-using-windows-powershell.md)

[測試 MED-V 工作區套件](testing-the-med-v-workspace-package.md)

[準備 MED-V 映像](prepare-a-med-v-image.md)









