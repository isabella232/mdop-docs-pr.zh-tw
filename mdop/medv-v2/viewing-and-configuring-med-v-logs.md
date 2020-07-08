---
title: 檢視及設定 MED-V 記錄
description: 檢視及設定 MED-V 記錄
author: dansimp
ms.assetid: a15537ce-981d-4f55-9c3c-e7fbf94b8fe5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7984cec072827136db9ea52a535c0ea44c6bc2c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810130"
---
# 檢視及設定 MED-V 記錄


當您排查 MED-V 問題和問題時，您可能會發現存取 MED-V 事件記錄很有説明。 您可以使用 MED-V 管理工具組開啟主機電腦和來賓虛擬機器的事件檢視器。 您也可以使用 MED-V 管理工具組來設定 MED-V 事件記錄的記錄層級（MED-V 事件）。

如需如何開啟 MED-V 管理工具組的相關資訊，請參閱[使用管理工具組在 med-v 中進行疑難排解](troubleshooting-med-v-by-using-the-administration-toolkit.md)。

## 查看 MED-V 事件記錄


在 [ **Med-v 管理工具**組] 視窗中，按一下 [**主機事件**] 來開啟主機電腦的事件檢視器。 或者，按一下 [**來賓事件**] 來開啟來賓虛擬機器的事件檢視器。

[事件檢視器] 會開啟並顯示對應的事件記錄，您可以用來針對您在部署或管理 MED-V 時可能遇到的問題進行疑難排解。 根據預設，只會顯示錯誤和警告。 如需特定事件識別碼和訊息的詳細資訊，請參閱[Med-v 事件記錄訊息](med-v-event-log-messages.md)。

**記事** 如果使用者擁有系統管理許可權，就只能將事件記錄檔儲存在來賓中。

 

### 手動開啟主機電腦中的 [事件檢視器]

1.  按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**管理工具**]。

2.  按兩下 [**事件檢視器**]，然後按一下 [**應用程式和服務記錄**]。

3.  按兩下 [ **MEDV**]。

## 設定 MED-V 事件記錄


您可以選取 MED-V 管理工具組上的對應選項按鈕，以指定 MED-V 事件記錄層級。 您可以決定事件記錄是否只包含錯誤、錯誤和警告，或錯誤、警告及資訊訊息。 針對主機電腦和來賓虛擬機器，會同時設定指定的事件記錄層級。

您也可以透過編輯 EventLogLevel 註冊表值來指定事件記錄層級。 如需詳細資訊，請參閱[管理 Med-v 工作區配置設定](managing-med-v-workspace-configuration-settings.md)。

**記事** 您在**Med-v 管理工具**組中指定的層級會套用至未來的 med-v 事件記錄。 如果您將階層設定為捕獲所有錯誤、警告及資訊性訊息，則會移除事件記錄更快速且較舊的事件。

 

## 相關主題


[重新啟動和重設 MED-V 工作區](restarting-and-resetting-a-med-v-workspace.md)

[檢視 MED-V 工作區設定](viewing-med-v-workspace-configurations.md)

 

 





