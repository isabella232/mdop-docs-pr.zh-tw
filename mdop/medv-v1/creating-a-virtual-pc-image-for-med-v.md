---
title: 建立 MED-V 的虛擬電腦映像
description: 建立 MED-V 的虛擬電腦映像
author: dansimp
ms.assetid: 5e02ea07-25b9-41a5-a803-d70c55eef586
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 84e45f9ff7213abdd6288bcd750238436d3ab68c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810089"
---
# 建立 MED-V 的虛擬電腦映像


若要建立 MED-V 的虛擬電腦（VPC）影像，您必須執行下列動作：

1.  [建立 VPC 影像](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)。

2.  [在 VPC 影像上安裝 med-v （msi）工作區。](#bkmk-howtoinstallthemedvworkspacemsipackage)

3.  [在 VPC 影像上執行 med-v 虛擬機器必備工具](#bkmk-howtorunthevirtualmachineprerequisitestool)。

4.  [在 VPC 影像上手動設定虛擬機器必備元件](#bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites)。

5.  [針對 med-v 影像設定 Sysprep](#bkmk-howtoconfiguresysprepformedvimages) （選用）。

6.  [關閉 Microsoft VIRTUAL PC](#bkmk-turningoffmicrosoftvirtualpc)。

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a>使用 Microsoft Virtual PC 建立虛擬電腦影像


若要使用 Microsoft 虛擬電腦建立虛擬電腦影像，請參閱虛擬電腦的檔。

如需詳細資訊，請參閱下列各項：

-   [Windows 虛擬電腦說明](https://go.microsoft.com/fwlink/?LinkId=182378)

-   [建立虛擬機器並安裝客體作業系統](https://go.microsoft.com/fwlink/?LinkId=182379)

## <a href="" id="bkmk-howtoinstallthemedvworkspacemsipackage"></a>如何安裝 MED-V 工作區 .msi 套件


建立虛擬電腦影像之後，請在影像上安裝 MED-V 工作區。

**若要安裝 MED-V 工作區圖像**

1.  啟動虛擬機器，然後將 MED-V 中的 .msi 套件複製到其中。

    會呼叫 MED-V 工作區， *MED-V\_workspace\_x.msi*，其中*x*是版本號碼。

    例如， *MED-V\_workspace\_1.0.65.msi*。

2.  按兩下 [MED-V] 工作區 .msi 套件，然後依照安裝精靈指示進行。

    **注意**  
    當您釋放新的 MED-V 版本，且已更新現有的虛擬電腦影像時，請卸載現有的 MED-V 工作區。 msi 套件，重新開機電腦，然後安裝新的 MED-V 工作區 .msi 套件。



~~~
**Note**  
After the MED-V workspace .msi package is installed, other products that replace GINA cannot be installed.
~~~



## <a href="" id="bkmk-howtorunthevirtualmachineprerequisitestool"></a>如何執行虛擬機器必備元件工具


虛擬機器（VM）先決條件工具是一個可自動執行幾個必備元件的嚮導。

**注意**  
雖然在嚮導中有許多參數可設定，但 MED-V 的正常運作所需的屬性無法進行設定。



**執行虛擬機器必備元件工具**

1.  安裝 MED-V 工作區後，請在 Windows [**開始**] 功能表上，選取 [**所有程式] &gt; med-v &gt; VM 必備工具**。

    **注意**  
    執行虛擬機器必備工具的使用者必須擁有本機系統管理員許可權，而且必須是唯一登入的使用者。



~~~
The **MED-V VM Prerequisite Wizard Welcome** page appears.
~~~

2. 按 **\[下一步\]**。

3. 在 [ **Windows 設定**] 頁面上，從下列可設定的屬性選取要設定的屬性：

   -   **清除使用者的個人歷程記錄資訊**

   -   **清除本機設定檔臨時目錄**

   -   **在下列 Windows 事件上停用聲音：啟動、登入、登出**

   **注意**  
   請勿在群組原則中啟用 Windows 頁面保護程式。



4. 按 **\[下一步\]**。

5. 在**Internet Explorer [設定**] 頁面上，從下列可設定的屬性選取要設定的屬性：

   -   **不要使用自動完成功能**

   -   **停用啟動快速鍵的 windows**

   -   **清除瀏覽歷程記錄**

   -   **在 Internet Explorer 7 中啟用分頁流覽**

6. 按 **\[下一步\]**。

7. 在 [ **Windows 服務**] 頁面上，從下列可設定的屬性選取要設定的屬性：

   -   **安全性中心服務**

   -   **任務計畫程式服務**

   -   **自動更新服務**

   -   **系統還原服務**

   -   **索引服務**

   -   **無線零設定**

   -   **快速使用者切換相容性**

8. 按 **\[下一步\]**。

9. 在 [ **Windows 自動登**入] 頁面上，執行下列動作：

   1.  選取 [**啟用 Windows 自動登**入] 核取方塊。

   2.  指派**使用者名稱**和**密碼**。

10. 按一下 **[** 套用]，然後在出現的確認方塊中，按一下 [**是]**。

11. 在 [**摘要**] 頁面上，按一下 **[完成] 結束**嚮導

**注意**  
確認 [群組原則] 不會覆寫 [先決條件工具] 中設定的強制設定。



## <a href="" id="bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites"></a>如何設定 MED-V Virtual 電腦手動安裝先決條件


無法透過虛擬機器必備工具來設定數種設定，必須手動執行。

-   虛擬機器設定

    建議您在 Microsoft Virtual PC 主控台中設定下列虛擬機器設定：

    -   停用軟碟磁片磁碟機。

    -   停用復原-磁片（**設定 &gt; 復原磁片**）。

    -   確定影像只有一個虛擬 CPU。

    -   消除虛擬機器與使用者之間的互動，與已發佈的應用程式無關（例如需要使用者輸入的訊息）。

-   影像設定

    在影像內設定下列手動設定：

    1.  在 [**電源選項屬性**] 視窗中，停用 [休眠] 和 [睡眠]。

    2.  套用最新的 Windows 更新。

    3.  在 [ **Windows 啟動及損毀修復**] 對話方塊的 [**系統失敗**] 區段中，清除 [**自動重新開機**] 核取方塊。

    4.  確定影像使用 VLK 授權金鑰。

-   安裝 VPC 新增功能

    在 [**動作**] 功能表上，選取 [**安裝或更新虛擬機器新增**]。

-   設定列印

    您可以透過下列其中一種方式，從 MED-V 工作區設定列印：

    -   新增印表機至虛擬機器。

    -   允許使用主機電腦上設定的印表機進行列印。

## <a href="" id="bkmk-howtoconfiguresysprepformedvimages"></a>如何針對 MED-V 影像設定 Sysprep


在 MED-V 工作區中，您可以設定 Sysprep 來指派唯一的安全識別碼（SID），特別是在一部電腦上執行多個 MED-V 工作區時。 建議您不要使用 Sysprep 來加入網域。請改為使用 MED-V join 網域腳本指令，如[如何設定腳本動作](how-to-set-up-script-actions.md)中所述。

**注意**  
Sysprep 是適用于 Windows 作業系統的 Microsoft 系統準備實用程式。



**在 MED-V 工作區中設定 Sysprep**

1.  在名為*Sysprep*的系統磁碟機根目錄中建立目錄。

2.  從 Windows 安裝 CD 中，將*deploy.cab*解壓至系統磁片磁碟機的根目錄，或從 Microsoft 網站下載最新的部署工具更新。

    -   針對 Windows 2000，請參閱適用[于 windows 2000 的部署工具更新](https://go.microsoft.com/fwlink/?LinkId=143001)。

    -   若是 Windows XP，請參閱適用[于 WINDOWS xp 的部署工具更新](https://go.microsoft.com/fwlink/?LinkId=143000)。

3.  執行**安裝管理員**（setupmgr.exe）。

4.  遵循 [安裝管理員] 嚮導。

在已設定 Sysprep 且已建立 MED-V 工作區之後，必須執行 Sysprep。

**若要執行 Sysprep**

1.  從位於系統磁碟機根目錄的 Sysprep 資料夾中，執行系統準備工具（Sysprep.exe）。

2.  在出現的 [警告訊息] 方塊中，按一下 **[確定]**。

3.  在 [ **Sysprep 屬性**] 對話方塊中，選取 [**不要重設啟用的寬限期**]，然後**使用 [最小化設定**] 核取方塊。

4.  按一下 [重新**封裝**]。

5.  如果您對 [確認訊息] 方塊中所列的資訊不滿意，請按一下 [**取消**] 並變更選取專案。

6.  按一下 **[確定]** 以完成系統準備程式。

## <a href="" id="bkmk-turningoffmicrosoftvirtualpc"></a>關閉 Microsoft Virtual PC


安裝並設定所有元件之後，請關閉 Microsoft Virtual PC，然後選取 [**關閉**]。

## 相關主題


建立 MED-V 影像[如何設定腳本動作](how-to-set-up-script-actions.md)









