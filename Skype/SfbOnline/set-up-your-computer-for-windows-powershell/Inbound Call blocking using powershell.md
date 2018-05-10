---
title: Входящий звонок, блокировка с помощью Powershell для Скайп для бизнеса нахождении в сети
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 05/07/2018
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Использование PowerShell для управления входящего вызова блокировки в Скайп для бизнеса в Интернет.
ms.openlocfilehash: 10aa92233f2a804edffef8bf6d5b8e5dd7746b06
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2018
---
# <a name="inbound-pstn-call-blocking-for-calling-plans"></a><span data-ttu-id="2dfd7-103">Входящий звонок через ТСОП блокировки для Тарифные планы</span><span class="sxs-lookup"><span data-stu-id="2dfd7-103">Inbound PSTN Call Blocking for Calling Plans</span></span>

<span data-ttu-id="2dfd7-104">Скайп для бизнеса планы Online вызов теперь поддерживает блокирование для входящих вызовов из телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="2dfd7-104">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="2dfd7-105">Эта функция позволяет клиента глобального списка шаблоны номеров можно определить, поэтому Звонящего каждого входящего вызова ТСОП для клиента могут быть установлено списка для соответствия.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-105">This feature allows a tenant global list of number patterns to be defined, so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="2dfd7-106">Входящий звонок отклоняется, если совпадение.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-106">If a match is made, an incoming call is rejected.</span></span> 

<span data-ttu-id="2dfd7-107">Эта функция блокировки входящего вызова работает только на входящие вызовы из ТСОП и работает только с глобально клиента и недоступен на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-107">This inbound call blocking feature only works on inbound calls originating from the PSTN and only works on a tenant global basis and is not available on a per user basis.</span></span>

<span data-ttu-id="2dfd7-108">Этот компонент еще не доступен для маршрутизации прямой.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-108">This feature is not yet available for Direct Routing.</span></span>

><span data-ttu-id="2dfd7-109">[Примечание] Заблокированных звонящих могут возникать несколько различных типов поведения, когда они были заблокированы.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-109">[Note] Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="2dfd7-110">Поведение зависит как поставщика заблокированных вызывающего абонента обрабатывает уведомление, вызов не может быть успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-110">The behavior will be based on how the blocked caller’s carrier handles the notification that the call is not allowed to be successfully completed.</span></span> <span data-ttu-id="2dfd7-111">Могут включать поставщика сообщение о том, не удается выполнить вызов с набором номера, или просто Завершение звонка.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-111">Examples may include a carrier message stating the call cannot be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="2dfd7-112">Вызов блокировки информацию и элементы управления администратора</span><span class="sxs-lookup"><span data-stu-id="2dfd7-112">Call Blocking Admin Controls and Information</span></span>
<span data-ttu-id="2dfd7-113">Элементы управления администратора для блокировки номеров, предоставляются только с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="2dfd7-114">Шаблоны номеров блока определены как шаблоны регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="2dfd7-115">Порядок выражений не имеет значения — первый шаблон сопоставления в списке приведет вызова окон.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-115">The order of the expressions is unimportant – the first pattern matched in the list will result in the call being blocked.</span></span> <span data-ttu-id="2dfd7-116">Новый номер или шаблон добавить или удалить в списке заблокированных списка абонентов может потребоваться до 24 часов для для шаблона станет активным.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-116">A new number or pattern added or removed in the blocked callers list may take up to 24 hours to for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="2dfd7-117">Блокировка команды PowerShell вызовов</span><span class="sxs-lookup"><span data-stu-id="2dfd7-117">Call Blocking PowerShell Commands</span></span>

<span data-ttu-id="2dfd7-118">*InboundBlockedNumberPattern* Шаблоны номеров управляются с помощью команды *CsInboundBlockedNumberPattern* **New**, **Получение**, **Установка**и **Удаление**.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-118">*InboundBlockedNumberPattern* Number patterns are managed via the *CsInboundBlockedNumberPattern* commands **New**, **Get**, **Set**, and **Remove**.</span></span>  

<span data-ttu-id="2dfd7-119">Данному шаблону можно управлять с помощью этих командлетов, включая возможность включения и отключения активации заданному шаблону.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="2dfd7-120">*Get-CsInboundBlockedNumberPattern* Возвращает список всех заблокированных шаблоны номеров, добавлен в список клиента, включая имя, описание, Enabled (ИСТИНА/ЛОЖЬ) и шаблон для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-120">*Get-CsInboundBlockedNumberPattern* Returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="2dfd7-121">*Новый CsInboundBlockedNumberPattern* Добавляет шаблон номера для заблокированных списка клиентов.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-121">*New-CsInboundBlockedNumberPattern* Adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="2dfd7-122">*Remove-CsInboundBlockedNumberPattern* Удаляет заблокированные шаблон номера в списке клиента.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-122">*Remove-CsInboundBlockedNumberPattern* Removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="2dfd7-123">*Set-CsInboundBlockedNumberPattern* Изменяет один или несколько параметров заблокированных шаблон номера в списке клиента.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-123">*Set-CsInboundBlockedNumberPattern* Modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>
- <span data-ttu-id="2dfd7-124">*TenantBlockedCallingNumbers* Просмотр и активация компонента блокировки всей продолжительности вызова осуществляется через CsTenantBlockingCallingNumbers команд получения и задания.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-124">*TenantBlockedCallingNumbers* The viewing and activation of the entire call blocking feature is managed via the CsTenantBlockingCallingNumbers commands Get and Set.</span></span> 
- <span data-ttu-id="2dfd7-125">*Get-CsTenantBlockedCallingNumbers* Возвращает параметры для глобального черный список номеров, включая Enabled (ИСТИНА/ЛОЖЬ).</span><span class="sxs-lookup"><span data-stu-id="2dfd7-125">*Get-CsTenantBlockedCallingNumbers* Returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="2dfd7-126">Еще одним клиентом глобального политика, которое нельзя изменить вручную не включать функцию полностью и отключение.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-126">There is a single global tenant policy that cannot be modified manually other than to turn the feature completely on/off.</span></span>
- <span data-ttu-id="2dfd7-127">*Set-CsTenantBlockedCallingNumbers* Позволяет изменить звонки глобального клиента заблокировано включить или выключить на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-127">*Set-CsTenantBlockedCallingNumbers* Allows modifying the global tenant blocked calls to be turned on/off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="2dfd7-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="2dfd7-128">Examples</span></span>
#### <a name="blocking-a-number"></a><span data-ttu-id="2dfd7-129">Блокировка номер</span><span class="sxs-lookup"><span data-stu-id="2dfd7-129">Blocking a Number</span></span>

<span data-ttu-id="2dfd7-130">В этом примере - включен и — описание параметров являются необязательными:</span><span class="sxs-lookup"><span data-stu-id="2dfd7-130">In this example, the -Enabled and -Description parameters are optional:</span></span>

`New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”`

 <span data-ttu-id="2dfd7-131">Создание нового шаблона по умолчанию добавит всегда используется шаблон как включенные и приводится описание и необязательные поля, чтобы предоставить дополнительную информацию.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-131">Creating a new pattern will by default add the pattern as enabled, and the description is always and optional field to provide more information.</span></span> 

<span data-ttu-id="2dfd7-132">Рекомендуется предоставить подходящее имя, чтобы понять, почему был добавлен шаблон.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="2dfd7-133">В случае просто блокирование нежелательной почты номера, считается именования правило же, как шаблон номера, совпадающих и добавить дополнительные сведения в поле Описание при необходимости.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-133">In the case of simply blocking spam numbers, considered naming the rule the same as the number pattern being matched, and add additional information in the description as required.</span></span>

<span data-ttu-id="2dfd7-134">Шаблоны сопоставляются с помощью регулярных выражений (regex).</span><span class="sxs-lookup"><span data-stu-id="2dfd7-134">Patterns are matched using Regular Expressions (regex).</span></span> <span data-ttu-id="2dfd7-135">Разрешить для репликации время до тестирования и проверки.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-135">Allow for replication time before testing and validating.</span></span>

#### <a name="allowing-a-number"></a><span data-ttu-id="2dfd7-136">Разрешение номер</span><span class="sxs-lookup"><span data-stu-id="2dfd7-136">Allowing a Number</span></span>

<span data-ttu-id="2dfd7-137">В этом примере параметр identity при необходимости (is?):`Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`</span><span class="sxs-lookup"><span data-stu-id="2dfd7-137">In this example, the identity parameter if (is?) required: `Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`</span></span>
 
<span data-ttu-id="2dfd7-138">Если идентификатор неизвестен, командлет *Get-CsInb undBlockedNumberPattern* для сначала найдите правильному шаблону и запишите идентификатор.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-138">If the Identity is not known, use the *Get-CsInb undBlockedNumberPattern* cmdlet to first locate the proper pattern and note the Identity.</span></span> <span data-ttu-id="2dfd7-139">Затем выполните командлет, *Удаление* и передайте соответствующее значение Identity.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-139">Then, run the *Remove* cmdlet and pass the appropriate Identity value.</span></span>

<span data-ttu-id="2dfd7-140">Разрешить для репликации время до тестирования и проверки.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-140">Allow for replication time before testing and validating.</span></span>
#### <a name="view-all-number-patterns"></a><span data-ttu-id="2dfd7-141">Просмотреть все шаблоны номер</span><span class="sxs-lookup"><span data-stu-id="2dfd7-141">View all Number Patterns</span></span>
<span data-ttu-id="2dfd7-142">Выполнение этого командлета возвращает список всех введенных заблокировано номеров для клиента:`Get-CsInboundBlockedNumberPattern`</span><span class="sxs-lookup"><span data-stu-id="2dfd7-142">Running this cmdlet will return a list of all entered blocked numbers for a tenant: `Get-CsInboundBlockedNumberPattern`</span></span>

<span data-ttu-id="2dfd7-143">Используйте встроенные возможности фильтрации PowerShell для синтаксического анализа возвращаемых значений при необходимости.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

#### <a name="a-note-on-regex"></a><span data-ttu-id="2dfd7-144">Обратите внимание на регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="2dfd7-144">A Note on Regex</span></span>
<span data-ttu-id="2dfd7-145">Как упоминалось ранее, шаблоны для блокировки абонентов выполняется с помощью регулярных выражений (regex).</span><span class="sxs-lookup"><span data-stu-id="2dfd7-145">As stated earlier, the pattern matching for blocking callers is done by using Regular Expressions (regex).</span></span> <span data-ttu-id="2dfd7-146">Существует несколько средств доступен через Интернет для проверки соответствия шаблону регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-146">There are multiple tools available online to help validate a regex pattern match.</span></span> <span data-ttu-id="2dfd7-147">Если вы не знакомы с помощью шаблонов регулярных выражений, рекомендуется выполнить некоторое время, чтобы ознакомиться с основными функциями и убедитесь, что вы получаете ожидаемые результаты использовать средство для проверки соответствия шаблону, перед добавлением нового заблокированных номеров совпадений в клиент.</span><span class="sxs-lookup"><span data-stu-id="2dfd7-147">If you are not familiar with regex patterns, we recommend that you take some time to familiarize yourself with the basics and to make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="2dfd7-148">See also</span><span class="sxs-lookup"><span data-stu-id="2dfd7-148">Related topics</span></span>
[<span data-ttu-id="2dfd7-149">Настройка компьютера для Скайп online управления бизнес-процессов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2dfd7-149">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)