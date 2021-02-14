---
title: Общий доступ к файлам и папок в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
description: Узнайте о том, как в Microsoft Teams можно делиться файлами и папками.
ms.openlocfilehash: 5b6847c42f13701e289b2efaad4a5489351f339b
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795783"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="c7ffb-103">Совместное использование файлов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c7ffb-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="c7ffb-104">В Microsoft Teams пользователи могут совместно использовать содержимое с другими пользователями Teams внутри и за пределами их организации.</span><span class="sxs-lookup"><span data-stu-id="c7ffb-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="c7ffb-105">Общий доступ к файлам и папам в Teams основан на параметрах, настроенных в SharePoint и OneDrive, поэтому все, что вы настроили для SharePoint и OneDrive, повлияет на общий доступ и в Teams.</span><span class="sxs-lookup"><span data-stu-id="c7ffb-105">Sharing files and folders in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will affect sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="c7ffb-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="c7ffb-106">Overview</span></span>

<span data-ttu-id="c7ffb-107">Пользователи могут представлять общий доступ к файлам из OneDrive, из групп и сайтов, к которым у них есть доступ, а также со своего компьютера.</span><span class="sxs-lookup"><span data-stu-id="c7ffb-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="c7ffb-108">Чтобы предоставить общий доступ к файлу, пользователи могут сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="c7ffb-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="c7ffb-p103">На канале щелкните **Прикрепить** (значок скрепки), выберите **Недавние**, **Загрузить из Teams и каналов**, **OneDrive** или **Загрузить с компьютера** и затем выберите нужный файл.</span><span class="sxs-lookup"><span data-stu-id="c7ffb-p103">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share. </span></span><br> 
    <span data-ttu-id="c7ffb-110">![Снимок экрана, показывающий предоставление общего доступа к файлу с канала](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="c7ffb-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="c7ffb-p104">В чате щелкните **Прикрепить** (значок скрепки), выберите или **OneDrive** или **Загрузить с компьютера** и затем выберите нужный файл.</span><span class="sxs-lookup"><span data-stu-id="c7ffb-p104">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share. </span></span><br>
    <span data-ttu-id="c7ffb-112">![Снимок экрана, показывающий предоставление общего доступа к файлу из чата](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="c7ffb-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="c7ffb-113">Скопируйте и вставьте ссылку для совместного использования в поле для создания сообщения.</span><span class="sxs-lookup"><span data-stu-id="c7ffb-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="c7ffb-114">![Снимок экрана, показывающий предварительный просмотр файла в поле для создания сообщения](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="c7ffb-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="c7ffb-115">Разрешения общих файлов и ссылок для общего доступа</span><span class="sxs-lookup"><span data-stu-id="c7ffb-115">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="c7ffb-116">Когда пользователи предоставляют общий доступ к файлу из Teams, можно указать, кто может получить доступ к файлу, как и в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c7ffb-116">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="c7ffb-117">Они могут предоставить доступ любому пользователю, сотрудникам организации, пользователям с доступом или определенным пользователям (которые могут включать люди в чате 1:1, групповом чате или канале).</span><span class="sxs-lookup"><span data-stu-id="c7ffb-117">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="c7ffb-118">При предоставлении общего доступа к файлу в сообщении доступен предварительный просмотр файла, а также все действия с файлом, такие как **Открыть онлайн**, **Загрузить** и **Скопировать ссылку**.</span><span class="sxs-lookup"><span data-stu-id="c7ffb-118">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="c7ffb-119">По умолчанию файл открывается в Teams.</span><span class="sxs-lookup"><span data-stu-id="c7ffb-119">By default, the file opens in Teams.</span></span>

<span data-ttu-id="c7ffb-120">Когда пользователи предоставляют общий доступ к файлу из чата или канала, они получат уведомление о наличии у некоторых или всех получателей разрешения на просмотр файла.</span><span class="sxs-lookup"><span data-stu-id="c7ffb-120">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="c7ffb-121">Они могут изменить разрешения для файла перед предоставлением общего доступа, щелкнув стрелку рядом с предварительным просмотром файла, который теперь отображается в сообщении.</span><span class="sxs-lookup"><span data-stu-id="c7ffb-121">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Снимок экрана с уведомлением об отсутствии у получателей разрешений](media/share-files-permissions.png)

## <a name="related-topics"></a><span data-ttu-id="c7ffb-123">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c7ffb-123">Related topics</span></span>

[<span data-ttu-id="c7ffb-124">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c7ffb-124">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

[<span data-ttu-id="c7ffb-125">Изменение типа ссылки по умолчанию для сайта</span><span class="sxs-lookup"><span data-stu-id="c7ffb-125">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

[<span data-ttu-id="c7ffb-126">Работайте вместе с гостями в команде</span><span class="sxs-lookup"><span data-stu-id="c7ffb-126">Collaborate with guests in a team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)