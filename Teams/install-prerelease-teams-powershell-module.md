---
title: Установка предварительной версии модуля PowerShell Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Выполните указанные ниже действия, чтобы установить предварительную версию модуля PowerShell Teams из коллекции тестов PowerShell.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321772"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="28ca6-103">Установка предварительной версии модуля PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="28ca6-103">Install the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="28ca6-104">В этой статье описано, как установить последнюю предварительную версию модуля PowerShell Teams из [коллекции тестов PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="28ca6-104">This article describes how to install the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="28ca6-105">Вам потребуется предварительная версия модуля PowerShell Teams в сценариях, где командлеты для управления компонентом Teams не поддерживаются в общедоступной версии модуля и доступны только в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="28ca6-105">You'll need the pre-release version of the Teams PowerShell module in scenarios where cmdlets for managing a Teams feature aren't supported in the Generally Available version of the module and are only available in the pre-release version.</span></span>

<span data-ttu-id="28ca6-106">Выполните указанные ниже действия, чтобы установить последнюю предварительную версию модуля PowerShell Teams из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ca6-106">Use these steps to install the latest pre-release version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="28ca6-107">Не устанавливайте модуль PowerShell Teams из коллекции тестов PowerShell рядом с версией модуля из [общедоступной галереи PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="28ca6-107">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the [public PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="28ca6-108">Выполните эти действия, чтобы сначала удалить модуль Teams PowerShell из общедоступной коллекции PowerShell, а затем установить последнюю версию модуля из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ca6-108">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="28ca6-109">Закройте все существующие сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ca6-109">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="28ca6-110">Начните новый экземпляр модуля Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ca6-110">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="28ca6-111">Выполните указанные ниже действия, чтобы удалить модуль PowerShell Teams из общедоступной галереи PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ca6-111">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="28ca6-112">Закройте все существующие сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ca6-112">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="28ca6-113">Запустите модуль Windows PowerShell еще раз, а затем выполните указанные ниже действия, чтобы зарегистрировать библиотеку тестов PowerShell в качестве надежного источника.</span><span class="sxs-lookup"><span data-stu-id="28ca6-113">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="28ca6-114">Выполните указанные ниже действия, чтобы установить последнюю версию модуля PowerShell для Teams из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ca6-114">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="28ca6-115">Выполните указанные ниже действия, чтобы убедиться в том, что новейшая версия модуля Teams PowerShell из коллекции тестов PowerShell успешно установлена.</span><span class="sxs-lookup"><span data-stu-id="28ca6-115">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="28ca6-116">Обновите модуль PowerShell до последней версии из коллекции тестовых команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ca6-116">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="28ca6-117">Если вы уже установили модуль Teams PowerShell из коллекции тестов PowerShell, выполните указанные ниже действия, чтобы обновить его до последней версии.</span><span class="sxs-lookup"><span data-stu-id="28ca6-117">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="28ca6-118">Закройте все существующие сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ca6-118">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="28ca6-119">Начните новый экземпляр модуля Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ca6-119">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="28ca6-120">Выполните указанные ниже действия, чтобы обновить текущую установленную версию модуля PowerShell Teams из коллекции тестов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28ca6-120">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="28ca6-121">Выполните указанные ниже действия, чтобы убедиться в том, что новейшая версия модуля Teams PowerShell из коллекции тестов PowerShell успешно установлена.</span><span class="sxs-lookup"><span data-stu-id="28ca6-121">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="28ca6-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="28ca6-122">Related topics</span></span>

- [<span data-ttu-id="28ca6-123">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="28ca6-123">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
