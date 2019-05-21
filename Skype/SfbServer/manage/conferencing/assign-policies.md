---
title: Назначение политик конференц-связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Сводка: Научитесь назначать политики конференций в Skype для бизнеса Server.'
ms.openlocfilehash: acd74262b51000a3f4af5668fb3c9271a8c0978d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289029"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Назначение политик конференц-связи в Skype для бизнеса Server
 
**Сводка:** Сведения о назначении политик конференц-связи в Skype для бизнеса Server.
  
Вы можете назначать политики Конференции пользователям с помощью командной консоли Skype для бизнеса Server и командлета **Grant-ксконференЦингполици** .
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Назначение политик конференц-связи с помощью командной консоли Skype для бизнеса Server

В примере ниже клиентская политика SalesConferencingPolicy назначается пользователю с идентификатором "Ken Myer".
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

В следующем примере политика конференций FinanceConferencingPolicy назначается всем пользователям, имеющим учетные записи в подразделении Finance (Финансы). Чтобы назначить одну политику всем пользователям в указанном подразделении, сначала вызывается командлет Get-CsUser, который извлекает все учетные записи в этом подразделении. После извлечения учетных записей пользователей они передаются командлету Grant-CsConferencingPolicy, который назначает политику FinanceConferencingPolicy каждому элементу в коллекции.
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Дополнительные сведения, в том числе полный синтаксис и список параметров, приведены в разделе [Grant-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

