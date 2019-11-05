---
title: Совместное использование файлов в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
search.appverid: MET150
description: Microsoft Teams использует параметры из OneDrive и SharePoint для управления демонстрацией.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4114444da68e7a18fe66f7d32e3f64ab98a0b00b
ms.sourcegitcommit: 7920c47eb73e665dad4bf7214b28541d357bce25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2019
ms.locfileid: "37962083"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="c4e23-103">Совместное использование файлов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4e23-103">Sharing files in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-coming-soon-article](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="c4e23-104">Функции общего доступа к файлам в Teams позволяют пользователям предоставлять общий доступ к содержимому другим пользователям Teams в своей организации.</span><span class="sxs-lookup"><span data-stu-id="c4e23-104">The file sharing features in Teams let users share content with other Teams users in their organization.</span></span> <span data-ttu-id="c4e23-105">Общий доступ в Teams основывается на параметрах, настроенных в SharePoint и OneDrive, поэтому все, что вы настроили для SharePoint и OneDrive, также будет управлять предоставлением общего доступ в Teams.</span><span class="sxs-lookup"><span data-stu-id="c4e23-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

![Диаграмма, показывающая совместную работу групп, SharePoint и OneDrive](media/sharing-files-in-teams-image1.png)

<span data-ttu-id="c4e23-107">Совместное использование команд позволяет пользователям выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c4e23-107">Teams sharing lets users do the following:</span></span>

- <span data-ttu-id="c4e23-108">Предоставление общего доступа к файлам в OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c4e23-108">Share files from OneDrive.</span></span>

- <span data-ttu-id="c4e23-109">Настройка разрешений для файлов, к которым они нужны другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="c4e23-109">Set permissions for files they want to share with others.</span></span>

- <span data-ttu-id="c4e23-110">Предоставление общего доступа к файлам в разных командах.</span><span class="sxs-lookup"><span data-stu-id="c4e23-110">Share files across Teams.</span></span>

- <span data-ttu-id="c4e23-111">Предоставление общего доступа к файлам из списка недавно использовавшихся файлов (как правило, это файлы, которые наиболее интересны пользователям).</span><span class="sxs-lookup"><span data-stu-id="c4e23-111">Share files from their list of recently accessed files (typically, these are the files users are most interested in sharing).</span></span>

- <span data-ttu-id="c4e23-112">Оставайтесь в Teams, когда они щелкают имя файла, чтобы открыть файл.</span><span class="sxs-lookup"><span data-stu-id="c4e23-112">Stay within Teams when they click a file name to open a file.</span></span>

<span data-ttu-id="c4e23-113">Teams сокращает длинные URL-адреса SharePoint и URL-адреса браузера, указывающие на файл.</span><span class="sxs-lookup"><span data-stu-id="c4e23-113">Teams shortens long SharePoint URLS and browser URLS that point to a file.</span></span> <span data-ttu-id="c4e23-114">Teams использует только имя файла для связи с файлом.</span><span class="sxs-lookup"><span data-stu-id="c4e23-114">Teams uses just the file name to link to a file.</span></span> <span data-ttu-id="c4e23-115">Кроме того, параметр " **получить ссылку** " изменился для **копирования ссылки** , чтобы избежать путаницы с тем, что пользователи могут получить доступ к файлу другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="c4e23-115">Additionally, the **Get link** option has been changed to **Copy link** to eliminate any confusion that users might have about giving others access to a file.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="c4e23-116">Настройка общего доступ в OneDrive и SharePoint</span><span class="sxs-lookup"><span data-stu-id="c4e23-116">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="c4e23-117">Дополнительные сведения об общем доступе к файлам в OneDrive и SharePoint, в том числе о том, как настроить общий доступ и как включить или отключить общий доступ, можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="c4e23-117">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="c4e23-118">[Общие сведения о внешнем общем доступе](https://docs.microsoft.com/sharepoint/external-sharing-overview) : в зависимости от того, к чему они предоставлены, и с кем они поделились.</span><span class="sxs-lookup"><span data-stu-id="c4e23-118">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="c4e23-119">[Включение и отключение функции внешнего совместного использования](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) : сведения о том, как глобальные и администраторы SharePoint могут изменять параметры общего предоставления на уровне Организации для SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c4e23-119">[Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="c4e23-120">[Изменить внешний общий доступ для сайта](https://docs.microsoft.com/sharepoint/change-external-sharing-site) — описывает, как глобальные и администраторы SharePoint могут включать и отключать внешний общий доступ для сайта.</span><span class="sxs-lookup"><span data-stu-id="c4e23-120">[Change external sharing for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="c4e23-121">[Изменение типа ссылки по умолчанию, когда пользователи получают ссылки для общего доступа](https://docs.microsoft.com/sharepoint/change-default-sharing-link) : в этой статье описано, как задать тип ссылки по умолчанию, чтобы сделать его более строгим.</span><span class="sxs-lookup"><span data-stu-id="c4e23-121">[Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it is more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="c4e23-122">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c4e23-122">More information</span></span>

- [<span data-ttu-id="c4e23-123">Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4e23-123">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- <span data-ttu-id="c4e23-124">[SharePoint и teams: Улучшенная совместная](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)работа.</span><span class="sxs-lookup"><span data-stu-id="c4e23-124">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

- [<span data-ttu-id="c4e23-125">Общий доступ к файлам и папкам OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4e23-125">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="c4e23-126">Предоставление общего доступа к файлам и папкам SharePoint</span><span class="sxs-lookup"><span data-stu-id="c4e23-126">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)

