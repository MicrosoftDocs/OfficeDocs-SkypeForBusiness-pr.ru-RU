---
title: Блокировать входящие звонки в Skype для бизнеса Online
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: dae0d585df2f67904712e9220f16213a2f925369
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238035"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="fe7f2-102">Блокировать входящие звонки</span><span class="sxs-lookup"><span data-stu-id="fe7f2-102">Block inbound calls</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="fe7f2-103">Skype для бизнеса Планы звонков по сети теперь поддерживают блокирование входящие вызовы из телефонной сети общего звонков (STN).</span><span class="sxs-lookup"><span data-stu-id="fe7f2-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="fe7f2-104">Эта функция позволяет определить глобальный список шаблонов номеров клиента, чтобы в списке на совпадение можно было проверить ИД звонящая для каждого входящих вызовов по ДНР в клиенте.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="fe7f2-105">Если совпадение выполнено, входящий звонок отклоняется.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="fe7f2-106">Эта функция блокировки входящие звонков работает только для входящие звонков, исходящие из ПСПС, и работает только на глобальной основе клиента.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="fe7f2-107">Она недоступна для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="fe7f2-108">Эта функция пока недоступна для прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="fe7f2-109">Заблокированные вызыватели могут немного отличаться в действиях при блокировании.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="fe7f2-110">Поведение зависит от того, как оператор связи заблокированного вызываемого звонка обрабатывает уведомление о том, что звонок не разрешен для успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="fe7f2-111">Примерами может быть сообщение о том, что звонок не может быть выполнен по телефону или просто перетассыв вызов.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="fe7f2-112">Блокировка вызовов элементов управления и сведений администратора</span><span class="sxs-lookup"><span data-stu-id="fe7f2-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="fe7f2-113">Элементы управления блокировкой номеров предоставляются только с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="fe7f2-114">Шаблоны блоков числов определяются как шаблоны регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="fe7f2-115">Порядок выражений не имеет ошеломления— первый шаблон, совпадающий с шаблоном в списке, приводит к блокированию вызова.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="fe7f2-116">На то, чтобы шаблон стал активным, может потребоваться до 24 часов, чтобы новый номер или шаблон, который был добавлен или удален в списке заблокированных вызывающих пользователей.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="fe7f2-117">Команды PowerShell, блокирующие вызовы</span><span class="sxs-lookup"><span data-stu-id="fe7f2-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="fe7f2-118">Шаблоны номеров можно управлять с ```CsInboundBlockedNumberPattern``` помощью команд , , и ```New``` ```Get``` ```Set``` ```Remove``` .</span><span class="sxs-lookup"><span data-stu-id="fe7f2-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="fe7f2-119">Вы можете управлять заданным шаблоном с помощью этих cmdlets, включая возможность переключения активации заданного шаблона.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="fe7f2-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) возвращает список всех шаблонов заблокированных номеров, добавленных в список клиентов, включая Имя, Описание, Включено (true/False) и Pattern для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="fe7f2-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) добавляет в список клиентов шаблон блокировки.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="fe7f2-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) удаляет из списка клиентов шаблон заблокированных номеров.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="fe7f2-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) изменяет один или несколько параметров шаблона заблокированных номеров в списке клиентов.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="fe7f2-124">Просмотром и активацией всей функции блокировки зовов управляется с помощью ```CsTenantBlockingCallingNumbers``` команд ```Get``` и ```Set``` .</span><span class="sxs-lookup"><span data-stu-id="fe7f2-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="fe7f2-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) возвращает параметры глобального списка заблокированных номеров, включая Enabled (True/False).</span><span class="sxs-lookup"><span data-stu-id="fe7f2-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="fe7f2-126">Существует одна глобальная политика клиента, которую нельзя изменить вручную, кроме как включить или отключить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="fe7f2-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) позволяет изменять глобальные звонки, заблокированные клиентом, на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="fe7f2-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="fe7f2-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="fe7f2-129">Блокировка номера</span><span class="sxs-lookup"><span data-stu-id="fe7f2-129">Block a number</span></span>

<span data-ttu-id="fe7f2-130">В этом примере ```-Enabled``` параметры ```-Description``` и параметры необязательны:</span><span class="sxs-lookup"><span data-stu-id="fe7f2-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="fe7f2-131">При создании шаблона шаблон добавляется как включенное по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="fe7f2-132">Описание — это необязательное поле для предоставления дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="fe7f2-133">Мы рекомендуем дать понятное имя, чтобы легко понять, почему был добавлен шаблон.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="fe7f2-134">Если вы просто блокируете номера спама, можно назвать правило так же, как шаблон, по совпадению с номером, и добавьте в описание дополнительные сведения, как требуется.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="fe7f2-135">Совпадения с шаблонами можно использовать с помощью регулярных выражений (Regex).</span><span class="sxs-lookup"><span data-stu-id="fe7f2-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="fe7f2-136">Разрешить время репликации перед проверкой и проверкой.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="fe7f2-137">Разрешить номер</span><span class="sxs-lookup"><span data-stu-id="fe7f2-137">Allow a number</span></span>

<span data-ttu-id="fe7f2-138">В этом примере ```-Identity``` параметр является требуемой:</span><span class="sxs-lookup"><span data-stu-id="fe7f2-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="fe7f2-139">Если удостоверение неизвестно, используйте его, чтобы сначала найти нужный шаблон и ```Get-CsInboundBlockedNumberPattern``` заметить удостоверение.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="fe7f2-140">Затем запустите ```Remove-CsTenantBlockedNumberPattern``` этот cmdlet и передатите соответствующее значение удостоверения.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="fe7f2-141">Разрешить время репликации перед проверкой и проверкой.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="fe7f2-142">Просмотр всех шаблонов номеров</span><span class="sxs-lookup"><span data-stu-id="fe7f2-142">View all number patterns</span></span>

<span data-ttu-id="fe7f2-143">При запуске этого cmdlet возвращается список всех заблокированных номеров, которые введены для клиента:</span><span class="sxs-lookup"><span data-stu-id="fe7f2-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="fe7f2-144">Используйте встроенные возможности фильтрации PowerShell, чтобы при необходимости проавнозить возвращаемую величину.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="fe7f2-145">Добавление числных исключений</span><span class="sxs-lookup"><span data-stu-id="fe7f2-145">Add number exceptions</span></span>

<span data-ttu-id="fe7f2-146">Вы можете добавить исключения для заблокированных шаблонов с помощью ```CsTenantBlockNumberExceptionPattern``` ```New``` команд, ```Get``` , , и ```Set``` ```Remove``` .</span><span class="sxs-lookup"><span data-stu-id="fe7f2-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="fe7f2-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) добавляет шаблон исключения числа в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="fe7f2-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) возвращает список всех шаблонов числов исключений, добавленных в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="fe7f2-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) изменяет один или несколько параметров на числовой шаблон исключения в списке клиентов.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="fe7f2-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) удаляет шаблон исключения числа из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="fe7f2-151">Примеры</span><span class="sxs-lookup"><span data-stu-id="fe7f2-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="fe7f2-152">Добавление числого исключения</span><span class="sxs-lookup"><span data-stu-id="fe7f2-152">Add a number exception</span></span>

<span data-ttu-id="fe7f2-153">В этом примере создается шаблон исключения для номеров, который по умолчанию добавляет шаблон как включенный.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="fe7f2-154">Параметры ```-Enabled``` ```-Description``` и параметры необязательны.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="fe7f2-155">Просмотр всех числных исключений</span><span class="sxs-lookup"><span data-stu-id="fe7f2-155">View all number exceptions</span></span>

<span data-ttu-id="fe7f2-156">В этом примере параметр -Identity необязателен.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="fe7f2-157">Если параметр не указан, этот cmdlet возвращает список всех шаблонов числового исключения, указанных ```-Identity``` для клиента.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="fe7f2-158">Изменение числого исключения</span><span class="sxs-lookup"><span data-stu-id="fe7f2-158">Modify a number exception</span></span>

<span data-ttu-id="fe7f2-159">В этом примере параметр -Identity является обязательным.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="fe7f2-160">Он позволяет изменить один или несколько параметров для ```Set-CsTenantBlockedNumberExceptionPattern``` идентификатора заданного числового шаблона.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="fe7f2-161">Удаление числого исключения</span><span class="sxs-lookup"><span data-stu-id="fe7f2-161">Remove a number exception</span></span>

<span data-ttu-id="fe7f2-162">В этом примере ```-Identity``` параметр является требуемой.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="fe7f2-163">Этот cmdlet удалит заданный шаблон номера из списка клиента.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="fe7f2-164">Если удостоверение неизвестно, используйте его, чтобы сначала найти нужный шаблон и ```Get-CsInboundBlockedNumberPattern``` заметить удостоверение.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="fe7f2-165">Затем запустите ```Remove-CsTenantBlockedNumberExceptionPattern``` этот cmdlet и передатите соответствующее значение удостоверения.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="fe7f2-166">Разрешить время репликации перед проверкой и проверкой.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="fe7f2-167">Проверка того, заблокировано ли число</span><span class="sxs-lookup"><span data-stu-id="fe7f2-167">Test whether a number is blocked</span></span>

<span data-ttu-id="fe7f2-168">Используйте его для проверки того, заблокирован ли номер ```Test-CsInboundBlockedNumberPattern``` в клиенте.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="fe7f2-169">В этом примере ```-Phonenumber``` необходимы ```-Tenant``` параметры и параметры.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="fe7f2-170">Параметр должен быть числовой строкой без дополнительных символов, ```-PhoneNumber``` таких как +или -.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="fe7f2-171">В TRPS это ```-Tenant parameter``` необязательный вариант.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="fe7f2-172">Результат возвращает значение True, если число заблокировано в клиенте, и False, если оно ```isNumberBlocked``` не заблокировано.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="fe7f2-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="fe7f2-173">httpResponseCode</span></span>  |<span data-ttu-id="fe7f2-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="fe7f2-174">isNumberBlocked</span></span>   |<span data-ttu-id="fe7f2-175">Errormessage</span><span class="sxs-lookup"><span data-stu-id="fe7f2-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="fe7f2-176">200</span><span class="sxs-lookup"><span data-stu-id="fe7f2-176">200</span></span>    | <span data-ttu-id="fe7f2-177">Верно</span><span class="sxs-lookup"><span data-stu-id="fe7f2-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="fe7f2-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="fe7f2-178">httpResponseCode</span></span>  |<span data-ttu-id="fe7f2-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="fe7f2-179">isNumberBlocked</span></span>   |<span data-ttu-id="fe7f2-180">Errormessage</span><span class="sxs-lookup"><span data-stu-id="fe7f2-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="fe7f2-181">200</span><span class="sxs-lookup"><span data-stu-id="fe7f2-181">200</span></span>    | <span data-ttu-id="fe7f2-182">False</span><span class="sxs-lookup"><span data-stu-id="fe7f2-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="fe7f2-183">Примечание о Regex</span><span class="sxs-lookup"><span data-stu-id="fe7f2-183">A note about Regex</span></span>

<span data-ttu-id="fe7f2-184">Как говорилось ранее, соответствие шаблона для блокирования вызывающих вызовов делается с помощью Regex.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="fe7f2-185">В Интернете доступно несколько инструментов для проверки совпадения с шаблоном Regex.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="fe7f2-186">Если вы не знакомы с шаблонами Regex, советуем ознакомиться с основами в течение некоторого времени.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="fe7f2-187">Чтобы получить ожидаемые результаты, используйте инструмент для проверки совпадений с шаблонами перед добавлением новых заблокированных номеров в клиент.</span><span class="sxs-lookup"><span data-stu-id="fe7f2-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="fe7f2-188">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fe7f2-188">Related topics</span></span>

- [<span data-ttu-id="fe7f2-189">Настройка компьютера для управления доступом Skype для бизнеса с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe7f2-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
