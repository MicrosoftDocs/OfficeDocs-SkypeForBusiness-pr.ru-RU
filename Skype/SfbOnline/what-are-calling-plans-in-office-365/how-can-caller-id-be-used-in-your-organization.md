---
title: Использование идентификатора абонента в организации
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Идентификатором вызывающего абонента можно управлять для входящих и исходящих вызовов для пользователей телефонной системы с помощью политики, которая называется CallingLineIdentity.
ms.openlocfilehash: c8a823235c3c3fedaf71d42e8482c5f4579b80ef
ms.sourcegitcommit: c5940ef2674a00281604045baf8b2a320c4b189d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "24958174"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="95f18-103">Использование идентификатора абонента в организации</span><span class="sxs-lookup"><span data-stu-id="95f18-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="95f18-104">Идентификатором вызывающего абонента можно управлять для входящих и исходящих вызовов для пользователей телефонной системы с помощью политики, которая называется CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="95f18-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="95f18-105">Функциональность идентификатора вызывающего абонента доступна для всех пользователей телефонной системы независимо от возможности подключения к сети ТСОП:</span><span class="sxs-lookup"><span data-stu-id="95f18-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="95f18-106">Подключение к сети ТСОП</span><span class="sxs-lookup"><span data-stu-id="95f18-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="95f18-107">Подключение к локальной сети ТСОП с помощью выпуска облачного соединителя Skype для бизнеса (требуется облачный соединитель 1.4.2 или более позднего выпуска)</span><span class="sxs-lookup"><span data-stu-id="95f18-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="95f18-108">Подключение к локальной сети ТСОП с помощью сервера Skype для бизнеса (требуется сервер Skype для бизнеса 2015 CU5 или более поздней версии)</span><span class="sxs-lookup"><span data-stu-id="95f18-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="95f18-109">Эта политика недоступна в сервере Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="95f18-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="95f18-110">Идентификация имени вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="95f18-110">Outbound caller ID</span></span>

<span data-ttu-id="95f18-111">Для идентификации имени вызывающего абонента сети ТСОП доступны три варианта:</span><span class="sxs-lookup"><span data-stu-id="95f18-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="95f18-112">Номер телефона, назначенный пользователю, который задан по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="95f18-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="95f18-113">Телефонный номер, который классифицируется как *служебный* и *бесплатный* номер в ваших тарифных планах для склада телефонных номеров Office 365.</span><span class="sxs-lookup"><span data-stu-id="95f18-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="95f18-114">Он обычно назначается автосекретарю или очереди звонков организации.</span><span class="sxs-lookup"><span data-stu-id="95f18-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="95f18-115">Задан как анонимный.</span><span class="sxs-lookup"><span data-stu-id="95f18-115">Set to anonymous.</span></span>
    
<span data-ttu-id="95f18-116">Тем не менее, невозможно назначить эти типы номеров телефонов для идентификатора вызывающего абонента:</span><span class="sxs-lookup"><span data-stu-id="95f18-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="95f18-117">Все номера телефонов, которые классифицируются как *пользовательские* в вашем тарифном плане склада телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="95f18-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="95f18-118">Локальный номер телефона сервера Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="95f18-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="95f18-119">Чтобы задать идентификатор вызывающего абонента, см. [Назначение идентификатора абонента пользователю](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="95f18-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="95f18-120">Контроль пользователем идентификатора вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="95f18-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="95f18-121">Атрибут EnableUserOverride позволяет одному или нескольким пользователям изменять их настройку идентификатора вызывающего абонента на **Анонимный**.</span><span class="sxs-lookup"><span data-stu-id="95f18-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="95f18-122">Эта функция применяется только при настройке политики CallingLineIdentity с параметром CallingIDSubstitute LineURI или заменой.</span><span class="sxs-lookup"><span data-stu-id="95f18-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="95f18-123">Значение по умолчанию EnableUserOverride — False.</span><span class="sxs-lookup"><span data-stu-id="95f18-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="95f18-124">Ваши пользователи могут установить их идентификатор вызывающего абонента как **Анонимный** с помощью вкладки **Call Forward Settings** в клиенте Skype для бизнеса для настольных приложений.</span><span class="sxs-lookup"><span data-stu-id="95f18-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="95f18-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="95f18-125">**Windows**</span></span> <br/> |<span data-ttu-id="95f18-126">**Версия**</span><span class="sxs-lookup"><span data-stu-id="95f18-126">**Version**</span></span> <br/> |<span data-ttu-id="95f18-127">**Поддерживается**</span><span class="sxs-lookup"><span data-stu-id="95f18-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="95f18-128">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="95f18-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="95f18-129">Текущая платформа канала выпущена 6 декабря 2016 года - версия 1611 (сборка 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="95f18-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="95f18-130">Да</span><span class="sxs-lookup"><span data-stu-id="95f18-130">Yes</span></span>  <br/> |
|<span data-ttu-id="95f18-131">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="95f18-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="95f18-132">Первый выпуск для отложенного канала был выпущен 22 февраля 2017 года - версия 1701 (сборка 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="95f18-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="95f18-133">Да</span><span class="sxs-lookup"><span data-stu-id="95f18-133">Yes</span></span>  <br/> |
|<span data-ttu-id="95f18-134">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="95f18-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="95f18-135">Отложенный канал выпущен 13 июня 2017 г. - версия 1701 (сборка 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="95f18-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="95f18-136">Да</span><span class="sxs-lookup"><span data-stu-id="95f18-136">Yes</span></span>  <br/> |
|<span data-ttu-id="95f18-137">MSI</span><span class="sxs-lookup"><span data-stu-id="95f18-137">MSI</span></span>  <br/> |<span data-ttu-id="95f18-138">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="95f18-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="95f18-139">Нет</span><span class="sxs-lookup"><span data-stu-id="95f18-139">No</span></span>  <br/> |
|<span data-ttu-id="95f18-140">Mac</span><span class="sxs-lookup"><span data-stu-id="95f18-140">Mac</span></span>  <br/> |<span data-ttu-id="95f18-141">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="95f18-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="95f18-142">Нет</span><span class="sxs-lookup"><span data-stu-id="95f18-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="95f18-143">Идентификация звонящего абонента</span><span class="sxs-lookup"><span data-stu-id="95f18-143">Inbound Caller ID</span></span>

<span data-ttu-id="95f18-144">Атрибут BlockIncomingCallerID обеспечивает блокирование идентификатора абонента на входящие вызовы в сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="95f18-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="95f18-145">Можно задать этот атрибут, но он не доступен вашим пользователям на странице параметров пользователей.</span><span class="sxs-lookup"><span data-stu-id="95f18-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="95f18-146">И в настоящее время он доступен только при возможности подключения к сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="95f18-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="95f18-147">Чтобы задать идентификатор вызывающего абонента, см. [Назначение идентификатора абонента пользователю](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="95f18-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="95f18-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="95f18-148">Related topics</span></span>
[<span data-ttu-id="95f18-149">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="95f18-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="95f18-150">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="95f18-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="95f18-151">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="95f18-151">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="95f18-152">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="95f18-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="95f18-153">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="95f18-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 