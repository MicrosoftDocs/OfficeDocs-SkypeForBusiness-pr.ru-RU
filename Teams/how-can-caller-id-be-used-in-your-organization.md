---
title: Как можно использовать идентификатор звонящего в организации
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: e723311b2780dd1d43bad4874b72133e09ff4fc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120680"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="c6647-103">Как можно использовать идентификатор звонящего в организации</span><span class="sxs-lookup"><span data-stu-id="c6647-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="c6647-104">Идентификатором вызывающего абонента можно управлять для входящих и исходящих вызовов для пользователей телефонной системы с помощью политики, которая называется CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="c6647-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="c6647-105">Функции "ИД вызываемого звоня" доступны всем пользователям телефонной системы независимо от подключения к ДНР.</span><span class="sxs-lookup"><span data-stu-id="c6647-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="c6647-106">Планы звонков Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c6647-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="c6647-107">Прямая маршрутизация телефонной системы</span><span class="sxs-lookup"><span data-stu-id="c6647-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="c6647-108">Подключение к сети ТСОП</span><span class="sxs-lookup"><span data-stu-id="c6647-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="c6647-109">Подключение к локальной сети ТСОП с помощью выпуска облачного соединителя Skype для бизнеса (требуется облачный соединитель 1.4.2 или более позднего выпуска)</span><span class="sxs-lookup"><span data-stu-id="c6647-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="c6647-110">Подключение к локальной сети ТСОП с помощью сервера Skype для бизнеса (требуется сервер Skype для бизнеса 2015 CU5 или более поздней версии)</span><span class="sxs-lookup"><span data-stu-id="c6647-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="c6647-111">Эта политика недоступна в сервере Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="c6647-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="c6647-112">Идентификация имени вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="c6647-112">Outbound caller ID</span></span>

<span data-ttu-id="c6647-113">Для ИД звоня в исходящие вызовы через ПС доступны три параметра:</span><span class="sxs-lookup"><span data-stu-id="c6647-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="c6647-114">Номер телефона, назначенный пользователю, который задан по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c6647-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="c6647-115">Номер телефона, классифицированный  как  услуга, и бесплатный номер из перечня номеров телефонов планов звонков.</span><span class="sxs-lookup"><span data-stu-id="c6647-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="c6647-116">Он обычно назначается автосекретарю или очереди звонков организации.</span><span class="sxs-lookup"><span data-stu-id="c6647-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="c6647-117">Задан как анонимный.</span><span class="sxs-lookup"><span data-stu-id="c6647-117">Set to anonymous.</span></span>
    
<span data-ttu-id="c6647-118">Тем не менее, невозможно назначить эти типы номеров телефонов для идентификатора вызывающего абонента:</span><span class="sxs-lookup"><span data-stu-id="c6647-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="c6647-119">Все номера телефонов, которые классифицируются как *пользовательские* в вашем тарифном плане склада телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="c6647-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="c6647-120">Локальный номер телефона сервера Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c6647-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="c6647-121">Чтобы задать идентификатор вызывающего абонента, см. [Назначение идентификатора абонента пользователю](./set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c6647-121">To set the outbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="c6647-122">Управление исходящие и исходящие ИД вызываемого звонка конечными пользователями</span><span class="sxs-lookup"><span data-stu-id="c6647-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="c6647-123">Атрибут EnableUserOverride позволяет одному или нескольким пользователям изменить параметры своих звонков на **анонимный.**</span><span class="sxs-lookup"><span data-stu-id="c6647-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="c6647-124">Эта функция применяется только при настройке политики CallingLineIdentity с параметром CallingIDSubstitute LineURI или заменой.</span><span class="sxs-lookup"><span data-stu-id="c6647-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="c6647-125">По умолчанию EnableUserOverride имеет значение False.</span><span class="sxs-lookup"><span data-stu-id="c6647-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="c6647-126">Конечные пользователи могут сделать свой  ИД звоня анонимным с помощью вкладки "Параметры" в клиенте Skype для бизнеса для настольных пк, выбрать "Звонки пользователю"  (если эта возможность включена администратором), а затем выбрать "Скрыть мой номер телефона и данные профиля для всех звонков".  </span><span class="sxs-lookup"><span data-stu-id="c6647-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="c6647-127">В Teams пользователи могут перейти к своему изображению профиля в правом верхнем углу, выбрать "Параметры звонков", а затем в области "ИД звоня" выбрать "Скрыть мой номер телефона и данные профиля для всех звонков".  >    </span><span class="sxs-lookup"><span data-stu-id="c6647-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="c6647-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="c6647-128">**Windows**</span></span> <br/> |<span data-ttu-id="c6647-129">**Версия**</span><span class="sxs-lookup"><span data-stu-id="c6647-129">**Version**</span></span> <br/> |<span data-ttu-id="c6647-130">**Поддерживается**</span><span class="sxs-lookup"><span data-stu-id="c6647-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="c6647-131">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="c6647-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="c6647-132">Текущая платформа канала выпущена 6 декабря 2016 года - версия 1611 (сборка 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="c6647-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="c6647-133">Да</span><span class="sxs-lookup"><span data-stu-id="c6647-133">Yes</span></span>  <br/> |
|<span data-ttu-id="c6647-134">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="c6647-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="c6647-135">Первый выпуск для отложенного канала был выпущен 22 февраля 2017 года - версия 1701 (сборка 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="c6647-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="c6647-136">Да</span><span class="sxs-lookup"><span data-stu-id="c6647-136">Yes</span></span>  <br/> |
|<span data-ttu-id="c6647-137">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="c6647-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="c6647-138">Отложенный канал выпущен 13 июня 2017 г. - версия 1701 (сборка 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="c6647-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="c6647-139">Да</span><span class="sxs-lookup"><span data-stu-id="c6647-139">Yes</span></span>  <br/> |
|<span data-ttu-id="c6647-140">MSI</span><span class="sxs-lookup"><span data-stu-id="c6647-140">MSI</span></span>  <br/> |<span data-ttu-id="c6647-141">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c6647-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="c6647-142">Нет</span><span class="sxs-lookup"><span data-stu-id="c6647-142">No</span></span>  <br/> |
|<span data-ttu-id="c6647-143">Mac</span><span class="sxs-lookup"><span data-stu-id="c6647-143">Mac</span></span>  <br/> |<span data-ttu-id="c6647-144">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c6647-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="c6647-145">Нет</span><span class="sxs-lookup"><span data-stu-id="c6647-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="c6647-146">ИД входящий звонок</span><span class="sxs-lookup"><span data-stu-id="c6647-146">Inbound caller ID</span></span>

<span data-ttu-id="c6647-147">Телефонная система будет показывать имя внешнего номера телефона, если он связан с пользователем в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c6647-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="c6647-148">Если номер телефона не находится в Azure AD, отображаемая телефонная фамилия будет отображаться, если она доступна.</span><span class="sxs-lookup"><span data-stu-id="c6647-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="c6647-149">Атрибут BlockIncomingCallerID обеспечивает блокирование идентификатора абонента на входящие вызовы в сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="c6647-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="c6647-150">Можно задать этот атрибут, но он не доступен вашим пользователям на странице параметров пользователей.</span><span class="sxs-lookup"><span data-stu-id="c6647-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="c6647-151">И в настоящее время он доступен только при возможности подключения к сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="c6647-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="c6647-152">Чтобы задать идентификатор вызывающего абонента, см. [Назначение идентификатора абонента пользователю](./set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c6647-152">To set the outbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c6647-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="c6647-153">Related topics</span></span>
[<span data-ttu-id="c6647-154">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="c6647-154">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="c6647-155">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="c6647-155">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="c6647-156">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="c6647-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="c6647-157">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="c6647-157">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="c6647-158">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c6647-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
