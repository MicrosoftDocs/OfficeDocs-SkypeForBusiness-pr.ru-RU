---
title: Удаление существующей политики архива в Skype для бизнеса Server
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: Сводка. Сведения об удалении политики архива для Skype для бизнеса Server.
ms.openlocfilehash: bee5cb3d48c079f0c918e15c607c163f3f67aea9e1dfed92309700b1795c699d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320251"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Удаление существующей политики архива в Skype для бизнеса Server

**Сводка:** Узнайте, как удалить политику архива для Skype для бизнеса Server.
  
Можно удалить политику пользователя или политику сайта, но не глобальную политику. Если удалить глобальную политику, Skype для бизнеса Server автоматически сбрасывает политику к значениям по умолчанию.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Удаление политики с помощью панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 
    
3. В левой панели навигации щелкните **Мониторинг** и архивации, а затем нажмите кнопку **Политика архивации**.
    
4. В списке политик архивации щелкните политику пользователей или сайта, которую следует удалить, щелкните **Изменить**, затем **Удалить**.
    
5. Щелкните **Исполнить**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Удаление политики с помощью Windows PowerShell

Вы также можете удалить политики архива с помощью **cmdlet Remove-CsArchivingPolicy.**
  
Например, следующая команда удаляет политику с помощью сайта Identity:Redmond. При удалении политики, настроенной на уровне сайта, пользователи, ранее управляемые политикой сайта, будут автоматически управляться глобальной политикой архива:
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

Эта команда удаляет все политики архива, применяемые к уровню каждого пользователя:
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Данная команда удаляет все политики архивации, в которых отключена внутренняя архивация:
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Дополнительные сведения см. в разделе Справка для [cmdlet Remove-CsArchivingPolicy.](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)