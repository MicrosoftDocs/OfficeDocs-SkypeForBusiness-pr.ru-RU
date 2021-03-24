---
title: Планирование политик расположения для Skype для бизнес-сервера
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Ознакомьтесь с этой темой, чтобы узнать, как спланировать политики расположения для расширенного развертывания экстренных служб (E9-1-1) в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 3d9c574d18351594d9773f02770e960c993ae401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101455"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="9d365-103">Планирование политик расположения для Skype для бизнес-сервера</span><span class="sxs-lookup"><span data-stu-id="9d365-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="9d365-104">Ознакомьтесь с этой темой, чтобы узнать, как спланировать политики расположения для расширенного развертывания экстренных служб (E9-1-1) в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="9d365-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9d365-105">Skype для бизнеса Server теперь поддерживает конфигурацию нескольких номеров экстренных служб для клиента.</span><span class="sxs-lookup"><span data-stu-id="9d365-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="9d365-106">Если вы хотите настроить несколько номеров экстренных служб, необходимо следовать сведениям в Plan [for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) и настроить несколько номеров экстренных служб в Skype для [бизнеса](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="9d365-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="9d365-107">Политики расположения создаются с помощью панели управления Skype для бизнеса или с помощью группы [New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9d365-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="9d365-108">Дополнительные сведения см. в [дополнительных сведениях о создании политик расположения в Skype для бизнеса Server.](../../deploy/deploy-enterprise-voice/create-location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9d365-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="9d365-109">Все политики расположений содержат следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="9d365-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="9d365-110">**Включить расширенный 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="9d365-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="9d365-111">Когда это значение включено, клиент включен для расширенных экстренных служб (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="9d365-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="9d365-112">Когда клиент регистрируется, он пытается получить расположение из службы информации о расположении и будет включать сведения о расположении в рамках экстренного вызова.</span><span class="sxs-lookup"><span data-stu-id="9d365-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="9d365-113">**Location**</span><span class="sxs-lookup"><span data-stu-id="9d365-113">**Location**</span></span>
  
<span data-ttu-id="9d365-114">Этот параметр используется только в том случае, **если включена система Enable Enhanced 9-1-1.**</span><span class="sxs-lookup"><span data-stu-id="9d365-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="9d365-115">Вы можете настроить параметр **Location,** чтобы определить поведение клиента следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9d365-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="9d365-116">Если задать значение **Нет**, расположение не будет запрашиваться у пользователя.</span><span class="sxs-lookup"><span data-stu-id="9d365-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="9d365-117">Если задать значение **Да**, расположение будет запрашиваться у пользователя, но он сможет отклонить запрос.</span><span class="sxs-lookup"><span data-stu-id="9d365-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="9d365-118">Если задать для параметра значение **Заявление об отказе**, расположение будет запрашиваться у пользователя и при попытке отклонить запрос будет выводиться уведомление об отказе.</span><span class="sxs-lookup"><span data-stu-id="9d365-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="9d365-119">В любом случае пользователь сможет использовать клиент.</span><span class="sxs-lookup"><span data-stu-id="9d365-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9d365-p105">Текст заявления не отображается, если пользовать вручную вводит расположение, прежде чем получить доступ к E9-1-1. Обновленный текст заявления об отказе не будет отображаться для пользователей, которые уже просмотрели заявление.</span><span class="sxs-lookup"><span data-stu-id="9d365-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="9d365-122">**Enhanced Emergency Service Disclaimer** (Расширенное заявление об отказе аварийных служб)</span><span class="sxs-lookup"><span data-stu-id="9d365-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="9d365-123">Этот параметр задает заявление об отказе, которое будет отображаться для пользователей, если они отклоняют запрос расположения.</span><span class="sxs-lookup"><span data-stu-id="9d365-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="9d365-124">В Skype для бизнеса Server можно использовать политику расположения для набора различных отказов для разных локалей или различных наборов пользователей.</span><span class="sxs-lookup"><span data-stu-id="9d365-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="9d365-125">**Строка экстренного набора (номер телефона E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="9d365-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="9d365-126">Эта строка набора (менее ведущее "+", но в том числе любая нормализация, сделанная в телефонной строке пользователя) означает, что вызов является экстренным вызовом.</span><span class="sxs-lookup"><span data-stu-id="9d365-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="9d365-127">Параметр **Строка набора аварийного номера** указывает клиенту на необходимость включения в вызов данных о расположении и обратном вызове.</span><span class="sxs-lookup"><span data-stu-id="9d365-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d365-128">Если в организации не используется префикс внешнего доступа к строке, не нужно создавать соответствующее правило нормализации dial plan, которое добавляет строку "+" к строке 911 до отправки вызова в исходящие маршруты на сервере, на сервере под управлением Skype для бизнеса Server; клиент Skype для бизнеса автоматически предопластит "+" в результате политики расположения.</span><span class="sxs-lookup"><span data-stu-id="9d365-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="9d365-129">Однако, если на вашем сайте используется префикс внешнего доступа, необходимо добавить правило нормализации в применимую политику Dial Plan, которая размыла префикс внешнего доступа и добавила "+".</span><span class="sxs-lookup"><span data-stu-id="9d365-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="9d365-130">Например, если в вашем расположении используется префикс внешнего доступа 9 и пользователь набирает 9 911 для экстренного вызова, клиент будет использовать политику dial Plan, чтобы нормализовать ее до +911, прежде чем набраный номер будет оцениваться маршрутами в профиле расположения вызываемого.</span><span class="sxs-lookup"><span data-stu-id="9d365-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="9d365-131">**Маски строки экстренного набора (маска набора E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="9d365-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="9d365-132">Разделенный полуколоном список строк набора, который переводится в указанную строку **экстренного набора.**</span><span class="sxs-lookup"><span data-stu-id="9d365-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="9d365-133">Например, может потребоваться добавить 112, который является номером службы экстренной помощи для большей части Европы.</span><span class="sxs-lookup"><span data-stu-id="9d365-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="9d365-134">Пользователь Skype для бизнеса из Европы может не знать, что 911 — это номер экстренной службы США, но он может набрать 112 и получить тот же результат.</span><span class="sxs-lookup"><span data-stu-id="9d365-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="9d365-135">Как и в случае со строкой экстренного набора, не включите перед каждым номером строку "+", и если вы используете внешние коды доступа к строкам, убедитесь, что в политике dial Plan пользователя существуют правила нормализации, чтобы снять цифру кода доступа.</span><span class="sxs-lookup"><span data-stu-id="9d365-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="9d365-136">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="9d365-136">**PSTN usage**</span></span>
  
<span data-ttu-id="9d365-137">Имя режима работы с ТСОП, содержащее пути маршрутизации, определяющие, через какую магистраль SIP, шлюз ТСОП или шлюз ELIN будут передаваться звонки в аварийные службы.</span><span class="sxs-lookup"><span data-stu-id="9d365-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d365-138">Политика расположения может быть назначена только одному использованию.</span><span class="sxs-lookup"><span data-stu-id="9d365-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="9d365-139">Это использование PSTN переопределяет использование ПСПС, назначенное политике голосовой связи пользователя, но применяется только к вызовам, размещенным в строке экстренного набора или к одной из масок строки экстренного набора.</span><span class="sxs-lookup"><span data-stu-id="9d365-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="9d365-140">**Notification URI** (URI уведомления)</span><span class="sxs-lookup"><span data-stu-id="9d365-140">**Notification URI**</span></span>
  
<span data-ttu-id="9d365-p111">Задает один или несколько URI SIP персонала службы безопасности, которые получают уведомление в виде мгновенного сообщения при отправке звонка в аварийную службу. Этот параметр поддерживает группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="9d365-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="9d365-143">**Conference URI** (URI конференции)</span><span class="sxs-lookup"><span data-stu-id="9d365-143">**Conference URI**</span></span>
  
<span data-ttu-id="9d365-144">Задает прямой внутренний номер (как правило, номер службы безопасности), по которому выполнятся подключение конференц-связи при отправке звонка в аварийную службу.</span><span class="sxs-lookup"><span data-stu-id="9d365-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="9d365-145">**Режим конференции**</span><span class="sxs-lookup"><span data-stu-id="9d365-145">**Conference Mode**</span></span>
  
<span data-ttu-id="9d365-146">Указывает, будет ли URI конференции включаться в вызов аварийной службы в режиме односторонней или двусторонней связи.</span><span class="sxs-lookup"><span data-stu-id="9d365-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="9d365-147">**Location Refresh Interval** (Интервал обновления данных расположения)</span><span class="sxs-lookup"><span data-stu-id="9d365-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="9d365-148">Указывает время (в часах) между запросами клиента на обновление расположения из службы информации о расположении.</span><span class="sxs-lookup"><span data-stu-id="9d365-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="9d365-149">Значение можно задать в диапазоне от 1 до 12.</span><span class="sxs-lookup"><span data-stu-id="9d365-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="9d365-150">Значение по умолчанию: 4 часа.</span><span class="sxs-lookup"><span data-stu-id="9d365-150">The default value is 4.</span></span>
