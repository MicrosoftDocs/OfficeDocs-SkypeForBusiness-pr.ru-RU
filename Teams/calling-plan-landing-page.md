---
title: Планы звонков в Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Вызов план Главная страница
appliesto:
- Microsoft Teams
ms.openlocfilehash: 412797a52e82c03937670e895fea7b42a3ce7b4a
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460758"
---
# <a name="phone-system-with-calling-plans"></a><span data-ttu-id="d29d7-103">Телефонная система с планами звонков</span><span class="sxs-lookup"><span data-stu-id="d29d7-103">Phone System with Calling Plans</span></span> 

<span data-ttu-id="d29d7-104">Вы завершили [приступить к работе](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="d29d7-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="d29d7-105">Вы развернули Teams с [чатом, командами, каналами и приложениями](deploy-chat-teams-channels-microsoft-teams-landing-page.md) в пределах всей организации.</span><span class="sxs-lookup"><span data-stu-id="d29d7-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="d29d7-106">Может быть развертывания [конференц-связи & собрания](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="d29d7-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="d29d7-107">Теперь вы готовы для добавления рабочих нагрузок облачных голосовой связи, и вы решили использовать Microsoft телефонной системой с вызова планирование для подключения к общедоступной переключения телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="d29d7-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="d29d7-108">В этой статье описываются основные развертывания решения, принимаемые при вызове планы, а также дополнительные сведения о выполнении, может потребоваться настроить, исходя из потребностей вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d29d7-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="d29d7-109">Также следует ознакомиться [Облачных голосовой связи в группах Майкрософт](cloud-voice-landing-page.md) Дополнительные сведения об облаке корпорации Майкрософт и услуги голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="d29d7-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="d29d7-110">Дополнительные сведения о вызове планы</span><span class="sxs-lookup"><span data-stu-id="d29d7-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="d29d7-111">Следующие статьи содержат дополнительные сведения о развертывании и использовании Microsoft вызов планов.</span><span class="sxs-lookup"><span data-stu-id="d29d7-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="d29d7-112">Телефонная система в Office 365</span><span class="sxs-lookup"><span data-stu-id="d29d7-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="d29d7-113">Планы звонков для Office 365</span><span class="sxs-lookup"><span data-stu-id="d29d7-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="d29d7-114">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="d29d7-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="d29d7-115">Основные решения по развертыванию</span><span class="sxs-lookup"><span data-stu-id="d29d7-115">Core deployment decisions</span></span>

<span data-ttu-id="d29d7-116">Чтобы использовать Microsoft в качестве своего оператора телефонной связи, необходимо получить вызов планирование лицензии и назначьте их пользователям телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="d29d7-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="d29d7-117">Существует два типа вызова планов.</span><span class="sxs-lookup"><span data-stu-id="d29d7-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="d29d7-118">Внутренние Тарифные планы</span><span class="sxs-lookup"><span data-stu-id="d29d7-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="d29d7-119">Внутреннее и международное Тарифные планы</span><span class="sxs-lookup"><span data-stu-id="d29d7-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="d29d7-120">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="d29d7-120">Ask yourself</span></span>|<span data-ttu-id="d29d7-121">Действие</span><span class="sxs-lookup"><span data-stu-id="d29d7-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="d29d7-122">Доступны вызов планы в Мои области?</span><span class="sxs-lookup"><span data-stu-id="d29d7-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="d29d7-123">Местоположения, в которых пользователь будет иметь вызов планирование службы?</span><span class="sxs-lookup"><span data-stu-id="d29d7-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="d29d7-124">Для получения дополнительных сведений см [страны и региона для конференц-связи аудио и вызов планов](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="d29d7-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="d29d7-125">Нужна ли мои пользователи международных звонков?</span><span class="sxs-lookup"><span data-stu-id="d29d7-125">Do my users need international calling?</span></span> | <span data-ttu-id="d29d7-126">Дополнительные сведения см в [Вызове планы для Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d29d7-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="d29d7-127">Должны ли мои пользователи вызов планы лицензий?</span><span class="sxs-lookup"><span data-stu-id="d29d7-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="d29d7-128">Чтобы приобрести и назначение лицензий, обратитесь к разделу [Шаг 2: купить и назначение лицензий](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="d29d7-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="d29d7-129">Должны ли мои пользователи прямых внутрь наберите номер телефона (DID)?</span><span class="sxs-lookup"><span data-stu-id="d29d7-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="d29d7-130">Чтобы получить номера телефонов, обратитесь к разделу [Шаг 3: Получение номера телефонов](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="d29d7-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="d29d7-131">Передача номеров телефонов в Office 365</span><span class="sxs-lookup"><span data-stu-id="d29d7-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="d29d7-132">Это просто перенести номеров телефонов из текущего поставщика услуг в группы.</span><span class="sxs-lookup"><span data-stu-id="d29d7-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="d29d7-133">После порт номера телефонов для групп, Microsoft станет поставщиком услуг и будет выставления счетов для тех номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="d29d7-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="d29d7-134">Дополнительные сведения можно [Переключить телефонных номеров в Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d29d7-134">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="d29d7-135">Номера телефонов и местоположения для экстренного реагирования</span><span class="sxs-lookup"><span data-stu-id="d29d7-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="d29d7-136">С помощью вызова планы в Office 365 все пользователи в вашей организации должно иметь уникальное прямого входящего набора телефона номер и соответствующий адрес проверенный emergency.</span><span class="sxs-lookup"><span data-stu-id="d29d7-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="d29d7-137">Также можно задать экстренных места в пределах экстренных адрес (например, номер офиса или этаж).</span><span class="sxs-lookup"><span data-stu-id="d29d7-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="d29d7-138">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="d29d7-138">Ask yourself</span></span>|<span data-ttu-id="d29d7-139">Действие</span><span class="sxs-lookup"><span data-stu-id="d29d7-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="d29d7-140">Как подробные надо экстренных адрес и расположение сведения?</span><span class="sxs-lookup"><span data-stu-id="d29d7-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="d29d7-141">Дополнительные сведения можно [Каковы местоположении для экстренных служб, адресов и маршрутизации вызовов?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="d29d7-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="d29d7-142">Идентификатор звонящего абонента</span><span class="sxs-lookup"><span data-stu-id="d29d7-142">Calling identity</span></span>

<span data-ttu-id="d29d7-143">По умолчанию все исходящие вызовы использовать назначенный номер в качестве удостоверения вызывающей (Звонящего).</span><span class="sxs-lookup"><span data-stu-id="d29d7-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="d29d7-144">Получатель звонка может быстро идентифицировать звонящего и решить, следует ли принять или отклонить вызов.</span><span class="sxs-lookup"><span data-stu-id="d29d7-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="d29d7-145">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="d29d7-145">Ask yourself</span></span>|<span data-ttu-id="d29d7-146">Действие</span><span class="sxs-lookup"><span data-stu-id="d29d7-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="d29d7-147">Хотите скрытие или отключение Звонящего?</span><span class="sxs-lookup"><span data-stu-id="d29d7-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="d29d7-148">[Идентификатор звонящего для пользователя,](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user)Чтобы изменить или заблокировать идентификатора звонящего, см.</span><span class="sxs-lookup"><span data-stu-id="d29d7-148">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||




