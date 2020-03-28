---
title: Обнаружение электронных данных в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Узнайте, что делать, если вам нужно провести обнаружение электронных данных, например, если вам нужно отправить информацию о юридическом лице, хранящуюся в процессы.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 315ec351450224dc8d5b98dc0d974b64573bc0ab
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033273"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="51648-103">Обнаружение электронных данных в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="51648-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="51648-104">Крупные предприятия часто открываются в юридическом лице процессы, требующем отправки всей информации, хранящейся в электронном виде (ESI).</span><span class="sxs-lookup"><span data-stu-id="51648-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="51648-105">Все команды групп 1:1 и групповых чатов записываются в почтовые ящики соответствующих пользователей, а все стандартные сообщения электронной почты записываются в почтовый ящик группы, который представляет группу.</span><span class="sxs-lookup"><span data-stu-id="51648-105">All Teams 1:1 or group chats are journaled through to the respective users' mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="51648-106">Файлы, отправленные в стандартных каналах, попадают в работу с обнаружением электронных данных в SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="51648-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="51648-107">Обнаружение электронных сообщений и файлов в [закрытых каналах](private-channels.md) отличается от работы с стандартными каналами.</span><span class="sxs-lookup"><span data-stu-id="51648-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="51648-108">Дополнительные сведения можно найти в разделе [Обнаружение электронных данных в частных каналах](#ediscovery-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="51648-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

> [!NOTE]
> <span data-ttu-id="51648-109">В настоящее время мы не поддерживаем обнаружение электронных сообщений в сценариях, в которых гостевые пользователи являются единственными участниками в 1:1 или 1: без чата.</span><span class="sxs-lookup"><span data-stu-id="51648-109">At this time, we don't support eDiscovery of chat messages in scenarios where guest users are the only participants in a 1:1 or 1:N chat.</span></span> <span data-ttu-id="51648-110">Эти типы чатов также называются *гостевыми* чат-членами, так как они не включают пользователей домашних клиентов.</span><span class="sxs-lookup"><span data-stu-id="51648-110">These types of chats are also called *guest-to-guest* chats because they don't include home tenant users.</span></span>

1. <span data-ttu-id="51648-111">Чтобы провести исследование обнаружения электронных данных с содержимым Microsoft Teams, ознакомьтесь с шагом 1 в [этой](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) ссылке.</span><span class="sxs-lookup"><span data-stu-id="51648-111">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2. <span data-ttu-id="51648-112">Данные Microsoft Teams выводятся в виде мгновенных сообщений или бесед в выходных данных экспорта eDiscovery Excel, и вы можете открыть PST-файл в Outlook, чтобы просмотреть эти сообщения после экспорта.</span><span class="sxs-lookup"><span data-stu-id="51648-112">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can open the PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="51648-113">При просмотре PST-файла команды Обратите внимание на то, что все беседы хранятся в папке "чат группы" в разделе "Журнал бесед".</span><span class="sxs-lookup"><span data-stu-id="51648-113">When viewing the PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="51648-114">Заголовок сообщения содержит команду и канал.</span><span class="sxs-lookup"><span data-stu-id="51648-114">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="51648-115">Проверив изображение ниже, вы увидите это сообщение от Боба, которое обработало канал проекта 7 Standard в команде производство спецификаций.</span><span class="sxs-lookup"><span data-stu-id="51648-115">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Снимок экрана: папка чата команды в почтовом ящике пользователя в Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. <span data-ttu-id="51648-117">Чтобы просмотреть личные разговоры в почтовом ящике пользователя, они также находятся в папке "чат группы" в разделе "Журнал бесед".</span><span class="sxs-lookup"><span data-stu-id="51648-117">To see private chats in a user's mailbox, they are also located in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="51648-118">Обнаружение электронных данных в частных каналах</span><span class="sxs-lookup"><span data-stu-id="51648-118">eDiscovery of private channels</span></span>

<span data-ttu-id="51648-119">Записи для сообщений, отправленных по частному каналу, доставляются в почтовый ящик всех участников частного канала, а не в групповой почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="51648-119">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="51648-120">Названия записей форматируются, чтобы указать, с какого частного канала они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="51648-120">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="51648-121">Поскольку каждый частный канал имеет собственную коллекцию сайтов SharePoint, отделенную от родительского сайта группы, файлы в частном канале управляются независимо от родительской команды.</span><span class="sxs-lookup"><span data-stu-id="51648-121">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="51648-122">Команды не поддерживают обнаружение электронных данных в одном канале, поэтому нужно выполнить поиск во всей команде.</span><span class="sxs-lookup"><span data-stu-id="51648-122">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="51648-123">Чтобы выполнить поиск обнаружения электронных данных в частном канале, выполните поиск по команде, в семействе веб-сайтов, связанном с частным каналом (для включения файлов), и почтовых ящиков участников личного канала (чтобы включить сообщения).</span><span class="sxs-lookup"><span data-stu-id="51648-123">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="51648-124">Выполните указанные ниже действия, чтобы идентифицировать файлы и сообщения в частном канале, чтобы включить их в поиск обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="51648-124">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="51648-125">Включение файлов закрытого канала в поиск обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="51648-125">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="51648-126">Перед выполнением этих действий установите [командную консоль SharePoint Online и подключитесь к SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="51648-126">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="51648-127">Выполните указанные ниже действия, чтобы получить список всех семейств веб-сайтов SharePoint, связанных с частными каналами в команде.</span><span class="sxs-lookup"><span data-stu-id="51648-127">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="51648-128">Запустите следующий сценарий PowerShell, чтобы получить список всех URL-адресов семейств веб-сайтов SharePoint, связанных с частными каналами в команде и ИДЕНТИФИКАТОРом родительской группы групп.</span><span class="sxs-lookup"><span data-stu-id="51648-128">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. <span data-ttu-id="51648-129">Для каждой команды или идентификатора группы выполните следующий сценарий PowerShell для идентификации всех соответствующих сайтов личного канала, где $groupID является ИДЕНТИФИКАТОРом группы для группы.</span><span class="sxs-lookup"><span data-stu-id="51648-129">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="51648-130">Включение сообщений личного канала в поиск обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="51648-130">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="51648-131">Перед выполнением этих действий убедитесь в том, что у вас установлена [новейшая версия модуля Teams PowerShell](teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="51648-131">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="51648-132">Выполните указанные ниже действия, чтобы получить список частных каналов в команде.</span><span class="sxs-lookup"><span data-stu-id="51648-132">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="51648-133">Выполните указанные ниже действия, чтобы получить список участников личного канала.</span><span class="sxs-lookup"><span data-stu-id="51648-133">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="51648-134">Добавьте в запрос поиска eDiscovery почтовые ящики всех участников группы из любого закрытого канала.</span><span class="sxs-lookup"><span data-stu-id="51648-134">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="51648-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="51648-135">Related topics</span></span>

- [<span data-ttu-id="51648-136">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="51648-136">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
