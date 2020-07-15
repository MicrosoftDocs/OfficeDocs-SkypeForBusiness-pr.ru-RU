---
title: Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & взаимодействие с OneDrive для бизнеса с помощью Teams; хранилище файлов в частном чате & взаимодействие между командой, стандартным каналом & библиотекой документов.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a66cacf7a60b020b4b56e0824d0a275efdf704f8
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2020
ms.locfileid: "45140947"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="dc0ea-103">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc0ea-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="dc0ea-104">В следующем сеансе показано, как взаимодействие Teams с Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint и OneDrive для бизнеса: [основы Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="dc0ea-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="dc0ea-105">Каждая группа в Microsoft Teams имеет сайт группы в SharePoint Online и каждый стандартный канал в группе получает папку в библиотеке документов сайта группы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="dc0ea-106">Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="dc0ea-107">Чтобы увидеть влияние изменения адреса сайта в SharePoint, прочитайте ссылку [изменение адреса сайта](https://docs.microsoft.com/sharepoint/change-site-address).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="dc0ea-108">Эта статья относится только к стандартным каналам.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-108">This article applies only to standard channels.</span></span> <span data-ttu-id="dc0ea-109">Архитектура частных каналов отличается от стандартных каналов.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="dc0ea-110">Каждый частный канал имеет собственную коллекцию сайтов SharePoint, отделенную от родительского сайта группы.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="dc0ea-111">Дополнительные сведения можно найти [в разделе частные каналы в Microsoft Teams](private-channels.md).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="dc0ea-112">Закрытые файлы чата хранятся в папке OneDrive для бизнеса отправителя, и разрешения автоматически предоставляются всем участникам как часть процесса общего доступа к файлам.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="dc0ea-113">Если пользователи не назначены и включены с лицензиями SharePoint Online, они не имеют хранилища OneDrive для бизнеса в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="dc0ea-114">Общий доступ к файлам продолжит работать в стандартных каналах, но пользователи не смогут предоставлять доступ к файлам в чате, не используя хранилище OneDrive для бизнеса в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="dc0ea-115">При сохранении файлов в библиотеке документов SharePoint Online и OneDrive для бизнеса выполняются все требования по обеспечению соответствия, заданные на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="dc0ea-116">Интеграция с SharePoint локально в настоящее время не поддерживается для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="dc0ea-117">Ниже приведен пример связей между командой, стандартным каналом и библиотекой документов.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="dc0ea-118">Для каждой команды создается сайт SharePoint, а также папка по умолчанию **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="dc0ea-119">Каждый стандартный канал, в том числе канал **общего** доступа (канал по умолчанию для каждой команды), имеет папку в **общих документах**.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Схема папок "Общие документы" в SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="dc0ea-121">В настоящее время вы не можете заменить библиотеку документов и сайт SharePoint по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="dc0ea-122">Нас часто спрашивают об этой возможности, и мы рассматриваем пути ее внедрения.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="dc0ea-123">Обо всех готовящихся изменениях вы можете узнать в [Стратегии развития Teams](https://aka.ms/teamsroadmap) и в [посвященном Teams разделе UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="dc0ea-124">Чтобы добавить вкладку в группу, которая ссылается на существующую страницу сайта SharePoint или на существующую библиотеку документов SharePoint, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="dc0ea-125">Щелкните знак "плюс" рядом с закладками.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="dc0ea-126">Выберите **SharePoint** для существующей библиотеки документов либо страницы сайта SharePoint или **библиотеки документов** .</span><span class="sxs-lookup"><span data-stu-id="dc0ea-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="dc0ea-127">Выберите нужную страницу или библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="dc0ea-128">У каждого пользователя имеется папка OneDrive **Файлы чатов Microsoft Teams** для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Схема папки OneDrive с именами файлов чата Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="dc0ea-130">Обратите внимание, что для общедоступных команд на сайте группы SharePoint предоставлен доступ для всех пользователей, кроме внешних.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="dc0ea-131">Общедоступная группа не отображается в Teams для пользователей, которые не входят в эту группу.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="dc0ea-132">Однако они могут получать доступ к контенту на сайте группы SharePoint, используя URL-адрес сайта группы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="dc0ea-133">Вкладка "файлы канала"</span><span class="sxs-lookup"><span data-stu-id="dc0ea-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="dc0ea-134">Вкладка " **файлы** " в Teams тесно напоминает представление "документы SharePoint".</span><span class="sxs-lookup"><span data-stu-id="dc0ea-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="dc0ea-135">На вкладке " **файлы** " пользователи могут:</span><span class="sxs-lookup"><span data-stu-id="dc0ea-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="dc0ea-136">Дополнительные параметры можно найти в меню **создать** файл.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="dc0ea-137">Синхронизация файлов на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="dc0ea-138">В меню **все документы** переключиться из режима **списка** в режим **сжатия списка** до **плитки** .</span><span class="sxs-lookup"><span data-stu-id="dc0ea-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="dc0ea-139">Определите файлы, которые требуют внимания или содержат вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="dc0ea-140">Немедленно проверьте, доступен ли файл только для чтения или извлечен.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="dc0ea-141">Извлечение и возврат файлов.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-141">Check out and check in files.</span></span>
- <span data-ttu-id="dc0ea-142">Закрепите, открепите и измените порядок сортировки файлов.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="dc0ea-143">Определение необходимых метаданных для файлов</span><span class="sxs-lookup"><span data-stu-id="dc0ea-143">Identify which files need metadata</span></span>
- <span data-ttu-id="dc0ea-144">Выберите один из нескольких других параметров фильтрации.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="dc0ea-145">Группировка файлов на основе заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-145">Group files based on column headings.</span></span>
- <span data-ttu-id="dc0ea-146">Изменение параметров столбца (перемещение влево или вправо, скрыть) и ширины столбцов.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="dc0ea-147">Параметр типа ссылки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="dc0ea-147">Default link type setting</span></span>

<span data-ttu-id="dc0ea-148">В SharePoint и OneDrive есть параметр администратора для задания типа ссылки по умолчанию для ссылок, создаваемых для файла.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="dc0ea-149">Teams использует тот же подход, повторно используя параметры, заданные администратором для SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="dc0ea-150">Дополнительные сведения об этом подходе описаны в разделе [изменение типа ссылки по умолчанию, когда пользователи получают ссылки для совместного использования](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-150">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="dc0ea-151">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="dc0ea-151">More information</span></span>

<span data-ttu-id="dc0ea-152">Дополнительные сведения о том, как SharePoint работает в Teams, можно найти в разделе [SharePoint и teams: более эффективное взаимодействие](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="dc0ea-153">Чтобы узнать больше о работе гостей в Teams, ознакомьтесь со статьей о том, [как они похожи на гостевой интерфейс](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

