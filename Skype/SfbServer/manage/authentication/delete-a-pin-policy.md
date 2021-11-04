---
title: Удаление политики ПИН-кода в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: Сводка. Удалите ПИН-код для телефонных Skype для бизнеса Server.
ms.openlocfilehash: 5cc487f5d8f9e66193446922d51c4c62d94143a9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762527"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Удаление политики ПИН-кода в Skype для бизнеса Server
 
**Сводка:** Удаление ПИН-кода для телефонных контактов пользователя для Skype для бизнеса Server.
  
Чтобы удалить политику персональных идентификационных номеров (политику ПИН-кодов), выполните следующие действия.
  
> [!NOTE]
> Глобальную политику ПИН-кодов удалить нельзя. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Удаление политики ПИН-кода в Skype для бизнеса Server панели управления

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой вы развернули Skype для бизнеса Server.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления.  
    
3. В левой панели навигации последовательно выберите пункты **Security (Безопасность)** и **PIN Policy (Политика ПИН-кодов)**.
    
4. На странице **PIN Policy (Политика ПИН-кодов)** в поле поиска полностью или частично введите имя политики, которую требуется удалить.
    
5. В появившемся списке политик щелкните нужную политику и последовательно выберите в меню пункты **Правка** и **Удалить**.
    
6. Нажмите кнопку **ОК**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик ПИН-кода с помощью Windows PowerShell cmdlets

Политики ПИН-кода можно удалить с помощью Windows PowerShell и Remove-CsPinPolicy. Этот комлет можно выполнить либо из Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в [материале Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Этот процесс в Skype для бизнеса Server.
  
### <a name="to-remove-a-specific-pin-policy"></a>Удаление определенной политики ПИН-кода

- Эта команда удаляет политику ПИН-кода с идентификатором RedmondPinPolicy:
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Удаление всех политик ПИН-кода, примененных к области сайта

- Эта команда удаляет все политики ПИН-кода, настроенные в области действия сайта:
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Удаление всех политик ПИН-кода, позволяющих использовать общие шаблоны

- А эта команда удаляет все политики ПИН-кодов, допускающие использование общих шаблонов:
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Дополнительные сведения см. в разделе Справка для [cmdlet Remove-CsPinPolicy.](/powershell/module/skype/remove-cspinpolicy?view=skype-ps)
