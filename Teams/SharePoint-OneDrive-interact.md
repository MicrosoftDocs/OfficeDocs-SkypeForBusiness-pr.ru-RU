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
description: В этой статье рассказывается о том, как с помощью SharePoint Online и OneDrive для бизнеса взаимодействовать с Microsoft Teams, такие как хранение файлов в частном чате и связь между командой, стандартным каналом и библиотекой документов.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 236b1d570d44395f3499c0a5fec3d3a415953e12
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834689"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="a364a-103">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a364a-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="a364a-104">В следующем сеансе показано, как взаимодействие Teams с Azure Active Directory (AAD), группами Office 365, Exchange, SharePoint и OneDrive для бизнеса: [основы Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="a364a-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="a364a-105">Каждая группа в Microsoft Teams имеет сайт группы в SharePoint Online и каждый стандартный канал в группе получает папку в библиотеке документов сайта группы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a364a-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="a364a-106">Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams.</span><span class="sxs-lookup"><span data-stu-id="a364a-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="a364a-107">Эта статья относится только к стандартным каналам.</span><span class="sxs-lookup"><span data-stu-id="a364a-107">This article applies only to standard channels.</span></span> <span data-ttu-id="a364a-108">Архитектура частных каналов отличается от стандартных каналов.</span><span class="sxs-lookup"><span data-stu-id="a364a-108">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="a364a-109">Каждый частный канал имеет собственную коллекцию сайтов SharePoint, отделенную от родительского сайта группы.</span><span class="sxs-lookup"><span data-stu-id="a364a-109">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="a364a-110">Дополнительные сведения можно найти [в разделе частные каналы в Microsoft Teams](private-channels.md).</span><span class="sxs-lookup"><span data-stu-id="a364a-110">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="a364a-111">Файлы приватного чата хранятся в папке OneDrive для бизнеса отправителя, а соответствующие разрешения автоматически предоставляются всем участникам в рамках процедуры общего доступа.</span><span class="sxs-lookup"><span data-stu-id="a364a-111">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="a364a-112">Если пользователям не назначены активные лицензии SharePoint Online, у них нет хранилища OneDrive для бизнеса в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a364a-112">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="a364a-113">Общий доступ к файлам будет продолжать работать в стандартных каналах, но пользователи не смогут предоставлять доступ к файлам в чате, не используя хранилище OneDrive для бизнеса в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a364a-113">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="a364a-114">При сохранении файлов в библиотеке документов SharePoint Online и OneDrive для бизнеса выполняются все требования по обеспечению соответствия, заданные на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="a364a-114">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="a364a-115">Интеграция с SharePoint локально в настоящее время не поддерживается для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a364a-115">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="a364a-116">Ниже приведен пример связей между командой, стандартным каналом и библиотекой документов.</span><span class="sxs-lookup"><span data-stu-id="a364a-116">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="a364a-117">Для каждой команды создается сайт SharePoint, а также папка по умолчанию **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="a364a-117">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="a364a-118">Каждый стандартный канал, в том числе канал **общего** доступа (канал по умолчанию для каждой команды), имеет папку в **общих документах**.</span><span class="sxs-lookup"><span data-stu-id="a364a-118">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Схема папок "Общие документы" в SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="a364a-120">В настоящее время вы не можете заменить библиотеку документов и сайт SharePoint по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a364a-120">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="a364a-121">Нас часто спрашивают об этой возможности, и мы рассматриваем пути ее внедрения.</span><span class="sxs-lookup"><span data-stu-id="a364a-121">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="a364a-122">Обо всех готовящихся изменениях вы можете узнать в [Стратегии развития Teams](https://aka.ms/teamsroadmap) и в [посвященном Teams разделе UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="a364a-122">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="a364a-123">Чтобы добавить вкладку в группу, которая ссылается на существующую страницу сайта SharePoint или на существующую библиотеку документов SharePoint, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a364a-123">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="a364a-124">Щелкните знак "плюс" рядом с закладками.</span><span class="sxs-lookup"><span data-stu-id="a364a-124">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="a364a-125">Выберите **SharePoint** для существующей библиотеки документов либо страницы сайта SharePoint или **библиотеки документов** .</span><span class="sxs-lookup"><span data-stu-id="a364a-125">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="a364a-126">Выберите нужную страницу или библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="a364a-126">Select the appropriate page or document library.</span></span>

<span data-ttu-id="a364a-127">У каждого пользователя имеется папка OneDrive **Файлы чатов Microsoft Teams** для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.</span><span class="sxs-lookup"><span data-stu-id="a364a-127">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Схема папки OneDrive с именами файлов чата Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="a364a-129">Вкладка "файлы канала"</span><span class="sxs-lookup"><span data-stu-id="a364a-129">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="a364a-130">Вкладка " **файлы** " в Teams тесно напоминает представление "документы SharePoint".</span><span class="sxs-lookup"><span data-stu-id="a364a-130">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="a364a-131">На вкладке " **файлы** " пользователи могут:</span><span class="sxs-lookup"><span data-stu-id="a364a-131">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="a364a-132">Дополнительные параметры можно найти в меню **создать** файл.</span><span class="sxs-lookup"><span data-stu-id="a364a-132">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="a364a-133">Синхронизация файлов на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="a364a-133">Sync files to their local drive.</span></span>
- <span data-ttu-id="a364a-134">В меню **все документы** переключиться из режима **списка** в режим **сжатия списка** до **плитки** .</span><span class="sxs-lookup"><span data-stu-id="a364a-134">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="a364a-135">Определите файлы, которые требуют внимания или содержат вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="a364a-135">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="a364a-136">Немедленно проверьте, доступен ли файл только для чтения или извлечен.</span><span class="sxs-lookup"><span data-stu-id="a364a-136">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="a364a-137">Извлечение и возврат файлов.</span><span class="sxs-lookup"><span data-stu-id="a364a-137">Check out and check in files.</span></span>
- <span data-ttu-id="a364a-138">Закрепите, открепите и измените порядок сортировки файлов.</span><span class="sxs-lookup"><span data-stu-id="a364a-138">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="a364a-139">Определение необходимых метаданных для файлов</span><span class="sxs-lookup"><span data-stu-id="a364a-139">Identify which files need metadata</span></span>
- <span data-ttu-id="a364a-140">Выберите один из нескольких других параметров фильтрации.</span><span class="sxs-lookup"><span data-stu-id="a364a-140">Choose from many more filter options.</span></span>
- <span data-ttu-id="a364a-141">Группировка файлов на основе заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="a364a-141">Group files based on column headings.</span></span>
- <span data-ttu-id="a364a-142">Изменение параметров столбца (перемещение влево или вправо, скрыть) и ширины столбцов.</span><span class="sxs-lookup"><span data-stu-id="a364a-142">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="a364a-143">Параметр типа ссылки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a364a-143">Default link type setting</span></span>

<span data-ttu-id="a364a-144">В SharePoint и OneDrive есть параметр администратора для задания типа ссылки по умолчанию для ссылок, создаваемых для файла.</span><span class="sxs-lookup"><span data-stu-id="a364a-144">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="a364a-145">Teams использует тот же подход, повторно используя параметры, заданные администратором для SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a364a-145">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="a364a-146">Дополнительные сведения об этом подходе описаны в разделе [изменение типа ссылки по умолчанию, когда пользователи получают ссылки для совместного использования](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="a364a-146">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="a364a-147">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a364a-147">More information</span></span>

<span data-ttu-id="a364a-148">Дополнительные сведения о том, как SharePoint работает в Teams, можно найти в разделе [SharePoint и teams: более эффективное взаимодействие](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="a364a-148">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="a364a-149">Чтобы узнать больше о работе гостей в Teams, ознакомьтесь со статьей о том, [как они похожи на гостевой интерфейс](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="a364a-149">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

