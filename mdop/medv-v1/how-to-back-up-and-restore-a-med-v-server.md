---
title: 如何備份與還原 MED-V 伺服器
description: 如何備份與還原 MED-V 伺服器
author: dansimp
ms.assetid: 8d05e3a4-279b-4ce6-a319-8a09e7a30c60
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d51cfe3727896ed68a1fd67441174a294a1073cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809746"
---
# 如何備份與還原 MED-V 伺服器


可以備份位於伺服器上的 XML 檔案，然後在伺服器上的資料遺失時還原。

**若要備份 MED-V 伺服器**

-   備份下列檔案（位於* &lt; InstallDir &gt; \\Servers\\ConfigurationServer*中）：

    **記事** 如果設定已從預設值變更，則檔案可能會儲存在不同的位置。

     

    -   ClientPolicy.xml

    -   ClientSettings.xml

    -   ConfigurationFiles.xml

    -   OrganizationPolicy.xml

    -   WorkspaceKeys.xml

    **記事** 您也可以備份 ServerSettings.xml 檔案。 不過，如果已變更特定設定（例如，在原始伺服器上），則 MED-V VM 目錄位於 [*C:\\Vms*]，而新伺服器上不存在這類目錄），可能會導致錯誤。

     

**若要還原 MED-V 伺服器**

1.  安裝新的 MED-V 伺服器。

2.  將備份檔案複製到下列目錄：

    *&lt;InstallDir &gt; \\Servers\\ConfigurationServer*

3.  重新開機 MED-V 服務。

 

 





