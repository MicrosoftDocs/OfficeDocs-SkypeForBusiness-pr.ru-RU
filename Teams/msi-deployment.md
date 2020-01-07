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
ms.openlocfilehash: a621c4e1cfcf9e485b68fd96a76d9179cef84a48
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952602"
---
# <a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="9f0f7-103">Установка Microsoft Teams с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="9f0f7-103">Install Microsoft Teams using MSI</span></span>

> [!Tip]
> <span data-ttu-id="9f0f7-104">Просмотрите следующее видео, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="9f0f7-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="9f0f7-105">Чтобы использовать System Center Configuration Manager, групповую политику или любые сторонние механизмы распространения для обширного развертывания, корпорация Майкрософт предоставила файлы MSI (как 32-, так и 64-разрядные), которые администраторы могут использовать для массового развертывания Teams для отдельных пользователей или на отдельных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="9f0f7-106">Администраторы могут использовать эти файлы для удаленного развертывания Teams, чтобы пользователям не нужно было вручную скачивать приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="9f0f7-107">После развертывания Teams автоматически запускается для всех пользователей, выполнивших вход на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="9f0f7-108">(Вы можете отключить автоматический запуск после установки приложения.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="9f0f7-109">[См. ниже](#disable-auto-launch-for-the-msi-installer).) Мы рекомендуем развертывать пакет на компьютере, чтобы все новые пользователи этого компьютера также могли воспользоваться преимуществами данного развертывания.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="9f0f7-110">Ниже указаны ссылки на MSI-файлы.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="9f0f7-111">Компании</span><span class="sxs-lookup"><span data-stu-id="9f0f7-111">Entity</span></span>  |<span data-ttu-id="9f0f7-112">32 бит</span><span class="sxs-lookup"><span data-stu-id="9f0f7-112">32 bit</span></span>      |<span data-ttu-id="9f0f7-113">64 бит</span><span class="sxs-lookup"><span data-stu-id="9f0f7-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="9f0f7-114">Промышленной</span><span class="sxs-lookup"><span data-stu-id="9f0f7-114">Commercial</span></span>     | [<span data-ttu-id="9f0f7-115">32 бит</span><span class="sxs-lookup"><span data-stu-id="9f0f7-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="9f0f7-116">64 бит</span><span class="sxs-lookup"><span data-stu-id="9f0f7-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="9f0f7-117">Федеральный правительственный орган – GCC</span><span class="sxs-lookup"><span data-stu-id="9f0f7-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="9f0f7-118">32 бит</span><span class="sxs-lookup"><span data-stu-id="9f0f7-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="9f0f7-119">64 бит</span><span class="sxs-lookup"><span data-stu-id="9f0f7-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="9f0f7-120">Федеральный правительственный орган – GCC High</span><span class="sxs-lookup"><span data-stu-id="9f0f7-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="9f0f7-121">32 бит</span><span class="sxs-lookup"><span data-stu-id="9f0f7-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="9f0f7-122">64 бит</span><span class="sxs-lookup"><span data-stu-id="9f0f7-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="9f0f7-123">Федеральный правительственный орган – DoD</span><span class="sxs-lookup"><span data-stu-id="9f0f7-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="9f0f7-124">32 бит</span><span class="sxs-lookup"><span data-stu-id="9f0f7-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="9f0f7-125">64 бит</span><span class="sxs-lookup"><span data-stu-id="9f0f7-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="9f0f7-126">Приложение Teams также может быть включено в развертывание Office 365 профессиональный плюс.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="9f0f7-127">Дополнительные сведения см. в статье [Развертывание Microsoft Teams с Office 365 профессиональный плюс](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="9f0f7-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="9f0f7-128">Дополнительные сведения о SCCM см. в статье [Знакомство с System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="9f0f7-128">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="9f0f7-129">Процедура развертывания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="9f0f7-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="9f0f7-130">Получите последний пакет.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="9f0f7-131">Используйте настройки по умолчанию, заданные MSI.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="9f0f7-132">По возможности разверните на компьютерах.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="9f0f7-133">Принцип работы пакета MSI Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f0f7-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="9f0f7-134">Установка на компьютере</span><span class="sxs-lookup"><span data-stu-id="9f0f7-134">PC installation</span></span>

<span data-ttu-id="9f0f7-135">MSI Teams помещает установщик в папку Program Files.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="9f0f7-136">Когда пользователь входит в новый профиль пользователя Windows, запускается установщик и в папку appdata этого пользователя устанавливается копия приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="9f0f7-137">Если приложение Teams в папке appdata этого пользователя уже установлено, установщик MSI пропускает данную процедуру для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-137">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="9f0f7-138">Не используйте MSI для развертывания обновлений, так как клиент обновляется автоматически при обнаружении новой версии в службе.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="9f0f7-139">Чтобы повторно развернуть последний установщик, используйте описанную ниже процедуру для MSI.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="9f0f7-140">Если вы развертываете более старую версию пакета MSI, клиент обновится автоматически (кроме применения в средах VDI), когда это возможно для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-140"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="9f0f7-141">При развертывании очень старой версии MSI активирует обновление приложения до того, как пользователь может начать работу с Teams.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="9f0f7-142">Мы не рекомендуем изменять расположения установки по умолчанию, так как это может нарушить поток обновления.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="9f0f7-143">Наличие слишком старой версии не позволит пользователям обращаться к службе.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="9f0f7-144">Требования к целевому компьютеру</span><span class="sxs-lookup"><span data-stu-id="9f0f7-144">Target computer requirements</span></span>

- <span data-ttu-id="9f0f7-145">.NET Framework версии 4.5 или более поздней</span><span class="sxs-lookup"><span data-stu-id="9f0f7-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="9f0f7-146">Windows 7 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="9f0f7-146">Windows 7 or later</span></span>
- <span data-ttu-id="9f0f7-147">3 ГБ места на диске для каждого профиля пользователя (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="9f0f7-147">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="9f0f7-148">Установка в VDI</span><span class="sxs-lookup"><span data-stu-id="9f0f7-148">VDI installation</span></span>

<span data-ttu-id="9f0f7-149">Полное руководство по развертыванию классического приложения Teams в VDI можно найти в разделе [Teams для виртуализованной инфраструктуры для настольных компьютеров](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="9f0f7-149">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="9f0f7-150">Процедура очистки и повторного развертывания</span><span class="sxs-lookup"><span data-stu-id="9f0f7-150">Clean up and redeployment procedure</span></span>

<span data-ttu-id="9f0f7-151">Если пользователь удаляет Teams из своего профиля, установщик MSI регистрирует это и перестает устанавливать Teams для этого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-151">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="9f0f7-152">Чтобы повторно развернуть Teams для этого пользователя на конкретном компьютере, откуда он был удален, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="9f0f7-152">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="9f0f7-153">Удалите установленное приложение Teams для каждого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-153">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="9f0f7-154">После удаления рекурсивно удалите каталог, вложенный в %localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-154">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="9f0f7-155">Повторно разверните пакет MSI на этом конкретном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-155">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="9f0f7-156">Вы можете использовать наш сценарий для [очистки развертывания Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md), чтобы выполнить шаги 1 и 2 через SCCM.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-156">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="9f0f7-157">Отключение автоматического запуска для установщика MSI</span><span class="sxs-lookup"><span data-stu-id="9f0f7-157">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="9f0f7-158">Поведением по умолчанию для MSI является установка клиента Teams сразу после входа пользователя с последующим запуском Teams.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-158">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="9f0f7-159">Это поведение можно изменить с помощью указанных ниже параметров.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-159">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="9f0f7-160">Когда пользователь входит в Windows, приложение Teams устанавливается с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="9f0f7-160">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="9f0f7-161">Однако клиент Teams не запустится, пока пользователь не запустит его вручную</span><span class="sxs-lookup"><span data-stu-id="9f0f7-161">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="9f0f7-162">Ярлык для запуска Teams добавляется на рабочий стол пользователя</span><span class="sxs-lookup"><span data-stu-id="9f0f7-162">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="9f0f7-163">После запуска вручную приложение Teams будет автоматически запускаться при каждом входе пользователя</span><span class="sxs-lookup"><span data-stu-id="9f0f7-163">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="9f0f7-164">Для 32-разрядной версии</span><span class="sxs-lookup"><span data-stu-id="9f0f7-164">For the 32-bit version</span></span>
```PowerShell
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="9f0f7-165">Для 64-разрядной версии</span><span class="sxs-lookup"><span data-stu-id="9f0f7-165">For the 64-bit version</span></span>
```PowerShell
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
> <span data-ttu-id="9f0f7-166">Запуск MSI вручную требуется выполнять с повышенными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-166">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="9f0f7-167">Даже если вы запускаете его от имени администратора, не используя повышенные разрешения, установщик не сможет настроить параметр для отключения автозапуска.</span><span class="sxs-lookup"><span data-stu-id="9f0f7-167">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
