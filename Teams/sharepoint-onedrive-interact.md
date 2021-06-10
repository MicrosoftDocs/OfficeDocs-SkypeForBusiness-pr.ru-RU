---
title: Взаимодействие SharePoint OneDrive взаимодействия с Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive взаимодействия с Teams; личные хранилища файлов чата & взаимодействия между командой, стандартным каналом и & библиотекой документов.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855958"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a><span data-ttu-id="bcb76-103">Взаимодействие SharePoint OneDrive взаимодействия с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcb76-103">How SharePoint and OneDrive interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="bcb76-104">В следующем сеансе вы узнаете Teams как Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint и OneDrive: основы [Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="bcb76-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="bcb76-105">У каждой группы Microsoft Teams есть сайт группы в SharePoint, а каждый стандартный канал группы получает папку в библиотеке документов сайта группы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bcb76-105">Each team in Microsoft Teams has a team site in SharePoint, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="bcb76-106">Каждый [частный](private-channels.md) канал имеет собственный отдельный SharePoint сайт.</span><span class="sxs-lookup"><span data-stu-id="bcb76-106">Each [private channel](private-channels.md) gets its own, separate SharePoint site.</span></span>

<span data-ttu-id="bcb76-107">Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams.</span><span class="sxs-lookup"><span data-stu-id="bcb76-107">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="bcb76-108">Чтобы узнать, как изменение адреса сайта влияет на SharePoint, см. статью Изменение [адреса сайта.](/sharepoint/change-site-address)</span><span class="sxs-lookup"><span data-stu-id="bcb76-108">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

<span data-ttu-id="bcb76-109">Личные файлы чата хранятся в папке отправитель OneDrive, и разрешения автоматически предоставлены всем участникам в процессе предоставления общего доступа к файлам.</span><span class="sxs-lookup"><span data-stu-id="bcb76-109">Private chat files are stored in the sender's OneDrive folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="bcb76-110">Если пользователям не назначены SharePoint лицензии, у них нет OneDrive хранилища в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bcb76-110">If users aren't assigned SharePoint licenses, they don't have OneDrive storage in Microsoft 365.</span></span> <span data-ttu-id="bcb76-111">Общий доступ к файлам работает в стандартных каналах, но пользователи не смогут делиться файлами в чатах без OneDrive хранения в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bcb76-111">File sharing works in standard channels, but users won't be able to share files in chats without OneDrive storage in Microsoft 365.</span></span>

<span data-ttu-id="bcb76-112">При хранении файлов в SharePoint документа и OneDrive правила соответствия требованиям, настроенные на уровне организации, будут следовать.</span><span class="sxs-lookup"><span data-stu-id="bcb76-112">By storing the files in the SharePoint document library and OneDrive, all compliance rules configured at the organization level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="bcb76-113">Интеграция с SharePoint Server не поддерживается для Teams.</span><span class="sxs-lookup"><span data-stu-id="bcb76-113">Integration with SharePoint Server is not supported for Teams.</span></span>

<span data-ttu-id="bcb76-114">Ниже приводится пример связей между командой, стандартным каналом и библиотекой документов.</span><span class="sxs-lookup"><span data-stu-id="bcb76-114">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="bcb76-115">Для каждой команды создается сайт SharePoint, а также папка по умолчанию **Общие документы**.</span><span class="sxs-lookup"><span data-stu-id="bcb76-115">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="bcb76-116">У каждого стандартного канала, включая канал **Общий** (канал по умолчанию для каждой команды), есть папка в **общие документы.**</span><span class="sxs-lookup"><span data-stu-id="bcb76-116">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Схема папок "Общие документы" В SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="bcb76-118">Стандартные SharePoint сайта и библиотеки документов нельзя заменить другими.</span><span class="sxs-lookup"><span data-stu-id="bcb76-118">The default SharePoint site and document library can't be replaced with a different one.</span></span>

<span data-ttu-id="bcb76-119">У каждого пользователя имеется папка OneDrive **Файлы чатов Microsoft Teams** для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.</span><span class="sxs-lookup"><span data-stu-id="bcb76-119">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Схема папки OneDrive "Файлы чата Microsoft Teams чата"](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="bcb76-121">Обратите внимание, что для общедоступных SharePoint группы предусмотрен доступ "Все, кроме внешних пользователей".</span><span class="sxs-lookup"><span data-stu-id="bcb76-121">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="bcb76-122">Команда не отображается в Teams для людей, которые не являются членами этой команды.</span><span class="sxs-lookup"><span data-stu-id="bcb76-122">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="bcb76-123">Однако они могут получать доступ к контенту SharePoint сайта группы, используя URL-адрес SharePoint сайта группы.</span><span class="sxs-lookup"><span data-stu-id="bcb76-123">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="bcb76-124">Вкладка "Файлы канала"</span><span class="sxs-lookup"><span data-stu-id="bcb76-124">Channel Files tab</span></span>

<span data-ttu-id="bcb76-125">Вкладка **Файлы** в Teams напоминает представление SharePoint документов.</span><span class="sxs-lookup"><span data-stu-id="bcb76-125">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="bcb76-126">На **вкладке** Файлы пользователи могут:</span><span class="sxs-lookup"><span data-stu-id="bcb76-126">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="bcb76-127">Дополнительные параметры в **меню Новый** файл.</span><span class="sxs-lookup"><span data-stu-id="bcb76-127">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="bcb76-128">Синхронизируйте файлы с локальным диском.</span><span class="sxs-lookup"><span data-stu-id="bcb76-128">Sync files to their local drive.</span></span>
- <span data-ttu-id="bcb76-129">В меню **Все документы переключение** из представления **"Список"** в представление **"Сжатое"** в представление **"Плитки".**</span><span class="sxs-lookup"><span data-stu-id="bcb76-129">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="bcb76-130">Определите файлы, которые требуют внимания или имеют вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="bcb76-130">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="bcb76-131">Сразу же проверяет, является ли файл файлом только для чтения или иным.</span><span class="sxs-lookup"><span data-stu-id="bcb76-131">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="bcb76-132">И ознакомьтесь с файлами.</span><span class="sxs-lookup"><span data-stu-id="bcb76-132">Check out and check in files.</span></span>
- <span data-ttu-id="bcb76-133">Закрепить, открепить и изменить порядок сортировки файлов.</span><span class="sxs-lookup"><span data-stu-id="bcb76-133">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="bcb76-134">Определение файлов, которым нужны метаданные</span><span class="sxs-lookup"><span data-stu-id="bcb76-134">Identify which files need metadata</span></span>
- <span data-ttu-id="bcb76-135">Выберите один из множества других параметров фильтрации.</span><span class="sxs-lookup"><span data-stu-id="bcb76-135">Choose from many more filter options.</span></span>
- <span data-ttu-id="bcb76-136">Группируются файлы на основе заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="bcb76-136">Group files based on column headings.</span></span>
- <span data-ttu-id="bcb76-137">Изменение параметров столбца (перемещение влево или вправо, скрытие) и ширины столбцов.</span><span class="sxs-lookup"><span data-stu-id="bcb76-137">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="bcb76-138">Тип ссылки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="bcb76-138">Default link type setting</span></span>

<span data-ttu-id="bcb76-139">Тип ссылки общего доступа, который отображается по умолчанию, если пользователь поделился файлом в центре SharePoint администрирования.</span><span class="sxs-lookup"><span data-stu-id="bcb76-139">The type of sharing link shown by default when a user shared a file is set in the SharePoint admin center.</span></span> <span data-ttu-id="bcb76-140">Сведения см. в разделе [Изменение типа ссылки по умолчанию, когда](/sharepoint/change-default-sharing-link) пользователи получают ссылки для общего доступа.</span><span class="sxs-lookup"><span data-stu-id="bcb76-140">See [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bcb76-141">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bcb76-141">Related topics</span></span>

<span data-ttu-id="bcb76-142">[SharePoint и Teams: лучше вместе](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="bcb76-142">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

[<span data-ttu-id="bcb76-143">Взаимодействие с гостями</span><span class="sxs-lookup"><span data-stu-id="bcb76-143">What the guest experience is like</span></span>](guest-experience.md)