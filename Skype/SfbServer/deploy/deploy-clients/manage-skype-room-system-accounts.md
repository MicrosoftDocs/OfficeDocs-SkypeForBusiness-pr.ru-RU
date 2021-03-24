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
description: Ознакомьтесь с этой темой, чтобы узнать, как управлять учетной записью skype Room System.
ms.openlocfilehash: e6b905b065badb729ccc9281d63ba050fc032ef2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093297"
---
# <a name="manage-skype-room-system-accounts"></a>Управление учетными записями системы комнат Skype
 
Ознакомьтесь с этой темой, чтобы узнать, как управлять учетной записью skype Room System. 

> [!NOTE]
> Microsoft Teams Rooms — это другой продукт с различными зависимостями и процедурами развертывания. Сведения о комнатах Microsoft Teams см. в обзоре управления Microsoft Teams [Rooms.](/microsoftteams/rooms/rooms-manage)
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Перемещение учетной записи Skype Room System между пулами

Если вам необходимо переместить учетную запись системы Skype Room System из одного пула Skype для бизнес-сервера в другую (например, во время обновления), используйте следующую команду для перемещения пула учетных записей системы номеров Skype: 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Отключение учетной записи skype Room System для служб Skype для бизнеса

Если вам необходимо отключить существующую учетную запись Skype Room System из служб Skype для бизнеса в пуле Skype для бизнеса Server, используйте следующую команду, чтобы отключить учетную запись: 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Необязательный вариант: создайте группу администратора системы номеров Skype в Active Directory

Каждый клиент системы номеров Skype, который присоединяется к домену, может полностью управляться пользователем домена с правами местного администратора на компьютере устройства Skype Room System. Таким образом, вы можете создать группу выделенных администраторов в Active Directory и предоставить этой группе административные права во время создания нового компьютера системы номеров Skype.
