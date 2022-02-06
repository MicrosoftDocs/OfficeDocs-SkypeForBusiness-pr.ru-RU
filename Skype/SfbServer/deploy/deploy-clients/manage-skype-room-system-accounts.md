---
title: Управление учетными записями системы комнат Skype
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: 'Ознакомьтесь с этой темой, чтобы узнать, как управлять Skype учетных записей системы номеров.'
---

# <a name="manage-skype-room-system-accounts"></a>Управление учетными записями системы комнат Skype
 
Ознакомьтесь с этой темой, чтобы узнать, как управлять Skype учетных записей системы номеров. 

> [!NOTE]
> Комнаты Microsoft Teams — это другой продукт с различными зависимостями и процедурами развертывания. Сведения о Комнаты Microsoft Teams см. в Комнаты Microsoft Teams [обзоре управления](/microsoftteams/rooms/rooms-manage).
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Перемещение учетной записи Skype комнат между пулами

Если вам необходимо переместить учетную запись Skype системы номеров из одного пула Skype для бизнеса Server в другой (например, во время обновления), используйте следующую команду для перемещения пула учетных записей Skype системы номеров: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Отключение Skype учетной записи системы номеров для Skype для бизнеса служб

Если вам необходимо отключить существующую учетную запись Skype room System из служб Skype для бизнеса в пуле Skype для бизнеса Server, используйте следующую команду для отключения учетной записи: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Необязательный: создайте группу администраторов Skype в Active Directory

Каждый клиент Skype, который присоединяется к домену, может полностью управляться пользователем домена с правами местного администратора на компьютере Skype системы номеров. Таким образом, вы можете создать группу выделенных администраторов в Active Directory и предоставить ей административные права во время создания нового Skype системы номеров.
