---
title: Включить групповой вызов для пользователей и назначить номер группы в Skype для бизнеса
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Включить пользователей для группового вызова в Skype для бизнеса Server Корпоративная голосовая связь и назначить номер группы.
ms.openlocfilehash: ab98244c570acbd7354abb7b7f6bed2fd85cf407
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864356"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Включить групповой вызов для пользователей и назначить номер группы в Skype для бизнеса

Включить пользователей для группового вызова в Skype для бизнеса Server Корпоративная голосовая связь и назначить номер группы.

После добавления номеров групп вызова в таблицу орбиты парка вызовов используется средство SEFAUtil, чтобы назначить групповые номера пользователям и включить для них групповую группу вызова.

> [!NOTE]
> В гибридном развертывании не назначать группу группового вызова пользователям, которые размещены в Интернете. Пользователи, которые находятся в сети, не могут участвовать в групповом вызове. То есть другие пользователи не могут отвечать на их звонки, а другие пользователи не могут отвечать на звонки.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Назначение группового номера и возможность группового вызова для пользователя

1. Войдите на компьютер, на котором установлен инструмент SEFAUtil с правами администратора.

2. В командной строке выполните следующую команду:

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Например, назначить пользователю номер группы 199:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>См. также

[Отключение группового пикапа для пользователей](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)