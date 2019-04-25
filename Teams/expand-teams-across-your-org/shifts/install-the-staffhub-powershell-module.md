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
description: Узнайте, как установить и подключитесь к модуля Microsoft StaffHub PowerShell.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245918"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="bdce0-103">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="bdce0-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdce0-104">Начиная с 1 октября 2019, Microsoft StaffHub будет из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="bdce0-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="bdce0-105">Мы создаем StaffHub возможностей в группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bdce0-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="bdce0-106">В настоящее время группы включает в себя приложение смены для управление планированием и дополнительные возможности будут развернуты со временем.</span><span class="sxs-lookup"><span data-stu-id="bdce0-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="bdce0-107">StaffHub перестанет работать для всех пользователей на 1 октября 2019.</span><span class="sxs-lookup"><span data-stu-id="bdce0-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="bdce0-108">Кто-то пытается открыть StaffHub отображается сообщение, предлагая загрузить групп.</span><span class="sxs-lookup"><span data-stu-id="bdce0-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="bdce0-109">Для получения дополнительных сведений см [Microsoft StaffHub из эксплуатации](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="bdce0-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="bdce0-110">Для установки и подключитесь к модуля Microsoft StaffHub PowerShell, выполните действия в этой статье.</span><span class="sxs-lookup"><span data-stu-id="bdce0-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="bdce0-111">Вам понадобится управление StaffHub с помощью PowerShell, а также для перемещения ваших команд StaffHub группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bdce0-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="bdce0-112">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="bdce0-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="bdce0-113">Загрузите [модуль StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="bdce0-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="bdce0-114">Откройте Windows PowerShell 3.0 или более поздней версии с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="bdce0-114">Open Windows PowerShell 3.0 or later as an administrator.</span></span> <span data-ttu-id="bdce0-115">Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="bdce0-115">To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="bdce0-116">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="bdce0-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```

4. <span data-ttu-id="bdce0-117">Проверьте путь к папке, в выходные данные и убедитесь в том, что всех папок в поле путь существует на компьютере, прежде чем перейти к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="bdce0-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="bdce0-118">Если папки не указаны, их создания.</span><span class="sxs-lookup"><span data-stu-id="bdce0-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="bdce0-119">Выполните следующие действия, где &lt;путь&gt; — это путь, в выходные данные на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="bdce0-119">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="bdce0-120">Например путь может иметь вид C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="bdce0-120">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="bdce0-121">Подключение к модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="bdce0-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="bdce0-122">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="bdce0-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="bdce0-123">Если появится запрос, войдите в систему как глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="bdce0-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bdce0-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bdce0-124">Related topics</span></span>

- [<span data-ttu-id="bdce0-125">Справочник по Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="bdce0-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="bdce0-126">Перемещение групп Microsoft StaffHub в приложение Shifts в Teams</span><span class="sxs-lookup"><span data-stu-id="bdce0-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
