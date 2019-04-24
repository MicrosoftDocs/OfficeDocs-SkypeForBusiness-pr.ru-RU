---
title: Облачная голосовая связь в Microsoft Teams
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
description: Главная страница для развертывания облака голосовой связи в группах
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47c534eba93c6f5af21a75fa20b5015fac00c674
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198373"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="cb833-103">Облачная голосовая связь в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cb833-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="cb833-104">Вы выполнили задачу [Начало работы](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="cb833-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="cb833-105">Вы развернули Teams с [чатом, командами, каналами и приложениями](deploy-chat-teams-channels-microsoft-teams-landing-page.md) в пределах всей организации.</span><span class="sxs-lookup"><span data-stu-id="cb833-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="cb833-106">Может быть развертывания [конференц-связи & собрания](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="cb833-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="cb833-107">Теперь вы готовы к добавлять облачных возможности голосовой связи для пользователей.</span><span class="sxs-lookup"><span data-stu-id="cb833-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="cb833-108">Облако голосовой предоставляет возможности Exchange закрытый филиала (УАТС) и параметры для подключения к общедоступной переключения телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="cb833-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="cb833-109">Эта статья поможет вам решить, нужно ли изменять любые параметры по умолчанию облачных голосовой связи, на основе профилей вашей организации и бизнес-требования, а затем его — описание каждого изменения.</span><span class="sxs-lookup"><span data-stu-id="cb833-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="cb833-110">Мы разделение параметры на две группы, начиная с базовый набор [вы, скорее всего, внесите изменения](#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="cb833-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="cb833-111">Вторая группа включает в себя [дополнительные параметры](#additional-deployment-decisions), которые вы можете захотеть настроить, с учетом потребностей вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cb833-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="cb833-112">Рекомендуется всей организации работает через основные решения и, если в вашей организации есть дополнительные требования, просмотрите следующие материалы.</span><span class="sxs-lookup"><span data-stu-id="cb833-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="cb833-113">Дополнительные сведения об облаке голосовой связи</span><span class="sxs-lookup"><span data-stu-id="cb833-113">Learn more about cloud voice</span></span>

<span data-ttu-id="cb833-114">Следующие статьи содержат дополнительные сведения о развертывании и использовании функции голосовой связи облака в группах.</span><span class="sxs-lookup"><span data-stu-id="cb833-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="cb833-115">Телефонная система Office 365</span><span class="sxs-lookup"><span data-stu-id="cb833-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="cb833-116">Система телефон с Тарифные планы</span><span class="sxs-lookup"><span data-stu-id="cb833-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="cb833-117">Прямая маршрутизация телефонной системы</span><span class="sxs-lookup"><span data-stu-id="cb833-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="cb833-118">Развертывание облачной системы голосовой связи</span><span class="sxs-lookup"><span data-stu-id="cb833-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="cb833-119">Решения Майкрософт для телефонии</span><span class="sxs-lookup"><span data-stu-id="cb833-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="cb833-120">Просмотрите следующие сеанса для получения дополнительных сведений о телефонной системой: [Знакомство с телефонной системой в группах Майкрософт](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="cb833-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="cb833-121">Основные решения по развертыванию</span><span class="sxs-lookup"><span data-stu-id="cb833-121">Core deployment decisions</span></span>

<span data-ttu-id="cb833-122">Ниже перечислены параметры, которые большинство организаций предпочитают изменить (если параметры Teams по умолчанию не подходят).</span><span class="sxs-lookup"><span data-stu-id="cb833-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="cb833-123">Телефонной системой (Office 365)</span><span class="sxs-lookup"><span data-stu-id="cb833-123">Phone System (Office 365)</span></span>

<span data-ttu-id="cb833-124">Телефонной системой — технология корпорации Майкрософт для включения управления звонками и возможности Exchange закрытый филиала (УАТС) в облаке Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb833-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="cb833-125">Телефонной системой можно заменить существующий закрытый Exchange филиала (УАТС) систему на набор функциональных возможностей непосредственно доставленных в период с Office 365 и тесно интегрируются с среда работы организации в облако.</span><span class="sxs-lookup"><span data-stu-id="cb833-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="cb833-126">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="cb833-126">Ask yourself</span></span>|<span data-ttu-id="cb833-127">Действие</span><span class="sxs-lookup"><span data-stu-id="cb833-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="cb833-128">В какие пользователя расположения или офисов будет реализовано телефонной системой?</span><span class="sxs-lookup"><span data-stu-id="cb833-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="cb833-129">Дополнительные сведения о телефонной системой приведены в статье [телефонной системой в Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="cb833-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="cb833-130">Подключение для общего пользования телефонной сети (общего пользования PSTN)</span><span class="sxs-lookup"><span data-stu-id="cb833-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="cb833-131">Для подключения телефонной системой для общедоступных переключения телефонной сети общего пользования (PSTN), чтобы пользователи могут выполнять телефонные звонки по всему миру, возможны варианты на основе принципа необходимого.</span><span class="sxs-lookup"><span data-stu-id="cb833-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="cb833-132">Ответьте на следующие:</span><span class="sxs-lookup"><span data-stu-id="cb833-132">Ask yourself the following:</span></span>


|<span data-ttu-id="cb833-133">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="cb833-133">Ask yourself</span></span>|<span data-ttu-id="cb833-134">Действие</span><span class="sxs-lookup"><span data-stu-id="cb833-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="cb833-135">Я хочу использовать вызов планирование Microsoft в качестве Мои поставщика телефонии?</span><span class="sxs-lookup"><span data-stu-id="cb833-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="cb833-136">Для получения дополнительных сведений см [Телефонной системы с помощью вызова планов](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="cb833-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="cb833-137">Нужно ли использовать собственный поставщика телефонии?</span><span class="sxs-lookup"><span data-stu-id="cb833-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="cb833-138">Для получения дополнительных сведений см [Телефонной системой при прямой маршрутизации](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="cb833-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="cb833-139">Дополнительные варианты развертывания</span><span class="sxs-lookup"><span data-stu-id="cb833-139">Additional deployment decisions</span></span>

<span data-ttu-id="cb833-140">Может потребоваться изменить параметры для следующего случая зависимости от потребностей организации и конфигурации:</span><span class="sxs-lookup"><span data-stu-id="cb833-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="cb833-141">Голосовая почта</span><span class="sxs-lookup"><span data-stu-id="cb833-141">Voicemail</span></span>
- <span data-ttu-id="cb833-142">Вызов удостоверений</span><span class="sxs-lookup"><span data-stu-id="cb833-142">Calling identity</span></span>
- <span data-ttu-id="cb833-143">Номера телефонов корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cb833-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="cb833-144">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="cb833-144">Dial plans</span></span>
- <span data-ttu-id="cb833-145">Очередь звонков</span><span class="sxs-lookup"><span data-stu-id="cb833-145">Call queues</span></span>
- <span data-ttu-id="cb833-146">Автосекретари</span><span class="sxs-lookup"><span data-stu-id="cb833-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="cb833-147">Голосовая почта</span><span class="sxs-lookup"><span data-stu-id="cb833-147">Voicemail</span></span>

<span data-ttu-id="cb833-148">Голосовой почты в облаке, на базе служб Azure голосовой почты, поддерживает вклады голосовой почты в почтовые ящики Exchange только и не поддерживает систем электронной почты сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="cb833-148">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="cb833-149">Голосовая почта облако включает в себя транскрибирования голосовой почты, который включен по умолчанию для всех пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cb833-149">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="cb833-150">Бизнес-требованиям может потребоваться отключить транскрибирования голосовой почты для определенных пользователей или всем пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="cb833-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="cb833-151">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="cb833-151">Ask yourself</span></span>|<span data-ttu-id="cb833-152">Действие</span><span class="sxs-lookup"><span data-stu-id="cb833-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="cb833-153">Требуется ли включение голосовой почты в облаке?</span><span class="sxs-lookup"><span data-stu-id="cb833-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="cb833-154">[Настройка голосовой почты в облаке](set-up-phone-system-voicemail.md)процедуры настройки голосовой почты, см.</span><span class="sxs-lookup"><span data-stu-id="cb833-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="cb833-155">Требуется ли включение транскрибирования голосовой почты для некоторых или всех Мои пользователи?</span><span class="sxs-lookup"><span data-stu-id="cb833-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="cb833-156">Чтобы отключить транскрибирования голосовой почты, обратитесь к [настройке политик голосовой почты в вашей организации](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="cb833-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="cb833-157">Вызов удостоверений</span><span class="sxs-lookup"><span data-stu-id="cb833-157">Calling identity</span></span>

<span data-ttu-id="cb833-158">По умолчанию все исходящие вызовы использовать назначенный номер в качестве удостоверения вызывающей (Звонящего).</span><span class="sxs-lookup"><span data-stu-id="cb833-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="cb833-159">Получатель звонка может быстро идентифицировать звонящего и решить, следует ли принять или отклонить вызов.</span><span class="sxs-lookup"><span data-stu-id="cb833-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="cb833-160">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="cb833-160">Ask yourself</span></span>|<span data-ttu-id="cb833-161">Действие</span><span class="sxs-lookup"><span data-stu-id="cb833-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="cb833-162">Хотите скрытие или отключение Звонящего?</span><span class="sxs-lookup"><span data-stu-id="cb833-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="cb833-163">[Идентификатор звонящего для пользователя,](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user)Чтобы изменить или заблокировать идентификатора звонящего, см.</span><span class="sxs-lookup"><span data-stu-id="cb833-163">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="cb833-164">Номера телефонов корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cb833-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="cb833-165">Корпорация Майкрософт предлагает два типа доступных телефонных номеров: номера *подписчика* (пользователь), которые можно назначить пользователям в вашей организации и доступные как международную и службы бесплатных номеров, которые имеют возможность выполнения одновременных звонков выше номера *службы* емкостью, чем номера и могут быть назначены службы, такие как аудио конференц-связи, автосекретари или позвонить очереди.</span><span class="sxs-lookup"><span data-stu-id="cb833-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="cb833-166">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="cb833-166">Ask yourself</span></span>|<span data-ttu-id="cb833-167">Действие</span><span class="sxs-lookup"><span data-stu-id="cb833-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="cb833-168">Местоположения пользователя, в которых требуется нового номера телефонов корпорацией Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="cb833-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="cb833-169">Сведения о получении телефонных номеров содержатся в разделе [Управление номера телефонов для вашей организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) и [Получение номера телефонов для пользователей](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="cb833-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span></span> 
| <span data-ttu-id="cb833-170">Какой тип телефонный номер (подписчика или службы) требуется?</span><span class="sxs-lookup"><span data-stu-id="cb833-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="cb833-171">Чтобы выбрать тип номера телефона, нужно просмотреть [различные виды телефонных номеров, используемый для вызова планов](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="cb833-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="cb833-172">Как мне порт существующего номера телефонов в Office 365?</span><span class="sxs-lookup"><span data-stu-id="cb833-172">How do I port existing phone numbers to Office 365?</span></span>|<span data-ttu-id="cb833-173">Дополнительные сведения можно [Переключить телефонных номеров в Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="cb833-173">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="cb833-174">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="cb833-174">Dial plans</span></span>

<span data-ttu-id="cb833-175">К абонентской группе в компоненте телефонной системой Office 365 — набор правил нормализации, переводить набора телефонных номеров в альтернативный формат (обычно формат E.164) для маршрутизации вызовов и проверка подлинности вызовов.</span><span class="sxs-lookup"><span data-stu-id="cb833-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="cb833-176">Дополнительные сведения об абонентских группах см. в статье [Что такое абонентские группы?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="cb833-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="cb833-177">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="cb833-177">Ask yourself</span></span>|<span data-ttu-id="cb833-178">Действие</span><span class="sxs-lookup"><span data-stu-id="cb833-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="cb833-179">Требуется ли моей организации настраиваемая абонентская группа?</span><span class="sxs-lookup"><span data-stu-id="cb833-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="cb833-180">Для определения необходимости настраиваемых абонентской группы, см [для клиента абонентские группы](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="cb833-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="cb833-181">Каким пользователям требуется настраиваемая абонентская группа, а также какие клиентские абонентские группы должны быть назначены каждому пользователю?</span><span class="sxs-lookup"><span data-stu-id="cb833-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="cb833-182">Чтобы добавить пользователей к настраиваемой абонентской группе в PowerShell, обратитесь к разделу [Создание и управление ими абонентских групп](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="cb833-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="cb833-183">Очередь звонков</span><span class="sxs-lookup"><span data-stu-id="cb833-183">Call queues</span></span>

<span data-ttu-id="cb833-184">Облако вызова очередей включают приветствие, используемые при получении звонка на номер телефона для вашей организации, возможность автоматически переводить звонки в режим удержания и возможность поиска для следующего агента доступные вызова для обработки вызова при пользователей, которые являются прослушивание музыки при удержании.</span><span class="sxs-lookup"><span data-stu-id="cb833-184">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="cb833-185">Вы можете создать для своей организации одну или несколько очередей вызовов.</span><span class="sxs-lookup"><span data-stu-id="cb833-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="cb833-186">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="cb833-186">Ask yourself</span></span>|<span data-ttu-id="cb833-187">Действие</span><span class="sxs-lookup"><span data-stu-id="cb833-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="cb833-188">Организации требуется позвонить очереди?</span><span class="sxs-lookup"><span data-stu-id="cb833-188">Does my organization need call queues?</span></span> | <span data-ttu-id="cb833-189">Для получения дополнительных сведений см. [Создание очереди вызовов облако](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) и [Настройка телефонной системой](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="cb833-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="cb833-190">Автосекретари</span><span class="sxs-lookup"><span data-stu-id="cb833-190">Auto attendants</span></span>

<span data-ttu-id="cb833-191">Облако автосекретари можно использовать для создания системы меню для вашей организации, которая позволяет внешним и внутреннего вызывающих объектов перемещения по системе меню Поиск и поместить или переводить звонки компании пользователей или отделов организации.</span><span class="sxs-lookup"><span data-stu-id="cb833-191">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="cb833-192">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="cb833-192">Ask yourself</span></span>|<span data-ttu-id="cb833-193">Действие</span><span class="sxs-lookup"><span data-stu-id="cb833-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="cb833-194">Требуется ли Моя организация автосекретари?</span><span class="sxs-lookup"><span data-stu-id="cb833-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="cb833-195">Для получения дополнительных сведений см [Каковы облачных автосекретарей](what-are-phone-system-auto-attendants.md) и [настроить автосекретарь облака](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="cb833-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> |

### <a name="devices"></a><span data-ttu-id="cb833-196">Устройства</span><span class="sxs-lookup"><span data-stu-id="cb833-196">Devices</span></span>

<span data-ttu-id="cb833-197">Дополнительные сведения о поддерживаемых устройств см.:</span><span class="sxs-lookup"><span data-stu-id="cb833-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="cb833-198">Управление устройствами в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cb833-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="cb833-199">IP-телефонов</span><span class="sxs-lookup"><span data-stu-id="cb833-199">IP Phones</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="cb833-200">USB-устройства для аудио и видео</span><span class="sxs-lookup"><span data-stu-id="cb833-200">USB audio and video devices</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="cb833-201">Интеллектуальный коммуникаций для устройств</span><span class="sxs-lookup"><span data-stu-id="cb833-201">Intelligent communications for devices</span></span>](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


