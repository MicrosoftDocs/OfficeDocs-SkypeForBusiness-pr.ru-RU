---
title: Включение отправки группового звонка для пользователей и назначение номера группы в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Предоставление пользователям возможности отправки группового звонка в Skype для бизнеса Server Enterprise и назначение номера группы.
ms.openlocfilehash: 14f17d3e217fa9ea44cc81db4d8fa6bf12644894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291583"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Включение отправки группового звонка для пользователей и назначение номера группы в Skype для бизнеса

Предоставление пользователям возможности отправки группового звонка в Skype для бизнеса Server Enterprise и назначение номера группы.

После добавления номеров групп для отправки звонков в таблицу "приостановить Звонок" вы можете использовать средство Сефаутил, чтобы назначить номера групп пользователям и включить для них функцию отправки групповых звонков.

> [!NOTE]
> В гибридном развертывании не назначайте группу отправки группового звонка пользователям, которые находятся в сети. Пользователи, которые подключены к сети, не могут принимать участие в расправке групповых звонков. That is, their calls cannot be answered by other users, and they cannot answer calls to other users.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Назначение номера группы и включение отправки группового звонка для пользователя

1. Войдите в систему компьютера, на котором установлено средство SEFAUtil, с правами администратора.

2. В командной строке выполните следующую команду:

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Например, чтобы назначить пользователю групповой номер 199, введите:

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>См. также

[Disable Group Pickup for Users](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

