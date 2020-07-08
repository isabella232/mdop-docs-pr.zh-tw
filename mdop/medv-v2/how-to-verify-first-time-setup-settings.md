---
title: 如何驗證第一次安裝設定
description: 如何驗證第一次安裝設定
author: dansimp
ms.assetid: e8a07d4c-5786-4455-ac43-2deac4042efd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d859d627ec90fbc26d18019062d5e316f907cec6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800240"
---
# 如何驗證第一次安裝設定


在您第一次安裝測試開始或完成之後，您可以執行下列工作，以驗證您在 MED-V 工作區中所設定的設定。

**記事** 如需有關如何在部署後監視整個企業中第一次設定成功完成的相關資訊，請參閱[監視 Med-v 工作區部署](monitoring-med-v-workspace-deployments.md)。

 

**在第一次設定期間驗證設定**

1.  第一次執行安裝程式時，請確認下列事項：

    如果您指定的是**無人參與**模式，請確認第一次執行安裝程式時不會顯示虛擬機器。

    如果您指定的是「有人值守」模式，請確認虛擬機器出現，而且會顯示所有需要使用者輸入的欄位。

2.  您也可以在第一次安裝程式執行時，透過查看虛擬機器來監視完整的第一次設定處理常式。 若要這樣做，請執行下列步驟：

    1.  開啟 Windows 虛擬電腦主控台。

        按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，然後按一下 [ **windows 虛擬電腦**]。

    2.  如果沒有執行，請啟動 MED-V-V。

        如果您在虛擬機器清單中顯示已部署 MED-V 工作區的名稱，則不會在短期內出現。

    3.  按兩下 MED-V 虛擬機器將它開啟。

        在進行設定時，您可以觀察 MED-V 虛擬機器，而且您可以針對最小化安裝程式進行疑難排解。 在其他螢幕上驗證資訊，例如設定網路設定、電腦網域加入資訊、設定來賓代理程式、設定個人設定及關閉。

    4.  在第一次設定完成時，虛擬機器會自動關閉。

        **記事** 您可以隨時關閉虛擬機器視窗，並在第一次設定繼續時關閉。

         

**在第一次設定完成後驗證設定**

1.  確定第一次安裝成功完成。

2.  確認 MED-V 工作區已正確設定。

    1.  開啟 Windows 虛擬電腦主控台。

        按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，然後按一下 [ **windows 虛擬電腦**]。

    2.  按兩下已安裝的 MED-V 工作區。

        如果 MED-V 工作區已執行虛擬應用程式，系統可能會提示您關閉應用程式，然後才能開啟虛擬機器。

    3.  在 MED-V 工作區中，以滑鼠右鍵按一下 [**我的電腦**]，然後按一下 [**屬性**]。

    4.  確認 MED-V 工作區已加入正確的網域。 如果適用于您的組織，請指定兩個不同的網域來測試網域加入，以確認由主機網域覆寫來賓網域。

    5.  確認 MED-V 工作區已加入您指定的網域組織單位。

    6.  如果您已指定電腦名稱稱遮罩，請確認新電腦名稱稱符合指定的名稱。

3.  確認您指定的地區設定正確無誤。

    1.  在 MED-V 工作區中，按一下 [**開始**]，然後按一下 [**控制台**]。

    2.  驗證您指定的設定，例如**日期和時間**，以及**地區及語言**。

**記事** 如果您在驗證第一次設定設定時遇到任何問題，請參閱[操作疑難排解](operations-troubleshooting-medv2.md)。

 

確認您的第一次設定設定正確之後，您可以測試其他的 MED-V 工作區設定，以確認其正常運作，例如應用程式發佈和 URL 重新導向。

在您完成所有的 MED-V 工作區套件測試並確認它已正常運作之後，您就可以將 MED-V 工作區部署到您的企業。

## 相關主題


[如何測試應用程式發佈](how-to-test-application-publishing.md)

[如何測試 URL 重新導向](how-to-test-url-redirection.md)

[部署 MED-V 工作區套件](deploying-the-med-v-workspace-package.md)

[管理 MED-V 工作區設定](manage-med-v-workspace-settings.md)

 

 





