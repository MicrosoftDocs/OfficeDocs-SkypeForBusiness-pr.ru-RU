---
title: Удаление политики ПИН-кодов в Skype для бизнеса Server
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
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: Сводка. Удаление ПИН-кода пользователя для телефонной сети для Skype для бизнеса Server.
ms.openlocfilehash: 6cf93d2ade053ba6e4bdbe7aabf0138206fdff88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828399"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Удаление политики ПИН-кодов в Skype для бизнеса Server
 
**Сводка:** Удаление ПИН-кода для телефонной комференции пользователя для Skype для бизнеса Server.
  
Чтобы удалить политику персональных идентификационных номеров (политику ПИН-кодов), выполните следующие действия.
  
> [!NOTE]
> Глобальную политику ПИН-кодов удалить нельзя. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Удаление политики ПИН-кодов на панели управления Skype для бизнеса Server

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.  
    
3. В левой панели навигации последовательно выберите пункты **Security (Безопасность)** и **PIN Policy (Политика ПИН-кодов)**.
    
4. На странице **PIN Policy (Политика ПИН-кодов)** в поле поиска полностью или частично введите имя политики, которую требуется удалить.
    
5. В появившемся списке политик щелкните нужную политику и последовательно выберите в меню пункты **Правка** и **Удалить**.
    
6. Нажмите кнопку **ОК**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик ПИН-кодов с помощью Windows PowerShell-кодов

Политики ПИН-кодов можно удалить с помощью Windows PowerShell и Remove-CsPinPolicy управления. Вы можете запустить этот Windows PowerShell из оболочки управления Skype для бизнеса Server. Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". В Skype для бизнеса Server этот процесс тот же.
  
### <a name="to-remove-a-specific-pin-policy"></a>Удаление определенной политики ПИН-кодов

- Эта команда удаляет политику ПИН-кода с идентификатором RedmondPinPolicy:
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Удаление всех политик ПИН-кодов, применяемых к области сайта

- Эта команда удаляет все политики ПИН-кода, настроенные в области действия сайта:
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Удаление всех политик ПИН-кодов, которые позволяют использовать общие шаблоны

- А эта команда удаляет все политики ПИН-кодов, допускающие использование общих шаблонов:
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Дополнительные сведения см. в разделе справки по [cmdlet Remove-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)
  

