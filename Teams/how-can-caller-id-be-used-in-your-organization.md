---
title: Как можно использовать идентификатор звонящего в организации
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
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
ms.openlocfilehash: 2a104679be84dfdaa4574353ccc79142d8a82284
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308348"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="e900f-103">Как можно использовать идентификатор звонящего в организации</span><span class="sxs-lookup"><span data-stu-id="e900f-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="e900f-104">ИД звонящая состоит из двух идентифицируемых пользователем фрагментов информации:</span><span class="sxs-lookup"><span data-stu-id="e900f-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="e900f-105">Номер телефона (обычно он называется CLID или ИД строки звонков).</span><span class="sxs-lookup"><span data-stu-id="e900f-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="e900f-106">Это общедоступный переключатель телефонного номера, который представлен в качестве идентификации вызывающего.</span><span class="sxs-lookup"><span data-stu-id="e900f-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="e900f-107">Имя вызываемой стороны (обычно называется CNAM).</span><span class="sxs-lookup"><span data-stu-id="e900f-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="e900f-108">Функция "ИД вызываемого звоня" доступна всем пользователям телефонная система независимо от варианта подключения к ПСС:</span><span class="sxs-lookup"><span data-stu-id="e900f-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="e900f-109">Планы звонков Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e900f-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="e900f-110">Прямая маршрутизация телефонной системы</span><span class="sxs-lookup"><span data-stu-id="e900f-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="e900f-111">Вы можете управлять ИД вызываемого звонка для входящие и исходящие звонки с помощью политики CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="e900f-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="e900f-112">Дополнительные сведения см. в [дополнительных сведениях об ИД строки звонков и Названии вызываемой стороны.](more-about-calling-line-id-and-calling-party-name.md)</span><span class="sxs-lookup"><span data-stu-id="e900f-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="e900f-113">ИД вызываемой службы для исходящие вызовы через ПСС</span><span class="sxs-lookup"><span data-stu-id="e900f-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="e900f-114">Для исходящие ИД вызываемой службы ПСС доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e900f-114">For the outbound PSTN caller ID, the following options are available.</span></span> 

> [!NOTE]
> <span data-ttu-id="e900f-115">Некоторые параметры, указанные ниже, доступны в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="e900f-115">Some options, indicated below, are in preview release.</span></span>
  
- <span data-ttu-id="e900f-116">Номер телефона, назначенный пользователю, который задан по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e900f-116">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="e900f-117">Анонимный доступ, который можно получить, удалив презентацию номера ЗВОНКОВ пользователя.</span><span class="sxs-lookup"><span data-stu-id="e900f-117">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="e900f-118">Замените номер телефона, который может быть:</span><span class="sxs-lookup"><span data-stu-id="e900f-118">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="e900f-119">Номер телефона, классифицированный как услуга, и бесплатный номер в перечне номеров телефонов планов звонков.</span><span class="sxs-lookup"><span data-stu-id="e900f-119">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="e900f-120">Как правило, она назначена авто Teams или очереди вызовов.</span><span class="sxs-lookup"><span data-stu-id="e900f-120">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="e900f-121">**Предварительный выпуск.**</span><span class="sxs-lookup"><span data-stu-id="e900f-121">**Preview release.**</span></span> <span data-ttu-id="e900f-122">Номер локального телефона в рамках прямой маршрутиза путем перенаправки, который назначен учетной записи ресурса, используемой Teams автозаправщиком или очередью вызовов.</span><span class="sxs-lookup"><span data-stu-id="e900f-122">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="e900f-123">**Предварительный выпуск.**</span><span class="sxs-lookup"><span data-stu-id="e900f-123">**Preview release.**</span></span> <span data-ttu-id="e900f-124">Имя вызываемой стороны или CNAM, задаваемая в исходящие вызовы по ПСN.</span><span class="sxs-lookup"><span data-stu-id="e900f-124">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="e900f-125">Дополнительные сведения см. в [этой](./set-the-caller-id-for-a-user.md)записи.</span><span class="sxs-lookup"><span data-stu-id="e900f-125">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="e900f-126">Управление конечным пользователем для ид исходящие вызовы</span><span class="sxs-lookup"><span data-stu-id="e900f-126">End user control of outbound caller ID</span></span>

<span data-ttu-id="e900f-127">Пользователи могут изменить параметр "Анонимный" в параметре "Анонимный",  задав атрибут EnableUserOverride.</span><span class="sxs-lookup"><span data-stu-id="e900f-127">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="e900f-128">Если для исходячего звонка задан анонимный ИД, EnableUserOverride не действует, а для него всегда установлено анонимное.</span><span class="sxs-lookup"><span data-stu-id="e900f-128">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="e900f-129">По умолчанию EnableUserOverride имеет значение False.</span><span class="sxs-lookup"><span data-stu-id="e900f-129">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="e900f-130">Конечные пользователи могут сделать свой ИД звонячего анонимным, выбрав Параметры > **Вызовы**, а затем в области ИД звонив **выберите** Скрыть номер телефона и данные профиля для всех **звонков**.</span><span class="sxs-lookup"><span data-stu-id="e900f-130">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="e900f-131">Notes</span><span class="sxs-lookup"><span data-stu-id="e900f-131">Notes</span></span>

<span data-ttu-id="e900f-132">Учитывайте следующее.</span><span class="sxs-lookup"><span data-stu-id="e900f-132">Keep the following in mind:</span></span>

- <span data-ttu-id="e900f-133">Для исходящие номера телефонов нельзя назначать следующие типы номеров:</span><span class="sxs-lookup"><span data-stu-id="e900f-133">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="e900f-134">Любые телефонные номера, которые классифицируются как пользовательские, в перечне номеров телефонов планов звонков.</span><span class="sxs-lookup"><span data-stu-id="e900f-134">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="e900f-135">Любой номер локального телефона через прямую маршрутику, который назначен пользователю.</span><span class="sxs-lookup"><span data-stu-id="e900f-135">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="e900f-136">Номер Skype для бизнеса Server локального телефона.</span><span class="sxs-lookup"><span data-stu-id="e900f-136">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="e900f-137">Подстановка номеров телефонов для учетных записей ресурсов работает только для Teams пользователей.</span><span class="sxs-lookup"><span data-stu-id="e900f-137">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="e900f-138">Замена номеров телефонов службы работает как для Skype для бизнеса Online, так и Teams пользователей.</span><span class="sxs-lookup"><span data-stu-id="e900f-138">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="e900f-139">Имя вызываемой стороны отправляется только при звонках, когда ИД звонящая заменяется номером телефона LineUri, номером телефона учетной записи службы или ресурса, а также при Teams пользователем.</span><span class="sxs-lookup"><span data-stu-id="e900f-139">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="e900f-140">Имя вызываемой стороны может иметь не более 200 символов, но система, ходящий вниз, может поддерживать меньше символов.</span><span class="sxs-lookup"><span data-stu-id="e900f-140">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="e900f-141">При прямой маршрутике подстановка номеров телефонов и имя вызываемой стороны отправляются в заглавной области FROM SIP.</span><span class="sxs-lookup"><span data-stu-id="e900f-141">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="e900f-142">Если соответствующая веб-часть OnlinePstnGateway настроена с помощью ForwardPai = True, заглавная карточка SIP P-НАСТОЛ-IDENTITY будет содержать реально вызывающего пользователя.</span><span class="sxs-lookup"><span data-stu-id="e900f-142">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="e900f-143">EnableUserOverride имеет приоритет над другими настройками в политике, если подстановка не задана для параметра Анонимно.</span><span class="sxs-lookup"><span data-stu-id="e900f-143">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="e900f-144">Например, предположим, что экземпляр политики имеет подстановку с помощью учетной записи ресурса, а enableUserOverride задан и включен пользователем.</span><span class="sxs-lookup"><span data-stu-id="e900f-144">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="e900f-145">В этом случае ИД исходящие звонки будут заблокированы и будут использоваться анонимные.</span><span class="sxs-lookup"><span data-stu-id="e900f-145">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="e900f-146">Если для экземпляра политики задано анонимное подстановка и задан параметр EnableUserOverride, то исходящие звонки всегда будут анонимными независимо от настроек конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="e900f-146">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="e900f-147">ИД входящий звонок</span><span class="sxs-lookup"><span data-stu-id="e900f-147">Inbound caller ID</span></span>

<span data-ttu-id="e900f-148">телефонная система номер входящих внешних телефонов в качестве ИД звоня.</span><span class="sxs-lookup"><span data-stu-id="e900f-148">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="e900f-149">Если номер связан с пользователем или контактом в Azure AD или личном контакте, клиенты Skype для бизнеса и Teams будут показывать ИД вызываемого пользователя на основе этой информации.</span><span class="sxs-lookup"><span data-stu-id="e900f-149">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="e900f-150">Если номер телефона не находится в Azure AD или личном контакте, отображается отображаемая телефонная связь, если она доступна.</span><span class="sxs-lookup"><span data-stu-id="e900f-150">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="e900f-151">Атрибут BlockIncomingCallerID обеспечивает блокирование идентификатора абонента на входящие вызовы в сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="e900f-151">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="e900f-152">Можно задать этот атрибут, но он не доступен вашим пользователям на странице параметров пользователей.</span><span class="sxs-lookup"><span data-stu-id="e900f-152">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="e900f-153">Если этот параметр включен, входящий звонок по STN будет отображаться как исходящая от анонимного.</span><span class="sxs-lookup"><span data-stu-id="e900f-153">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="e900f-154">Чтобы заблокировать ИД входящие вызовы, см. настройка ИД звоня для [пользователя.](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="e900f-154">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e900f-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="e900f-155">Related topics</span></span>
[<span data-ttu-id="e900f-156">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="e900f-156">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="e900f-157">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="e900f-157">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="e900f-158">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="e900f-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="e900f-159">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="e900f-159">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="e900f-160">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="e900f-160">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
