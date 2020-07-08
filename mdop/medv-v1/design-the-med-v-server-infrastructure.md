---
title: 設計 MED-V 伺服器基礎結構
description: 設計 MED-V 伺服器基礎結構
author: dansimp
ms.assetid: 2781040f-880e-4e16-945d-a38c0adb4151
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4ba4c38328c5484b7daa292f9fc33a4e59824327
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810401"
---
# 設計 MED-V 伺服器基礎結構


在本主題中，您將針對每個 MED-V 實例設計伺服器基礎結構。 這包括判斷 SQL Server 實例是否會存在於 MED-V 伺服器或遠端伺服器上，以及 SQL Server 資料庫的大小。 您也將決定管理主控台的位置。

## 針對每個 MED-V 實例設計並放置伺服器


MED-V 伺服器會實施原則，並儲存其用戶端的狀態與記錄資料。

### 外形規格

MED-V 建議您使用 2.8 GHz 的雙核 CPU 伺服器（2GB） RAM。 這個建議是依據假設 MED-V 伺服器將在專用電腦上執行，而該 SQL Server 和 MED-V 管理主控台會在不同的電腦上執行。

考慮到這種工作負荷，MED-V 伺服器應該相對輕微地載入。 在伺服器外形規格沒有特定的體系結構指導方針的情況下，使用 MED-V 建議（含與組織標準規格相符的記憶體）設計伺服器。 MED-V 伺服器可以在 Windows Server2008 上的虛擬電腦（VM）上執行，即 Hyper-v。 如果將使用 VM，請確定它有權存取與針對物理電腦所指定的 CPU 和記憶體資源。

MED-V 伺服器所需的磁片容量必須足以儲存 MED-V 工作區設定檔。 MED-V 工作區只能針對一或多位使用者使用一個 VM 和一個原則。 因此，必須儲存的 MED-V 工作區數量取決於相同 VM 的不同使用者所需的不同原則，以及要使用的虛擬機器數量的程度。 MED-V 工作區 XML 檔案的大小會與典型的 MED-V 工作區30KB。 若要判斷所需的磁片容量，請將 30 KB 乘以 MED-V 伺服器將儲存的 MED-V 工作區數。

MED-V 伺服器最重要的網路連線是其用戶端的連結，因此請將伺服器放在可提供最可用頻寬和其用戶端最穩定連結的網路位置。

### 容錯

在 MED-V 實例中，只能有一個作用中的 MED-V 伺服器，而 MED-V 不包含將伺服器放在 Microsoft 叢集服務器（MSCS）群集中以提供容錯的標準功能。 被動備份伺服器可以手動設定。

若要決定是否應該針對 MED-V 實例手動設定被動式備份伺服器，請判斷是否允許使用者在離線模式中使用 MED-V 影像。 如需離線模式的詳細資訊，請參閱[如何設定網域使用者或群組](how-to-configure-a-domain-user-or-groupmedvv2.md)。 如果不允許使用者離線工作，即使已在用戶端上啟動 MED-V 工作區，也無法繼續在 MED-V 伺服器失敗的事件中運作。 如果允許離線工作，請針對每個 MED-V 工作區，決定用戶端在必須進行驗證之前離線工作的時間。 這是伺服器無法使用的最大時間長度。

## 設計並放置 SQL Server 資料庫


MED-V 伺服器會使用 SQL Server 資料庫來儲存用戶端狀態及事件。 您可以在與 MED-V 伺服器相同的電腦上安裝 SQL Server 資料庫，也可以將它放在執行 SQL Server 的個別伺服器上（選擇性是 [遠端]）。 您可以與其他 MED-V 實例共用資料庫，在這種情況下，來自這些實例的事件和警報會儲存在相同的資料庫中，而報告將包含來自所有實例的事件。 您可以在現有的 SQL Server 實例中安裝資料庫，而其他 MED-V 伺服器的資料庫可以駐留在該實例中。

如果您將資料庫伺服器放在一個從 MED-V 伺服器遠端的位置，且在沒有足夠頻寬可用的網路連結中，報告可能會在主機中載入緩慢，而且可能不會顯示來自用戶端的最新資料。 請參閱您在[定義專案範圍](define-the-project-scope.md)中所決定的組織服務層級預期，並使用該資訊來決定放置 SQL Server 資料庫的位置。

### 外形規格

如果您將在與 MED-V 相同的伺服器上執行 SQL Server，且如果 SQL Server 只是用來儲存該伺服器的資料，請從 MED-V 建議開始，並為 SQL Server load 新增資源。 如果 SQL Server 要儲存來自多個 MED-V 實例的事件與警報，請參閱[基礎結構規劃與設計 MICROSOFT SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南（HTTP://go.microsoft.com/fwlink/?LinkId=163302）。

資料庫的大小取決於資料庫將儲存的用戶端事件數量。 事件是由用戶端的一般操作（例如，啟動 MED-V 工作區時，或在 MED-V 工作區中發生錯誤時）建立。 用戶端傳送事件的預設間隔是1分鐘。

若要估計資料庫的大小，請判斷下列事項：

-   MED-V 實例中的用戶端數量。 最大值為5000。

-   典型的事件到達速度。 這個速度取決於用戶端使用方式的行為，但每個用戶端每天大約有15到20個事件。

-   事件大小。 此大小通常大約200個位元組。

-   儲存空間量。 要儲存事件的天數。

將這些值相乘，以位元組為單位計算所需的資料儲存大小，然後在下列專案中新增安全要素：

-   錯誤，這可能會在短時間內從用戶端建立大量事件。

-   資料庫資料表和組織空間。

若要估計每秒基礎結構優化（IOPs）需求，請使用上述值，將一般事件到貨率乘以實例中的用戶端數。 這會產生每天可以撰寫的記錄數。 將該數除以86400，以衍生每秒寫入的記錄數。 如果可以使用單一基礎結構優化（IO）作業 equated 寫入操作，這個數位就是所需的寫入 IOPs。 在報告活動時新增緩衝區。 這是難以判斷的，但視與實例搭配使用的主控台數量以及它們用於產生報告的頻率而定。

### 容錯

當 MED-V 用戶端正在執行時，如果伺服器無法使用，系統就會在用戶端上備份事件，而且管理主控台將無法使用報告。 請參閱[定義專案範圍](define-the-project-scope.md)來決定是否需要容錯 SQL Server 基礎結構的設計，以確定組織的服務等級預期。

MED-V 不提供在 MSCS 群集中運行 SQL Server 的支援。 為了提供熱備用，並避免發生失敗的資料遺失，您可以將 SQL Server 放在記錄傳送設定中。 如需有關記錄傳送的詳細資訊，請參閱[基礎結構規劃與設計 MICROSOFT SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南（ https://go.microsoft.com/fwlink/?LinkId=163302) 。

## 設計管理主控台


MED-V 管理主控台的其中一部分功能是先測試 Vm，然後再將其打包以發佈到 MED-V 用戶端。 因此，管理主控台的設計方式應該與典型的 MED-V 用戶端電腦的外形規格一樣，以盡可能接近的方式來設計。

管理主控台應用程式是與 MED-V 用戶端一起安裝，並將 Microsoft Virtual PC2007 SP1 與 Microsoft 知識庫文章974918中所述的修正程式搭配使用。 必須使用用戶端作業系統;MED-V 管理主控台無法在與 MED-V 伺服器相同的系統上執行。

您無法與多個 MED-V 伺服器實例共用管理主控台。 MED-V 伺服器的位址是在安裝管理主控台的 MED-V 用戶端期間指定;此功能可以在安裝後進行變更，但在任何時候，管理主控台只能與單一 MED-V 伺服器搭配使用。

您可以將多個管理主控台搭配單一的 MED-V 伺服器使用。 為了避免發生衝突，有一個可讓其他主控台使用者在其中一個主機變更 MED-V 工作區的機制。

針對每個 MED-V 實例，判斷需要多少管理主控台，以及它們將放在哪裡。 選取要用於管理主控台的典型 MED-V 用戶端外形規格。

## 相關主題


[MED-V 1.0 SP1 支援的組態](med-v-10-sp1-supported-configurationsmedv-10-sp1.md)

[設定叢集模式的 MED-V 伺服器](configuring-med-v-server-for-cluster-mode.md)

[如何安裝 MED-V 用戶端及 MED-V 管理主控台](how-to-install-med-v-client-and-med-v-management-console.md)

[使用 MED-V 管理主控台使用者介面](using-the-med-v-management-console-user-interface.md)

 

 





