---
title: Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & взаимодействия OneDrive для бизнеса с Teams; личные хранилища файлов чата & взаимодействия между командой, стандартным каналом и & библиотекой документов.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d063cae8b87ffcacd63676da17fc000384c432c
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948632"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="85b98-103">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85b98-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="85b98-104">Посмотрите следующий эпизод, чтобы узнать, как Teams взаимодействует с Azure Active Directory (AAD), группами Microsoft 365, Exchange, SharePoint и OneDrive для бизнеса: [Основы Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="85b98-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="85b98-105">У каждой группы в Microsoft Teams есть сайт группы в SharePoint Online, а каждый стандартный канал группы получает папку в стандартной библиотеке документов сайта группы.</span><span class="sxs-lookup"><span data-stu-id="85b98-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="85b98-106">Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams.</span><span class="sxs-lookup"><span data-stu-id="85b98-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="85b98-107">Чтобы узнать, как изменение адреса сайта повлияет на SharePoint, см. статью Изменение [адреса сайта.](/sharepoint/change-site-address)</span><span class="sxs-lookup"><span data-stu-id="85b98-107">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="85b98-108">Эта статья относится только к стандартным каналам.</span><span class="sxs-lookup"><span data-stu-id="85b98-108">This article applies only to standard channels.</span></span> <span data-ttu-id="85b98-109">Архитектура частных каналов отличается от стандартной.</span><span class="sxs-lookup"><span data-stu-id="85b98-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="85b98-110">Каждый частный канал имеет собственное собрание веб-сайтов SharePoint, которое отделено от родительского сайта группы.</span><span class="sxs-lookup"><span data-stu-id="85b98-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="85b98-111">Дополнительные узнать см. в [оке Закрытые каналы в Microsoft Teams.](private-channels.md)</span><span class="sxs-lookup"><span data-stu-id="85b98-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="85b98-112">Личные файлы чата хранятся в папке OneDrive для бизнеса отправителем, и в процессе предоставления общего доступа всем участникам автоматически предоставлены разрешения.</span><span class="sxs-lookup"><span data-stu-id="85b98-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="85b98-113">Если пользователям не назначены активные лицензии SharePoint Online, у них нет хранилища OneDrive для бизнеса в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="85b98-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="85b98-114">Общий доступ к файлам будет по-прежнему работать в стандартных каналах, но пользователи не смогут делиться файлами в чатах без хранилища OneDrive для бизнеса в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="85b98-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="85b98-115">При сохранении файлов в библиотеке документов SharePoint Online и OneDrive для бизнеса выполняются все требования по обеспечению соответствия, заданные на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="85b98-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="85b98-116">Интеграция с локальной службой SharePoint в настоящее время не поддерживается в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="85b98-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="85b98-117">Ниже приводится пример связей между командой, стандартным каналом и библиотекой документов.</span><span class="sxs-lookup"><span data-stu-id="85b98-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="85b98-118">Для каждой команды создается сайт SharePoint, а также папка по умолчанию **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="85b98-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="85b98-119">У каждого стандартного канала, включая канал **Общий** (канал по умолчанию для каждой команды), есть папка в **общие документы.**</span><span class="sxs-lookup"><span data-stu-id="85b98-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Схема папок "Общие документы" в SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="85b98-121">В настоящее время вы не можете заменить библиотеку документов и сайт SharePoint по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="85b98-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="85b98-122">Нас часто спрашивают об этой возможности, и мы рассматриваем пути ее внедрения.</span><span class="sxs-lookup"><span data-stu-id="85b98-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="85b98-123">Обо всех готовящихся изменениях вы можете узнать в [Стратегии развития Teams](https://aka.ms/teamsroadmap) и в [посвященном Teams разделе UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="85b98-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

> [!TIP]
> <span data-ttu-id="85b98-124">Чтобы добавить в команду вкладку со ссылкой на существующую страницу сайта SharePoint или на существующую библиотеку документов SharePoint:</span><span class="sxs-lookup"><span data-stu-id="85b98-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="85b98-125">Выберите знак "плюс" рядом с вкладками.</span><span class="sxs-lookup"><span data-stu-id="85b98-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="85b98-126">Выберите **SharePoint для** существующей страницы  сайта SharePoint или библиотеку документов для существующей библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="85b98-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="85b98-127">Выберите соответствующую страницу или библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="85b98-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="85b98-128">У каждого пользователя имеется папка OneDrive **Файлы чатов Microsoft Teams** для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.</span><span class="sxs-lookup"><span data-stu-id="85b98-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Схема папки OneDrive с именем "Файлы чата Microsoft Teams"](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="85b98-130">Обратите внимание, что для общедоступных групп сайт группы SharePoint имеет доступ "Все, кроме внешних пользователей".</span><span class="sxs-lookup"><span data-stu-id="85b98-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="85b98-131">Общедоступные команды не отображаются в Teams для людей, которые не являются членами этой команды.</span><span class="sxs-lookup"><span data-stu-id="85b98-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="85b98-132">Однако они могут получать доступ к контенту на сайте группы SharePoint, используя URL-адрес сайта группы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="85b98-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="85b98-133">Вкладка "Файлы канала"</span><span class="sxs-lookup"><span data-stu-id="85b98-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="85b98-134">Вкладка **Файлы** в Teams напоминает представление документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="85b98-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="85b98-135">На **вкладке** Файлы пользователи могут:</span><span class="sxs-lookup"><span data-stu-id="85b98-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="85b98-136">Дополнительные параметры в **меню Новый** файл.</span><span class="sxs-lookup"><span data-stu-id="85b98-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="85b98-137">Синхронизируйте файлы с локальным диском.</span><span class="sxs-lookup"><span data-stu-id="85b98-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="85b98-138">В меню **Все документы переключение** из представления **"Список"** в представление **"Сжатое"** в представление **"Плитки".**</span><span class="sxs-lookup"><span data-stu-id="85b98-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="85b98-139">Определите файлы, которые требуют внимания или имеют вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="85b98-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="85b98-140">Сразу же проверяет, является ли файл файлом только для чтения или иным.</span><span class="sxs-lookup"><span data-stu-id="85b98-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="85b98-141">И ознакомьтесь с файлами.</span><span class="sxs-lookup"><span data-stu-id="85b98-141">Check out and check in files.</span></span>
- <span data-ttu-id="85b98-142">Закрепить, открепить и изменить порядок сортировки файлов.</span><span class="sxs-lookup"><span data-stu-id="85b98-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="85b98-143">Определение файлов, которым нужны метаданные</span><span class="sxs-lookup"><span data-stu-id="85b98-143">Identify which files need metadata</span></span>
- <span data-ttu-id="85b98-144">Выберите один из множества других параметров фильтрации.</span><span class="sxs-lookup"><span data-stu-id="85b98-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="85b98-145">Группируются файлы на основе заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="85b98-145">Group files based on column headings.</span></span>
- <span data-ttu-id="85b98-146">Изменение параметров столбца (перемещение влево или вправо, скрытие) и ширины столбцов.</span><span class="sxs-lookup"><span data-stu-id="85b98-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="85b98-147">Тип ссылки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="85b98-147">Default link type setting</span></span>

<span data-ttu-id="85b98-148">В SharePoint и OneDrive есть параметр администратора, определяющий тип ссылок по умолчанию для ссылок, созданных для файла.</span><span class="sxs-lookup"><span data-stu-id="85b98-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="85b98-149">В Teams используется тот же подход, что и для параметров SharePoint и OneDrive, за которые администратор устанавливает параметры.</span><span class="sxs-lookup"><span data-stu-id="85b98-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="85b98-150">Дополнительные сведения об этом способе описаны в разделе Изменение типа ссылки по умолчанию при ссылке для [общего доступа.](/sharepoint/change-default-sharing-link)</span><span class="sxs-lookup"><span data-stu-id="85b98-150">More details about this approach are described in [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="85b98-151">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="85b98-151">More information</span></span>

<span data-ttu-id="85b98-152">Дополнительные сведения о том, как SharePoint работает с Teams, см. в [sharePoint и Teams: улучшение совместной работы.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)</span><span class="sxs-lookup"><span data-stu-id="85b98-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="85b98-153">Дополнительные информацию о гостевом опыте в Teams можно найти в этой [публикации.](guest-experience.md)</span><span class="sxs-lookup"><span data-stu-id="85b98-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>