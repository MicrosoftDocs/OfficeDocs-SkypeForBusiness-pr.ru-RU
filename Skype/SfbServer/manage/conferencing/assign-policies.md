---
title: Назначение политик конференциинга в Skype для бизнеса Server
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
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: Сводка. Узнайте, как назначить политики конференций в Skype для бизнеса Server.
ms.openlocfilehash: e63e59f806bcef14a50f75924527aa0f8733799b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767837"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Назначение политик конференциинга в Skype для бизнеса Server
 
**Сводка:** Узнайте, как назначить политики конференциинга в Skype для бизнеса Server.
  
Политики конференции можно назначить пользователям с помощью Skype для бизнеса Server и команды **Grant-CsConferencingPolicy.**
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Назначение политик conferencing с помощью Skype для бизнеса Server управленческой оболочки

В следующем примере политика SalesConferencingPolicy назначена пользователю с удостоверением "Ken Myer":
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

В следующем примере политика conferencing FinanceConferencingPolicy назначена всем пользователям, у которых есть учетные записи в организационном подразделении Finance. Чтобы назначить одну политику всем пользователям в указанном подразделении, сначала вызывается командлет Get-CsUser, который извлекает все учетные записи в этом подразделении. После получения учетных записей пользователей эта информация передается в Grant-CsConferencingPolicy, который назначает политику FinanceConferencingPolicy каждому пользователю в коллекции:
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Дополнительные сведения, включая полный синтаксис и список параметров, см. в [обзоре Grant-CsConferencingPolicy.](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)
