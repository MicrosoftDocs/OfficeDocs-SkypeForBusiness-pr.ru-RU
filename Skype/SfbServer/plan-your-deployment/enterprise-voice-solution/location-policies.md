---
title: Планирование политик местоположения для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: В этой статье рассказывается, как планировать политики местоположения для расширенной среды экстренных служб (E9-1-1) в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 5064197dd8d23113d7bfeca30fd3596d5ee89c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802809"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="2467d-103">Планирование политик местоположения для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2467d-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="2467d-104">В этой статье рассказывается, как планировать политики местоположения для расширенной среды экстренных служб (E9-1-1) в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2467d-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2467d-105">Skype для бизнеса Server теперь поддерживает конфигурацию нескольких номеров экстренного реагирования для клиента.</span><span class="sxs-lookup"><span data-stu-id="2467d-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="2467d-106">Если вы хотите настроить несколько номеров для экстренного реагирования, необходимо выполнить описанные ниже действия в разделе [Планирование нескольких номеров для экстренных случаев в Skype для бизнеса Server](multiple-emergency-numbers.md) и [Настройте несколько номеров для экстренной помощи в Skype для бизнеса](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="2467d-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="2467d-107">Политики местоположений создаются с помощью панели управления Skype для бизнеса или с помощью командлета [New-кслокатионполици](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="2467d-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="2467d-108">Дополнительные сведения можно найти [в разделе Создание политик местоположений в Skype для бизнеса Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2467d-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="2467d-109">Все политики расположений содержат следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="2467d-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="2467d-110">**Разрешить расширенные службы экстренного вызова**</span><span class="sxs-lookup"><span data-stu-id="2467d-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="2467d-111">Если этого параметр включен, для клиента включена поддержка E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="2467d-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="2467d-112">Когда клиент регистрируется, он пытается получить место из службы сведений о местоположении и будет включать сведения о расположении в процессе вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="2467d-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="2467d-113">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="2467d-113">**Location**</span></span>
  
<span data-ttu-id="2467d-114">Эта настройка используется только в том случае, если включен параметр **Разрешить расширенные службы экстренного вызова**. </span><span class="sxs-lookup"><span data-stu-id="2467d-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="2467d-115">Чтобы определить поведение клиентов, можно настроить параметр **Расположение** следующим образом:   </span><span class="sxs-lookup"><span data-stu-id="2467d-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="2467d-116">Если задать значение **Нет**, расположение не будет запрашиваться у пользователя.</span><span class="sxs-lookup"><span data-stu-id="2467d-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="2467d-117">Если задать значение **Да**, расположение будет запрашиваться у пользователя, но он сможет отклонить запрос.</span><span class="sxs-lookup"><span data-stu-id="2467d-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="2467d-p104">Если задать для параметра значение **Заявление об отказе**, расположение будет запрашиваться у пользователя и при попытке отклонить запрос будет выводиться уведомление об отказе. В любом случае пользователь сможет использовать клиент.</span><span class="sxs-lookup"><span data-stu-id="2467d-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2467d-p105">Текст заявления не отображается, если пользователь вручную вводит расположение, прежде чем получить доступ к E9-1-1. Обновленный текст заявления об отказе не будет отображаться для пользователей, которые уже просмотрели заявление. </span><span class="sxs-lookup"><span data-stu-id="2467d-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="2467d-122">**Заявление об отказе расширенных экстренных служб**</span><span class="sxs-lookup"><span data-stu-id="2467d-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="2467d-123">Этот параметр задает заявление об отказе, которое будет отображаться для пользователей, если они отклоняют запрос расположения.</span><span class="sxs-lookup"><span data-stu-id="2467d-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="2467d-124">В Skype для бизнеса Server вы можете использовать политику местоположений для настройки различных отказов на использование разных языков или разных групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="2467d-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="2467d-125">**Строка набора аварийного номера (номер экстренного вызова)**</span><span class="sxs-lookup"><span data-stu-id="2467d-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="2467d-126">Эта строка набора номера (меньше, чем интерлиньяж "+", но все нормализация, выполненная абонентской панелью пользователя) означает, что звонок является экстренным звонком.</span><span class="sxs-lookup"><span data-stu-id="2467d-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="2467d-127">На клиенте **строка набора аварийного номера** обеспечивает включение в вызов данных о местоположении и информации для обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="2467d-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2467d-128">Если в вашей организации не используется префикс доступа к внешней линии, вам не нужно создавать соответствующее правило нормализации для абонентской группы, добавляющее "+" в строку 911 перед отправкой вызова на исходящую маршрутизацию на сервере, на котором работает Skype для бизнеса Server; Приложение "+" будет автоматически добавляться клиентом Skype для бизнеса в качестве результата политики расположения.</span><span class="sxs-lookup"><span data-stu-id="2467d-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="2467d-129">Однако если на сайте используется префикс внешнего доступа, необходимо добавить правило нормализации для соответствующей политики абонентского плана, которое удаляет префикс доступа к внешним данным и добавляет знак "+".</span><span class="sxs-lookup"><span data-stu-id="2467d-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="2467d-130">Например, если в вашем местоположении используется префикс внешнего доступа 9 и пользователь набирает номер 9 911 для вызова экстренной помощи, клиент будет использовать политику абонентской группы для нормализации этого номера до + 911 перед тем, как вызываемый абонент будет оцениваться маршрутами в профиле местоположения вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="2467d-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="2467d-131">**Маски строки набора аварийного номера (маска номера экстренного вызова)**</span><span class="sxs-lookup"><span data-stu-id="2467d-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="2467d-132">Список разделенных точкой с запятой строк набора номера, который преобразуется в указанную **строку для экстренного набора**.</span><span class="sxs-lookup"><span data-stu-id="2467d-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="2467d-133">Например, вы можете добавить 112, который является номером службы экстренной помощи в большинстве стран Европы.</span><span class="sxs-lookup"><span data-stu-id="2467d-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="2467d-134">Пользователи Skype для бизнеса из Европы могут не знать, что 911 является номером экстренного реагирования на звонки в США, но они могут набрать номер 112 и получить тот же результат.</span><span class="sxs-lookup"><span data-stu-id="2467d-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="2467d-135">Как и в случае со строкой набора экстренных вызовов, не включайте знак "+" перед каждым числом, и если вы используете коды доступа внешней линии, убедитесь в том, что в политике абонентской группы пользователя есть правила нормализации для удаления цифр кода доступа.</span><span class="sxs-lookup"><span data-stu-id="2467d-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="2467d-136">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="2467d-136">**PSTN usage**</span></span>
  
<span data-ttu-id="2467d-137">Имя режима работы с ТСОП, содержащее пути маршрутизации, определяющие, через какую магистраль SIP, шлюз ТСОП или шлюз ELIN будут передаваться звонки в аварийные службы.</span><span class="sxs-lookup"><span data-stu-id="2467d-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2467d-138">Для политики местоположения можно назначить только одно использование.</span><span class="sxs-lookup"><span data-stu-id="2467d-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="2467d-139">Использование PSTN заменяет использование PSTN, назначенное голосовой политике пользователя, но применимо только к звонкам, помещенным в строку набора номера или в одну из масок строки набора экстренных загрузок.</span><span class="sxs-lookup"><span data-stu-id="2467d-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="2467d-140">**URI уведомления**</span><span class="sxs-lookup"><span data-stu-id="2467d-140">**Notification URI**</span></span>
  
<span data-ttu-id="2467d-p111">Задает один или несколько URI SIP персонала службы безопасности, которые получают уведомление в виде мгновенного сообщения при отправке звонка в аварийную службу. Этот параметр поддерживает группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="2467d-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="2467d-143">**Идентификатор URI конференции**</span><span class="sxs-lookup"><span data-stu-id="2467d-143">**Conference URI**</span></span>
  
<span data-ttu-id="2467d-144">Задает прямой внутренний номер (как правило, номер службы безопасности), по которому выполнятся подключение конференц-связи при отправке звонка в аварийную службу.  </span><span class="sxs-lookup"><span data-stu-id="2467d-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="2467d-145">**Режим конференции**</span><span class="sxs-lookup"><span data-stu-id="2467d-145">**Conference Mode**</span></span>
  
<span data-ttu-id="2467d-146">Указывает, будет ли URI конференции включаться в вызов аварийной службы в режиме односторонней или двусторонней связи. </span><span class="sxs-lookup"><span data-stu-id="2467d-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="2467d-147">**Интервал обновления данных расположения**</span><span class="sxs-lookup"><span data-stu-id="2467d-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="2467d-148">Указывает время (в часах) между запросами клиентов на обновление расположения в службе сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="2467d-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="2467d-149">The value can be set to any value between 1 and 12.</span><span class="sxs-lookup"><span data-stu-id="2467d-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="2467d-150">The default value is 4.</span><span class="sxs-lookup"><span data-stu-id="2467d-150">The default value is 4.</span></span>
  

