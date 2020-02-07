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
description: Сведения о том, когда требуется обнаружение электронных данных, например при передаче всей информации, хранящейся в электронной форме, для судебных разбирательств.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d85bef224966d15a6c383163d9ac4a5dd5ed126c
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833799"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="aaba3-103">Обнаружение электронных данных в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aaba3-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="aaba3-104">Крупные предприятия часто открываются в юридическом лице процессы, требующем отправки всей информации, хранящейся в электронном виде (еси).</span><span class="sxs-lookup"><span data-stu-id="aaba3-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="aaba3-105">Все команды групп 1:1 и групповых чатов записываются в почтовые ящики соответствующих пользователей, а все стандартные сообщения электронной почты записываются в почтовый ящик группы, который представляет группу.</span><span class="sxs-lookup"><span data-stu-id="aaba3-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="aaba3-106">Файлы, отправленные в стандартных каналах, попадают в работу с обнаружением электронных данных в SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="aaba3-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="aaba3-107">Обнаружение электронных сообщений и файлов в [закрытых каналах](private-channels.md) отличается от работы с стандартными каналами.</span><span class="sxs-lookup"><span data-stu-id="aaba3-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="aaba3-108">Дополнительные сведения можно найти в разделе [Обнаружение электронных данных в частных каналах](#ediscovery-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="aaba3-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

1.  <span data-ttu-id="aaba3-109">Чтобы провести исследование обнаружения электронных данных с содержимым Microsoft Teams, ознакомьтесь с шагом 1 в [этой](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) ссылке.</span><span class="sxs-lookup"><span data-stu-id="aaba3-109">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="aaba3-110">Данные Microsoft Teams будут отображаться в виде мгновенных сообщений или бесед в выходных данных экспорта eDiscovery Excel, и вы можете подключить. PST-файл в Outlook, чтобы просмотреть эти сообщения после экспорта.</span><span class="sxs-lookup"><span data-stu-id="aaba3-110">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="aaba3-111">При подключении PST-файла для команды обратите внимание, что все беседы хранятся в папке "Чат группы" журнала бесед.</span><span class="sxs-lookup"><span data-stu-id="aaba3-111">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="aaba3-112">Заголовок сообщения содержит команду и канал.</span><span class="sxs-lookup"><span data-stu-id="aaba3-112">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="aaba3-113">Проверив изображение ниже, вы увидите это сообщение от Боба, которое обработало канал проекта 7 Standard в команде производство спецификаций.</span><span class="sxs-lookup"><span data-stu-id="aaba3-113">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Снимок экрана: папка чата команды в почтовом ящике пользователя в Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="aaba3-115">Чтобы просмотреть личные разговоры в почтовом ящике пользователя, они также находятся в папке "чат группы" в разделе "Журнал бесед".</span><span class="sxs-lookup"><span data-stu-id="aaba3-115">To see private chats in a user’s mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="aaba3-116">Обнаружение электронных чатов "гость – гость"</span><span class="sxs-lookup"><span data-stu-id="aaba3-116">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="aaba3-117">В настоящее время в случае, если участие в ситуации, когда гостевые пользователи участвуют в 1:1 или 1: N, не поддерживает обнаружение электронных данных этих сообщений в чате.</span><span class="sxs-lookup"><span data-stu-id="aaba3-117">Presently, for a scenario where only guests are participating in 1:1 or 1:N chat, we don't support eDiscovery of those chat messages.</span></span> 

<span data-ttu-id="aaba3-118">Без почтового ящика (например, если в 1xN сеансы, в которых нет пользователей клиентов домашних компьютеров) не будут индексироваться, и в результате они не будут включены в eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="aaba3-118">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="aaba3-119">Чтобы облегчить обнаружение электронных данных для гостевых чатов, создается почтовый ящик на основе облака (или фиктивный почтовый ящик), в котором хранятся данные 1xN.</span><span class="sxs-lookup"><span data-stu-id="aaba3-119">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="aaba3-120">После того как данные чата в Teams будут сохранены в облачном почтовом ящике, она индексируется для поиска в электронных данных и для соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="aaba3-120">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="aaba3-121">На приведенном ниже рисунке показано, как обнаружение электронных данных работает для гостевых чатов, в которых нет почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="aaba3-121">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![Гостевая — разговоры в чате-без почтового ящика](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="aaba3-123">Обнаружение электронных данных в частных каналах</span><span class="sxs-lookup"><span data-stu-id="aaba3-123">eDiscovery of private channels</span></span>

<span data-ttu-id="aaba3-124">Записи для сообщений, отправленных в частном канале, доставляются в почтовый ящик всех участников личного канала, а не в почтовом ящике группы.</span><span class="sxs-lookup"><span data-stu-id="aaba3-124">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="aaba3-125">Заголовки записей форматируются для обозначения закрытого канала, с которого они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="aaba3-125">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="aaba3-126">Поскольку каждый частный канал имеет собственную коллекцию сайтов SharePoint, отделенную от родительского сайта группы, файлы в частном канале управляются независимо от родительской команды.</span><span class="sxs-lookup"><span data-stu-id="aaba3-126">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="aaba3-127">Команды не поддерживают обнаружение электронных данных в одном канале, поэтому нужно выполнить поиск во всей команде.</span><span class="sxs-lookup"><span data-stu-id="aaba3-127">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="aaba3-128">Чтобы выполнить поиск обнаружения электронных данных в частном канале, выполните поиск по команде, в семействе веб-сайтов, связанном с частным каналом (для включения файлов), и почтовых ящиков участников личного канала (чтобы включить сообщения).</span><span class="sxs-lookup"><span data-stu-id="aaba3-128">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="aaba3-129">Выполните указанные ниже действия, чтобы идентифицировать файлы и сообщения в частном канале, чтобы включить их в поиск обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="aaba3-129">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="aaba3-130">Включение файлов закрытого канала в поиск обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="aaba3-130">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="aaba3-131">Перед выполнением этих действий установите [командную консоль SharePoint Online и подключитесь к SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="aaba3-131">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="aaba3-132">Выполните указанные ниже действия, чтобы получить список всех семейств веб-сайтов SharePoint, связанных с частными каналами в команде.</span><span class="sxs-lookup"><span data-stu-id="aaba3-132">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="aaba3-133">Запустите следующий сценарий PowerShell, чтобы получить список всех URL-адресов семейств веб-сайтов SharePoint, связанных с частными каналами в команде и ИДЕНТИФИКАТОРом родительской группы групп.</span><span class="sxs-lookup"><span data-stu-id="aaba3-133">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="aaba3-134">Для каждой команды или идентификатора группы выполните следующий сценарий PowerShell для идентификации всех соответствующих сайтов личного канала, где $groupID является ИДЕНТИФИКАТОРом группы для группы.</span><span class="sxs-lookup"><span data-stu-id="aaba3-134">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="aaba3-135">Включение сообщений личного канала в поиск обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="aaba3-135">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="aaba3-136">Перед выполнением этих действий убедитесь в том, что у вас установлена [новейшая версия модуля Teams PowerShell](teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="aaba3-136">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="aaba3-137">Выполните указанные ниже действия, чтобы получить список частных каналов в команде.</span><span class="sxs-lookup"><span data-stu-id="aaba3-137">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="aaba3-138">Выполните указанные ниже действия, чтобы получить список участников личного канала.</span><span class="sxs-lookup"><span data-stu-id="aaba3-138">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="aaba3-139">Добавьте в запрос поиска eDiscovery почтовые ящики всех участников группы из любого закрытого канала.</span><span class="sxs-lookup"><span data-stu-id="aaba3-139">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="aaba3-140">См. также</span><span class="sxs-lookup"><span data-stu-id="aaba3-140">Related topics</span></span>

- [<span data-ttu-id="aaba3-141">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="aaba3-141">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
