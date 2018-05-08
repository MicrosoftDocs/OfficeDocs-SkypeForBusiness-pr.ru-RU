---
title: Как можно использовать идентификатор звонящего в вашей организации
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Идентификатор звонящего можно управлять для входящих и исходящих вызовов для пользователей телефонной системы с помощью политики, называется CallingLineIdentity.
ms.openlocfilehash: a1a809805b96152e4b205c8f38b3c8409014eb55
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="d0c47-103">Как можно использовать идентификатор звонящего в вашей организации</span><span class="sxs-lookup"><span data-stu-id="d0c47-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="d0c47-104">Идентификатор звонящего можно управлять для входящих и исходящих вызовов для пользователей телефонной системы с помощью политики, называется CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="d0c47-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="d0c47-105">Идентификатор звонящего функциональные возможности доступны для всех пользователей телефонной системой независимо от того, подключение к ТСОП:</span><span class="sxs-lookup"><span data-stu-id="d0c47-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="d0c47-106">Подключение к сети ТСОП</span><span class="sxs-lookup"><span data-stu-id="d0c47-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="d0c47-107">Подключение к ТСОП в локальной с Скайп для соединителя Cloud Business Edition (требуется облачных соединителя 1.4.2 и далее)</span><span class="sxs-lookup"><span data-stu-id="d0c47-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="d0c47-108">Подключение к ТСОП в локальной с Скайп для сервера Business (требуется Скайп для Business Server 2015 накопительным пакетом обновления 5 и за ее пределами)</span><span class="sxs-lookup"><span data-stu-id="d0c47-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="d0c47-109">Эта политика недоступен в Скайп для 2015 Business Server.</span><span class="sxs-lookup"><span data-stu-id="d0c47-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="d0c47-110">Идентификатор исходящего вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="d0c47-110">Outbound caller ID</span></span>

<span data-ttu-id="d0c47-111">Для исходящего PSTN Звонящего доступны три варианта:</span><span class="sxs-lookup"><span data-stu-id="d0c47-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="d0c47-112">Номер телефона, назначенных пользователю, по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d0c47-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="d0c47-113">Телефонный номер, который классифицировано как *службы* и *бесплатный* номер в вашей вызов планы в Office 365 телефонный номер инвентаризации.</span><span class="sxs-lookup"><span data-stu-id="d0c47-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="d0c47-114">Обычно назначается в очередь организационной auto attendant или звонок.</span><span class="sxs-lookup"><span data-stu-id="d0c47-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="d0c47-115">Задайте анонимных.</span><span class="sxs-lookup"><span data-stu-id="d0c47-115">Set to anonymous.</span></span>
    
<span data-ttu-id="d0c47-116">Тем не менее невозможно назначить эти типы номера телефонов для исходящих Звонящего:</span><span class="sxs-lookup"><span data-stu-id="d0c47-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="d0c47-117">Все номера телефонов, классифицируются как *пользователь* в телефонном вызов планы, какой номер запасов</span><span class="sxs-lookup"><span data-stu-id="d0c47-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="d0c47-118">Скайп для номера телефона в локальной Business Server</span><span class="sxs-lookup"><span data-stu-id="d0c47-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="d0c47-119">Чтобы задать идентификатор исходящего вызывающего абонента, [Звонящего для пользователя,](set-the-caller-id-for-a-user.md)см.</span><span class="sxs-lookup"><span data-stu-id="d0c47-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="d0c47-120">Элемент управления конечного пользователя из исходящих Звонящего</span><span class="sxs-lookup"><span data-stu-id="d0c47-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="d0c47-121">Атрибут EnableUserOverride позволяет пользователям одного или нескольких изменен идентификатор звонящего на **Анонимный доступ**.</span><span class="sxs-lookup"><span data-stu-id="d0c47-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="d0c47-122">Применяется только при настройке политики CallingLineIdentity с параметром CallingIDSubstitute LineURI или замены.</span><span class="sxs-lookup"><span data-stu-id="d0c47-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="d0c47-123">Значение по умолчанию EnableUserOverride — False.</span><span class="sxs-lookup"><span data-stu-id="d0c47-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="d0c47-124">Пользователям можно включить их Звонящего **Анонимный доступ** с помощью вкладки **Переадресовывать настройки звонков** в Скайп для настольных компьютеров клиента Business.</span><span class="sxs-lookup"><span data-stu-id="d0c47-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d0c47-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="d0c47-125">**Windows**</span></span> <br/> |<span data-ttu-id="d0c47-126">**Версия**</span><span class="sxs-lookup"><span data-stu-id="d0c47-126">**Version**</span></span> <br/> |<span data-ttu-id="d0c47-127">**Поддерживается**</span><span class="sxs-lookup"><span data-stu-id="d0c47-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="d0c47-128">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="d0c47-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="d0c47-129">Текущая платформа канала выпущен на 6 декабря 2016 - версии 1611 (построение 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="d0c47-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="d0c47-130">Да</span><span class="sxs-lookup"><span data-stu-id="d0c47-130">Yes</span></span>  <br/> |
|<span data-ttu-id="d0c47-131">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="d0c47-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="d0c47-132">Первый выпуск для канала отложенный выпущен 22 февраля 2017 - 1701 версии (построение 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="d0c47-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="d0c47-133">Да</span><span class="sxs-lookup"><span data-stu-id="d0c47-133">Yes</span></span>  <br/> |
|<span data-ttu-id="d0c47-134">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="d0c47-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="d0c47-135">Отложенное канала на 13 июня 2017-1701 версии (построение 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="d0c47-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="d0c47-136">Да</span><span class="sxs-lookup"><span data-stu-id="d0c47-136">Yes</span></span>  <br/> |
|<span data-ttu-id="d0c47-137">MSI</span><span class="sxs-lookup"><span data-stu-id="d0c47-137">MSI</span></span>  <br/> |<span data-ttu-id="d0c47-138">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d0c47-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="d0c47-139">Нет</span><span class="sxs-lookup"><span data-stu-id="d0c47-139">No</span></span>  <br/> |
|<span data-ttu-id="d0c47-140">Mac</span><span class="sxs-lookup"><span data-stu-id="d0c47-140">Mac</span></span>  <br/> |<span data-ttu-id="d0c47-141">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d0c47-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="d0c47-142">Нет</span><span class="sxs-lookup"><span data-stu-id="d0c47-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="d0c47-143">Входящий трафик идентификатора звонящего</span><span class="sxs-lookup"><span data-stu-id="d0c47-143">Inbound Caller ID</span></span>

<span data-ttu-id="d0c47-144">Атрибут BlockIncomingCallerID обеспечивает блокирование Звонящего на входящие вызовы в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="d0c47-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="d0c47-145">Можно задать этот атрибут, но не доступна для конечных пользователей на странице параметров пользователей.</span><span class="sxs-lookup"><span data-stu-id="d0c47-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="d0c47-146">И в настоящее время доступна только при наличии подключения к сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="d0c47-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="d0c47-147">Чтобы задать идентификатор исходящего вызывающего абонента, [Звонящего для пользователя,](set-the-caller-id-for-a-user.md)см.</span><span class="sxs-lookup"><span data-stu-id="d0c47-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d0c47-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="d0c47-148">Related topics</span></span>
[<span data-ttu-id="d0c47-149">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="d0c47-149">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="d0c47-150">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="d0c47-150">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="d0c47-151">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="d0c47-151">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="d0c47-152">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="d0c47-152">Emergency calling terms and conditions</span></span>](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

<span data-ttu-id="d0c47-153">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d0c47-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 