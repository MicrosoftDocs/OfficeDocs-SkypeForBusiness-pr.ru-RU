---
title: Обзор Microsoft Teams PowerShell
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте, как использовать элементы управления PowerShell для управления Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d191d4d1dbb9c3d3d2f206bce76e9d3ddd7d78d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094119"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="6f163-103">Обзор Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f163-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="6f163-104">Microsoft Teams PowerShell — это набор командлетов для управления Teams непосредственно из командной строки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f163-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="6f163-105">Teams PowerShell, написанный в стандарте .NET, работает в PowerShell 5.1 для Windows, PowerShell 6.x и более высоких версиях на всех платформах, включая облачную оболочку Azure.</span><span class="sxs-lookup"><span data-stu-id="6f163-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="6f163-106">Прежде чем приступить к использованию PowerShell, необходимо [установить его.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="6f163-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="6f163-107">Известные проблемы с PowerShell 7 и Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f163-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="6f163-108">Мы рекомендуем использовать PowerShell 5.1, пока проблемы не будут устранены.</span><span class="sxs-lookup"><span data-stu-id="6f163-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="6f163-109">Выпуски</span><span class="sxs-lookup"><span data-stu-id="6f163-109">Releases</span></span>


<span data-ttu-id="6f163-110">Teams PowerShell доступен в коллекции [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) двух типов.</span><span class="sxs-lookup"><span data-stu-id="6f163-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="6f163-111">**Общая доступность (GA)**: готовые к эксплуатации cmdlets, обновляются ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="6f163-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="6f163-112">**Общедоступный предварительный** просмотр: ранний доступ к функциям.</span><span class="sxs-lookup"><span data-stu-id="6f163-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="6f163-113">Может обновляться чаще, чем обычно.</span><span class="sxs-lookup"><span data-stu-id="6f163-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="6f163-114">Подробные сведения о добавлении и улучшении функций обоих выпусков можно получить в заметках [о выпуске Teams PowerShell.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="6f163-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="6f163-115">Управление Teams с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f163-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="6f163-116">Модули Teams PowerShell используются для полного управления Teams.</span><span class="sxs-lookup"><span data-stu-id="6f163-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="6f163-117">[Модуль Microsoft Teams PowerShell:](https://www.powershellgallery.com/packages/MicrosoftTeams/)модуль Teams PowerShell содержит командлеты для управления командами, чатом и каналами.</span><span class="sxs-lookup"><span data-stu-id="6f163-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="6f163-118">Общедоступный выпуск [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) версии 1.1.6 или более поздней интегрирован со Skype для бизнеса Online Connector, что позволяет использовать один модуль для управления Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f163-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 1.1.6 or later is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="6f163-119">[Соединитель Skype для бизнеса PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): соединитель Skype для бизнеса PowerShell теперь является частью модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f163-119">[Skype for Business PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="6f163-120">Полное руководство по управлению Teams с помощью этих модулей см. в руководстве [Teams с помощью Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6f163-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="6f163-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6f163-121">Related topics</span></span>

[<span data-ttu-id="6f163-122">Установка Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f163-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="6f163-123">Управление Teams с помощью Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f163-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="6f163-124">Заметки о выпуске Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f163-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="6f163-125">Справочник по командлетам Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f163-125">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="6f163-126">Справочник по cmdlet в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6f163-126">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="6f163-127">Управление Microsoft Teams с ролями администратора</span><span class="sxs-lookup"><span data-stu-id="6f163-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)