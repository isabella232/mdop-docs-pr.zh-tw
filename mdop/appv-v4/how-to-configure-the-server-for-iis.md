---
title: 如何設定伺服器使用 IIS
description: 如何設定伺服器使用 IIS
author: dansimp
ms.assetid: 1fcfc583-322f-4a38-90d0-e64bfa9ee3d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9fe3367698b6f387d4467afdad1b3e17211134d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801538"
---
# 如何設定伺服器使用 IIS


在虛擬應用程式可以傳送到應用程式虛擬化桌面用戶端和遠端桌面服務的用戶端（以前稱為終端服務）之前，必須先設定 IIS 伺服器。 當您設定伺服器時，您就是在儲存 SFT 檔案的位置設定 [內容目錄]。 SFT 檔案包含虛擬應用程式（或應用程式）。

**若要在 IIS 伺服器上設定內容目錄**

1.  在執行 IIS 的伺服器上，找出您要用來做為內容目錄的目錄，或建立不存在的目錄。 將此目錄設定為標準檔案共用。

2.  在執行 IIS 的伺服器上，開啟 [ **Iis 管理員**]，然後在 [預設網站] 底下，建立一個與您在伺服器上建立之內容目錄相對應的虛擬目錄。 請確定已核取 [**讀取**]。

3.  為新建立的虛擬目錄提供別名**內容**。

4.  接受此虛擬目錄的所有其他預設設定。

5.  使用您先前定義的 Active Directory 網域服務中的安全性群組，將 NTFS 檔案系統許可權設定為內容目錄及 [內容目錄] 底下的 [套件] 資料夾。

**記事** 如果您使用 IIS 發佈 .ICO 和 OSD 檔案，您必須設定 OSD = TXT 的 MIME 類型;否則，IIS 將不會將 .ICO 和 OSD 檔案提供給用戶端。 如果您使用 IIS 發佈套件（SFT 檔案），則必須針對 SFT = Binary 設定 MIME 類型;否則，IIS 將不會將 SFT 檔案提供給用戶端。

 

## 相關主題


[以 Application Virtualization 伺服器為基礎的案例](application-virtualization-server-based-scenario.md)

[以電子軟體發佈為基礎的案例](electronic-software-distribution-based-scenario.md)

[如何設定 Application Virtualization Management Server](how-to-configure-the-application-virtualization-management-servers.md)

[如何設定 Application Virtualization Streaming Server](how-to-configure-the-application-virtualization-streaming-servers.md)

[如何設定檔案伺服器](how-to-configure-the-file-server.md)

 

 





