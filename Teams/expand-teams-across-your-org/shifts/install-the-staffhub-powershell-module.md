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
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef80290e6b8a1ce4de834a000148d60b2c5ef89d
ms.sourcegitcommit: 7d5dd650480ca2e55c24ce30408a5058067f6932
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "37775078"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="12d77-103">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="12d77-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12d77-104">Вступление в силу 31 декабря 2019 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="12d77-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="12d77-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="12d77-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="12d77-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="12d77-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="12d77-107">StaffHub перестанет работать для всех пользователей 31 декабря 2019 г.</span><span class="sxs-lookup"><span data-stu-id="12d77-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="12d77-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="12d77-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="12d77-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="12d77-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="12d77-110">Выполните действия, описанные в этой статье, чтобы установить и подключить модуль Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12d77-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="12d77-111">Это необходимо для того, чтобы [переместить StaffHub Teams в Teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="12d77-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="12d77-112">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="12d77-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="12d77-113">Скачайте [модуль PowerShell StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span><span class="sxs-lookup"><span data-stu-id="12d77-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span></span>
2. <span data-ttu-id="12d77-114">Откройте Windows PowerShell 3,0 или более поздней версии в качестве администратора. Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**, а затем выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="12d77-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="12d77-115">Чтобы получить последнюю версию Windows PowerShell, ознакомьтесь со статьей [Установка Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="12d77-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span>
3. <span data-ttu-id="12d77-116">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="12d77-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
4. <span data-ttu-id="12d77-117">Проверьте путь к папке в выходных данных и убедитесь в том, что все папки в пути существуют на компьютере, прежде чем переходить к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="12d77-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="12d77-118">Если папки отсутствуют, создайте их.</span><span class="sxs-lookup"><span data-stu-id="12d77-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="12d77-119">Чтобы разрешить установку модуля PowerShell StaffHub, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="12d77-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
6. <span data-ttu-id="12d77-120">Выполните указанные ниже действия, &lt;где&gt; путь — это путь в выходных данных, начиная с шага 3.</span><span class="sxs-lookup"><span data-stu-id="12d77-120">Run the following, where &lt;path&gt; is the path in the output from step 3.</span></span> <span data-ttu-id="12d77-121">Например, путь может выглядеть так, как C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="12d77-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="12d77-122">Не забудьте выполнить каждую команду отдельно.</span><span class="sxs-lookup"><span data-stu-id="12d77-122">Be sure to run each command separately.</span></span>

    ```
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. <span data-ttu-id="12d77-123">Выйдите из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12d77-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="12d77-124">Откройте Windows PowerShell 3,0 или более поздней версии в качестве глобального администратора, а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="12d77-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub

## Connect to the Microsoft StaffHub PowerShell module

1. Run the following:

    ```
    <span data-ttu-id="12d77-125">Connect-StaffHub</span><span class="sxs-lookup"><span data-stu-id="12d77-125">Connect-StaffHub</span></span>
    ```

2. When you're prompted, log in as a global admin.

## Related topics

- [Microsoft StaffHub PowerShell reference](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Move your Microsoft StaffHub teams to Shifts in Teams](move-staffhub-teams-to-shifts-in-teams.md)
