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
ms.openlocfilehash: 6679cd22800307ec95ac242c190d6483411413a9
ms.sourcegitcommit: 109b3869afb5ff1ca4eaf771399d7cda70a43bea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2021
ms.locfileid: "51586548"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="43ae3-103">Установка Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="43ae3-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="43ae3-104">В этой статье объясняется, как установить модуль Microsoft Teams PowerShell с помощью [PowerShellGet.](/powershell/scripting/gallery/installing-psget)</span><span class="sxs-lookup"><span data-stu-id="43ae3-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="43ae3-105">Эти инструкции работают на [платформах Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="43ae3-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="43ae3-106">Требования</span><span class="sxs-lookup"><span data-stu-id="43ae3-106">Requirements</span></span>

<span data-ttu-id="43ae3-107">Для Teams PowerShell требуется PowerShell 5.1 или более высокого уровня на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="43ae3-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="43ae3-108">Установите последнюю [версию PowerShell,](/powershell/scripting/install/installing-powershell) доступную для вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="43ae3-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="43ae3-109">Известные проблемы с PowerShell 7 и Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43ae3-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="43ae3-110">Для лучшей работы рекомендуется использовать PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="43ae3-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="43ae3-111">Установка модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="43ae3-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="43ae3-112">Для лучшей работы используйте как общедоступные, так и общедоступные модули предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="43ae3-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="43ae3-113">Они не предназначены для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="43ae3-113">They're not intended to work together.</span></span>


<span data-ttu-id="43ae3-114">Используйте **командлеты PowerShellGet** для установки модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43ae3-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="43ae3-115">Установка модуля для всех пользователей в системе требует повышенных привилегий.</span><span class="sxs-lookup"><span data-stu-id="43ae3-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="43ae3-116">Начните сеанс PowerShell с использованием команды **"Запуск** от администратора" в Windows или воспользуйтесь командой `sudo` в macOS или Linux:</span><span class="sxs-lookup"><span data-stu-id="43ae3-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="43ae3-117">По умолчанию галерея PowerShell (PSGallery) не настроена как надежный репозиторий **для PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="43ae3-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="43ae3-118">При первом использовании PSGallery вы увидите следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="43ae3-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="43ae3-119">Чтобы **продолжить установку,** **ответьте** "Да" или "Да" для всех.</span><span class="sxs-lookup"><span data-stu-id="43ae3-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="sign-in"></a><span data-ttu-id="43ae3-120">Вход</span><span class="sxs-lookup"><span data-stu-id="43ae3-120">Sign in</span></span>

<span data-ttu-id="43ae3-121">Чтобы приступить к работе с Teams PowerShell, войте учетные данные Azure.</span><span class="sxs-lookup"><span data-stu-id="43ae3-121">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="43ae3-122">Если вы используете последний общедоступный предварительный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="43ae3-122">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="43ae3-123">Вход с использованием MFA и современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="43ae3-123">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="43ae3-124">Если в вашей учетной записи используется многофакторная проверка подлинности, воспользуйтесь действиями, которые необходимо предпринять в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="43ae3-124">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="43ae3-125">Обновление Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="43ae3-125">Update Teams PowerShell</span></span>

<span data-ttu-id="43ae3-126">Чтобы обновить Teams PowerShell, откройте новую командную команду PowerShell с повышенными уровнями и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="43ae3-126">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="43ae3-127">Если teams PowerShell уже импортируется в сеанс PowerShell, обновление модуля будет невозмауэром.</span><span class="sxs-lookup"><span data-stu-id="43ae3-127">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="43ae3-128">Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.</span><span class="sxs-lookup"><span data-stu-id="43ae3-128">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="43ae3-129">Удалить Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="43ae3-129">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="43ae3-130">Чтобы удалить Teams PowerShell, откройте новую командную команду PowerShell с повышенными уровнями и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="43ae3-130">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="43ae3-131">Если teams PowerShell уже импортируется в сеанс PowerShell, при этом не удастся это делать.</span><span class="sxs-lookup"><span data-stu-id="43ae3-131">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="43ae3-132">Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.</span><span class="sxs-lookup"><span data-stu-id="43ae3-132">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="43ae3-133">Установка открытой предварительной версии Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="43ae3-133">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="43ae3-134">Если вы используете общедоступный предварительный выпуск Teams PowerShell, настоятельно рекомендуем сначала удалить соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="43ae3-134">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="43ae3-135">Установка открытого предварительного модуля Teams PowerShell для всех пользователей в системе требует повышенных привилегий.</span><span class="sxs-lookup"><span data-stu-id="43ae3-135">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="43ae3-136">Начните сеанс PowerShell с использованием команды **"Запуск** от администратора" в Windows или используйте команду `sudo` в macOS или Linux.</span><span class="sxs-lookup"><span data-stu-id="43ae3-136">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="43ae3-137">Если вы используете PowerShell 5.1, необходимо предварительно обновить модуль **PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="43ae3-137">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="43ae3-138">После обновления **PowerShellGet** закроете и снова откроете сеанс PowerShell с повышенными уровнями, чтобы убедиться, что будет загружена последняя версия **PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="43ae3-138">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="43ae3-139">Чтобы установить общедоступный предварительный просмотр Teams PowerShell, запустите команду PowerShell ниже.</span><span class="sxs-lookup"><span data-stu-id="43ae3-139">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="43ae3-140">Последнюю предварительную версию можно найти в [коллекции PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) или в PowerShell с помощью команд "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions".</span><span class="sxs-lookup"><span data-stu-id="43ae3-140">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a><span data-ttu-id="43ae3-141">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="43ae3-141">Next Steps</span></span>

<span data-ttu-id="43ae3-142">Теперь вы готовы управлять Teams с помощью Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43ae3-142">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="43ae3-143">Для начала работы см. управление Teams с [помощью Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="43ae3-143">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="43ae3-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="43ae3-144">Related topics</span></span>

[<span data-ttu-id="43ae3-145">Управление Teams с помощью Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="43ae3-145">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="43ae3-146">Заметки о выпуске Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="43ae3-146">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="43ae3-147">Справочник по командлетам Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43ae3-147">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="43ae3-148">Справочник по cmdlet в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="43ae3-148">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)