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
description: Сводка. Узнайте, как удалить политику архива для Skype для бизнеса Server.
ms.openlocfilehash: 7d71fd9ca03f743cd51e0161cd1a3b437be43cb2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817619"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Удаление существующей политики архива в Skype для бизнеса Server

**Сводка:** Узнайте, как удалить политику архива для Skype для бизнеса Server.
  
Можно удалить политику пользователя или политику сайта, но не глобальную политику. При удалении глобальной политики Skype для бизнеса Server автоматически сбрасывает политику до значений по умолчанию.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Удаление политики с помощью панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. В левой панели навигации щелкните **"Мониторинг** и архивации" и выберите "Политика **архивации".**
    
4. В списке политик архивации щелкните политику пользователей или сайта, которую следует удалить, щелкните **Изменить**, затем **Удалить**.
    
5. Щелкните **Исполнить**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Удаление политики с помощью Windows PowerShell

Вы также можете удалить политики архива с помощью **cmdlet Remove-CsArchivingPolicy.**
  
Например, следующая команда удаляет политику с идентификатором site:Redmond. При удалении политики, настроенной на уровне сайта, пользователи, которыми ранее управляла политика сайта, будут автоматически управляться глобальной политикой архива:
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

Эта команда удаляет все политики архива, применяемые на уровне пользователя:
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Данная команда удаляет все политики архивации, в которых отключена внутренняя архивация:
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Дополнительные сведения см. в разделе справки по [cmdlet Remove-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)
