---
title: Удаление политики ПИН-кода в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Сводка: удаление ПИН-кода конференц-связи с телефонным подключением пользователя для Skype для бизнеса Server.'
ms.openlocfilehash: cfdb14ad8107c8d3450e6d50245831f723ca1153
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992326"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Удаление политики ПИН-кода в Skype для бизнеса Server
 
**Сводка:** Удаление ПИН-кода конференц-связи с телефонным подключением пользователя для Skype для бизнеса Server.
  
Чтобы удалить политику персональных идентификационных номеров (политику ПИН-кодов), выполните следующие действия.
  
> [!NOTE]
> Глобальную политику ПИН-кодов удалить нельзя. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Удаление политики ПИН-кода на панели управления Skype для бизнеса Server

1.  Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.  
    
3. В левой панели навигации последовательно выберите пункты **Безопасность** и **Политика ПИН-кода**.
    
4. На странице **Политика ПИН-кода** в поле поиска полностью или частично введите имя политики, которую требуется удалить.
    
5. В списке политик выберите необходимую политику, щелкните **Правка**, затем выберите **Удалить**.
    
6. Нажмите **ОК**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик закрепления с помощью командлетов Windows PowerShell

Вы можете удалять политики закрепления с помощью Windows PowerShell и командлета Remove-Кспинполици. Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876). Этот процесс одинаков в Skype для бизнеса Server.
  
### <a name="to-remove-a-specific-pin-policy"></a>Удаление определенной политики ПИН-кода

- Эта команда удаляет политику ПИН-кода с идентификатором RedmondPinPolicy:
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Порядок применения всех политик ПИН-кода, применяемых на уровне сайта

- Эта команда удаляет все политики ПИН-кода, настроенные в области действия сайта:
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Удаление всех политик ПИН-кодов, позволяющих использовать общие шаблоны

- А эта команда удаляет все политики ПИН-кодов, допускающие использование общих шаблонов:
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Дополнительные сведения можно найти в разделе справки по командлету [Remove-кспинполици](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .
  

