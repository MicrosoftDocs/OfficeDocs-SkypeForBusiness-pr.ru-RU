---
title: Совместное использование файлов в Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Узнайте о совместном использовании файлов в Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138383"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="344e2-103">Совместное использование файлов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="344e2-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="344e2-104">В Microsoft Teams пользователи могут совместно использовать содержимое с другими пользователями Teams внутри и за пределами их организации.</span><span class="sxs-lookup"><span data-stu-id="344e2-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="344e2-105">Совместное использование в Teams основано на параметрах, настроенных в SharePoint и OneDrive, поэтому все параметры, настроены для SharePoint и OneDrive, также будет управлять совместным доступом в Teams.</span><span class="sxs-lookup"><span data-stu-id="344e2-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="344e2-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="344e2-106">Overview</span></span>

<span data-ttu-id="344e2-107">Пользователи могут представлять общий доступ к файлам из OneDrive, из групп и сайтов, к которым у них есть доступ, а также со своего компьютера.</span><span class="sxs-lookup"><span data-stu-id="344e2-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="344e2-108">Чтобы предоставить общий доступ к файлу, пользователи могут сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="344e2-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="344e2-109">На канале щелкните **Прикрепить** (значок скрепки), выберите **Недавние**, **Загрузить из Teams и каналов**, **OneDrive** или **Загрузить с компьютера** и затем выберите нужный файл.</span><span class="sxs-lookup"><span data-stu-id="344e2-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="344e2-110">![Снимок экрана, показывающий предоставление общего доступа к файлу с канала](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="344e2-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="344e2-111">В чате щелкните **Прикрепить** (значок скрепки), выберите или **OneDrive** или **Загрузить с компьютера** и затем выберите нужный файл.</span><span class="sxs-lookup"><span data-stu-id="344e2-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="344e2-112">![Снимок экрана, показывающий предоставление общего доступа к файлу из чата](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="344e2-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="344e2-113">Скопируйте и вставьте ссылку для совместного использования в поле для создания сообщения.</span><span class="sxs-lookup"><span data-stu-id="344e2-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="344e2-114">![Снимок экрана, показывающий предварительный просмотр файла в поле для создания сообщения](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="344e2-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="344e2-115">Что нужно знать о предоставлении общего доступа к файлу</span><span class="sxs-lookup"><span data-stu-id="344e2-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="344e2-116">Разрешения общих файлов и ссылок для общего доступа</span><span class="sxs-lookup"><span data-stu-id="344e2-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="344e2-117">Когда пользователи предоставляют общий доступ к файлу, загружая его из OneDrive, команд и каналов, всем получателям предоставляется доступ вместе с [разрешением по умолчанию, установленное на уровне организации](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="344e2-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="344e2-118">Когда пользователь копирует и вставляет ссылку для общего доступа, разрешения, настроенные для этой ссылки для общего доступа, и URL-адрес SharePoint сокращается до имени файла.</span><span class="sxs-lookup"><span data-stu-id="344e2-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="344e2-119">Другими словами, Teams использует только имя файла для ссылки на файл.</span><span class="sxs-lookup"><span data-stu-id="344e2-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="344e2-120">Когда пользователи предоставляют общий доступ к файлу из Teams, можно указать, кто может получить доступ к файлу, как и в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="344e2-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="344e2-121">Они могут предоставить доступ любому пользователю, сотрудникам организации, пользователям с доступом или определенным пользователям (которые могут включать люди в чате 1:1, групповом чате или канале).</span><span class="sxs-lookup"><span data-stu-id="344e2-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="344e2-122">При предоставлении общего доступа к файлу в сообщении доступен предварительный просмотр файла, а также все действия с файлом, такие как **Открыть онлайн**, **Загрузить** и **Скопировать ссылку**.</span><span class="sxs-lookup"><span data-stu-id="344e2-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="344e2-123">По умолчанию файл открывается в Teams.</span><span class="sxs-lookup"><span data-stu-id="344e2-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="344e2-124">Иногда ссылка для общего доступа может не преобразоваться в предварительный просмотр файла к моменту отправки сообщения пользователем.</span><span class="sxs-lookup"><span data-stu-id="344e2-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="344e2-125">Предварительный просмотр файла будет создан системой, но в этом сценарии ссылка для общего доступа не будет сокращена до единственного имени файла.</span><span class="sxs-lookup"><span data-stu-id="344e2-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="344e2-126">Когда пользователи предоставляют общий доступ к файлу из чата или канала, они получат уведомление о наличии у некоторых или всех получателей разрешения на просмотр файла.</span><span class="sxs-lookup"><span data-stu-id="344e2-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="344e2-127">Они могут изменить разрешения для файла перед предоставлением общего доступа, щелкнув стрелку рядом с предварительным просмотром файла, который теперь отображается в сообщении.</span><span class="sxs-lookup"><span data-stu-id="344e2-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Снимок экрана с уведомлением об отсутствии у получателей разрешений](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="344e2-129">Копирование ссылки для общего доступа в Teams</span><span class="sxs-lookup"><span data-stu-id="344e2-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="344e2-130">Пользователи могут скопировать ссылку для общего доступа SharePoint и изменить разрешения на предоставление совместного доступа, как и в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="344e2-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="344e2-131">Они могут предоставить доступ любому пользователю, сотрудникам организации, пользователям с доступом или определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="344e2-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="344e2-132">Разрешение по умолчанию для ссылки такое же, как разрешение по умолчанию, установленное на уровне организации, если только разрешения на уровне сайта SharePoint не переопределяют его.</span><span class="sxs-lookup"><span data-stu-id="344e2-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="344e2-133">Настройка общего доступа в OneDrive и SharePoint</span><span class="sxs-lookup"><span data-stu-id="344e2-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="344e2-134">Дополнительные сведения о совместном использовании файлов в OneDrive и SharePoint, в том числе о настройке общего доступа, а также включении и отключении общий доступ, см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="344e2-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="344e2-135">[Обзор внешнего доступа](https://docs.microsoft.com/sharepoint/external-sharing-overview) — описано, что происходит при предоставлении пользователями общего доступа в зависимости от того, кому и к чему он предоставляется.</span><span class="sxs-lookup"><span data-stu-id="344e2-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="344e2-136">[Управление параметрами общего доступа](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) — описано, как глобальные администраторы и администраторы SharePoint могут изменить параметры общего доступа на уровне организации для SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="344e2-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="344e2-137">[Включение и отключение внешнего общего доступа для сайта](https://docs.microsoft.com/sharepoint/change-external-sharing-site) — описано, как глобальные администраторы и администраторы SharePoint могут включать или отключать внешний общий доступ к сайту.</span><span class="sxs-lookup"><span data-stu-id="344e2-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="344e2-138">[Изменение типа ссылки по умолчанию для сайта](https://docs.microsoft.com/sharepoint/change-default-sharing-link) — описано, как установить тип ссылки по умолчанию, чтобы он был более строгим.</span><span class="sxs-lookup"><span data-stu-id="344e2-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="344e2-139">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="344e2-139">More information</span></span>

- [<span data-ttu-id="344e2-140">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="344e2-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="344e2-141">SharePoint и Teams: лучше вместе</span><span class="sxs-lookup"><span data-stu-id="344e2-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="344e2-142">Общий доступ к файлам и папкам OneDrive</span><span class="sxs-lookup"><span data-stu-id="344e2-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="344e2-143">Общий доступ к файлам и папкам SharePoint</span><span class="sxs-lookup"><span data-stu-id="344e2-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
