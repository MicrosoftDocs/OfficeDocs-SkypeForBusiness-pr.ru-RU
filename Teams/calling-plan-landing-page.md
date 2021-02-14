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
description: Определите, какой план звонков в телефонной системе (Майкрософт) лучше всего будет обслуживать вашу организацию при голосовой связи через облако в Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71fe92646a3a2976e9a4d393e54ea56a7669b400
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031855"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="bc1eb-103">Какой план звонков подходит для вас?</span><span class="sxs-lookup"><span data-stu-id="bc1eb-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="bc1eb-104">Вы выполнили процесс ["Начало работы".](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="bc1eb-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="bc1eb-105">Вы развернули Teams с [чатом, командами, каналами и приложениями](deploy-chat-teams-channels-microsoft-teams-landing-page.md) в пределах всей организации.</span><span class="sxs-lookup"><span data-stu-id="bc1eb-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="bc1eb-106">Возможно, вы развернули & [для собраний.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="bc1eb-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="bc1eb-107">Теперь вы готовы добавить облачную голосовую нагрузку и решили использовать телефонную систему Майкрософт с планом звонков для подключения к телефонной сети общего пользования (ННР).</span><span class="sxs-lookup"><span data-stu-id="bc1eb-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="bc1eb-108">В этой статье описаны основные решения по развертыванию планов звонков, а также дополнительные факторы, которые может потребоваться настроить в зависимости от потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="bc1eb-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="bc1eb-109">Дополнительные сведения о предложениях Microsoft Cloud Voice вы также можете прочитать в [Microsoft Teams.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="bc1eb-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="bc1eb-110">Подробнее о планах звонков</span><span class="sxs-lookup"><span data-stu-id="bc1eb-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="bc1eb-111">Дополнительные сведения о развертывании и использовании планов звонков Майкрософт можно получить в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="bc1eb-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="bc1eb-112">Телефонная система в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="bc1eb-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="bc1eb-113">Планы звонков для Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="bc1eb-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="bc1eb-114">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="bc1eb-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="bc1eb-115">Основные решения по развертыванию</span><span class="sxs-lookup"><span data-stu-id="bc1eb-115">Core deployment decisions</span></span>

<span data-ttu-id="bc1eb-116">Чтобы использовать в качестве оператора телефонии Майкрософт, необходимо получить лицензии на план звонков и назначить их пользователям телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="bc1eb-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="bc1eb-117">Существует два типа планов звонков:</span><span class="sxs-lookup"><span data-stu-id="bc1eb-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="bc1eb-118">Планы внутренних звонков</span><span class="sxs-lookup"><span data-stu-id="bc1eb-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="bc1eb-119">Планы внутренних и международных звонков</span><span class="sxs-lookup"><span data-stu-id="bc1eb-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="bc1eb-120">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="bc1eb-120">Ask yourself</span></span>|<span data-ttu-id="bc1eb-121">Действие</span><span class="sxs-lookup"><span data-stu-id="bc1eb-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="bc1eb-122">Доступны ли планы звонков в моем регионе?</span><span class="sxs-lookup"><span data-stu-id="bc1eb-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="bc1eb-123">В каких расположениях пользователей будет служба плана звонков?</span><span class="sxs-lookup"><span data-stu-id="bc1eb-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="bc1eb-124">Дополнительные сведения см. в сведениях о доступности стран и регионов для аудиоконференций [и планов звонков.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="bc1eb-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="bc1eb-125">Нужны ли пользователям международные вызовы?</span><span class="sxs-lookup"><span data-stu-id="bc1eb-125">Do my users need international calling?</span></span> | <span data-ttu-id="bc1eb-126">Дополнительные сведения см. в планах [звонков для Microsoft 365 или Office 365.](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="bc1eb-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="bc1eb-127">Есть ли у моих пользователей лицензии на планы звонков?</span><span class="sxs-lookup"><span data-stu-id="bc1eb-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="bc1eb-128">Чтобы приобрести и назначить лицензии, см. шаг [2. Покупка и назначение лицензий.](set-up-calling-plans.md#step-2-buy-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="bc1eb-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="bc1eb-129">У каждого из моих пользователей есть прямой номер телефона «внутрь» (DID)?</span><span class="sxs-lookup"><span data-stu-id="bc1eb-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="bc1eb-130">Чтобы узнать, как получить номера телефонов, см. шаг [3. Получить номера телефонов.](set-up-calling-plans.md#step-3-get-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="bc1eb-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="bc1eb-131">Перенос номеров телефонов в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="bc1eb-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="bc1eb-132">Перенести номера телефонов текущего поставщика услуг в Teams очень просто.</span><span class="sxs-lookup"><span data-stu-id="bc1eb-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="bc1eb-133">После переноса номеров телефонов в Teams корпорация Майкрософт становится вашим поставщиком услуг и вы будете вы выставлены счета за эти телефонные номера.</span><span class="sxs-lookup"><span data-stu-id="bc1eb-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="bc1eb-134">Дополнительные сведения см. в [переносе номеров телефонов в Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bc1eb-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="bc1eb-135">Номера телефонов и местоположения для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="bc1eb-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="bc1eb-136">В планах звонков Microsoft 365 или Office 365 у каждого пользователя в организации должен быть уникальный номер телефона для прямого звонка внутрь (DID) и соответствующий проверенный адрес для экстренного вызова.</span><span class="sxs-lookup"><span data-stu-id="bc1eb-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="bc1eb-137">В адресе также можно указать местоположение для экстренного помощи (например, номер офиса или номер этажа).</span><span class="sxs-lookup"><span data-stu-id="bc1eb-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="bc1eb-138">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="bc1eb-138">Ask yourself</span></span>|<span data-ttu-id="bc1eb-139">Действие</span><span class="sxs-lookup"><span data-stu-id="bc1eb-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="bc1eb-140">Насколько подробным должен быть адрес для экстренного помощи и сведения о расположении?</span><span class="sxs-lookup"><span data-stu-id="bc1eb-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="bc1eb-141">Дополнительные сведения см. в сведениях о [местоположениях, адресах](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)для экстренного вызова и маршрутинге экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="bc1eb-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="bc1eb-142">Удостоверение для звонков</span><span class="sxs-lookup"><span data-stu-id="bc1eb-142">Calling identity</span></span>

<span data-ttu-id="bc1eb-143">По умолчанию все исходящие звонки используют номер назначенного телефона в качестве идентификации вызывающего.</span><span class="sxs-lookup"><span data-stu-id="bc1eb-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="bc1eb-144">Получатель звонка может быстро идентифицировать звонящего и решить, следует ли принять или отклонить вызов.</span><span class="sxs-lookup"><span data-stu-id="bc1eb-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="bc1eb-145">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="bc1eb-145">Ask yourself</span></span>|<span data-ttu-id="bc1eb-146">Действие</span><span class="sxs-lookup"><span data-stu-id="bc1eb-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="bc1eb-147">Нужно ли скрыть или отключить ИД звоня?</span><span class="sxs-lookup"><span data-stu-id="bc1eb-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="bc1eb-148">Чтобы изменить или заблокировать свой ИД звоня, см. также: ["Настройка ИД вызываемой вызовы для пользователя".](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="bc1eb-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




