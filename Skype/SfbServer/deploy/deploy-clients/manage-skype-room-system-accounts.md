---
title: Управление учетными записями системы комнат Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: В этом разделе описывается управление учетными записями системы комнат Skype.
ms.openlocfilehash: 502e9c3e7036abef832bf051513b11dff4c3becc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20999634"
---
# <a name="manage-skype-room-system-accounts"></a>Управление учетными записями системы комнат Skype
 
В этом разделе описывается управление учетными записями системы комнат Skype. 

> [!NOTE]
> Версии 2 Скайп комнаты систем — это разные продукт с другой зависимости и процедуры развертывания. Сведения о версии 2 Скайп комнаты систем содержатся v2 систем комнаты Скайп [Общие сведения об управлении](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Перемещение между пулами Скайп комнаты системной учетной записи

Если необходимо переместить Скайп комнаты системную учетную запись из одной Скайп для пула сервера на другой (например, во время обновления), используйте следующую команду для перемещения Скайп комнаты системной учетной записи группы: 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Отключение Скайп комнаты системную учетную запись для Скайп для бизнес-служб

Если требуется отключить существующей системы комнаты Скайп учетной записи из Скайп для бизнес-служб на Скайп для пула Business Server, используйте следующую команду для отключения учетной записи: 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Необязательно: Создание группы администраторов системы комнаты Скайп в Active Directory

Каждый клиент Скайп комнаты системы, который присоединен к домену управляемые пользователем домена с правами локального администратора на устройство системы комнаты Скайп ПК. Таким образом можно создать группу выделенного администраторов в Active Directory и обеспечить административные права этой группы во время set up нового Скайп комнаты системы компьютера.
  

