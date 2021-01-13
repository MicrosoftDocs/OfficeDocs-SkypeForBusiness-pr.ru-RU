---
title: Enable Group Call Pickup for users and assign a group number in Skype for Business
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
description: Включить для пользователей групповой выбор звонков в Skype для бизнеса Server Корпоративная голосовая связь и назначить номер группы.
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830969"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Enable Group Call Pickup for users and assign a group number in Skype for Business

Включить для пользователей групповой выбор звонков в Skype для бизнеса Server Корпоративная голосовая связь и назначить номер группы.

После того как вы добавите номера группы раздатки вызовов в таблицу орбит парковки вызовов, используйте средство SEFAUtil, чтобы назначить номера групп пользователям и включить для них групповой звонок.

> [!NOTE]
> В гибридном развертывании не назначать группу группового вызова пользователям, которые размещены в Интернете. Пользователи, которые находятся в Сети, не могут участвовать в групповом звоноке. То есть другие пользователи не могут отвечать на их вызовы, а они не могут отвечать на вызовы других пользователей.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Назначение номера группы и включить групповой звонок для пользователя

1. Войдите на компьютер, на котором установлено средство SEFAUtil, с правами администратора.

2. В командной строке выполните следующую команду:

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Например, чтобы назначить пользователю номер группы 199:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>См. также

[Отключение группового разметки для пользователей](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

