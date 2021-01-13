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
ms.openlocfilehash: ca2f8de5962572a08ab2a0ae7127446d14334c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799909"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="dd606-102">Блокировать входящие звонки</span><span class="sxs-lookup"><span data-stu-id="dd606-102">Block inbound calls</span></span>

<span data-ttu-id="dd606-103">Прямая маршрутия и планы звонков телефонной системы поддерживают блокирование входящие вызовы из телефонной сети общего звонков (STN).</span><span class="sxs-lookup"><span data-stu-id="dd606-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="dd606-104">Эта функция позволяет определить глобальный список шаблонов номеров, чтобы можно было проверить в списке номер звонящую ИД каждого входящих вызовов по ННР в клиенте.</span><span class="sxs-lookup"><span data-stu-id="dd606-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="dd606-105">Если совпадает, входящий звонок отклоняется.</span><span class="sxs-lookup"><span data-stu-id="dd606-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="dd606-106">Эта функция блокировки входящие звонков работает только для входящие звонков из STN и работает только на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="dd606-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="dd606-107">Она недоступна для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="dd606-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="dd606-108">Заблокированные вызыватели могут несколько отличаться в действиях, если они заблокированы.</span><span class="sxs-lookup"><span data-stu-id="dd606-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="dd606-109">Поведение зависит от того, как оператор заблокированного вызова обрабатывает уведомление о том, что звонок не разрешен для успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="dd606-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="dd606-110">Примерами могут быть сообщения о том, что звонок не может быть выполнен в качестве набора номера, или просто перетащение звонка.</span><span class="sxs-lookup"><span data-stu-id="dd606-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="dd606-111">Средства контроля и сведения о блокировке вызовов администратора</span><span class="sxs-lookup"><span data-stu-id="dd606-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="dd606-112">Элементы управления блокировкой номеров администратора предоставляются только с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd606-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="dd606-113">Шаблоны блоков номеров определяются как шаблоны регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="dd606-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="dd606-114">Порядок выражений не совпадает — первый шаблон, совпадающий с шаблоном в списке, приводит к блокировке вызова.</span><span class="sxs-lookup"><span data-stu-id="dd606-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="dd606-115">На то, чтобы шаблон стал активным, может потребоваться до 24 часов, чтобы новый номер или шаблон, добавлялся или удалялся из списка заблокированных вызывающих пользователей.</span><span class="sxs-lookup"><span data-stu-id="dd606-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="dd606-116">Команды PowerShell, блокирующие вызовы</span><span class="sxs-lookup"><span data-stu-id="dd606-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="dd606-117">Шаблоны номеров можно настроить с помощью новых, **get,** **set** и **remove**  - **CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="dd606-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="dd606-118">Вы можете управлять заданным шаблоном с помощью этих cmdlets, в том числе с помощью активации заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="dd606-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="dd606-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) возвращает список всех шаблонов заблокированных номеров, добавленных в список клиентов, включая "Имя", "Описание", "Включено" (истина или ложь) и "Шаблон" для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="dd606-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="dd606-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) добавляет шаблон блокировки для номеров в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="dd606-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="dd606-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) удаляет шаблон заблокированных номеров из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="dd606-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="dd606-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) изменяет один или несколько параметров шаблона заблокированных номеров в списке клиентов.</span><span class="sxs-lookup"><span data-stu-id="dd606-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="dd606-123">Просмотром и активацией всей функции блокировки вызовов управляется с помощью управления get **,** **Set**  - **CsTenantBlockingCallingNumbers.**</span><span class="sxs-lookup"><span data-stu-id="dd606-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="dd606-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) возвращает параметры для глобального списка заблокированных номеров, включая Enabled (True/False).</span><span class="sxs-lookup"><span data-stu-id="dd606-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="dd606-125">Существует одна глобальная политика клиента, которую нельзя изменить вручную, кроме как включить или отключить функцию.</span><span class="sxs-lookup"><span data-stu-id="dd606-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="dd606-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) позволяет изменять параметры звонков, заблокированных глобальным клиентом, на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="dd606-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="dd606-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="dd606-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="dd606-128">Блокировка номера</span><span class="sxs-lookup"><span data-stu-id="dd606-128">Block a number</span></span>

<span data-ttu-id="dd606-129">В этом примере **параметры Enabled** и **Description** необязательны.</span><span class="sxs-lookup"><span data-stu-id="dd606-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="dd606-130">При создании шаблона шаблон добавляется в качестве включенного по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dd606-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="dd606-131">Описание — это необязательное поле, в поле с более подробными сведениями.</span><span class="sxs-lookup"><span data-stu-id="dd606-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="dd606-132">Рекомендуется дать понятное имя, чтобы легко понять, почему был добавлен шаблон.</span><span class="sxs-lookup"><span data-stu-id="dd606-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="dd606-133">Если нужно просто заблокировать нежелательные номера, можно назвать правило таким же, как шаблону совмеченного числа, и добавить в описание дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="dd606-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="dd606-134">Совпадения с шаблонами можно использовать с помощью регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="dd606-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="dd606-135">Время репликации перед проверкой и проверкой.</span><span class="sxs-lookup"><span data-stu-id="dd606-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="dd606-136">Разрешить номер</span><span class="sxs-lookup"><span data-stu-id="dd606-136">Allow a number</span></span>

<span data-ttu-id="dd606-137">В этом примере параметр **Identity** является required.</span><span class="sxs-lookup"><span data-stu-id="dd606-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="dd606-138">Если нужное удостоверение неизвестно, сначала найдите нужный шаблон и заметьте его с помощью **cmdlet Get-CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="dd606-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="dd606-139">Затем запустите cmdlet **Remove-CsTenantBlockedNumberPattern** и передайте соответствующее значение удостоверения.</span><span class="sxs-lookup"><span data-stu-id="dd606-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="dd606-140">Время репликации перед проверкой и проверкой.</span><span class="sxs-lookup"><span data-stu-id="dd606-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="dd606-141">Просмотр всех шаблонов номеров</span><span class="sxs-lookup"><span data-stu-id="dd606-141">View all number patterns</span></span>

<span data-ttu-id="dd606-142">Запуск этого cmdlet возвращает список всех заблокированных номеров, которые введены для клиента:</span><span class="sxs-lookup"><span data-stu-id="dd606-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="dd606-143">Используйте встроенные возможности фильтрации PowerShell для размыки возвращаемого значения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="dd606-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="dd606-144">Добавление числных исключений</span><span class="sxs-lookup"><span data-stu-id="dd606-144">Add number exceptions</span></span>

<span data-ttu-id="dd606-145">Исключения для заблокированных шаблонов номеров можно добавить с помощью новых, **get,** **set** и **remove**  - **CsTenantBlockNumberExceptionPattern.**</span><span class="sxs-lookup"><span data-stu-id="dd606-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="dd606-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) добавляет шаблон исключения для числа в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="dd606-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="dd606-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) возвращает список всех шаблонов числных исключений, добавленных в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="dd606-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="dd606-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) изменяет один или несколько параметров на числовой шаблон исключения в списке клиентов.</span><span class="sxs-lookup"><span data-stu-id="dd606-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="dd606-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) удаляет шаблон исключения для номера из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="dd606-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="dd606-150">Примеры</span><span class="sxs-lookup"><span data-stu-id="dd606-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="dd606-151">Добавление числого исключения</span><span class="sxs-lookup"><span data-stu-id="dd606-151">Add a number exception</span></span>

<span data-ttu-id="dd606-152">В этом примере создается шаблон числового исключения, который по умолчанию добавляет шаблон как включенный.</span><span class="sxs-lookup"><span data-stu-id="dd606-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="dd606-153">Параметры **Enabled** **и Description** необязательны.</span><span class="sxs-lookup"><span data-stu-id="dd606-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="dd606-154">Просмотр всех числных исключений</span><span class="sxs-lookup"><span data-stu-id="dd606-154">View all number exceptions</span></span>

<span data-ttu-id="dd606-155">В этом примере параметр **Identity** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="dd606-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="dd606-156">Если параметр **Identity** не задан, этот cmdlet возвращает список всех шаблонов числового исключения, указанных для клиента.</span><span class="sxs-lookup"><span data-stu-id="dd606-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="dd606-157">Изменение числого исключения</span><span class="sxs-lookup"><span data-stu-id="dd606-157">Modify a number exception</span></span>

<span data-ttu-id="dd606-158">В этом примере параметр **Identity** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="dd606-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="dd606-159">С **помощью cmdlet Set-CsTenantBlockedNumberExceptionPattern можно** изменить один или несколько параметров для заданного идентификатора шаблона номера.</span><span class="sxs-lookup"><span data-stu-id="dd606-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="dd606-160">Удаление числого исключения</span><span class="sxs-lookup"><span data-stu-id="dd606-160">Remove a number exception</span></span>

<span data-ttu-id="dd606-161">В этом примере параметр **Identity** является required.</span><span class="sxs-lookup"><span data-stu-id="dd606-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="dd606-162">Этот cmdlet удалит заданный шаблон номера из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="dd606-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="dd606-163">Если нужное удостоверение неизвестно, сначала найдите нужный шаблон и заметьте его с помощью **cmdlet Get-CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="dd606-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="dd606-164">Затем запустите cmdlet **Remove-CsTenantBlockedNumberExceptionPattern** и передайте соответствующее значение удостоверения.</span><span class="sxs-lookup"><span data-stu-id="dd606-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="dd606-165">Время репликации перед проверкой и проверкой.</span><span class="sxs-lookup"><span data-stu-id="dd606-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="dd606-166">Проверка блокировки номера</span><span class="sxs-lookup"><span data-stu-id="dd606-166">Test whether a number is blocked</span></span>

<span data-ttu-id="dd606-167">С помощью **cmdlet Test-CsInboundBlockedNumberPattern проверьте,** заблокировано ли число в клиенте.</span><span class="sxs-lookup"><span data-stu-id="dd606-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="dd606-168">В этом примере **требуются параметры PhoneNumber** и **Tenant.**</span><span class="sxs-lookup"><span data-stu-id="dd606-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="dd606-169">Параметр **PhoneNumber должен** быть числовой строкой без дополнительных символов, таких как + или -.</span><span class="sxs-lookup"><span data-stu-id="dd606-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="dd606-170">В TRPS параметр **Tenant является необязательным.**</span><span class="sxs-lookup"><span data-stu-id="dd606-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="dd606-171">В результате параметр **IsNumberBlocked** возвращает значение True, если число заблокировано в клиенте, и False, если оно не заблокировано.</span><span class="sxs-lookup"><span data-stu-id="dd606-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="dd606-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="dd606-172">httpResponseCode</span></span>  |<span data-ttu-id="dd606-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="dd606-173">isNumberBlocked</span></span>   |<span data-ttu-id="dd606-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="dd606-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dd606-175">200</span><span class="sxs-lookup"><span data-stu-id="dd606-175">200</span></span>    | <span data-ttu-id="dd606-176">Верно</span><span class="sxs-lookup"><span data-stu-id="dd606-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="dd606-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="dd606-177">httpResponseCode</span></span>  |<span data-ttu-id="dd606-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="dd606-178">isNumberBlocked</span></span>   |<span data-ttu-id="dd606-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="dd606-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dd606-180">200</span><span class="sxs-lookup"><span data-stu-id="dd606-180">200</span></span>    | <span data-ttu-id="dd606-181">False</span><span class="sxs-lookup"><span data-stu-id="dd606-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="dd606-182">Примечание о Regex</span><span class="sxs-lookup"><span data-stu-id="dd606-182">A note about Regex</span></span>

<span data-ttu-id="dd606-183">Как было сказано ранее, для блокировки вызывающих вызовов соответствие шаблонам используется Regex.</span><span class="sxs-lookup"><span data-stu-id="dd606-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="dd606-184">В Интернете доступно несколько инструментов для проверки совпадения с шаблоном регулярного регулярного анализа.</span><span class="sxs-lookup"><span data-stu-id="dd606-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="dd606-185">Если вы не знакомы с шаблонами Regex, рекомендуем ознакомиться с базовыми задачами в течение некоторого времени.</span><span class="sxs-lookup"><span data-stu-id="dd606-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="dd606-186">Чтобы получить ожидаемые результаты, используйте инструмент для проверки совпадений с шаблонами перед добавлением новых заблокированных совпадений в клиенте.</span><span class="sxs-lookup"><span data-stu-id="dd606-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
