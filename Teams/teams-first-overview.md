---
title: Сначала разокатить Microsoft Teams
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
description: Используйте это руководство, чтобы использовать Microsoft Teams в качестве первой рабочей нагрузки Microsoft 365 или Office 365.
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
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="863b6-103">Сначала разокатить Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="863b6-104">Microsoft Teams помогает вашим сотрудникам оставаться на связи и взаимодействовать друг с другом, особенно во время текущего время розыгрыша, когда удаленная работа — это реальность сотрудников по всему миру.</span><span class="sxs-lookup"><span data-stu-id="863b6-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="863b6-105">Возможность общаться в чате, видеособраний и совместной работы над документами Office в Teams помогает компаниям эффективно работать.</span><span class="sxs-lookup"><span data-stu-id="863b6-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="863b6-106">Независимо от того, работаете ли вы в небольшой организации, некоммерческой или крупной организации, вы можете начать работу с Teams в качестве первой рабочей нагрузки в Microsoft 365 или Office 365 перед развертыванием любого другого приложения или службы Office.</span><span class="sxs-lookup"><span data-stu-id="863b6-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="863b6-107">В этой статье подробно рассматривается подход "Teams First".</span><span class="sxs-lookup"><span data-stu-id="863b6-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="863b6-108">Несмотря на то, что Teams может быть первой облачной рабочей нагрузкой в вашей организации, развертывание Teams должно быть частью общей стратегии развертывания облака.</span><span class="sxs-lookup"><span data-stu-id="863b6-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="863b6-109">Если вы уже окатили другие службы Microsoft 365 или Office 365, а Teams — ваша следующая рабочая нагрузка, начните с того, как запустить [Teams.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="863b6-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="863b6-110">С чего начать</span><span class="sxs-lookup"><span data-stu-id="863b6-110">Start here</span></span>

<span data-ttu-id="863b6-111">Чтобы начать развертывание Teams First, вам потребуется выполнить как минимум некоторые предварительные требования.</span><span class="sxs-lookup"><span data-stu-id="863b6-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="863b6-112">В следующем списке покажите, какие возможности необходимо иметь для вашей организации, чтобы включить Teams:</span><span class="sxs-lookup"><span data-stu-id="863b6-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="863b6-113">Организация Microsoft 365 или Office 365, настроенная с вашим доменным именем</span><span class="sxs-lookup"><span data-stu-id="863b6-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="863b6-114">Подключение к Azure Active Directory (AAD Connect) или аналогичное решение для синхронизации облачных удостоверений. Все необходимые атрибуты синхронизируются с клиентом</span><span class="sxs-lookup"><span data-stu-id="863b6-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="863b6-115">Чтобы понять атрибуты, синхронизированные с синхронизацией AAD, прочитайте статью ["Синхронизация Azure AD Connect:](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) атрибуты, синхронизированные с Azure Active Directory"</span><span class="sxs-lookup"><span data-stu-id="863b6-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="863b6-116">Соответствующие пользовательские лицензии, которые назначены для Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="863b6-117">Чтобы ознакомиться с лицензированием Teams, ознакомьтесь с [описанием службы Microsoft Teams.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="863b6-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="863b6-118">Сеть организации подготовлена для Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="863b6-119">Чтобы понять, как подготовить сеть, прочел статью "Подготовка [сети организации к началу работы с Teams".](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="863b6-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="863b6-120">Разрешить сетевой доступ к Exchange, Sharepoint и OneDrive для бизнеса в Microsoft 365 или Office 365: [URL-адреса и диапазоны IP-адресов Office 365.](/office365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="863b6-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="863b6-121">Клиенты, созданные после 1 сентября 2019 г., будут созданы в режиме "Только Teams".</span><span class="sxs-lookup"><span data-stu-id="863b6-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="863b6-122">Если у вас развернут Skype для бизнеса Server и ваш клиент был размещен после 1 сентября 2019 г., обратитесь в службу поддержки, чтобы включить возможности сосуществования для Teams.</span><span class="sxs-lookup"><span data-stu-id="863b6-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="863b6-123">Прежде чем назначать лицензии Teams пользователю, убедитесь, что в вашей "политике обновления для всей <span class="underline">организации"</span> установлен режим "Остров".</span><span class="sxs-lookup"><span data-stu-id="863b6-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="863b6-124">Начальные точки миграции</span><span class="sxs-lookup"><span data-stu-id="863b6-124">Migration Starting points</span></span>

<span data-ttu-id="863b6-125">Ваше путешествие к Microsoft 365 или Office 365 и функции, доступные в Teams, зависят от того, с какой точки вы начинаете использовать и когда существуют локальное приложение Skype для бизнеса или сервер Lync.</span><span class="sxs-lookup"><span data-stu-id="863b6-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="863b6-126">В следующих разделах в дополнение к перечисленным выше предварительным требованиям будут подробно о возможностях и параметрах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="863b6-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="863b6-127">Мы разбиты начальные сценарии на следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="863b6-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="863b6-128">**Конфигурация Teams клиента:** для управления поведением получателя используются режимы клиента и пользователя.</span><span class="sxs-lookup"><span data-stu-id="863b6-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="863b6-129">Эти параметры можно на уровне клиента или пользователя в организации.</span><span class="sxs-lookup"><span data-stu-id="863b6-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="863b6-130">Чтобы узнать больше, ознакомьтесь с [сосуществованием со Skype для бизнеса.](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="863b6-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="863b6-131">**Чат и внешняя связь** в Teams: службы чата относятся к одноранговых или групповым чатам внутри организации, организации или за ее внешними коллегами.</span><span class="sxs-lookup"><span data-stu-id="863b6-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="863b6-132">Внешняя связь также называется федерацией в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="863b6-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="863b6-133">Создание и просмотр собраний **в Teams:** пользователь всегда может создавать собрания по сети с помощью надстройки Outlook Teams, а также телефонного набора по STN во всех сценариях после того, как у пользователя есть лицензия.</span><span class="sxs-lookup"><span data-stu-id="863b6-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="863b6-134">Teams и Skype для бизнеса хранят данные календаря в почтовом ящике Exchange пользователя.</span><span class="sxs-lookup"><span data-stu-id="863b6-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="863b6-135">Чтобы клиент Teams мог взаимодействовать с почтовым ящиком пользователя, на локальном сервере Exchange должен быть Exchange Server 2016 с cu3 или более высокой.</span><span class="sxs-lookup"><span data-stu-id="863b6-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="863b6-136">Если у почтового ящика Exchange нет доступа к значку "Календарь" в Teams, пользователь не сможет просматривать, создавать и изменять собрания в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="863b6-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="863b6-137">**Функции звонков VoIP и STN** в Teams: звонки могут быть голосовой связью по IP-адресу (VoIP) или телефонной сети общего звонков (STN).</span><span class="sxs-lookup"><span data-stu-id="863b6-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="863b6-138">Подключение по VoIP происходит в основном между клиентами Teams, а подключение по STN происходит при наборе пользователем внешнего номера телефона.</span><span class="sxs-lookup"><span data-stu-id="863b6-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="863b6-139">Teams поддерживает два типа связи через ДНР.</span><span class="sxs-lookup"><span data-stu-id="863b6-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="863b6-140">План звонков Майкрософт, если корпорация Майкрософт предоставляет инфраструктуру телефонии, включая номер телефона пользователя или конфигурацию прямой маршрутации, где клиент обеспечивает телефонное подключение по граничным контроллерам сеансов (SBC) для пользователя Teams.</span><span class="sxs-lookup"><span data-stu-id="863b6-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="863b6-141">Чтобы узнать больше, ознакомьтесь с планом звонков, который вам больше всего [нужно?](calling-plan-landing-page.md) и прямой [маршрутизов телефонной системы.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="863b6-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="863b6-142">**Совместная работа в Teams** и каналах: в Teams команды — это группы людей, сгрупп которых были общими для работы, проектов или общих интересов.</span><span class="sxs-lookup"><span data-stu-id="863b6-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="863b6-143">Команды состоит из каналов.</span><span class="sxs-lookup"><span data-stu-id="863b6-143">Teams are made up of channels.</span></span> <span data-ttu-id="863b6-144">Каждый канал строится на тему, например "События команды", название отдела или просто для развлечения.</span><span class="sxs-lookup"><span data-stu-id="863b6-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="863b6-145">Каналы — это место проведения собраний, бесед и совместной работы над файлами.</span><span class="sxs-lookup"><span data-stu-id="863b6-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="863b6-146">Во время совместной работы</span><span class="sxs-lookup"><span data-stu-id="863b6-146">During collaboration</span></span>

<span data-ttu-id="863b6-147">OneDrive для бизнеса **(P2P-** общий доступ к файлам) в Teams: за пределами Teams и каналов пользователи Teams могут делиться файлами одноранговой связи с помощью OneDrive для бизнеса или других файлов P2P-файлов, таких как Файлы Citrix, DropBox, Box и Google Диск.</span><span class="sxs-lookup"><span data-stu-id="863b6-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="863b6-148">Для OneDrive для бизнеса пользователю должна быть назначена лицензия на SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="863b6-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="863b6-149">**Платформа приложений:** приложения предоставляют вам все необходимые инструменты для вашей организации, чтобы лучше использовать Teams.</span><span class="sxs-lookup"><span data-stu-id="863b6-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="863b6-150">В этих приложениях доступны вкладки, расширения для обмена сообщениями, соединители и боты, предоставляемые корпорацией Майкрософт, сторонними разработчиками или сторонними разработчиками.</span><span class="sxs-lookup"><span data-stu-id="863b6-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="863b6-151">**Функции безопасности и соответствия требованиям:** Teams имеет широкий набор сведений, которые помогут вам в обеспечении соответствия требованиям, включая политики хранения, защиту от потери данных (DLP), eDiscovery и удержание по юридическим каналам, чатам и файлам, поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="863b6-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="863b6-152">Для получения дополнительных данных ознакомьтесь [с безопасностью и соответствием требованиям в Microsoft Teams.](security-compliance-overview.md)</span><span class="sxs-lookup"><span data-stu-id="863b6-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="863b6-153">Для advance eDiscovery требуется лицензирование E5.</span><span class="sxs-lookup"><span data-stu-id="863b6-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="863b6-154">[Сравнение вариантов лицензирования.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)</span><span class="sxs-lookup"><span data-stu-id="863b6-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="863b6-155">Узнайте, [как Exchange и Microsoft Teams взаимодействуют,](exchange-teams-interact.md) чтобы узнать, какие функции соответствия требованиям доступны в вашем сценарии.</span><span class="sxs-lookup"><span data-stu-id="863b6-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="863b6-156">Организации **<span class="underline">без</span>** Skype для бизнеса и Lync Server</span><span class="sxs-lookup"><span data-stu-id="863b6-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="863b6-157">Предполагается, что ваша организация в настоящее время не использует Skype для бизнеса или Lync Server, а Teams будет вашим первым приложением в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="863b6-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="863b6-158">В следующей таблице данная таблица подробных сведений о высокоуровневой конфигурации и возможностях конечных пользователей в Teams для основных служб.</span><span class="sxs-lookup"><span data-stu-id="863b6-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="863b6-159">Item</span><span class="sxs-lookup"><span data-stu-id="863b6-159">Item</span></span></th>
<th><span data-ttu-id="863b6-160">Notes</span><span class="sxs-lookup"><span data-stu-id="863b6-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="863b6-161">Конфигурация Teams клиента</span><span class="sxs-lookup"><span data-stu-id="863b6-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="863b6-162">Режим "Только в Teams", все функции чата и звонков находятся только в Teams.</span><span class="sxs-lookup"><span data-stu-id="863b6-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="863b6-163">Чат и внешняя связь в Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="863b6-164">Внутренняя (внутренняя организация Microsoft 365 или Office 365) и взаимодействие с внешним чатом из Teams.</span><span class="sxs-lookup"><span data-stu-id="863b6-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="863b6-165"><em>Примечание. Для внешнего доступа необходимо настроить записи DNS.</span><span class="sxs-lookup"><span data-stu-id="863b6-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="863b6-166">Записи DNS для Skype для бизнеса необходимы, даже если у вас нет локальной службы Skype для бизнеса или в Microsoft 365 или Office 365 можно разрешить федерацию со средами Lync и Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="863b6-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="863b6-167">
<a href="/office365/enterprise/external-domain-name-system-records">Записи внешней системы доменных имен</a></em></span><span class="sxs-lookup"><span data-stu-id="863b6-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="863b6-168">Создание и просмотр собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="863b6-169">Возможность создавать внутренние и внешние собрания с помощью надстройки Outlook.</span><span class="sxs-lookup"><span data-stu-id="863b6-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="863b6-170">Для лицензий на аудиоконференцию доступны функции телефонного дозвона и телефонного набора через ПС.</span><span class="sxs-lookup"><span data-stu-id="863b6-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="863b6-171">Для доступа к календарю Teams требуется exchange 2016 с дополнительными локальной конфигурацией, развернутой с помощью гибридного развертывания Exchange: создание гибридного развертывания с помощью мастера <a href="/exchange/hybrid-deployment/deploy-hybrid">гибридной конфигурации.</a> </span><span class="sxs-lookup"><span data-stu-id="863b6-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="863b6-172">Помимо гибридной конфигурации Exchange, можно установить проверку подлинности Exchange OAuth: настроить проверку подлинности <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth между организациями Exchange и Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="863b6-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="863b6-173">Функции звонков</span><span class="sxs-lookup"><span data-stu-id="863b6-173">Calling Features</span></span><br />
<span data-ttu-id="863b6-174">VoIP и STN в Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="863b6-175">Доступно внутреннее и внешнее voIP-решение для клиента.</span><span class="sxs-lookup"><span data-stu-id="863b6-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="863b6-176">Службы ННР можно настроить с помощью телефонной системы Майкрософт, а также добавить план звонков Майкрософт или прямую маршрутику.</span><span class="sxs-lookup"><span data-stu-id="863b6-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="863b6-177">Совместная работа в командах и каналах в Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="863b6-178">Для полноценной работы, включая функции соответствия требованиям, пользователю необходимо назначит лицензию На SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="863b6-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="863b6-179">Перенос существующих локального сайта SharePoint не требуется.</span><span class="sxs-lookup"><span data-stu-id="863b6-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="863b6-180">OneDrive для бизнеса (P2P-файлами)</span><span class="sxs-lookup"><span data-stu-id="863b6-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="863b6-181">Для работы OneDrive для бизнеса необходимо, чтобы пользователю была назначена лицензия на SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="863b6-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="863b6-182">Без этой одноранговой лицензии одноранговой общий доступ к файлам будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="863b6-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="863b6-183">Платформа приложений</span><span class="sxs-lookup"><span data-stu-id="863b6-183">Application platform</span></span></td>
<td><span data-ttu-id="863b6-184">Пользователи смогут использовать приложения, назначенные для них в соответствии с политиками компании.</span><span class="sxs-lookup"><span data-stu-id="863b6-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="863b6-185">Подробнее: <a href="/microsoftteams/admin-settings">параметры администратора для приложений в Teams</a></span><span class="sxs-lookup"><span data-stu-id="863b6-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="863b6-186">Функции безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="863b6-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="863b6-187">Доступны политики хранения.</span><span class="sxs-lookup"><span data-stu-id="863b6-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="863b6-188">Поддерживается eDiscovery и удержание по юридическим каналам для обеспечения соответствия требованиям в сообщениях каналов.</span><span class="sxs-lookup"><span data-stu-id="863b6-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="863b6-189">В настоящее время доступны политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="863b6-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="863b6-190">Полный набор функций, доступных в Exchange Online; Большая часть этих функций поддерживается локальной службой Exchange.</span><span class="sxs-lookup"><span data-stu-id="863b6-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="863b6-191">Полный список см. в <a href="/MicrosoftTeams/exchange-teams-interact">взаимодействии Exchange и Teams.</a></span><span class="sxs-lookup"><span data-stu-id="863b6-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="863b6-192">Шаги для обеспечения работы организаций без Skype для бизнеса и Lync Server</span><span class="sxs-lookup"><span data-stu-id="863b6-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="863b6-193">Соответствует требованиям, подробным в разделе "Начните здесь" выше</span><span class="sxs-lookup"><span data-stu-id="863b6-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="863b6-194">Переключение клиента в режим "Только Teams" (только для существующих клиентов): настройка параметров сосуществования [и обновления.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="863b6-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="863b6-195">Настройте клиент в соответствии с политиками организации: управление настройками [Microsoft Teams в организации.](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="863b6-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="863b6-196">Развертывание клиента Teams для пользователей: ["Получить клиенты для Teams"](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="863b6-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="863b6-197">Управлять программой принятия</span><span class="sxs-lookup"><span data-stu-id="863b6-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="863b6-198">Внедрение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="863b6-199">Краткий контрольный список по внедрению Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="863b6-200">Планирование переноса других рабочих нагрузок в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="863b6-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="863b6-201">Организации **<span class="underline">со</span>** Skype для бизнеса или сервером Lync</span><span class="sxs-lookup"><span data-stu-id="863b6-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="863b6-202">Предполагается, что ваша организация использует локально сервер Skype для бизнеса 2019 или 2015+ или Lync 2013+.</span><span class="sxs-lookup"><span data-stu-id="863b6-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="863b6-203">Для организаций, переносимых с локального сервера в Teams, уже есть различные рекомендации, и в этих сценариях необходимо следовать этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="863b6-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="863b6-204">Это руководство характерна для сценария, когда Teams является первым приложением, которое вы используете в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="863b6-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="863b6-205">В следующей таблице данная таблица подробных сведений о высокоуровневой конфигурации и возможностях конечных пользователей в Teams для основных служб.</span><span class="sxs-lookup"><span data-stu-id="863b6-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="863b6-206">Item</span><span class="sxs-lookup"><span data-stu-id="863b6-206">Item</span></span></th>
<th><span data-ttu-id="863b6-207">Notes</span><span class="sxs-lookup"><span data-stu-id="863b6-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="863b6-208">Конфигурация Teams клиента</span><span class="sxs-lookup"><span data-stu-id="863b6-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="863b6-209">Режим "О-ва".</span><span class="sxs-lookup"><span data-stu-id="863b6-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="863b6-210">Чат и внешняя связь в Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="863b6-211">Внутренняя внешняя связь (федерация) осуществляется только в рамках развертывания Skype для бизнеса или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="863b6-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="863b6-212">Создание и просмотр собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="863b6-213">Возможность создавать внутренние и внешние собрания с помощью надстройки Outlook.</span><span class="sxs-lookup"><span data-stu-id="863b6-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="863b6-214">Для лицензий на аудиоконференцию доступны функции телефонного дозвона и телефонного набора через ПС.</span><span class="sxs-lookup"><span data-stu-id="863b6-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="863b6-215">Для доступа к календарю Teams требуется локальное развертывание Exchange 2016 CU3+ с установленным гибридным развертыванием Exchange:</span><span class="sxs-lookup"><span data-stu-id="863b6-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="863b6-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Создайте гибридное развертывание с помощью мастера гибридной конфигурации.</a></span><span class="sxs-lookup"><span data-stu-id="863b6-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="863b6-217">Администратор может управлять надстройкой Skype для бизнеса Outlook с помощью атрибута PreferredMeetingProviderForIslandsMode политики собраний Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy.</a></span><span class="sxs-lookup"><span data-stu-id="863b6-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="863b6-218">Функции звонков</span><span class="sxs-lookup"><span data-stu-id="863b6-218">Calling Features</span></span><br />
<span data-ttu-id="863b6-219">VoIP и STN в Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="863b6-220">Доступно внутреннее решение VoIP для клиента.</span><span class="sxs-lookup"><span data-stu-id="863b6-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="863b6-221">Службы ПС или плана звонков недоступны, пока пользователь не будет перемещен в интерфейс Только Teams.</span><span class="sxs-lookup"><span data-stu-id="863b6-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="863b6-222">Совместная работа в командах и каналах в Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="863b6-223">Для полноценной работы, включая функции соответствия требованиям, пользователю необходимо назначит лицензию На SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="863b6-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="863b6-224">Перенос существующих локального сайта SharePoint не требуется.</span><span class="sxs-lookup"><span data-stu-id="863b6-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="863b6-225">OneDrive для бизнеса (P2P-файлами)</span><span class="sxs-lookup"><span data-stu-id="863b6-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="863b6-226">Для работы OneDrive для бизнеса необходимо, чтобы пользователю была назначена лицензия на SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="863b6-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="863b6-227">Без этой лицензии одноранговой общий доступ к файлам будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="863b6-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="863b6-228">Платформа приложений</span><span class="sxs-lookup"><span data-stu-id="863b6-228">Application platform</span></span></td>
<td><span data-ttu-id="863b6-229">Пользователи смогут использовать приложения, назначенные для них в соответствии с политиками компании.</span><span class="sxs-lookup"><span data-stu-id="863b6-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="863b6-230">Подробнее: <a href="/microsoftteams/admin-settings">параметры администратора для приложений в Teams</a></span><span class="sxs-lookup"><span data-stu-id="863b6-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="863b6-231">Функции безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="863b6-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="863b6-232">Доступны политики хранения.</span><span class="sxs-lookup"><span data-stu-id="863b6-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="863b6-233">Поддерживается eDiscovery и удержание по юридическим каналам для обеспечения соответствия требованиям в сообщениях каналов.</span><span class="sxs-lookup"><span data-stu-id="863b6-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="863b6-234">В настоящее время доступны политики защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="863b6-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="863b6-235">Полный набор функций, доступных в Exchange Online; Большая часть этих функций поддерживается локальной службой Exchange.</span><span class="sxs-lookup"><span data-stu-id="863b6-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="863b6-236">Полный список см. в взаимодействии <a href="/MicrosoftTeams/exchange-teams-interact">Exchange и Teams.</a></span><span class="sxs-lookup"><span data-stu-id="863b6-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="863b6-237">Этапы обеспечения работы для организаций со Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="863b6-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="863b6-238">Соответствует требованиям, подробным в разделе "Начните здесь" выше.</span><span class="sxs-lookup"><span data-stu-id="863b6-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="863b6-239">Переключение клиента в режим "О-ва" (для клиентов, которые были подготовка после 01.09.2019 г., обратитесь в службу поддержки, чтобы внести это изменение)</span><span class="sxs-lookup"><span data-stu-id="863b6-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="863b6-240">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="863b6-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="863b6-241">Настройка клиента в соответствии с политиками организации</span><span class="sxs-lookup"><span data-stu-id="863b6-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="863b6-242">Управление параметрами Microsoft Teams в организации</span><span class="sxs-lookup"><span data-stu-id="863b6-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="863b6-243">Развертывание клиента Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="863b6-244">Получите клиенты для Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="863b6-245">Управлять программой принятия</span><span class="sxs-lookup"><span data-stu-id="863b6-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="863b6-246">Внедрение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="863b6-247">Краткий контрольный список по внедрению Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="863b6-248">Планирование переноса других рабочих нагрузок в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="863b6-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="863b6-249">Гибридное решение Skype для бизнеса и обновление Серверов Skype для бизнеса и Lync с помощью рекомендуемых путей обновления</span><span class="sxs-lookup"><span data-stu-id="863b6-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="863b6-250">Обновление локального приложения Skype для бизнеса до Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="863b6-251">Закрываю выписку</span><span class="sxs-lookup"><span data-stu-id="863b6-251">Closing statement</span></span>

<span data-ttu-id="863b6-252">Microsoft Teams позволяет вашей организации собрать всех сотрудников, информационных работников и сотрудников, работающих с frontline, на одной платформе.</span><span class="sxs-lookup"><span data-stu-id="863b6-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="863b6-253">Вы можете [начать работу уже](https://products.office.com/microsoft-teams/group-chat-software) сегодня.</span><span class="sxs-lookup"><span data-stu-id="863b6-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="863b6-254">Здесь вы можете всегда быть на связи со всеми последними объявлениями и ежемесячными обновлениями [продуктов.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)</span><span class="sxs-lookup"><span data-stu-id="863b6-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="863b6-255">Кроме того, так как компании во всем мире управляют текущей ситуацией COVID-19, мы создали ряд контента, который поможет вам использовать Teams для максимального влияния в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="863b6-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="863b6-256">Наши [обязательства перед клиентами во время COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="863b6-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="863b6-257">Две недели: что мы узнали о удаленной работе</span><span class="sxs-lookup"><span data-stu-id="863b6-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="863b6-258">Проведения собраний и мероприятий по сети</span><span class="sxs-lookup"><span data-stu-id="863b6-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="863b6-259">Помощь малым и средним предприятиями с удаленной работой в Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="863b6-260">Цифровое преобразование трансляций: результаты наблюдений Г.Берина на переднем</span><span class="sxs-lookup"><span data-stu-id="863b6-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="863b6-261">9 основных способов, с помощью которых ИТ-специалисты Майкрософт обеспечивает удаленную работу для своих сотрудников</span><span class="sxs-lookup"><span data-stu-id="863b6-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="863b6-262">Работа в удаленном режиме и обеспечение безопасности — советы по CISOS</span><span class="sxs-lookup"><span data-stu-id="863b6-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="863b6-263">Помощь преподавателям и учащимся в переходе на дистанционное обучение</span><span class="sxs-lookup"><span data-stu-id="863b6-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="863b6-264">Работая удаленно с помощью Microsoft Teams, вы работаете эффективно</span><span class="sxs-lookup"><span data-stu-id="863b6-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="863b6-265">Справка по службам поддержки</span><span class="sxs-lookup"><span data-stu-id="863b6-265">Support Services reference</span></span>

<span data-ttu-id="863b6-266">Teams использует Exchange Online, SharePoint Online, OneDrive для бизнеса и Группы Microsoft 365, чтобы предоставить пользователям полностью интегрированную службу Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="863b6-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="863b6-267">Как было отмечено выше, Teams будет работать без полного развертывания этих служб с ограниченными возможностями.</span><span class="sxs-lookup"><span data-stu-id="863b6-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="863b6-268">Дополнительные информацию о Teams и ее предварительных требованиях можно найти здесь: [добро пожаловать в Teams.](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="863b6-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="863b6-269">Для конкретных служб, указанных выше, выполните указанные ниже ссылки.</span><span class="sxs-lookup"><span data-stu-id="863b6-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="863b6-270">Exchange Online используется для календаря и хранения одноранговых сообщений в Teams.</span><span class="sxs-lookup"><span data-stu-id="863b6-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="863b6-271">Чтобы узнать больше, ознакомьтесь с [взаимодействием Exchange и Teams](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="863b6-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="863b6-272">Для взаимодействия Teams с локальной exchange необходимо настроить новый протокол проверки подлинности Exchange OAuth, как описано в окне "Настройка проверки подлинности OAuth между exchange и [Exchange Online".](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="863b6-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="863b6-273">SharePoint используется для общего доступа к файлам в каналах, а /OneDrive для бизнеса — для обмена файлами в 1:1 или групповом чате.</span><span class="sxs-lookup"><span data-stu-id="863b6-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="863b6-274">Чтобы узнать больше, ознакомьтесь с тем, как [SharePoint Online и OneDrive для бизнеса](sharepoint-onedrive-interact.md)взаимодействуют с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="863b6-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="863b6-275">[Группы Microsoft 365](office-365-groups.md) используются для создания и управления командами и каналами.</span><span class="sxs-lookup"><span data-stu-id="863b6-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="863b6-276">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="863b6-276">Related topics</span></span>

[<span data-ttu-id="863b6-277">Плакаты ИТ-архитектуры и решений для телефонии Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="863b6-278">Планирование гибридного подключения между приложением Skype для бизнеса Server и Office 365</span><span class="sxs-lookup"><span data-stu-id="863b6-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="863b6-279">Поддержка удаленных сотрудников с помощью Teams</span><span class="sxs-lookup"><span data-stu-id="863b6-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="863b6-280">Удаленная работа с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="863b6-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)