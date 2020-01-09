---
title: Удаление политик конференц-связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Сводка: сведения об удалении политик конференц-связи в Skype для бизнеса Server.'
ms.openlocfilehash: 7cf195e53ec159a8999561c0ddb8461ee1bf0ba6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991874"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Удаление политик конференц-связи в Skype для бизнеса Server
 
**Сводка:** Сведения об удалении политик конференц-связи в Skype для бизнеса Server.
  
Политики конференц-связи можно удалить с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Удаление политик конференц-связи с помощью панели управления Skype для бизнеса Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.
    
4. В списке политик конференц-связи выберите политику узла или пользователя для удаления и щелкните **Изменить**, затем **Удалить**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Удаление политик конференц-связи с помощью командной консоли Skype для бизнеса Server

Политики конференц-связи удаляются с помощью командлета **Remove-CsConferencingPolicy**.
  
Следующая команда удаляет политику конференц-связи с идентификатором RedmondConferencingPolicy:
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

При выполнении следующей команды удаляются все политики конференц-связи, разрешающие внешним пользователям записывать конференцию:
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Дополнительные сведения, в том числе полный синтаксис и список параметров, приведены в разделе [Remove-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
  

