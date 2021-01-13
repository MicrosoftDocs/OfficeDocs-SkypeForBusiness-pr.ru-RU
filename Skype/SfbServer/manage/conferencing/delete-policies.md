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
description: Сводка. Узнайте, как удалить политики в Skype для бизнеса Server.
ms.openlocfilehash: eedb0b3676f0cc046e6096dca2cb1ec5ced5d6ec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828199"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Удаление политик conferencing в Skype для бизнеса Server
 
**Сводка:** Learn how to delete conferencing policies in Skype for Business Server.
  
You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Delete conferencing policies by using Skype for Business Server Control Panel

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации щелкните **"Conferencing" (Conferencing),** а затем выберите **"Conferencing Policy" (Политика).**
    
4. В списке политик для conferencing щелкните сайт или политику пользователя, которую необходимо удалить, нажмите кнопку "Изменить", а затем щелкните **"Удалить".**
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Delete conferencing policies by using Skype for Business Server Management Shell

Чтобы удалить политики conferencing, используйте cmdlet **Remove-CsConferencingPolicy.**
  
Следующая команда удаляет политику конференц-связи с идентификатором RedmondConferencingPolicy:
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

Следующая команда удаляет все политики конференц-конференций, которые позволяют внешним пользователям записывать конференцию:
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Дополнительные сведения, включая полный синтаксис и список параметров, см. в [remove-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)
  

