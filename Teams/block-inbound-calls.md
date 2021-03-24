---
title: Блокировать входящие звонки в Microsoft Teams
ms.author: v-cichur
author: cichur
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
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: fcf50f96f352cfb72ff3bd700f2118c3cda51dd7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092867"
---
# <a name="block-inbound-calls"></a>Блокировать входящие звонки

Прямая маршрутия и планы звонков телефонной системы поддерживают блокирование входящие вызовы из телефонной сети общего звонков (STN). Эта функция позволяет определить глобальный список шаблонов номеров, чтобы можно было проверить в списке номер звонящую ИД каждого входящих вызовов по ННР в клиенте. Если совпадает, входящий звонок отклоняется.

Эта функция блокировки входящие звонков работает только для входящие звонков из ННР и работает только на уровне клиента. Она недоступна для каждого пользователя.  

>[!NOTE]
> Заблокированные вызыватели могут несколько отличаться в действиях, если они заблокированы. Это зависит от того, как оператор связи заблокированного вызова обрабатывает уведомление о том, что звонок не разрешен для успешного завершения. Примерами могут быть сообщения о том, что звонок не может быть выполнен в качестве набора номера, или просто перетащение звонка.

## <a name="call-blocking-admin-controls-and-information"></a>Средства контроля и сведения о блокировке вызовов администратора

Элементы управления блокировкой номеров администратора предоставляются только с помощью PowerShell. Шаблоны блоков номеров определяются как шаблоны регулярных выражений. Порядок выражений не совпадает — первый шаблон, совпадающий с шаблоном в списке, приводит к блокировке вызова. На то, чтобы шаблон стал активным, может потребоваться до 24 часов, чтобы новый номер или шаблон, который был добавлен или удален в списке заблокированных вызывающих пользователей.

## <a name="call-blocking-powershell-commands"></a>Команды PowerShell, блокирующие вызовы

Шаблоны номеров можно настроить с помощью новых, **get,** **set** и **remove**  - **CsInboundBlockedNumberPattern.** С помощью этих cmdlets можно управлять заданным шаблоном, включая возможность переключения активации этого шаблона.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) возвращает список всех шаблонов заблокированных номеров, добавленных в список клиентов, включая "Имя", "Описание", "Включено" (истина или ложь) и "Шаблон" для каждого из них.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) добавляет шаблон блокировки для номеров в список клиентов.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) удаляет шаблон заблокированных номеров из списка клиентов.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) изменяет один или несколько параметров шаблона заблокированных номеров в списке клиентов.

Просмотром и активацией всей функции блокировки вызовов управляется с помощью управления get **,** **Set**  - **CsTenantBlockingCallingNumbers.**

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) возвращает параметры для глобального списка заблокированных номеров, включая Enabled (True/False). Существует одна глобальная политика клиента, которую нельзя изменить вручную, кроме как включить или отключить функцию.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) позволяет изменять параметры звонков, заблокированных глобальным клиентом, на уровне клиента.

### <a name="examples"></a>Примеры

#### <a name="block-a-number"></a>Блокировка номера

В этом примере **параметры Enabled** и **Description** необязательны.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

При создании шаблона шаблон добавляется в качестве включенного по умолчанию. Описание — это необязательное поле, в поле с более подробными сведениями.

Рекомендуется дать понятное имя, чтобы легко понять, почему был добавлен шаблон. Если нужно просто заблокировать нежелательные номера, можно назвать правило таким же, как шаблону совмеченного числа, и добавить в описание дополнительные сведения.

Совпадения с шаблонами можно использовать с помощью регулярных выражений. Разрешить время репликации перед проверкой и проверкой.

#### <a name="allow-a-number"></a>Разрешить номер

В этом примере параметр **Identity** является required.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Если нужное удостоверение неизвестно, сначала найдите нужный шаблон и заметьте его с помощью **cmdlet Get-CsInboundBlockedNumberPattern.** Затем запустите cmdlet **Remove-CsTenantBlockedNumberPattern** и передайте соответствующее значение удостоверения.

Время репликации перед проверкой и проверкой.

#### <a name="view-all-number-patterns"></a>Просмотр всех шаблонов номеров

Запуск этого cmdlet возвращает список всех заблокированных номеров, которые введены для клиента:

```powershell
Get-CsInboundBlockedNumberPattern
```

Используйте встроенные возможности фильтрации PowerShell для размыки возвращаемого значения по мере необходимости.

## <a name="add-number-exceptions"></a>Добавление числных исключений

Исключения для заблокированных шаблонов номеров можно добавить с помощью **новых,** **get,** **set** и **remove**  - **CsTenantBlockNumberExceptionPattern.**

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) добавляет шаблон исключения для числа в список клиентов. 
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) возвращает список всех шаблонов числных исключений, добавленных в список клиентов.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) изменяет один или несколько параметров на числовой шаблон исключения в списке клиентов.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) удаляет шаблон исключения для номера из списка клиентов.

### <a name="examples"></a>Примеры

#### <a name="add-a-number-exception"></a>Добавление числого исключения

В этом примере создается шаблон числового исключения, который по умолчанию добавляет шаблон как включенный. Параметры **Enabled** **и Description** необязательны.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Просмотр всех числных исключений

В этом примере параметр **Identity** является необязательным. Если параметр **Identity** не задан, этот cmdlet возвращает список всех шаблонов числового исключения, указанных для клиента.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Изменение числого исключения

В этом примере параметр **Identity** является обязательным. С **помощью cmdlet Set-CsTenantBlockedNumberExceptionPattern можно** изменить один или несколько параметров для заданного идентификатора шаблона номера.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Удаление числого исключения

В этом примере параметр **Identity** является required. Этот cmdlet удалит заданный шаблон номера из списка клиентов.  Если нужное удостоверение неизвестно, сначала найдите нужный шаблон и заметьте его с помощью **cmdlet Get-CsInboundBlockedNumberPattern.** Затем запустите cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** и передайте соответствующее значение удостоверения.Разрешить время репликации перед проверкой и проверкой.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Проверка блокировки номера

С помощью **cmdlet Test-CsInboundBlockedNumberPattern** проверьте, заблокировано ли число в клиенте.
 
В этом примере **требуются параметры PhoneNumber** и **Tenant.** Параметр **PhoneNumber должен** быть числовой строкой без дополнительных символов, таких как + или -. В TRPS параметр **Tenant является необязательным.** В результате **параметрNumberBlocked** возвращает значение True, если число заблокировано в клиенте, и False, если оно не заблокировано.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | Верно        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | False        |         |

## <a name="a-note-about-regex"></a>Примечание об Regex

Как говорилось ранее, для блокирования вызывающих вызовов используется Regex. В Интернете доступно несколько инструментов для проверки совпадения с шаблоном регулярного регулярного анализа. Если вы не знакомы с шаблонами Regex, рекомендуем ознакомиться с базовыми задачами в течение некоторого времени. Чтобы получить ожидаемые результаты, используйте инструмент для проверки совпадений с шаблонами перед добавлением новых заблокированных совпадений в клиенте.