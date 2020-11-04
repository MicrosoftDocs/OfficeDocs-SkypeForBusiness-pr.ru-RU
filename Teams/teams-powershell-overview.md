---
title: Общие сведения о Microsoft Teams PowerShell
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
description: Сведения об использовании элементов управления PowerShell для управления Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852160"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="60203-103">Общие сведения о Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="60203-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="60203-104">Microsoft Teams PowerShell — это набор командлетов, предназначенных для управления группами непосредственно из командной строки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60203-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="60203-105">В стандарте .NET Standard оболочки Teams PowerShell работают на PowerShell 5,1 для Windows, PowerShell 6. x и более новых версий на всех платформах, включая облачную оболочку Azure.</span><span class="sxs-lookup"><span data-stu-id="60203-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="60203-106">Прежде чем приступить к работе с оболочкой PowerShell, необходимо [установить ее](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="60203-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="60203-107">Обнаружены проблемы с PowerShell 7 и Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60203-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="60203-108">Мы рекомендуем использовать PowerShell 5,1, пока проблемы не будут устранены.</span><span class="sxs-lookup"><span data-stu-id="60203-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="60203-109">Оболочек</span><span class="sxs-lookup"><span data-stu-id="60203-109">Releases</span></span>


<span data-ttu-id="60203-110">В [коллекции оболочки PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) для Teams PowerShell доступны два типа выпусков.</span><span class="sxs-lookup"><span data-stu-id="60203-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="60203-111">**Общая доступность (GA)** : командлеты для подготовки к производству, обновленные ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="60203-111">**General Availability (GA)** : Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="60203-112">**Общедоступный предварительный просмотр** : ранний доступ к функциям.</span><span class="sxs-lookup"><span data-stu-id="60203-112">**Public Preview** : Early access to features.</span></span> <span data-ttu-id="60203-113">Может обновляться чаще, чем в GA.</span><span class="sxs-lookup"><span data-stu-id="60203-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="60203-114">Подробная информация о дополнениях и улучшениях для обоих выпусков, читайте в статье сведения [о выпуске оболочки PowerShell для Teams](teams-powershell-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="60203-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="60203-115">Управление группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="60203-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="60203-116">Для полного управления группами вы будете использовать модули Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60203-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="60203-117">[Модуль Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): модуль команд PowerShell Teams включает командлеты для управления группами, чат и каналами.</span><span class="sxs-lookup"><span data-stu-id="60203-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="60203-118">Новейшая [общедоступная версия оболочки PowerShell для Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) поддерживается с помощью соединителя Skype для бизнеса Online, что обеспечивает единый модуль для управления оболочкой PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60203-118">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="60203-119">[Соединитель PowerShell для Skype для бизнеса](https://www.microsoft.com/download/details.aspx?id=39366): теперь соединитель PowerShell для Skype для бизнеса является частью модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60203-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="60203-120">Полный Руководство по управлению группами с использованием этих модулей можно найти в разделе [Управление группами с помощью PowerShell Teams](teams-powershell-managing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="60203-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="60203-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="60203-121">Related topics</span></span>

[<span data-ttu-id="60203-122">Установка оболочки PowerShell для Teams</span><span class="sxs-lookup"><span data-stu-id="60203-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="60203-123">Управление группами с помощью PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="60203-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="60203-124">Заметки о выпуске оболочки PowerShell для Teams</span><span class="sxs-lookup"><span data-stu-id="60203-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="60203-125">Справочник по командлетам Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60203-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="60203-126">Справочник по командлетам Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="60203-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="60203-127">Управление Microsoft Teams с ролями администратора</span><span class="sxs-lookup"><span data-stu-id="60203-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
