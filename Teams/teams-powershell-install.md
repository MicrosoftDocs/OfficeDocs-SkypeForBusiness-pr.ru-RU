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
ms.openlocfilehash: 966dd62a9917c616c53fc57e13ca468e64acf218
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824940"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="5a693-103">Установка Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a693-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="5a693-104">В этой статье объясняется, как установить модуль Microsoft Teams PowerShellскую версию [с помощью PowerShellGet.](/powershell/scripting/gallery/installing-psget)</span><span class="sxs-lookup"><span data-stu-id="5a693-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="5a693-105">Эти инструкции относятся к платформам Azure Оболочки [Azure,](/azure/cloud-shell/overview)Linux, macOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="5a693-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a693-106">Требования</span><span class="sxs-lookup"><span data-stu-id="5a693-106">Requirements</span></span>

<span data-ttu-id="5a693-107">Для всех платформ для Teams требуется PowerShell 5.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="5a693-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="5a693-108">Установите [последнюю версию PowerShell для](/powershell/scripting/install/installing-powershell) вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="5a693-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="5a693-109">С помощью PowerShell 7 и Teams есть известные проблемы.</span><span class="sxs-lookup"><span data-stu-id="5a693-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="5a693-110">Для оптимальной работы мы рекомендуем использовать PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="5a693-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="5a693-111">Установка модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a693-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="5a693-112">Для оптимальной работы используйте общий доступность (GA) или открытый модули общедоступной версии (не оба варианта).</span><span class="sxs-lookup"><span data-stu-id="5a693-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="5a693-113">Они не должны совместно работать.</span><span class="sxs-lookup"><span data-stu-id="5a693-113">They're not intended to work together.</span></span>


<span data-ttu-id="5a693-114">Установите **модуль Teams PowerShellGet с** помощью командлетов PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="5a693-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="5a693-115">Для установки модуля для всех пользователей в системе требуется повышенные права.</span><span class="sxs-lookup"><span data-stu-id="5a693-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="5a693-116">Запустите сеанс PowerShell с помощью **команды "Запуск от** имени администратора" в Windows или `sudo` используйте команду в macOS или Linux:</span><span class="sxs-lookup"><span data-stu-id="5a693-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="5a693-117">По умолчанию коллекция PowerShell (PSGallery) не настроена как надежный репозиторий **для PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="5a693-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="5a693-118">При первом использовании PSGallery вы увидите следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="5a693-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="5a693-119">Ответы **"Да"** или **"Все" для** продолжения установки.</span><span class="sxs-lookup"><span data-stu-id="5a693-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="5a693-120">Установка общедоступной предварительной версии Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a693-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="5a693-121">Если вы используете общедоступную предварительную версию Teams PowerShell, настоятельно рекомендуем сначала удалить Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="5a693-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="5a693-122">Для установки модуля предварительной версии Teams PowerShell для всех пользователей в системе необходимы повышенные права.</span><span class="sxs-lookup"><span data-stu-id="5a693-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="5a693-123">Запустите сеанс PowerShell, используя **команду "Запуск от** имени администратора" в Windows или `sudo` используйте команду в macOS или Linux.</span><span class="sxs-lookup"><span data-stu-id="5a693-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="5a693-124">Если вы используете PowerShell 5.1, необходимо обновить модуль **PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="5a693-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="5a693-125">После обновления **PowerShellGet**закройте и снова откройте сеанс PowerShellGet, чтобы убедиться, **что PowerShellGet** загружен.</span><span class="sxs-lookup"><span data-stu-id="5a693-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="5a693-126">Чтобы установить общедоступную предварительную версию Teams PowerShell, выполните следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5a693-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="5a693-127">Последнюю предварительную версию [в коллекции PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) или PowerShell можно найти с помощью команды "Найти-модуль MicrosoftTeams -AllowPrerelease"</span><span class="sxs-lookup"><span data-stu-id="5a693-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="5a693-128">Установка соединителя Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5a693-128">Install the Skype for Business Online Connector</span></span>

> [!WARNING]
> <span data-ttu-id="5a693-129">Skype для бизнеса Online Connector в настоящее время входит в общедоступную версию Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a693-129">Skype for Business Online Connector is currently part of Teams PowerShell public preview.</span></span> <span data-ttu-id="5a693-130">После развертывания этой функции в географическом выпуске Teams PowerShell соединитель Skype для бизнеса Online больше не будет доступен.</span><span class="sxs-lookup"><span data-stu-id="5a693-130">Once we've rolled this feature into the GA release of Teams PowerShell, Skype for Business Online Connector will no longer be available.</span></span>

<span data-ttu-id="5a693-131">Скачайте и [установите модуль Skype для бизнеса PowerShell,](https://www.microsoft.com/download/details.aspx?id=39366)а затем выполните в PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5a693-131">Download and install the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), then run the following in PowerShell.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="5a693-132">Вход</span><span class="sxs-lookup"><span data-stu-id="5a693-132">Sign in</span></span>

<span data-ttu-id="5a693-133">Чтобы приступить к работе с Teams PowerShell, войдите с учетными данными Azure.</span><span class="sxs-lookup"><span data-stu-id="5a693-133">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="5a693-134">Если вы используете последнюю предварительную [версию Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5a693-134">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="5a693-135">Обновление Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a693-135">Update Teams PowerShell</span></span>

<span data-ttu-id="5a693-136">Чтобы обновить Teams PowerShell, откройте новую командную строку PowerShell с повышенными возможностями PowerShell и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5a693-136">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="5a693-137">Если Команды PowerShell уже были импортированы в сеанс PowerShell, произойдет сбой.</span><span class="sxs-lookup"><span data-stu-id="5a693-137">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="5a693-138">Закройте PowerShell и снова откройте новый сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a693-138">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="5a693-139">Удаление Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a693-139">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="5a693-140">Чтобы удалить команды PowerShell, откройте новую командную строку PowerShell с повышенными возможностями PowerShell и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5a693-140">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="5a693-141">Если Teams PowerShell уже была импортирована в сеанс PowerShell, удаление модуля завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="5a693-141">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="5a693-142">Закройте PowerShell и снова откройте новый сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a693-142">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5a693-143">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5a693-143">Next Steps</span></span>

<span data-ttu-id="5a693-144">Теперь вы готовы управлять Командами с помощью команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a693-144">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="5a693-145">[Узнайте, как управлять Командами с помощью Teams PowerShell,](teams-powershell-managing-teams.md) чтобы приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="5a693-145">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5a693-146">См. также</span><span class="sxs-lookup"><span data-stu-id="5a693-146">Related topics</span></span>

[<span data-ttu-id="5a693-147">Управление командами с помощью Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a693-147">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="5a693-148">Заметки о выпуске Командной оболочки Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a693-148">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="5a693-149">Справочник по командлету Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a693-149">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="5a693-150">Справочник командлета Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5a693-150">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
