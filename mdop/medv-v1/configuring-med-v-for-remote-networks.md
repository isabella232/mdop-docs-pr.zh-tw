---
title: 設定遠端網路的 MED V
description: 設定遠端網路的 MED V
author: dansimp
ms.assetid: 4d2f0081-622f-4a6f-8d73-f8c2108036e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328376046ee5213f3d5bb09be7adf8c81f8508b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811925"
---
# 設定遠端網路的 MED V


您可以將 MED-V 設定為在網路內部、遠端或從網路內部或遠端從網路內部進行工作。

## <a href="" id="bkmk-howtoconfiguremedvtoworkfrominsideanetworkorremotely"></a>


**將 MED-V 設定為從網路內工作**

-   在網路內設定 MED-V 伺服器與影像發佈。

**將 MED-V 設定為遠端作業**

1.  設定 MED-V 伺服器以及可從網際網路存取的影像發佈伺服器。

2.  如有需要，請設定周邊網路（也稱為 DMZ）反向 proxy。

3.  在*ClientSettings.xml*檔案中設定驗證方法，可在 [ **Servers\\Configuration Server\\** ] 資料夾中找到該檔案。

**將 MED-V 設定為從網路內部和遠端使用**

1.  在網路內設定 MED-V 伺服器與影像發佈伺服器。

2.  確保伺服器可從網際網路存取。

3.  設定 DNS 解析，讓用戶端嘗試連線到伺服器時，會根據用戶端位置自動連接到正確的伺服器（在網路或網際網路內）。

4.  如有需要，請設定周邊網路反向 proxy。

5.  在*ClientSettings.xml*檔案中設定驗證方法，可在 [ **Servers\\Configuration Server\\** ] 資料夾中找到該檔案。

**記事** 在套用新設定時，必須重新開機該服務。

 

-   您可以將 IIS 驗證配置變更為下列其中一項：基本、摘要、NTLM 或協商。 預設為 [協商]，並使用下列專案：

    ```xml
    <ImageDistribution>
    <!-- The authentication used for image download. Basic and digest authentication should be used only under SSL.-->
       <!-- The line below can be one of the following: -->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_BASIC</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_DIGEST</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NTLM</BG_AUTH_SCHEME-->
       <!--BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME-->
       <Authentication type="Kidaro.Foundation.Bits.BG_AUTH_SCHEME">
          <BG_AUTH_SCHEME>BG_AUTH_SCHEME_NEGOTIATE</BG_AUTH_SCHEME>
       </Authentication>
    </ImageDistribution>
    ```

## 相關主題


[MED-V 基礎結構規劃和設計](med-v-infrastructure-planning-and-design.md)

 

 





