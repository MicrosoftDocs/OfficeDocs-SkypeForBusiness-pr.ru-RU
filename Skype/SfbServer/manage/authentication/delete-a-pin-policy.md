---
title: Удаление политики ПИН-кодов в Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Сводка: Удаление пользователя телефонных конференций ПИН-кода для Скайп для Business Server 2015.'
ms.openlocfilehash: b64a4509105214358549f320cf8885d6386986f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="delete-a-pin-policy-in-skype-for-business-server-2015"></a>Удаление политики ПИН-кодов в Skype для бизнеса Server 2015
 
**Сводка:** Удаление пользователя телефонных конференций ПИН-кода для Скайп для Business Server 2015.
  
Чтобы удалить политику персональных идентификационных номеров (политику ПИН-кодов), выполните следующие действия.
  
> [!NOTE]
> Глобальную политику ПИН-кодов удалить нельзя. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Удаление политики ПИН-код в Скайп для панели управления Business Server

1.  Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2015.
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.  
    
3. В левой панели навигации последовательно выберите пункты **Безопасность** и **Политика ПИН-кода**.
    
4. На странице **Политика ПИН-кода** в поле поиска полностью или частично введите имя политики, которую требуется удалить.
    
5. В списке политик выберите необходимую политику, щелкните **Правка**, затем выберите **Удалить**.
    
6. Нажмите **ОК**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик ПИН-кода с помощью командлетов Windows PowerShell

Политики ПИН-код можно удалить с помощью Windows PowerShell и командлет Remove-CsPinPolicy. Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Процесс одинаков в Скайп для Business Server.
  
### <a name="to-remove-a-specific-pin-policy"></a>Удаление определенной политики ПИН-кода

- Эта команда удаляет политику ПИН-кода с идентификатором RedmondPinPolicy:
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Порядок применения всех политик ПИН-кода, применяемых на уровне сайта

- Эта команда удаляет все политики ПИН-кода, настроенные в области действия сайта:
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Удаление всех политик ПИН-кодов, позволяющих использовать общие шаблоны

- А эта команда удаляет все политики ПИН-кодов, допускающие использование общих шаблонов:
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Для получения дополнительных сведений см раздел справки для командлета [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .
  

