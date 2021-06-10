---
title: Сначала разо Microsoft Teams.
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: Воспользуйтесь этим руководством, чтобы Microsoft Teams как первую Microsoft 365 или Office 365 рабочей нагрузкой.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119358"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="6f665-103">Сначала разо Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6f665-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="6f665-104">Microsoft Teams помогает вашим сотрудникам оставаться на связи и сотрудничать друг с другом, особенно в период, когда удаленная работа — это реальность сотрудников по всему миру.</span><span class="sxs-lookup"><span data-stu-id="6f665-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="6f665-105">Возможность общаться в чате, видеособраний и совместной работы над документами Office в Teams помогает компаниям оставаться продуктивными.</span><span class="sxs-lookup"><span data-stu-id="6f665-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="6f665-106">Независимо от того, являетесь ли вы небольшим бизнесом, некоммерческой или крупной организацией, вы можете начать работу с Teams в качестве первой рабочей нагрузки в наборе Microsoft 365 или Office 365 перед развертыванием других Приложение Office или служб.</span><span class="sxs-lookup"><span data-stu-id="6f665-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="6f665-107">В этой статье подробно рассматриваются вопросы, которые необходимо учитывать при Teams первую очередь.</span><span class="sxs-lookup"><span data-stu-id="6f665-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f665-108">Хотя Teams может быть первой развернутой в организации рабочей нагрузкой в облаке, Teams должно быть частью общей стратегии развертывания в облаке.</span><span class="sxs-lookup"><span data-stu-id="6f665-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="6f665-109">Если вы уже свернуты другие службы Microsoft 365 или Office 365 и Teams ваша следующую нагрузку (а не первую), начните с ссылки Как Teams [.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6f665-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="6f665-110">С чего начать</span><span class="sxs-lookup"><span data-stu-id="6f665-110">Start here</span></span>

<span data-ttu-id="6f665-111">Чтобы начать работу с Teams развертывания, необходимо выполнить как минимум некоторые предварительные требования.</span><span class="sxs-lookup"><span data-stu-id="6f665-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="6f665-112">В следующем списке будет покажите, что необходимо сделать для вашей организации, чтобы включить Teams включить:</span><span class="sxs-lookup"><span data-stu-id="6f665-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="6f665-113">Организация Microsoft 365 или Office 365 с вашим доменным именем</span><span class="sxs-lookup"><span data-stu-id="6f665-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="6f665-114">Azure Active Directory подключения (AAD Connect) или аналогичного решения для синхронизации облачных удостоверений со всеми требуемой атрибутами, синхронизированными с клиентом</span><span class="sxs-lookup"><span data-stu-id="6f665-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="6f665-115">Чтобы понять атрибуты, синхронизированные с синхронизацией AAD, прочитайте статью [Синхронизация Azure AD Подключение:](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) атрибуты, синхронизированные с Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6f665-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="6f665-116">Соответствующие пользовательские лицензии, которые назначены Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="6f665-117">Чтобы ознакомиться Teams лицензирования, ознакомьтесь с Microsoft Teams [службы.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="6f665-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="6f665-118">Сеть организации подготовлена к Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="6f665-119">Чтобы понять, как подготовить сеть, ознакомьтесь со статьей Подготовка сети [организации к Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="6f665-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="6f665-120">Разрешить сетевой доступ Exchange, Sharepoint и OneDrive для бизнеса в Microsoft 365 или Office 365: [URL-Office 365 и диапазоны IP-адресов](/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="6f665-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="6f665-121">Клиенты, созданные после 1 сентября 2019 г., будут Teams только в режиме Teams.</span><span class="sxs-lookup"><span data-stu-id="6f665-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="6f665-122">Если после Skype для бизнеса Server 1 сентября 2019 г. ваш клиент был размещен, обратитесь в службу поддержки, чтобы включить возможности Teams.</span><span class="sxs-lookup"><span data-stu-id="6f665-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="6f665-123">Прежде чем назначать пользователю какие-либо лицензии <span class="underline"></span> на Teams, убедитесь, что для вашей политики обновления для всей организации установлен режим "Остров".</span><span class="sxs-lookup"><span data-stu-id="6f665-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="6f665-124">Начальные точки миграции</span><span class="sxs-lookup"><span data-stu-id="6f665-124">Migration Starting points</span></span>

<span data-ttu-id="6f665-125">Ваше путешествие к Microsoft 365 или Office 365 и функциям, доступным в Teams в зависимости от исходной точки и наличия локального Skype для бизнеса или сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="6f665-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="6f665-126">В следующих разделах, помимо перечисленных выше предварительных условий, подробно огосят основные возможности и параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6f665-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="6f665-127">Мы разбиты начальные сценарии на следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="6f665-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="6f665-128">**Конфигурация Teams** клиента: для управления поведением получателя используются режимы клиента и пользователя.</span><span class="sxs-lookup"><span data-stu-id="6f665-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="6f665-129">Эти параметры можно на уровне клиента или пользователя в организации.</span><span class="sxs-lookup"><span data-stu-id="6f665-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="6f665-130">Подробнее об этом можно [узнать](coexistence-chat-calls-presence.md)в этой Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6f665-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="6f665-131">**Чат и внешняя связь** в Teams . Службы чата ссылаются на одноранговые или групповые беседы чата внутри организации, организации или за ее внешними границами.</span><span class="sxs-lookup"><span data-stu-id="6f665-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="6f665-132">Внешняя связь также называется федерацией в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6f665-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="6f665-133">Создание и просмотр собраний в **Teams.** Пользователь всегда может создавать собрания по сети с помощью надстройки Outlook Teams и телефонного номера ДНР, доступной во всех сценариях после получения лицензии.</span><span class="sxs-lookup"><span data-stu-id="6f665-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="6f665-134">Teams и Skype для бизнеса данные календаря в почтовом ящике Exchange пользователя.</span><span class="sxs-lookup"><span data-stu-id="6f665-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="6f665-135">Чтобы клиент Teams мог взаимодействовать с почтовым ящиком пользователя, Exchange сервер должен быть Exchange Server 2016 CU3 или более высокой.</span><span class="sxs-lookup"><span data-stu-id="6f665-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="6f665-136">Если Exchange доступ к почтовому ящику значок Календарь в Teams не будет отображаться и пользователь не сможет просматривать, создавать и изменять собрания в клиенте Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="6f665-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="6f665-137">**Функции звонков VoIP и STN** в Teams: звонки могут быть голосовой связью по IP-адресу (VoIP) или по телефонной сети общего звонков (STN).</span><span class="sxs-lookup"><span data-stu-id="6f665-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="6f665-138">Подключение voIP происходит в основном Teams клиентах, в то время как подключение по STN происходит при наборе пользователем внешнего номера телефона.</span><span class="sxs-lookup"><span data-stu-id="6f665-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="6f665-139">Teams поддерживают два типа подключения к ДНР.</span><span class="sxs-lookup"><span data-stu-id="6f665-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="6f665-140">План звонков Майкрософт, когда корпорация Майкрософт предоставляет инфраструктуру телефонии, включая телефонный номер пользователя, или конфигурацию Прямой маршрутации, где клиент предоставляет телефонное подключение через SBC-контроллер Teams пользователя.</span><span class="sxs-lookup"><span data-stu-id="6f665-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="6f665-141">Чтобы узнать больше, ознакомьтесь со статьей [Какой](calling-plan-landing-page.md) план звонков вам больше всего подаваем? и [телефонная система прямой маршрутизов.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="6f665-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="6f665-142">**Teams каналов** и совместной работы в Teams : в Teams группах — это группы людей, совместная работа, проекты или общие интересы.</span><span class="sxs-lookup"><span data-stu-id="6f665-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="6f665-143">Teams каналов.</span><span class="sxs-lookup"><span data-stu-id="6f665-143">Teams are made up of channels.</span></span> <span data-ttu-id="6f665-144">Каждый канал строится на тему, например "События группы", название отдела или просто для развлечения.</span><span class="sxs-lookup"><span data-stu-id="6f665-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="6f665-145">Каналы — это место для проведения собраний, бесед и совместной работы над файлами.</span><span class="sxs-lookup"><span data-stu-id="6f665-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="6f665-146">Во время совместной работы</span><span class="sxs-lookup"><span data-stu-id="6f665-146">During collaboration</span></span>

<span data-ttu-id="6f665-147">**OneDrive для бизнеса (P2P-файл)** в Teams: за пределами Teams и каналов пользователи Teams могут делиться файлами с помощью OneDrive для бизнеса или других программ общего доступа к P2P, таких как Файлы Citrix, DropBox, Box и Google Диск.</span><span class="sxs-lookup"><span data-stu-id="6f665-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="6f665-148">Для OneDrive для бизнеса пользователю должна быть назначена SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6f665-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="6f665-149">**Платформа приложений:** приложения предоставляют вам новые инструменты для вашей организации, чтобы использовать Teams.</span><span class="sxs-lookup"><span data-stu-id="6f665-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="6f665-150">Эти приложения объединяют в себе функции вкладок, расширений для сообщений, соединитеров и ботов, предоставляемых корпорацией Майкрософт, сторонними разработчиками или сторонними разработчиками.</span><span class="sxs-lookup"><span data-stu-id="6f665-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="6f665-151">Функции безопасности и соответствия **требованиям.** Teams содержит широкий набор сведений, которые помогут вам в области соответствия требованиям, включая политики хранения, защиту от потери данных (DLP), eDiscovery и удержание по юридическим вопросам для каналов, чатов и файлов, поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="6f665-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="6f665-152">Подробнее об этом можно узнать в [этой](security-compliance-overview.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6f665-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="6f665-153">Для advance eDiscovery требуется лицензирование E5.</span><span class="sxs-lookup"><span data-stu-id="6f665-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="6f665-154">[Сравнение параметров лицензирования](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span><span class="sxs-lookup"><span data-stu-id="6f665-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="6f665-155">Ознакомьтесь [Exchange взаимодействия Microsoft Teams,](exchange-teams-interact.md) чтобы узнать, какие функции соответствия требованиям доступны в вашем сценарии.</span><span class="sxs-lookup"><span data-stu-id="6f665-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="6f665-156">Организации **<span class="underline">без Skype для бизнеса</span>** или Lync Server</span><span class="sxs-lookup"><span data-stu-id="6f665-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="6f665-157">Предполагается, что ваша организация в настоящее время не использует Skype для бизнеса или Lync Server и Teams будет первым приложением в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f665-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="6f665-158">В таблице ниже данная таблица подробно о настройке и возможностях конечных пользователей для Teams основных служб.</span><span class="sxs-lookup"><span data-stu-id="6f665-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="6f665-159">Item</span><span class="sxs-lookup"><span data-stu-id="6f665-159">Item</span></span></th>
<th><span data-ttu-id="6f665-160">Notes</span><span class="sxs-lookup"><span data-stu-id="6f665-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6f665-161">Конфигурация Teams клиента</span><span class="sxs-lookup"><span data-stu-id="6f665-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="6f665-162">Teams Только режим, все функции чата и звонков находятся в Teams только.</span><span class="sxs-lookup"><span data-stu-id="6f665-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f665-163">Чат и внешняя связь в Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="6f665-164">Внутренняя (внутренняя Microsoft 365 или Office 365 организации) и взаимодействие с внешним чатом можно из Teams.</span><span class="sxs-lookup"><span data-stu-id="6f665-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="6f665-165"><em>Примечание. Записи DNS должны быть настроены для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="6f665-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="6f665-166">Skype для бизнеса Записи DNS необходимы, даже если у вас нет локальной Skype для бизнеса или в Microsoft 365 или Office 365, чтобы разрешить федерацию с Lync и Skype для бизнеса средами:</span><span class="sxs-lookup"><span data-stu-id="6f665-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="6f665-167">
<a href="/office365/enterprise/external-domain-name-system-records">Внешние записи системы доменных имен</a></em></span><span class="sxs-lookup"><span data-stu-id="6f665-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6f665-168">Создание и просмотр собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="6f665-169">Возможность создавать внутренние и внешние собрания с помощью Outlook надстройки.</span><span class="sxs-lookup"><span data-stu-id="6f665-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="6f665-170">Для лицензий на аудиоконференцию доступны функции телефонного и телефонного связи через ДНР.</span><span class="sxs-lookup"><span data-stu-id="6f665-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="6f665-171">Teams доступа к календарю требуется Exchange 2016 с установленным гибридным развертыванием Exchange 2016 CU3: создание гибридного развертывания с помощью мастера гибридной <a href="/exchange/hybrid-deployment/deploy-hybrid">конфигурации.</a> </span><span class="sxs-lookup"><span data-stu-id="6f665-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="6f665-172">В дополнение к Exchange гибридной конфигурации, Exchange проверку подлинности OAuth: Настройка проверки подлинности OAuth Exchange и <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> Exchange Online организациях".</span><span class="sxs-lookup"><span data-stu-id="6f665-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f665-173">Функции звонков</span><span class="sxs-lookup"><span data-stu-id="6f665-173">Calling Features</span></span><br />
<span data-ttu-id="6f665-174">VoIP/STN в Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="6f665-175">VoIP для клиента доступен как для внутренних, так и для внешних клиентов.</span><span class="sxs-lookup"><span data-stu-id="6f665-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="6f665-176">Службы ЗВОНКОВ можно настроить с помощью Телефон (Майкрософт), а также добавить план звонков Майкрософт или прямую маршрутику.</span><span class="sxs-lookup"><span data-stu-id="6f665-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6f665-177">Teams каналы и каналы в Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="6f665-178">Для полноценного интерфейса, включая функции соответствия SharePoint, пользователю должна быть назначена лицензия на SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6f665-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="6f665-179">Перенос существующих SharePoint не требуется.</span><span class="sxs-lookup"><span data-stu-id="6f665-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f665-180">OneDrive для бизнеса (общий доступ к P2P-файлам)</span><span class="sxs-lookup"><span data-stu-id="6f665-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="6f665-181">OneDrive для бизнеса требуется, чтобы пользователю была назначена SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6f665-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="6f665-182">Без этой лицензии одноранговой доступ к файлам будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="6f665-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6f665-183">Платформа приложений</span><span class="sxs-lookup"><span data-stu-id="6f665-183">Application platform</span></span></td>
<td><span data-ttu-id="6f665-184">Пользователи смогут использовать приложения, назначенные им в соответствии с политиками компании.</span><span class="sxs-lookup"><span data-stu-id="6f665-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="6f665-185">Подробнее об этом: <a href="/microsoftteams/admin-settings">Параметры администратора для приложений в Teams</a></span><span class="sxs-lookup"><span data-stu-id="6f665-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f665-186">Функции безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="6f665-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="6f665-187">Доступны политики хранения.</span><span class="sxs-lookup"><span data-stu-id="6f665-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="6f665-188">Поддержка eDiscovery и удержания по юридическим каналам для соблюдения требований к сообщениям каналов.</span><span class="sxs-lookup"><span data-stu-id="6f665-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="6f665-189">Доступны политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="6f665-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="6f665-190">Полный набор функций, доступный в Exchange Online; Exchange поддерживает большинство этих функций.</span><span class="sxs-lookup"><span data-stu-id="6f665-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="6f665-191">Полный список см. в <a href="/MicrosoftTeams/exchange-teams-interact">Exchange взаимодействия Teams взаимодействия.</a></span><span class="sxs-lookup"><span data-stu-id="6f665-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="6f665-192">Шаги по ветвению для организаций без Skype для бизнеса или Lync Server</span><span class="sxs-lookup"><span data-stu-id="6f665-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="6f665-193">Требования, подробные в разделе "Начать здесь" выше</span><span class="sxs-lookup"><span data-stu-id="6f665-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="6f665-194">Переключение клиента в режим Teams только для существующих клиентов): настройка параметров сосуществования [и обновления](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6f665-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="6f665-195">Настройте клиент в соответствии с политиками организации: Управление настройками Microsoft Teams [организации.](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="6f665-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="6f665-196">Развертывание клиента Teams для пользователей: ["Получить клиенты для Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="6f665-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="6f665-197">Управлять программой принятия</span><span class="sxs-lookup"><span data-stu-id="6f665-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="6f665-198">Внедрение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="6f665-199">Краткий контрольный список по внедрению Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="6f665-200">Начните планирование переноса других рабочих нагрузок Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="6f665-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="6f665-201">Организации **<span class="underline">с Skype для бизнеса</span>** или сервером Lync</span><span class="sxs-lookup"><span data-stu-id="6f665-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="6f665-202">При этом предполагается, что ваша организация использует локально Skype для бизнеса 2019 или 2015 или Lync 2013+.</span><span class="sxs-lookup"><span data-stu-id="6f665-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="6f665-203">У нас уже есть обширные рекомендации для организаций, которые переходят с локального сервера на Teams и следует следовать этим сценариям.</span><span class="sxs-lookup"><span data-stu-id="6f665-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="6f665-204">Это руководство будет действовать только в том Teams, которое вы используете в первой Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f665-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="6f665-205">В таблице ниже данная таблица подробно о настройке и возможностях конечных пользователей для Teams основных служб.</span><span class="sxs-lookup"><span data-stu-id="6f665-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="6f665-206">Item</span><span class="sxs-lookup"><span data-stu-id="6f665-206">Item</span></span></th>
<th><span data-ttu-id="6f665-207">Notes</span><span class="sxs-lookup"><span data-stu-id="6f665-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6f665-208">Конфигурация Teams клиента</span><span class="sxs-lookup"><span data-stu-id="6f665-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="6f665-209">Режим "Острова".</span><span class="sxs-lookup"><span data-stu-id="6f665-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f665-210">Чат и внешняя связь в Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="6f665-211">Внутренняя в пределах вашего клиента внешняя связь (федерация) осуществляется через Skype для бизнеса или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f665-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6f665-212">Создание и просмотр собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="6f665-213">Возможность создавать внутренние и внешние собрания с помощью Outlook надстройки.</span><span class="sxs-lookup"><span data-stu-id="6f665-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="6f665-214">Для лицензий на аудиоконференцию доступны функции телефонного и телефонного связи через ДНР.</span><span class="sxs-lookup"><span data-stu-id="6f665-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="6f665-215">Teams доступа к календарю требуется Exchange 2016 CU3+ на локальном развертывании с установленным гибридным Exchange:</span><span class="sxs-lookup"><span data-stu-id="6f665-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="6f665-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Создайте гибридное развертывание с помощью мастера гибридной конфигурации.</a></span><span class="sxs-lookup"><span data-stu-id="6f665-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="6f665-217">Администратор может управлять надстройкой Skype для бизнеса Outlook с помощью атрибута PreferredMeetingProviderForIslandsMode политики собраний Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy.</a></span><span class="sxs-lookup"><span data-stu-id="6f665-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f665-218">Функции звонков</span><span class="sxs-lookup"><span data-stu-id="6f665-218">Calling Features</span></span><br />
<span data-ttu-id="6f665-219">VoIP/STN в Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="6f665-220">VoIP для внутреннего клиента доступен.</span><span class="sxs-lookup"><span data-stu-id="6f665-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="6f665-221">Службы ЗВОНКОВ и ЗВОНКОВ недоступны до тех пор, пока пользователь не будет перемещен в Teams только интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6f665-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6f665-222">Teams каналы и каналы в Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="6f665-223">Для полноценного интерфейса, включая функции соответствия SharePoint, пользователю должна быть назначена лицензия на SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6f665-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="6f665-224">Перенос существующих SharePoint не требуется.</span><span class="sxs-lookup"><span data-stu-id="6f665-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f665-225">OneDrive для бизнеса (общий доступ к P2P-файлам)</span><span class="sxs-lookup"><span data-stu-id="6f665-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="6f665-226">OneDrive для бизнеса требуется, чтобы пользователю была назначена SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6f665-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="6f665-227">Без этой лицензии одноранговой общий доступ к файлам будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="6f665-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6f665-228">Платформа приложений</span><span class="sxs-lookup"><span data-stu-id="6f665-228">Application platform</span></span></td>
<td><span data-ttu-id="6f665-229">Пользователи смогут использовать приложения, назначенные им в соответствии с политиками компании.</span><span class="sxs-lookup"><span data-stu-id="6f665-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="6f665-230">Подробнее об этом: <a href="/microsoftteams/admin-settings">Параметры администратора для приложений в Teams</a></span><span class="sxs-lookup"><span data-stu-id="6f665-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f665-231">Функции безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="6f665-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="6f665-232">Доступны политики хранения.</span><span class="sxs-lookup"><span data-stu-id="6f665-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="6f665-233">Поддержка eDiscovery и удержания по юридическим каналам для соблюдения требований к сообщениям каналов.</span><span class="sxs-lookup"><span data-stu-id="6f665-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="6f665-234">Доступны политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="6f665-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="6f665-235">Полный набор функций, доступный в Exchange Online; Exchange поддерживает большинство этих функций.</span><span class="sxs-lookup"><span data-stu-id="6f665-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="6f665-236">Полный список см. в <a href="/MicrosoftTeams/exchange-teams-interact">Exchange взаимодействия Teams взаимодействия.</a></span><span class="sxs-lookup"><span data-stu-id="6f665-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="6f665-237">Шаги по вреализации для организаций с Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6f665-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="6f665-238">Соответствует предварительным требованиям, подробно описанным в разделе "Начать здесь" выше.</span><span class="sxs-lookup"><span data-stu-id="6f665-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="6f665-239">Переключение клиента в режим "Острова" (для клиентов, которые были подготовка после 01.09.2019, обратитесь в службу поддержки, чтобы внести это изменение)</span><span class="sxs-lookup"><span data-stu-id="6f665-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="6f665-240">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="6f665-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="6f665-241">Настройка клиента в соответствии с политиками организации</span><span class="sxs-lookup"><span data-stu-id="6f665-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="6f665-242">Управление параметрами Microsoft Teams в организации</span><span class="sxs-lookup"><span data-stu-id="6f665-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="6f665-243">Развертывание клиента Teams клиента</span><span class="sxs-lookup"><span data-stu-id="6f665-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="6f665-244">Получите клиенты для Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="6f665-245">Управлять программой принятия</span><span class="sxs-lookup"><span data-stu-id="6f665-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="6f665-246">Внедрение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="6f665-247">Краткий контрольный список по внедрению Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="6f665-248">Начните планирование переноса других рабочих нагрузок Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="6f665-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="6f665-249">Создание гибридной Skype для бизнеса и следуйте рекомендуемым путям обновления для серверов Skype для бизнеса и Lync</span><span class="sxs-lookup"><span data-stu-id="6f665-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="6f665-250">Обновив Skype для бизнеса локально до Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="6f665-251">Закрываемая выписка</span><span class="sxs-lookup"><span data-stu-id="6f665-251">Closing statement</span></span>

<span data-ttu-id="6f665-252">Microsoft Teams организации может помочь собрать всех сотрудников, информационных работников и сотрудников, работающих с данными, на одной платформе.</span><span class="sxs-lookup"><span data-stu-id="6f665-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="6f665-253">Вы можете [начать работу уже](https://products.office.com/microsoft-teams/group-chat-software) сегодня.</span><span class="sxs-lookup"><span data-stu-id="6f665-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="6f665-254">Здесь вы можете быть на связи со всеми нашими последними объявлениями и ежемесячными обновлениями [продуктов.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)</span><span class="sxs-lookup"><span data-stu-id="6f665-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="6f665-255">Кроме того, поскольку компании по всему миру управляют текущей ситуацией COVID-19, мы создали ряд материалов, которые помогут вам использовать Teams для максимального влияния на вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="6f665-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="6f665-256">Наши [обязательства перед клиентами в COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="6f665-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="6f665-257">Две недели: что мы узнали о удаленной работе</span><span class="sxs-lookup"><span data-stu-id="6f665-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="6f665-258">Проведения собраний и мероприятий по сети</span><span class="sxs-lookup"><span data-stu-id="6f665-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="6f665-259">Помощь малым и средним предприятиями с удаленной работой в Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="6f665-260">Цифровое преобразование трансляций: наблюдения г-жи Безовой</span><span class="sxs-lookup"><span data-stu-id="6f665-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="6f665-261">9 основных способов, с помощью которых ИТ-специалисты Майкрософт обеспечивает удаленную работу для своих сотрудников</span><span class="sxs-lookup"><span data-stu-id="6f665-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="6f665-262">Работая удаленно, оставайтесь в безопасности — советы для CISOs</span><span class="sxs-lookup"><span data-stu-id="6f665-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="6f665-263">Помощь преподавателям и учащимся в переходе на дистанционное обучение</span><span class="sxs-lookup"><span data-stu-id="6f665-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="6f665-264">Работая удаленно с помощью Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="6f665-265">Справка по службам поддержки</span><span class="sxs-lookup"><span data-stu-id="6f665-265">Support Services reference</span></span>

<span data-ttu-id="6f665-266">Teams для предоставления пользователям полностью интегрированной Exchange Online, SharePoint Online, OneDrive для бизнеса и Microsoft 365 Office 365 Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="6f665-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="6f665-267">Как было отмечено выше, Teams будут работать без полного развертывания этих служб с ограниченными возможностями.</span><span class="sxs-lookup"><span data-stu-id="6f665-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="6f665-268">Дополнительные информацию о Teams и его предварительных требованиях можно найти здесь: Добро пожаловать [в Teams.](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6f665-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="6f665-269">Для конкретных служб, перечисленных выше, выполните указанные ниже ссылки.</span><span class="sxs-lookup"><span data-stu-id="6f665-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="6f665-270">Exchange Online используется для функций календаря и хранения одноранговых сообщений в Teams.</span><span class="sxs-lookup"><span data-stu-id="6f665-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="6f665-271">Подробнее об этом можно узнать в [Exchange взаимодействия Teams взаимодействия.](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="6f665-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f665-272">Для Teams взаимодействия с локальной Exchange необходимо настроить новый протокол проверки подлинности Exchange OAuth, как описано в Exchange и [Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)организации.</span><span class="sxs-lookup"><span data-stu-id="6f665-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="6f665-273">SharePoint используется для общего доступа к файлам в каналах, а /OneDrive для бизнеса используется для общего доступа к файлам в 1:1 или групповом чате.</span><span class="sxs-lookup"><span data-stu-id="6f665-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="6f665-274">Подробнее об этом можно узнать в [SharePoint Взаимодействия OneDrive для бизнеса в Интернете и Microsoft Teams.](sharepoint-onedrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="6f665-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="6f665-275">[Microsoft 365 групп](office-365-groups.md) используются для создания и управления командами и каналами.</span><span class="sxs-lookup"><span data-stu-id="6f665-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="6f665-276">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6f665-276">Related topics</span></span>

[<span data-ttu-id="6f665-277">Плакаты ИТ-архитектуры и решений для телефонии Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="6f665-278">Планирование гибридного подключения между приложением Skype для бизнеса Server и Office 365</span><span class="sxs-lookup"><span data-stu-id="6f665-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="6f665-279">Поддержка удаленных сотрудников с помощью Teams</span><span class="sxs-lookup"><span data-stu-id="6f665-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="6f665-280">Удаленная работа с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f665-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)