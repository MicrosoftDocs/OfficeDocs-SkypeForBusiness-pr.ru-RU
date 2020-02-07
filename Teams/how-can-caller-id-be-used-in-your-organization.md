---
title: Как можно использовать идентификатор звонящего в организации
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: Идентификатором вызывающего абонента можно управлять для входящих и исходящих вызовов для пользователей телефонной системы с помощью политики, которая называется CallingLineIdentity.
ms.openlocfilehash: af578cf92f6c19e8ac612dfe8301914c9e55833b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836311"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="9d17c-103">Как можно использовать идентификатор звонящего в организации</span><span class="sxs-lookup"><span data-stu-id="9d17c-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="9d17c-104">Идентификатором вызывающего абонента можно управлять для входящих и исходящих вызовов для пользователей телефонной системы с помощью политики, которая называется CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="9d17c-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="9d17c-105">Функциональность идентификатора вызывающего абонента доступна для всех пользователей телефонной системы независимо от возможности подключения к сети ТСОП:</span><span class="sxs-lookup"><span data-stu-id="9d17c-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="9d17c-106">Подключение к сети ТСОП</span><span class="sxs-lookup"><span data-stu-id="9d17c-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="9d17c-107">Подключение к локальной сети ТСОП с помощью выпуска облачного соединителя Skype для бизнеса (требуется облачный соединитель 1.4.2 или более позднего выпуска)</span><span class="sxs-lookup"><span data-stu-id="9d17c-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="9d17c-108">Подключение к локальной сети ТСОП с помощью сервера Skype для бизнеса (требуется сервер Skype для бизнеса 2015 CU5 или более поздней версии)</span><span class="sxs-lookup"><span data-stu-id="9d17c-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="9d17c-109">Эта политика недоступна в сервере Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="9d17c-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="9d17c-110">Идентификация имени вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="9d17c-110">Outbound caller ID</span></span>

<span data-ttu-id="9d17c-111">Для идентификации имени вызывающего абонента сети ТСОП доступны три варианта:</span><span class="sxs-lookup"><span data-stu-id="9d17c-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="9d17c-112">Номер телефона, назначенный пользователю, который задан по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d17c-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="9d17c-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="9d17c-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="9d17c-115">Задан как анонимный.</span><span class="sxs-lookup"><span data-stu-id="9d17c-115">Set to anonymous.</span></span>
    
<span data-ttu-id="9d17c-116">Тем не менее, невозможно назначить эти типы номеров телефонов для идентификатора вызывающего абонента:</span><span class="sxs-lookup"><span data-stu-id="9d17c-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="9d17c-117">Все номера телефонов, которые классифицируются как *пользовательские* в вашем тарифном плане склада телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="9d17c-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="9d17c-118">Локальный номер телефона сервера Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9d17c-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="9d17c-119">Чтобы задать идентификатор вызывающего абонента, см. [Назначение идентификатора абонента пользователю](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="9d17c-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="9d17c-120">Контроль пользователем идентификатора вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="9d17c-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="9d17c-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span><span class="sxs-lookup"><span data-stu-id="9d17c-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="9d17c-124">Конечные пользователи могут настроить для идентификатора вызывающего абонента значение **anonymous** с помощью вкладки " **Параметры** " в классическом клиенте Skype для бизнеса **, выберите команду** " **Скрыть мой номер телефона" и сведения о профиле для всех звонков**.</span><span class="sxs-lookup"><span data-stu-id="9d17c-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9d17c-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="9d17c-125">**Windows**</span></span> <br/> |<span data-ttu-id="9d17c-126">**Версия**</span><span class="sxs-lookup"><span data-stu-id="9d17c-126">**Version**</span></span> <br/> |<span data-ttu-id="9d17c-127">**Поддерживаются**</span><span class="sxs-lookup"><span data-stu-id="9d17c-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="9d17c-128">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="9d17c-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9d17c-129">Текущая платформа канала выпущена 6 декабря 2016 года - версия 1611 (сборка 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="9d17c-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="9d17c-130">Да</span><span class="sxs-lookup"><span data-stu-id="9d17c-130">Yes</span></span>  <br/> |
|<span data-ttu-id="9d17c-131">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="9d17c-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9d17c-132">Первый выпуск для отложенного канала был выпущен 22 февраля 2017 года - версия 1701 (сборка 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="9d17c-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="9d17c-133">Да</span><span class="sxs-lookup"><span data-stu-id="9d17c-133">Yes</span></span>  <br/> |
|<span data-ttu-id="9d17c-134">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="9d17c-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9d17c-135">Отложенный канал выпущен 13 июня 2017 г. - версия 1701 (сборка 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="9d17c-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="9d17c-136">Да</span><span class="sxs-lookup"><span data-stu-id="9d17c-136">Yes</span></span>  <br/> |
|<span data-ttu-id="9d17c-137">MSI</span><span class="sxs-lookup"><span data-stu-id="9d17c-137">MSI</span></span>  <br/> |<span data-ttu-id="9d17c-138">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9d17c-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="9d17c-139">Нет</span><span class="sxs-lookup"><span data-stu-id="9d17c-139">No</span></span>  <br/> |
|<span data-ttu-id="9d17c-140">Mac</span><span class="sxs-lookup"><span data-stu-id="9d17c-140">Mac</span></span>  <br/> |<span data-ttu-id="9d17c-141">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9d17c-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="9d17c-142">Нет</span><span class="sxs-lookup"><span data-stu-id="9d17c-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="9d17c-143">Идентификация звонящего абонента</span><span class="sxs-lookup"><span data-stu-id="9d17c-143">Inbound Caller ID</span></span>

<span data-ttu-id="9d17c-144">Телефонная система отображает вызываемый ИДЕНТИФИКАЦИОНный номер внешнего номера, если номер связан с пользователем в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9d17c-144">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="9d17c-145">Если номер телефона не входит в Azure AD, выводится отображаемое имя Telco, если оно доступно.</span><span class="sxs-lookup"><span data-stu-id="9d17c-145">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="9d17c-146">Атрибут BlockIncomingCallerID обеспечивает блокирование идентификатора абонента на входящие вызовы в сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="9d17c-146">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="9d17c-147">Можно задать этот атрибут, но он не доступен вашим пользователям на странице параметров пользователей.</span><span class="sxs-lookup"><span data-stu-id="9d17c-147">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="9d17c-148">И в настоящее время он доступен только при возможности подключения к сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="9d17c-148">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="9d17c-149">Чтобы задать идентификатор вызывающего абонента, см. [Назначение идентификатора абонента пользователю](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="9d17c-149">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9d17c-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="9d17c-150">Related topics</span></span>
[<span data-ttu-id="9d17c-151">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="9d17c-151">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="9d17c-152">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="9d17c-152">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="9d17c-153">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="9d17c-153">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="9d17c-154">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="9d17c-154">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="9d17c-155">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="9d17c-155">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
