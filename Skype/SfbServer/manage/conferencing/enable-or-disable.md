---
title: Включение и отключение конференц-связи в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Сводка: Узнайте, как использовать панель управления или командной консоли для включения или отключения конференц-связи в Скайп для Business Server.'
ms.openlocfilehash: 1392c67e2b432a6acc9bca805367083d311fd7d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919803"
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
  

