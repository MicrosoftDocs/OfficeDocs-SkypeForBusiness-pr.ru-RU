---
title: Управление учетными записями системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: В этом разделе описывается управление учетными записями системы комнат Skype.
ms.openlocfilehash: 2a45fc8507b9b09b777e6aa91c47fff2b3dfc3d2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234075"
---
# <a name="manage-skype-room-system-accounts"></a>Управление учетными записями системы комнат Skype
 
В этом разделе описывается управление учетными записями системы комнат Skype. 

> [!NOTE]
> Комнаты Microsoft Teams — это другой продукт с разными зависимостями и процедурами развертывания. Сведения о комнатах Microsoft Teams можно найти в разделе [Общие сведения об управлении](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)комнатами Microsoft Teams.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Перемещение учетной записи системы комнаты Skype между пулами

Если вам нужно перенести учетную запись системы комнаты Skype из одного пула серверов Skype для бизнеса в другой (например, во время обновления), используйте следующую команду для перемещения пула учетных записей системы для помещения в Skype. 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Отключение учетной записи системы комнаты Skype для служб Skype для бизнеса

Если вам нужно отключить существующую учетную запись комнаты Skype для служб Skype для бизнеса в пуле сервера Skype для бизнеса, используйте следующую команду для отключения учетной записи: 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Необязательно: создание группы администраторов комнатной комнаты Skype в службе каталогов Active Directory

Каждый клиент системы комнаты Skype, который присоединяется к домену, может полностью управляться пользователем домена с правами локального администратора на компьютере с системой управления комнатой Skype на устройстве. Таким образом, вы можете создать группу выделенных администраторов в службе каталогов Active Directory и предоставить этой группе права администратора во время настройки нового компьютера с операционной системой комнаты для Skype.
  

