---
title: Блокирование входящих звонков в Microsoft Teams
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 3bb1222f0662228e5c0de7b2253cbac162571b1e
ms.sourcegitcommit: a36514c7c8ea47bde4edb09c11ff99061b1f74c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094685"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="ae525-102">Блокировать входящие звонки</span><span class="sxs-lookup"><span data-stu-id="ae525-102">Block inbound calls</span></span>

<span data-ttu-id="ae525-103">Планы прямой маршрутизации и звонков для телефонной системы поддерживают блокирование входящих звонков из коммутируемой телефонной сети, поддерживающей коммутируемую связь.</span><span class="sxs-lookup"><span data-stu-id="ae525-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="ae525-104">Эта функция позволяет определять глобальный список шаблонов для клиентов, чтобы идентификатор вызывающего абонента для каждого входящего звонка PSTN в клиент мог быть проверен относительно списка соответствия.</span><span class="sxs-lookup"><span data-stu-id="ae525-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="ae525-105">Если соответствие установлено, входящий звонок отклоняется.</span><span class="sxs-lookup"><span data-stu-id="ae525-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="ae525-106">Этот компонент блокирования входящих звонков действует только для входящих звонков, исходящих от КТСОП, и работает только на глобальной основе клиента.</span><span class="sxs-lookup"><span data-stu-id="ae525-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="ae525-107">Она недоступна отдельно для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae525-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="ae525-108">Заблокированные вызывающие абоненты могут испытывать некоторые другие проблемы, когда они заблокированы.</span><span class="sxs-lookup"><span data-stu-id="ae525-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="ae525-109">Поведение зависит от того, как перевозчик вызывающего абонента обрабатывает уведомление о том, что звонок не может быть успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="ae525-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="ae525-110">Примеры могут включать в себя сообщение о недосообщении, в котором не удается выполнить звонок или просто удалить звонок.</span><span class="sxs-lookup"><span data-stu-id="ae525-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="ae525-111">Блокировка звонков элементы управления и сведения для администраторов</span><span class="sxs-lookup"><span data-stu-id="ae525-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="ae525-112">Элементы управления администрированием для номеров блокировки предоставляются только с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae525-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="ae525-113">Шаблоны блоков чисел определяются как шаблоны регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="ae525-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="ae525-114">Порядок выражений не важен — первый шаблон, совпадающий со списком, приводит к блокировке звонка.</span><span class="sxs-lookup"><span data-stu-id="ae525-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="ae525-115">Новый номер или шаблон, добавленные или удаленные в списке заблокированных вызывающих абонентов, может занимать до 24 часов, пока шаблон не станет активным.</span><span class="sxs-lookup"><span data-stu-id="ae525-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="ae525-116">Блокировка вызова команд PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae525-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="ae525-117">Вы управляете шаблонами чисел с помощью командлетов **New**, **Get**, **Set**, **Remove**  - **CsInboundBlockedNumberPattern** .</span><span class="sxs-lookup"><span data-stu-id="ae525-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="ae525-118">Вы можете управлять данным шаблоном, используя эти командлеты, в том числе возможность переключать активацию определенного шаблона.</span><span class="sxs-lookup"><span data-stu-id="ae525-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="ae525-119">Функция [Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) возвращает список всех шаблонов заблокированных номеров, добавленных в список клиентов, включая имя, описание, разрешено (истина/ложь) и шаблон для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="ae525-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="ae525-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) добавляет шаблон заблокированного номера в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="ae525-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="ae525-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) удаляет заблокированный шаблон номера из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="ae525-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="ae525-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) изменяет один или несколько параметров заблокированного числового шаблона в списке клиентов.</span><span class="sxs-lookup"><span data-stu-id="ae525-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="ae525-123">Для просмотра и активации функции блокирования звонков используется командлет **Get**, **Set**  - **CsTenantBlockingCallingNumbers** .</span><span class="sxs-lookup"><span data-stu-id="ae525-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="ae525-124">Функция [Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) Возвращает параметры для глобального списка блокируемых номеров, включая Enabled (истина/ложь).</span><span class="sxs-lookup"><span data-stu-id="ae525-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="ae525-125">Существует единая глобальная политика клиентов, которая не может быть изменена вручную, кроме включения и отключения этой функции.</span><span class="sxs-lookup"><span data-stu-id="ae525-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="ae525-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) позволяет изменить заблокированные вызовы для глобальных клиентов на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="ae525-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="ae525-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="ae525-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="ae525-128">Блокировка номера</span><span class="sxs-lookup"><span data-stu-id="ae525-128">Block a number</span></span>

<span data-ttu-id="ae525-129">В этом примере параметры **Enabled** и **Description** являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="ae525-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="ae525-130">При создании нового узора по умолчанию добавляется шаблон с включением.</span><span class="sxs-lookup"><span data-stu-id="ae525-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="ae525-131">Описание — необязательное поле для предоставления дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="ae525-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="ae525-132">Рекомендуем дать понятное имя, чтобы легко понять, почему был добавлен шаблон.</span><span class="sxs-lookup"><span data-stu-id="ae525-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="ae525-133">В случае простого блокирования нежелательной почты рекомендуется присвоить правилу имя, совпадающее с шаблоном числа, и при необходимости добавить дополнительные сведения в описание.</span><span class="sxs-lookup"><span data-stu-id="ae525-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="ae525-134">Шаблоны сопоставлены с помощью регулярных выражений (Regex).</span><span class="sxs-lookup"><span data-stu-id="ae525-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="ae525-135">Разрешите время репликации, прежде чем вы проверите и проверите.</span><span class="sxs-lookup"><span data-stu-id="ae525-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="ae525-136">Разрешение номера</span><span class="sxs-lookup"><span data-stu-id="ae525-136">Allow a number</span></span>

<span data-ttu-id="ae525-137">В этом примере параметр **Identity** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ae525-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="ae525-138">Если идентификация неизвестна, используйте командлет **Get-CsInboundBlockedNumberPattern** , чтобы сначала найти правильный шаблон и заметку его удостоверения.</span><span class="sxs-lookup"><span data-stu-id="ae525-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="ae525-139">Затем выполните командлет **Remove-CsTenantBlockedNumberPattern** и передайте нужное значение удостоверения.</span><span class="sxs-lookup"><span data-stu-id="ae525-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="ae525-140">Разрешите время репликации, прежде чем вы проверите и проверите.</span><span class="sxs-lookup"><span data-stu-id="ae525-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="ae525-141">Просмотр всех числовых шаблонов</span><span class="sxs-lookup"><span data-stu-id="ae525-141">View all number patterns</span></span>

<span data-ttu-id="ae525-142">Выполнение этого командлета возвращает список всех заблокированных номеров, введенных для клиента:</span><span class="sxs-lookup"><span data-stu-id="ae525-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="ae525-143">Используйте встроенные возможности фильтрации PowerShell для синтаксического анализа возвращаемых значений в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="ae525-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="ae525-144">Добавление исключений номеров</span><span class="sxs-lookup"><span data-stu-id="ae525-144">Add number exceptions</span></span>

<span data-ttu-id="ae525-145">Вы можете добавлять исключения в шаблоны заблокированных номеров с помощью командлетов **New**, **Get**, **Set**, **Remove**  - **CsTenantBlockNumberExceptionPattern** .</span><span class="sxs-lookup"><span data-stu-id="ae525-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="ae525-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) добавляет шаблон исключения номера в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="ae525-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="ae525-147">Функция [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) возвращает список всех шаблонов исключений номеров, добавленных в список клиентов.</span><span class="sxs-lookup"><span data-stu-id="ae525-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="ae525-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) изменяет один или несколько параметров в шаблон исключения для номера в списке клиентов.</span><span class="sxs-lookup"><span data-stu-id="ae525-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="ae525-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) удаляет шаблон исключения номера из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="ae525-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="ae525-150">Примеры</span><span class="sxs-lookup"><span data-stu-id="ae525-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="ae525-151">Добавление исключения числа</span><span class="sxs-lookup"><span data-stu-id="ae525-151">Add a number exception</span></span>

<span data-ttu-id="ae525-152">В этом примере создается шаблон исключения для нового номера, который по умолчанию будет добавлен как включенный.</span><span class="sxs-lookup"><span data-stu-id="ae525-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="ae525-153">Параметры **Enabled** и **Description** являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="ae525-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="ae525-154">Просмотр всех исключений для номеров</span><span class="sxs-lookup"><span data-stu-id="ae525-154">View all number exceptions</span></span>

<span data-ttu-id="ae525-155">В этом примере параметр **Identity** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ae525-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="ae525-156">Если параметр **Identity** не указан, этот командлет возвращает список всех шаблонов исключений количества, введенных для клиента.</span><span class="sxs-lookup"><span data-stu-id="ae525-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="ae525-157">Изменение числа исключений</span><span class="sxs-lookup"><span data-stu-id="ae525-157">Modify a number exception</span></span>

<span data-ttu-id="ae525-158">В этом примере параметр **Identity** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ae525-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="ae525-159">Командлет **Set-CsTenantBlockedNumberExceptionPattern** позволяет изменить один или несколько параметров для определенного удостоверения шаблона номера.</span><span class="sxs-lookup"><span data-stu-id="ae525-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="ae525-160">Удаление исключения числа</span><span class="sxs-lookup"><span data-stu-id="ae525-160">Remove a number exception</span></span>

<span data-ttu-id="ae525-161">В этом примере параметр **Identity** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ae525-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="ae525-162">Этот командлет удалит указанный шаблон номера из списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="ae525-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="ae525-163">Если идентификация неизвестна, используйте командлет **Get-CsInboundBlockedNumberPattern** , чтобы сначала найти правильный шаблон и заметку его удостоверения.</span><span class="sxs-lookup"><span data-stu-id="ae525-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="ae525-164">Затем выполните командлет **Remove-CsTenantBlockedNumberExceptionPattern** и передайте нужное значение удостоверения.</span><span class="sxs-lookup"><span data-stu-id="ae525-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="ae525-165">Разрешите время репликации, прежде чем вы проверите и проверите.</span><span class="sxs-lookup"><span data-stu-id="ae525-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="ae525-166">Проверка того, заблокировано ли число</span><span class="sxs-lookup"><span data-stu-id="ae525-166">Test whether a number is blocked</span></span>

<span data-ttu-id="ae525-167">Используйте командлет **Test-CsInboundBlockedNumberPattern** , чтобы проверить, заблокировано ли число в клиенте.</span><span class="sxs-lookup"><span data-stu-id="ae525-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="ae525-168">В этом примере требуются параметры **заданный** и **клиента** .</span><span class="sxs-lookup"><span data-stu-id="ae525-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="ae525-169">Параметр **заданный** должен быть числовой строкой без дополнительных знаков, таких как + и-.</span><span class="sxs-lookup"><span data-stu-id="ae525-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="ae525-170">В TRPS параметр " **клиент** " является необязательным.</span><span class="sxs-lookup"><span data-stu-id="ae525-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="ae525-171">Конечный параметр **isNumberBlocked** возвращает значение true, если номер заблокирован в клиенте, и значение false, если оно не заблокировано.</span><span class="sxs-lookup"><span data-stu-id="ae525-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="ae525-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="ae525-172">httpResponseCode</span></span>  |<span data-ttu-id="ae525-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="ae525-173">isNumberBlocked</span></span>   |<span data-ttu-id="ae525-174">Ошибк</span><span class="sxs-lookup"><span data-stu-id="ae525-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ae525-175">200</span><span class="sxs-lookup"><span data-stu-id="ae525-175">200</span></span>    | <span data-ttu-id="ae525-176">Верно</span><span class="sxs-lookup"><span data-stu-id="ae525-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="ae525-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="ae525-177">httpResponseCode</span></span>  |<span data-ttu-id="ae525-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="ae525-178">isNumberBlocked</span></span>   |<span data-ttu-id="ae525-179">Ошибк</span><span class="sxs-lookup"><span data-stu-id="ae525-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ae525-180">200</span><span class="sxs-lookup"><span data-stu-id="ae525-180">200</span></span>    | <span data-ttu-id="ae525-181">False</span><span class="sxs-lookup"><span data-stu-id="ae525-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="ae525-182">Примечание о регулярном выражении</span><span class="sxs-lookup"><span data-stu-id="ae525-182">A note about Regex</span></span>

<span data-ttu-id="ae525-183">Как упоминалось ранее, соответствие шаблону для вызывающих абонентов выполняется с помощью регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="ae525-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="ae525-184">Для проверки соответствия шаблону регулярного выражения в Интернете доступно несколько средств.</span><span class="sxs-lookup"><span data-stu-id="ae525-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="ae525-185">Если вы не знакомы с шаблонами регулярных выражений, мы рекомендуем вам ознакомиться с основными принципами.</span><span class="sxs-lookup"><span data-stu-id="ae525-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="ae525-186">Чтобы убедиться в том, что вы получаете ожидаемые результаты, используйте инструмент для проверки соответствия шаблону, прежде чем добавлять новые заблокированные номера для поиска в клиенте.</span><span class="sxs-lookup"><span data-stu-id="ae525-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
