---
title: 管理 MED-V 工作區的自動更新
description: 管理 MED-V 工作區的自動更新
author: dansimp
ms.assetid: 306f28a2-d653-480d-b737-4b8b3132de5d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b22d3250db806e740c1d62da4fed98d5956b0eeb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811067"
---
# 管理 MED-V 工作區的自動更新


MED-V 工作區是一個虛擬電腦，其中包含獨立的作業系統，其自動軟體更新程式必須與企業中的物理電腦一樣加以管理。 因為在主機作業系統執行時，客體作業系統不一定要執行，所以您必須確認 MED-V 虛擬機器已設定為可根據需要將軟體更新套用至客體作業系統。 Microsoft 企業版桌面虛擬化（MED-V）2.0 解決方案提供的功能可讓您判斷自動軟體更新在 MED-V 工作區中的處理方式。

## 管理 MED-V-V 工作區喚醒原則


MED-V 工作區喚醒原則可保證在 MED-V 設定設定中所指定的時間，將 MED-V 虛擬機器提供給更新。 這適用于從 Microsoft 透過 Windows Update 發佈的更新，以及由非 Microsoft 解決方案（例如防病毒應用程式）部署及控制的更新。

**重要** MED-V 工作區喚醒原則已針對 Microsoft 更新基礎結構進行優化。 如果您使用 Microsoft System Center Configuration Manager 來部署非 Microsoft 更新，我們建議您同時使用 System Center 更新發行者，這會利用與 Microsoft Update 相同的基礎結構，因此可從 MED-V 工作區的喚醒原則獲益。 如需詳細資訊，請參閱[系統中心更新發行者](https://go.microsoft.com/fwlink/?LinkId=200035)（ https://go.microsoft.com/fwlink/?LinkId=200035) 。

 

當您建立 MED-V 工作區套件時，您可以在使用者登入時（**快速啟動**），或當使用者第一次開啟發佈的應用程式（**正常啟動**）時，進行設定。 或者，您可以設定讓使用者控制此設定的選項。

不論是哪一種方式，只要選取 [**快速啟動**] 選項，只要 med-v 主機以使用者身分登入，虛擬機器就會繼續執行。 在這個設定中，因為主機在使用中時，MED-V 是作用中的，所以自動更新會在不需要從 MED-V 進行任何額外處理的情況下套用。

不過，對於未指定**快速啟動**或虛擬機器處於休眠或停止狀態的情況，med-v 會透過其 med-v 工作區喚醒原則（即使未定期使用 med-v），也能保證該客體作業系統會定期更新。 MED-V 會根據您指定的設定設定，定期喚醒虛擬機器來執行此功能。 這可讓虛擬機器中的自動更新用戶端根據其配置執行。在由 MED-V 設定設定所定義的時間週期過後，MED-V 會將虛擬機器傳回其先前的狀態。

**記事** 如果使用者在更新期間開啟發佈的應用程式，則會套用所需的更新，但在更新期間結束後，MED-V 不會自動休眠或關閉。 相反地，MED-V 會繼續執行。

 

MED-V 工作區喚醒原則包含三個主要元件：

**來賓更新管理員**

這個獨立的可執行程式位於 MED-V 主機上，負責根據預先定義且可設定的排程來喚醒虛擬機器。 指定 [設定] 設定，以指出更新管理員每天要喚醒虛擬機器的時間，以及虛擬機器應保持在最新狀態（以分鐘為單位）以允許應用更新的時間。 在已達到指定的分鐘數之後，來賓更新管理員會將虛擬機器置於休眠，準備好供下次使用。 您可以透過 Windows [工作管理員]，排程此可執行程式的執行。

**來賓重新開機管理服務**

此服務位於 MED-V 主機上，有三個主要職責。 隨著來賓更新管理員，它會在使用者登入時管理虛擬機器的重新開機（如果需要的話）。 它會偵測到需要重新開機虛擬機器的情況，因為更新已安裝。 而且它可確保來賓更新管理員的工作會根據設定隨時排程。

**來賓更新服務**

此 Windows 服務位於 MED-V 虛擬機器上，負責在已安裝更新需要重新開機時進行監視。 在服務意識到需要重新開機之後，它會通知主機上的來賓重新開機管理服務。

### MED-V 工作區喚醒原則的配置設定

您可以在登錄中定義下列兩個設定值，以控制虛擬機器 awakens 接收自動更新的時間和時間。 這兩個值都位於 HKLM\\Software\\Microsoft\\MEDV\\v2\\VM 索引鍵底下。

**GuestUpdateTime** –在 med-v 必須根據24小時制的時鐘標準來喚醒虛擬機器以進行更新，每日設定小時與分鐘數。 以 HH： MM 格式指定時間。 預設值為00:00 （午夜）。

**GuestUpdateDuration** –設定 med-v 必須讓虛擬機器保持從喚醒來更新的分鐘數，從在 GuestUpdateTime 設定設定中指定的時間開始。 預設值為240（4小時）。 將此值設定為零（0）會停用 MED-V 工作區喚醒原則。

如需如何定義 MED-V 設定值的詳細資訊，請參閱[管理 Med-v 工作區配置設定](managing-med-v-workspace-configuration-settings.md)。

**記事** MED-V 最佳做法是設定您的喚醒間隔，以符合 MED-V 虛擬機器計畫定期更新的時間。 此外，建議您將這些設定設定為類似主機電腦的行為。

 

### 使用 ESD 系統重新開機通知

您可以將您的 ESD 系統設定為在應用自動更新之後，在 MED-V 工作區需要重新開機時通知 MED-V。 當您在您知道需要重新開機的 ESD 系統中套用自動更新時，您應該撰寫腳本以在 MED-V 工作區上通知下列全域事件：

**重要** 您必須以 [只修改] 許可權開啟事件，然後向其發出通知。 如果您不是以正確的許可權開啟，就無法使用。

 

``` syntax
/// <summary>
/// The guest is required to be restarted due to an ESD update.
/// </summary>
public const string MedvGuestRebootRequiredEventName = @"Global\MedvGuestRebootRequiredEvent";
using (EventWaitHandle notificationEvent = 
EventWaitHandle.OpenExisting(eventName, EventWaitHandleRights.Modify))
{
notificationEvent.Set();
}
```

當您發出這個事件的信號時，MED-V 會捕獲它，並通知虛擬機器需要重新開機。

## 相關主題


[管理 MED-V 工作區的軟體更新](managing-software-updates-for-med-v-workspaces.md)

 

 





