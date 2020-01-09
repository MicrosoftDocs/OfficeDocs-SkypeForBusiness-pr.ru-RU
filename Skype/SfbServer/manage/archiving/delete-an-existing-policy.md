---
title: Удаление существующей политики архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Сводка: Удаление политики архивации в Skype для бизнеса Server.'
ms.openlocfilehash: c08b76996b3d54e8be07e731faae87dce0470cc1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992366"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Удаление существующей политики архивации в Skype для бизнеса Server

**Сводка:** Сведения о том, как удалить политику архивации в Skype для бизнеса Server.
  
Можно удалить политику пользователей или сайта, но не глобальную политику. Если вы удалите глобальную политику, в Skype для бизнеса Server автоматически восстанавливаются значения по умолчанию для этой политики.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Удаление политику архивации с помощью панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.
    
4. В списке политик архивации щелкните политику пользователей или сайта, которую следует удалить, щелкните **Изменить**, затем **Удалить**.
    
5. Нажмите **Исполнить**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Удаление политики с помощью Windows PowerShell

Политики архивации также можно удалить с помощью командлета **Remove-CsArchivingPolicy**.
  
Например, следующая команда удаляет политику с идентификатором site:Redmond. При удалении политики, настроенной на уровне сайта, пользователи, которые раньше управлялись политикой сайта, автоматически станут управляться глобальной политикой архивирования.
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

Данная команда удаляет все политики архивации, примененные на уровне пользователей:
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Данная команда удаляет все политики архивации, в которых отключена внутренняя архивация:
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксарчивингполици](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .
