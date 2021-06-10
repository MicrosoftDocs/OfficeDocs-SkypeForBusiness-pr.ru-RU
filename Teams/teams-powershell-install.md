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
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768347"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="b5036-103">Установка Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5036-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="b5036-104">В этой статье объясняется, как установить модуль Microsoft Teams PowerShell с помощью [PowerShellGet.](/powershell/scripting/gallery/installing-psget)</span><span class="sxs-lookup"><span data-stu-id="b5036-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="b5036-105">Эти инструкции работают на [платформах Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS и Windows Windows.</span><span class="sxs-lookup"><span data-stu-id="b5036-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="b5036-106">Требования</span><span class="sxs-lookup"><span data-stu-id="b5036-106">Requirements</span></span>

<span data-ttu-id="b5036-107">Teams Для работы PowerShell требуется PowerShell 5.1 или более высокого уровня на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="b5036-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="b5036-108">Установите последнюю [версию PowerShell,](/powershell/scripting/install/installing-powershell) доступную для вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b5036-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!NOTE]
> <span data-ttu-id="b5036-109">Для лучшей работы рекомендуется использовать PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="b5036-109">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="b5036-110">Установка модуля Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5036-110">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="b5036-111">Для лучшей работы используйте модули Общего доступа или Общедоступная предварительная версия, но не оба.</span><span class="sxs-lookup"><span data-stu-id="b5036-111">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="b5036-112">Они не предназначены для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="b5036-112">They're not intended to work together.</span></span>


<span data-ttu-id="b5036-113">Установите модуль **PowerShell** с Teams PowerShell с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5036-113">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="b5036-114">Установка модуля для всех пользователей в системе требует повышенных привилегий.</span><span class="sxs-lookup"><span data-stu-id="b5036-114">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="b5036-115">Запустите сеанс PowerShell с **помощью** команды Запуск от Windows или воспользуйтесь `sudo` командой в macOS или Linux:</span><span class="sxs-lookup"><span data-stu-id="b5036-115">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="b5036-116">По умолчанию галерея PowerShell (PSGallery) не настроена как надежный репозиторий **для PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="b5036-116">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="b5036-117">При первом использовании PSGallery вы увидите следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="b5036-117">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="b5036-118">Чтобы **продолжить** **установку, ответьте** Да или Да для всех.</span><span class="sxs-lookup"><span data-stu-id="b5036-118">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="sign-in"></a><span data-ttu-id="b5036-119">Вход</span><span class="sxs-lookup"><span data-stu-id="b5036-119">Sign in</span></span>

<span data-ttu-id="b5036-120">Чтобы приступить к работе с Teams PowerShell, войте учетные данные Azure.</span><span class="sxs-lookup"><span data-stu-id="b5036-120">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="b5036-121">Если вы используете последний общедоступный предварительный [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="b5036-121">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="b5036-122">Вход с использованием MFA и современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b5036-122">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="b5036-123">Если в вашей учетной записи используется многофакторная проверка подлинности, воспользуйтесь действиями из этого раздела.</span><span class="sxs-lookup"><span data-stu-id="b5036-123">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a><span data-ttu-id="b5036-124">Обновление Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5036-124">Update Teams PowerShell</span></span>

<span data-ttu-id="b5036-125">Чтобы обновить Teams PowerShell, откройте новую командную команду PowerShell с повышенными уровнями и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b5036-125">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="b5036-126">Если Teams powerShell уже импортируется в сеанс PowerShell, обновление модуля не будет работать.</span><span class="sxs-lookup"><span data-stu-id="b5036-126">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="b5036-127">Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.</span><span class="sxs-lookup"><span data-stu-id="b5036-127">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="b5036-128">Удалить Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5036-128">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="b5036-129">Чтобы удалить Teams PowerShell, откройте новую командную команду PowerShell с повышенными уровнями и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b5036-129">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="b5036-130">Если Teams PowerShell уже импортируется в сеанс PowerShell, при этом не удастся его выустановить.</span><span class="sxs-lookup"><span data-stu-id="b5036-130">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="b5036-131">Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.</span><span class="sxs-lookup"><span data-stu-id="b5036-131">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="b5036-132">Установка Teams предварительной версии PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5036-132">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="b5036-133">Если вы используете общедоступный предварительный просмотр Teams PowerShell, настоятельно рекомендуем сначала удалить Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="b5036-133">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="b5036-134">Установка общего предварительного Teams PowerShell для всех пользователей в системе требует повышенных привилегий.</span><span class="sxs-lookup"><span data-stu-id="b5036-134">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="b5036-135">Запустите сеанс PowerShell с **помощью** команды Запуск от Windows или воспользуйтесь `sudo` командой в macOS или Linux.</span><span class="sxs-lookup"><span data-stu-id="b5036-135">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="b5036-136">Если вы используете PowerShell 5.1, необходимо предварительно обновить **модуль PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="b5036-136">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="b5036-137">После обновления **PowerShellGet**, закрытия и повторного открытия сеанса PowerShell с повышенными уровнями для обеспечения загрузки последней версии **PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="b5036-137">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="b5036-138">Чтобы установить Teams предварительной версии PowerShell, запустите команду PowerShell ниже.</span><span class="sxs-lookup"><span data-stu-id="b5036-138">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="b5036-139">Последнюю предварительную версию можно найти в [коллекции PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) или в PowerShell с помощью команд "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span><span class="sxs-lookup"><span data-stu-id="b5036-139">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a><span data-ttu-id="b5036-140">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="b5036-140">Next Steps</span></span>

<span data-ttu-id="b5036-141">Теперь вы можете управлять Teams помощью Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5036-141">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="b5036-142">См. [Teams управления Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b5036-142">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5036-143">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b5036-143">Related topics</span></span>

[<span data-ttu-id="b5036-144">Управление Teams с помощью Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5036-144">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="b5036-145">Teams Заметки о выпуске PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5036-145">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="b5036-146">Microsoft Teams ссылки на cmdlet</span><span class="sxs-lookup"><span data-stu-id="b5036-146">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="b5036-147">Skype для бизнеса ссылки на cmdlet</span><span class="sxs-lookup"><span data-stu-id="b5036-147">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
