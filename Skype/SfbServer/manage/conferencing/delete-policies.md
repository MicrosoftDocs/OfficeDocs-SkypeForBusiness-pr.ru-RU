---
title: Удаление политик конференц-связи в Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Сводка: Узнайте, как для удаления политики конференц-связи в Скайп для Business Server.'
ms.openlocfilehash: 404e981af46b29bd95b36ca402c9f691e34737a5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222809"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Удаление политик конференц-связи в Скайп для Business Server
 
**Сводка:** Узнайте, как для удаления политики конференц-связи в Скайп для Business Server.
  
Политики конференц-связи можно удалить с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Удаление политик конференц-связи с помощью Скайп для панели управления Business Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте Скайп для панели управления Business Server.
    
3. На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.
    
4. В списке политик конференц-связи выберите политику узла или пользователя для удаления и щелкните **Изменить**, затем **Удалить**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Удаление политик конференц-связи с помощью Скайп для консоли Business Server

Политики конференц-связи удаляются с помощью командлета **Remove-CsConferencingPolicy**.
  
Следующая команда удаляет политику конференц-связи с идентификатором RedmondConferencingPolicy:
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

При выполнении следующей команды удаляются все политики конференц-связи, разрешающие внешним пользователям записывать конференцию:
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Дополнительные сведения, включая полный синтаксис и список параметров [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)см.
  

