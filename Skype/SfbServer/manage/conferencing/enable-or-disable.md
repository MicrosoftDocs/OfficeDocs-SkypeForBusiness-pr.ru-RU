---
title: Включение и отключение конференц-связи в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Сводка: Узнайте, как использовать панель управления или командной консоли для включения или отключения конференц-связи в Скайп для Business Server.'
ms.openlocfilehash: 47393140e41277aef3ec137ee3f1c6a96fa9efca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983863"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Включение и отключение конференц-связи в Скайп для Business Server
 
**Сводка:** Узнайте, как использовать панель управления или командной консоли для включения или отключения конференц-связи в Скайп для Business Server.
  
Конференц-связь можно включить с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Включение или отключение конференц-связи с помощью Скайп для панели управления Business Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте Скайп для панели управления Business Server.
    
3. На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.
    
4. В списке политик конференции выберите политику, для которой следует включить конференцию с подключением по телефону, щелкните **Изменить**, затем **Показать подробности**. 
    
5. Чтобы разрешить пользователям присоединяться к собраниям по телефону, установите флажок **Разрешить конференц-связь с подключением к ТСОП**. По умолчанию пользователи могут присоединяться к собраниям по телефону через телефонную сеть общего пользования (ТСОП).
    
6. Нажмите **Исполнить**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Включение или отключение конференц-связи с помощью Скайп для консоли Business Server

Для включения или отключения конференц-связи с телефонным подключением используется командлет **Set-CsConferencingPolicy** с параметром EnableDialInConferencing (см. ниже).
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Для получения дополнительных сведений см [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

