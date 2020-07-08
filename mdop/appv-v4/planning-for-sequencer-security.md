---
title: 規劃排序器安全性
description: 規劃排序器安全性
author: dansimp
ms.assetid: 8043cb02-476d-4c28-a850-903a8ac5b2d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bf1e85e24d93d373add38b5efe51ceb40faae24e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800914"
---
# 規劃排序器安全性


您可以在設定應用程式虛擬化（App-v）時儘早納入推薦的實施做法，讓您的排序器實現運作正常且更安全。 如果您已設定排序器，請使用下列最佳做法指導方針，以重新審視您的設計決策，並從安全形度分析它們。

**重要**  
App-v 排序器會收集並部署執行排序器之電腦上錄製的所有應用程式資訊。 您應該確保所有存取執行排序器的電腦的使用者都有管理認證。 擁有使用者帳號憑證的使用者，不應該有控制套件內容和套件檔案的存取權。 如果您是在執行遠端桌面服務（舊稱終端服務）的電腦上進行排序，請確認該電腦是專門進行排序的電腦，且在進行排序期間，擁有使用者帳號憑證的使用者並未連線至該電腦。



## 排序器安全性最佳做法


在實施及使用 Application Virtualization （App-v） Sequencer 時，請考慮下列案例和相關的最佳做法：

-   **在執行排序器的電腦上進行病毒掃描**，建議您先掃描執行排序器的電腦以尋找病毒，然後在先後順序程式期間停用執行排序器的電腦上的所有防病毒及惡意程式碼檢測軟體。 這會加快排序程式，並防止防毒軟體元件與反惡意程式碼軟體元件干擾排序程式。 接著，在未執行排序器的電腦上安裝排序的套件，並在成功安裝之後，掃描該電腦是否有病毒。 如果發現病毒，請聯絡軟體的製造商，告知受感染的來源檔案，並在沒有病毒的情況下要求更新的安裝來源。 或者，您也可以在安裝階段之後掃描 Sequencer，如果發現有病毒，請依照上述所述的方式聯繫軟體製造商。

    **注意**  
    如果在應用程式中偵測到病毒，則不應將應用程式部署到目的電腦。



-   **在 NTFS 檔案上捕獲存取控制清單（acl）**： app-v 排序器會捕獲安裝產品期間監視之檔案的 NTFS 檔案系統許可權。 這項功能可讓您更精確地複製應用程式的預期行為，就像它是在本機安裝且未虛擬化。 在某些情況下，應用程式可能會儲存使用者不想要在應用程式檔案中存取的資訊。 例如，應用程式可以在應用程式內的檔案中儲存身分認證資訊。 如果不是在套件上強制執行 Acl，使用者可能會在應用程式之外查看並使用這項資訊。

    **注意**  
    您不應該將儲存未加密之安全特定資訊（例如密碼等）的應用程式序列化。



~~~
During the installation phase, you can modify the default permissions of the files if necessary. After completion of the sequencing process, but before saving the package, you can choose whether to enforce security descriptors that were captured during the installation of the application. By default, App-V will enforce the security descriptors specified during the installation of the application. If you turn off security descriptor enforcement, you should test the application to ensure the removal of associated Access Control Lists (ACL) will not cause the application to perform unexpectedly.
~~~

-   **Sequencer 不會捕獲登錄 acl**，雖然排序器會在排序期間的安裝階段捕獲 NTFS 檔案系統 acl，但無法捕獲註冊表的 acl。 除了服務之外，使用者將擁有虛擬應用程式的所有登錄機碼的完整存取權。 不過，如果使用者修改虛擬應用程式的登錄，該變更將會儲存在特定的書店（**uservol _sftfs \ _v1**）中，而不會影響其他使用者。

-   **應用程式服務**-app-v 針對屬於虛擬化應用程式的應用程式服務提供支援。 不過，在虛擬環境中，它們將會執行的安全性內容受到限制。 虛擬環境中唯一支援的安全性內容是本機系統、本機服務和網路服務。 在排序期間，如果為所支援的三種應用程式服務指定了安全性內容，則會在虛擬環境中套用本機系統安全性內容。 如果應用程式服務設定為使用本機服務或網路服務，則會在虛擬環境中生效。 您可以使用這三個安全上下文，在排序程式期間完成設定服務帳戶的操作。

-   **保留的安全性資訊**：在排序應用程式時，您可以將應用程式作為使用者安裝，或者您可以開發自動方法來安裝應用程式，同時監視。 不會從套件中排除的所有專案都會被捕獲為該套件的一部分，因此應用程式將會有必要的資產在虛擬化環境中執行。 某些應用程式會在安裝期間儲存機密的安全性資訊（例如密碼）;如果持久保持不受保護，則其他可存取套件的使用者就能存取此安全性資訊。 在安裝期間，如果應用程式安裝要求輸入密碼或其他安全性敏感資訊，請檢查檔，以確保它不會繼續（在安裝之後移除），或在已保留的狀態下（已加密）。

-   **保護虛擬應用程式套件**（安全）：請務必將虛擬應用程式套件儲存在網路上的安全位置，以防止套件遭到篡改或損毀。

## 相關主題


[規劃安全性與保護](planning-for-security-and-protection.md)









