---
title: Блокировка входящих вызовов в Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.custom: ''
description: Узнайте, как использовать PowerShell для управления блокировкой входящих вызовов.
ms.openlocfilehash: 217a4fe6770d916e9013acf7f90ebf6a5556b837
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789604"
---
# <a name="block-inbound-calls"></a>Блокировка входящих вызовов

Планы звонков Майкрософт, прямая маршрутизация и подключение операторов поддерживают блокировку входящих вызовов из телефонной сети общего пользования (ТСОП). Эта функция позволяет администратору определить список шаблонов номеров на глобальном уровне клиента, чтобы идентификатор вызывающего абонента каждого входящего вызова ТСОП к клиенту можно было проверить в списке на соответствие. Если сопоставление выполнено, входящий вызов отклоняется.

Эта функция блокировки входящих вызовов работает только для входящих вызовов, исходящих из ТСОП, и работает только на глобальном уровне клиента. Отдельные пользователи Teams не могут управлять этим списком. Клиент Teams позволяет отдельным пользователям блокировать вызовы ТСОП. Сведения о том, как конечные пользователи могут реализовать блокировку вызовов, см. в разделе "Управление параметрами параметров [зова в Teams"](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).

> [!NOTE]
> Заблокированные вызывающие объекты могут немного отличаться в поведении, если они заблокированы. Поведение зависит от того, как оператор заблокированного абонента обрабатывает уведомление о том, что звонок не может быть успешно завершен. Примеры могут включать в себя сообщение оператора о том, что звонок не может быть завершен как на телефоне, или просто удалить звонок.

## <a name="call-blocking-admin-controls-and-information"></a>Блокировка вызовов элементов управления и сведений администратора

Администратор для блокирующих номеров предоставляются только с помощью PowerShell. Шаблоны числового блока определяются как шаблоны регулярных выражений. Порядок выражений не имеет значения— первый шаблон, сопоставленный в списке, приводит к блокировке вызова. Новый номер или шаблон, добавленный или удаленный в списке заблокированных вызывающих абонентов, может занять до 24 часов, чтобы шаблон стал активным.

## <a name="call-blocking-powershell-commands"></a>Команды PowerShell, блокирующие вызовы

Шаблонами чина можно управлять с помощью командлетов **New-**, **Get-**, **Set-и** **Remove-CsInboundBlockedNumberPattern** . Вы можете управлять заданным шаблоном с помощью этих командлетов, включая возможность переключать активацию заданного шаблона.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) возвращает список всех заблокированных шаблонов номеров, добавленных в список клиентов, включая "Имя", "Описание", "Включено" (true/False) и "Шаблон" для каждого из них.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) добавляет в список клиентов шаблон заблокированных номеров.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) удаляет из списка клиентов шаблон заблокированных номеров.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) изменяет один или несколько параметров шаблона заблокированного числа в списке клиентов.

Просмотр и активация всей функции блокировки вызовов осуществляется с помощью командлетов **Get-** и **Set-CsTenantBlockingCallingNumbers** .

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) возвращает входящие шаблоны номеров блоков и параметры шаблонов исключенных номеров для глобального списка заблокированных номеров. Этот командлет также возвращает значение, указывающее, включена ли блокировка (True или False). Существует одна глобальная политика клиента, которую нельзя изменить вручную, кроме включения или отключения функции.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) позволяет включать и отключать вызовы, заблокированные глобальным клиентом, на уровне клиента.

### <a name="examples"></a>Примеры

#### <a name="block-a-number"></a>Блокировать число

В следующем примере администратор клиента хочет заблокировать все вызовы, поступающие из диапазона от 1 (312) 555-0000 до 1 (312) 555-9999. Шаблон чисел создается таким образом, чтобы совпадали как числа в диапазоне с префиксом +, так и числа в диапазоне без префикса +. Вам не нужно включать символы и () в номера телефонов, так как система отключит эти символы перед сопоставлением.  Чтобы включить числовую схему, для **параметра Enabled** задано значение True. Чтобы отключить этот шаблон числа, задайте для параметра значение False.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

В следующем примере администратор клиента хочет заблокировать все вызовы, поступающие с номера 1 (412) 555-1234. Чтобы включить числовую схему, для **параметра Enabled** задано значение True.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

При создании нового шаблона шаблон добавляется как включенный по умолчанию. Описание является необязательным полем для предоставления дополнительных сведений.

Рекомендуется указать понятное имя, чтобы легко понять, почему был добавлен шаблон. В случае простой блокировки номеров нежелательной почты рассмотрите возможность именования правила так же, как и сопоставленный шаблон чисел, и добавьте дополнительные сведения в описание по мере необходимости.

Шаблоны сопоставляется с помощью регулярных выражений (регулярных выражений). Дополнительные сведения см. в [разделе "Использование регулярных выражений"](#using-regex).

Утвердите время репликации перед тестированием и проверкой.

#### <a name="allow-a-number"></a>Разрешить число

Вы можете разрешить вызов номера, удалив шаблон заблокированного номера. В следующем примере администратор клиента хочет разрешить 1 (412) 555-1234 для повторного вызова.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```

Если удостоверение неизвестно, сначала найдите нужный шаблон и запишите удостоверение с помощью командлета **Get-CsInboundBlockedNumberPattern** . Затем выполните **командлет Remove-CsInboundBlockedNumberPattern** и передайте соответствующее значение удостоверения.

Утвердите время репликации перед тестированием и проверкой.

#### <a name="view-all-number-patterns"></a>Просмотр всех шаблонов чина

При выполнении этого командлета возвращается список всех заблокированных номеров, введенных для клиента:

```powershell
Get-CsInboundBlockedNumberPattern
```

Используйте встроенные возможности фильтрации PowerShell для анализа возвращаемых значений по мере необходимости.

## <a name="add-number-exceptions"></a>Добавление исключений числа

Исключения в шаблоны заблокированных чичек можно добавить с помощью командлетов **New-**, **Get-**, **Set-и** **Remove-CsInboundExemptNumberPattern** .

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) добавляет шаблон исключения числа в список клиентов.
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) возвращает список всех шаблонов числового исключения, добавленных в список клиентов.
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) изменяет один или несколько параметров на числовой шаблон исключения в списке клиентов.
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) удаляет шаблон исключения числа из списка клиентов.

### <a name="examples"></a>Примеры

#### <a name="add-a-number-exception"></a>Добавление числовое исключение

В следующем примере администратор клиента хочет разрешить телефонные номера 1 (312) 555-8882 и 1 (312) 555-8883, чтобы совершать звонки клиенту, даже если эти два номера телефонов находятся в диапазоне, который был заблокирован в приведенном выше примере. Чтобы включить эту функцию, создается новый шаблон исключения числа следующим образом:

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

Чтобы включить числовую схему, для **параметра Enabled** задано значение True. Чтобы отключить этот шаблон числа, задайте для параметра значение False.

#### <a name="view-all-number-exceptions"></a>Просмотр всех числов исключений

В этом примере параметр **Identity** является необязательным. Если параметр **Identity** не указан, этот командлет возвращает список всех шаблонов числового исключения, введенных для клиента.

```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Get-CsInboundExemptNumberPattern
```

#### <a name="modify-a-number-exception"></a>Изменение исключения числа

**Командлет Set-CsInboundExemptNumberPattern** позволяет изменить один или несколько параметров для заданного идентификатора шаблона числа. В этом примере параметр **Identity** является обязательным.

```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>Удаление исключения числа

**Командлет Remove-CsInboundExemptNumberPattern** удалит заданный шаблон номера из списка клиентов. В этом примере параметр **Identity** является обязательным.

Если удостоверение неизвестно, сначала найдите нужный шаблон и запишите удостоверение с помощью командлета **Get-CsInboundExemptNumberPattern** . Затем выполните **командлет Remove-CsInboundExemptNumberPattern** и передайте соответствующее значение удостоверения. Утвердите время репликации перед тестированием и проверкой.

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>Проверка блокировки числа

Используйте **командлет Test-CsInboundBlockedNumberPattern** , чтобы проверить, заблокировано ли число в клиенте.

Параметр **PhoneNumber** является обязательным и должен быть числовой строкой без дополнительных символов, таких как +, - или (). **Результирующий параметр IsNumberBlocked** возвращает значение True, если число заблокировано в клиенте; Параметр возвращает значение False, если он не заблокирован.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>Примеры

В этих примерах можно увидеть, что номер телефона 1 (312) 555-8884 заблокирован, так как он должен находиться в указанном выше диапазоне блокировки, а номер телефона 1 (312) 555-8883 может вызываться так, как должно быть основано на исключении, созданном выше.

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

## <a name="using-regex"></a>Использование регулярных выражений

Сопоставление шаблонов для блокирующих вызывающих абонентов выполняется с помощью регулярного выражения. В Интернете доступно несколько средств для проверки соответствия шаблона регулярного выражения. Если вы не знакомы с шаблонами регулярных выражений, рекомендуем ознакомиться с основами в течение некоторого времени. Чтобы убедиться, что вы получаете ожидаемые результаты, используйте средство для проверки совпадений шаблонов перед добавлением новых совпадений заблокированных номеров в клиент.
