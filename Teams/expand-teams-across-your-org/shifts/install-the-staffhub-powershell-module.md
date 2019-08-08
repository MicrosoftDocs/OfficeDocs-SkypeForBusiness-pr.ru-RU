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
description: Сведения о том, как установить и подключить модуль Microsoft StaffHub PowerShell.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 179276a049a30f1d049521cc3b4db326b988667c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36246183"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="fb543-103">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb543-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb543-104">Начиная с 1 октября 2019 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="fb543-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="fb543-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fb543-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="fb543-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="fb543-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="fb543-107">StaffHub перестанет работать для всех пользователей 1 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="fb543-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="fb543-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="fb543-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="fb543-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="fb543-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="fb543-110">Выполните действия, описанные в этой статье, чтобы установить и подключить модуль Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb543-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="fb543-111">Это необходимо для управления StaffHub с помощью PowerShell, а также для перемещения команд StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fb543-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="fb543-112">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb543-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="fb543-113">Скачайте [модуль PowerShell StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="fb543-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="fb543-114">Откройте Windows PowerShell 3,0 или более поздней версии в качестве администратора. Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**, а затем выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="fb543-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="fb543-115">Чтобы получить последнюю версию Windows PowerShell, ознакомьтесь со статьей [Установка Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="fb543-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
3. <span data-ttu-id="fb543-116">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="fb543-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
    

4. <span data-ttu-id="fb543-117">Проверьте путь к папке в выходных данных и убедитесь в том, что все папки в пути существуют на компьютере, прежде чем переходить к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="fb543-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="fb543-118">Если папки отсутствуют, создайте их.</span><span class="sxs-lookup"><span data-stu-id="fb543-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="fb543-119">Чтобы разрешить установку модуля PowerShell StaffHub, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fb543-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

6. <span data-ttu-id="fb543-120">Выполните указанные ниже действия, &lt;где&gt; путь — это путь в выходных данных, начиная с шага 2.</span><span class="sxs-lookup"><span data-stu-id="fb543-120">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="fb543-121">Например, путь может выглядеть так, как C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="fb543-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="fb543-122">Не забудьте выполнить каждую команду отдельно.</span><span class="sxs-lookup"><span data-stu-id="fb543-122">Be sure to run each command separately.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```
7. <span data-ttu-id="fb543-123">Выйдите из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb543-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="fb543-124">Откройте Windows PowerShell 3,0 или более поздней версии в качестве глобального администратора, а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fb543-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="fb543-125">Подключение к модулю PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="fb543-125">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="fb543-126">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="fb543-126">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="fb543-127">После появления соответствующего запроса войдите в систему как глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="fb543-127">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fb543-128">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fb543-128">Related topics</span></span>

- [<span data-ttu-id="fb543-129">Справочник по Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb543-129">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="fb543-130">Перемещение групп Microsoft StaffHub в приложение "Смены" в Teams</span><span class="sxs-lookup"><span data-stu-id="fb543-130">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
