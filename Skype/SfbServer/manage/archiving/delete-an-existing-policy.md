---
title: Удаление существующей политики архивации в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Сводка: Узнайте, как для удаления политики архивации для Скайп для Business Server 2015.'
ms.openlocfilehash: aeb640cc832bffbded4765e5b6cc931a17365215
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server-2015"></a>Удаление существующей политики архивации в Skype для бизнеса Server 2015

**Сводка:** Узнайте, как для удаления политики архивации для Скайп для Business Server 2015.
  
Можно удалить политику пользователей или сайта, но не глобальную политику. Если удалить глобальную политику, Скайп для Business Server автоматически устанавливает политики значения по умолчанию.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Удаление политику архивации с помощью панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server. 
    
3. На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.
    
4. В списке политик архивации щелкните политику пользователей или сайта, которую следует удалить, щелкните **Изменить**, затем **Удалить**.
    
5. Нажмите **Исполнить**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Удаление политики с помощью Windows PowerShell

Политики архивации также можно удалить с помощью командлета **Remove-CsArchivingPolicy**.
  
Например, следующая команда удаляет политику с идентификатором site:Redmond. При удалении политики, настроенной на уровне сайта, пользователи, которые раньше управлялись политикой сайта, автоматически станут управляться глобальной политикой архивирования.
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

Данная команда удаляет все политики архивации, примененные на уровне пользователей:
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Данная команда удаляет все политики архивации, в которых отключена внутренняя архивация:
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Для получения дополнительных сведений см раздел справки по командлет [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .