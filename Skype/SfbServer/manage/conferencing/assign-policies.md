---
title: Назначение политики конференц-связи в Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Сводка: Узнайте, как назначение политик конференц-связи в Скайп для Business Server.'
ms.openlocfilehash: 44e29842fd11d600aa5a692e98b5ddbb72149ade
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892634"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Назначение политики конференц-связи в Скайп для Business Server
 
**Сводка:** Узнайте, как назначение политик конференц-связи в Скайп для Business Server.
  
Политики конференц-связи можно назначать пользователей с помощью Скайп для консоли Business Server и командлета **Grant-CsConferencingPolicy** .
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Назначение политики конференц-связи с помощью Скайп для консоли Business Server

В примере ниже клиентская политика SalesConferencingPolicy назначается пользователю с идентификатором "Ken Myer".
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

В следующем примере политика конференций FinanceConferencingPolicy назначается всем пользователям, имеющим учетные записи в подразделении Finance (Финансы). Чтобы назначить одну политику всем пользователям в указанном подразделении, сначала вызывается командлет Get-CsUser, который извлекает все учетные записи в этом подразделении. После извлечения учетных записей пользователей они передаются командлету Grant-CsConferencingPolicy, который назначает политику FinanceConferencingPolicy каждому элементу в коллекции.
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Дополнительные сведения, включая полный синтаксис и список параметров можно [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

