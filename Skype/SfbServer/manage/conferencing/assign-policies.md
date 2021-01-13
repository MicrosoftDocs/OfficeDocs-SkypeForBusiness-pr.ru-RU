---
title: Назначение политик для видеоконференций в Skype для бизнеса Server
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
description: Сводка. Узнайте, как назначать политики в Skype для бизнеса Server.
ms.openlocfilehash: d13710d2cc4f6edf1cee16cbc9aa77799ceec8a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806479"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Назначение политик для видеоконференций в Skype для бизнеса Server
 
**Сводка:** Learn how to assign conferencing policies in Skype for Business Server.
  
You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Assign conferencing policies by using Skype for Business Server Management Shell

В следующем примере политика SalesConferencingPolicy назначена пользователю с удостоверением "Ken Myer":
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

В следующем примере политика conferencing FinanceConferencingPolicy назначена всем пользователям, у которых есть учетные записи в финансовом подразделении. Чтобы назначить одну политику всем пользователям в указанном подразделении, сначала вызывается командлет Get-CsUser, который извлекает все учетные записи в этом подразделении. После извлечения учетных записей пользователей эта информация передается в Grant-CsConferencingPolicy, который назначает политику FinanceConferencingPolicy каждому пользователю в коллекции:
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Дополнительные сведения, включая полный синтаксис и список параметров, см. в списке [Grant-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)
  

