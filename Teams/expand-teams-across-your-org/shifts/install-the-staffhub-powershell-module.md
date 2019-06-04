---
title: Установка модуля StaffHub PowerShell
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как установить и подключить модуль Microsoft StaffHub PowerShell.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6eab331c8d8b2213225ad8c7ee216f9f6ec2b51
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681883"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="3c035-103">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c035-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c035-104">Начиная с 1 октября 2019 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="3c035-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="3c035-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3c035-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="3c035-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="3c035-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="3c035-107">StaffHub перестанет работать для всех пользователей 1 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="3c035-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="3c035-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="3c035-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="3c035-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="3c035-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="3c035-110">Выполните действия, описанные в этой статье, чтобы установить и подключить модуль Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c035-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="3c035-111">Это необходимо для управления StaffHub с помощью PowerShell, а также для перемещения команд StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3c035-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="3c035-112">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c035-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="3c035-113">Скачайте [модуль PowerShell StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="3c035-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="3c035-114">Откройте Windows PowerShell 3,0 или более поздней версии в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="3c035-114">Open Windows PowerShell 3.0 or later as an administrator.</span></span> <span data-ttu-id="3c035-115">Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**, а затем выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="3c035-115">To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="3c035-116">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="3c035-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
    

4. <span data-ttu-id="3c035-117">Проверьте путь к папке в выходных данных и убедитесь в том, что все папки в пути существуют на компьютере, прежде чем переходить к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="3c035-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="3c035-118">Если папки отсутствуют, создайте их.</span><span class="sxs-lookup"><span data-stu-id="3c035-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="3c035-119">Чтобы разрешить установку модуля PowerShell StaffHub, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3c035-119">Run the following to allow for the installation of the StaffHub PowerShell module:</span></span>

```
Set-ExecutionPolicy RemoteSigned
```

6. <span data-ttu-id="3c035-120">Выполните указанные ниже действия, &lt;где&gt; путь — это путь в выходных данных, начиная с шага 2.</span><span class="sxs-lookup"><span data-stu-id="3c035-120">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="3c035-121">Например, путь может выглядеть так, как C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="3c035-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="3c035-122">Подключение к модулю PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="3c035-122">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="3c035-123">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="3c035-123">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="3c035-124">После появления соответствующего запроса войдите в систему как глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="3c035-124">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3c035-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3c035-125">Related topics</span></span>

- [<span data-ttu-id="3c035-126">Справочник по Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c035-126">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="3c035-127">Перемещение групп Microsoft StaffHub в приложение "Смены" в Teams</span><span class="sxs-lookup"><span data-stu-id="3c035-127">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
