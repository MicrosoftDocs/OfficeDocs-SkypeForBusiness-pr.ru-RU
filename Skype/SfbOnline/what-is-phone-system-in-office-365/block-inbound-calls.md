---
title: Блокировать входящие звонки в Skype для бизнеса Online
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 0c40bea45d569a8887f23c38a62efe03977ad461
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840631"
---
# <a name="block-inbound-calls"></a>Блокировать входящие звонки

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype для бизнеса Планы звонков по сети теперь поддерживают блокирование входящие вызовы из телефонной сети общего звонков (ПССК). Эта функция позволяет определить глобальный список шаблонов номеров клиента, чтобы в списке на совпадение можно было проверить ИД звонящая для каждого входящих вызовов по НН. Если совпадение выполнено, входящий звонок отклоняется.

Эта функция блокировки входящие звонков работает только для входящие звонков, исходящие из ПСПС, и работает только на глобальной основе клиента. Она недоступна для каждого пользователя.  

Эта функция пока недоступна для прямой маршрутии.

>[!NOTE]
> Заблокированные вызыватели могут немного отличаться в действиях при блокировании. Поведение зависит от того, как оператор связи заблокированного вызываемого звонка обрабатывает уведомление о том, что звонок не разрешен для успешного завершения. Примерами может быть сообщение о том, что звонок не может быть выполнен по телефону или просто перетассыв вызов.

## <a name="call-blocking-admin-controls-and-information"></a>Блокировка вызовов элементов управления и сведений администратора

Элементы управления блокировкой номеров предоставляются только с помощью PowerShell. Шаблоны блоков числов определяются как шаблоны регулярных выражений. Порядок выражений не имеет ошеломления— первый шаблон, совпадающий с шаблоном в списке, приводит к блокированию вызова. На то, чтобы шаблон стал активным, может потребоваться до 24 часов, чтобы добавить или удалить его из списка заблокированных вызывающих пользователей.

## <a name="call-blocking-powershell-commands"></a>Команды PowerShell, блокирующие вызовы

Шаблоны номеров можно управлять с ```CsInboundBlockedNumberPattern``` помощью команд , , и ```New``` ```Get``` ```Set``` ```Remove``` . Вы можете управлять заданным шаблоном с помощью этих cmdlets, включая возможность переключения активации заданного шаблона.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) возвращает список всех шаблонов заблокированных номеров, добавленных в список клиентов, включая Name, Description, Enabled (True/False) и Pattern для каждого из них.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) добавляет в список клиентов шаблон блокировки.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) удаляет шаблон заблокированных номеров из списка клиентов.
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) изменяет один или несколько параметров шаблона заблокированных номеров в списке клиентов.

Просмотром и активацией всей функции блокировки зовов управляется с помощью ```CsTenantBlockingCallingNumbers``` команд ```Get``` и ```Set``` .

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) возвращает параметры глобального списка заблокированных номеров, включая Enabled (True/False). Существует одна глобальная политика клиента, которую нельзя изменить вручную, кроме как включить или отключить эту функцию.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) позволяет изменять глобальные звонки, заблокированные клиентом, на уровне клиента.

### <a name="examples"></a>Примеры

#### <a name="block-a-number"></a>Блокировка номера

В этом примере ```-Enabled``` параметры ```-Description``` и параметры необязательны:

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

При создании шаблона шаблон добавляется как включенный по умолчанию. Описание — это необязательное поле для предоставления дополнительных сведений.

Мы рекомендуем дать понятное имя, чтобы легко понять, почему был добавлен шаблон. Если вы просто блокируете номера спама, можно назвать правило так же, как шаблон номера, который соответствует этому шаблону, и при необходимости добавить дополнительные сведения в описание.

Совпадения с шаблонами можно использовать с помощью регулярных выражений (Regex). Разрешить время репликации перед проверкой и проверкой.

#### <a name="allow-a-number"></a>Разрешить номер

В этом примере ```-Identity``` параметр является требуемой:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Если удостоверение неизвестно, используйте его, чтобы сначала найти нужный шаблон и ```Get-CsInboundBlockedNumberPattern``` заметить удостоверение. Затем запустите ```Remove-CsTenantBlockedNumberPattern``` этот cmdlet и передатите соответствующее значение удостоверения.

Разрешить время репликации перед проверкой и проверкой.

#### <a name="view-all-number-patterns"></a>Просмотр всех шаблонов номеров

При запуске этого cmdlet возвращается список всех заблокированных номеров, которые введены для клиента:

```powershell
Get-CsInboundBlockedNumberPattern
```

Используйте встроенные возможности фильтрации PowerShell, чтобы при необходимости проавнозить возвращаемую величину.

## <a name="add-number-exceptions"></a>Добавление числных исключений

Вы можете добавить исключения для заблокированных шаблонов с помощью ```CsTenantBlockNumberExceptionPattern``` ```New``` команд, ```Get``` , , и ```Set``` ```Remove``` .

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) добавляет шаблон исключения числа в список клиентов. 
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) возвращает список всех шаблонов числов исключений, добавленных в список клиентов.
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) изменяет один или несколько параметров на числовой шаблон исключения в списке клиентов.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) удаляет шаблон исключения числа из списка клиентов.

### <a name="examples"></a>Примеры

#### <a name="add-a-number-exception"></a>Добавление числого исключения

В этом примере создается шаблон исключения для номеров, который по умолчанию добавляет шаблон как включенный. Параметры ```-Enabled``` ```-Description``` необязательны.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Просмотр всех числных исключений

В этом примере параметр -Identity необязателен. Если параметр не указан, этот cmdlet возвращает список всех шаблонов числового исключения, указанных ```-Identity``` для клиента.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Изменение числого исключения

В этом примере параметр -Identity является обязательным. Он позволяет изменить один или несколько параметров для ```Set-CsTenantBlockedNumberExceptionPattern``` идентификатора заданного числового шаблона.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Удаление числого исключения

В этом примере ```-Identity``` параметр является требуемой. Этот cmdlet удалит заданный шаблон номера из списка клиента.  Если удостоверение неизвестно, используйте его, чтобы сначала найти нужный шаблон и ```Get-CsInboundBlockedNumberPattern``` заметить удостоверение. Затем запустите ```Remove-CsTenantBlockedNumberExceptionPattern``` этот cmdlet и передатите соответствующее значение удостоверения.Разрешить время репликации перед проверкой и проверкой.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Проверка того, заблокировано ли число

Используйте его для проверки того, заблокирован ли номер ```Test-CsInboundBlockedNumberPattern``` в клиенте.
 
В этом примере ```-Phonenumber``` необходимы ```-Tenant``` параметры и параметры. Параметр должен быть числовой строкой без дополнительных символов, ```-PhoneNumber``` таких как +или -. В TRPS это ```-Tenant parameter``` необязательный вариант. Результат возвращает значение True, если число заблокировано в клиенте, и False, если оно ```isNumberBlocked``` не заблокировано.

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

## <a name="a-note-about-regex"></a>Примечание о Regex

Как говорилось ранее, соответствие шаблона для блокировки вызывающих океров делается с помощью Regex. В Интернете доступно несколько инструментов для проверки совпадения с шаблоном Regex. Если вы не знакомы с шаблонами Regex, советуем ознакомиться с основами в течение некоторого времени. Чтобы получить ожидаемые результаты, используйте инструмент для проверки совпадений с шаблонами перед добавлением новых заблокированных номеров в клиент. 

## <a name="related-topics"></a>Статьи по теме

- [Настройка компьютера для управления доступом Skype для бизнеса с помощью Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
