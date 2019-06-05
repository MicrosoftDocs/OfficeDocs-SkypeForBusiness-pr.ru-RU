---
title: Установка Microsoft Teams с помощью MSI (через SCCM)
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Администраторы могут использовать MSI Teams для массового развертывания Microsoft Teams для отдельных пользователей или на отдельных компьютерах.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e35c3d62ee43e3b3123993e29c17a8ec1e8f94f7
ms.sourcegitcommit: c4827e9124ebfb62d8e5c93dc2652d24988bd811
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "34694731"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="2ba3a-103">Установка Microsoft Teams с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="2ba3a-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="2ba3a-104">Просмотрите следующий сеанс, чтобы узнать о преимуществах настольного клиента Windows, о том, как его спланировать и развертывание: клиент Teams для настольных [систем Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="2ba3a-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="2ba3a-105">Для использования System Center Configuration Manager или групповой политики или любых сторонних механизмов распространения для широкого развертывания корпорация Майкрософт предоставила MSI-файлы (как [32](https://aka.ms/teams32bitmsi) , так и [64-разр](https://aka.ms/teams64bitmsi)), которые администраторы могут использовать для массового развертывания Teams, чтобы выбрать Пользователи или компьютеры.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="2ba3a-106">Администраторы могут использовать эти файлы для удаленного развертывания команд, чтобы пользователи не могли вручную загрузить приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="2ba3a-107">При развертывании Teams автоматически запускается для всех пользователей, которые выполняют вход на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="2ba3a-108">(Вы можете отключить функцию автоматического запуска после установки приложения.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="2ba3a-109">[См. ниже](#disable-auto-launch-for-the-msi-installer).) Рекомендуется развернуть пакет на компьютере, чтобы все новые пользователи компьютера также смогли воспользоваться этим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 

<span data-ttu-id="2ba3a-110">Кроме того, Teams можно включить в развертывание Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-110">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="2ba3a-111">Дополнительные сведения можно найти [в разделе развертывание Microsoft Teams с Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="2ba3a-111">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>
 
> [!Note] 
> <span data-ttu-id="2ba3a-112">Чтобы узнать больше о SCCM, ознакомьтесь со статьей общие сведения о [System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="2ba3a-112">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="2ba3a-113">Процедура развертывания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="2ba3a-113">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="2ba3a-114">Загрузите последнюю версию пакета.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-114">Retrieve the latest package.</span></span>
2. <span data-ttu-id="2ba3a-115">Используйте значения по умолчанию, предварительно заполненные MSI.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-115">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="2ba3a-116">Разворачивать на компьютерах по возможности.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-116">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="2ba3a-117">Как работает пакет MSI Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ba3a-117">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="2ba3a-118">Установка ПК</span><span class="sxs-lookup"><span data-stu-id="2ba3a-118">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="2ba3a-119">Инструкции по развертыванию групп в среде виртуальных Десктопинфраструктуре (VDI) можно найти в статье [Установка VDI](#vdi-installation) .</span><span class="sxs-lookup"><span data-stu-id="2ba3a-119">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="2ba3a-120">MSI-файл Teams помещает установщик в файлы программы.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-120">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="2ba3a-121">При каждом входе пользователя в новый профиль пользователя Windows запускается установщик, и копия приложения Teams будет установлена в папку AppData этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-121">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="2ba3a-122">Если у пользователя уже есть приложение Teams, установленное в папке AppData, установщик MSI пропустит процесс для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-122">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="2ba3a-123">Не используйте MSI для развертывания обновлений, так как клиент будет автоматически обновляться при обнаружении новой версии, доступной из этой службы.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-123">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="2ba3a-124">Для повторного развертывания последней версии программы установки используйте процедуру повторного развертывания MSI, описанную ниже.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-124">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="2ba3a-125">Если вы развертываете более старую версию пакета MSI, клиент будет автоматически обновляться (за исключением случаев, когда это возможно в среде VDI).</span><span class="sxs-lookup"><span data-stu-id="2ba3a-125"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="2ba3a-126">Если вы разворачиваете самую старую версию, MSI вызывает обновление приложения, прежде чем пользователь сможет использовать команды.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-126">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="2ba3a-127">Мы не рекомендуем изменить расположения для установки по умолчанию, так как это может привести к разрыву процесса обновления.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-127">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="2ba3a-128">Слишком старая версия в конечном итоге блокирует доступ пользователей к службе.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-128">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="2ba3a-129">Требования к целевому компьютеру</span><span class="sxs-lookup"><span data-stu-id="2ba3a-129">Target computer requirements</span></span>

- <span data-ttu-id="2ba3a-130">.NET Framework 4,5 или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="2ba3a-130">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="2ba3a-131">Windows 7 или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="2ba3a-131">Windows 7 or later</span></span>
- <span data-ttu-id="2ba3a-132">3 ГБ места на диске для каждого профиля пользователя (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="2ba3a-132">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="2ba3a-133">Установка VDI</span><span class="sxs-lookup"><span data-stu-id="2ba3a-133">VDI installation</span></span>

<span data-ttu-id="2ba3a-134">Ниже описан процесс развертывания классического приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-134">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="2ba3a-135">Полные инструкции можно найти в разделе [Teams для виртуализованной инфраструктуры для настольных компьютеров](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="2ba3a-135">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="2ba3a-136">Скачайте пакет MSI Teams с помощью одной из приведенных ниже ссылок в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-136">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="2ba3a-137">Рекомендуем использовать 64-разрядную версию для виртуальной машины VDI с 64-разрядной операционной системой.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-137">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="2ba3a-138">32-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="2ba3a-138">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="2ba3a-139">64-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="2ba3a-139">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="2ba3a-140">Выполните следующую команду, чтобы установить MSI на виртуальную машину VDI (или завершить ее обновление).</span><span class="sxs-lookup"><span data-stu-id="2ba3a-140">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1

    <span data-ttu-id="2ba3a-141">Эти команды устанавливаются в файлы программы.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-141">This installs Teams to Program Files.</span></span> <span data-ttu-id="2ba3a-142">На этом этапе Настройка первоначальных изображений завершена.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-142">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="2ba3a-143">Следующий интерактивный сеанс входа запускает Teams и запрашивает учетные данные.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-143">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="2ba3a-144">Обратите внимание на то, что при установке Teams в VDI невозможно отключить автоматическое запуск Teams с помощью свойства ALLUSERS.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-144">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSERS property.</span></span>

3. <span data-ttu-id="2ba3a-145">Выполните следующую команду, чтобы удалить MSI из виртуальной машины VDI (или подготовиться к его обновлению).</span><span class="sxs-lookup"><span data-stu-id="2ba3a-145">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="2ba3a-146">Это действие удаляет группы из файлов программы.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-146">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="2ba3a-147">Процедура очистки и повторного развертывания</span><span class="sxs-lookup"><span data-stu-id="2ba3a-147">Clean up and redeployment procedure</span></span>

<span data-ttu-id="2ba3a-148">Если пользователь удаляет команды из своего профиля пользователя, установщик MSI будет отслеживать, что пользователь удалил приложение Teams и больше не будет устанавливать команды для этого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-148">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="2ba3a-149">Чтобы повторно развернуть команды для этого пользователя на определенном компьютере, на котором он был удален, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-149">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="2ba3a-150">Удалите приложение Teams, установленное для каждого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-150">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="2ba3a-151">После удаления каталог рекурсивно удаляется в%Локалаппдата%\микрософт\теамс\.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-151">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="2ba3a-152">Повторно разверните пакет MSI для определенного компьютера.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-152">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="2ba3a-153">Вы можете использовать сценарий [очистки для развертывания Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) , чтобы выполнить шаги 1 и 2 через SCCM.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-153">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="2ba3a-154">Отключение автоматического запуска установщика MSI</span><span class="sxs-lookup"><span data-stu-id="2ba3a-154">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="2ba3a-155">Поведение MSI по умолчанию — установка клиента Teams, когда пользователь входит в приложение, а затем автоматически запускает Teams.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-155">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="2ba3a-156">Это поведение можно изменить следующими параметрами ниже.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-156">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="2ba3a-157">При входе пользователя в Windows Teams будет установлен вместе с MSI-файлом</span><span class="sxs-lookup"><span data-stu-id="2ba3a-157">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="2ba3a-158">Однако клиент Teams не будет запущен, пока пользователь не запустит команды вручную</span><span class="sxs-lookup"><span data-stu-id="2ba3a-158">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="2ba3a-159">Ярлык для запуска Teams будет добавлен на Рабочий стол пользователя.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-159">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="2ba3a-160">После того как пользователь запустится вручную, группа будет автоматически запускаться каждый раз при входе в систему.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-160">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="2ba3a-161">Для 32-разрядной версии</span><span class="sxs-lookup"><span data-stu-id="2ba3a-161">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="2ba3a-162">Для 64-разрядной версии</span><span class="sxs-lookup"><span data-stu-id="2ba3a-162">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="2ba3a-163">Если вы запустите MSI вручную, не забудьте запустить его с повышенными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-163">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="2ba3a-164">Даже если вы запускаете учетную запись администратора, не запуская ее с повышенными разрешениями, установщик не сможет настроить параметр отключения автоматического запуска.</span><span class="sxs-lookup"><span data-stu-id="2ba3a-164">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
