---
title: Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Сведения о том, как SharePoint Online и OneDrive для бизнеса работают с Microsoft Teams, включая хранение файлов в приватных чатах, а также взаимодействие между командой, каналом и библиотекой документов.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f790a01050811ee46526fe37a4d6c14f107491b5
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827742"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="559e9-103">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="559e9-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="559e9-104">Просмотрите следующие сеанса, чтобы узнать, как группы взаимодействует с Azure Active Directory (AAD), группы Office 365, Exchange, SharePoint и OneDrive для бизнеса: [Основы группами Майкрософт](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="559e9-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="559e9-105">Каждая команда в Microsoft Teams имеет свой сайт в SharePoint Online, а каждому каналу в команде назначается папка в библиотеке документов по умолчанию на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="559e9-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="559e9-106">Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams.</span><span class="sxs-lookup"><span data-stu-id="559e9-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="559e9-107">Файлы приватного чата хранятся в папке OneDrive для бизнеса отправителя, а соответствующие разрешения автоматически предоставляются всем участникам в рамках процедуры общего доступа.</span><span class="sxs-lookup"><span data-stu-id="559e9-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="559e9-108">Если пользователям не назначены активные лицензии SharePoint Online, у них нет хранилища OneDrive для бизнеса в Office 365.</span><span class="sxs-lookup"><span data-stu-id="559e9-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="559e9-109">Общий доступ к файлам будет продолжать работать в каналы, но пользователи не смогут для совместного использования файлов в чаты без OneDrive для бизнеса хранилища в Office 365.</span><span class="sxs-lookup"><span data-stu-id="559e9-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="559e9-110">При сохранении файлов в библиотеке документов SharePoint Online и OneDrive для бизнеса выполняются все требования по обеспечению соответствия, заданные на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="559e9-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="559e9-111">Интеграция с SharePoint в локальной не поддерживается для групп Майкрософт в данный момент.</span><span class="sxs-lookup"><span data-stu-id="559e9-111">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="559e9-112">Ниже приведен пример взаимодействия между командой, каналом и библиотекой документов.</span><span class="sxs-lookup"><span data-stu-id="559e9-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="559e9-113">Для каждой команды создается сайт SharePoint, а также папка по умолчанию **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="559e9-113">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="559e9-114">Каждый канал команды, включая канал по умолчанию **Общие**, имеет свою папку внутри папки **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="559e9-114">Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Схема папок "Общие документы" в SharePoint Online для команды и ее каналов в Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="559e9-116">В настоящее время вы не можете заменить библиотеку документов и сайт SharePoint по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="559e9-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="559e9-117">Нас часто спрашивают об этой возможности, и мы рассматриваем пути ее внедрения.</span><span class="sxs-lookup"><span data-stu-id="559e9-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="559e9-118">Обо всех готовящихся изменениях вы можете узнать в [Стратегии развития Teams](https://aka.ms/teamsroadmap) и в [посвященном Teams разделе UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="559e9-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="559e9-119">Добавление вкладки в группу, приведены ссылки на существующие страницы сайта SharePoint или для вашей существующей библиотеки документов SharePoint:</span><span class="sxs-lookup"><span data-stu-id="559e9-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="559e9-120">Выберите значок "плюс" рядом с вкладками.</span><span class="sxs-lookup"><span data-stu-id="559e9-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="559e9-121">Выберите **SharePoint** для существующей страницы сайта SharePoint или **Библиотеки документов** для существующей библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="559e9-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="559e9-122">Выберите соответствующую библиотеку страницы или документа.</span><span class="sxs-lookup"><span data-stu-id="559e9-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="559e9-123">У каждого пользователя имеется папка OneDrive **Файлы чатов Microsoft Teams** для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.</span><span class="sxs-lookup"><span data-stu-id="559e9-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Схема папки OneDrive с именем "Файлы чатов Microsoft Teams" для каждого из чатов пользователя.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="559e9-125">Вкладка файлы канала</span><span class="sxs-lookup"><span data-stu-id="559e9-125">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="559e9-126">На вкладку **файлы** в группах аналогичны представления документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="559e9-126">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="559e9-127">На вкладке **файлы** пользователи могут:</span><span class="sxs-lookup"><span data-stu-id="559e9-127">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="559e9-128">Просмотрите дополнительные параметры в меню Файл **New** .</span><span class="sxs-lookup"><span data-stu-id="559e9-128">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="559e9-129">Синхронизация файлов на локальном диске.</span><span class="sxs-lookup"><span data-stu-id="559e9-129">Sync files to their local drive.</span></span>
- <span data-ttu-id="559e9-130">В меню **Все документы** переключитесь из представления **списка** в **компактном список** **заголовков** представление.</span><span class="sxs-lookup"><span data-stu-id="559e9-130">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="559e9-131">Определение файлов, которые требуют внимания или иметь вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="559e9-131">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="559e9-132">Сразу просмотреть ли файл только для чтения или установленное состояние ожидания.</span><span class="sxs-lookup"><span data-stu-id="559e9-132">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="559e9-133">Извлечение и возврат в файлах.</span><span class="sxs-lookup"><span data-stu-id="559e9-133">Check out and check in files.</span></span>
- <span data-ttu-id="559e9-134">Прикрепление и открепление измените порядок сортировки файлов.</span><span class="sxs-lookup"><span data-stu-id="559e9-134">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="559e9-135">Определите, какие файлы должны метаданных</span><span class="sxs-lookup"><span data-stu-id="559e9-135">Identify which files need metadata</span></span>
- <span data-ttu-id="559e9-136">Выберите один из многих дополнительных параметров фильтра.</span><span class="sxs-lookup"><span data-stu-id="559e9-136">Choose from many more filter options.</span></span>
- <span data-ttu-id="559e9-137">Группируйте файлы на основании заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="559e9-137">Group files based on column headings.</span></span>
- <span data-ttu-id="559e9-138">Измените параметры столбца (влево или вправо, скрыть) и ширина столбца.</span><span class="sxs-lookup"><span data-stu-id="559e9-138">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="559e9-139">Настройка типа ссылок по умолчанию</span><span class="sxs-lookup"><span data-stu-id="559e9-139">Default link type setting</span></span>

<span data-ttu-id="559e9-140">SharePoint и OneDrive у параметра для указания типа связи по умолчанию для ссылок, которые создаются для файла.</span><span class="sxs-lookup"><span data-stu-id="559e9-140">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="559e9-141">Команды использует такой же подход, повторное использование параметров, которые администратор устанавливает для SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="559e9-141">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="559e9-142">Дополнительные сведения о такой подход, описаны в [Изменить тип связи по умолчанию, когда пользователи получают ссылки для общего доступа к](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="559e9-142">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="559e9-143">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="559e9-143">More information</span></span>

<span data-ttu-id="559e9-144">Дополнительные сведения о работе с группами SharePoint можно [SharePoint и рабочих групп: эффективная совместная работа](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="559e9-144">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="559e9-145">Для получения дополнительных сведений о гостевой взаимодействия в группах, прочитайте [возможности взаимодействия гостя](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="559e9-145">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

