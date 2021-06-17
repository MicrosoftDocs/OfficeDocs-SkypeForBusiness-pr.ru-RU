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
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947570"
---
# <a name="install-microsoft-teams-powershell-module"></a><span data-ttu-id="74340-103">Установка Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74340-103">Install Microsoft Teams PowerShell Module</span></span>

<span data-ttu-id="74340-104">В этой статье объясняется, как установить Microsoft Teams PowerShell с помощью коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74340-104">This article explains how to install the Microsoft Teams PowerShell module using PowerShell Gallery.</span></span> <span data-ttu-id="74340-105">Модуль Microsoft Teams PowerShell поддерживается на всех Windows платформах.</span><span class="sxs-lookup"><span data-stu-id="74340-105">The Microsoft Teams PowerShell module is supported on all Windows platforms.</span></span> 

## <a name="requirements"></a><span data-ttu-id="74340-106">Требования</span><span class="sxs-lookup"><span data-stu-id="74340-106">Requirements</span></span>

<span data-ttu-id="74340-107">Microsoft Teams Для модуля PowerShell требуется PowerShell 5.1 или более высокого уровня на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="74340-107">Microsoft Teams PowerShell module requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="74340-108">Установите последнюю [версию PowerShell,](/powershell/scripting/install/installing-powershell)   доступную для вашей операционной системы.</span><span class="sxs-lookup"><span data-stu-id="74340-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> 

<span data-ttu-id="74340-109">Чтобы проверить версию PowerShell, в сеансе PowerShell запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74340-109">To check your PowerShell version, run the following command from within a PowerShell session:</span></span> 

```powershell
$PSVersionTable.PSVersion 
```
<span data-ttu-id="74340-110">Рекомендуется использовать командлет Install-Module для установки Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74340-110">We recommend that you use the  Install-Module cmdlet to install the Microsoft Teams PowerShell module.</span></span> 
 
<span data-ttu-id="74340-111">Если галерея PowerShell (PSGallery) не настроена как надежный репозиторий **для PowerShellGet,** при первом использовании PSGallery вы увидите следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="74340-111">If PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**, the first time you use the PSGallery you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="74340-112">Чтобы **продолжить** **установку, ответьте** Да или Да для всех.</span><span class="sxs-lookup"><span data-stu-id="74340-112">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="installing-using-the-powershellgallery"></a><span data-ttu-id="74340-113">Установка с помощью PowerShellGallery</span><span class="sxs-lookup"><span data-stu-id="74340-113">Installing using the PowerShellGallery</span></span>

<span data-ttu-id="74340-114">Microsoft Teams Модуль PowerShell в настоящее время поддерживается для использования с PowerShell 5.1 в Windows.</span><span class="sxs-lookup"><span data-stu-id="74340-114">Microsoft Teams PowerShell module is currently supported for use with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="74340-115">Чтобы установить модуль, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="74340-115">Follow these steps to install the module:</span></span> 

- <span data-ttu-id="74340-116">Обновим [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="74340-116">Update to [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span></span> <span data-ttu-id="74340-117">Если вы на Windows 10 1607 или более высокой версии, у вас уже установлен PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="74340-117">If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.</span></span> 
- <span data-ttu-id="74340-118">Установите [платформа .NET Framework 4.7.2](/dotnet/framework/install) или более поздней.</span><span class="sxs-lookup"><span data-stu-id="74340-118">Install [.NET Framework 4.7.2](/dotnet/framework/install) or later.</span></span> 
- <span data-ttu-id="74340-119">Чтобы установить последнюю версию PowerShellGet, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74340-119">Run the following command to install the latest PowerShellGet:</span></span>
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- <span data-ttu-id="74340-120">Установите модуль Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74340-120">Install the Teams PowerShell Module.</span></span>

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a><span data-ttu-id="74340-121">Установка в автономном режиме</span><span class="sxs-lookup"><span data-stu-id="74340-121">Offline Installation</span></span> 

<span data-ttu-id="74340-122">В некоторых средах невозможно подключиться к коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74340-122">In some environments, it's not possible to connect to the PowerShell Gallery.</span></span> <span data-ttu-id="74340-123">В таких ситуациях выполните указанные [инструкции по установке вручную.](https://aka.ms/psgallery-manualdownload)</span><span class="sxs-lookup"><span data-stu-id="74340-123">In those situations, please follow these [manual installation steps](https://aka.ms/psgallery-manualdownload).</span></span>  

## <a name="sign-in"></a><span data-ttu-id="74340-124">Вход</span><span class="sxs-lookup"><span data-stu-id="74340-124">Sign in</span></span>

<span data-ttu-id="74340-125">Чтобы начать работу с модулем Microsoft Teams PowerShell, войте вход с помощью учетных данных Azure.</span><span class="sxs-lookup"><span data-stu-id="74340-125">To start working with Microsoft Teams PowerShell module, sign in with your Azure credentials.</span></span>

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a><span data-ttu-id="74340-126">Обновление Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74340-126">Update Teams PowerShell Module</span></span>

<span data-ttu-id="74340-127">Чтобы обновить любой модуль PowerShell, используйте тот же способ, который использовался для установки модуля.</span><span class="sxs-lookup"><span data-stu-id="74340-127">To update any PowerShell module, you should use the same method used to install the module.</span></span> <span data-ttu-id="74340-128">Например, если вы изначально использовали install-Module, для получения последней версии следует использовать [Update-Module.](/powershell/module/powershellget/update-module)</span><span class="sxs-lookup"><span data-stu-id="74340-128">For example, if you originally used Install-Module, then you should use [Update-Module](/powershell/module/powershellget/update-module) to get the latest version.</span></span>  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="74340-129">Если Teams powerShell уже импортируется в сеанс PowerShell, обновление модуля не будет работать.</span><span class="sxs-lookup"><span data-stu-id="74340-129">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="74340-130">Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.</span><span class="sxs-lookup"><span data-stu-id="74340-130">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="74340-131">Удалить Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74340-131">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="74340-132">Чтобы удалить Microsoft Teams PowerShell, откройте новую командную команду PowerShell и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74340-132">To uninstall Microsoft Teams PowerShell, open a new PowerShell command prompt and run the following:</span></span> 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a><span data-ttu-id="74340-133">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="74340-133">Next Steps</span></span> 

<span data-ttu-id="74340-134">Теперь вы можете управлять Microsoft Teams помощью Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74340-134">Now you're ready to manage Microsoft Teams using Microsoft Teams PowerShell.</span></span> <span data-ttu-id="74340-135">См. [Teams управления Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="74340-135">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="74340-136">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="74340-136">Related topics</span></span>

[<span data-ttu-id="74340-137">Управление Teams с помощью Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74340-137">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="74340-138">Teams Заметки о выпуске PowerShell</span><span class="sxs-lookup"><span data-stu-id="74340-138">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="74340-139">Microsoft Teams ссылки на cmdlet</span><span class="sxs-lookup"><span data-stu-id="74340-139">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="74340-140">Skype для бизнеса ссылки на cmdlet</span><span class="sxs-lookup"><span data-stu-id="74340-140">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
