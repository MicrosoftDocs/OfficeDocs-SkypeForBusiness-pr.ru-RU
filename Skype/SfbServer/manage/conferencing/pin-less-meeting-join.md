---
title: Настройка присоединить к собранию без ПИН-кода в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: Сводка. Узнайте, как настроить параметр присоединить к собранию без ПИН-кода в Skype для бизнеса Server.
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827989"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Настройка присоединить к собранию без ПИН-кода в Skype для бизнеса Server
 
**Сводка:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.
  
Когда звоня из телефонного номера пытается присоединиться к собранию, служба conference автосекретарь (CAA) помещает вызываемого в перо для удержания, которое отличается от номера "Зал залов" &#x2014; если он еще не звонит, а вызываемая служба не введет ПИН-код руководителя. Параметр присоединиться к собранию без ПИН-кода позволяет звонятелям с телефонным звонякой присоединяться к собранию без ввода ПИН-кода руководителя, даже если они являются первым звоня лицом. 
  
При настройке этой функции следует иметь в виду следующее:
  
- Применяется только к частным собраниям.
    
- Позволяет звонятелям ТСОП оставаться на частных собраниях без присутствия пользователей, подлинность в которые прошла.
    
- После изменения параметра он применяется ко всем существующим и новым частным собраниям.
    
- Может быть включен на сайте организатора или на глобальном уровне.
    
- Параметры для тех, кто может обходить "lobby", можно настроить для одного из следующих вариантов: 
    
  - **Все, кто из моей организации с вызывателями, получают прямой звонок**
    
  - **Все (без ограничений) с вызывателями получают** прямой ввод (это параметр по умолчанию).)
    
- Если для этого настроено участие без ПИН-кода, служба CAA по-прежнему запросит ПИН-код руководителя. Пользователи могут присоединяться к собранию независимо от того, введен ли ПИН-код. Тем не менее, сохранение возможности ввода ПИН-кода руководителя позволяет вызываемой по телефонной телефонии проходить проверку подлинности в качестве руководителя и при необходимости управлять собранием.
    
## <a name="configure-pin-less-meeting-join"></a>Настройка присоединить к собранию без ПИН-кода

Чтобы разрешить пользователям присоединяться к собранию без ПИН-кода, используйте с параметром AllowAnonymousPstnActivation с помощью параметра [Set-CsDialInConferencingConfiguration:](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Например, следующая команда позволяет присоединяться к собранию без ПИН-кода для сайта Redmond:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

В целях безопасности, если включено присоединяние к собранию без ПИН-кода, может потребоваться запретить анонимным пользователям набор номера, убедившись, что для conferencingPolicy установлено значение:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Дополнительные сведения [см. в подстроке Set-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
  

