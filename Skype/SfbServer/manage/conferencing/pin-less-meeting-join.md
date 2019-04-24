---
title: Настройка присоединения к собранию без ПИН-кода в Skype для бизнеса Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Сводка: Сведения о настройке ПИН-кода меньше собраний вариант присоединиться в Скайп для Business Server.'
ms.openlocfilehash: 4ea20f68b123f6593c5a98fc82dbca62f90f31b1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198269"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Настройка присоединения к собранию без ПИН-кода в Skype для бизнеса Server
 
**Сводка:** Сведения о настройке ПИН-кода меньше собраний вариант присоединиться в Скайп для Business Server.
  
При попытке присоединиться к собранию вызывающего-связь, служба Attendant автоматически конференции (CAA) помещает вызывающего абонента в перо удержания, отличается от & зал ожидания #x 2014 г.; Если выступающим еще не на вызов и вызывающего абонента-связь не вошел лидера ПИН-кода. ПИН-код меньше вариант присоединения к собранию позволяет присоединиться к собранию без ввода ПИН-код ведущего даже в том случае, если они находятся на первого лица на вызов вызывающей-связь. 
  
При настройке этого компонента следует учитывать следующие сведения.
  
- Применяется только к частным собраниям.
    
- Позволяет вызывающим абонентам ТСОП оставаться в частых собраниях при отсутствии прошедших проверку пользователей.
    
- Измененные настройки применяются ко всем существующим и новым частным собраниям.
    
- Можно включить либо на сайте организатора, либо на глобальном уровне.
    
- Можно установить следующие варианты обхода зала ожидания: 
    
  - **Все вызывающие абоненты из моей организации попадают напрямую**
    
  - **Все вызывающие абоненты попадают напрямую** (Эта настройка используется по умолчанию.)
    
- Если присоединение без ПИН-кода включено, служба CAA по-прежнему запрашивает ПИН-код ведущего. Пользователи могут присоединиться к собранию независимо от того, введен ли ПИН-код. Тем не менее сохраняя возможность вводить ПИН-код ведущего позволяет телефонные вызывающей стороне проверку в качестве лидера и управление ими собрания, если это необходимо.
    
## <a name="configure-pin-less-meeting-join"></a>Настройка присоединения к собранию без ПИН-кода

Чтобы включить присоединения к собранию без использования ПИН-кода для пользователей, используйте командлет [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) с параметром AllowAnonymousPstnActivation следующим образом:
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Например, следующая команда включает присоединение к собранию без ПИН-кода для сайта Redmond:
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Когда присоединение к собранию без ПИН-кода включено, в целях безопасности можно запретить анонимным пользователям присоединяться к собранию обратным звонком. Для этого политику конференц-связи следует настроить следующим образом.
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Для получения дополнительных сведений см [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

