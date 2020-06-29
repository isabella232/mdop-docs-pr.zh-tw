---
title: 關於虛擬環境
description: 關於虛擬環境
author: dansimp
ms.assetid: e03a8c72-56c1-4ae9-aa45-0283c50a154c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 15f3ae29ae8d5586f83baa98ea6821e09ae5c305
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809327"
---
# 關於虛擬環境


虛擬應用程式在虛擬環境中執行。 虛擬環境可讓每個應用程式在桌上型電腦、膝上型電腦或遠端桌面工作階段主機（RDSession 主機）伺服器上執行，而不需安裝及變更主機作業系統。 每個應用程式都會在虛擬環境中攜帶自己的設定資訊。 因此，許多應用程式與同一部電腦上的其他應用程式並排執行，而不會發生任何衝突。

虛擬應用程式是在本機執行，因此它們會以完整的效能、功能及存取權，讓您在本機安裝任何應用程式時都能使用這些服務。

因為每個應用程式都是在虛擬環境中執行，所以下列問題有所減少：

-   應用程式衝突：在不使用應用程式虛擬化的環境中，您必須徹底測試每個應用程式，以確保它不會干擾其他已安裝的應用程式。

-   迴歸測試—因為應用程式不會變更基礎作業系統，所以會消除漫長的迴歸測試。

-   版本不相容：相同應用程式的不同版本可以同時在同一部電腦上執行。

-   多使用者存取：不會在多使用者模式下執行的應用程式，因此不能在 RDSession 主機內執行，現在可以在單一 RDSession 主機上為多位使用者正確執行此操作並正常運作。

-   多筆問題—同一應用程式使用不同設定的兩個實例可以同時在同一部電腦上執行。

-   伺服器 siloing —已消除許多個別伺服器群的需求。

虛擬環境包含每個應用程式的虛擬機器碼。 其他應用程式或公用程式（例如 Regedit）無法看到由一個應用程式所建立的登錄設定。 虛擬機器不會複製整個註冊表，而是使用重迭*的方法。* 只要虛擬機器中不包含該登錄機碼目的虛擬複本，應用程式就可以讀取用戶端登錄中的專案。 所有的應用程式寫入登錄都包含在虛擬登錄中。

虛擬環境也包含虛擬檔案系統和其他虛擬元件，包括虛擬服務和虛擬 COM。

## 相關主題


[Application Virtualization Client 管理主控台概觀](application-virtualization-client-management-console-overview.md)

 

 





