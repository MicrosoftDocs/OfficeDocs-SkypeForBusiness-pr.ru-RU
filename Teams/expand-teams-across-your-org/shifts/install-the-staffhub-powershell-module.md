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
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464669"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="0bd69-103">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bd69-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bd69-104">Начиная с 1 октября 2019 г. Корпорация Microsoft StaffHub будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="0bd69-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="0bd69-105">Мы создаем возможности StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0bd69-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="0bd69-106">Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="0bd69-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="0bd69-107">StaffHub перестанет работать для всех пользователей 1 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="0bd69-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="0bd69-108">Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп.</span><span class="sxs-lookup"><span data-stu-id="0bd69-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="0bd69-109">Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="0bd69-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="0bd69-110">Выполните действия, описанные в этой статье, чтобы установить и подключить модуль Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bd69-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="0bd69-111">Это необходимо для управления StaffHub с помощью PowerShell, а также для перемещения команд StaffHub в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0bd69-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="0bd69-112">Установка модуля Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bd69-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="0bd69-113">Откройте Windows PowerShell 3,0 или более поздней версии в качестве администратора. Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**, а затем выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="0bd69-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="0bd69-114">Чтобы получить последнюю версию Windows PowerShell, ознакомьтесь со статьей [Установка Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0bd69-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="0bd69-115">Чтобы установить текущую стабильную версию модуля PowerShell StaffHub, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0bd69-115">Run the following to install the current stable version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    <span data-ttu-id="0bd69-116">Эту команду можно выполнить, только если вам нужно установить последнюю версию, которая может быть более стабильной, чем текущая стабильная версия:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span><span class="sxs-lookup"><span data-stu-id="0bd69-116">You can run this command only if you need to install the latest version, which may have more instabilities than the current stable version: `Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span></span>

     > [!NOTE]
     > <span data-ttu-id="0bd69-117">Если при установке последней версии появляется сообщение об ошибке, вы можете выполнить следующие действия:`Install-Module PowershellGet -Force`</span><span class="sxs-lookup"><span data-stu-id="0bd69-117">If you receive an error during the installation of the latest version with more instabilities, you can run: `Install-Module PowershellGet -Force`</span></span>

3. <span data-ttu-id="0bd69-118">Вы можете увидеть сообщение с предупреждением:</span><span class="sxs-lookup"><span data-stu-id="0bd69-118">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

<span data-ttu-id="0bd69-119">Введите `Y` текст и `Enter`нажмите кнопку.</span><span class="sxs-lookup"><span data-stu-id="0bd69-119">Type `Y` and click `Enter`.</span></span>
 
4. <span data-ttu-id="0bd69-120">Выйдите из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bd69-120">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="0bd69-121">Подключение к модулю PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="0bd69-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="0bd69-122">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="0bd69-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="0bd69-123">После появления соответствующего запроса войдите в систему как глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="0bd69-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0bd69-124">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0bd69-124">Related topics</span></span>

- [<span data-ttu-id="0bd69-125">Справочник по Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bd69-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="0bd69-126">Перемещение групп Microsoft StaffHub в приложение "Смены" в Teams</span><span class="sxs-lookup"><span data-stu-id="0bd69-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
