---
title: Блокировка входящих звонков в Skype для бизнеса Online
ms.author: v-lanac
author: lanachin
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: b238d69087c5b29e6d9abc898e91c44fd8053411
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266072"
---
# <a name="block-inbound-calls"></a>Блокировать входящие звонки

Планы звонков в Skype для бизнеса Online теперь поддерживают блокирование входящих звонков из коммутируемой телефонной сети, поддерживающей коммутируемую связь. Эта функция позволяет определять глобальный список шаблонов для клиентов, чтобы идентификатор вызывающего абонента для каждого входящего звонка PSTN в клиент мог быть проверен относительно списка соответствия. Если соответствие установлено, входящий звонок отклоняется.

Этот компонент блокирования входящих звонков действует только для входящих звонков, исходящих от КТСОП, и работает только на глобальной основе клиента. Она недоступна отдельно для каждого пользователя.  

Эта функция пока не доступна для прямой маршрутизации.

>[!NOTE]
> Заблокированные вызывающие абоненты могут испытывать некоторые другие проблемы, когда они заблокированы. Поведение зависит от того, как перевозчик вызывающего абонента обрабатывает уведомление о том, что звонок не может быть успешно выполнен. Примеры могут включать в себя сообщение о недосообщении, в котором не удается выполнить звонок или просто удалить звонок.

## <a name="call-blocking-admin-controls-and-information"></a>Блокировка звонков элементы управления и сведения для администраторов

Элементы управления администрированием для номеров блокировки предоставляются только с помощью PowerShell. Шаблоны блоков чисел определяются как шаблоны регулярных выражений. Порядок выражений не важен — первый шаблон, совпадающий со списком, приводит к блокировке звонка. Новый номер или шаблон, добавленные или удаленные в списке заблокированных вызывающих абонентов, может занимать до 24 часов, пока шаблон не станет активным.

## <a name="call-blocking-powershell-commands"></a>Блокировка вызова команд PowerShell

Нумерация осуществляется ```CsInboundBlockedNumberPattern``` с помощью команд ```New```, ```Get``` ```Set```, и. ```Remove``` Вы можете управлять данным шаблоном, используя эти командлеты, в том числе возможность переключать активацию определенного шаблона.
- Функция [Get-ксинбаундблоккеднумберпаттерн](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) возвращает список всех шаблонов заблокированных номеров, добавленных в список клиентов, включая имя, описание, разрешено (истина/ложь) и шаблон для каждого из них.
- [New-ксинбаундблоккеднумберпаттерн](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) добавляет шаблон заблокированного номера в список клиентов.
- [Remove-ксинбаундблоккеднумберпаттерн](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) удаляет заблокированный шаблон номера из списка клиентов.
- [Set-ксинбаундблоккеднумберпаттерн](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) изменяет один или несколько параметров заблокированного числового шаблона в списке клиентов.

Просмотр и активация функции блокировки звонков осуществляется с помощью ```CsTenantBlockingCallingNumbers``` команд ```Get``` и. ```Set```

- Функция [Get-кстенантблоккедкаллингнумберс](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) Возвращает параметры для глобального списка блокируемых номеров, включая Enabled (истина/ложь). Существует единая глобальная политика клиентов, которая не может быть изменена вручную, кроме включения и отключения этой функции.
- [Set-кстенантблоккедкаллингнумберс](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) позволяет изменить заблокированные вызовы для глобальных клиентов на уровне клиента.

### <a name="examples"></a>Примеры

#### <a name="block-a-number"></a>Блокировка номера

В этом примере параметры ```-Enabled``` и и ```-Description``` не являются обязательными.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

При создании нового узора по умолчанию добавляется шаблон с включением. Описание — необязательное поле для предоставления дополнительной информации.

Рекомендуем дать понятное имя, чтобы легко понять, почему был добавлен шаблон. В случае простого блокирования нежелательной почты рекомендуется присвоить правилу имя, совпадающее с шаблоном числа, и при необходимости добавить дополнительные сведения в описание.

Шаблоны сопоставлены с помощью регулярных выражений (Regex). Разрешите время репликации, прежде чем вы проверите и проверите.

#### <a name="allow-a-number"></a>Разрешение номера

В этом примере требуется ```-Identity``` параметр:

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Если идентификация неизвестна, сначала ```Get-CsInboundBlockedNumberPattern``` с помощью командлета найдите нужный шаблон и запомните его. Затем выполните ```Remove-CsTenantBlockedNumberPattern``` командлет и передайте нужное значение идентификатора.

Разрешите время репликации, прежде чем вы проверите и проверите.

#### <a name="view-all-number-patterns"></a>Просмотр всех числовых шаблонов

Выполнение этого командлета возвращает список всех заблокированных номеров, введенных для клиента:

```powershell
Get-CsInboundBlockedNumberPattern
```

Используйте встроенные возможности фильтрации PowerShell для синтаксического анализа возвращаемых значений в соответствии с требованиями.

## <a name="add-number-exceptions"></a>Добавление исключений номеров

Вы можете добавлять исключения для заблокированных числовых шаблонов с ```CsTenantBlockNumberExceptionPattern``` помощью команд ```New```, ```Get``` ```Set```,, и ```Remove```.

- [New-кстенантблоккеднумберексцептионпаттерн](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) добавляет шаблон исключения номера в список клиентов. 
- Функция [Get-кстенантблоккеднумберексцептионпаттерн](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) возвращает список всех шаблонов исключений номеров, добавленных в список клиентов.
- [Set-кстенантблоккеднумберексцептионпаттерн](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) изменяет один или несколько параметров в шаблон исключения для номера в списке клиентов.
- [Remove-кстенантблоккеднумберексцептионпаттерн](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) удаляет шаблон исключения номера из списка клиентов.

### <a name="examples"></a>Примеры

#### <a name="add-a-number-exception"></a>Добавление исключения числа

В этом примере создается шаблон исключения для нового номера, который по умолчанию будет добавлен как включенный. Параметры ```-Enabled``` и ```-Description``` не являются обязательными.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>Просмотр всех исключений для номеров

В этом примере параметр-Identity является необязательным. Если ```-Identity``` параметр не указан, этот командлет возвращает список всех шаблонов исключений количества, введенных для клиента.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>Изменение числа исключений

В этом примере параметр-Identity является обязательным. ```Set-CsTenantBlockedNumberExceptionPattern``` Командлет позволяет изменить один или несколько параметров для определенного идентификатора шаблона номера.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>Удаление исключения числа

В этом примере ```-Identity``` параметр является обязательным. Этот командлет удалит указанный шаблон номера из списка клиентов.  Если идентификация неизвестна, сначала ```Get-CsInboundBlockedNumberPattern``` с помощью командлета найдите нужный шаблон и запомните его. Затем выполните ```Remove-CsTenantBlockedNumberExceptionPattern``` командлет и передайте нужное значение идентификатора.Разрешите время репликации, прежде чем вы проверите и проверите.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>Проверка того, заблокировано ли число

Используйте ```Test-CsInboundBlockedNumberPattern``` командлет для проверки того, заблокировано ли число в клиенте.
 
В этом примере требуются параметры ```-Phonenumber``` и ```-Tenant``` . ```-PhoneNumber``` Параметр должен представлять собой числовую строку без дополнительных знаков, таких как + или-. В ТРПС ```-Tenant parameter``` это необязательный аргумент. Конечный ```isNumberBlocked``` параметр возвращает значение true, если номер заблокирован в клиенте, и значение false, если оно не заблокировано.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|хттпреспонсекоде  |иснумберблоккед   |Ошибк |
|---------|---------|---------|
|200    | Верно        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|хттпреспонсекоде  |иснумберблоккед   |Ошибк |
|---------|---------|---------|
|200    | False        |         |

## <a name="a-note-about-regex"></a>Примечание о регулярном выражении

Как упоминалось ранее, соответствие шаблону для вызывающих абонентов выполняется с помощью регулярного выражения. Для проверки соответствия шаблону регулярного выражения в Интернете доступно несколько средств. Если вы не знакомы с шаблонами регулярных выражений, мы рекомендуем вам ознакомиться с основными принципами. Чтобы убедиться в том, что вы получаете ожидаемые результаты, используйте инструмент для проверки соответствия шаблону, прежде чем добавлять новые заблокированные номера для поиска в клиенте. 

## <a name="related-topics"></a>Статьи по теме

- [Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
