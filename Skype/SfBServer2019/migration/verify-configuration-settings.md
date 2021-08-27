---
title: Проверка параметров настройки
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Вы можете проверить репликацию сведений о конфигурации на сервер Edge, заняв Skype для бизнеса Server 2019 Get-CsManagementStoreReplicationStatus на внутреннем компьютере, на котором расположен центральный магазин управления, или на любом компьютере, на котором установлен Skype для бизнеса Server 2019 Core Components (OcsCore.msi).
ms.openlocfilehash: ff46dbad696ac4bf200bb669de768a28d0815e1b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594267"
---
# <a name="verify-configuration-settings"></a>Проверка параметров настройки

Вы можете проверить репликацию сведений о конфигурации на сервер Edge, заняв Skype для бизнеса Server 2019 г. команды **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором расположен центральный магазин управления, или на любом компьютере, на котором установлен Skype для бизнеса Server 2019 Core Components (OcsCore.msi). 
  
Исходные результаты могут указывать состояние репликации как "False" вместо "True". В этом случае запустите командлет **Invoke-CsManagementStoreReplication** и дайте некоторое время для завершения репликации, прежде чем повторно запускать командлет **Get-CsManagementStoreReplicationStatus**. 
  

