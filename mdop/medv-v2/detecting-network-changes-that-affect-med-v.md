---
title: 偵測影響 MED-V 的網路變更
description: 偵測影響 MED-V 的網路變更
author: dansimp
ms.assetid: fd29b95a-cda2-464d-b86d-50b6bd64b4ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5f43c30dee9ef8e06a7ae226849a4f21e83257c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809915"
---
# 偵測影響 MED-V 的網路變更


Microsoft 企業桌面虛擬化（MED-V）2.0 解決方案可讓您設定您的環境，以偵測在部署 MED-V 工作區且可能會影響 MED-V 的特定網路變更。

此功能包含在客體作業系統中執行的元件，系統會在主機電腦上收到網路設定變更的通知。 它允許在來賓中執行的非 Microsoft ESD 或其他應用程式解析為主機 ESD 或應用程式解析的相同網路端點。

**記事** 此功能只有在虛擬機器設定為「網路位址轉譯（NAT）」模式時才能使用。 如果虛擬機器是針對橋接模式進行設定，則不會產生變更指示。

 

本節提供資訊與指示，協助您監視那些可能會影響 MED-V 的網路變更。

## 若要偵測 MED-V 的網路變更


部署 MED-V 工作區之後，您可以 preforming 下列工作來監視某些網路設定的變更：

1. 建立受管理的物件格式（MOF）檔案，該檔案會尋找您要監視的網路設定變更。 下列程式碼會顯示您可以建立的 MOF 檔案範例。

   ``` syntax
   #pragma namespace ("\\\\.\\root\\ccm\\NetworkConfig")

   class CCM_IPConfig
   {
       [NotNull: ToInstance ToSubClass] uint32 AddressFamily; // AF_INET, AF_INET6
       [Key, NotNull: ToInstance ToSubClass] string IPAddress; // IPv4 or IPv6 address
       [NotNull: ToInstance ToSubClass] string SubnetMask; // IPv4 subnet mask
   };

   class CCM_NetworkAdapter
   {
       [Key, NotNull: ToInstance ToSubClass] string Name;
       [NotNull: ToInstance ToSubClass] uint32 DHCPEnabled = 0; 
       [NotNull: ToInstance ToSubClass] uint32 Quarantined = 0; // To check if it is quarantined.
       CCM_IPConfig IPConfigInfo[];
   };

   [singleton]
   class CCM_NetworkAdapters
   {
       [NotNull: ToInstance ToSubClass] String ProviderName; // MED-V or other provider
       CCM_NetworkAdapter AdaptersInfo[];
   };
   ```

2. 編譯 MOF 檔案。

3. 在來賓中安裝 MOF 檔案。

安裝 MOF 檔案之後，您就可以建立一個事件訂閱，以訂閱對**CCM \ _NetworkAdapters**類別進行的 Windows Management INSTRUMENTATION （WMI）建立、修改或刪除事件。 這會偵測到主機的下列變更：

網路是否有任何設定變更，例如 IP 位址或網路介面卡的變更？

網路可用或無法使用？

網路設定是否已從橋接模式變更為 NAT 模式？

網路設定是否已從 NAT 模式變更為橋接模式？

主機上的 MED-V 元件會針對這些變更監視網路，然後向訪客指示變更。 來賓中的元件會建立 WMI 實例來監視 MED-V 工作區，以瞭解這些變更。

您所建立的事件訂閱會在其中一或多個網路變更時（即建立、修改或刪除），在 WMI 系統中提供通知。

## 相關主題


[監控 MED-V 工作區](monitor-med-v-workspaces.md)

[管理 MED-V 工作區設定](manage-med-v-workspace-settings.md)

 

 





