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
description: Сведения об использовании поиска контента в Microsoft Teams для запроса данных Microsoft Teams из Exchange, SharePoint Online, OneDrive для бизнеса и OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d05d815a74fc395c06763920014b7de453847bec
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121529"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="40da9-103">Поиск контента в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40da9-103">Use Content Search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="40da9-104">Поиск контента сообщений и файлов в [закрытых каналах](private-channels.md) отличается от работы со стандартными каналами.</span><span class="sxs-lookup"><span data-stu-id="40da9-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="40da9-105">Дополнительные сведения можно найти в разделе [Поиск контента в частных каналах](#content-search-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="40da9-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="40da9-106">Поиск контента позволяет запрашивать сведения о Microsoft Teams, попадающее в Exchange, SharePoint Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="40da9-106">Content Search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="40da9-107">Подробнее читайте [в статье Поиск содержимого в Microsoft 365 или Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span><span class="sxs-lookup"><span data-stu-id="40da9-107">To learn more, read [Content Search in Microsoft 365 or Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span></span>

<span data-ttu-id="40da9-108">Например, с помощью **поиска по содержимому** на веб-сайте SharePoint specs and specs можно выполнять поиск по стандартным каналам связи в Exchange, отправлять файлы и изменения из SharePoint Online и вносить изменения в OneNote.</span><span class="sxs-lookup"><span data-stu-id="40da9-108">For example, using **Content Search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="40da9-109">Вы также можете добавить условия запроса для **Поиска контента**, чтобы сузить возвращаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="40da9-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="40da9-110">В приведенном выше примере вы можете найти содержимое, в котором использовались ключевые слова "**новые спецификации фабрики"** .</span><span class="sxs-lookup"><span data-stu-id="40da9-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="40da9-111">После добавления условий поиска вы можете экспортировать отчет или данные на компьютер для анализа.</span><span class="sxs-lookup"><span data-stu-id="40da9-111">After adding search conditions, you can export a report or the data to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="40da9-112">Поиск контента в частных каналах</span><span class="sxs-lookup"><span data-stu-id="40da9-112">Content search of private channels</span></span>

<span data-ttu-id="40da9-113">Записи для сообщений, отправленных по частному каналу, доставляются в почтовый ящик всех участников частного канала, а не в групповой почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="40da9-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="40da9-114">Названия записей форматируются, чтобы указать, с какого частного канала они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="40da9-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="40da9-115">Поскольку каждый частный канал имеет собственную коллекцию сайтов SharePoint, отделенную от родительского сайта группы, файлы в частном канале управляются независимо от родительской команды.</span><span class="sxs-lookup"><span data-stu-id="40da9-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="40da9-116">Команды не поддерживают поиск контента в одном канале, поэтому для всей команды нужно выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="40da9-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="40da9-117">Чтобы выполнить поиск контента в частном канале, выполните поиск по команде, в семействе веб-сайтов, связанном с частным каналом (для включения файлов), и почтовых ящиков участников личного канала (для включения сообщений).</span><span class="sxs-lookup"><span data-stu-id="40da9-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="40da9-118">Выполните указанные ниже действия, чтобы определить файлы и сообщения в частном канале, чтобы включить в поиск контента.</span><span class="sxs-lookup"><span data-stu-id="40da9-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="40da9-119">Включение файлов закрытого канала в поиск контента</span><span class="sxs-lookup"><span data-stu-id="40da9-119">Include private channel files in a content search</span></span>

<span data-ttu-id="40da9-120">Перед выполнением этих действий установите [командную консоль SharePoint Online и подключитесь к SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="40da9-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="40da9-121">Выполните указанные ниже действия, чтобы получить список всех семейств веб-сайтов SharePoint, связанных с частными каналами в команде.</span><span class="sxs-lookup"><span data-stu-id="40da9-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="40da9-122">Запустите следующий сценарий PowerShell, чтобы получить список всех URL-адресов семейств веб-сайтов SharePoint, связанных с частными каналами в команде и ИДЕНТИФИКАТОРом родительской группы групп.</span><span class="sxs-lookup"><span data-stu-id="40da9-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="40da9-123">Для каждого кода группы или группы выполните следующий сценарий PowerShell для идентификации всех соответствующих сайтов закрытого канала.</span><span class="sxs-lookup"><span data-stu-id="40da9-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="40da9-124">Включение сообщений личного канала в поиск контента</span><span class="sxs-lookup"><span data-stu-id="40da9-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="40da9-125">Перед выполнением этих действий убедитесь в том, что у вас установлена [новейшая версия модуля Teams PowerShell](teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="40da9-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="40da9-126">Выполните указанные ниже действия, чтобы получить список частных каналов в команде.</span><span class="sxs-lookup"><span data-stu-id="40da9-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="40da9-127">Выполните указанные ниже действия, чтобы получить список участников личного канала.</span><span class="sxs-lookup"><span data-stu-id="40da9-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="40da9-128">Включите в поисковый запрос содержимого почтовые ящики всех участников группы из любого закрытого канала.</span><span class="sxs-lookup"><span data-stu-id="40da9-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="40da9-129">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="40da9-129">Related topics</span></span>

- [<span data-ttu-id="40da9-130">варианты обнаружения электронных данных в центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="40da9-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 