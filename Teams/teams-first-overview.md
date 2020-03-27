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
ms.openlocfilehash: 79607004c8f750ceed0325733c8c52a4873e9cdc
ms.sourcegitcommit: 89a7c0427a5abbef838a17ae7eac6934c6176a35
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2020
ms.locfileid: "42982163"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="9e8e8-103">Предварительное развертывание Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="9e8e8-104">Microsoft Teams помогает вашим сотрудникам оставаться на связи и взаимодействовать друг с другом, особенно в неопределенном времени, когда удаленная работа является реальной для сотрудников по всему миру.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="9e8e8-105">Вы можете общаться с друзьями, проводить видеособрания и работать над документами Office в рамках групп, чтобы помочь компаниям оставаться на курсе труда.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="9e8e8-106">Если вы являетесь малым предприятием, некоммерческой или крупной организацией, вы можете приступить к работе с группами в качестве первой рабочей нагрузки в Office 365 Suite, прежде чем развертывать любые другие приложения или службы Office.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="9e8e8-107">В этой статье приводятся сведения о том, что нужно сделать с подходом "Teams First".</span><span class="sxs-lookup"><span data-stu-id="9e8e8-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e8e8-108">Несмотря на то, что Teams может быть первой развернутой рабочей нагрузкой Организации, развертывание групп должно быть частью вашей общей стратегии развертывания в облаке.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="9e8e8-109">Если вы уже выполнили развертывание других служб Office 365, а затем вы выполняете следующую рабочую нагрузку (вместо первой), начните с [того, чтобы выполнить развертывание групп](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-109">If you have already rolled out other Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out  Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="9e8e8-110">С чего начать</span><span class="sxs-lookup"><span data-stu-id="9e8e8-110">Start here</span></span>

<span data-ttu-id="9e8e8-111">Чтобы приступить к первому развертыванию Teams, вам нужно будет выполнить по крайней мере некоторые предварительные требования.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="9e8e8-112">В списке ниже приведены сведения о том, что необходимо для вашей организации, прежде чем можно будет включить Teams.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="9e8e8-113">Клиент Office 365, настроенный с использованием вашего доменного имени</span><span class="sxs-lookup"><span data-stu-id="9e8e8-113">An Office 365 tenant configured with your domain name</span></span>

2.  <span data-ttu-id="9e8e8-114">Подключение к Azure Active Directory (AAD Connect) или аналогичное решение для синхронизации облачных удостоверений — с синхронизацией всех необходимых атрибутов с вашим клиентом</span><span class="sxs-lookup"><span data-stu-id="9e8e8-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="9e8e8-115">Для понимания атрибутов, синхронизированных с синхронизацией AAD, читайте [в Azure AD Connect Sync: атрибуты, синхронизированные с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="9e8e8-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="9e8e8-116">Соответствующие пользовательские лицензии, назначенные для Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="9e8e8-117">Для понимания лицензирования Teams ознакомьтесь со статьей [Лицензирование Office 365 для Microsoft Teams](office-365-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="9e8e8-117">To understand Teams licensing, read [Office 365 licensing for Microsoft Teams](office-365-licensing.md)</span></span>

4.  <span data-ttu-id="9e8e8-118">Сеть Организации, подготовленная для Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="9e8e8-119">Для понимания подготовки сети прочтите [Подготовьте сеть Организации для Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="9e8e8-120">Предоставление доступа к сети для Exchange, SharePoint и OneDrive для бизнеса в Office 365: [URL-адреса и диапазоны IP-адресов для office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="9e8e8-121">Клиенты, созданные после 1 сентября 2019, подготавливаются в режиме "только для Teams".</span><span class="sxs-lookup"><span data-stu-id="9e8e8-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="9e8e8-122">Если у вас развернутый сервер Skype для бизнеса и клиент был предоставлен после 1 сентября 2019, обратитесь в службу поддержки Premier, чтобы включить возможности сосуществования для Teams.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact premier support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="9e8e8-123">Убедитесь в том, что для политики «корпоративная настройка обновления» задано значение "режим предмета", <span class="underline">перед тем как</span> назначать пользователям лицензии на команды.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="9e8e8-124">Начальные точки миграции</span><span class="sxs-lookup"><span data-stu-id="9e8e8-124">Migration Starting points</span></span>

<span data-ttu-id="9e8e8-125">Ваше путешествие в Office 365 и компоненты, доступные в Teams, в зависимости от начальной точки и существования локального Skype для бизнеса или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-125">Your journey to Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="9e8e8-126">В следующих разделах описаны базовые возможности и параметры конфигурации, а также предварительные условия, описанные выше.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="9e8e8-127">Мы разработали сценарии начальной точки в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9e8e8-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="9e8e8-128">**Конфигурация Teams**: клиент и пользовательский режимы используются для управления работой получателя.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="9e8e8-129">Эти параметры могут быть назначены на уровне клиента или на уровне пользователя в Организации.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="9e8e8-130">Для получения дополнительных сведений ознакомьтесь с разделом " [сосуществование" в Skype для бизнеса](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="9e8e8-131">**Чат/внешняя связь в Teams**: службы чата ссылаются на одноранговые и групповые беседы в Организации и в рамках Организации или внешней компании.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="9e8e8-132">Внешняя связь также называется федерациям в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="9e8e8-133">**Создавайте и просматривайте собрания в Teams**: пользователь всегда может создавать собрания по сети с помощью надстройки Outlook Teams, а коммутируемая телефонная сеть — во всех сценариях после лицензирования пользователя.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="9e8e8-134">Службы Teams и Skype для бизнеса хранят данные календаря в почтовом ящике Exchange пользователя.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="9e8e8-135">Для того чтобы клиент Teams мог взаимодействовать с почтовым ящиком пользователя, на локальном сервере Exchange Server должно быть Exchange Server 2016 CU3 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="9e8e8-136">Без доступа к почтовому ящику Exchange значок календаря в Teams не отображается, и пользователи не смогут просматривать, создавать и изменять собрания в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="9e8e8-137">**Вызов функций VoIP/КТСОП в Teams**: звонки могут принимать голосовую связь по протоколу IP (VoIP) или коммутируемую телефонную сеть (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="9e8e8-138">Подключение к VoIP осуществляется изначально между клиентами Teams, в то время как подключение по протоколу PSTN происходит, когда пользователь звонит на внешний номер телефона.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="9e8e8-139">Teams поддерживает два типа сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="9e8e8-140">План звонков (Майкрософт), когда корпорация Майкрософт предоставляет номер телефона пользователя или конфигурацию Direct Routing, где клиент обеспечивает подключение телефонной связи через контроллер границ сеанса (SBC) для пользователя Teams.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="9e8e8-141">Чтобы узнать больше, прочитайте, [какой тарифный план вам подойдет для вас?](calling-plan-landing-page.md) и [прямую маршрутизацию на телефонную систему](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="9e8e8-142">**Совместная работа групп и каналов в Teams**: в Teams Teams — это группы людей, Объединенные по работе, проектам и общим интересам.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="9e8e8-143">Группы состоят из каналов.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-143">Teams are made up of channels.</span></span> <span data-ttu-id="9e8e8-144">Каждый канал строится вокруг темы, например "события группы", "название отдела" или только для экспериментов.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="9e8e8-145">Каналы служат для хранения собраний, общения и совместной работы над файлами.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="9e8e8-146">Во время совместной работы</span><span class="sxs-lookup"><span data-stu-id="9e8e8-146">During collaboration</span></span>

<span data-ttu-id="9e8e8-147">**Onedrive для бизнеса (общий доступ к ФАЙЛАМ P2P) в Teams**: за пределами Teams и channels пользователи Teams могут предоставлять доступ к файлам одноранговой сети с помощью OneDrive для бизнеса или других приложений для совместного доступа к файлам, таких как Citrix Files, Dropbox, Box и Google диск.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="9e8e8-148">Для OneDrive для бизнеса пользователю должна быть назначена лицензия SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="9e8e8-149">**Платформа приложений**: приложения предоставляют готовые инструменты для Организации, позволяющие получить доступ к группам.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="9e8e8-150">Эти приложения объединяют функции вкладок, расширения для сообщений, соединителей и ботов, предоставляемые корпорацией Майкрософт, разработанные сторонними разработчиками или разработчиков вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="9e8e8-151">**Возможности обеспечения безопасности и соответствия требованиям:** В Teams предусмотрен широкий спектр сведений, которые помогут вам в использовании областей соответствия требованиям, в том числе политик хранения, защиты от потери данных (DLP), eDiscovery и юридических удержаний для каналов, чатов и файлов, поиска в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="9e8e8-152">Для получения дополнительных сведений ознакомьтесь со статьей [безопасность и соответствие требованиям в Microsoft Teams](security-compliance-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="9e8e8-153">Для авансовых возможностей обнаружения электронных данных требуется лицензирование вододействия.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="9e8e8-154">[Сравните параметры лицензирования](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="9e8e8-155">Узнайте, [как Exchange и Microsoft Teams взаимодействуют с тем](exchange-teams-interact.md) , какие функции соответствия доступны в вашем сценарии.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="9e8e8-156">Организации **<span class="underline">без</span>** Skype для бизнеса или Lync Server</span><span class="sxs-lookup"><span data-stu-id="9e8e8-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="9e8e8-157">В этой начальной точке предполагается, что ваша организация не использует Skype для бизнеса или Lync Server в настоящее время, а teams будет первым приложением в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-157">This starting point assumes that your organization does not utilize Skype for Business or Lync server currently and Teams will be your first application in Office 365.</span></span> <span data-ttu-id="9e8e8-158">В приведенной ниже таблице описаны возможности конфигурации высокого уровня и конечных пользователей для Teams для основных служб.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="9e8e8-159">Item</span><span class="sxs-lookup"><span data-stu-id="9e8e8-159">Item</span></span></th>
<th><span data-ttu-id="9e8e8-160">Notes</span><span class="sxs-lookup"><span data-stu-id="9e8e8-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9e8e8-161">Настройка клиентов Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="9e8e8-162">Режим "только для Teams", все функции "чат" и "звонки" доступны только в Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-162">Teams Only mode, all chat and calling features are in Teams Only</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9e8e8-163">Чат/внешняя связь в Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="9e8e8-164">Внутренние (в клиенте Office 365) и связь с внешним чат из Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-164">Internal (intra Office 365 tenant) and external chat communication possible from Teams</span></span></p>
<p><span data-ttu-id="9e8e8-165"><em>Примечание. DNS-записи должны быть настроены для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="9e8e8-166">DNS-записи в Skype для бизнеса необходимы даже в том случае, если у вас нет локальной компании Skype для бизнеса или в Office 365, чтобы разрешить федерацию в среде Lync и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises or in Office 365 to allow federation with Lync and Skype for Business environments.</span></span><br /><span data-ttu-id="9e8e8-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Внешние записи в системе доменных имен для Office 365</a></em></span><span class="sxs-lookup"><span data-stu-id="9e8e8-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records for Office 365</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9e8e8-168"><em>Создание и Просмотр собраний в Teams</em></span><span class="sxs-lookup"><span data-stu-id="9e8e8-168"><em>Create and view Meetings in Teams</em></span></span></td>
<td><p><span data-ttu-id="9e8e8-169"><em>Возможность создания собраний с помощью надстройки Outlook</em></span><span class="sxs-lookup"><span data-stu-id="9e8e8-169"><em>Able to create meetings via Outlook add-in</em></span></span></p>
<p><span data-ttu-id="9e8e8-170"><em>Коммутируемая телефонная связь и возможность исходящих звонков доступны с помощью лицензий на голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-170"><em>PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="9e8e8-171">Примечание. для доступа к календарю Teams требуется Exchange 2016 CU3 + локально развернуто с установленным гибридным приложением Exchange: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">создание гибридного развертывания с помощью мастера гибридной конфигурации</a></span><span class="sxs-lookup"><span data-stu-id="9e8e8-171">Note: Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span><br />
<span data-ttu-id="9e8e8-172">В дополнение к гибридной конфигурации Exchange Установите проверку подлинности OAuth Exchange: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Настройка проверки подлинности OAuth между Exchange и организациями Exchange Online</a></em></span><span class="sxs-lookup"><span data-stu-id="9e8e8-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations</a></em></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9e8e8-173">Функции звонков</span><span class="sxs-lookup"><span data-stu-id="9e8e8-173">Calling Features</span></span><br />
<span data-ttu-id="9e8e8-174">VoIP/КТСОП в Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="9e8e8-175">Доступно внутреннее и внешнее VoIP-связь с клиентом.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-175">VoIP internally and externally to the tenant is available</span></span></p>
<p><span data-ttu-id="9e8e8-176">Услуги PSTN можно настроить через телефонную систему Microsoft, а также добавить план звонков (Майкрософт) или прямую переадресацию.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9e8e8-177">Совместная работа групп и каналов в Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="9e8e8-178">Для полного взаимодействия, в том числе функций соответствия требованиям, необходимо назначить лицензию на SharePoint Online пользователю.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="9e8e8-179">Миграция существующих локальных сайтов SharePoint не требуется.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9e8e8-180">OneDrive для бизнеса (общий доступ к файлам P2P)</span><span class="sxs-lookup"><span data-stu-id="9e8e8-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="9e8e8-181">Для работы с OneDrive для бизнеса требуется, чтобы у пользователя была назначена лицензия SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="9e8e8-182">Без этого партнера одноранговый общий доступ к файлам будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9e8e8-183">Платформа приложения</span><span class="sxs-lookup"><span data-stu-id="9e8e8-183">Application platform</span></span></td>
<td><span data-ttu-id="9e8e8-184">Пользователи смогут использовать приложения, которые предназначены для них в соответствии с политиками компании.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="9e8e8-185">Дополнительные сведения: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Параметры администратора для приложений в Teams</a></span><span class="sxs-lookup"><span data-stu-id="9e8e8-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9e8e8-186">Функции безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="9e8e8-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="9e8e8-187">Доступны политики хранения</span><span class="sxs-lookup"><span data-stu-id="9e8e8-187">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="9e8e8-188">поддерживается обнаружение электронных данных и юридическое удержание для соответствия с сообщениями канала</span><span class="sxs-lookup"><span data-stu-id="9e8e8-188">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="9e8e8-189">Доступны политики защиты от потери данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="9e8e8-189">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="9e8e8-190">Полный набор функций, доступных в Exchange Online, в локальной среде Exchange поддерживается большинство этих функций.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-190">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="9e8e8-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Взаимодействие Exchange и Teams</a></span><span class="sxs-lookup"><span data-stu-id="9e8e8-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<p><span data-ttu-id="9e8e8-192">для полного списка</span><span class="sxs-lookup"><span data-stu-id="9e8e8-192">for full list</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="9e8e8-193">Действия по включению для организаций без Skype для бизнеса или Lync Server</span><span class="sxs-lookup"><span data-stu-id="9e8e8-193">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="9e8e8-194">Соблюдайте предварительные требования, описанные в разделе "начало</span><span class="sxs-lookup"><span data-stu-id="9e8e8-194">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="9e8e8-195">Переключение клиента в режим "только для Teams" (только для существующих клиентов): [Настройка параметров сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-195">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="9e8e8-196">Настройте клиент в соответствии с политикой Организации и Организации: [Управление параметрами Microsoft Teams для Организации](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-196">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="9e8e8-197">Развертывание клиента Teams для пользователей: [получение клиентов для Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="9e8e8-197">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="9e8e8-198">Диск программы внедрения</span><span class="sxs-lookup"><span data-stu-id="9e8e8-198">Drive your adoption program</span></span>  
    [<span data-ttu-id="9e8e8-199">Внедрение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-199">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="9e8e8-200">Краткий контрольный список по внедрению Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-200">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="9e8e8-201">Начало планирования перемещения других рабочих нагрузок в Office 365</span><span class="sxs-lookup"><span data-stu-id="9e8e8-201">Begin planning moving other workloads to Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="9e8e8-202">Организации **<span class="underline">с помощью</span>** Skype для бизнеса или Lync Server</span><span class="sxs-lookup"><span data-stu-id="9e8e8-202">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="9e8e8-203">Эта начальная точка предполагает, что ваша организация использует Skype для бизнеса 2019 или 2015 + или Lync 2013 + Server локально.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-203">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="9e8e8-204">У нас уже есть обширные рекомендации для организаций, которые переходят с локальных серверов на Teams и должны следовать этим сценариям.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-204">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="9e8e8-205">Это руководство характерно для сценария, который Teams является первым приложением, которое вы использует в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-205">This guidance is specific to the scenario that Teams is the first application you utilize in Office 365.</span></span> <span data-ttu-id="9e8e8-206">В приведенной ниже таблице описаны возможности конфигурации высокого уровня и конечных пользователей для Teams для основных служб.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-206">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="9e8e8-207">Item</span><span class="sxs-lookup"><span data-stu-id="9e8e8-207">Item</span></span></th>
<th><span data-ttu-id="9e8e8-208">Notes</span><span class="sxs-lookup"><span data-stu-id="9e8e8-208">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9e8e8-209">Настройка клиентов Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-209">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="9e8e8-210">Режим "острова"</span><span class="sxs-lookup"><span data-stu-id="9e8e8-210">Islands mode</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9e8e8-211">Чат/внешняя связь в Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-211">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="9e8e8-212">Внутренние только в рамках собственного клиента, внешняя связь (Федерация) — это развертывание Skype для бизнеса или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-212">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9e8e8-213">Создание и Просмотр собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-213">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="9e8e8-214">Возможность создания собраний с помощью надстройки Outlook</span><span class="sxs-lookup"><span data-stu-id="9e8e8-214">Able to create meetings via Outlook add-in</span></span></p>
<p><span data-ttu-id="9e8e8-215">Коммутируемая телефонная связь и возможность исходящих звонков доступны с помощью лицензий на голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-215">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="9e8e8-216">Для доступа к календарю Teams требуется Exchange 2016 CU3 + локально развернуто с установленным гибридным приложением Exchange:</span><span class="sxs-lookup"><span data-stu-id="9e8e8-216">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="9e8e8-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Создание гибридного развертывания с помощью мастера гибридной конфигурации</a></span><span class="sxs-lookup"><span data-stu-id="9e8e8-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9e8e8-218">Функции звонков</span><span class="sxs-lookup"><span data-stu-id="9e8e8-218">Calling Features</span></span><br />
<span data-ttu-id="9e8e8-219">VoIP/КТСОП в Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="9e8e8-220">Доступно внутреннее VoIP с клиентом</span><span class="sxs-lookup"><span data-stu-id="9e8e8-220">VoIP internally to the tenant is available</span></span></p>
<p><span data-ttu-id="9e8e8-221">Услуги PSTN и планы звонков недоступны, пока пользователь не переместится в Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9e8e8-222">Совместная работа групп и каналов в Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="9e8e8-223">Для полного взаимодействия, в том числе функций соответствия требованиям, необходимо назначить лицензию на SharePoint Online пользователю.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="9e8e8-224">Миграция существующих локальных сайтов SharePoint не требуется.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9e8e8-225">OneDrive для бизнеса (общий доступ к файлам P2P)</span><span class="sxs-lookup"><span data-stu-id="9e8e8-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="9e8e8-226">Для работы с OneDrive для бизнеса требуется, чтобы у пользователя была назначена лицензия SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="9e8e8-227">Без этой лицензии общий доступ к файлам для одноранговых лицензий будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9e8e8-228">Платформа приложения</span><span class="sxs-lookup"><span data-stu-id="9e8e8-228">Application platform</span></span></td>
<td><span data-ttu-id="9e8e8-229">Пользователи смогут использовать приложения, которые предназначены для них в соответствии с политиками компании.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="9e8e8-230">Дополнительные сведения: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Параметры администратора для приложений в Teams</a></span><span class="sxs-lookup"><span data-stu-id="9e8e8-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9e8e8-231">Функции безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="9e8e8-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="9e8e8-232">Доступны политики хранения</span><span class="sxs-lookup"><span data-stu-id="9e8e8-232">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="9e8e8-233">поддерживается обнаружение электронных данных и юридическое удержание для соответствия с сообщениями канала</span><span class="sxs-lookup"><span data-stu-id="9e8e8-233">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="9e8e8-234">Доступны политики защиты от потери данных (DLP)</span><span class="sxs-lookup"><span data-stu-id="9e8e8-234">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="9e8e8-235">Полный набор функций, доступных в Exchange Online, в локальной среде Exchange поддерживается большинство этих функций.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-235">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="9e8e8-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Взаимодействие Exchange и Teams</a></span><span class="sxs-lookup"><span data-stu-id="9e8e8-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<ul>
<li><p><span data-ttu-id="9e8e8-237">для полного списка</span><span class="sxs-lookup"><span data-stu-id="9e8e8-237">for full list</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="9e8e8-238">Действия по включению для организаций с помощью Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9e8e8-238">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="9e8e8-239">Соблюдайте предварительные требования, описанные в разделе Start here выше.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-239">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="9e8e8-240">Переключение клиента в режим "острова" (для клиентов, подготовленных после 9/1/2019, обратитесь в службу поддержки Premier, чтобы внести изменения).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-240">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact premier support to make this change)</span></span>  
    [<span data-ttu-id="9e8e8-241">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="9e8e8-241">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="9e8e8-242">Настройка клиента в соответствии с политикой Организации или компании</span><span class="sxs-lookup"><span data-stu-id="9e8e8-242">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="9e8e8-243">Управление параметрами Microsoft Teams в организации</span><span class="sxs-lookup"><span data-stu-id="9e8e8-243">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="9e8e8-244">Развертывание клиента Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-244">Deploy the Teams client</span></span>  
    [<span data-ttu-id="9e8e8-245">Работа с клиентами для Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-245">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="9e8e8-246">Диск программы внедрения</span><span class="sxs-lookup"><span data-stu-id="9e8e8-246">Drive your adoption program</span></span>  
    [<span data-ttu-id="9e8e8-247">Внедрение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-247">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="9e8e8-248">Краткий контрольный список по внедрению Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-248">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="9e8e8-249">Начало планирования перемещения других рабочих нагрузок в Office 365</span><span class="sxs-lookup"><span data-stu-id="9e8e8-249">Begin planning moving other workloads to Office 365</span></span>

7.  <span data-ttu-id="9e8e8-250">Установка гибридного развертывания Skype для бизнеса и соблюдение рекомендуемых вариантов перехода для серверов Skype для бизнеса и Lync Server</span><span class="sxs-lookup"><span data-stu-id="9e8e8-250">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="9e8e8-251">Переход с Skype для бизнеса локально на Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-251">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="9e8e8-252">Закрывающая Инструкция</span><span class="sxs-lookup"><span data-stu-id="9e8e8-252">Closing statement</span></span>

<span data-ttu-id="9e8e8-253">Microsoft Teams можно использовать для Организации, чтобы предоставить всем сотрудникам, сотрудникам отдела информационных и Firstline работников вместе на одной платформе.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-253">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Firstline workers, together on a single platform.</span></span> <span data-ttu-id="9e8e8-254">Вы можете приступить к [работе](https://products.office.com/microsoft-teams/group-chat-software) прямо сейчас.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-254">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="9e8e8-255">Вы можете всегда оставаться на связи со всеми актуальными объявлениями и ежемесячными [обновлениями](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)продуктов.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-255">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="9e8e8-256">Кроме того, так как компании по всему миру управляют текущей ситуацией КОВИД-19, мы создали серию содержимого, которая поможет вам использовать группы для максимального воздействия в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-256">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="9e8e8-257">Наши [обязательства для пользователей во время ковид-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="9e8e8-257">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="9e8e8-258">2 недели в: что мы узнали об удаленной работе</span><span class="sxs-lookup"><span data-stu-id="9e8e8-258">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="9e8e8-259">Доставка собраний по сети и событий</span><span class="sxs-lookup"><span data-stu-id="9e8e8-259">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="9e8e8-260">Работа с группами для малых и средних предприятий</span><span class="sxs-lookup"><span data-stu-id="9e8e8-260">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="9e8e8-261">Цифровое преобразование событий Live Events: Бежанные наблюдения из рядовые</span><span class="sxs-lookup"><span data-stu-id="9e8e8-261">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="9e8e8-262">9 основных способов, с помощью которых Microsoft IT обеспечивает удаленную работу для своих сотрудников</span><span class="sxs-lookup"><span data-stu-id="9e8e8-262">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="9e8e8-263">Работайте в удаленном режиме, поддерживайте безопасность — советы для Цисос</span><span class="sxs-lookup"><span data-stu-id="9e8e8-263">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="9e8e8-264">Помощь преподавателям и студентам переход на удаленное обучение</span><span class="sxs-lookup"><span data-stu-id="9e8e8-264">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="9e8e8-265">Совместная работа в автономном режиме с помощью Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-265">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="9e8e8-266">Справочник по службам поддержки</span><span class="sxs-lookup"><span data-stu-id="9e8e8-266">Support Services reference</span></span>

<span data-ttu-id="9e8e8-267">Группа разработчиков Exchange Online, SharePoint Online, OneDrive для бизнеса и Office 365 предоставляет пользователям полностью интегрированную среду Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-267">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Office 365 Groups to provide your users with a fully integrated Office 365 experience.</span></span> <span data-ttu-id="9e8e8-268">Как указано выше, команды будут работать без полного развертывания этих служб с ограниченными возможностями.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-268">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="9e8e8-269">Дополнительные сведения о Teams и их предварительных требованиях можно узнать здесь: [Добро пожаловать в Teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-269">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="9e8e8-270">Для тех, кто указан в указанных выше службах, воспользуйтесь приведенными ниже ссылками.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-270">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="9e8e8-271">Exchange Online используется для работы с календарем и хранения сообщений одноранговых элементов в Teams.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-271">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="9e8e8-272">Ознакомьтесь с дополнительными сведениями [о взаимодействии Exchange и Teams](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="9e8e8-272">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e8e8-273">Для взаимодействия Teams с локальным сервером Exchange необходимо настроить новый протокол проверки подлинности OAuth (Exchange), как описано в разделе [Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-273">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="9e8e8-274">SharePoint используется для обмена файлами в каналах, в то время как/Онедриве для бизнеса используется для обмена файлами в 1:1 или группового чата.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-274">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="9e8e8-275">Чтобы узнать больше, Узнайте, [как SharePoint Online и OneDrive для бизнеса могут взаимодействовать с Microsoft Teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="9e8e8-275">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="9e8e8-276">[Группы Office 365](office-365-groups.md) используются для создания и управления группами и каналами.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-276">[Office 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9e8e8-277">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9e8e8-277">Related topics</span></span>

[<span data-ttu-id="9e8e8-278">Плакаты ИТ-архитектуры и решений для телефонии Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-278">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="9e8e8-279">Планирование гибридного подключения между приложением Skype для бизнеса Server и Office 365</span><span class="sxs-lookup"><span data-stu-id="9e8e8-279">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="9e8e8-280">Поддержка удаленных сотрудников с помощью Teams</span><span class="sxs-lookup"><span data-stu-id="9e8e8-280">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="9e8e8-281">Удаленная работа с Office 365</span><span class="sxs-lookup"><span data-stu-id="9e8e8-281">Work remotely with Office 365</span></span>](https://aka.ms/remote-work)