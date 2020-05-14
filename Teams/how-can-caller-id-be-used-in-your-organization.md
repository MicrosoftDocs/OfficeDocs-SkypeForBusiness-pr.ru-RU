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
ms.openlocfilehash: 2547e6ca3aed10d112897aa1b24900a479c5c8ef
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224212"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="a2161-103">Как можно использовать идентификатор звонящего в организации</span><span class="sxs-lookup"><span data-stu-id="a2161-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="a2161-104">Идентификатором вызывающего абонента можно управлять для входящих и исходящих вызовов для пользователей телефонной системы с помощью политики, которая называется CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="a2161-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="a2161-105">Функции идентификации вызывающего абонента доступны для всех пользователей телефонной системы независимо от КТСОП.</span><span class="sxs-lookup"><span data-stu-id="a2161-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="a2161-106">Подключение к сети ТСОП</span><span class="sxs-lookup"><span data-stu-id="a2161-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="a2161-107">Подключение к локальной сети ТСОП с помощью выпуска облачного соединителя Skype для бизнеса (требуется облачный соединитель 1.4.2 или более позднего выпуска)</span><span class="sxs-lookup"><span data-stu-id="a2161-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="a2161-108">Подключение к локальной сети ТСОП с помощью сервера Skype для бизнеса (требуется сервер Skype для бизнеса 2015 CU5 или более поздней версии)</span><span class="sxs-lookup"><span data-stu-id="a2161-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="a2161-109">Эта политика недоступна в сервере Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="a2161-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="a2161-110">Идентификация имени вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="a2161-110">Outbound caller ID</span></span>

<span data-ttu-id="a2161-111">Для идентификации исходящего абонента PSTN доступны три варианта:</span><span class="sxs-lookup"><span data-stu-id="a2161-111">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="a2161-112">Номер телефона, назначенный пользователю, который задан по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a2161-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="a2161-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="a2161-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="a2161-115">Задан как анонимный.</span><span class="sxs-lookup"><span data-stu-id="a2161-115">Set to anonymous.</span></span>
    
<span data-ttu-id="a2161-116">Тем не менее, невозможно назначить эти типы номеров телефонов для идентификатора вызывающего абонента:</span><span class="sxs-lookup"><span data-stu-id="a2161-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="a2161-117">Все номера телефонов, которые классифицируются как *пользовательские* в вашем тарифном плане склада телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="a2161-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="a2161-118">Локальный номер телефона сервера Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a2161-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="a2161-119">Чтобы задать идентификатор вызывающего абонента, см. [Назначение идентификатора абонента пользователю](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="a2161-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="a2161-120">Конечный пользовательский контроль идентификатора исходящего вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="a2161-120">End user control of outbound caller ID</span></span>

<span data-ttu-id="a2161-p102">Атрибут EnableUserOverride позволяет одному или нескольким пользователям изменить параметр идентификатора вызывающего абонента на **Анонимный**. Это применимо только в том случае, если для политики CallingLineIdentity задан параметр CallingIDSubstitute из LineURI или подстановки. Значением по умолчанию для EnableUserOverride является false.</span><span class="sxs-lookup"><span data-stu-id="a2161-p102">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="a2161-124">Конечные пользователи могут установить для идентификатора вызывающего абонента значение **anonymous** с помощью вкладки " **Параметры** " в классическом клиенте Skype для бизнеса, выберите команду " **вызов пользователя** " (если она включена администратором), а затем выберите пункт **Скрыть мой номер телефона и сведения о профиле для всех звонков**.</span><span class="sxs-lookup"><span data-stu-id="a2161-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="a2161-125">В Teams пользователи могут перейти к своему аватару в правом верхнем углу, выбрать **Параметры**  >  **звонков**, а затем в разделе **Идентификация звонящего**выберите **Скрыть мой номер телефона и сведения о профиле для всех звонков**.</span><span class="sxs-lookup"><span data-stu-id="a2161-125">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a2161-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="a2161-126">**Windows**</span></span> <br/> |<span data-ttu-id="a2161-127">**Версия**</span><span class="sxs-lookup"><span data-stu-id="a2161-127">**Version**</span></span> <br/> |<span data-ttu-id="a2161-128">**Поддерживаются**</span><span class="sxs-lookup"><span data-stu-id="a2161-128">**Supported**</span></span> <br/> |
|<span data-ttu-id="a2161-129">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="a2161-129">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a2161-130">Текущая платформа канала выпущена 6 декабря 2016 года - версия 1611 (сборка 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="a2161-130">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="a2161-131">Да</span><span class="sxs-lookup"><span data-stu-id="a2161-131">Yes</span></span>  <br/> |
|<span data-ttu-id="a2161-132">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="a2161-132">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a2161-133">Первый выпуск для отложенного канала был выпущен 22 февраля 2017 года - версия 1701 (сборка 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="a2161-133">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="a2161-134">Да</span><span class="sxs-lookup"><span data-stu-id="a2161-134">Yes</span></span>  <br/> |
|<span data-ttu-id="a2161-135">Технология «нажми и работай»</span><span class="sxs-lookup"><span data-stu-id="a2161-135">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a2161-136">Отложенный канал выпущен 13 июня 2017 г. - версия 1701 (сборка 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="a2161-136">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="a2161-137">Да</span><span class="sxs-lookup"><span data-stu-id="a2161-137">Yes</span></span>  <br/> |
|<span data-ttu-id="a2161-138">MSI</span><span class="sxs-lookup"><span data-stu-id="a2161-138">MSI</span></span>  <br/> |<span data-ttu-id="a2161-139">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a2161-139">Skype for Business</span></span>  <br/> |<span data-ttu-id="a2161-140">Нет</span><span class="sxs-lookup"><span data-stu-id="a2161-140">No</span></span>  <br/> |
|<span data-ttu-id="a2161-141">Mac</span><span class="sxs-lookup"><span data-stu-id="a2161-141">Mac</span></span>  <br/> |<span data-ttu-id="a2161-142">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a2161-142">Skype for Business</span></span>  <br/> |<span data-ttu-id="a2161-143">Нет</span><span class="sxs-lookup"><span data-stu-id="a2161-143">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="a2161-144">Идентификатор входящего абонента</span><span class="sxs-lookup"><span data-stu-id="a2161-144">Inbound caller ID</span></span>

<span data-ttu-id="a2161-145">Телефонная система отображает вызываемый ИДЕНТИФИКАЦИОНный номер внешнего номера, если номер связан с пользователем в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a2161-145">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="a2161-146">Если номер телефона не входит в Azure AD, выводится отображаемое имя Telco, если оно доступно.</span><span class="sxs-lookup"><span data-stu-id="a2161-146">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="a2161-147">Атрибут BlockIncomingCallerID обеспечивает блокирование идентификатора абонента на входящие вызовы в сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a2161-147">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="a2161-148">Можно задать этот атрибут, но он не доступен вашим пользователям на странице параметров пользователей.</span><span class="sxs-lookup"><span data-stu-id="a2161-148">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="a2161-149">И в настоящее время он доступен только при возможности подключения к сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a2161-149">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="a2161-150">Чтобы задать идентификатор вызывающего абонента, см. [Назначение идентификатора абонента пользователю](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="a2161-150">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a2161-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2161-151">Related topics</span></span>
[<span data-ttu-id="a2161-152">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="a2161-152">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="a2161-153">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="a2161-153">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="a2161-154">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="a2161-154">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="a2161-155">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="a2161-155">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="a2161-156">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a2161-156">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
