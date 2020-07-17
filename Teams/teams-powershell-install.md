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
description: Сведения об использовании элементов управления PowerShell для управления Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f42548439c0915eea8405b3c466f7696767f80c
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085885"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="031aa-103">Установка Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="031aa-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="031aa-104">В этой статье объясняется, как установить модуль Microsoft Teams PowerShell с помощью [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="031aa-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="031aa-105">Эти инструкции применимы к [облачной оболочке Azure](/azure/cloud-shell/overview), Linux, macOS и платформам Windows.</span><span class="sxs-lookup"><span data-stu-id="031aa-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="031aa-106">Требования</span><span class="sxs-lookup"><span data-stu-id="031aa-106">Requirements</span></span>

<span data-ttu-id="031aa-107">Для команд PowerShell требуется PowerShell 5,1 или более новой платформы на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="031aa-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="031aa-108">Установите [последнюю версию PowerShell](/powershell/scripting/install/installing-powershell) , доступную для вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="031aa-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="031aa-109">Обнаружены проблемы с PowerShell 7 и Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="031aa-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="031aa-110">Для оптимальной работы мы рекомендуем использовать PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="031aa-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="031aa-111">Установка модуля PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="031aa-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="031aa-112">Для оптимальной работы используйте либо общие, либо общедоступные модули предварительного просмотра, а не оба.</span><span class="sxs-lookup"><span data-stu-id="031aa-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="031aa-113">Они не предназначены для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="031aa-113">They're not intended to work together.</span></span>


<span data-ttu-id="031aa-114">Для установки модуля PowerShell Teams используйте командлеты **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="031aa-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="031aa-115">Установка модуля для всех пользователей системы требует повышенных привилегий.</span><span class="sxs-lookup"><span data-stu-id="031aa-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="031aa-116">Запустите сеанс PowerShell с помощью команды " **Запуск от имени администратора** " в Windows или используйте `sudo` команду на macOS или Linux:</span><span class="sxs-lookup"><span data-stu-id="031aa-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="031aa-117">По умолчанию коллекция PowerShell (PSGallery) не настроена как доверенный репозиторий для **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="031aa-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="031aa-118">При первом использовании PSGallery появляется следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="031aa-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="031aa-119">Ответьте **Да** или **Да,** чтобы продолжить установку.</span><span class="sxs-lookup"><span data-stu-id="031aa-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="031aa-120">Установка общедоступной предварительной версии PowerShell для Teams</span><span class="sxs-lookup"><span data-stu-id="031aa-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="031aa-121">Если вы используете общедоступную версию предварительной версии оболочки Teams PowerShell, настоятельно рекомендуем сначала удалить соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="031aa-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="031aa-122">Для установки общедоступного модуля предварительной версии PowerShell для всех пользователей системы требуются повышенные полномочия.</span><span class="sxs-lookup"><span data-stu-id="031aa-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="031aa-123">Запустите сеанс PowerShell с помощью команды " **Запуск от имени администратора** " в Windows или используйте `sudo` команду на macOS или Linux.</span><span class="sxs-lookup"><span data-stu-id="031aa-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="031aa-124">Если вы используете PowerShell 5,1, необходимо сначала обновить модуль **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="031aa-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="031aa-125">После обновления **PowerShellGet**закройте и снова откройте сеанс PowerShell с повышенными привилегиями, чтобы убедиться в том, что вы загрузили последнюю версию **powershellget** .</span><span class="sxs-lookup"><span data-stu-id="031aa-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="031aa-126">Чтобы установить общедоступную версию оболочки PowerShell для Teams, выполните команду PowerShell ниже.</span><span class="sxs-lookup"><span data-stu-id="031aa-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="031aa-127">Установка соединителя Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="031aa-127">Install the Skype for Business Online Connector</span></span>

> [!WARNING]
> <span data-ttu-id="031aa-128">В настоящее время Skype для бизнеса Online входит в общедоступный предварительный просмотр Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="031aa-128">Skype for Business Online Connector is currently part of Teams PowerShell public preview.</span></span> <span data-ttu-id="031aa-129">После того как мы сделали эту функцию в окончательном выпуске Teams PowerShell, соединитель Skype для бизнеса Online больше не будет доступен.</span><span class="sxs-lookup"><span data-stu-id="031aa-129">Once we've rolled this feature into the GA release of Teams PowerShell, Skype for Business Online Connector will no longer be available.</span></span>

<span data-ttu-id="031aa-130">Скачайте и установите [модуль PowerShell для Skype для бизнеса](https://www.microsoft.com/download/details.aspx?id=39366), а затем выполните следующую команду в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="031aa-130">Download and install the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), then run the following in PowerShell.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="031aa-131">Вход</span><span class="sxs-lookup"><span data-stu-id="031aa-131">Sign in</span></span>

<span data-ttu-id="031aa-132">Для начала работы с Teams PowerShell выполните вход с помощью учетных данных Azure.</span><span class="sxs-lookup"><span data-stu-id="031aa-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="031aa-133">Если вы используете последнюю версию [общедоступного предварительного просмотра для Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="031aa-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="031aa-134">Обновление команд PowerShell</span><span class="sxs-lookup"><span data-stu-id="031aa-134">Update Teams PowerShell</span></span>

<span data-ttu-id="031aa-135">Чтобы обновить Teams PowerShell, откройте новую командную команду PowerShell с повышенными привилегиями и выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="031aa-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="031aa-136">Если командная группа PowerShell уже импортирована в сеанс PowerShell, обновление модуля завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="031aa-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="031aa-137">Закройте PowerShell и повторно откройте новый сеанс PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="031aa-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="031aa-138">Удаление команд оболочки PowerShell</span><span class="sxs-lookup"><span data-stu-id="031aa-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="031aa-139">Чтобы удалить Teams PowerShell, откройте новую командную команду PowerShell с повышенными привилегиями и выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="031aa-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="031aa-140">Если командная группа PowerShell уже импортирована в сеанс PowerShell, то при удалении модуля произойдет сбой.</span><span class="sxs-lookup"><span data-stu-id="031aa-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="031aa-141">Закройте PowerShell и повторно откройте новый сеанс PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="031aa-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="031aa-142">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="031aa-142">Next Steps</span></span>

<span data-ttu-id="031aa-143">Теперь вы можете управлять группами с помощью PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="031aa-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="031aa-144">Чтобы приступить к работе, ознакомьтесь со статьей [Управление группами с помощью PowerShell Teams](teams-powershell-managing-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="031aa-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="031aa-145">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="031aa-145">Related topics</span></span>

[<span data-ttu-id="031aa-146">Управление группами с помощью PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="031aa-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="031aa-147">Заметки о выпуске оболочки PowerShell для Teams</span><span class="sxs-lookup"><span data-stu-id="031aa-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="031aa-148">Справочник по командлетам Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="031aa-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="031aa-149">Справочник по командлетам Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="031aa-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
