---
title: Блокировка входящих вызовов в Skype для бизнеса Online
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
description: Администраторы могут узнать, как блокировать входящие вызовы в Skype для бизнеса Online.
ms.openlocfilehash: 40b43f669ededf7ac334c25c79b5af09140c075d
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671655"
---
# <a name="block-inbound-calls"></a>Блокировка входящих вызовов

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype для бизнеса сетевые планы звонков теперь поддерживают блокировку входящих звонков из телефонной сети общего пользования (ТСОП). Эта функция позволяет определить глобальный список шаблонов номеров клиента, чтобы идентификатор вызывающего абонента каждого входящего вызова ТСОП к клиенту можно было проверить в списке на соответствие. Если сопоставление выполнено, входящий вызов отклоняется.

Эта функция блокировки входящих вызовов работает только для входящих вызовов, исходящих из ТСОП, и работает только на глобальной основе клиента. Он недоступен для каждого пользователя.

Эта функция пока недоступна для прямой маршрутизации.

>[!NOTE]
> Заблокированные вызывающие объекты могут немного отличаться в поведении, если они заблокированы. Поведение зависит от того, как оператор заблокированного абонента обрабатывает уведомление о том, что звонок не может быть успешно завершен. Примеры могут включать в себя сообщение оператора о том, что звонок не может быть завершен как на телефоне, или просто удалить звонок.

## <a name="call-blocking-admin-controls-and-information"></a>Блокировка вызовов элементов управления и сведений администратора

Администратор для блокирующих номеров предоставляются только с помощью PowerShell. Шаблоны числового блока определяются как шаблоны регулярных выражений. Порядок выражений не имеет значения— первый шаблон, сопоставленный в списке, приводит к блокировке вызова. Новый номер или шаблон, добавленный или удаленный в списке заблокированных вызывающих абонентов, может занять до 24 часов, чтобы шаблон стал активным.

## <a name="call-blocking-powershell-commands"></a>Команды PowerShell, блокирующие вызовы

Шаблоны чина управляются с помощью ```CsInboundBlockedNumberPattern``` команд ```New```, ```Get```и ```Set``````Remove```. Вы можете управлять заданным шаблоном с помощью этих командлетов, включая возможность переключать активацию заданного шаблона.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) возвращает список всех заблокированных шаблонов номеров, добавленных в список клиентов, включая "Имя", "Описание", "Включено" (true/False) и "Шаблон" для каждого из них.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) добавляет в список клиентов шаблон заблокированных номеров.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) удаляет из списка клиентов шаблон заблокированных номеров.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) изменяет один или несколько параметров шаблона заблокированного числа в списке клиентов.

Просмотр и активация всей функции блокировки вызовов управляется с помощью ```CsTenantBlockingCallingNumbers``` команд ```Get``` и ```Set```.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) возвращает параметры глобального списка заблокированных номеров, включая Enabled (True или False). Существует одна глобальная политика клиента, которую нельзя изменить вручную, кроме включения или отключения функции.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) позволяет включать и отключать вызовы, заблокированные глобальным клиентом, на уровне клиента.

### <a name="examples"></a>Примеры

#### <a name="block-a-number"></a>Блокировать число

В этом примере параметры ```-Enabled``` и параметры ```-Description``` являются необязательными:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

При создании нового шаблона шаблон добавляется как включенный по умолчанию. Описание является необязательным полем для предоставления дополнительных сведений.

Рекомендуется указать понятное имя, чтобы легко понять, почему был добавлен шаблон. В случае простой блокировки номеров нежелательной почты рассмотрите возможность именования правила так же, как и сопоставленный шаблон чисел, и добавьте дополнительные сведения в описание по мере необходимости.

Шаблоны сопоставляется с помощью регулярных выражений (регулярных выражений).
Утвердите время репликации перед тестированием и проверкой.

#### <a name="allow-a-number"></a>Разрешить число

В этом примере параметр ```-Identity``` является обязательным:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```

Если удостоверение неизвестно, используйте командлет, ```Get-CsInboundBlockedNumberPattern``` чтобы сначала найти правильный шаблон и запишите удостоверение. Затем выполните командлет ```Remove-CsTenantBlockedNumberPattern``` и передайте соответствующее значение удостоверения.

Утвердите время репликации перед тестированием и проверкой.

#### <a name="view-all-number-patterns"></a>Просмотр всех шаблонов чина

При выполнении этого командлета возвращается список всех заблокированных номеров, введенных для клиента:

```powershell
Get-CsInboundBlockedNumberPattern
```

Используйте встроенные возможности фильтрации PowerShell для анализа возвращаемых значений по мере необходимости.

## <a name="add-number-exceptions"></a>Добавление исключений числа

Вы можете добавлять исключения в блокированные числимые ```CsTenantBlockNumberExceptionPattern``` шаблоны с помощью команд, ```New```, и ```Remove``````Get``````Set```.

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) добавляет шаблон исключения числа в список клиентов.
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) возвращает список всех шаблонов числового исключения, добавленных в список клиентов.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) изменяет один или несколько параметров на числовой шаблон исключения в списке клиентов.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) удаляет шаблон исключения числа из списка клиентов.

### <a name="examples"></a>Примеры

#### <a name="add-a-number-exception"></a>Добавление числовое исключение

В этом примере создается новый шаблон исключения числа, который по умолчанию добавляет шаблон как включенный. Параметры ```-Enabled``` ```-Description``` и параметры являются необязательными.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"
```

#### <a name="view-all-number-exceptions"></a>Просмотр всех числов исключений

В этом примере параметр -Identity является необязательным. Если параметр ```-Identity``` не указан, этот командлет возвращает список всех шаблонов числового исключения, введенных для клиента.

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Изменение исключения числа

В этом примере параметр -Identity является обязательным. Командлет ```Set-CsTenantBlockedNumberExceptionPattern``` позволяет изменить один или несколько параметров для заданного идентификатора шаблона числа.

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$"
```

#### <a name="remove-a-number-exception"></a>Удаление исключения числа

В этом примере параметр ```-Identity``` является обязательным. Этот командлет удалит заданный шаблон номера из списка клиентов.  Если удостоверение неизвестно, используйте командлет, ```Get-CsInboundBlockedNumberPattern``` чтобы сначала найти правильный шаблон и запишите удостоверение. Затем выполните командлет ```Remove-CsTenantBlockedNumberExceptionPattern``` и передайте соответствующее значение удостоверения. Утвердите время репликации перед тестированием и проверкой.

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Проверка блокировки числа

Используйте командлет ```Test-CsInboundBlockedNumberPattern``` , чтобы проверить, заблокировано ли число в клиенте.

В этом примере требуются ```-Phonenumber``` ```-Tenant``` параметры и параметры. Параметр ```-PhoneNumber``` должен быть числовой строкой без дополнительных символов, таких как +или -. В TRPS это необязательный ```-Tenant parameter``` параметр. Результирующий ```isNumberBlocked``` параметр возвращает значение True, если число заблокировано в клиенте, и false, если оно не заблокировано.

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

## <a name="a-note-about-regex"></a>Примечание о регулярных выражениях

Как упоминалось ранее, сопоставление шаблонов для блокирующих вызывающих абонентов выполняется с помощью регулярного выражения. В Интернете доступно несколько средств для проверки соответствия шаблона регулярного выражения. Если вы не знакомы с шаблонами регулярных выражений, рекомендуем ознакомиться с основами в течение некоторого времени. Чтобы убедиться, что вы получаете ожидаемые результаты, используйте средство для проверки совпадений шаблонов перед добавлением новых совпадений заблокированных номеров в клиент.

## <a name="related-topics"></a>Статьи по теме

- [Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
