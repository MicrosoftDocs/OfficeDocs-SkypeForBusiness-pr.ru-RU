---
title: Планы звонков в Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Определите Телефон (Майкрософт) какой план системных звонков лучше всего будет обслуживать вашу организацию с облачную голосовую Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102735"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="4c6c8-103">Какой план звонков подходит для вас?</span><span class="sxs-lookup"><span data-stu-id="4c6c8-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="4c6c8-104">Вы завершили работу с [.](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="4c6c8-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="4c6c8-105">Вы развернули Teams с [чатом, командами, каналами и приложениями](deploy-chat-teams-channels-microsoft-teams-landing-page.md) в пределах всей организации.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="4c6c8-106">Возможно, вы развернули [&](deploy-meetings-microsoft-teams-landing-page.md)собрания.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="4c6c8-107">Теперь вы готовы добавить облачную голосовую нагрузку и решили использовать Телефон (Майкрософт) System с планом звонков для подключения к телефонной сети общего пользования (STN).</span><span class="sxs-lookup"><span data-stu-id="4c6c8-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="4c6c8-108">В этой статье описаны основные решения по развертыванию планов звонков, а также дополнительные факторы, которые может потребоваться настроить в зависимости от потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="4c6c8-109">Дополнительные сведения об облачных голосовых предложениях Майкрософт Microsoft Teams в Cloud [Voice](cloud-voice-landing-page.md) в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="4c6c8-110">Подробнее о планах звонков</span><span class="sxs-lookup"><span data-stu-id="4c6c8-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="4c6c8-111">Дополнительные сведения о развертывании и использовании планов звонков Майкрософт можно получить в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="4c6c8-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="4c6c8-112">телефонная система в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="4c6c8-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="4c6c8-113">Планы звонков для Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="4c6c8-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="4c6c8-114">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="4c6c8-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="4c6c8-115">Основные решения по развертыванию</span><span class="sxs-lookup"><span data-stu-id="4c6c8-115">Core deployment decisions</span></span>

<span data-ttu-id="4c6c8-116">Чтобы использовать Майкрософт в качестве оператора телефонии, необходимо получить лицензии на план звонков и назначить их пользователям телефонная система телефонии.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="4c6c8-117">Существует два типа планов звонков:</span><span class="sxs-lookup"><span data-stu-id="4c6c8-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="4c6c8-118">Планы внутренних звонков</span><span class="sxs-lookup"><span data-stu-id="4c6c8-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="4c6c8-119">Планы внутренних и международных звонков</span><span class="sxs-lookup"><span data-stu-id="4c6c8-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="4c6c8-120">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="4c6c8-120">Ask yourself</span></span>|<span data-ttu-id="4c6c8-121">Действие</span><span class="sxs-lookup"><span data-stu-id="4c6c8-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="4c6c8-122">Доступны ли планы звонков в моем регионе?</span><span class="sxs-lookup"><span data-stu-id="4c6c8-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="4c6c8-123">Какие расположения пользователей будут иметь службу плана звонков?</span><span class="sxs-lookup"><span data-stu-id="4c6c8-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="4c6c8-124">Дополнительные сведения см. в сведениях о доступности страны и региона для аудиоконференций [и планов звонков.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="4c6c8-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="4c6c8-125">Нужны ли пользователям международные вызовы?</span><span class="sxs-lookup"><span data-stu-id="4c6c8-125">Do my users need international calling?</span></span> | <span data-ttu-id="4c6c8-126">Дополнительные сведения см. в [Microsoft 365 или Office 365.](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="4c6c8-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="4c6c8-127">Есть ли у моих пользователей лицензии на планы звонков?</span><span class="sxs-lookup"><span data-stu-id="4c6c8-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="4c6c8-128">Чтобы приобрести и назначить лицензии, см. шаг [2. Покупка и назначение лицензий.](set-up-calling-plans.md#step-2-buy-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="4c6c8-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="4c6c8-129">У каждого из моих пользователей есть номер телефона для прямого звонка внутрь (DID)?</span><span class="sxs-lookup"><span data-stu-id="4c6c8-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="4c6c8-130">Чтобы получить номера телефонов, [см. шаг 3. Получить номера телефонов.](set-up-calling-plans.md#step-3-get-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="4c6c8-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="4c6c8-131">Перенос номеров телефонов Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="4c6c8-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="4c6c8-132">Перенести номера телефонов от текущего поставщика услуг в Teams.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="4c6c8-133">После переноса номеров телефонов в Teams поставщиком услуг становится корпорация Майкрософт, которая вы выставлена вам счета за эти телефонные номера.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="4c6c8-134">Дополнительные сведения см. в [этой](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="4c6c8-135">Номера телефонов и местоположения для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="4c6c8-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="4c6c8-136">Благодаря планам звонков в Microsoft 365 или Office 365 у каждого пользователя в организации должен быть уникальный номер телефона для прямого звонка внутрь (DID) и соответствующий проверенный адрес для экстренного вызова.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="4c6c8-137">Вы также можете указать местоположение для экстренного обращения в адресе для экстренного обращения (например, номер офиса или номер этажа).</span><span class="sxs-lookup"><span data-stu-id="4c6c8-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="4c6c8-138">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="4c6c8-138">Ask yourself</span></span>|<span data-ttu-id="4c6c8-139">Действие</span><span class="sxs-lookup"><span data-stu-id="4c6c8-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="4c6c8-140">Насколько подробными должны быть адреса для экстренного обращения и сведения о местоположении?</span><span class="sxs-lookup"><span data-stu-id="4c6c8-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="4c6c8-141">Дополнительные сведения см. в [этой](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)теме.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-141">For more information, see [What are emergency locations, addresses, and call routing?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="4c6c8-142">Удостоверение для звонков</span><span class="sxs-lookup"><span data-stu-id="4c6c8-142">Calling identity</span></span>

<span data-ttu-id="4c6c8-143">По умолчанию для всех исходяющих звонков в качестве идентификатора (идентификатора вызывающего) используется номер телефона, который назначен.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="4c6c8-144">Получатель звонка может быстро идентифицировать звонящего и решить, следует ли принять или отклонить вызов.</span><span class="sxs-lookup"><span data-stu-id="4c6c8-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="4c6c8-145">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="4c6c8-145">Ask yourself</span></span>|<span data-ttu-id="4c6c8-146">Действие</span><span class="sxs-lookup"><span data-stu-id="4c6c8-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="4c6c8-147">Нужно ли маскировать или отключать ИД вызываемой вызовы?</span><span class="sxs-lookup"><span data-stu-id="4c6c8-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="4c6c8-148">Чтобы изменить или заблокировать его, см. настройка [ИД вызываемой вызовы для пользователя.](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="4c6c8-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||