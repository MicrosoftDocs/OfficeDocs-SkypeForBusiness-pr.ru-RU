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
localization_priority: Normal
description: Вы можете проверить репликацию сведений о конфигурации на сервер Edge, заняв Skype для бизнеса Server 2019 Get-CsManagementStoreReplicationStatus на внутреннем компьютере, на котором расположен центральный магазин управления, или на любом компьютере, на котором установлен Skype для бизнеса Server 2019 Core Components (OcsCore.msi).
ms.openlocfilehash: e681781598af876f722094b0191aa784da2c533adc509a9f9fc4fad96fa4db4c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335749"
---
# <a name="verify-configuration-settings"></a>Проверка параметров настройки

Вы можете проверить репликацию сведений о конфигурации на сервер Edge, заняв Skype для бизнеса Server 2019 г. команды **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором расположен центральный магазин управления, или на любом компьютере, на котором установлен Skype для бизнеса Server 2019 Core Components (OcsCore.msi). 
  
Исходные результаты могут указывать состояние репликации как "False" вместо "True". В этом случае запустите командлет **Invoke-CsManagementStoreReplication** и дайте некоторое время для завершения репликации, прежде чем повторно запускать командлет **Get-CsManagementStoreReplicationStatus**. 
  

