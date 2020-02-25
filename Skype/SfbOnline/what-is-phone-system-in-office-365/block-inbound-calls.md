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
# <a name="block-inbound-calls"></a><span data-ttu-id="0908a-102">Блокировать входящие звонки</span><span class="sxs-lookup"><span data-stu-id="0908a-102">Block inbound calls</span></span>

<span data-ttu-id="0908a-103">Планы звонков в Skype для бизнеса Online теперь поддерживают блокирование входящих звонков из коммутируемой телефонной сети, поддерживающей коммутируемую связь.</span><span class="sxs-lookup"><span data-stu-id="0908a-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="0908a-104">Эта функция позволяет определять глобальный список шаблонов для клиентов, чтобы идентификатор вызывающего абонента для каждого входящего звонка PSTN в клиент мог быть проверен относительно списка соответствия.</span><span class="sxs-lookup"><span data-stu-id="0908a-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="0908a-105">Если соответствие установлено, входящий звонок отклоняется.</span><span class="sxs-lookup"><span data-stu-id="0908a-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="0908a-106">Этот компонент блокирования входящих звонков действует только для входящих звонков, исходящих от КТСОП, и работает только на глобальной основе клиента.</span><span class="sxs-lookup"><span data-stu-id="0908a-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="0908a-107">Она недоступна отдельно для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="0908a-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="0908a-108">Эта функция пока не доступна для прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="0908a-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="0908a-109">Заблокированные вызывающие абоненты могут испытывать некоторые другие проблемы, когда они заблокированы.</span><span class="sxs-lookup"><span data-stu-id="0908a-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="0908a-110">Поведение зависит от того, как перевозчик вызывающего абонента обрабатывает уведомление о том, что звонок не может быть успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="0908a-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="0908a-111">Примеры могут включать в себя сообщение о недосообщении, в котором не удается выполнить звонок или просто удалить звонок.</span><span class="sxs-lookup"><span data-stu-id="0908a-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="0908a-112">Блокировка звонков элементы управления и сведения для администраторов</span><span class="sxs-lookup"><span data-stu-id="0908a-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="0908a-113">Элементы управления администрированием для номеров блокировки предоставляются только с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0908a-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="0908a-114">Шаблоны блоков чисел определяются как шаблоны регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="0908a-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="0908a-115">Порядок выражений не важен — первый шаблон, совпадающий со списком, приводит к блокировке звонка.</span><span class="sxs-lookup"><span data-stu-id="0908a-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="0908a-116">Новый номер или шаблон, добавленные или удаленные в списке заблокированных вызывающих абонентов, может занимать до 24 часов, пока шаблон не станет активным.</span><span class="sxs-lookup"><span data-stu-id="0908a-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="0908a-117">Блокировка вызова команд PowerShell</span><span class="sxs-lookup"><span data-stu-id="0908a-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="0908a-118">Нумерация осуществляется ```CsInboundBlockedNumberPattern``` с помощью команд ```New```, ```Get``` ```Set```, и. ```Remove```</span><span class="sxs-lookup"><span data-stu-id="0908a-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="0908a-119">Вы можете управлять данным шаблоном, используя эти командлеты, в том числе возможность переключать активацию определенного шаблона.</span><span class="sxs-lookup"><span data-stu-id="0908a-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="0908a-120">Функция [Get-ксинбаундблоккеднумберпаттерн](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) возвращает список всех шаблонов заблокированных номеров, добавленных в список клиентов, включая имя, описание, разрешено (истина/ложь) и шаблон для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="0908a-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="0908a-121">[New-ксинбаундблоккеднумберпаттерн](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) добавляет шаблон заблокированного номера в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="0908a-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="0908a-122">[Remove-ксинбаундблоккеднумберпаттерн](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) удаляет заблокированный шаблон номера из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="0908a-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="0908a-123">[Set-ксинбаундблоккеднумберпаттерн](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) изменяет один или несколько параметров заблокированного числового шаблона в списке клиентов.</span><span class="sxs-lookup"><span data-stu-id="0908a-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="0908a-124">Просмотр и активация функции блокировки звонков осуществляется с помощью ```CsTenantBlockingCallingNumbers``` команд ```Get``` и. ```Set```</span><span class="sxs-lookup"><span data-stu-id="0908a-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="0908a-125">Функция [Get-кстенантблоккедкаллингнумберс](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) Возвращает параметры для глобального списка блокируемых номеров, включая Enabled (истина/ложь).</span><span class="sxs-lookup"><span data-stu-id="0908a-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="0908a-126">Существует единая глобальная политика клиентов, которая не может быть изменена вручную, кроме включения и отключения этой функции.</span><span class="sxs-lookup"><span data-stu-id="0908a-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="0908a-127">[Set-кстенантблоккедкаллингнумберс](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) позволяет изменить заблокированные вызовы для глобальных клиентов на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="0908a-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="0908a-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="0908a-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="0908a-129">Блокировка номера</span><span class="sxs-lookup"><span data-stu-id="0908a-129">Block a number</span></span>

<span data-ttu-id="0908a-130">В этом примере параметры ```-Enabled``` и и ```-Description``` не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="0908a-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="0908a-131">При создании нового узора по умолчанию добавляется шаблон с включением.</span><span class="sxs-lookup"><span data-stu-id="0908a-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="0908a-132">Описание — необязательное поле для предоставления дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="0908a-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="0908a-133">Рекомендуем дать понятное имя, чтобы легко понять, почему был добавлен шаблон.</span><span class="sxs-lookup"><span data-stu-id="0908a-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="0908a-134">В случае простого блокирования нежелательной почты рекомендуется присвоить правилу имя, совпадающее с шаблоном числа, и при необходимости добавить дополнительные сведения в описание.</span><span class="sxs-lookup"><span data-stu-id="0908a-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="0908a-135">Шаблоны сопоставлены с помощью регулярных выражений (Regex).</span><span class="sxs-lookup"><span data-stu-id="0908a-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="0908a-136">Разрешите время репликации, прежде чем вы проверите и проверите.</span><span class="sxs-lookup"><span data-stu-id="0908a-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="0908a-137">Разрешение номера</span><span class="sxs-lookup"><span data-stu-id="0908a-137">Allow a number</span></span>

<span data-ttu-id="0908a-138">В этом примере требуется ```-Identity``` параметр:</span><span class="sxs-lookup"><span data-stu-id="0908a-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="0908a-139">Если идентификация неизвестна, сначала ```Get-CsInboundBlockedNumberPattern``` с помощью командлета найдите нужный шаблон и запомните его.</span><span class="sxs-lookup"><span data-stu-id="0908a-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="0908a-140">Затем выполните ```Remove-CsTenantBlockedNumberPattern``` командлет и передайте нужное значение идентификатора.</span><span class="sxs-lookup"><span data-stu-id="0908a-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="0908a-141">Разрешите время репликации, прежде чем вы проверите и проверите.</span><span class="sxs-lookup"><span data-stu-id="0908a-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="0908a-142">Просмотр всех числовых шаблонов</span><span class="sxs-lookup"><span data-stu-id="0908a-142">View all number patterns</span></span>

<span data-ttu-id="0908a-143">Выполнение этого командлета возвращает список всех заблокированных номеров, введенных для клиента:</span><span class="sxs-lookup"><span data-stu-id="0908a-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="0908a-144">Используйте встроенные возможности фильтрации PowerShell для синтаксического анализа возвращаемых значений в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="0908a-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="0908a-145">Добавление исключений номеров</span><span class="sxs-lookup"><span data-stu-id="0908a-145">Add number exceptions</span></span>

<span data-ttu-id="0908a-146">Вы можете добавлять исключения для заблокированных числовых шаблонов с ```CsTenantBlockNumberExceptionPattern``` помощью команд ```New```, ```Get``` ```Set```,, и ```Remove```.</span><span class="sxs-lookup"><span data-stu-id="0908a-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="0908a-147">[New-кстенантблоккеднумберексцептионпаттерн](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) добавляет шаблон исключения номера в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="0908a-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="0908a-148">Функция [Get-кстенантблоккеднумберексцептионпаттерн](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) возвращает список всех шаблонов исключений номеров, добавленных в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="0908a-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="0908a-149">[Set-кстенантблоккеднумберексцептионпаттерн](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) изменяет один или несколько параметров в шаблон исключения для номера в списке клиентов.</span><span class="sxs-lookup"><span data-stu-id="0908a-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="0908a-150">[Remove-кстенантблоккеднумберексцептионпаттерн](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) удаляет шаблон исключения номера из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="0908a-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="0908a-151">Примеры</span><span class="sxs-lookup"><span data-stu-id="0908a-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="0908a-152">Добавление исключения числа</span><span class="sxs-lookup"><span data-stu-id="0908a-152">Add a number exception</span></span>

<span data-ttu-id="0908a-153">В этом примере создается шаблон исключения для нового номера, который по умолчанию будет добавлен как включенный.</span><span class="sxs-lookup"><span data-stu-id="0908a-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="0908a-154">Параметры ```-Enabled``` и ```-Description``` не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="0908a-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="0908a-155">Просмотр всех исключений для номеров</span><span class="sxs-lookup"><span data-stu-id="0908a-155">View all number exceptions</span></span>

<span data-ttu-id="0908a-156">В этом примере параметр-Identity является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0908a-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="0908a-157">Если ```-Identity``` параметр не указан, этот командлет возвращает список всех шаблонов исключений количества, введенных для клиента.</span><span class="sxs-lookup"><span data-stu-id="0908a-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="0908a-158">Изменение числа исключений</span><span class="sxs-lookup"><span data-stu-id="0908a-158">Modify a number exception</span></span>

<span data-ttu-id="0908a-159">В этом примере параметр-Identity является обязательным.</span><span class="sxs-lookup"><span data-stu-id="0908a-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="0908a-160">```Set-CsTenantBlockedNumberExceptionPattern``` Командлет позволяет изменить один или несколько параметров для определенного идентификатора шаблона номера.</span><span class="sxs-lookup"><span data-stu-id="0908a-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="0908a-161">Удаление исключения числа</span><span class="sxs-lookup"><span data-stu-id="0908a-161">Remove a number exception</span></span>

<span data-ttu-id="0908a-162">В этом примере ```-Identity``` параметр является обязательным.</span><span class="sxs-lookup"><span data-stu-id="0908a-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="0908a-163">Этот командлет удалит указанный шаблон номера из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="0908a-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="0908a-164">Если идентификация неизвестна, сначала ```Get-CsInboundBlockedNumberPattern``` с помощью командлета найдите нужный шаблон и запомните его.</span><span class="sxs-lookup"><span data-stu-id="0908a-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="0908a-165">Затем выполните ```Remove-CsTenantBlockedNumberExceptionPattern``` командлет и передайте нужное значение идентификатора.</span><span class="sxs-lookup"><span data-stu-id="0908a-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="0908a-166">Разрешите время репликации, прежде чем вы проверите и проверите.</span><span class="sxs-lookup"><span data-stu-id="0908a-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="0908a-167">Проверка того, заблокировано ли число</span><span class="sxs-lookup"><span data-stu-id="0908a-167">Test whether a number is blocked</span></span>

<span data-ttu-id="0908a-168">Используйте ```Test-CsInboundBlockedNumberPattern``` командлет для проверки того, заблокировано ли число в клиенте.</span><span class="sxs-lookup"><span data-stu-id="0908a-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="0908a-169">В этом примере требуются параметры ```-Phonenumber``` и ```-Tenant``` .</span><span class="sxs-lookup"><span data-stu-id="0908a-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="0908a-170">```-PhoneNumber``` Параметр должен представлять собой числовую строку без дополнительных знаков, таких как + или-.</span><span class="sxs-lookup"><span data-stu-id="0908a-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="0908a-171">В ТРПС ```-Tenant parameter``` это необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="0908a-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="0908a-172">Конечный ```isNumberBlocked``` параметр возвращает значение true, если номер заблокирован в клиенте, и значение false, если оно не заблокировано.</span><span class="sxs-lookup"><span data-stu-id="0908a-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="0908a-173">хттпреспонсекоде</span><span class="sxs-lookup"><span data-stu-id="0908a-173">httpResponseCode</span></span>  |<span data-ttu-id="0908a-174">иснумберблоккед</span><span class="sxs-lookup"><span data-stu-id="0908a-174">isNumberBlocked</span></span>   |<span data-ttu-id="0908a-175">Ошибк</span><span class="sxs-lookup"><span data-stu-id="0908a-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="0908a-176">200</span><span class="sxs-lookup"><span data-stu-id="0908a-176">200</span></span>    | <span data-ttu-id="0908a-177">Верно</span><span class="sxs-lookup"><span data-stu-id="0908a-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="0908a-178">хттпреспонсекоде</span><span class="sxs-lookup"><span data-stu-id="0908a-178">httpResponseCode</span></span>  |<span data-ttu-id="0908a-179">иснумберблоккед</span><span class="sxs-lookup"><span data-stu-id="0908a-179">isNumberBlocked</span></span>   |<span data-ttu-id="0908a-180">Ошибк</span><span class="sxs-lookup"><span data-stu-id="0908a-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="0908a-181">200</span><span class="sxs-lookup"><span data-stu-id="0908a-181">200</span></span>    | <span data-ttu-id="0908a-182">False</span><span class="sxs-lookup"><span data-stu-id="0908a-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="0908a-183">Примечание о регулярном выражении</span><span class="sxs-lookup"><span data-stu-id="0908a-183">A note about Regex</span></span>

<span data-ttu-id="0908a-184">Как упоминалось ранее, соответствие шаблону для вызывающих абонентов выполняется с помощью регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="0908a-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="0908a-185">Для проверки соответствия шаблону регулярного выражения в Интернете доступно несколько средств.</span><span class="sxs-lookup"><span data-stu-id="0908a-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="0908a-186">Если вы не знакомы с шаблонами регулярных выражений, мы рекомендуем вам ознакомиться с основными принципами.</span><span class="sxs-lookup"><span data-stu-id="0908a-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="0908a-187">Чтобы убедиться в том, что вы получаете ожидаемые результаты, используйте инструмент для проверки соответствия шаблону, прежде чем добавлять новые заблокированные номера для поиска в клиенте.</span><span class="sxs-lookup"><span data-stu-id="0908a-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="0908a-188">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0908a-188">Related topics</span></span>

- [<span data-ttu-id="0908a-189">Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0908a-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
