---
title: MED-V 1.0 SP1 升級檢查清單
description: MED-V 1.0 SP1 升級檢查清單
author: dansimp
ms.assetid: 1a462b37-8c7a-4826-9175-0b1b701d345b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9c418eff8dfb6146204d7d9212d42e49db000fb1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812254"
---
# MED-V 1.0 SP1 升級檢查清單


若要將 Microsoft 企業版桌面虛擬化（MED-V）1.0 升級至 MED-V 1.0 服務 Pack1 （SP1），必須升級用戶端。 您也可以選擇升級伺服器。

## 伺服器升級


**若要將 MED-V 1.0 伺服器升級至 MED-V 1.0 SP1**

1.  備份位於* &lt; InstallDir &gt; /Servers/ConfigurationServer*目錄中的下列檔案：

    -   OrganizationalPolicy.XML

    -   ClientPolicy.XML

    -   WorkspaceKeys.XML

2.  備份* &lt; InstallDir &gt; /伺服器/ServerSettings.xml*檔案。

3.  卸載 MED-V 1.0 伺服器。

4.  安裝 MED-V 1.0 SP1 伺服器。

5.  將備份檔案還原至適當的目錄。

6.  重新開機 MED-V 伺服器服務。

**記事** 如果伺服器設定已從預設值變更，則檔案可能會儲存在不同的位置。

 

## 用戶端升級


若要將 MED-V 1.0 用戶端升級至 MED-V 1.0 SP1，請在 MED-V 1.0 用戶端上安裝 .msp 檔案。 用戶端和 MED-V 會自動升級。

 

 





