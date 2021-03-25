---
title: Включить групповую подбираемую группу для пользователей и назначить номер группы в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Включить пользователей для группового вызова в Skype для бизнеса server Корпоративная голосовая связь и назначить номер группы.
ms.openlocfilehash: 5469e9634e16b855993518092114184a2dca7359
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111835"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Включить групповую подбираемую группу для пользователей и назначить номер группы в Skype для бизнеса

Включить пользователей для группового вызова в Skype для бизнеса server Корпоративная голосовая связь и назначить номер группы.

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