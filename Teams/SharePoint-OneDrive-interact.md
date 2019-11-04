---
title: Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Сведения о том, как SharePoint Online и OneDrive для бизнеса работают с Microsoft Teams, включая хранение файлов в приватных чатах, а также взаимодействие между командой, каналом и библиотекой документов.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af1d12eda58dc481ba28bf96ff4ecbfeab8ed5f0
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "37567122"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="3211f-103">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3211f-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="3211f-104">В следующем сеансе показано, как взаимодействие Teams с Azure Active Directory (AAD), группами Office 365, Exchange, SharePoint и OneDrive для бизнеса: [основы Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="3211f-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="3211f-105">Каждая команда в Microsoft Teams имеет свой сайт в SharePoint Online, а каждому каналу в команде назначается папка в библиотеке документов по умолчанию на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="3211f-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="3211f-106">Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams.</span><span class="sxs-lookup"><span data-stu-id="3211f-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="3211f-107">Файлы приватного чата хранятся в папке OneDrive для бизнеса отправителя, а соответствующие разрешения автоматически предоставляются всем участникам в рамках процедуры общего доступа.</span><span class="sxs-lookup"><span data-stu-id="3211f-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="3211f-108">Если пользователям не назначены активные лицензии SharePoint Online, у них нет хранилища OneDrive для бизнеса в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3211f-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="3211f-109">Общий доступ к файлам будет продолжать работать в каналах, но пользователи не смогут предоставлять доступ к файлам в чате, не используя хранилище OneDrive для бизнеса в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3211f-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="3211f-110">При сохранении файлов в библиотеке документов SharePoint Online и OneDrive для бизнеса выполняются все требования по обеспечению соответствия, заданные на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="3211f-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="3211f-111">Интеграция с SharePoint локально в настоящее время не поддерживается для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3211f-111">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="3211f-112">Ниже приведен пример взаимодействия между командой, каналом и библиотекой документов.</span><span class="sxs-lookup"><span data-stu-id="3211f-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="3211f-113">Для каждой команды создается сайт SharePoint, а также папка по умолчанию **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="3211f-113">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="3211f-114">Каждый канал команды, включая канал по умолчанию **Общие**, имеет свою папку внутри папки **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="3211f-114">Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Схема папок "Общие документы" в SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="3211f-116">В настоящее время вы не можете заменить библиотеку документов и сайт SharePoint по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3211f-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="3211f-117">Нас часто спрашивают об этой возможности, и мы рассматриваем пути ее внедрения.</span><span class="sxs-lookup"><span data-stu-id="3211f-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="3211f-118">Обо всех готовящихся изменениях вы можете узнать в [Стратегии развития Teams](https://aka.ms/teamsroadmap) и в [посвященном Teams разделе UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="3211f-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="3211f-119">Чтобы добавить вкладку в группу, которая ссылается на существующую страницу сайта SharePoint или на существующую библиотеку документов SharePoint, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3211f-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="3211f-120">Щелкните знак "плюс" рядом с закладками.</span><span class="sxs-lookup"><span data-stu-id="3211f-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="3211f-121">Выберите **SharePoint** для существующей библиотеки документов либо страницы сайта SharePoint или **библиотеки документов** .</span><span class="sxs-lookup"><span data-stu-id="3211f-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="3211f-122">Выберите нужную страницу или библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="3211f-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="3211f-123">У каждого пользователя имеется папка OneDrive **Файлы чатов Microsoft Teams** для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.</span><span class="sxs-lookup"><span data-stu-id="3211f-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Схема папки OneDrive с именами файлов чата Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="3211f-125">Вкладка "файлы канала"</span><span class="sxs-lookup"><span data-stu-id="3211f-125">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="3211f-126">Вкладка " **файлы** " в Teams тесно напоминает представление "документы SharePoint".</span><span class="sxs-lookup"><span data-stu-id="3211f-126">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="3211f-127">На вкладке " **файлы** " пользователи могут:</span><span class="sxs-lookup"><span data-stu-id="3211f-127">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="3211f-128">Дополнительные параметры можно найти в меню **создать** файл.</span><span class="sxs-lookup"><span data-stu-id="3211f-128">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="3211f-129">Синхронизация файлов на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="3211f-129">Sync files to their local drive.</span></span>
- <span data-ttu-id="3211f-130">В меню **все документы** переключиться из режима **списка** в режим **сжатия списка** до **плитки** .</span><span class="sxs-lookup"><span data-stu-id="3211f-130">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="3211f-131">Определите файлы, которые требуют внимания или содержат вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="3211f-131">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="3211f-132">Немедленно проверьте, доступен ли файл только для чтения или извлечен.</span><span class="sxs-lookup"><span data-stu-id="3211f-132">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="3211f-133">Извлечение и возврат файлов.</span><span class="sxs-lookup"><span data-stu-id="3211f-133">Check out and check in files.</span></span>
- <span data-ttu-id="3211f-134">Закрепите, открепите и измените порядок сортировки файлов.</span><span class="sxs-lookup"><span data-stu-id="3211f-134">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="3211f-135">Определение необходимых метаданных для файлов</span><span class="sxs-lookup"><span data-stu-id="3211f-135">Identify which files need metadata</span></span>
- <span data-ttu-id="3211f-136">Выберите один из нескольких других параметров фильтрации.</span><span class="sxs-lookup"><span data-stu-id="3211f-136">Choose from many more filter options.</span></span>
- <span data-ttu-id="3211f-137">Группировка файлов на основе заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="3211f-137">Group files based on column headings.</span></span>
- <span data-ttu-id="3211f-138">Изменение параметров столбца (перемещение влево или вправо, скрыть) и ширины столбцов.</span><span class="sxs-lookup"><span data-stu-id="3211f-138">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="3211f-139">Параметр типа ссылки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3211f-139">Default link type setting</span></span>

<span data-ttu-id="3211f-140">В SharePoint и OneDrive есть параметр администратора для задания типа ссылки по умолчанию для ссылок, создаваемых для файла.</span><span class="sxs-lookup"><span data-stu-id="3211f-140">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="3211f-141">Teams использует тот же подход, повторно используя параметры, заданные администратором для SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3211f-141">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="3211f-142">Дополнительные сведения об этом подходе описаны в разделе [изменение типа ссылки по умолчанию, когда пользователи получают ссылки для совместного использования](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="3211f-142">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="3211f-143">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3211f-143">More information</span></span>

<span data-ttu-id="3211f-144">Дополнительные сведения о том, как SharePoint работает в Teams, можно найти в разделе [SharePoint и teams: более эффективное взаимодействие](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="3211f-144">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="3211f-145">Чтобы узнать больше о работе гостей в Teams, ознакомьтесь со статьей о том, [как они похожи на гостевой интерфейс](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="3211f-145">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

