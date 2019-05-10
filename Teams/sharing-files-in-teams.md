---
title: Совместное использование файлов в группах Майкрософт
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Группами Майкрософт использует параметры из OneDrive и SharePoint для управления общего доступа.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69f4ee036c951197e697c1f74bffb5c079d85bc3
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835077"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="4e0c0-103">Совместное использование файлов в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4e0c0-103">Sharing files in Microsoft Teams</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="4e0c0-104">Файл, общий доступ к функции в группах пользователям, общий доступ к содержимому с другими группами пользователей в своей организации.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-104">The file sharing features in Teams let users share content with other Teams users in their organization.</span></span> <span data-ttu-id="4e0c0-105">Совместное использование в группах основано на параметров, настроенных в SharePoint и OneDrive, поэтому все, что можно настроить для SharePoint и OneDrive будет управлять также совместное использование в группах.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

<span data-ttu-id="4e0c0-106">Совместное использование групп позволяет пользователям выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="4e0c0-106">Teams sharing lets users do the following:</span></span>

- <span data-ttu-id="4e0c0-107">Общий доступ к файлам из службы OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-107">Share files from OneDrive.</span></span>

- <span data-ttu-id="4e0c0-108">Установка разрешений для файлов, которые требуется использовать совместно с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-108">Set permissions for files they want to share with others.</span></span>

- <span data-ttu-id="4e0c0-109">Совместное использование файлов по группам.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-109">Share files across Teams.</span></span>

- <span data-ttu-id="4e0c0-110">Совместное использование файлов из их список недавно использовавшихся файлов (обычно это файлы, пользователи наиболее заинтересованы в общий доступ к).</span><span class="sxs-lookup"><span data-stu-id="4e0c0-110">Share files from their list of recently accessed files (typically, these are the files users are most interested in sharing).</span></span>

- <span data-ttu-id="4e0c0-111">При щелчке по имени файла, чтобы открыть файл всегда оставаться внутри групп.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-111">Stay within Teams when they click a file name to open a file.</span></span>

<span data-ttu-id="4e0c0-112">Группы сокращает длинные URL-адреса SharePoint и веб-браузере URL-адреса, который указывает на файл.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-112">Teams shortens long SharePoint URLS and browser URLS that point to a file.</span></span> <span data-ttu-id="4e0c0-113">Команды использует имя файла для ссылки на файл.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-113">Teams uses just the file name to link to a file.</span></span> <span data-ttu-id="4e0c0-114">Кроме того параметр **получения ссылки** был изменен в **ссылке** во избежание путаницы, пользователи могут иметь о предоставление другим пользователям доступа в файл.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-114">Additionally, the **Get link** option has been changed to **Copy link** to eliminate any confusion that users might have about giving others access to a file.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="4e0c0-115">Настройка общего доступа к в OneDrive и SharePoint</span><span class="sxs-lookup"><span data-stu-id="4e0c0-115">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="4e0c0-116">Дополнительные сведения о совместном использовании файлов в OneDrive и SharePoint в том числе о настройке общего доступа и включить общий доступ и отключает см</span><span class="sxs-lookup"><span data-stu-id="4e0c0-116">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="4e0c0-117">[Обзор внешнего совместного доступа](https://docs.microsoft.com/sharepoint/external-sharing-overview) — описывает, что произойдет, если пользователей работают, в зависимости от того, что они совместно используют и с кем.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-117">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="4e0c0-118">[Включить внешний общий доступ к включено или отключено](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - описывается как глобальный и Администраторы SharePoint могут изменять параметры уровня организации общего доступа для SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-118">[Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="4e0c0-119">Описывает [Изменение внешнего общего доступа для сайта](https://docs.microsoft.com/sharepoint/change-external-sharing-site) — как глобальный и Администраторы SharePoint можно включить внешний общий доступ к включено или отключено для сайта.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-119">[Change external sharing for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="4e0c0-120">[Измените тип связи по умолчанию, когда пользователи получают ссылки для общего доступа к](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - описывается, как задать тип связи по умолчанию, чтобы он стал более жесткие.</span><span class="sxs-lookup"><span data-stu-id="4e0c0-120">[Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it is more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="4e0c0-121">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4e0c0-121">More information</span></span>

- [<span data-ttu-id="4e0c0-122">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e0c0-122">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- <span data-ttu-id="4e0c0-123">[SharePoint и рабочих групп: эффективная совместная работа](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="4e0c0-123">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

- [<span data-ttu-id="4e0c0-124">Совместное использование папки и файлы OneDrive</span><span class="sxs-lookup"><span data-stu-id="4e0c0-124">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="4e0c0-125">Совместное использование файлов SharePoint или папки</span><span class="sxs-lookup"><span data-stu-id="4e0c0-125">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)

