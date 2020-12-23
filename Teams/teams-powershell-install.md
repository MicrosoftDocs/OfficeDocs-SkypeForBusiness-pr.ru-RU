---
title: Установка Microsoft Teams PowerShell
ms.reviewer: brandber
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
ms.openlocfilehash: cd5b38dd3a43a405794209a9dc7ac4a4468386ef
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662024"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="494c5-103">Установка Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="494c5-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="494c5-104">В этой статье объясняется, как установить модуль Microsoft Teams PowerShell с помощью [PowerShellGet.](/powershell/scripting/gallery/installing-psget)</span><span class="sxs-lookup"><span data-stu-id="494c5-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="494c5-105">Эти инструкции работают на [платформах Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="494c5-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="494c5-106">Требования</span><span class="sxs-lookup"><span data-stu-id="494c5-106">Requirements</span></span>

<span data-ttu-id="494c5-107">Для Teams PowerShell требуется PowerShell 5.1 или более высокого уровня на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="494c5-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="494c5-108">Установите последнюю [версию PowerShell,](/powershell/scripting/install/installing-powershell) доступную для вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="494c5-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="494c5-109">Известные проблемы с PowerShell 7 и Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="494c5-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="494c5-110">Для лучшей работы рекомендуется использовать PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="494c5-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="494c5-111">Установка модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="494c5-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="494c5-112">Для лучшей работы используйте как общедоступные, так и общедоступные модули предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="494c5-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="494c5-113">Они не предназначены для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="494c5-113">They're not intended to work together.</span></span>


<span data-ttu-id="494c5-114">Используйте **командлеты PowerShellGet** для установки модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="494c5-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="494c5-115">Установка модуля для всех пользователей в системе требует повышенных привилегий.</span><span class="sxs-lookup"><span data-stu-id="494c5-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="494c5-116">Начните сеанс PowerShell с администратором **"Запуск"** в Windows или используйте команду `sudo` в macOS или Linux:</span><span class="sxs-lookup"><span data-stu-id="494c5-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="494c5-117">По умолчанию галерея PowerShell (PSGallery) не настроена как надежный репозиторий **для PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="494c5-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="494c5-118">При первом использовании PSGallery вы увидите следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="494c5-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="494c5-119">Чтобы **продолжить установку,** **ответьте** "Да" или "Да" для всех.</span><span class="sxs-lookup"><span data-stu-id="494c5-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="494c5-120">Установка открытой предварительной версии Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="494c5-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="494c5-121">Если вы используете общедоступный предварительный выпуск Teams PowerShell, настоятельно рекомендуем сначала удалить Соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="494c5-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="494c5-122">Установка открытого предварительного модуля Teams PowerShell для всех пользователей в системе требует повышенных привилегий.</span><span class="sxs-lookup"><span data-stu-id="494c5-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="494c5-123">Начните сеанс PowerShell с использованием команды **"Запуск** от администратора" в Windows или используйте команду `sudo` в macOS или Linux.</span><span class="sxs-lookup"><span data-stu-id="494c5-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="494c5-124">Если вы используете PowerShell 5.1, необходимо предварительно обновить модуль **PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="494c5-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="494c5-125">После обновления **PowerShellGet** закроете и снова откроете сеанс PowerShell с повышенными уровнями, чтобы убедиться, что будет загружена последняя версия **PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="494c5-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="494c5-126">Чтобы установить общедоступный предварительный просмотр Teams PowerShell, запустите команду PowerShell ниже.</span><span class="sxs-lookup"><span data-stu-id="494c5-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="494c5-127">Последнюю предварительную версию можно найти в [коллекции PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) или в PowerShell с помощью команд "Find-Module MicrosoftTeams -AllowPrerelease"</span><span class="sxs-lookup"><span data-stu-id="494c5-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="494c5-128">Установка соединителя Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="494c5-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="494c5-129">Соединитель Skype для бизнеса Online сейчас является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="494c5-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="494c5-130">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="494c5-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="494c5-131">Вход</span><span class="sxs-lookup"><span data-stu-id="494c5-131">Sign in</span></span>

<span data-ttu-id="494c5-132">Чтобы приступить к работе с Teams PowerShell, войте учетные данные Azure.</span><span class="sxs-lookup"><span data-stu-id="494c5-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="494c5-133">Если вы используете последний общедоступный предварительный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="494c5-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="494c5-134">Обновление Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="494c5-134">Update Teams PowerShell</span></span>

<span data-ttu-id="494c5-135">Чтобы обновить Teams PowerShell, откройте новую командную команду PowerShell с повышенными уровнями и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="494c5-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="494c5-136">Если teams PowerShell уже импортируется в сеанс PowerShell, обновление модуля не будет работать.</span><span class="sxs-lookup"><span data-stu-id="494c5-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="494c5-137">Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.</span><span class="sxs-lookup"><span data-stu-id="494c5-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="494c5-138">Удалить Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="494c5-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="494c5-139">Чтобы удалить Teams PowerShell, откройте новую командную команду PowerShell с повышенными уровнями и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="494c5-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="494c5-140">Если teams PowerShell уже импортируется в сеанс PowerShell, при этом не удастся это делать.</span><span class="sxs-lookup"><span data-stu-id="494c5-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="494c5-141">Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.</span><span class="sxs-lookup"><span data-stu-id="494c5-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="494c5-142">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="494c5-142">Next Steps</span></span>

<span data-ttu-id="494c5-143">Теперь вы готовы управлять Teams с помощью Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="494c5-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="494c5-144">Для начала работы см. управление Teams с [помощью Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="494c5-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="494c5-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="494c5-145">Related topics</span></span>

[<span data-ttu-id="494c5-146">Управление Teams с помощью Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="494c5-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="494c5-147">Заметки о выпуске Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="494c5-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="494c5-148">Справочник по командлетам Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="494c5-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="494c5-149">Справочник по cmdlet в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="494c5-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
