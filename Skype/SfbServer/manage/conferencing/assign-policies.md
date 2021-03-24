---
title: Назначение политик conferencing в Skype для бизнеса Server
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
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: Сводка. Сведения о назначении политик конференций в Skype для бизнеса Server.
ms.openlocfilehash: 61082a9189b085c852e7593207fc86dcc6509139
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099165"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Назначение политик conferencing в Skype для бизнеса Server
 
**Сводка:** Узнайте, как назначить политики конференциинга в Skype для бизнеса Server.
  
Политики конференции можно назначить пользователям с помощью команды Управления Skype для бизнес-серверов и команды **Grant-CsConferencingPolicy.**
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Назначение политик conferencing с помощью оболочки управления Skype для бизнес-серверов

В следующем примере политика SalesConferencingPolicy назначена пользователю с удостоверением "Ken Myer":
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

В следующем примере политика conferencing FinanceConferencingPolicy назначена всем пользователям, у которых есть учетные записи в организационном подразделении Finance. Чтобы назначить одну политику всем пользователям в указанном подразделении, сначала вызывается командлет Get-CsUser, который извлекает все учетные записи в этом подразделении. После получения учетных записей пользователей эта информация передается в Grant-CsConferencingPolicy, который назначает политику FinanceConferencingPolicy каждому пользователю в коллекции:
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Дополнительные сведения, включая полный синтаксис и список параметров, см. в [обзоре Grant-CsConferencingPolicy.](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)
