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
ms.openlocfilehash: e584e9f0c16ef77424121c37ce87c6d63afb4b92
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689767"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="586d1-102">Блокировать входящие звонки</span><span class="sxs-lookup"><span data-stu-id="586d1-102">Block inbound calls</span></span>

<span data-ttu-id="586d1-103">Планы звонков Майкрософт, прямая маршрутия и оператор Подключение блокируют входящие звонки из телефонной сети общего звонков (ПСОП).</span><span class="sxs-lookup"><span data-stu-id="586d1-103">Microsoft Calling Plans, Direct Routing, and Operator Connect all support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="586d1-104">Эта функция позволяет администратору определить список шаблонов номеров на глобальном уровне клиента, чтобы в списке на совпадение можно было проверить ИД звонящая для каждого входящих вызовов по ДНР в клиенте.</span><span class="sxs-lookup"><span data-stu-id="586d1-104">This feature allows an administrator to define a  list of number patterns at the tenant global level so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="586d1-105">Если совпадение выполнено, входящий звонок отклоняется.</span><span class="sxs-lookup"><span data-stu-id="586d1-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="586d1-106">Эта функция блокировки входящие звонков работает только для входящие звонков, исходящие из ПСПС, и работает только на глобальном уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="586d1-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant global level.</span></span> <span data-ttu-id="586d1-107">Отдельные Teams не могут управлять этим списком.</span><span class="sxs-lookup"><span data-stu-id="586d1-107">Individual Teams users can’t manipulate this list.</span></span> <span data-ttu-id="586d1-108">Клиент Teams позволяет отдельным пользователям блокировать звонки по ННР.</span><span class="sxs-lookup"><span data-stu-id="586d1-108">The Teams client does allow individual users to block PSTN calls.</span></span> <span data-ttu-id="586d1-109">Сведения о том, как конечные пользователи могут блокировать вызовы, см. в [Teams.](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="586d1-109">For information about how your end users can implement call blocking, see [Manage call settings in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span>

>[!NOTE]
> <span data-ttu-id="586d1-110">Заблокированные вызыватели могут немного отличаться в действиях, если они заблокированы.</span><span class="sxs-lookup"><span data-stu-id="586d1-110">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="586d1-111">Поведение зависит от того, как оператор связи заблокированного вызываемого звонка обрабатывает уведомление о том, что звонок не разрешен для успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="586d1-111">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="586d1-112">Примерами может быть сообщение о том, что звонок не может быть выполнен по телефону или просто перетассыв вызов.</span><span class="sxs-lookup"><span data-stu-id="586d1-112">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="586d1-113">Блокировка вызовов элементов управления и сведений администратора</span><span class="sxs-lookup"><span data-stu-id="586d1-113">Call blocking admin controls and information</span></span>

<span data-ttu-id="586d1-114">Элементы управления блокировкой номеров предоставляются только с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="586d1-114">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="586d1-115">Шаблоны блоков числов определяются как шаблоны регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="586d1-115">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="586d1-116">Порядок выражений не имеет важного отношения— первый шаблон, совпадающий с шаблоном в списке, приводит к блокированию звонка.</span><span class="sxs-lookup"><span data-stu-id="586d1-116">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="586d1-117">На то, чтобы шаблон стал активным, может потребоваться до 24 часов, чтобы новый номер или шаблон, который был добавлен или удален в списке заблокированных вызывающих пользователей.</span><span class="sxs-lookup"><span data-stu-id="586d1-117">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="586d1-118">Команды PowerShell, блокирующие вызовы</span><span class="sxs-lookup"><span data-stu-id="586d1-118">Call blocking PowerShell commands</span></span>

<span data-ttu-id="586d1-119">Шаблоны номеров можно настроить с помощью **нью-,** **Get-**, **Set-** и **Remove-CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="586d1-119">You manage number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="586d1-120">Вы можете управлять заданным шаблоном с помощью этих cmdlets, включая возможность переключения активации заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="586d1-120">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="586d1-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) возвращает список всех шаблонов заблокированных номеров, добавленных в список клиентов, включая Name, Description, Enabled (True/False) и Pattern для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="586d1-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="586d1-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) добавляет в список клиентов шаблон заблокированных номеров.</span><span class="sxs-lookup"><span data-stu-id="586d1-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="586d1-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) удаляет из списка клиентов шаблон заблокированных номеров.</span><span class="sxs-lookup"><span data-stu-id="586d1-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="586d1-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) изменяет один или несколько параметров шаблона заблокированных номеров в списке клиентов.</span><span class="sxs-lookup"><span data-stu-id="586d1-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="586d1-125">Просмотром и активацией всей функции блокировки зовов управляется с помощью элементов **Get-** и **Set-CsTenantBlockingCallingNumbers.**</span><span class="sxs-lookup"><span data-stu-id="586d1-125">Viewing and activating the entire call blocking feature is managed through the **Get-** and **Set-CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="586d1-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) возвращает шаблоны входящий номер блока и параметры исключаемого числа для глобального списка блокировок.</span><span class="sxs-lookup"><span data-stu-id="586d1-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the inbound block number patterns and the inbound exempt number patterns parameters for the global blocked number list.</span></span> <span data-ttu-id="586d1-127">Этот cmdlet также возвращает, включена ли блокировка (True или False).</span><span class="sxs-lookup"><span data-stu-id="586d1-127">This cmdlet also returns whether blocking has been Enabled (True or False).</span></span> <span data-ttu-id="586d1-128">Существует одна глобальная политика клиента, которую нельзя изменить вручную, кроме как включить или отключить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="586d1-128">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="586d1-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) позволяет изменять глобальные звонки, заблокированные клиентом, на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="586d1-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="586d1-130">Примеры</span><span class="sxs-lookup"><span data-stu-id="586d1-130">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="586d1-131">Блокировка номера</span><span class="sxs-lookup"><span data-stu-id="586d1-131">Block a number</span></span>

<span data-ttu-id="586d1-132">В следующем примере администратор клиента хочет заблокировать все звонки из диапазона 1 (312) 555-0000-1 (312) 555-9999.</span><span class="sxs-lookup"><span data-stu-id="586d1-132">In the following example, the tenant administrator wants to block all calls coming from the number range 1 (312) 555-0000 to 1 (312) 555-9999.</span></span> <span data-ttu-id="586d1-133">Шаблон чисел создается таким образом, что совпадают как числа в диапазоне с префиксом +, так и числа в диапазоне без префикса +.</span><span class="sxs-lookup"><span data-stu-id="586d1-133">The number pattern is created so that both numbers in range with + prefixed and numbers in the range without + prefixed are matched.</span></span> <span data-ttu-id="586d1-134">Вам не нужно включать символы – и () в номера телефонов, так как система размыкает эти символы перед соответствием.</span><span class="sxs-lookup"><span data-stu-id="586d1-134">You don’t need to include the symbols – and () in the phone numbers because the system strips these symbols before matching.</span></span>  <span data-ttu-id="586d1-135">Чтобы включить шаблон номера, для **параметра Enabled** задано true.</span><span class="sxs-lookup"><span data-stu-id="586d1-135">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="586d1-136">Чтобы отключить этот шаблон номера, задан параметр False.</span><span class="sxs-lookup"><span data-stu-id="586d1-136">To disable this specific number pattern, set the parameter to False.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

<span data-ttu-id="586d1-137">В следующем примере администратор клиента хочет заблокировать все звонки, исходят из номера 1 (412) 555-1234.</span><span class="sxs-lookup"><span data-stu-id="586d1-137">In the next example, the tenant administrator wants to block all calls coming from the number 1 (412) 555-1234.</span></span> <span data-ttu-id="586d1-138">Чтобы включить шаблон номера, для **параметра Enabled** задано true.</span><span class="sxs-lookup"><span data-stu-id="586d1-138">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

<span data-ttu-id="586d1-139">При создании шаблона шаблон добавляется как включенное по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="586d1-139">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="586d1-140">Описание — это необязательное поле для предоставления дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="586d1-140">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="586d1-141">Мы рекомендуем дать понятное имя, чтобы легко понять, почему был добавлен шаблон.</span><span class="sxs-lookup"><span data-stu-id="586d1-141">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="586d1-142">Если вы просто блокируете номера спама, можно назвать правило так же, как шаблон, по совпадению с номером, и добавьте в описание дополнительные сведения, как требуется.</span><span class="sxs-lookup"><span data-stu-id="586d1-142">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="586d1-143">Совпадения с шаблонами можно использовать с помощью регулярных выражений (Regex).</span><span class="sxs-lookup"><span data-stu-id="586d1-143">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="586d1-144">Дополнительные сведения см. [в теме Использование Regex](#using-regex).</span><span class="sxs-lookup"><span data-stu-id="586d1-144">For more information, see [Using Regex](#using-regex).</span></span>

<span data-ttu-id="586d1-145">Разрешить время репликации перед проверкой и проверкой.</span><span class="sxs-lookup"><span data-stu-id="586d1-145">Allow time for replication before you test and validate.</span></span> 

#### <a name="allow-a-number"></a><span data-ttu-id="586d1-146">Разрешить номер</span><span class="sxs-lookup"><span data-stu-id="586d1-146">Allow a number</span></span>

<span data-ttu-id="586d1-147">Вы можете разрешить звонок на номер, удалив шаблон заблокированного номера.</span><span class="sxs-lookup"><span data-stu-id="586d1-147">You can allow a number to call by removing the blocked number pattern.</span></span> <span data-ttu-id="586d1-148">В следующем примере администратор клиента хочет разрешить 1 (412) 555-1234-555-1234 для повторного вызова.</span><span class="sxs-lookup"><span data-stu-id="586d1-148">In the following example, the tenant administrator wants to allow 1 (412) 555-1234 to make calls again.</span></span>

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
<span data-ttu-id="586d1-149">Если удостоверение неизвестно, сначала найдите нужный шаблон и обратите внимание на его идентификатор с помощью **cmdlet Get-CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="586d1-149">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="586d1-150">Затем запустите **cmdlet Remove-CsInboundBlockedNumberPattern** и передайте соответствующее значение удостоверения.</span><span class="sxs-lookup"><span data-stu-id="586d1-150">Then, run the **Remove-CsInboundBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="586d1-151">Разрешить время репликации перед проверкой и проверкой.</span><span class="sxs-lookup"><span data-stu-id="586d1-151">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="586d1-152">Просмотр всех шаблонов номеров</span><span class="sxs-lookup"><span data-stu-id="586d1-152">View all number patterns</span></span>

<span data-ttu-id="586d1-153">При запуске этого cmdlet возвращается список всех заблокированных номеров, которые введены для клиента:</span><span class="sxs-lookup"><span data-stu-id="586d1-153">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="586d1-154">Используйте встроенные возможности фильтрации PowerShell, чтобы при необходимости проавнозить возвращаемую величину.</span><span class="sxs-lookup"><span data-stu-id="586d1-154">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="586d1-155">Добавление числных исключений</span><span class="sxs-lookup"><span data-stu-id="586d1-155">Add number exceptions</span></span>

<span data-ttu-id="586d1-156">Вы можете добавить исключения для заблокированных шаблонов номеров с помощью **нью-,** **get-,** **Set-** и **Remove-CsInboundExemptNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="586d1-156">You can add exceptions to blocked number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundExemptNumberPattern** cmdlets.</span></span>

- <span data-ttu-id="586d1-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) добавляет шаблон исключения числа в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="586d1-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="586d1-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) возвращает список всех шаблонов числов исключений, добавленных в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="586d1-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="586d1-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) изменяет один или несколько параметров в шаблон числового исключения в списке клиентов.</span><span class="sxs-lookup"><span data-stu-id="586d1-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="586d1-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) удаляет шаблон исключения числа из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="586d1-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="586d1-161">Примеры</span><span class="sxs-lookup"><span data-stu-id="586d1-161">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="586d1-162">Добавление числого исключения</span><span class="sxs-lookup"><span data-stu-id="586d1-162">Add a number exception</span></span>

<span data-ttu-id="586d1-163">В следующем примере администратор клиента хочет разрешить телефонные номера 1 (312) 555-8882 и 1 (312) 555-8883 для звонков в клиент, даже если эти два номера телефонов находятся в диапазоне, заблокированном в примере выше.</span><span class="sxs-lookup"><span data-stu-id="586d1-163">In the following example, the tenant administrator wants to allow the phone numbers 1 (312) 555-8882 and 1 (312) 555-8883 to make calls to the tenant, even if these two phone numbers are in the range that has been blocked in the example above.</span></span> <span data-ttu-id="586d1-164">Чтобы включить эту функцию, создается новый шаблон исключения для числа:</span><span class="sxs-lookup"><span data-stu-id="586d1-164">To enable this, a new number exception pattern is created as follows:</span></span>

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

<span data-ttu-id="586d1-165">Чтобы включить шаблон номера, для **параметра Enabled** задано true.</span><span class="sxs-lookup"><span data-stu-id="586d1-165">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="586d1-166">Чтобы отключить этот шаблон номера, задан параметр False.</span><span class="sxs-lookup"><span data-stu-id="586d1-166">To disable this specific number pattern, set the parameter to False.</span></span>


#### <a name="view-all-number-exceptions"></a><span data-ttu-id="586d1-167">Просмотр всех числных исключений</span><span class="sxs-lookup"><span data-stu-id="586d1-167">View all number exceptions</span></span>

<span data-ttu-id="586d1-168">В этом примере параметр **Identity** необязателен.</span><span class="sxs-lookup"><span data-stu-id="586d1-168">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="586d1-169">Если параметр **Identity** не указан, этот cmdlet возвращает список всех шаблонов числового исключения, указанных для клиента.</span><span class="sxs-lookup"><span data-stu-id="586d1-169">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="586d1-170">Изменение числого исключения</span><span class="sxs-lookup"><span data-stu-id="586d1-170">Modify a number exception</span></span>

<span data-ttu-id="586d1-171">С **помощью cmdlet Set-CsInboundExemptNumberPattern** можно изменить один или несколько параметров для заданного числового шаблона.</span><span class="sxs-lookup"><span data-stu-id="586d1-171">The **Set-CsInboundExemptNumberPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span> <span data-ttu-id="586d1-172">В этом примере требуется **параметр Identity.**</span><span class="sxs-lookup"><span data-stu-id="586d1-172">In this example, the **Identity** parameter is required.</span></span>
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="586d1-173">Удаление числого исключения</span><span class="sxs-lookup"><span data-stu-id="586d1-173">Remove a number exception</span></span>

<span data-ttu-id="586d1-174">При **этом из списка** клиента удаляется заданный шаблон номера.</span><span class="sxs-lookup"><span data-stu-id="586d1-174">The **Remove-CsInboundExemptNumberPattern** cmdlet will remove the given number pattern from the tenant list.</span></span> <span data-ttu-id="586d1-175">В этом примере требуется **параметр Identity.**</span><span class="sxs-lookup"><span data-stu-id="586d1-175">In this example, the **Identity** parameter is required.</span></span> 

<span data-ttu-id="586d1-176">Если удостоверение неизвестно, сначала найдите нужный шаблон и обратите внимание на его идентификатор с помощью **cmdlet Get-CsInboundExemptNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="586d1-176">If the identity isn't known, use the **Get-CsInboundExemptNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="586d1-177">Затем запустите **cmdlet Remove-CsInboundExemptNumberPattern** и передайте соответствующее значение удостоверения.</span><span class="sxs-lookup"><span data-stu-id="586d1-177">Then, run the **Remove-CsInboundExemptNumberPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="586d1-178">Разрешить время репликации перед проверкой и проверкой.</span><span class="sxs-lookup"><span data-stu-id="586d1-178"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="586d1-179">Проверка того, заблокировано ли число</span><span class="sxs-lookup"><span data-stu-id="586d1-179">Test whether a number is blocked</span></span>

<span data-ttu-id="586d1-180">Чтобы проверить, заблокировано ли число в клиенте, используйте для этого **cmdlet Test-CsInboundBlockedNumberPattern.**</span><span class="sxs-lookup"><span data-stu-id="586d1-180">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="586d1-181">Параметр **PhoneNumber** является required и должен быть числовой строкой без дополнительных символов, таких как +, - или ().</span><span class="sxs-lookup"><span data-stu-id="586d1-181">The **PhoneNumber** parameter is required, and should be a numeric string without any additional characters, such as +, - or ().</span></span> <span data-ttu-id="586d1-182">Итоговая **величина параметра IsNumberBlocked** возвращает значение True, если число заблокировано в клиенте. параметр возвращает false, если он не заблокирован.</span><span class="sxs-lookup"><span data-stu-id="586d1-182">The resulting **IsNumberBlocked** parameter returns a value of True if the number is blocked in the tenant; the parameter returns False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a><span data-ttu-id="586d1-183">Примеры</span><span class="sxs-lookup"><span data-stu-id="586d1-183">Examples</span></span>

<span data-ttu-id="586d1-184">В этих примерах можно увидеть, что номер телефона 1 (312) 555-8884 заблокирован так, как должен быть из-за того, что он находится в диапазоне заблокированных выше, а номер телефона 1 (312) 555-8883 можно звонить на основе созданного выше освобождения.</span><span class="sxs-lookup"><span data-stu-id="586d1-184">In these examples you can see that the phone number 1 (312) 555-8884 is blocked as it should be due to it being in the blocked range above, while the phone number 1 (312) 555-8883 is allowed to call as it should be based on the exemption created above.</span></span>

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

## <a name="using-regex"></a><span data-ttu-id="586d1-185">Использование Regex</span><span class="sxs-lookup"><span data-stu-id="586d1-185">Using Regex</span></span>

<span data-ttu-id="586d1-186">Соответствие шаблона для блокирования вызывающих людей делается с помощью Regex.</span><span class="sxs-lookup"><span data-stu-id="586d1-186">The pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="586d1-187">В Интернете доступно несколько инструментов для проверки совпадения с шаблоном Regex.</span><span class="sxs-lookup"><span data-stu-id="586d1-187">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="586d1-188">Если вы не знакомы с шаблонами Regex, советуем ознакомиться с основами в течение некоторого времени.</span><span class="sxs-lookup"><span data-stu-id="586d1-188">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="586d1-189">Чтобы получить ожидаемые результаты, используйте инструмент для проверки совпадений с шаблонами перед добавлением новых заблокированных номеров в клиент.</span><span class="sxs-lookup"><span data-stu-id="586d1-189">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>