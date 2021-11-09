---
title: Блокировать входящие звонки в Microsoft Teams
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: d1b5b19189ea301eab5d2c06dfa85be7d4ddb6eb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827392"
---
# <a name="block-inbound-calls"></a>Блокировать входящие звонки

Планы звонков Майкрософт, прямая маршрутия и оператор Подключение блокируют входящие звонки из телефонной сети общего звонков (ПСОП). Эта функция позволяет администратору определить список шаблонов номеров на глобальном уровне клиента, чтобы в списке на совпадение можно было проверить ИД звонящая для каждого входящих вызовов по ДНР в клиенте. Если совпадение выполнено, входящий звонок отклоняется.

Эта функция блокировки входящие звонков работает только для входящие звонков, исходящие из ПСПС, и работает только на глобальном уровне клиента. Отдельные Teams пользователи не могут управлять этим списком. Клиент Teams позволяет отдельным пользователям блокировать звонки по ННР. Сведения о том, как конечные пользователи могут блокировать вызовы, см. в [Teams.](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

>[!NOTE]
> Заблокированные вызыватели могут немного отличаться в действиях, если они заблокированы. Поведение зависит от того, как оператор связи заблокированного вызываемого звонка обрабатывает уведомление о том, что звонок не разрешен для успешного завершения. Примерами может быть сообщение о том, что звонок не может быть выполнен по телефону или просто перетассыв вызов.

## <a name="call-blocking-admin-controls-and-information"></a>Блокировка вызовов элементов управления и сведений администратора

Элементы управления блокировкой номеров предоставляются только с помощью PowerShell. Шаблоны блоков числов определяются как шаблоны регулярных выражений. Порядок выражений не имеет важного отношения— первый шаблон, совпадающий с шаблоном в списке, приводит к блокированию звонка. На то, чтобы шаблон стал активным, может потребоваться до 24 часов, чтобы добавить или удалить его из списка заблокированных вызывающих пользователей.

## <a name="call-blocking-powershell-commands"></a>Команды PowerShell, блокирующие вызовы

Шаблоны номеров можно настроить с помощью **нью-,** **Get-**, **Set-** и **Remove-CsInboundBlockedNumberPattern.** Вы можете управлять заданным шаблоном с помощью этих cmdlets, включая возможность переключения активации заданного шаблона.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) возвращает список всех шаблонов заблокированных номеров, добавленных в список клиентов, включая Name, Description, Enabled (True/False) и Pattern для каждого из них.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) добавляет в список клиентов шаблон заблокированных номеров.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) удаляет шаблон заблокированных номеров из списка клиентов.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) изменяет один или несколько параметров шаблона заблокированных номеров в списке клиентов.

Просмотром и активацией всей функции блокирования зовов управляется с помощью элементов **Get-** и **Set-CsTenantBlockingCallingNumbers.**

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) возвращает шаблоны входящий номер блока и параметры исключаемого числа для глобального списка блокировок. Этот cmdlet также возвращает, включена ли блокировка (True или False). Существует одна глобальная политика клиента, которую нельзя изменить вручную, кроме как включить или отключить эту функцию.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) позволяет изменять глобальные звонки, заблокированные клиентом, на уровне клиента.

### <a name="examples"></a>Примеры

#### <a name="block-a-number"></a>Блокировка номера

В следующем примере администратор клиента хочет заблокировать все звонки из диапазона 1 (312) 555-0000-1 (312) 555-9999. Шаблон чисел создается таким образом, что совпадают как числа в диапазоне с префиксом +, так и числа в диапазоне без префикса +. Вам не нужно включать символы – и () в номера телефонов, так как система разместит их перед соответствием.  Чтобы включить шаблон номера, для **параметра Enabled** задано true. Чтобы отключить этот шаблон номера, задан параметр False.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

В следующем примере администратору клиента нужно заблокировать все звонки с номера 1 (412) 555-1234. Чтобы включить шаблон номера, для **параметра Enabled** задано true.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

При создании шаблона шаблон добавляется как включенный по умолчанию. Описание — это необязательное поле для предоставления дополнительных сведений.

Мы рекомендуем дать понятное имя, чтобы легко понять, почему был добавлен шаблон. Если вы просто блокируете номера спама, можно назвать правило так же, как шаблон чисел и добавить дополнительные сведения в описание.

Совпадения с шаблонами можно использовать с помощью регулярных выражений (Regex). Дополнительные сведения см. [в теме Использование Regex](#using-regex).

Разрешить время репликации перед проверкой и проверкой. 

#### <a name="allow-a-number"></a>Разрешить номер

Вы можете разрешить звонок на номер, удалив шаблон заблокированного номера. В следующем примере администратор клиента хочет разрешить 1 (412) 555-1234 повторно звонить.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
Если удостоверение неизвестно, сначала найдите нужный шаблон и обратите внимание на его идентификатор с помощью **cmdlet Get-CsInboundBlockedNumberPattern.** Затем запустите **cmdlet Remove-CsInboundBlockedNumberPattern** и передайте соответствующее значение удостоверения.

Разрешить время репликации перед проверкой и проверкой.

#### <a name="view-all-number-patterns"></a>Просмотр всех шаблонов номеров

При запуске этого cmdlet возвращается список всех заблокированных номеров, которые введены для клиента:

```powershell
Get-CsInboundBlockedNumberPattern
```

Используйте встроенные возможности фильтрации PowerShell, чтобы при необходимости проавнозить возвращаемую величину.

## <a name="add-number-exceptions"></a>Добавление числных исключений

Вы можете добавить исключения для заблокированных шаблонов номеров с помощью **нью-,** **get-,** **Set-** и **Remove-CsInboundExemptNumberPattern.**

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) добавляет шаблон исключения числа в список клиентов. 
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) возвращает список всех шаблонов числов исключений, добавленных в список клиентов.
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) изменяет один или несколько параметров в шаблон числового исключения в списке клиентов.
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) удаляет шаблон исключения числа из списка клиентов.

### <a name="examples"></a>Примеры

#### <a name="add-a-number-exception"></a>Добавление числого исключения

В следующем примере администратор клиента хочет разрешить звонки на клиент по номерам 1 (312) 555-8882 и 1 (312) 555-8883, даже если эти два номера телефонов находятся в диапазоне, заблокированном в примере выше. Чтобы включить эту функцию, создается новый шаблон исключения для числа:

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Чтобы включить шаблон номера, для **параметра Enabled** задано true. Чтобы отключить этот шаблон номера, задан параметр False.


#### <a name="view-all-number-exceptions"></a>Просмотр всех числных исключений

В этом примере параметр **Identity** необязателен. Если параметр **Identity** не указан, этот cmdlet возвращает список всех шаблонов числового исключения, указанных для клиента.
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a>Изменение числого исключения

С **помощью cmdlet Set-CsInboundExemptNumberPattern** можно изменить один или несколько параметров для заданного числового шаблона. В этом примере требуется **параметр Identity.**
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>Удаление числого исключения

При **этом из списка** клиента удаляется заданный шаблон номера. В этом примере требуется **параметр Identity.** 

Если удостоверение неизвестно, сначала найдите нужный шаблон и обратите внимание на его идентификатор с помощью **cmdlet Get-CsInboundExemptNumberPattern.** Затем запустите **cmdlet Remove-CsInboundExemptNumberPattern** и передайте соответствующее значение удостоверения.Разрешить время репликации перед проверкой и проверкой.  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>Проверка того, заблокировано ли число

Чтобы проверить, заблокировано ли число в клиенте, используйте для этого **cmdlet Test-CsInboundBlockedNumberPattern.**
 
Параметр **PhoneNumber** является required и должен быть числовой строкой без дополнительных символов, таких как +, - или (). Итоговые **параметры IsNumberBlocked** возвращают значение True, если число заблокировано в клиенте. параметр возвращает false, если он не заблокирован.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>Примеры

В этих примерах видно, что номер телефона 1 (312) 555-8884 заблокирован так, как должен быть из-за того, что он находится в заблокированном диапазоне выше, а номер телефона 1 (312) 555-8883 можно звонить на основе созданного выше освобождения.

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

## <a name="using-regex"></a>Использование Regex

Соответствие шаблона для блокирования вызывающих людей делается с помощью Regex. В Интернете доступно несколько инструментов для проверки совпадения с шаблоном Regex. Если вы не знакомы с шаблонами Regex, советуем ознакомиться с основами в течение некоторого времени. Чтобы убедиться в том, что вы получаете ожидаемые результаты, используйте инструмент для проверки совпадений с шаблоном перед добавлением новых заблокированных номеров в клиент.