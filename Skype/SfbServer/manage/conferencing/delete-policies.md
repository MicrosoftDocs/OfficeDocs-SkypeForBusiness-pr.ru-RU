---
title: Удаление политик conferencing в Skype для бизнеса Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: Сводка. Сведения об удалении политик конференциинга в Skype для бизнеса Server.
ms.openlocfilehash: d0447facef0f94b4e2a9c073b23f51438db7080a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391171"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Удаление политик conferencing в Skype для бизнеса Server
 
**Сводка:** Узнайте, как удалить политики conferencing в Skype для бизнеса Server.
  
Политики конференциинга можно удалить с Skype для бизнеса Server панели управления или с помощью Skype для бизнеса Server диспетчерской оболочки.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Удаление политик conferencing с помощью Skype для бизнеса Server панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель Skype для бизнеса Server управления.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.
    
4. В списке политик conferencing щелкните веб-сайт или политику пользователя, которую необходимо удалить, нажмите кнопку **Изменить**, а затем нажмите **кнопку Удалить**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Удаление политик conferencing с помощью Skype для бизнеса Server управленческой оболочки

Чтобы удалить политики conferencing, используйте **cmdlet Remove-CsConferencingPolicy** .
  
Следующая команда удаляет политику конференц-связи с идентификатором RedmondConferencingPolicy:
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

Следующая команда удаляет все политики конференц-конференций, которые позволяют внешним пользователям записывать конференцию:
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Дополнительные сведения, включая полный синтаксис и список параметров, см. в обзоре [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
