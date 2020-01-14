---
title: Установка Microsoft Teams с помощью MSI (через SCCM)
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Администраторы могут использовать MSI Teams для массового развертывания Microsoft Teams для отдельных пользователей или на отдельных компьютерах.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d4a14876f359b2742a04461671ccaefd523ef3f1
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111543"
---
# <a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="472de-103">Установка Microsoft Teams с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="472de-103">Install Microsoft Teams using MSI</span></span>

> [!Tip]
> <span data-ttu-id="472de-104">Просмотрите следующее видео, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="472de-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="472de-105">Чтобы использовать System Center Configuration Manager, групповую политику или любые сторонние механизмы распространения для обширного развертывания, корпорация Майкрософт предоставила файлы MSI (как 32-, так и 64-разрядные), которые администраторы могут использовать для массового развертывания Teams для отдельных пользователей или на отдельных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="472de-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="472de-106">Администраторы могут использовать эти файлы для удаленного развертывания Teams, чтобы пользователям не нужно было вручную скачивать приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="472de-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="472de-107">После развертывания Teams автоматически запускается для всех пользователей, выполнивших вход на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="472de-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="472de-108">(Вы можете отключить автоматический запуск после установки приложения.</span><span class="sxs-lookup"><span data-stu-id="472de-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="472de-109">[См. ниже](#disable-auto-launch-for-the-msi-installer).) Мы рекомендуем развертывать пакет на компьютере, чтобы все новые пользователи этого компьютера также могли воспользоваться преимуществами данного развертывания.</span><span class="sxs-lookup"><span data-stu-id="472de-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="472de-110">Ниже указаны ссылки на MSI-файлы.</span><span class="sxs-lookup"><span data-stu-id="472de-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="472de-111">Компании</span><span class="sxs-lookup"><span data-stu-id="472de-111">Entity</span></span>  |<span data-ttu-id="472de-112">32 бит</span><span class="sxs-lookup"><span data-stu-id="472de-112">32 bit</span></span>      |<span data-ttu-id="472de-113">64 бит</span><span class="sxs-lookup"><span data-stu-id="472de-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="472de-114">Промышленной</span><span class="sxs-lookup"><span data-stu-id="472de-114">Commercial</span></span>     | [<span data-ttu-id="472de-115">32 бит</span><span class="sxs-lookup"><span data-stu-id="472de-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="472de-116">64 бит</span><span class="sxs-lookup"><span data-stu-id="472de-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="472de-117">Федеральный правительственный орган – GCC</span><span class="sxs-lookup"><span data-stu-id="472de-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="472de-118">32 бит</span><span class="sxs-lookup"><span data-stu-id="472de-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="472de-119">64 бит</span><span class="sxs-lookup"><span data-stu-id="472de-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="472de-120">Федеральный правительственный орган – GCC High</span><span class="sxs-lookup"><span data-stu-id="472de-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="472de-121">32 бит</span><span class="sxs-lookup"><span data-stu-id="472de-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="472de-122">64 бит</span><span class="sxs-lookup"><span data-stu-id="472de-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="472de-123">Федеральный правительственный орган – DoD</span><span class="sxs-lookup"><span data-stu-id="472de-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="472de-124">32 бит</span><span class="sxs-lookup"><span data-stu-id="472de-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="472de-125">64 бит</span><span class="sxs-lookup"><span data-stu-id="472de-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="472de-126">Приложение Teams также может быть включено в развертывание Office 365 профессиональный плюс.</span><span class="sxs-lookup"><span data-stu-id="472de-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="472de-127">Дополнительные сведения см. в статье [Развертывание Microsoft Teams с Office 365 профессиональный плюс](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="472de-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="472de-128">Дополнительные сведения о SCCM см. в статье [Знакомство с System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="472de-128">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="472de-129">Процедура развертывания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="472de-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="472de-130">Получите последний пакет.</span><span class="sxs-lookup"><span data-stu-id="472de-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="472de-131">Используйте настройки по умолчанию, заданные MSI.</span><span class="sxs-lookup"><span data-stu-id="472de-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="472de-132">По возможности разверните на компьютерах.</span><span class="sxs-lookup"><span data-stu-id="472de-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="472de-133">Принцип работы пакета MSI Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="472de-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="472de-134">Установка на компьютере</span><span class="sxs-lookup"><span data-stu-id="472de-134">PC installation</span></span>

<span data-ttu-id="472de-135">MSI Teams помещает установщик в папку Program Files.</span><span class="sxs-lookup"><span data-stu-id="472de-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="472de-136">Когда пользователь входит в новый профиль пользователя Windows, запускается установщик и в папку appdata этого пользователя устанавливается копия приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="472de-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="472de-137">Если приложение Teams в папке appdata этого пользователя уже установлено, установщик MSI пропускает данную процедуру для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="472de-137">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="472de-138">Не используйте MSI для развертывания обновлений, так как клиент обновляется автоматически при обнаружении новой версии в службе.</span><span class="sxs-lookup"><span data-stu-id="472de-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="472de-139">Чтобы повторно развернуть последний установщик, используйте описанную ниже процедуру для MSI.</span><span class="sxs-lookup"><span data-stu-id="472de-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="472de-140">Если вы развертываете более старую версию пакета MSI, клиент обновится автоматически (кроме применения в средах VDI), когда это возможно для пользователя.</span><span class="sxs-lookup"><span data-stu-id="472de-140"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="472de-141">При развертывании очень старой версии MSI активирует обновление приложения до того, как пользователь может начать работу с Teams.</span><span class="sxs-lookup"><span data-stu-id="472de-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="472de-142">Мы не рекомендуем изменять расположения установки по умолчанию, так как это может нарушить поток обновления.</span><span class="sxs-lookup"><span data-stu-id="472de-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="472de-143">Наличие слишком старой версии не позволит пользователям обращаться к службе.</span><span class="sxs-lookup"><span data-stu-id="472de-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="472de-144">Требования к целевому компьютеру</span><span class="sxs-lookup"><span data-stu-id="472de-144">Target computer requirements</span></span>

- <span data-ttu-id="472de-145">.NET Framework версии 4.5 или более поздней</span><span class="sxs-lookup"><span data-stu-id="472de-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="472de-146">Windows 7 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="472de-146">Windows 7 or later</span></span>
- <span data-ttu-id="472de-147">Windows Server 2012 R2 или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="472de-147">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="472de-148">3 ГБ места на диске для каждого профиля пользователя (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="472de-148">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="472de-149">Установка в VDI</span><span class="sxs-lookup"><span data-stu-id="472de-149">VDI installation</span></span>

<span data-ttu-id="472de-150">Полное руководство по развертыванию классического приложения Teams в VDI можно найти в разделе [Teams для виртуализованной инфраструктуры для настольных компьютеров](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="472de-150">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="472de-151">Процедура очистки и повторного развертывания</span><span class="sxs-lookup"><span data-stu-id="472de-151">Clean up and redeployment procedure</span></span>

<span data-ttu-id="472de-152">Если пользователь удаляет Teams из своего профиля, установщик MSI регистрирует это и перестает устанавливать Teams для этого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="472de-152">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="472de-153">Чтобы повторно развернуть Teams для этого пользователя на конкретном компьютере, откуда он был удален, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="472de-153">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="472de-154">Удалите установленное приложение Teams для каждого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="472de-154">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="472de-155">После удаления рекурсивно удалите каталог, вложенный в %localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="472de-155">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="472de-156">Повторно разверните пакет MSI на этом конкретном компьютере.</span><span class="sxs-lookup"><span data-stu-id="472de-156">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="472de-157">Вы можете использовать наш сценарий для [очистки развертывания Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md), чтобы выполнить шаги 1 и 2 через SCCM.</span><span class="sxs-lookup"><span data-stu-id="472de-157">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="472de-158">Запрещение автоматического запуска групп после установки</span><span class="sxs-lookup"><span data-stu-id="472de-158">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="472de-159">По умолчанию MSI-файла устанавливают приложение Teams, как только пользователь входит в программу, а затем автоматически запускает Teams.</span><span class="sxs-lookup"><span data-stu-id="472de-159">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="472de-160">Если вы не хотите, чтобы группы автоматически запускались для пользователей после установки, вы можете использовать групповую политику, чтобы настроить параметр политики или отключить автоматический запуск установщика MSI.</span><span class="sxs-lookup"><span data-stu-id="472de-160">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

#### <a name="use-group-policy-recommended"></a><span data-ttu-id="472de-161">Использование групповой политики (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="472de-161">Use Group Policy (recommended)</span></span>

<span data-ttu-id="472de-162">Установите флажок **запретить автоматический запуск Microsoft Teams после установки** групповой политики.</span><span class="sxs-lookup"><span data-stu-id="472de-162">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="472de-163">Этот параметр политики можно найти в группе Конфигурация пользователя Темплатес\микрософт Teams.</span><span class="sxs-lookup"><span data-stu-id="472de-163">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="472de-164">Это рекомендуемый способ, так как вы можете отключить или включить параметр политики в соответствии с потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="472de-164">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="472de-165">Если вы включаете этот параметр политики до установки Teams, команды не запускаются автоматически при входе пользователя в Windows.</span><span class="sxs-lookup"><span data-stu-id="472de-165">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="472de-166">После того как пользователь войдет в Teams в первый раз, команды запускаются автоматически при следующем входе пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="472de-166">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="472de-167">Дополнительные сведения можно найти в статье [Использование групповой политики для предотвращения автоматического запуска групп после установки](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span><span class="sxs-lookup"><span data-stu-id="472de-167">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="472de-168">Отключение автоматического запуска для установщика MSI</span><span class="sxs-lookup"><span data-stu-id="472de-168">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="472de-169">Вы можете отключить автоматический запуск установщика MSI с помощью параметра **Options = "ноаутостарт = true"** , как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="472de-169">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="472de-170">Для 32-разрядной версии</span><span class="sxs-lookup"><span data-stu-id="472de-170">For the 32-bit version</span></span>
```PowerShell
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="472de-171">Для 64-разрядной версии</span><span class="sxs-lookup"><span data-stu-id="472de-171">For the 64-bit version</span></span>
```PowerShell
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="472de-172">Когда пользователь входит в систему Windows, программа Teams устанавливается вместе с MSI и ярлык для запуска Teams добавляется на Рабочий стол пользователя.</span><span class="sxs-lookup"><span data-stu-id="472de-172">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="472de-173">Команды не запускаются до тех пор, пока пользователь не запустит Teams вручную.</span><span class="sxs-lookup"><span data-stu-id="472de-173">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="472de-174">После того как пользователь вручную запускает Teams, группа автоматически запускается каждый раз, когда пользователь входит в систему.</span><span class="sxs-lookup"><span data-stu-id="472de-174">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

> [!Note]
> <span data-ttu-id="472de-175">Запуск MSI вручную требуется выполнять с повышенными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="472de-175">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="472de-176">Даже если вы запускаете учетную запись администратора, не запуская ее с повышенными разрешениями, установщик не сможет настроить параметр отключения автоматического запуска.</span><span class="sxs-lookup"><span data-stu-id="472de-176">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
