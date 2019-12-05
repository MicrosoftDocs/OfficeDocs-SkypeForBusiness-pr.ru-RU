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
ms.openlocfilehash: 0b80b82a89fc162e33263c784480f619dcd5cf32
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "37567962"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="53430-103">Установка Microsoft Teams с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="53430-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="53430-104">Просмотрите следующее видео, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="53430-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="53430-105">Чтобы использовать System Center Configuration Manager, групповую политику или любые сторонние механизмы распространения для обширного развертывания, корпорация Майкрософт предоставила файлы MSI (как [32-](https://aka.ms/teams32bitmsi), так и [64-разрядные](https://aka.ms/teams64bitmsi)), которые администраторы могут использовать для массового развертывания Teams для отдельных пользователей или на отдельных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="53430-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="53430-106">Администраторы могут использовать эти файлы для удаленного развертывания Teams, чтобы пользователям не нужно было вручную скачивать приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="53430-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="53430-107">После развертывания Teams автоматически запускается для всех пользователей, выполнивших вход на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="53430-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="53430-108">(Вы можете отключить автоматический запуск после установки приложения.</span><span class="sxs-lookup"><span data-stu-id="53430-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="53430-109">[См. ниже](#disable-auto-launch-for-the-msi-installer).) Мы рекомендуем развертывать пакет на компьютере, чтобы все новые пользователи этого компьютера также могли воспользоваться преимуществами данного развертывания.</span><span class="sxs-lookup"><span data-stu-id="53430-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 

<span data-ttu-id="53430-110">Приложение Teams также может быть включено в развертывание Office 365 профессиональный плюс.</span><span class="sxs-lookup"><span data-stu-id="53430-110">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="53430-111">Дополнительные сведения см. в статье [Развертывание Microsoft Teams с Office 365 профессиональный плюс](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="53430-111">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>
 
> [!Note] 
> <span data-ttu-id="53430-112">Дополнительные сведения о SCCM см. в статье [Знакомство с System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="53430-112">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="53430-113">Процедура развертывания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="53430-113">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="53430-114">Получите последний пакет.</span><span class="sxs-lookup"><span data-stu-id="53430-114">Retrieve the latest package.</span></span>
2. <span data-ttu-id="53430-115">Используйте настройки по умолчанию, заданные MSI.</span><span class="sxs-lookup"><span data-stu-id="53430-115">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="53430-116">По возможности разверните на компьютерах.</span><span class="sxs-lookup"><span data-stu-id="53430-116">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="53430-117">Принцип работы пакета MSI Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="53430-117">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="53430-118">Установка на компьютере</span><span class="sxs-lookup"><span data-stu-id="53430-118">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="53430-119">Инструкции по развертыванию Teams в среде инфраструктуры виртуальных рабочих столов (VDI) см. в разделе [Установка в VDI](#vdi-installation).</span><span class="sxs-lookup"><span data-stu-id="53430-119">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="53430-120">MSI Teams помещает установщик в папку Program Files.</span><span class="sxs-lookup"><span data-stu-id="53430-120">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="53430-121">Когда пользователь входит в новый профиль пользователя Windows, запускается установщик и в папку appdata этого пользователя устанавливается копия приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="53430-121">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="53430-122">Если приложение Teams в папке appdata этого пользователя уже установлено, установщик MSI пропускает данную процедуру для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="53430-122">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="53430-123">Не используйте MSI для развертывания обновлений, так как клиент обновляется автоматически при обнаружении новой версии в службе.</span><span class="sxs-lookup"><span data-stu-id="53430-123">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="53430-124">Чтобы повторно развернуть последний установщик, используйте описанную ниже процедуру для MSI.</span><span class="sxs-lookup"><span data-stu-id="53430-124">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="53430-125">Если вы развертываете более старую версию пакета MSI, клиент обновится автоматически (кроме применения в средах VDI), когда это возможно для пользователя.</span><span class="sxs-lookup"><span data-stu-id="53430-125"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="53430-126">При развертывании очень старой версии MSI активирует обновление приложения до того, как пользователь может начать работу с Teams.</span><span class="sxs-lookup"><span data-stu-id="53430-126">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="53430-127">Мы не рекомендуем изменять расположения установки по умолчанию, так как это может нарушить поток обновления.</span><span class="sxs-lookup"><span data-stu-id="53430-127">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="53430-128">Наличие слишком старой версии не позволит пользователям обращаться к службе.</span><span class="sxs-lookup"><span data-stu-id="53430-128">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="53430-129">Требования к целевому компьютеру</span><span class="sxs-lookup"><span data-stu-id="53430-129">Target computer requirements</span></span>

- <span data-ttu-id="53430-130">.NET Framework версии 4.5 или более поздней</span><span class="sxs-lookup"><span data-stu-id="53430-130">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="53430-131">Windows 7 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="53430-131">Windows 7 or later</span></span>
- <span data-ttu-id="53430-132">3 ГБ места на диске для каждого профиля пользователя (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="53430-132">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="53430-133">Установка в VDI</span><span class="sxs-lookup"><span data-stu-id="53430-133">VDI installation</span></span>

<span data-ttu-id="53430-134">Ниже описан процесс развертывания классического приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="53430-134">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="53430-135">Полное руководство см. в статье [Teams для инфраструктуры виртуальных рабочих столов](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="53430-135">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="53430-136">Скачайте пакет MSI Teams, используя одну из следующих ссылок в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="53430-136">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="53430-137">Рекомендуем использовать 64-разрядную версию для виртуальной машины VDI с 64-разрядной операционной системой.</span><span class="sxs-lookup"><span data-stu-id="53430-137">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="53430-138">32-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="53430-138">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="53430-139">64-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="53430-139">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="53430-140">Выполните следующую команду, чтобы установить MSI на виртуальной машине VDI (или завершить ее обновление).</span><span class="sxs-lookup"><span data-stu-id="53430-140">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="53430-141">При этом приложение Teams устанавливается в папку Program Files.</span><span class="sxs-lookup"><span data-stu-id="53430-141">This installs Teams to Program Files.</span></span> <span data-ttu-id="53430-142">На этом этапе завершается установка "золотого образа".</span><span class="sxs-lookup"><span data-stu-id="53430-142">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="53430-143">Следующий интерактивный сеанс входа запускает Teams и запрашивает учетные данные.</span><span class="sxs-lookup"><span data-stu-id="53430-143">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="53430-144">Обратите внимание, что нельзя отключить автоматический запуск приложения Teams при его установке в VDI с использованием свойства ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="53430-144">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="53430-145">Выполните следующую команду, чтобы удалить MSI с виртуальной машины VDI (или подготовить ее к обновлению).</span><span class="sxs-lookup"><span data-stu-id="53430-145">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="53430-146">В результате приложение Teams удаляется из папки Program Files.</span><span class="sxs-lookup"><span data-stu-id="53430-146">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="53430-147">Процедура очистки и повторного развертывания</span><span class="sxs-lookup"><span data-stu-id="53430-147">Clean up and redeployment procedure</span></span>

<span data-ttu-id="53430-148">Если пользователь удаляет Teams из своего профиля, установщик MSI регистрирует это и перестает устанавливать Teams для этого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="53430-148">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="53430-149">Чтобы повторно развернуть Teams для этого пользователя на конкретном компьютере, откуда он был удален, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="53430-149">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="53430-150">Удалите установленное приложение Teams для каждого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="53430-150">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="53430-151">После удаления рекурсивно удалите каталог, вложенный в %localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="53430-151">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="53430-152">Повторно разверните пакет MSI на этом конкретном компьютере.</span><span class="sxs-lookup"><span data-stu-id="53430-152">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="53430-153">Вы можете использовать наш сценарий для [очистки развертывания Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md), чтобы выполнить шаги 1 и 2 через SCCM.</span><span class="sxs-lookup"><span data-stu-id="53430-153">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="53430-154">Отключение автоматического запуска для установщика MSI</span><span class="sxs-lookup"><span data-stu-id="53430-154">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="53430-155">Поведением по умолчанию для MSI является установка клиента Teams сразу после входа пользователя с последующим запуском Teams.</span><span class="sxs-lookup"><span data-stu-id="53430-155">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="53430-156">Это поведение можно изменить с помощью указанных ниже параметров.</span><span class="sxs-lookup"><span data-stu-id="53430-156">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="53430-157">Когда пользователь входит в Windows, приложение Teams устанавливается с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="53430-157">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="53430-158">Однако клиент Teams не запустится, пока пользователь не запустит его вручную</span><span class="sxs-lookup"><span data-stu-id="53430-158">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="53430-159">Ярлык для запуска Teams добавляется на рабочий стол пользователя</span><span class="sxs-lookup"><span data-stu-id="53430-159">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="53430-160">После запуска вручную приложение Teams будет автоматически запускаться при каждом входе пользователя</span><span class="sxs-lookup"><span data-stu-id="53430-160">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="53430-161">Для 32-разрядной версии</span><span class="sxs-lookup"><span data-stu-id="53430-161">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="53430-162">Для 64-разрядной версии</span><span class="sxs-lookup"><span data-stu-id="53430-162">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="53430-163">Запуск MSI вручную требуется выполнять с повышенными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="53430-163">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="53430-164">Даже если вы запускаете его от имени администратора, не используя повышенные разрешения, установщик не сможет настроить параметр для отключения автозапуска.</span><span class="sxs-lookup"><span data-stu-id="53430-164">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
