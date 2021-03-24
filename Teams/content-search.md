---
title: Поиск контента в Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Узнайте, как с помощью поиска контента в Центре соответствия требованиям Microsoft 365 искать содержимое Microsoft Teams, которое хранится в Exchange Online, SharePoint Online, OneDrive для бизнеса и OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3758f96dc4755303ce8ccf3cae4443deb2a5cd99
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094289"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="1c470-103">Использование поиска контента в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1c470-103">Use Content search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="1c470-104">Поиск контента в сообщениях и файлах в частных [каналах](private-channels.md) работает не так, как в стандартных каналах.</span><span class="sxs-lookup"><span data-stu-id="1c470-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="1c470-105">Подробнее см. в [поиске контента в закрытых каналах.](#content-search-of-private-channels)</span><span class="sxs-lookup"><span data-stu-id="1c470-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="1c470-106">Поиск контента позволяет запрашивать сведения в Microsoft Teams, охватывающих Exchange, SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1c470-106">Content search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="1c470-107">Подробнее см. в [поиске контента в Microsoft 365.](/microsoft-365/compliance/content-search)</span><span class="sxs-lookup"><span data-stu-id="1c470-107">To learn more, see [Content search in Microsoft 365](/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="1c470-108">Например, используя  поиск контента для почтового ящика производственной спецификации и сайта SharePoint по производственным спецификациям, вы можете искать беседы стандартных каналов Teams из Exchange, отправку файлов и изменения из SharePoint Online и OneNote.</span><span class="sxs-lookup"><span data-stu-id="1c470-108">For example, using **Content search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="1c470-109">Вы также можете добавить условия запроса для **Поиска контента**, чтобы сузить возвращаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="1c470-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="1c470-110">В примере выше можно найти содержимое, в котором использовались ключевые слова **"New Factory Specs".**</span><span class="sxs-lookup"><span data-stu-id="1c470-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="1c470-111">После добавления условий поиска можно экспортировать отчет или фактическое содержимое на компьютер для анализа.</span><span class="sxs-lookup"><span data-stu-id="1c470-111">After adding search conditions, you can export a report or the actual content to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="1c470-112">Поиск контента в закрытых каналах</span><span class="sxs-lookup"><span data-stu-id="1c470-112">Content search of private channels</span></span>

<span data-ttu-id="1c470-113">Записи для сообщений, отправленных по частному каналу, доставляются в почтовый ящик всех участников частного канала, а не в групповой почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="1c470-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="1c470-114">Названия записей форматируются, чтобы указать, с какого частного канала они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="1c470-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="1c470-115">Так как у каждого частного канала есть собственное веб-собрание SharePoint, которое отделено от родительского сайта группы, управление файлами в частном канале не отделялось от родительской команды.</span><span class="sxs-lookup"><span data-stu-id="1c470-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="1c470-116">Teams не поддерживает поиск контента в одном канале, поэтому необходимо искать вся команда.</span><span class="sxs-lookup"><span data-stu-id="1c470-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="1c470-117">Чтобы выполнить поиск контента в частном канале, выполните поиск в группе, в семейсе веб-сайтов, связанном с закрытым каналом (чтобы включить файлы), а также в почтовых ящиках участников частного канала (включая сообщения).</span><span class="sxs-lookup"><span data-stu-id="1c470-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="1c470-118">Чтобы определить файлы и сообщения в частном канале и включить их в поиск контента, с помощью следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1c470-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="1c470-119">Включить файлы частных каналов в поиск контента</span><span class="sxs-lookup"><span data-stu-id="1c470-119">Include private channel files in a content search</span></span>

<span data-ttu-id="1c470-120">Перед выполнением этих действий установите управляющую оболочку [SharePoint Online и подключитесь к SharePoint Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="1c470-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="1c470-121">Чтобы получить список всех коллекций веб-сайтов SharePoint, связанных с частными каналами в группе, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1c470-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="1c470-122">Запустите следующий сценарий PowerShell, чтобы получить список URL-адресов всех сайтов sharePoint, связанных с частными каналами в группе, и их ИД родительской группы.</span><span class="sxs-lookup"><span data-stu-id="1c470-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="1c470-123">Чтобы определить все соответствующие сайты частных каналов, запустите следующий сценарий PowerShell для каждой группы или группы:</span><span class="sxs-lookup"><span data-stu-id="1c470-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="1c470-124">Включить сообщения частного канала в поиск контента</span><span class="sxs-lookup"><span data-stu-id="1c470-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="1c470-125">Перед выполнением этих действий убедитесь, что установлена последняя версия [модуля Teams PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1c470-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="1c470-126">Чтобы получить список частных каналов в команде, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1c470-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="1c470-127">Чтобы получить список участников частного канала, запустите следующую ссылку:</span><span class="sxs-lookup"><span data-stu-id="1c470-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="1c470-128">Включите в запрос поиска контента почтовые ящики всех участников каждого частного канала в команду.</span><span class="sxs-lookup"><span data-stu-id="1c470-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1c470-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1c470-129">Related topics</span></span>

- [<span data-ttu-id="1c470-130">Дела eDiscovery в Центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1c470-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](/Office365/SecurityCompliance/ediscovery-cases)