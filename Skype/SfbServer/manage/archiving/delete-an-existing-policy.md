---
title: Удаление существующей политики в Скайп архивации для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Сводка: Узнайте, как для удаления политики архивации для Скайп для Business Server.'
ms.openlocfilehash: 0446999923b462311f941b6653157b41000b1f43
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973103"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Удаление существующей политики в Скайп архивации для Business Server

**Сводка:** Узнайте, как для удаления политики архивации для Скайп для Business Server.
  
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