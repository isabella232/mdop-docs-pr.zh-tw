---
title: 如何使用 MED-V 工作區封裝工具來管理 URL 重新導向
description: 如何使用 MED-V 工作區封裝工具來管理 URL 重新導向
author: dansimp
ms.assetid: 1a8d25af-479f-42d3-bf5f-c7fd974bbf8c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 88167923e3bd47f2a3b0b3ada5e818715740dbe3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810784"
---
# 如何使用 MED-V 工作區封裝工具來管理 URL 重新導向


您可以在 MED-V 工作區中使用 MED-V 工作區包裝程式來管理 URL 重新導向。

**在 MED-V 工作區中管理 web 位址重新導向**

1.  若要開啟**Med-v 工作區包裝**程式，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 企業版桌面虛擬化**]，然後按一下 [ **med-v 工作區包裝程式**]。

2.  在**Med-v 工作區包裝**程式主版面板上，按一下 [**管理 Web**重新導向]。

3.  在 [**管理 Web**重新導向] 視窗中，您可以輸入、貼上或匯入在 med-v 工作區中重新導向至 Internet Explorer 的 url 清單。

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



4. 按一下 [**另存**新格式]。 將更新的 URL 重新導向檔案儲存在指定的資料夾中。 MED-V 會建立包含更新之 URL 重新導向資訊的登錄檔案。 使用 [群組原則] 部署更新的登錄機碼。 如需如何使用群組原則的詳細資訊，請參閱[群群組原則軟體安裝](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。

   MED-V 也會在指定的資料夾中建立 Windows PowerShell 腳本，您可以用來重新建立更新的 MED-V 工作區套件。

## 相關主題


[如何新增或移除已部署 MED-V 工作區中的 URL 重新導向資訊](how-to-add-or-remove-url-redirection-information-in-a-deployed-med-v-workspace.md)

[管理 MED-V URL 重新導向](manage-med-v-url-redirection.md)









