---
title: Планирование политик расположения для Skype для бизнеса Server
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
description: В этом разделе вы узнаете, как спланировать политики расположения для расширенного развертывания экстренных служб (E9-1-1) в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 1e89c2f0ea9d5115b29e9bc6d77b3863bb11888c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825539"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="60a7b-103">Планирование политик расположения для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="60a7b-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="60a7b-104">В этом разделе вы узнаете, как спланировать политики расположения для расширенного развертывания экстренных служб (E9-1-1) в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="60a7b-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="60a7b-105">Skype для бизнеса Server теперь поддерживает конфигурацию нескольких номеров экстренных служб для клиента.</span><span class="sxs-lookup"><span data-stu-id="60a7b-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="60a7b-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="60a7b-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="60a7b-107">Политики расположения создаются с помощью панели управления Skype для бизнеса или с помощью cmdlet [New-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="60a7b-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="60a7b-108">Дополнительные сведения см. в дополнительных сведениях о создании [политик расположения в Skype для бизнеса Server.](../../deploy/deploy-enterprise-voice/create-location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="60a7b-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="60a7b-109">Все политики расположений содержат следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="60a7b-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="60a7b-110">**Включить Enhanced 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="60a7b-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="60a7b-111">Если это значение включено, клиент получает расширенные экстренные службы (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="60a7b-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="60a7b-112">Когда клиент регистрируется, он пытается получить расположение из службы сведений о расположении и будет включать сведения о расположении в качестве части экстренного вызова.</span><span class="sxs-lookup"><span data-stu-id="60a7b-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="60a7b-113">**Location**</span><span class="sxs-lookup"><span data-stu-id="60a7b-113">**Location**</span></span>
  
<span data-ttu-id="60a7b-114">Этот параметр используется, только если включена возможность **включения enhanced 9-1-1.**</span><span class="sxs-lookup"><span data-stu-id="60a7b-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="60a7b-115">Вы можете настроить параметр **"Расположение",** чтобы определить поведение клиента следующим образом:</span><span class="sxs-lookup"><span data-stu-id="60a7b-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="60a7b-116">Если задать значение **Нет**, расположение не будет запрашиваться у пользователя.</span><span class="sxs-lookup"><span data-stu-id="60a7b-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="60a7b-117">Если задать значение **Да**, расположение будет запрашиваться у пользователя, но он сможет отклонить запрос.</span><span class="sxs-lookup"><span data-stu-id="60a7b-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="60a7b-118">Если задать для параметра значение **Заявление об отказе**, расположение будет запрашиваться у пользователя и при попытке отклонить запрос будет выводиться уведомление об отказе.</span><span class="sxs-lookup"><span data-stu-id="60a7b-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="60a7b-119">В любом случае пользователь сможет использовать клиент.</span><span class="sxs-lookup"><span data-stu-id="60a7b-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="60a7b-p105">Текст заявления не отображается, если пользовать вручную вводит расположение, прежде чем получить доступ к E9-1-1. Обновленный текст заявления об отказе не будет отображаться для пользователей, которые уже просмотрели заявление.</span><span class="sxs-lookup"><span data-stu-id="60a7b-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="60a7b-122">**Enhanced Emergency Service Disclaimer** (Расширенное заявление об отказе аварийных служб)</span><span class="sxs-lookup"><span data-stu-id="60a7b-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="60a7b-123">Этот параметр задает заявление об отказе, которое будет отображаться для пользователей, если они отклоняют запрос расположения.</span><span class="sxs-lookup"><span data-stu-id="60a7b-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="60a7b-124">В Skype для бизнеса Server можно использовать политику расположения, чтобы установить разные оговорки для разных региональных звонков или разных наборов пользователей.</span><span class="sxs-lookup"><span data-stu-id="60a7b-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="60a7b-125">**Строка набора номера экстренной службы (номер E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="60a7b-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="60a7b-126">Эта строка набора номера (за исключением ведущего "+", но включая нормализацию, сделанную телефонной планом пользователя) означает, что звонок является экстренным.</span><span class="sxs-lookup"><span data-stu-id="60a7b-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="60a7b-127">Параметр **Строка набора аварийного номера** указывает клиенту на необходимость включения в вызов данных о расположении и обратном вызове.</span><span class="sxs-lookup"><span data-stu-id="60a7b-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60a7b-128">Если в организации не используется префикс доступа к внешней линии, нет необходимости создавать соответствующее правило нормализации телефонной плана, которое добавляет "+" в строку 911 перед отправкой вызова в исходящие маршруты на сервере Skype для бизнеса Server; В результате политики расположения клиент Skype для бизнеса автоматически включит "+".</span><span class="sxs-lookup"><span data-stu-id="60a7b-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="60a7b-129">Однако если на сайте используется префикс внешнего доступа, необходимо добавить правило нормализации в применимую политику dial plan, которая убирает префикс внешнего доступа и добавляет "+".</span><span class="sxs-lookup"><span data-stu-id="60a7b-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="60a7b-130">Например, если в вашем расположении используется префикс внешнего доступа 9, а пользователь набирает номер 9 911 для экстренного вызова, клиент будет использовать политику телефонной связи, чтобы нормализовать этот номер до +911, прежде чем набраный номер будет оценен маршрутами в профиле местоположения вызываемого.</span><span class="sxs-lookup"><span data-stu-id="60a7b-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="60a7b-131">**Маски строки набора экстренного номера (маска набора E9-1-1)**</span><span class="sxs-lookup"><span data-stu-id="60a7b-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="60a7b-132">Список строк набора, разделенных за заданным с заданным заданным списком, который преобразуется в указанную строку набора номера для экстренного **экстренного номера.**</span><span class="sxs-lookup"><span data-stu-id="60a7b-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="60a7b-133">Например, можно добавить номер экстренной службы для большей части Европы.</span><span class="sxs-lookup"><span data-stu-id="60a7b-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="60a7b-134">Пользователь Skype для бизнеса из Европы может не знать, что 911 является номером экстренной службы США, но он может набрать номер 112 и получить такой же результат.</span><span class="sxs-lookup"><span data-stu-id="60a7b-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="60a7b-135">Как и в случае со строкой набора номера экстренной службы, не включайте знак "+" перед каждым номером, а если вы используете коды доступа к внешней линии, убедитесь, что в политике телефонной линии пользователя существуют правила нормализации, которые отключат цифру кода доступа.</span><span class="sxs-lookup"><span data-stu-id="60a7b-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="60a7b-136">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="60a7b-136">**PSTN usage**</span></span>
  
<span data-ttu-id="60a7b-137">Имя режима работы с ТСОП, содержащее пути маршрутизации, определяющие, через какую магистраль SIP, шлюз ТСОП или шлюз ELIN будут передаваться звонки в аварийные службы.</span><span class="sxs-lookup"><span data-stu-id="60a7b-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60a7b-138">Политика расположения может быть назначена только одному использованию.</span><span class="sxs-lookup"><span data-stu-id="60a7b-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="60a7b-139">Этот режим работы с STN переопределяет режимы работы с PSTN, которые назначены политике голосовой связи пользователя, но применяется только к вызовам, размещенным в строке набора номера экстренного вызова или одной из масок строки набора номера для экстренного вызова.</span><span class="sxs-lookup"><span data-stu-id="60a7b-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="60a7b-140">**Notification URI** (URI уведомления)</span><span class="sxs-lookup"><span data-stu-id="60a7b-140">**Notification URI**</span></span>
  
<span data-ttu-id="60a7b-p111">Задает один или несколько URI SIP персонала службы безопасности, которые получают уведомление в виде мгновенного сообщения при отправке звонка в аварийную службу. Этот параметр поддерживает группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="60a7b-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="60a7b-143">**Conference URI** (URI конференции)</span><span class="sxs-lookup"><span data-stu-id="60a7b-143">**Conference URI**</span></span>
  
<span data-ttu-id="60a7b-144">Задает прямой внутренний номер (как правило, номер службы безопасности), по которому выполнятся подключение конференц-связи при отправке звонка в аварийную службу.</span><span class="sxs-lookup"><span data-stu-id="60a7b-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="60a7b-145">**Режим конференции**</span><span class="sxs-lookup"><span data-stu-id="60a7b-145">**Conference Mode**</span></span>
  
<span data-ttu-id="60a7b-146">Указывает, будет ли URI конференции включаться в вызов аварийной службы в режиме односторонней или двусторонней связи.</span><span class="sxs-lookup"><span data-stu-id="60a7b-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="60a7b-147">**Location Refresh Interval** (Интервал обновления данных расположения)</span><span class="sxs-lookup"><span data-stu-id="60a7b-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="60a7b-148">Указывает время (в часах) между запросами клиента на обновление расположения из службы сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="60a7b-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="60a7b-149">Значение можно задать в диапазоне от 1 до 12.</span><span class="sxs-lookup"><span data-stu-id="60a7b-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="60a7b-150">Значение по умолчанию: 4 часа.</span><span class="sxs-lookup"><span data-stu-id="60a7b-150">The default value is 4.</span></span>
  

