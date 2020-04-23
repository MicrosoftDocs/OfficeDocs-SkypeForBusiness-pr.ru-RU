---
title: Предварительное развертывание Microsoft Teams
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
description: Используйте это руководство для развертывания Microsoft Teams в качестве первой рабочей нагрузки Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9db6b2192224e796475c903cf5eeeaa06ecdc8ee
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780378"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="37e47-103">Предварительное развертывание Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="37e47-104">Microsoft Teams помогает вашим сотрудникам оставаться на связи и взаимодействовать друг с другом, особенно в неопределенном времени, когда удаленная работа является реальной для сотрудников по всему миру.</span><span class="sxs-lookup"><span data-stu-id="37e47-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="37e47-105">Вы можете общаться с друзьями, проводить видеособрания и работать над документами Office в рамках групп, чтобы помочь компаниям оставаться на курсе труда.</span><span class="sxs-lookup"><span data-stu-id="37e47-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="37e47-106">Если вы являетесь малым предприятием, некоммерческой или крупной организацией, вы можете приступить к работе с группами в качестве первой рабочей нагрузки в Office 365 Suite, прежде чем развертывать любые другие приложения или службы Office.</span><span class="sxs-lookup"><span data-stu-id="37e47-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="37e47-107">В этой статье приводятся сведения о том, что нужно сделать с подходом "Teams First".</span><span class="sxs-lookup"><span data-stu-id="37e47-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37e47-108">Несмотря на то, что Teams может быть первой развернутой рабочей нагрузкой Организации, развертывание групп должно быть частью вашей общей стратегии развертывания в облаке.</span><span class="sxs-lookup"><span data-stu-id="37e47-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="37e47-109">Если вы уже выполнили развертывание других служб Office 365, а затем вы выполняете следующую рабочую нагрузку (вместо первой), начните с [того, чтобы выполнить развертывание групп](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="37e47-109">If you have already rolled out other Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out  Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="37e47-110">С чего начать</span><span class="sxs-lookup"><span data-stu-id="37e47-110">Start here</span></span>

<span data-ttu-id="37e47-111">Чтобы приступить к первому развертыванию Teams, вам нужно будет выполнить по крайней мере некоторые предварительные требования.</span><span class="sxs-lookup"><span data-stu-id="37e47-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="37e47-112">В списке ниже приведены сведения о том, что необходимо для вашей организации, прежде чем можно будет включить Teams.</span><span class="sxs-lookup"><span data-stu-id="37e47-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="37e47-113">Организация Office 365, настроенная с использованием вашего доменного имени</span><span class="sxs-lookup"><span data-stu-id="37e47-113">An Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="37e47-114">Подключение к Azure Active Directory (AAD Connect) или аналогичное решение для синхронизации облачных удостоверений — с синхронизацией всех необходимых атрибутов с вашим клиентом</span><span class="sxs-lookup"><span data-stu-id="37e47-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="37e47-115">Для понимания атрибутов, синхронизированных с синхронизацией AAD, читайте [в Azure AD Connect Sync: атрибуты, синхронизированные с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="37e47-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="37e47-116">Соответствующие пользовательские лицензии, назначенные для Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="37e47-117">Для понимания лицензирования Teams ознакомьтесь со статьей [Лицензирование Office 365 для Microsoft Teams](office-365-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="37e47-117">To understand Teams licensing, read [Office 365 licensing for Microsoft Teams](office-365-licensing.md)</span></span>

4.  <span data-ttu-id="37e47-118">Сеть Организации, подготовленная для Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="37e47-119">Для понимания подготовки сети прочтите [Подготовьте сеть Организации для Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="37e47-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="37e47-120">Предоставление доступа к сети для Exchange, SharePoint и OneDrive для бизнеса в Office 365: [URL-адреса и диапазоны IP-адресов для office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="37e47-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="37e47-121">Клиенты, созданные после 1 сентября 2019, подготавливаются в режиме "только для Teams".</span><span class="sxs-lookup"><span data-stu-id="37e47-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="37e47-122">Если у вас развернутый сервер Skype для бизнеса и клиент был предоставлен после 1 сентября 2019, обратитесь в службу поддержки Premier, чтобы включить возможности сосуществования для Teams.</span><span class="sxs-lookup"><span data-stu-id="37e47-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact premier support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="37e47-123">Убедитесь в том, что для политики «корпоративная настройка обновления» задано значение "режим предмета", <span class="underline">перед тем как</span> назначать пользователям лицензии на команды.</span><span class="sxs-lookup"><span data-stu-id="37e47-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="37e47-124">Начальные точки миграции</span><span class="sxs-lookup"><span data-stu-id="37e47-124">Migration Starting points</span></span>

<span data-ttu-id="37e47-125">Ваше путешествие в Office 365 и компоненты, доступные в Teams, в зависимости от начальной точки и существования локального Skype для бизнеса или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37e47-125">Your journey to Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="37e47-126">В следующих разделах описаны базовые возможности и параметры конфигурации, а также предварительные условия, описанные выше.</span><span class="sxs-lookup"><span data-stu-id="37e47-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="37e47-127">Мы разработали сценарии начальной точки в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="37e47-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="37e47-128">**Конфигурация Teams**: клиент и пользовательский режимы используются для управления работой получателя.</span><span class="sxs-lookup"><span data-stu-id="37e47-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="37e47-129">Эти параметры могут быть назначены на уровне клиента или на уровне пользователя в Организации.</span><span class="sxs-lookup"><span data-stu-id="37e47-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="37e47-130">Для получения дополнительных сведений ознакомьтесь с разделом " [сосуществование" в Skype для бизнеса](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="37e47-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="37e47-131">**Чат/внешняя связь в Teams**: службы чата ссылаются на одноранговые и групповые беседы в Организации и в рамках Организации или внешней компании.</span><span class="sxs-lookup"><span data-stu-id="37e47-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="37e47-132">Внешняя связь также называется федерациям в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="37e47-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="37e47-133">**Создавайте и просматривайте собрания в Teams**: пользователь всегда может создавать собрания по сети с помощью надстройки Outlook Teams, а коммутируемая телефонная сеть — во всех сценариях после лицензирования пользователя.</span><span class="sxs-lookup"><span data-stu-id="37e47-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="37e47-134">Службы Teams и Skype для бизнеса хранят данные календаря в почтовом ящике Exchange пользователя.</span><span class="sxs-lookup"><span data-stu-id="37e47-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="37e47-135">Для того чтобы клиент Teams мог взаимодействовать с почтовым ящиком пользователя, на локальном сервере Exchange Server должно быть Exchange Server 2016 CU3 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="37e47-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="37e47-136">Без доступа к почтовому ящику Exchange значок календаря в Teams не отображается, и пользователи не смогут просматривать, создавать и изменять собрания в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="37e47-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="37e47-137">**Вызов функций VoIP/КТСОП в Teams**: звонки могут принимать голосовую связь по протоколу IP (VoIP) или коммутируемую телефонную сеть (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="37e47-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="37e47-138">Подключение к VoIP осуществляется изначально между клиентами Teams, в то время как подключение по протоколу PSTN происходит, когда пользователь звонит на внешний номер телефона.</span><span class="sxs-lookup"><span data-stu-id="37e47-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="37e47-139">Teams поддерживает два типа сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="37e47-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="37e47-140">План звонков (Майкрософт), когда корпорация Майкрософт предоставляет номер телефона пользователя или конфигурацию Direct Routing, где клиент обеспечивает подключение телефонной связи через контроллер границ сеанса (SBC) для пользователя Teams.</span><span class="sxs-lookup"><span data-stu-id="37e47-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="37e47-141">Чтобы узнать больше, прочитайте, [какой тарифный план вам подойдет для вас?](calling-plan-landing-page.md) и [прямую маршрутизацию на телефонную систему](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="37e47-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="37e47-142">**Совместная работа групп и каналов в Teams**: в Teams Teams — это группы людей, Объединенные по работе, проектам и общим интересам.</span><span class="sxs-lookup"><span data-stu-id="37e47-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="37e47-143">Группы состоят из каналов.</span><span class="sxs-lookup"><span data-stu-id="37e47-143">Teams are made up of channels.</span></span> <span data-ttu-id="37e47-144">Каждый канал строится вокруг темы, например "события группы", "название отдела" или только для экспериментов.</span><span class="sxs-lookup"><span data-stu-id="37e47-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="37e47-145">Каналы служат для хранения собраний, общения и совместной работы над файлами.</span><span class="sxs-lookup"><span data-stu-id="37e47-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="37e47-146">Во время совместной работы</span><span class="sxs-lookup"><span data-stu-id="37e47-146">During collaboration</span></span>

<span data-ttu-id="37e47-147">**Onedrive для бизнеса (общий доступ к ФАЙЛАМ P2P) в Teams**: за пределами Teams и channels пользователи Teams могут предоставлять доступ к файлам одноранговой сети с помощью OneDrive для бизнеса или других приложений для совместного доступа к файлам, таких как Citrix Files, Dropbox, Box и Google диск.</span><span class="sxs-lookup"><span data-stu-id="37e47-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="37e47-148">Для OneDrive для бизнеса пользователю должна быть назначена лицензия SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="37e47-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="37e47-149">**Платформа приложений**: приложения предоставляют готовые инструменты для Организации, позволяющие получить доступ к группам.</span><span class="sxs-lookup"><span data-stu-id="37e47-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="37e47-150">Эти приложения объединяют функции вкладок, расширения для сообщений, соединителей и ботов, предоставляемые корпорацией Майкрософт, разработанные сторонними разработчиками или разработчиков вашей организации.</span><span class="sxs-lookup"><span data-stu-id="37e47-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="37e47-151">**Возможности обеспечения безопасности и соответствия требованиям:** В Teams предусмотрен широкий спектр сведений, которые помогут вам в использовании областей соответствия требованиям, в том числе политик хранения, защиты от потери данных (DLP), eDiscovery и юридических удержаний для каналов, чатов и файлов, поиска в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="37e47-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="37e47-152">Для получения дополнительных сведений ознакомьтесь со статьей [безопасность и соответствие требованиям в Microsoft Teams](security-compliance-overview.md).</span><span class="sxs-lookup"><span data-stu-id="37e47-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="37e47-153">Для авансовых возможностей обнаружения электронных данных требуется лицензирование вододействия.</span><span class="sxs-lookup"><span data-stu-id="37e47-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="37e47-154">[Сравните параметры лицензирования](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span><span class="sxs-lookup"><span data-stu-id="37e47-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="37e47-155">Узнайте, [как Exchange и Microsoft Teams взаимодействуют с тем](exchange-teams-interact.md) , какие функции соответствия доступны в вашем сценарии.</span><span class="sxs-lookup"><span data-stu-id="37e47-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="37e47-156">Организации **<span class="underline">без</span>** Skype для бизнеса или Lync Server</span><span class="sxs-lookup"><span data-stu-id="37e47-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="37e47-157">В этой начальной точке предполагается, что ваша организация не использует Skype для бизнеса или Lync Server в настоящее время, а teams будет первым приложением в Office 365.</span><span class="sxs-lookup"><span data-stu-id="37e47-157">This starting point assumes that your organization does not utilize Skype for Business or Lync server currently and Teams will be your first application in Office 365.</span></span> <span data-ttu-id="37e47-158">В приведенной ниже таблице описаны возможности конфигурации высокого уровня и конечных пользователей для Teams для основных служб.</span><span class="sxs-lookup"><span data-stu-id="37e47-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="37e47-159">Item</span><span class="sxs-lookup"><span data-stu-id="37e47-159">Item</span></span></th>
<th><span data-ttu-id="37e47-160">Notes</span><span class="sxs-lookup"><span data-stu-id="37e47-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="37e47-161">Настройка клиентов Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="37e47-162">Режим "только для Teams", все функции "чат" и "звонки" доступны только в Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-162">Teams Only mode, all chat and calling features are in Teams Only</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37e47-163">Чат/внешняя связь в Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="37e47-164">Внутренние (в организациях Office 365) и внешние возможности общения с друзьями из Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-164">Internal (intra Office 365 organization) and external chat communication possible from Teams</span></span></p>
<p><span data-ttu-id="37e47-165"><em>Примечание. DNS-записи должны быть настроены для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="37e47-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="37e47-166">DNS-записи в Skype для бизнеса необходимы даже в том случае, если у вас нет локальной компании Skype для бизнеса или в Office 365, чтобы разрешить федерацию в среде Lync и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="37e47-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises or in Office 365 to allow federation with Lync and Skype for Business environments.</span></span><br /><span data-ttu-id="37e47-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Внешние записи в системе доменных имен для Office 365</a></em></span><span class="sxs-lookup"><span data-stu-id="37e47-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records for Office 365</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37e47-168"><em>Создание и Просмотр собраний в Teams</em></span><span class="sxs-lookup"><span data-stu-id="37e47-168"><em>Create and view Meetings in Teams</em></span></span></td>
<td><p><span data-ttu-id="37e47-169"><em>Возможность создания собраний с помощью надстройки Outlook</em></span><span class="sxs-lookup"><span data-stu-id="37e47-169"><em>Able to create meetings via Outlook add-in</em></span></span></p>
<p><span data-ttu-id="37e47-170"><em>Коммутируемая телефонная связь и возможность исходящих звонков доступны с помощью лицензий на голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="37e47-170"><em>PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="37e47-171">Примечание. для доступа к календарю Teams требуется Exchange 2016 CU3 + локально развернуто с установленным гибридным приложением Exchange: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">создание гибридного развертывания с помощью мастера гибридной конфигурации</a></span><span class="sxs-lookup"><span data-stu-id="37e47-171">Note: Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span><br />
<span data-ttu-id="37e47-172">В дополнение к гибридной конфигурации Exchange Установите проверку подлинности OAuth Exchange: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Настройка проверки подлинности OAuth между Exchange и организациями Exchange Online</a></em></span><span class="sxs-lookup"><span data-stu-id="37e47-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations</a></em></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37e47-173">Функции звонков</span><span class="sxs-lookup"><span data-stu-id="37e47-173">Calling Features</span></span><br />
<span data-ttu-id="37e47-174">VoIP/КТСОП в Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="37e47-175">Доступно внутреннее и внешнее VoIP-связь с клиентом.</span><span class="sxs-lookup"><span data-stu-id="37e47-175">VoIP internally and externally to the tenant is available</span></span></p>
<p><span data-ttu-id="37e47-176">Услуги PSTN можно настроить через телефонную систему Microsoft, а также добавить план звонков (Майкрософт) или прямую переадресацию.</span><span class="sxs-lookup"><span data-stu-id="37e47-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37e47-177">Совместная работа групп и каналов в Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="37e47-178">Для полного взаимодействия, в том числе функций соответствия требованиям, необходимо назначить лицензию на SharePoint Online пользователю.</span><span class="sxs-lookup"><span data-stu-id="37e47-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="37e47-179">Миграция существующих локальных сайтов SharePoint не требуется.</span><span class="sxs-lookup"><span data-stu-id="37e47-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37e47-180">OneDrive для бизнеса (общий доступ к файлам P2P)</span><span class="sxs-lookup"><span data-stu-id="37e47-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="37e47-181">Для работы с OneDrive для бизнеса требуется, чтобы у пользователя была назначена лицензия SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="37e47-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="37e47-182">Без этого партнера одноранговый общий доступ к файлам будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="37e47-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37e47-183">Платформа приложения</span><span class="sxs-lookup"><span data-stu-id="37e47-183">Application platform</span></span></td>
<td><span data-ttu-id="37e47-184">Пользователи смогут использовать приложения, которые предназначены для них в соответствии с политиками компании.</span><span class="sxs-lookup"><span data-stu-id="37e47-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="37e47-185">Дополнительные сведения: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Параметры администратора для приложений в Teams</a></span><span class="sxs-lookup"><span data-stu-id="37e47-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37e47-186">Функции безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="37e47-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="37e47-187">Доступны политики хранения</span><span class="sxs-lookup"><span data-stu-id="37e47-187">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="37e47-188">поддерживается обнаружение электронных данных и юридическое удержание для соответствия с сообщениями канала</span><span class="sxs-lookup"><span data-stu-id="37e47-188">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="37e47-189">Доступны политики защиты от потери данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="37e47-189">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="37e47-190">Полный набор функций, доступных в Exchange Online, в локальной среде Exchange поддерживается большинство этих функций.</span><span class="sxs-lookup"><span data-stu-id="37e47-190">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="37e47-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Взаимодействие Exchange и Teams</a></span><span class="sxs-lookup"><span data-stu-id="37e47-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<p><span data-ttu-id="37e47-192">для полного списка</span><span class="sxs-lookup"><span data-stu-id="37e47-192">for full list</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="37e47-193">Действия по включению для организаций без Skype для бизнеса или Lync Server</span><span class="sxs-lookup"><span data-stu-id="37e47-193">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="37e47-194">Соблюдайте предварительные требования, описанные в разделе "начало</span><span class="sxs-lookup"><span data-stu-id="37e47-194">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="37e47-195">Переключение клиента в режим "только для Teams" (только для существующих клиентов): [Настройка параметров сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="37e47-195">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="37e47-196">Настройте клиент в соответствии с политикой Организации и Организации: [Управление параметрами Microsoft Teams для Организации](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="37e47-196">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="37e47-197">Развертывание клиента Teams для пользователей: [получение клиентов для Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="37e47-197">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="37e47-198">Диск программы внедрения</span><span class="sxs-lookup"><span data-stu-id="37e47-198">Drive your adoption program</span></span>  
    [<span data-ttu-id="37e47-199">Внедрение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-199">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="37e47-200">Краткий контрольный список по внедрению Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-200">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="37e47-201">Начало планирования перемещения других рабочих нагрузок в Office 365</span><span class="sxs-lookup"><span data-stu-id="37e47-201">Begin planning moving other workloads to Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="37e47-202">Организации **<span class="underline">с помощью</span>** Skype для бизнеса или Lync Server</span><span class="sxs-lookup"><span data-stu-id="37e47-202">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="37e47-203">Эта начальная точка предполагает, что ваша организация использует Skype для бизнеса 2019 или 2015 + или Lync 2013 + Server локально.</span><span class="sxs-lookup"><span data-stu-id="37e47-203">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="37e47-204">У нас уже есть обширные рекомендации для организаций, которые переходят с локальных серверов на Teams и должны следовать этим сценариям.</span><span class="sxs-lookup"><span data-stu-id="37e47-204">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="37e47-205">Это руководство характерно для сценария, который Teams является первым приложением, которое вы использует в Office 365.</span><span class="sxs-lookup"><span data-stu-id="37e47-205">This guidance is specific to the scenario that Teams is the first application you utilize in Office 365.</span></span> <span data-ttu-id="37e47-206">В приведенной ниже таблице описаны возможности конфигурации высокого уровня и конечных пользователей для Teams для основных служб.</span><span class="sxs-lookup"><span data-stu-id="37e47-206">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="37e47-207">Item</span><span class="sxs-lookup"><span data-stu-id="37e47-207">Item</span></span></th>
<th><span data-ttu-id="37e47-208">Notes</span><span class="sxs-lookup"><span data-stu-id="37e47-208">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="37e47-209">Настройка клиентов Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-209">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="37e47-210">Режим "острова"</span><span class="sxs-lookup"><span data-stu-id="37e47-210">Islands mode</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37e47-211">Чат/внешняя связь в Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-211">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="37e47-212">Внутренние только в рамках собственного клиента, внешняя связь (Федерация) — это развертывание Skype для бизнеса или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37e47-212">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37e47-213">Создание и Просмотр собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-213">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="37e47-214">Возможность создания собраний с помощью надстройки Outlook</span><span class="sxs-lookup"><span data-stu-id="37e47-214">Able to create meetings via Outlook add-in</span></span></p>
<p><span data-ttu-id="37e47-215">Коммутируемая телефонная связь и возможность исходящих звонков доступны с помощью лицензий на голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="37e47-215">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="37e47-216">Для доступа к календарю Teams требуется Exchange 2016 CU3 + локально развернуто с установленным гибридным приложением Exchange:</span><span class="sxs-lookup"><span data-stu-id="37e47-216">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="37e47-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Создание гибридного развертывания с помощью мастера гибридной конфигурации</a></span><span class="sxs-lookup"><span data-stu-id="37e47-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37e47-218">Функции звонков</span><span class="sxs-lookup"><span data-stu-id="37e47-218">Calling Features</span></span><br />
<span data-ttu-id="37e47-219">VoIP/КТСОП в Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="37e47-220">Доступно внутреннее VoIP с клиентом</span><span class="sxs-lookup"><span data-stu-id="37e47-220">VoIP internally to the tenant is available</span></span></p>
<p><span data-ttu-id="37e47-221">Услуги PSTN и планы звонков недоступны, пока пользователь не переместится в Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37e47-222">Совместная работа групп и каналов в Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="37e47-223">Для полного взаимодействия, в том числе функций соответствия требованиям, необходимо назначить лицензию на SharePoint Online пользователю.</span><span class="sxs-lookup"><span data-stu-id="37e47-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="37e47-224">Миграция существующих локальных сайтов SharePoint не требуется.</span><span class="sxs-lookup"><span data-stu-id="37e47-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37e47-225">OneDrive для бизнеса (общий доступ к файлам P2P)</span><span class="sxs-lookup"><span data-stu-id="37e47-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="37e47-226">Для работы с OneDrive для бизнеса требуется, чтобы у пользователя была назначена лицензия SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="37e47-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="37e47-227">Без этой лицензии общий доступ к файлам для одноранговых лицензий будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="37e47-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37e47-228">Платформа приложения</span><span class="sxs-lookup"><span data-stu-id="37e47-228">Application platform</span></span></td>
<td><span data-ttu-id="37e47-229">Пользователи смогут использовать приложения, которые предназначены для них в соответствии с политиками компании.</span><span class="sxs-lookup"><span data-stu-id="37e47-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="37e47-230">Дополнительные сведения: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Параметры администратора для приложений в Teams</a></span><span class="sxs-lookup"><span data-stu-id="37e47-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37e47-231">Функции безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="37e47-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="37e47-232">Доступны политики хранения</span><span class="sxs-lookup"><span data-stu-id="37e47-232">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="37e47-233">поддерживается обнаружение электронных данных и юридическое удержание для соответствия с сообщениями канала</span><span class="sxs-lookup"><span data-stu-id="37e47-233">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="37e47-234">Доступны политики защиты от потери данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="37e47-234">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="37e47-235">Полный набор функций, доступных в Exchange Online, в локальной среде Exchange поддерживается большинство этих функций.</span><span class="sxs-lookup"><span data-stu-id="37e47-235">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="37e47-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Взаимодействие Exchange и Teams</a></span><span class="sxs-lookup"><span data-stu-id="37e47-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<ul>
<li><p><span data-ttu-id="37e47-237">для полного списка</span><span class="sxs-lookup"><span data-stu-id="37e47-237">for full list</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="37e47-238">Действия по включению для организаций с помощью Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="37e47-238">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="37e47-239">Соблюдайте предварительные требования, описанные в разделе Start here выше.</span><span class="sxs-lookup"><span data-stu-id="37e47-239">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="37e47-240">Переключение клиента в режим "острова" (для клиентов, подготовленных после 9/1/2019, обратитесь в службу поддержки Premier, чтобы внести изменения).</span><span class="sxs-lookup"><span data-stu-id="37e47-240">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact premier support to make this change)</span></span>  
    [<span data-ttu-id="37e47-241">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="37e47-241">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="37e47-242">Настройка клиента в соответствии с политикой Организации или компании</span><span class="sxs-lookup"><span data-stu-id="37e47-242">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="37e47-243">Управление параметрами Microsoft Teams в организации</span><span class="sxs-lookup"><span data-stu-id="37e47-243">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="37e47-244">Развертывание клиента Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-244">Deploy the Teams client</span></span>  
    [<span data-ttu-id="37e47-245">Получите клиенты для Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-245">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="37e47-246">Диск программы внедрения</span><span class="sxs-lookup"><span data-stu-id="37e47-246">Drive your adoption program</span></span>  
    [<span data-ttu-id="37e47-247">Внедрение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-247">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="37e47-248">Краткий контрольный список по внедрению Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-248">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="37e47-249">Начало планирования перемещения других рабочих нагрузок в Office 365</span><span class="sxs-lookup"><span data-stu-id="37e47-249">Begin planning moving other workloads to Office 365</span></span>

7.  <span data-ttu-id="37e47-250">Установка гибридного развертывания Skype для бизнеса и соблюдение рекомендуемых вариантов перехода для серверов Skype для бизнеса и Lync Server</span><span class="sxs-lookup"><span data-stu-id="37e47-250">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="37e47-251">Переход с Skype для бизнеса локально на Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-251">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="37e47-252">Закрывающая Инструкция</span><span class="sxs-lookup"><span data-stu-id="37e47-252">Closing statement</span></span>

<span data-ttu-id="37e47-253">Microsoft Teams можно использовать для Организации, чтобы предоставить всем сотрудникам, сотрудникам отдела информационных и Firstline работников вместе на одной платформе.</span><span class="sxs-lookup"><span data-stu-id="37e47-253">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Firstline workers, together on a single platform.</span></span> <span data-ttu-id="37e47-254">Вы можете приступить к [работе](https://products.office.com/microsoft-teams/group-chat-software) прямо сейчас.</span><span class="sxs-lookup"><span data-stu-id="37e47-254">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="37e47-255">Вы можете всегда оставаться на связи со всеми актуальными объявлениями и ежемесячными [обновлениями](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)продуктов.</span><span class="sxs-lookup"><span data-stu-id="37e47-255">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="37e47-256">Кроме того, так как компании по всему миру управляют текущей ситуацией COVID-19, мы создали серию содержимого, которая поможет вам использовать группы для максимального воздействия в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="37e47-256">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="37e47-257">Наши [обязательства для пользователей во время COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="37e47-257">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="37e47-258">2 недели в: что мы узнали об удаленной работе</span><span class="sxs-lookup"><span data-stu-id="37e47-258">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="37e47-259">Доставка собраний по сети и событий</span><span class="sxs-lookup"><span data-stu-id="37e47-259">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="37e47-260">Помощь малым и средним предприятиями с удаленной работой в Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-260">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="37e47-261">Цифровое преобразование событий Live Events: Bejanные наблюдения из рядовые</span><span class="sxs-lookup"><span data-stu-id="37e47-261">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="37e47-262">9 основных способов, с помощью которых ИТ-специалисты Майкрософт обеспечивает удаленную работу для своих сотрудников</span><span class="sxs-lookup"><span data-stu-id="37e47-262">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="37e47-263">Работайте в удаленном режиме, поддерживайте безопасность — советы для CISOs</span><span class="sxs-lookup"><span data-stu-id="37e47-263">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="37e47-264">Помощь преподавателям и студентам переход на удаленное обучение</span><span class="sxs-lookup"><span data-stu-id="37e47-264">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="37e47-265">Совместная работа в автономном режиме с помощью Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-265">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="37e47-266">Справочник по службам поддержки</span><span class="sxs-lookup"><span data-stu-id="37e47-266">Support Services reference</span></span>

<span data-ttu-id="37e47-267">Группа разработчиков Exchange Online, SharePoint Online, OneDrive для бизнеса и Microsoft 365 предоставляет пользователям полностью интегрированную среду Office 365.</span><span class="sxs-lookup"><span data-stu-id="37e47-267">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Office 365 experience.</span></span> <span data-ttu-id="37e47-268">Как указано выше, команды будут работать без полного развертывания этих служб с ограниченными возможностями.</span><span class="sxs-lookup"><span data-stu-id="37e47-268">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="37e47-269">Дополнительные сведения о Teams и их предварительных требованиях можно узнать здесь: [Добро пожаловать в Teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="37e47-269">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="37e47-270">Для тех, кто указан в указанных выше службах, воспользуйтесь приведенными ниже ссылками.</span><span class="sxs-lookup"><span data-stu-id="37e47-270">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="37e47-271">Exchange Online используется для работы с календарем и хранения сообщений одноранговых элементов в Teams.</span><span class="sxs-lookup"><span data-stu-id="37e47-271">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="37e47-272">Ознакомьтесь с дополнительными сведениями [о взаимодействии Exchange и Teams](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="37e47-272">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37e47-273">Для взаимодействия Teams с локальным сервером Exchange необходимо настроить новый протокол проверки подлинности OAuth (Exchange), как описано в разделе [Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="37e47-273">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="37e47-274">SharePoint используется для обмена файлами в каналах, в то время как/OneDrive для бизнеса используется для обмена файлами в 1:1 или группового чата.</span><span class="sxs-lookup"><span data-stu-id="37e47-274">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="37e47-275">Чтобы узнать больше, Узнайте, [как SharePoint Online и OneDrive для бизнеса могут взаимодействовать с Microsoft Teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="37e47-275">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="37e47-276">[Группы Microsoft 365](office-365-groups.md) используются для создания и управления группами и каналами.</span><span class="sxs-lookup"><span data-stu-id="37e47-276">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="37e47-277">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="37e47-277">Related topics</span></span>

[<span data-ttu-id="37e47-278">Плакаты ИТ-архитектуры и решений для телефонии Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-278">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="37e47-279">Планирование гибридного подключения между приложением Skype для бизнеса Server и Office 365</span><span class="sxs-lookup"><span data-stu-id="37e47-279">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="37e47-280">Поддержка удаленных сотрудников с помощью Teams</span><span class="sxs-lookup"><span data-stu-id="37e47-280">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="37e47-281">Удаленная работа с Office 365</span><span class="sxs-lookup"><span data-stu-id="37e47-281">Work remotely with Office 365</span></span>](https://aka.ms/remote-work)