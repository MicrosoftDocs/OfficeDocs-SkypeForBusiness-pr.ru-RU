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
description: Узнайте о том, как совместно работать с файлами в Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138383"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="daecb-103">Совместное использование файлов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="daecb-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="daecb-104">В Microsoft Teams пользователи могут предоставлять доступ к содержимому другим пользователям Teams, находящимся за пределами Организации.</span><span class="sxs-lookup"><span data-stu-id="daecb-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="daecb-105">Общий доступ в Teams основывается на параметрах, настроенных в SharePoint и OneDrive, поэтому все, что вы настроили для SharePoint и OneDrive, также будет управлять предоставлением общего доступ в Teams.</span><span class="sxs-lookup"><span data-stu-id="daecb-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="daecb-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="daecb-106">Overview</span></span>

<span data-ttu-id="daecb-107">Пользователи могут предоставлять доступ к файлам из OneDrive, из групп и сайтов, к которым у них есть доступ, и с компьютера.</span><span class="sxs-lookup"><span data-stu-id="daecb-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="daecb-108">Чтобы предоставить общий доступ к файлу, пользователи могут выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="daecb-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="daecb-109">В канале нажмите кнопку **прикрепить** (значок скрепки), выберите пункт **недавние**, **Просмотрите команды и каналы**, **OneDrive**или **загрузить с моего компьютера**, а затем выберите файл, к которому нужно предоставить общий доступ.</span><span class="sxs-lookup"><span data-stu-id="daecb-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="daecb-110">![Снимок экрана, на котором показано, как предоставить общий доступ к файлу из канала](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="daecb-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="daecb-111">В чате нажмите кнопку **прикрепить** (значок скрепки), выберите или **OneDrive** или **Загрузите приложение с компьютера**, а затем выберите файл, к которому нужно предоставить общий доступ.</span><span class="sxs-lookup"><span data-stu-id="daecb-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="daecb-112">![Снимок экрана: демонстрация файла из чата](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="daecb-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="daecb-113">Скопируйте и вставьте ссылку "общий доступ" в поле создания сообщения.</span><span class="sxs-lookup"><span data-stu-id="daecb-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="daecb-114">![Снимок экрана: предварительный просмотр файлов в окне создания сообщения](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="daecb-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="daecb-115">Что необходимо знать о работе с общим доступом к файлам</span><span class="sxs-lookup"><span data-stu-id="daecb-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="daecb-116">Разрешения общих файлов и ссылки для общего доступа</span><span class="sxs-lookup"><span data-stu-id="daecb-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="daecb-117">Когда пользователи совместно применяют файл с помощью обзора в OneDrive или рабочих группах и каналах, всем получателям предоставляется доступ вместе с [разрешением по умолчанию, которое задается на уровне Организации](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="daecb-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="daecb-118">Когда пользователь копирует и вставляет ссылку для совместного доступа, разрешения для этой ссылки соблюдаются и URL-адрес SharePoint сокращается до имени файла.</span><span class="sxs-lookup"><span data-stu-id="daecb-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="daecb-119">Другими словами, Teams использует только имя файла для связи с файлом.</span><span class="sxs-lookup"><span data-stu-id="daecb-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="daecb-120">Когда пользователи совместно используют файлы в Teams, они могут настроить пользователей, которые могут получать доступ к файлу, так же как и в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="daecb-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="daecb-121">Они могут предоставить доступ любому пользователю, сотрудникам Организации, людям с существующим доступом или конкретным людям (которые могут включать людей в чате 1:1, групповой чат или канал).</span><span class="sxs-lookup"><span data-stu-id="daecb-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="daecb-122">При совместном доступе к файлу предварительный просмотр файла доступен в сообщении, а также все действия с файлами, такие как **Open Online**, **download**и **Copy Link**.</span><span class="sxs-lookup"><span data-stu-id="daecb-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="daecb-123">По умолчанию файл открывается в Teams.</span><span class="sxs-lookup"><span data-stu-id="daecb-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="daecb-124">Иногда ссылка для совместного использования может не преобразовываться в предварительный просмотр файла на время отправки сообщения пользователем.</span><span class="sxs-lookup"><span data-stu-id="daecb-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="daecb-125">Файл будет создан системой, но в этом случае ссылка для совместного использования не будет укорочена только на имя файла.</span><span class="sxs-lookup"><span data-stu-id="daecb-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="daecb-126">Когда пользователи совместно используют файл в чате или канале, они получают уведомление о том, что у некоторых или всех получателей нет разрешения на просмотр файла.</span><span class="sxs-lookup"><span data-stu-id="daecb-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="daecb-127">Они могут изменить разрешения для файла, прежде чем поделиться им, щелкнув стрелку рядом с предварительным просмотром файла, который теперь отображается в сообщении.</span><span class="sxs-lookup"><span data-stu-id="daecb-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Снимок экрана с уведомлением о том, что у получателя нет разрешений](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="daecb-129">Копирование ссылки для совместного использования в Teams</span><span class="sxs-lookup"><span data-stu-id="daecb-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="daecb-130">Пользователи могут скопировать ссылку на общий доступ к SharePoint и изменить разрешения на общий доступ, как и в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="daecb-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="daecb-131">Они могут предоставить доступ любому пользователю, сотрудникам Организации, людям с существующим доступом или конкретным людям.</span><span class="sxs-lookup"><span data-stu-id="daecb-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="daecb-132">Разрешение по умолчанию для ссылки совпадает с набором разрешений по умолчанию на уровне Организации, если он не переопределен разрешениями на уровне сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="daecb-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="daecb-133">Настройка общего доступ в OneDrive и SharePoint</span><span class="sxs-lookup"><span data-stu-id="daecb-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="daecb-134">Дополнительные сведения об общем доступе к файлам в OneDrive и SharePoint, в том числе о том, как настроить общий доступ и как включить или отключить общий доступ, можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="daecb-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="daecb-135">[Общие сведения о внешнем общем доступе](https://docs.microsoft.com/sharepoint/external-sharing-overview) : в зависимости от того, к чему они предоставлены, и с кем они поделились.</span><span class="sxs-lookup"><span data-stu-id="daecb-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="daecb-136">[Управление параметрами общего использования](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) : сведения о том, как глобальные и администраторы SharePoint могут изменять параметры общего управления доступом на уровне Организации для SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="daecb-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="daecb-137">[Включение и отключение функции внешнего совместного использования для сайта](https://docs.microsoft.com/sharepoint/change-external-sharing-site) — описывает, как глобальные и администраторы SharePoint могут включать и отключать внешний общий доступ для сайта.</span><span class="sxs-lookup"><span data-stu-id="daecb-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="daecb-138">[Изменение типа ссылки по умолчанию для сайта](https://docs.microsoft.com/sharepoint/change-default-sharing-link) : в этой статье описано, как задать тип ссылки по умолчанию, чтобы сделать его более строгим.</span><span class="sxs-lookup"><span data-stu-id="daecb-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="daecb-139">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="daecb-139">More information</span></span>

- [<span data-ttu-id="daecb-140">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="daecb-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="daecb-141">SharePoint и teams: Улучшенная совместная работа</span><span class="sxs-lookup"><span data-stu-id="daecb-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="daecb-142">Общий доступ к файлам и папкам OneDrive</span><span class="sxs-lookup"><span data-stu-id="daecb-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="daecb-143">Предоставление общего доступа к файлам и папкам SharePoint</span><span class="sxs-lookup"><span data-stu-id="daecb-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
