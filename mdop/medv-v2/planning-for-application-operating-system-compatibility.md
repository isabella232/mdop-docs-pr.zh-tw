---
title: 規劃應用程式作業系統相容性
description: 規劃應用程式作業系統相容性
author: dansimp
ms.assetid: cdb0a7f0-9da4-4562-8277-12972eb0fea8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b10da2c870e5ddc32098136225515cdd0523809
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811174"
---
# 規劃應用程式作業系統相容性


本主題可協助您判斷如何解決應用程式作業系統相容性問題，並討論 Microsoft 企業版桌面虛擬化（MED-V）2.0 作為貴組織的解決方案的運作方式。

本主題討論 MED-V 的商業需求，並將 MED-V 與 Windows XP 模式及 Microsoft Application Virtualization （App-v）進行比較：

-   [MED-V 的業務需求](#bkmk-whenmedv)

-   [MED-V 與 Windows XP 模式的優點](#bkmk-medvvsxp)

-   [MED-V 與 app-v 的優點](#bkmk-medvvsappv)

## <a href="" id="bkmk-whenmedv"></a>MED-V 的業務需求


當貴公司的 IT 部門決定是否要升級至 Windows 7 時，必須注意其行業應用程式和 web 的商務線應用程式，以確保這些功能可以在新作業系統上執行。 通常，這些應用程式和 Url 是透過舊版 Windows 或 Internet Explorer 建立的，在新的作業系統中嘗試使用它們時，可能會發生問題。 Microsoft 提供多種不同的方法來處理升級時可能發生的各種相容性問題，例如應用程式相容性工具箱（ACT）和 Windows 7 程式相容性小幫手。 但即使已針對相容性測試所有應用程式且已確定，某些應用程式仍無法在 Windows 7 上正常運作，或因成本太高而無法解決。

使用 MED-V，您可以透過執行 Windows XP 的 Windows 虛擬電腦環境來執行這些繼承應用程式。 因為您不需要在升級之前在新作業系統上測試和驗證這些問題應用程式，所以您的遷移至 Windows 7 會更順利且更快速。

### 使用 MED-V 檢查清單

如果下列任何一種情況適用于您，請考慮使用 MED-V：

-   您是大型組織（例如，500的使用者等等）、與 Microsoft 有企業協定，以及規劃升級至 Windows 7。

-   您已測試您的商務用行應用程式，但發現與 Windows 7 不相容的專案。

-   您已透過升級應用程式或使用 Microsoft 提供的墊片（例如應用程式相容性工具箱（ACT）），解決了這些問題應用程式的相容性問題，但某些應用程式的相容性問題仍會保留。

-   您已考慮使用 App-v 作為傳遞不相容的應用程式的選項，並在您實現 App-v 之後結束，您仍有必須解決的應用程式作業系統相容性問題。

-   您已將 Windows XP 模式視為方案，並已確定它不是有效的選項，因為：

    -   您想要同時將包含問題應用程式的虛擬影像部署到所有的使用者，而不是個別的方式，並讓虛擬影像自動加入至網域。

    -   您已決定管理這些繼承應用程式（實際提供）並從集中位置（而不是每個使用者的桌面）控制 Windows 虛擬電腦設定。

    -   您想要能夠以比例（而不是每個桌面）來更新和支援虛擬機器。

    -   您想要重新導向較舊版本 Internet Explorer 的 Url 在虛擬機器上的執行方式，並在稍後輕鬆管理 URL 重新導向。

-   您已認為，您可以儘快升級至 Windows 7，且決定要推遲解決您剩餘的應用程式相容性問題，直到您在 MED-V 中找到可用的解決方案為止。

## <a href="" id="bkmk-medvvsxp"></a> MED-V 與 Windows XP 模式的優點


Windows 7 版 windows 版電腦可讓您同時在單一裝置上執行不同版本的作業系統，且包含在 Windows 7 專業版及更新版本中。

Windows XP 模式功能提供預先配置的 Windows XP 映射，讓您可以建立虛擬 Windows XP 環境，以利用 Windows 虛擬電腦。 在這個虛擬環境中，您可以手動安裝與 Windows 7 不相容且無法透過 Windows 虛擬電腦順暢執行的應用程式。

**使用 Windows XP 模式，您可以執行下列動作：**

-   在執行 Windows Virtual 電腦的虛擬機器內，執行與 Windows XP 相容的應用程式。

-   將這些應用程式發佈到主機的桌面或程式功能表。

如果您想要將這些虛擬機器以大型規模的方式提供給 Windows 7，您必須能夠快速部署虛擬機器、提供及自訂它們、控制其設定並輕鬆支援。

MED-V 建立在 Windows XP 模式上，以提供企業範圍的應用程式相容性。 雖然 Windows XP 模式僅限為個人和小型企業提供虛擬的應用程式功能，但 MED-V 可讓您在公司網路中的預先設定的 Windows XP 映射大規模部署。 它為您提供企業版的管理解決方案，以供您設定、部署及維護這些虛擬 MED-V 工作區。 MED-V 也提供 enterpriseadministrators 用來控制影像使用的一組原則。 這包括哪些使用者將能夠存取這些影像中的哪些特定應用程式。

**使用 MED-V，您可以執行下列動作：**

-   升級到您的新作業系統，而不需要測試並解決每個不相容的應用程式和 URL。

-   部署自動以網域連接並針對每個使用者進行自訂的虛擬 Windows XP 影像。

-   將應用程式和 URL 重新導向資訊提供給使用者。

-   控制 Windows 虛擬電腦設定。

-   透過監視和疑難排解來維護和支援端點。

-   確定來賓電腦已修補，即使是處於暫停狀態也一樣。

-   自動化每個使用者的虛擬機器建立與 sysprep 初始化。

-   輕鬆診斷主機和來賓電腦上的問題。

-   透過 Windows Virtual PC NAT 模式，無縫管理連線的來賓電腦。

## <a href="" id="bkmk-medvvsappv"></a>MED-V 與 app-v 的優點


MED-V 和 App-v 是兩種非常不同的技術，可以輕鬆地共同解決您的應用程式作業系統相容性問題。 使用 App-v，您可以為每個應用程式建立個人化的套件，每個應用程式都要與其他應用程式分開。 然後，您就可以將每個虛擬應用程式立即傳送給使用者，這對於 Windows 7 部署策略非常有用。

MED-V 不會個別處理應用程式。 相反地，它會在執行 Windows 7 的同一台電腦上建立另一個 Windows XP 實例。 您可以視需要在這個虛擬影像中安裝任意多個應用程式，並像管理貴組織中的任何其他桌面一樣來管理影像。

此外，您也可以將 MED-V 搭配 App-v 搭配使用，以使用 MED-V 來安裝、發佈和管理依應用程式排序的虛擬應用程式。

## 相關主題


[定義和規劃 MED-V 部署](define-and-plan-your-med-v-deployment.md)

 

 





