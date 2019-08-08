---
title: Облачная голосовая связь в Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Главная страница для развертывания облачной голосовой связи в Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7a17e207911ad4865cef5b82f7fe7f5f143a172
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236983"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="ff027-103">Облачная голосовая связь в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff027-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="ff027-104">Вы выполнили задачу [Начало работы](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="ff027-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="ff027-105">Вы развернули Teams с [чатом, командами, каналами и приложениями](deploy-chat-teams-channels-microsoft-teams-landing-page.md) в пределах всей организации.</span><span class="sxs-lookup"><span data-stu-id="ff027-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="ff027-106">Возможно, вы развернули [собрания & конференции](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="ff027-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="ff027-107">Теперь вы можете добавлять возможности облачных голосовых возможностей для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ff027-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="ff027-108">Облачный голосовой звонок обеспечивает возможности обмена данными в частной ветви (АТС) и параметры для подключения к телефонной сети с открытым коммутируемым подключением (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="ff027-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="ff027-109">В этой статье рассказывается, как выбрать, нужно ли вам изменить какие-либо настройки голосовой связи по умолчанию, в зависимости от профиля организации и требований бизнеса, после чего вы сможете пройти все изменения.</span><span class="sxs-lookup"><span data-stu-id="ff027-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="ff027-110">Мы разделяем настройки на две группы, начиная с основного набора изменений, которые, возможно, [вам нужно будет создать](#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="ff027-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="ff027-111">Вторая группа включает в себя [дополнительные параметры](#additional-deployment-decisions), которые вы можете захотеть настроить, с учетом потребностей вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ff027-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="ff027-112">Рекомендуется, чтобы все организации работали по основным решениям, а затем, если у вашей организации есть дополнительные требования, ознакомьтесь со следующими материалами.</span><span class="sxs-lookup"><span data-stu-id="ff027-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="ff027-113">Дополнительные сведения о облачных голосах</span><span class="sxs-lookup"><span data-stu-id="ff027-113">Learn more about cloud voice</span></span>

<span data-ttu-id="ff027-114">В следующих статьях содержатся дополнительные сведения о развертывании и использовании облачных функций голосовой связи в Teams.</span><span class="sxs-lookup"><span data-stu-id="ff027-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="ff027-115">Телефонная система Office 365</span><span class="sxs-lookup"><span data-stu-id="ff027-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="ff027-116">Телефонная система с тарифными планами</span><span class="sxs-lookup"><span data-stu-id="ff027-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="ff027-117">Прямая маршрутизация телефонной системы</span><span class="sxs-lookup"><span data-stu-id="ff027-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="ff027-118">Развертывание облачной системы голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ff027-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="ff027-119">Решения Майкрософт для телефонии</span><span class="sxs-lookup"><span data-stu-id="ff027-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="ff027-120">Чтобы узнать больше о телефонной системе, просмотрите следующий сеанс: [Введение в телефонную систему в Microsoft Teams](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="ff027-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="ff027-121">Основные решения по развертыванию</span><span class="sxs-lookup"><span data-stu-id="ff027-121">Core deployment decisions</span></span>

<span data-ttu-id="ff027-122">Ниже перечислены параметры, которые большинство организаций предпочитают изменить (если параметры Teams по умолчанию не подходят).</span><span class="sxs-lookup"><span data-stu-id="ff027-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="ff027-123">Телефонная система (Office 365)</span><span class="sxs-lookup"><span data-stu-id="ff027-123">Phone System (Office 365)</span></span>

<span data-ttu-id="ff027-124">Телефонная система — это технология Microsoft, позволяющая использовать возможности управления звонками и обмена личной ветвью (АТС) в облаке Office 365.</span><span class="sxs-lookup"><span data-stu-id="ff027-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="ff027-125">Телефонная система позволяет заменить существующую систему обмена частной ветвью (УАТС) набором функций, непосредственно предоставленных из Office 365 и тесно интегрированных в облачную среду организации.</span><span class="sxs-lookup"><span data-stu-id="ff027-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="ff027-126">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="ff027-126">Ask yourself</span></span>|<span data-ttu-id="ff027-127">Действие</span><span class="sxs-lookup"><span data-stu-id="ff027-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="ff027-128">В каких расположениях пользователи или офисы будут реализовывать телефонную систему?</span><span class="sxs-lookup"><span data-stu-id="ff027-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="ff027-129">Дополнительные сведения о телефонной системе можно найти [в разделе что такое телефонная система в Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ff027-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="ff027-130">Подключение к общественной коммутируемой телефонной сети (КТСОП)</span><span class="sxs-lookup"><span data-stu-id="ff027-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="ff027-131">Чтобы подключить телефонную систему к общественной коммутируемой телефонной сети (PSTN), чтобы пользователи могли звонить по всему миру, вы можете использовать параметры, зависящие от нужды вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ff027-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="ff027-132">Ответьте на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="ff027-132">Ask yourself the following:</span></span>


|<span data-ttu-id="ff027-133">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="ff027-133">Ask yourself</span></span>|<span data-ttu-id="ff027-134">Действие</span><span class="sxs-lookup"><span data-stu-id="ff027-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="ff027-135">Я хочу использовать план звонков Microsoft в качестве несущей для телефонной связи?</span><span class="sxs-lookup"><span data-stu-id="ff027-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="ff027-136">Дополнительные сведения можно найти [в разделе телефонная система с](calling-plan-landing-page.md)тарифными планами.</span><span class="sxs-lookup"><span data-stu-id="ff027-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="ff027-137">Нужно ли использовать собственную телефонную салазку?</span><span class="sxs-lookup"><span data-stu-id="ff027-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="ff027-138">Дополнительные сведения можно найти [в разделе телефонная система с прямым маршрутом](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="ff027-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="ff027-139">Дополнительные решения по развертыванию</span><span class="sxs-lookup"><span data-stu-id="ff027-139">Additional deployment decisions</span></span>

<span data-ttu-id="ff027-140">Вы можете изменить параметры, указанные ниже, в зависимости от потребностей Организации и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ff027-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="ff027-141">Голосовая почта</span><span class="sxs-lookup"><span data-stu-id="ff027-141">Voicemail</span></span>
- <span data-ttu-id="ff027-142">Идентификация звонка</span><span class="sxs-lookup"><span data-stu-id="ff027-142">Calling identity</span></span>
- <span data-ttu-id="ff027-143">Номера телефонов от корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ff027-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="ff027-144">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="ff027-144">Dial plans</span></span>
- <span data-ttu-id="ff027-145">Очередь звонков</span><span class="sxs-lookup"><span data-stu-id="ff027-145">Call queues</span></span>
- <span data-ttu-id="ff027-146">Автосекретари</span><span class="sxs-lookup"><span data-stu-id="ff027-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="ff027-147">Голосовая почта</span><span class="sxs-lookup"><span data-stu-id="ff027-147">Voicemail</span></span>

<span data-ttu-id="ff027-148">Облачная Голосовая почта, основанная на службах голосовой почты Azure, поддерживает депозиты голосовой почты только для почтовых ящиков Exchange и не поддерживает сторонние системы электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ff027-148">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="ff027-149">Облачная Голосовая почта включает функцию транскрипции голосовой почты, которая включена для всех пользователей в вашей организации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ff027-149">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="ff027-150">Для вашего бизнеса может потребоваться отключить функцию транскрипции голосовой почты для отдельных пользователей или всех участников в рамках всей Организации.</span><span class="sxs-lookup"><span data-stu-id="ff027-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="ff027-151">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="ff027-151">Ask yourself</span></span>|<span data-ttu-id="ff027-152">Действие</span><span class="sxs-lookup"><span data-stu-id="ff027-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="ff027-153">Вы хотите включить облачную голосовую почту?</span><span class="sxs-lookup"><span data-stu-id="ff027-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="ff027-154">Инструкции по настройке голосовой почты можно найти в разделе [Настройка голосовой почты](set-up-phone-system-voicemail.md)в облаке.</span><span class="sxs-lookup"><span data-stu-id="ff027-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="ff027-155">Нужно ли включить функцию транскрипции голосовой почты для некоторых или всех пользователей?</span><span class="sxs-lookup"><span data-stu-id="ff027-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="ff027-156">Сведения о том, как отключить транскрипцию голосовой почты, можно найти [в разделе Настройка политик голосовой почты в Организации](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="ff027-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="ff027-157">Идентификация звонка</span><span class="sxs-lookup"><span data-stu-id="ff027-157">Calling identity</span></span>

<span data-ttu-id="ff027-158">По умолчанию во всех исходящих звонках используется назначенный номер телефона для идентификации звонка (идентификатор вызывающего абонента).</span><span class="sxs-lookup"><span data-stu-id="ff027-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="ff027-159">Получатель звонка может быстро идентифицировать звонящего и решить, следует ли принять или отклонить вызов.</span><span class="sxs-lookup"><span data-stu-id="ff027-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="ff027-160">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="ff027-160">Ask yourself</span></span>|<span data-ttu-id="ff027-161">Действие</span><span class="sxs-lookup"><span data-stu-id="ff027-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="ff027-162">Нужно ли маскировать или отключать идентификатор вызывающего абонента?</span><span class="sxs-lookup"><span data-stu-id="ff027-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="ff027-163">Чтобы изменить или заблокировать идентификатор вызывающего абонента, обратитесь к разделу [Установка идентификатора вызывающего абонента для пользователя](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="ff027-163">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="ff027-164">Номера телефонов от корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ff027-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="ff027-165">У Microsoft есть два типа телефонных номеров: номера *абонентов* (пользователей), которые могут быть назначены для пользователей в вашей организации, и номера *услуг* , доступные в виде платных и бесплатных номеров услуг, которые повышают одновременные звонки емкостью, чем номера абонентов, и они могут быть назначены для таких служб, как голосовая конференция, автосекретарь или очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="ff027-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="ff027-166">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="ff027-166">Ask yourself</span></span>|<span data-ttu-id="ff027-167">Действие</span><span class="sxs-lookup"><span data-stu-id="ff027-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="ff027-168">В каких расположениях пользователей должны быть введены новые номера телефонов из Microsoft?</span><span class="sxs-lookup"><span data-stu-id="ff027-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="ff027-169">Сведения о том, как получить телефонные номера, можно найти в разделе [Управление номерами телефонов для Организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) и [сбор телефонных номеров для пользователей](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="ff027-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="ff027-170">Какой тип номера телефона (подписчика или службы) нужен?</span><span class="sxs-lookup"><span data-stu-id="ff027-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="ff027-171">Чтобы выбрать нужный тип номера телефона, ознакомьтесь с разрешениями, [используемыми для планов звонков, на разных видах номеров](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="ff027-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="ff027-172">Как перенести существующие номера телефонов в Office 365?</span><span class="sxs-lookup"><span data-stu-id="ff027-172">How do I port existing phone numbers to Office 365?</span></span>|<span data-ttu-id="ff027-173">Дополнительные сведения можно найти [в разделе Передача номеров телефонов в Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ff027-173">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="ff027-174">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="ff027-174">Dial plans</span></span>

<span data-ttu-id="ff027-175">Абонентская группа в компоненте "телефонная система" в Office 365 — это набор правил нормализации, который преобразует номера набранных номеров в альтернативный формат (обычно это формат E. 164) для авторизации звонков и маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="ff027-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="ff027-176">Дополнительные сведения об абонентских группах см. в статье [Что такое абонентские группы?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="ff027-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="ff027-177">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="ff027-177">Ask yourself</span></span>|<span data-ttu-id="ff027-178">Действие</span><span class="sxs-lookup"><span data-stu-id="ff027-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="ff027-179">Требуется ли моей организации настраиваемая абонентская группа?</span><span class="sxs-lookup"><span data-stu-id="ff027-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="ff027-180">Сведения о том, как определить, нужна ли вам пользовательская абонентская группа, можно найти в разделе [планирование абонентских планов](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="ff027-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="ff027-181">Каким пользователям требуется настраиваемая абонентская группа, а также какие клиентские абонентские группы должны быть назначены каждому пользователю?</span><span class="sxs-lookup"><span data-stu-id="ff027-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="ff027-182">Чтобы добавить пользователей в настроенную абонентскую группу в PowerShell, ознакомьтесь с разделами [Создание абонентов и управление ими](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="ff027-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="ff027-183">Очередь звонков</span><span class="sxs-lookup"><span data-stu-id="ff027-183">Call queues</span></span>

<span data-ttu-id="ff027-184">Очереди облачных вызовов включают приветствия, которые используются при звонках на номер телефона для вашей организации, возможность автоматически помещать звонки на удержание и возможность поиска следующего доступного агента звонков для обработки звонка во время звонка. Прослушивание музыки на удержании.</span><span class="sxs-lookup"><span data-stu-id="ff027-184">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="ff027-185">Вы можете создать для своей организации одну или несколько очередей вызовов.</span><span class="sxs-lookup"><span data-stu-id="ff027-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="ff027-186">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="ff027-186">Ask yourself</span></span>|<span data-ttu-id="ff027-187">Действие</span><span class="sxs-lookup"><span data-stu-id="ff027-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="ff027-188">Требуются ли в организации очереди звонков?</span><span class="sxs-lookup"><span data-stu-id="ff027-188">Does my organization need call queues?</span></span> | <span data-ttu-id="ff027-189">Дополнительные сведения можно найти [в разделе Создание очереди облачных звонков](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) и [Настройка телефонной системы](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="ff027-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="ff027-190">Автосекретари</span><span class="sxs-lookup"><span data-stu-id="ff027-190">Auto attendants</span></span>

<span data-ttu-id="ff027-191">Автоматические ассистенты в облаке можно использовать для создания системы меню для Организации, позволяющей внешним и внутренним вызывающим абонентам перемещаться по системе меню для поиска и размещения и передачи звонков пользователям или подразделениям компании в Организации.</span><span class="sxs-lookup"><span data-stu-id="ff027-191">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="ff027-192">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="ff027-192">Ask yourself</span></span>|<span data-ttu-id="ff027-193">Действие</span><span class="sxs-lookup"><span data-stu-id="ff027-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="ff027-194">Требуются ли для моей организации автосекретаря?</span><span class="sxs-lookup"><span data-stu-id="ff027-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="ff027-195">Дополнительные сведения можно найти в разделе [что такое автоматические](what-are-phone-system-auto-attendants.md) автосекретарей и [настроить облачный автоматический секретарь](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="ff027-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="ff027-196">Устройства</span><span class="sxs-lookup"><span data-stu-id="ff027-196">Devices</span></span>

<span data-ttu-id="ff027-197">Дополнительные сведения о поддерживаемых устройствах можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="ff027-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="ff027-198">Управление устройствами в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff027-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="ff027-199">IP-телефоны</span><span class="sxs-lookup"><span data-stu-id="ff027-199">IP Phones</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="ff027-200">USB-устройства для аудио и видео</span><span class="sxs-lookup"><span data-stu-id="ff027-200">USB audio and video devices</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="ff027-201">Интеллектуальная связь для устройств</span><span class="sxs-lookup"><span data-stu-id="ff027-201">Intelligent communications for devices</span></span>](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


