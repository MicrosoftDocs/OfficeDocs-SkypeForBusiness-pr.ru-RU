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
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Определите, какой план вызова Microsoft Phone System поможет вам в вашей организации с помощью облачного голоса в Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b1fb0abed3477039f4c19c0e2de0ea696626f35
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905031"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="32b6b-103">Какой план звонков подходит для вас?</span><span class="sxs-lookup"><span data-stu-id="32b6b-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="32b6b-104">Вы выполнили [Начало работы](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="32b6b-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="32b6b-105">Вы развернули Teams с [чатом, командами, каналами и приложениями](deploy-chat-teams-channels-microsoft-teams-landing-page.md) в пределах всей организации.</span><span class="sxs-lookup"><span data-stu-id="32b6b-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="32b6b-106">Возможно, вы развернули [собрания & конференции](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="32b6b-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="32b6b-107">Теперь вы можете добавить облачные рабочие нагрузки, и вы решили использовать телефонную систему Microsoft с планом звонков для подключения к телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="32b6b-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="32b6b-108">В этой статье описаны основные решения по развертыванию планов звонков, а также дополнительные аспекты, которые можно настроить в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="32b6b-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="32b6b-109">Вы также должны прочитать [облачный голосовой звонок в Microsoft Teams](cloud-voice-landing-page.md) , чтобы получить дополнительные сведения о облачных голосовых предложениях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="32b6b-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="32b6b-110">Дополнительные сведения о тарифных планах</span><span class="sxs-lookup"><span data-stu-id="32b6b-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="32b6b-111">В следующих статьях приведены дополнительные сведения о развертывании и использовании планов звонков Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32b6b-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="32b6b-112">Телефонная система Office 365</span><span class="sxs-lookup"><span data-stu-id="32b6b-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="32b6b-113">Планы звонков для Office 365</span><span class="sxs-lookup"><span data-stu-id="32b6b-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="32b6b-114">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="32b6b-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="32b6b-115">Решения по развертыванию основных функций</span><span class="sxs-lookup"><span data-stu-id="32b6b-115">Core deployment decisions</span></span>

<span data-ttu-id="32b6b-116">Чтобы использовать Microsoft в качестве несущей для телефонной связи, необходимо получить лицензии на план звонков и назначить их пользователям телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="32b6b-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="32b6b-117">Доступны два типа планов звонков:</span><span class="sxs-lookup"><span data-stu-id="32b6b-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="32b6b-118">Планы внутренних звонков</span><span class="sxs-lookup"><span data-stu-id="32b6b-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="32b6b-119">Планы внутренних и международных звонков</span><span class="sxs-lookup"><span data-stu-id="32b6b-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="32b6b-120">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="32b6b-120">Ask yourself</span></span>|<span data-ttu-id="32b6b-121">Действие</span><span class="sxs-lookup"><span data-stu-id="32b6b-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="32b6b-122">Доступны ли планы звонков в моей области?</span><span class="sxs-lookup"><span data-stu-id="32b6b-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="32b6b-123">Для каких расположений пользователей будет указана служба плана звонков?</span><span class="sxs-lookup"><span data-stu-id="32b6b-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="32b6b-124">Дополнительные сведения можно найти в разделе [доступ к странам и регионам для голосовой конференции и планов звонков](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="32b6b-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="32b6b-125">Нужно ли пользователям использовать международные звонки?</span><span class="sxs-lookup"><span data-stu-id="32b6b-125">Do my users need international calling?</span></span> | <span data-ttu-id="32b6b-126">Дополнительные сведения можно найти в разделе [планы звонков для Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="32b6b-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="32b6b-127">Есть ли у моих пользователей лицензии на планы звонков?</span><span class="sxs-lookup"><span data-stu-id="32b6b-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="32b6b-128">Для приобретения и назначения лицензий ознакомьтесь с [Раздействием 2: приобретение и назначение лицензий](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="32b6b-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="32b6b-129">Есть ли у моих пользователей прямой телефонный номер?</span><span class="sxs-lookup"><span data-stu-id="32b6b-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="32b6b-130">Чтобы получить телефонные номера, ознакомьтесь со [статьей этап 3: получение телефонных номеров](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="32b6b-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="32b6b-131">Передача номеров телефонов в Office 365</span><span class="sxs-lookup"><span data-stu-id="32b6b-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="32b6b-132">Вы можете легко передавать ваши номера из текущего поставщика услуг в Teams.</span><span class="sxs-lookup"><span data-stu-id="32b6b-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="32b6b-133">После того как вы перейдете на свой номер телефона в Teams, корпорация Майкрософт станет поставщиком услуг и выведет счет за эти телефонные номера.</span><span class="sxs-lookup"><span data-stu-id="32b6b-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="32b6b-134">Дополнительные сведения можно найти [в разделе Перенос номеров телефонов в Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="32b6b-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="32b6b-135">Номера телефонов и местоположения для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="32b6b-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="32b6b-136">В планах звонков в Office 365 каждому пользователю в вашей организации должен быть назначен уникальный прямой телефонный номер и соответствующий адрес проверки на чрезвычайный случай.</span><span class="sxs-lookup"><span data-stu-id="32b6b-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="32b6b-137">Вы также можете указать место для экстренного реагирования в адресе для экстренного реагирования (например, номер Office или номер этажа).</span><span class="sxs-lookup"><span data-stu-id="32b6b-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="32b6b-138">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="32b6b-138">Ask yourself</span></span>|<span data-ttu-id="32b6b-139">Действие</span><span class="sxs-lookup"><span data-stu-id="32b6b-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="32b6b-140">Как сделать так, чтобы адреса для экстренного реагирования и сведения о местоположении были в сети?</span><span class="sxs-lookup"><span data-stu-id="32b6b-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="32b6b-141">Дополнительные сведения можно найти в разделе [что такое места для экстренного реагирования, адреса и маршрутизация звонков?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="32b6b-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="32b6b-142">Идентификация звонка</span><span class="sxs-lookup"><span data-stu-id="32b6b-142">Calling identity</span></span>

<span data-ttu-id="32b6b-143">По умолчанию во всех исходящих звонках используется назначенный номер телефона для идентификации звонка (идентификатор вызывающего абонента).</span><span class="sxs-lookup"><span data-stu-id="32b6b-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="32b6b-144">Получатель звонка может быстро идентифицировать звонящего и решить, следует ли принять или отклонить вызов.</span><span class="sxs-lookup"><span data-stu-id="32b6b-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="32b6b-145">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="32b6b-145">Ask yourself</span></span>|<span data-ttu-id="32b6b-146">Действие</span><span class="sxs-lookup"><span data-stu-id="32b6b-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="32b6b-147">Нужно ли маскировать или отключать идентификатор вызывающего абонента?</span><span class="sxs-lookup"><span data-stu-id="32b6b-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="32b6b-148">Чтобы изменить или заблокировать идентификатор вызывающего абонента, обратитесь к разделу [Установка идентификатора вызывающего абонента для пользователя](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="32b6b-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




