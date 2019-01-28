---
title: Облако голосовой связи в группах Майкрософт
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: crowe
search.appverid: MET150
description: Главная страница для развертывания облака голосовой связи в группах
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f81c9a2c158781303e0d0db67448ae19964cb8d
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595427"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="56f4e-103">Облако голосовой связи в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="56f4e-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="56f4e-104">Вы завершили [приступить к работе](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="56f4e-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="56f4e-105">Вы для развертывания групп с [чата, групп, каналы, & приложения](deploy-chat-teams-channels-microsoft-teams-landing-page.md) внутри организации.</span><span class="sxs-lookup"><span data-stu-id="56f4e-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="56f4e-106">Может быть развертывания [конференц-связи & собрания](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="56f4e-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="56f4e-107">Теперь вы готовы к добавлять облачных возможности голосовой связи для пользователей.</span><span class="sxs-lookup"><span data-stu-id="56f4e-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="56f4e-108">Облако голосовой предоставляет возможности Exchange закрытый филиала (УАТС) и параметры для подключения к общедоступной переключения телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="56f4e-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="56f4e-109">Эта статья поможет вам решить, нужно ли изменять любые параметры по умолчанию облачных голосовой связи, на основе профилей вашей организации и бизнес-требования, а затем его — описание каждого изменения.</span><span class="sxs-lookup"><span data-stu-id="56f4e-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="56f4e-110">Мы разделение параметры на две группы, начиная с базовый набор [вы, скорее всего, внесите изменения](#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="56f4e-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="56f4e-111">Второй группы включает в себя [Дополнительные параметры](#additional-deployment-decisions) , которые может потребоваться настроить, исходя из потребностей вашей организации.</span><span class="sxs-lookup"><span data-stu-id="56f4e-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="56f4e-112">Рекомендуется всей организации работает через основные решения и, если в вашей организации есть дополнительные требования, просмотрите следующие материалы.</span><span class="sxs-lookup"><span data-stu-id="56f4e-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="56f4e-113">Дополнительные сведения об облаке голосовой связи</span><span class="sxs-lookup"><span data-stu-id="56f4e-113">Learn more about cloud voice</span></span>

<span data-ttu-id="56f4e-114">Следующие статьи содержат дополнительные сведения о развертывании и использовании функции голосовой связи облака в группах.</span><span class="sxs-lookup"><span data-stu-id="56f4e-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="56f4e-115">Телефонная система в Office 365</span><span class="sxs-lookup"><span data-stu-id="56f4e-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="56f4e-116">Телефонной системой с вызова плана</span><span class="sxs-lookup"><span data-stu-id="56f4e-116">Phone System with Calling Plan</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="56f4e-117">Прямой маршрутизации телефонной системы</span><span class="sxs-lookup"><span data-stu-id="56f4e-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="56f4e-118">Развертывание облачной системы голосовой связи</span><span class="sxs-lookup"><span data-stu-id="56f4e-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="56f4e-119">Решения Майкрософт телефонной связи</span><span class="sxs-lookup"><span data-stu-id="56f4e-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="56f4e-120">Просмотрите следующие сеанса для получения дополнительных сведений о телефонной системой: [Знакомство с телефонной системой в группах Майкрософт](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="56f4e-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="56f4e-121">Основные решения, касающиеся развертывания</span><span class="sxs-lookup"><span data-stu-id="56f4e-121">Core deployment decisions</span></span>

<span data-ttu-id="56f4e-122">Это параметры, которые в большинстве организаций необходимо изменить (Если группы по умолчанию не работает для организации).</span><span class="sxs-lookup"><span data-stu-id="56f4e-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="56f4e-123">Телефонной системой (Office 365)</span><span class="sxs-lookup"><span data-stu-id="56f4e-123">Phone System (Office 365)</span></span>

<span data-ttu-id="56f4e-124">Телефонной системой — технология корпорации Майкрософт для включения управления звонками и возможности Exchange закрытый филиала (УАТС) в облаке Office 365.</span><span class="sxs-lookup"><span data-stu-id="56f4e-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="56f4e-125">Телефонной системой можно заменить существующий закрытый Exchange филиала (УАТС) систему на набор функциональных возможностей непосредственно доставленных в период с Office 365 и тесно интегрируются с среда работы организации в облако.</span><span class="sxs-lookup"><span data-stu-id="56f4e-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="56f4e-126">Задайте себе</span><span class="sxs-lookup"><span data-stu-id="56f4e-126">Ask yourself</span></span>|<span data-ttu-id="56f4e-127">Действие</span><span class="sxs-lookup"><span data-stu-id="56f4e-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="56f4e-128">В какие пользователя расположения или офисов будет реализовано телефонной системой?</span><span class="sxs-lookup"><span data-stu-id="56f4e-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="56f4e-129">Дополнительные сведения о телефонной системой приведены в статье [телефонной системой в Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="56f4e-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="56f4e-130">Подключение для общего пользования телефонной сети (общего пользования PSTN)</span><span class="sxs-lookup"><span data-stu-id="56f4e-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="56f4e-131">Для подключения телефонной системой для общедоступных переключения телефонной сети общего пользования (PSTN), чтобы пользователи могут выполнять телефонные звонки по всему миру, возможны варианты на основе принципа необходимого.</span><span class="sxs-lookup"><span data-stu-id="56f4e-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="56f4e-132">Ответьте на следующие:</span><span class="sxs-lookup"><span data-stu-id="56f4e-132">Ask yourself the following:</span></span>


|<span data-ttu-id="56f4e-133">Задайте себе</span><span class="sxs-lookup"><span data-stu-id="56f4e-133">Ask yourself</span></span>|<span data-ttu-id="56f4e-134">Действие</span><span class="sxs-lookup"><span data-stu-id="56f4e-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="56f4e-135">Я хочу использовать вызов планирование Microsoft в качестве Мои поставщика телефонии?</span><span class="sxs-lookup"><span data-stu-id="56f4e-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="56f4e-136">Для получения дополнительных сведений см [Телефонной системы с помощью вызова планов](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="56f4e-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="56f4e-137">Нужно ли использовать собственный поставщика телефонии?</span><span class="sxs-lookup"><span data-stu-id="56f4e-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="56f4e-138">Для получения дополнительных сведений см [Телефонной системой при прямой маршрутизации](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="56f4e-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="56f4e-139">Дополнительные развертывания решения</span><span class="sxs-lookup"><span data-stu-id="56f4e-139">Additional deployment decisions</span></span>

<span data-ttu-id="56f4e-140">Может потребоваться изменить параметры для следующего случая зависимости от потребностей организации и конфигурации:</span><span class="sxs-lookup"><span data-stu-id="56f4e-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="56f4e-141">Голосовая почта</span><span class="sxs-lookup"><span data-stu-id="56f4e-141">Voicemail</span></span>
- <span data-ttu-id="56f4e-142">Идентификатор звонящего абонента</span><span class="sxs-lookup"><span data-stu-id="56f4e-142">Calling identity</span></span>
- <span data-ttu-id="56f4e-143">Номера телефонов корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="56f4e-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="56f4e-144">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="56f4e-144">Dial plans</span></span>
- <span data-ttu-id="56f4e-145">Очередь звонков</span><span class="sxs-lookup"><span data-stu-id="56f4e-145">Call queues</span></span>
- <span data-ttu-id="56f4e-146">Автосекретари</span><span class="sxs-lookup"><span data-stu-id="56f4e-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="56f4e-147">Голосовая почта</span><span class="sxs-lookup"><span data-stu-id="56f4e-147">Voicemail</span></span>

<span data-ttu-id="56f4e-148">Система голосовой почты телефона, на базе служб Azure голосовой почты, поддерживает вклады голосовой почты в почтовые ящики Exchange только и не поддерживает систем электронной почты сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="56f4e-148">Phone System voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="56f4e-149">Голосовая почта Телефонной системы включает функцию расшифровки голосовых сообщений, которая по умолчанию включена для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="56f4e-149">Phone System voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="56f4e-150">Бизнес-требованиям может потребоваться отключить транскрибирования голосовой почты для определенных пользователей или всем пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="56f4e-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="56f4e-151">Задайте себе</span><span class="sxs-lookup"><span data-stu-id="56f4e-151">Ask yourself</span></span>|<span data-ttu-id="56f4e-152">Действие</span><span class="sxs-lookup"><span data-stu-id="56f4e-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="56f4e-153">Требуется ли Включение телефонной системы голосовой почты?</span><span class="sxs-lookup"><span data-stu-id="56f4e-153">Do I want to enable Phone System voicemail?</span></span> | <span data-ttu-id="56f4e-154">Процедуры настройки голосовой почты см [телефонной системы голосовой почты](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="56f4e-154">For voicemail setup procedures, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="56f4e-155">Требуется ли включение транскрибирования голосовой почты для некоторых или всех Мои пользователи?</span><span class="sxs-lookup"><span data-stu-id="56f4e-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="56f4e-156">Чтобы отключить транскрибирования голосовой почты, обратитесь к [настройке политик голосовой почты в вашей организации](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="56f4e-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="56f4e-157">Идентификатор звонящего абонента</span><span class="sxs-lookup"><span data-stu-id="56f4e-157">Calling identity</span></span>

<span data-ttu-id="56f4e-158">По умолчанию все исходящие вызовы использовать назначенный номер в качестве удостоверения вызывающей (Звонящего).</span><span class="sxs-lookup"><span data-stu-id="56f4e-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="56f4e-159">Получатель звонка может быстро идентифицировать звонящего и решить, следует ли принять или отклонить вызов.</span><span class="sxs-lookup"><span data-stu-id="56f4e-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="56f4e-160">Задайте себе</span><span class="sxs-lookup"><span data-stu-id="56f4e-160">Ask yourself</span></span>|<span data-ttu-id="56f4e-161">Действие</span><span class="sxs-lookup"><span data-stu-id="56f4e-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="56f4e-162">Хотите скрытие или отключение Звонящего?</span><span class="sxs-lookup"><span data-stu-id="56f4e-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="56f4e-163">[Идентификатор звонящего для пользователя,](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user)Чтобы изменить или заблокировать идентификатора звонящего, см.</span><span class="sxs-lookup"><span data-stu-id="56f4e-163">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="56f4e-164">Номера телефонов корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="56f4e-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="56f4e-165">Корпорация Майкрософт предлагает два типа доступных телефонных номеров: номера *подписчика* (пользователь), которые можно назначить пользователям в вашей организации и доступные как международную и службы бесплатных номеров, которые имеют возможность выполнения одновременных звонков выше номера *службы* емкостью, чем номера и могут быть назначены службы, такие как аудио конференц-связи, автосекретари или позвонить очереди.</span><span class="sxs-lookup"><span data-stu-id="56f4e-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="56f4e-166">Задайте себе</span><span class="sxs-lookup"><span data-stu-id="56f4e-166">Ask yourself</span></span>|<span data-ttu-id="56f4e-167">Действие</span><span class="sxs-lookup"><span data-stu-id="56f4e-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="56f4e-168">Местоположения пользователя, в которых требуется нового номера телефонов корпорацией Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="56f4e-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="56f4e-169">Сведения о получении телефонных номеров содержатся в разделе [Управление номера телефонов для вашей организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) и [Получение номера телефонов для пользователей](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="56f4e-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span></span> 
| <span data-ttu-id="56f4e-170">Какой тип телефонный номер (подписчика или службы) требуется?</span><span class="sxs-lookup"><span data-stu-id="56f4e-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="56f4e-171">Чтобы выбрать тип номера телефона, нужно просмотреть [различные виды телефонных номеров, используемый для вызова планов](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="56f4e-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="56f4e-172">Как мне порт существующего номера телефонов в Office 365?</span><span class="sxs-lookup"><span data-stu-id="56f4e-172">How do I port existing phone numbers to Office 365?</span></span>|<span data-ttu-id="56f4e-173">Дополнительные сведения можно [Переключить телефонных номеров в Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="56f4e-173">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="56f4e-174">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="56f4e-174">Dial plans</span></span>

<span data-ttu-id="56f4e-175">К абонентской группе в компоненте телефонной системой Office 365 — набор правил нормализации, переводить набора телефонных номеров в альтернативный формат (обычно формат E.164) для маршрутизации вызовов и проверка подлинности вызовов.</span><span class="sxs-lookup"><span data-stu-id="56f4e-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="56f4e-176">Дополнительные сведения об абонентских групп можно [Каковы абонентских групп?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="56f4e-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="56f4e-177">Задайте себе</span><span class="sxs-lookup"><span data-stu-id="56f4e-177">Ask yourself</span></span>|<span data-ttu-id="56f4e-178">Действие</span><span class="sxs-lookup"><span data-stu-id="56f4e-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="56f4e-179">Требуется ли Моя организация настраиваемого абонентской группы?</span><span class="sxs-lookup"><span data-stu-id="56f4e-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="56f4e-180">Для определения необходимости настраиваемых абонентской группы, см [для клиента абонентские группы](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="56f4e-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="56f4e-181">Пользователей, которым требуется настроенный абонентской группы, а какие клиента абонентская группа должна быть назначена каждому пользователю?</span><span class="sxs-lookup"><span data-stu-id="56f4e-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="56f4e-182">Чтобы добавить пользователей к настраиваемой абонентской группе в PowerShell, обратитесь к разделу [Создание и управление ими абонентских групп](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="56f4e-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="56f4e-183">Очередь звонков</span><span class="sxs-lookup"><span data-stu-id="56f4e-183">Call queues</span></span>

<span data-ttu-id="56f4e-184">Телефонный звонок системы очередей включают приветствие, используемые при получении звонка на номер телефона для вашей организации, возможность автоматически переводить звонки в режим удержания и возможность поиска для следующего агента доступные вызова для обработки вызова при людей, вызов прослушивают музыку при удержании.</span><span class="sxs-lookup"><span data-stu-id="56f4e-184">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="56f4e-185">Вы можете создать для своей организации одну или несколько очередей вызовов.</span><span class="sxs-lookup"><span data-stu-id="56f4e-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="56f4e-186">Задайте себе</span><span class="sxs-lookup"><span data-stu-id="56f4e-186">Ask yourself</span></span>|<span data-ttu-id="56f4e-187">Действие</span><span class="sxs-lookup"><span data-stu-id="56f4e-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="56f4e-188">Организации требуется позвонить очереди?</span><span class="sxs-lookup"><span data-stu-id="56f4e-188">Does my organization need call queues?</span></span> | <span data-ttu-id="56f4e-189">Для получения дополнительных сведений см. [Создание очереди вызовов с телефонной системой](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) и [Настройка телефонной системой](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="56f4e-189">For more information, see [Create a Phone System call queue](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="56f4e-190">Автосекретари</span><span class="sxs-lookup"><span data-stu-id="56f4e-190">Auto attendants</span></span>

<span data-ttu-id="56f4e-191">Телефонной системой автосекретари можно использовать для создания системы меню для вашей организации, которая позволяет внешнего и внутреннего вызывающих объектов переход по системе меню Поиск и поместить или переводить звонки компании пользователей или отделов организации.</span><span class="sxs-lookup"><span data-stu-id="56f4e-191">Phone System auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="56f4e-192">Задайте себе</span><span class="sxs-lookup"><span data-stu-id="56f4e-192">Ask yourself</span></span>|<span data-ttu-id="56f4e-193">Действие</span><span class="sxs-lookup"><span data-stu-id="56f4e-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="56f4e-194">Требуется ли Моя организация автосекретари?</span><span class="sxs-lookup"><span data-stu-id="56f4e-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="56f4e-195">Для получения дополнительных сведений см [что такое автосекретари телефонной системой](what-are-phone-system-auto-attendants.md) и [настроить автосекретарь телефонной системой](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="56f4e-195">For more information, see [What are Phone System auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Phone System auto attendant](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> |

### <a name="devices"></a><span data-ttu-id="56f4e-196">Устройства</span><span class="sxs-lookup"><span data-stu-id="56f4e-196">Devices</span></span>

<span data-ttu-id="56f4e-197">Дополнительные сведения о поддерживаемых устройств см.:</span><span class="sxs-lookup"><span data-stu-id="56f4e-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="56f4e-198">Управление устройствами в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="56f4e-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="56f4e-199">IP-телефонов</span><span class="sxs-lookup"><span data-stu-id="56f4e-199">IP Phones</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="56f4e-200">USB-устройства аудио- и видеоконференций</span><span class="sxs-lookup"><span data-stu-id="56f4e-200">USB audio and video devices</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="56f4e-201">Интеллектуальный коммуникаций для устройств</span><span class="sxs-lookup"><span data-stu-id="56f4e-201">Intelligent communications for devices</span></span>](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


