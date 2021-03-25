---
title: Удаление политик conferencing в Skype для бизнеса Server
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: Сводка. Сведения об удалении политик конференциинга в Skype для бизнеса Server.
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119508"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Удаление политик conferencing в Skype для бизнеса Server
 
**Сводка:** Узнайте, как удалить политики conferencing в Skype для бизнеса Server.
  
Политики конференциинга можно удалить с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления skype для бизнес-серверов.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Удаление политик конференций с помощью панели управления Skype для бизнес-серверов

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнес-серверов.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.
    
4. В списке политик конференциинга щелкните веб-сайт или политику пользователей, которые необходимо удалить, нажмите кнопку **Изменить** и нажмите **кнопку Удалить**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Удаление политик conferencing с помощью оболочки управления Skype для бизнес-серверов

Чтобы удалить политики conferencing, используйте **cmdlet Remove-CsConferencingPolicy.**
  
Следующая команда удаляет политику конференц-связи с идентификатором RedmondConferencingPolicy:
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

Следующая команда удаляет все политики конференц-конференций, которые позволяют внешним пользователям записывать конференцию:
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Дополнительные сведения, включая полный синтаксис и список параметров, см. в обзоре [Remove-CsConferencingPolicy.](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)
