---
title: 設定憑證以支援 APP-V Management Server 或 Streaming Server
description: 設定憑證以支援 APP-V Management Server 或 Streaming Server
author: dansimp
ms.assetid: 2f24e550-585e-4b7e-b486-22a3f181f543
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e537244b24d7303af550b3ced8286ba2680009e7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809032"
---
# 設定憑證以支援 APP-V Management Server 或 Streaming Server


完成證書置備程式並變更私人金鑰許可權以支援 App-v 安裝之後，您就可以啟動管理伺服器或流式處理伺服器的設定。 在安裝期間，如果在執行安裝程式前已提供憑證，嚮導會在連線**安全模式**畫面中顯示憑證，而且預設會選取 [**使用增強型安全性**] 核取方塊。

**記事** 選取針對此伺服器預配有一個以上的憑證的情況下為 App-v 設定的憑證。

 

**重要** 從版本4.2 升級到版本4.5 時，安裝程式會提供使用 [**增強的安全性**] 的選項。不過，選取此選項並不會停用 RTSP 的資料流程。 安裝之後，您必須使用管理主控台停用 RTSP。

 

選取服務將用於用戶端通訊的 TCP 埠。 預設埠是 TCP 322;不過，您可以將埠變更為您環境的自訂埠。

嚮導的其餘步驟與您在不使用 [**增強的安全性**] 功能的情況下部署 App V 管理或流式伺服器一樣。

## 為 NLB 環境設定憑證


為了支援大型企業，通常會將管理伺服器放在網路負載平衡（NLB）群集中，以支援大量連線。 這需要至少兩個顯示為單一管理伺服器的管理伺服器。 當您的環境使用具有多個管理伺服器的 NLB 群集時，您必須具備用於 NLB 群集的憑證的高級配置。

App-v 憑證會提交至在執行 Windows Server2003 的電腦上設定的認證機構（CA）。 SAN 可讓您使用與實際電腦名稱稱不同的網域名稱系統（DNS）名稱，連線到特定的管理伺服器 NLB 群集主機名稱，因為可能會有多達32台組成 NLB 群集的伺服器。

這個設定只有在使用 NLB 群集時才有必要。 當用戶端連線到伺服器時，它會使用 NLB 群集的完整功能變數名稱（FQDN），而不是個別伺服器的 FQDN 來連線。 如果您沒有使用群集中伺服器節點的 FQDN 新增 SAN 屬性，所有用戶端連線都會遭到拒絕，因為證書的公用名不符合伺服器名稱。

如需使用 SAN 屬性設定憑證的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133228> 。

## 相關主題


[支援憑證以支援安全串流](configuring-certificates-to-support-secure-streaming.md)

[如何修改私密金鑰權限以支援管理伺服器或串流伺服器](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)

 

 





