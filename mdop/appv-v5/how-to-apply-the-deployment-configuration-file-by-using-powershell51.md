---
title: 如何使用 PowerShell 來套用部署設定檔案
description: 如何使用 PowerShell 來套用部署設定檔案
author: dansimp
ms.assetid: 78fe0f15-4a36-41e3-96d6-7d5aa77c1e06
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 49beb7ea4afe46c9b0f1640152c786d7c6ba8663
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800594"
---
# 如何使用 PowerShell 來套用部署設定檔案


在已發佈套件之前，當您在執行 App-v 5.1 用戶端的電腦上新增或設定套件時，就會套用動態部署設定檔。 此檔案會針對執行 App-v 5.1 用戶端的電腦上的所有使用者，設定封裝的預設設定。 本節說明使用部署設定檔的步驟。 程式會根據下列範例進行，並假設電腦上存在下列套件和設定檔：

**c:\\Packages\\Contoso\\MyApp.appv**

**c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml**

**使用 PowerShell 來套用部署設定檔**

-   若要針對將在特定電腦上執行套件的所有使用者指定一組新的預設設定，請輸入下列專案：

    **AppVClientPackage – Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml**

    **注意**  
    這個命令會將產生的物件捕獲到 $pkg 中。 如果套件已存在於電腦上，可以使用 AppVclientPackage Cmdlet 來套用部署**設定**檔：

    **AppVClientPackage – Name Myapp-Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml**



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 相關主題


[App-V 5.1 作業](operations-for-app-v-51.md)









