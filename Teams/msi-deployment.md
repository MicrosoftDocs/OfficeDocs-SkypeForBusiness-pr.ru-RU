---
title: Установка Microsoft Teams с помощью MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Администраторы могут использовать MSI Teams для массового развертывания Microsoft Teams для отдельных пользователей или на отдельных компьютерах.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4983f8089a5d221a29f67ae25dfa6766751a7394
ms.sourcegitcommit: 8a6bf02958436fcdeed336f09079bd3827e2fccb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2018
ms.locfileid: "26282959"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="13b87-103">Установка Microsoft Teams с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="13b87-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="13b87-104">Просмотрите следующие сеанса, чтобы узнать о преимуществах клиент рабочий стол Windows, планировании его и способе развертывания: [Группы Windows Desktop Client](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="13b87-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="13b87-105">Чтобы использовать System Center Configuration Manager или групповой политики или любой механизма распространения сторонних производителей для широкомасштабного развертывания решения, корпорация Майкрософт предоставляет файлов MSI ( [32-разрядная](https://aka.ms/teams32bitmsi) и [64-разрядная версия](https://aka.ms/teams64bitmsi)), администраторы могут использовать для развертывания массового рабочих групп для выбора пользователей или компьютеров.</span><span class="sxs-lookup"><span data-stu-id="13b87-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="13b87-106">Администраторы могут использовать эти файлы для удаленного развертывания групп, чтобы пользователи не имеют для ручной загрузки приложения группы.</span><span class="sxs-lookup"><span data-stu-id="13b87-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="13b87-107">При развертывании команды будет автоматически запуска для всех пользователей, вход на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="13b87-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="13b87-108">(Можно отключить запуск после установки приложения.</span><span class="sxs-lookup"><span data-stu-id="13b87-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="13b87-109">[Ниже приведены](#disable-auto-lanuch-for-the-msi-installer)). Мы рекомендуем развертывание пакета на компьютере, поэтому всех новых пользователей компьютера также выиграют от этого развертывания.</span><span class="sxs-lookup"><span data-stu-id="13b87-109">[See below](#disable-auto-lanuch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="13b87-110">Чтобы узнать больше о SCCM, см [В System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="13b87-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="13b87-111">Процедуры развертывания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="13b87-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="13b87-112">Получите последнюю версию пакета.</span><span class="sxs-lookup"><span data-stu-id="13b87-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="13b87-113">Используйте параметры по умолчанию, предварительно с MSI-файла.</span><span class="sxs-lookup"><span data-stu-id="13b87-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="13b87-114">Развертывания на компьютерах, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="13b87-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="13b87-115">Как работает пакет MSI группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="13b87-115">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="13b87-116">MSI группы будут помещены установщика в Program Files.</span><span class="sxs-lookup"><span data-stu-id="13b87-116">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="13b87-117">Каждый раз, когда пользователь входит в новый профиль пользователя Windows, запускается программа установки и копию приложения группы должны устанавливаться в папку appdata этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="13b87-117">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="13b87-118">Если пользователь уже имеет приложения группы, устанавливается в папку appdata, установщик MSI пропустит процесс для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="13b87-118">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="13b87-119">Не используйте MSI-файла для развертывания обновлений, так как клиент будет автоматически обновления, когда обнаруживает, что новая версия, доступные в службе.</span><span class="sxs-lookup"><span data-stu-id="13b87-119">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="13b87-120">Повторное развертывание последние установщик использовать процесс повторное развертывание MSI описано ниже.</span><span class="sxs-lookup"><span data-stu-id="13b87-120">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="13b87-121">При развертывании более старые версии пакета MSI, клиент будет автоматическое обновление по возможности для пользователя.</span><span class="sxs-lookup"><span data-stu-id="13b87-121"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="13b87-122">Если очень старой версии получает развернут, MSI-файла будет активировано обновления приложения, прежде чем пользователь сможет использовать команды.</span><span class="sxs-lookup"><span data-stu-id="13b87-122">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="13b87-123">Не рекомендуется изменить расположения установки по умолчанию, как это может нарушить этот процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="13b87-123">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="13b87-124">Наличие слишком старой версии со временем блокировать пользователям доступ к службе.</span><span class="sxs-lookup"><span data-stu-id="13b87-124">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="13b87-125">Требования к конечного компьютера</span><span class="sxs-lookup"><span data-stu-id="13b87-125">Target computer requirements</span></span>

- <span data-ttu-id="13b87-126">.NET framework 4.5 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="13b87-126">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="13b87-127">Windows 7 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="13b87-127">Windows 7 or later</span></span>
- <span data-ttu-id="13b87-128">3 ГБ дискового пространства для каждого профиля пользователя (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="13b87-128">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="13b87-129">Очистка и процедура повторного развертывания</span><span class="sxs-lookup"><span data-stu-id="13b87-129">Clean up and redeployment procedure</span></span>
<span data-ttu-id="13b87-130">Если пользователь удаляет команды из своего профиля пользователя, установщик MSI будет отслеживать, что пользователь отменил установку приложения группы и больше не установить групп для этого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="13b87-130">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="13b87-131">Повторное развертывание групп для этого пользователя на конкретном компьютере, где она была удалена, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="13b87-131">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="13b87-132">Удаление группы приложения, установленные для каждого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="13b87-132">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="13b87-133">После удаления, удалите рекурсивно каталога в разделе % localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="13b87-133">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="13b87-134">Повторное развертывание пакета MSI для данного компьютера.</span><span class="sxs-lookup"><span data-stu-id="13b87-134">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="13b87-135">Наш сценарий [развертывания групп Майкрософт Очистка](scripts/Powershell-script-teams-deployment-clean-up.md) можно использовать для выполнения действия 1 и 2 с помощью SCCM.</span><span class="sxs-lookup"><span data-stu-id="13b87-135">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>    
                    
## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="13b87-136">Отключение автоматического запуска для установщика MSI</span><span class="sxs-lookup"><span data-stu-id="13b87-136">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="13b87-137">Поведения MSI-файла по умолчанию — установить клиент группы, как только пользователь входит в и автоматически запускать команды.</span><span class="sxs-lookup"><span data-stu-id="13b87-137">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="13b87-138">Можно изменить это поведение вместе с параметрами под следующим образом:</span><span class="sxs-lookup"><span data-stu-id="13b87-138">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="13b87-139">Когда пользователь входит в в Windows, групп должны устанавливаться с помощью MSI-файла</span><span class="sxs-lookup"><span data-stu-id="13b87-139">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="13b87-140">Тем не менее клиент группы не будет запускаться, пока пользователь начинает группам вручную</span><span class="sxs-lookup"><span data-stu-id="13b87-140">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="13b87-141">Ярлык для запуска групп добавляются на рабочем столе пользователя</span><span class="sxs-lookup"><span data-stu-id="13b87-141">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="13b87-142">После запуска вручную, команды будет автоматический запуск каждый раз, когда пользователь входит в</span><span class="sxs-lookup"><span data-stu-id="13b87-142">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="13b87-143">Для 32-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="13b87-143">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="13b87-144">Для 64-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="13b87-144">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```
> [!Note] 
>  <span data-ttu-id="13b87-145">При выполнении MSI-файла вручную, необходимо запустить его с повышенным уровнем разрешений.</span><span class="sxs-lookup"><span data-stu-id="13b87-145">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="13b87-146">Даже при выполнении его с правами администратора без запуска с повышенным уровнем разрешений, программа установки будет не могут настроить параметр, чтобы отключить автоматический запуск.</span><span class="sxs-lookup"><span data-stu-id="13b87-146">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
