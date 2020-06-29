---
title: 修改 AGPM 服務接聽的連接埠
description: 修改 AGPM 服務接聽的連接埠
author: dansimp
ms.assetid: a82c6873-e916-4a04-b263-aa612cd6956b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2af79ecb9bd05acbc55083163903ae14ab44d06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802637"
---
# 修改 AGPM 服務接聽的連接埠


AGPM 服務是一個充當安全性 proxy 的 Windows 服務，管理用戶端對封存和生產環境中的群組原則物件（Gpo）的存取權。 根據預設，AGPM 服務會偵聽埠4600。 您可以針對每個封存修改高級群組原則管理（AGPM）封存索引檔案，以變更這個埠。

**記事** 在修改 AGPM 服務所偵聽的埠之前，建議您備份 AGPM 封存索引檔案（gpostate.xml）。 這個檔案位於您在安裝高級群組原則管理-伺服器期間，在輸入為封存路徑的資料夾中。 根據預設，此檔案的這個位置是在 AGPM 服務器上，% CommonAppData% \\Microsoft\\AGPM\\gpostate.xml%。 如果您不知道哪台電腦主持封存，您可以依照修改封存路徑的程式來顯示目前的封存路徑。 如需詳細資訊，請參閱[修改封存路徑](modify-the-archive-path.md)。

 

擁有 AGPM 服務器存取權的使用者帳戶（安裝 AGPM 服務的電腦），而封存索引檔案則需要完成此程式。

**修改 AGPM 服務偵聽的埠**

1.  在主持封存的電腦上，在文字編輯器中開啟封存索引檔（gpostate.xml）。

2.  在檔案中，搜尋**agpm： port = "4600"**。

3.  將**4600**取代為 AGPM 服務應聆聽的埠;然後，儲存並關閉檔案。

4.  在 AGPM 服務器上，重新開機 AGPM 服務。 （如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service.md)。）

5.  針對每個群組原則管理員，在 AGPM 服務器連線中修改埠。 （如需詳細資訊，請參閱[設定 AGPM 服務器](configure-the-agpm-server-connection.md)連線）。

6.  針對每個封存和 AGPM 服務器重複上述步驟。

### 其他參考資料

-   [管理 AGPM 服務](managing-the-agpm-service.md)

 

 





