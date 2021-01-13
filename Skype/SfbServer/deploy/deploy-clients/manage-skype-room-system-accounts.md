---
title: Управление учетными записями системы комнат Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: В этом разделе вы узнаете, как управлять учетной записью системы комнат Skype.
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805559"
---
# <a name="manage-skype-room-system-accounts"></a>Управление учетными записями системы комнат Skype
 
В этом разделе вы узнаете, как управлять учетной записью системы комнат Skype. 

> [!NOTE]
> Комнаты Microsoft Teams — это другой продукт с разными зависимостями и процедурами развертывания. Сведения о комнатах Microsoft Teams см. в обзоре управления комнатами Microsoft [Teams.](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Перемещение учетной записи системы комнат Skype между пулами

Если необходимо переместить учетную запись системы комнат Skype из одного пула Skype для бизнеса Server в другой (например, во время обновления), используйте следующую команду для перемещения пула учетных записей системы комнат Skype: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Отключение учетной записи системы комнат Skype для служб Skype для бизнеса

Чтобы отключить существующую учетную запись системы комнат Skype для бизнеса в пуле Skype для бизнеса Server, используйте следующую команду для отключения учетной записи: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Необязательно: создание группы администраторов системы комнат Skype в Active Directory

Каждый клиент системы комнат Skype, который присоединяется к домену, может полностью управляться пользователем домена с правами локального администратора на компьютере устройства системы комнат Skype. Таким образом, вы можете создать выделенную группу администраторов в Active Directory и предоставить ей права администратора во время создания нового компьютера системы комнат Skype.
  

