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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142038"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="33732-103">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="33732-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33732-104">Начиная с 1 октября 2019 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="33732-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="33732-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="33732-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="33732-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="33732-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="33732-107">StaffHub перестанет работать для всех пользователей 1 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="33732-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="33732-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="33732-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="33732-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="33732-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="33732-110">Выполните действия, описанные в этой статье, чтобы установить и подключиться к предварительной версии модуля Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33732-110">Use the steps in this article to install and connect to the prerelease version of the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="33732-111">Это необходимо для того, чтобы [переместить StaffHub Teams в Teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="33732-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="33732-112">Установка предварительной версии модуля PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="33732-112">Install the prerelease version of the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="33732-113">Откройте Windows PowerShell 3,0 или более поздней версии в качестве администратора. Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**, а затем выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="33732-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="33732-114">Чтобы получить последнюю версию Windows PowerShell, ознакомьтесь со статьей [Установка Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="33732-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="33732-115">Чтобы установить предварительную версию модуля PowerShell StaffHub, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="33732-115">Run the following to install the prerelease version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. <span data-ttu-id="33732-116">Вы можете увидеть сообщение с предупреждением:</span><span class="sxs-lookup"><span data-stu-id="33732-116">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    <span data-ttu-id="33732-117">Введите `Y`текст и нажмите кнопку `Enter`.</span><span class="sxs-lookup"><span data-stu-id="33732-117">Type `Y`, and then click `Enter`.</span></span>
 
4. <span data-ttu-id="33732-118">Выйдите из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33732-118">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="33732-119">Подключение к модулю PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="33732-119">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="33732-120">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="33732-120">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="33732-121">После появления соответствующего запроса войдите в систему как глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="33732-121">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="33732-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="33732-122">Related topics</span></span>

- [<span data-ttu-id="33732-123">Справочник по Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="33732-123">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="33732-124">Перемещение групп Microsoft StaffHub в приложение "Смены" в Teams</span><span class="sxs-lookup"><span data-stu-id="33732-124">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
