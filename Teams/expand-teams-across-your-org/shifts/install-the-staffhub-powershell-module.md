---
title: Установка модуля StaffHub PowerShell
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как установить и подключиться к предварительной версии модуля Microsoft StaffHub PowerShell.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa7f84342b2d4ae16cf801be513e1ae9d6440802
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569214"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="67cc2-103">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="67cc2-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67cc2-104">Вступление в силу 31 декабря 2019 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="67cc2-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="67cc2-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67cc2-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="67cc2-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="67cc2-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="67cc2-107">StaffHub перестанет работать для всех пользователей 31 декабря 2019 г.</span><span class="sxs-lookup"><span data-stu-id="67cc2-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="67cc2-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="67cc2-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="67cc2-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="67cc2-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="67cc2-110">Выполните действия, описанные в этой статье, чтобы установить и подключиться к предварительной версии модуля Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67cc2-110">Use the steps in this article to install and connect to the prerelease version of the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="67cc2-111">Это необходимо для того, чтобы [переместить StaffHub Teams в Teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="67cc2-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="67cc2-112">Установка предварительной версии модуля PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="67cc2-112">Install the prerelease version of the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="67cc2-113">Откройте Windows PowerShell 3,0 или более поздней версии в качестве администратора. Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**, а затем выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="67cc2-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="67cc2-114">Чтобы получить последнюю версию Windows PowerShell, ознакомьтесь со статьей [Установка Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="67cc2-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="67cc2-115">Чтобы установить предварительную версию модуля PowerShell StaffHub, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="67cc2-115">Run the following to install the prerelease version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. <span data-ttu-id="67cc2-116">Вы можете увидеть сообщение с предупреждением:</span><span class="sxs-lookup"><span data-stu-id="67cc2-116">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    <span data-ttu-id="67cc2-117">Введите `Y`текст и нажмите кнопку `Enter`.</span><span class="sxs-lookup"><span data-stu-id="67cc2-117">Type `Y`, and then click `Enter`.</span></span>
 
4. <span data-ttu-id="67cc2-118">Выйдите из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67cc2-118">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="67cc2-119">Подключение к модулю PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="67cc2-119">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="67cc2-120">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="67cc2-120">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="67cc2-121">После появления соответствующего запроса войдите в систему как глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="67cc2-121">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="67cc2-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="67cc2-122">Related topics</span></span>

- [<span data-ttu-id="67cc2-123">Справочник по Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="67cc2-123">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="67cc2-124">Перемещение групп Microsoft StaffHub в приложение "Смены" в Teams</span><span class="sxs-lookup"><span data-stu-id="67cc2-124">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
