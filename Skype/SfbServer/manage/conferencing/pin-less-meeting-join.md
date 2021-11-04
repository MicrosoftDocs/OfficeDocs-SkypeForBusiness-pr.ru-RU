---
title: Настройка собрания без ПИН-кода в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: Сводка. Сведения о настройке параметра присоединиться к собранию без ПИН-кода в Skype для бизнеса Server.
ms.openlocfilehash: 1f579a3f88553130bec68a1e6e6070c742f8824d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770267"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Настройка собрания без ПИН-кода в Skype для бизнеса Server
 
**Сводка:** Узнайте, как настроить параметр присоединиться к собранию без ПИН-кода в Skype для бизнеса Server.
  
Когда звонивая по телефону пытается присоединиться к собранию, служба конференции автосекретарь (CAA) помещает вызываемого в удерживаемую ручку, которая отличается от службы &#x2014;, если телеведуарь еще не на вызове, а звонивщик не вошел в ПИН-код лидера. Возможность присоединиться к собранию без ПИН-кода позволяет звонителям присоединиться к собранию, не вступая в ПИН-код лидера, даже если они являются первым лицом на вызове. 
  
При настройке этой функции следует помнить следующее:
  
- Применяется только к закрытым собраниям.
    
- Позволяет вызывателям ТСОП находиться на закрытых собраниях без присутствия пользователей с проверкой подлинности.
    
- После изменения параметра он применяется ко всем существующим и новым закрытым собраниям.
    
- Можно включить на сайте организатора или на глобальном уровне.
    
- Параметры, которые могут обойти вестибюль, можно задать для любого из следующих вариантов: 
    
  - **Все, кто из моей Организации с вызывателями, получают непосредственно**
    
  - **Все (без ограничений) с вызывателями получают** непосредственно (это параметр по умолчанию.)
    
- При настройке, чтобы включить pin-код, служба CAA по-прежнему подсказываю пин-код лидера. Пользователи могут присоединиться к собранию вне зависимости от того, вошел ПИН-код или нет. Однако сохранение возможности ввода ПИН-кода лидера позволяет вызываемой в диалоговом окантовке проверить подлинность в качестве лидера и при необходимости управлять собранием.
    
## <a name="configure-pin-less-meeting-join"></a>Настройка присоединиться к собранию без ПИН-кода

Чтобы включить участие в собраниях без ПИН-кода для пользователей, используйте комлет [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) с параметром AllowAnonymousPstnActivation следующим образом:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Например, следующая команда позволяет присоединиться к собранию без ПИН-кода для сайта Redmond:
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

В целях безопасности при включенном включаемом собрании без ПИН-кода может потребоваться запретить анонимным пользователям звонить, обеспечив, чтобы значение ConferencingPolicy было установлено следующим образом:
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Дополнительные сведения см. в дополнительных сведениях [в set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
