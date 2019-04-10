---
title: Установка Microsoft Teams с помощью MSI (через SCCM)
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Администраторы могут использовать MSI Teams для массового развертывания Microsoft Teams для отдельных пользователей или на отдельных компьютерах.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8412b6998e824c05ac4d7f394d2283c265f78b04
ms.sourcegitcommit: 9bb2bfd09ca279752dbedf17911ea46568649c4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "31749687"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="2e02b-103">Установка Microsoft Teams с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="2e02b-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="2e02b-104">Просмотрите следующие сеанса, чтобы узнать о преимуществах клиент рабочий стол Windows, планировании его и способе развертывания: [Группы Windows Desktop Client](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="2e02b-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="2e02b-105">Чтобы использовать System Center Configuration Manager или групповой политики или любой механизма распространения сторонних производителей для широкомасштабного развертывания решения, корпорация Майкрософт предоставляет файлов MSI ( [32-разрядная](https://aka.ms/teams32bitmsi) и [64-разрядная версия](https://aka.ms/teams64bitmsi)), администраторы могут использовать для развертывания массового рабочих групп для выбора пользователей или компьютеров.</span><span class="sxs-lookup"><span data-stu-id="2e02b-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="2e02b-106">Администраторы могут использовать эти файлы для удаленного развертывания групп, чтобы пользователи не имеют для ручной загрузки приложения группы.</span><span class="sxs-lookup"><span data-stu-id="2e02b-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="2e02b-107">При развертывании команды будет автоматически запуска для всех пользователей, вход на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="2e02b-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="2e02b-108">(Можно отключить запуск после установки приложения.</span><span class="sxs-lookup"><span data-stu-id="2e02b-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="2e02b-109">[Ниже приведены](#disable-auto-launch-for-the-msi-installer)). Мы рекомендуем развертывание пакета на компьютере, поэтому всех новых пользователей компьютера также выиграют от этого развертывания.</span><span class="sxs-lookup"><span data-stu-id="2e02b-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="2e02b-110">Чтобы узнать больше о SCCM, см [В System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="2e02b-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="2e02b-111">Процедуры развертывания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="2e02b-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="2e02b-112">Получите последнюю версию пакета.</span><span class="sxs-lookup"><span data-stu-id="2e02b-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="2e02b-113">Используйте параметры по умолчанию, предварительно с MSI-файла.</span><span class="sxs-lookup"><span data-stu-id="2e02b-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="2e02b-114">Развертывания на компьютерах, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="2e02b-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="2e02b-115">Как работает пакет MSI группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="2e02b-115">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="2e02b-116">Установка ПК</span><span class="sxs-lookup"><span data-stu-id="2e02b-116">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="2e02b-117">Руководство по развертыванию группы в среде виртуальных DesktopInfrastructure (VDI) в разделе [установки инфраструктуры виртуальных рабочих СТОЛОВ](#vdi-installation) .</span><span class="sxs-lookup"><span data-stu-id="2e02b-117">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="2e02b-118">MSI группы будут помещены установщика в Program Files.</span><span class="sxs-lookup"><span data-stu-id="2e02b-118">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="2e02b-119">Каждый раз, когда пользователь входит в новый профиль пользователя Windows, запускается программа установки и копию приложения группы должны устанавливаться в папку appdata этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e02b-119">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="2e02b-120">Если пользователь уже имеет приложения группы, устанавливается в папку appdata, установщик MSI пропустит процесс для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e02b-120">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="2e02b-121">Не используйте MSI-файла для развертывания обновлений, так как клиент будет автоматически обновления, когда обнаруживает, что новая версия, доступные в службе.</span><span class="sxs-lookup"><span data-stu-id="2e02b-121">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="2e02b-122">Повторное развертывание последние установщик использовать процесс повторное развертывание MSI описано ниже.</span><span class="sxs-lookup"><span data-stu-id="2e02b-122">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="2e02b-123">При развертывании более старые версии пакета MSI, клиент будет автоматическое обновление по возможности для пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e02b-123"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="2e02b-124">Если очень старой версии получает развернут, MSI-файла будет активировано обновления приложения, прежде чем пользователь сможет использовать команды.</span><span class="sxs-lookup"><span data-stu-id="2e02b-124">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="2e02b-125">Не рекомендуется изменить расположения установки по умолчанию, как это может нарушить этот процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="2e02b-125">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="2e02b-126">Наличие слишком старой версии со временем блокировать пользователям доступ к службе.</span><span class="sxs-lookup"><span data-stu-id="2e02b-126">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="2e02b-127">Требования к конечного компьютера</span><span class="sxs-lookup"><span data-stu-id="2e02b-127">Target computer requirements</span></span>

- <span data-ttu-id="2e02b-128">.NET framework 4.5 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="2e02b-128">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="2e02b-129">Windows 7 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="2e02b-129">Windows 7 or later</span></span>
- <span data-ttu-id="2e02b-130">3 ГБ дискового пространства для каждого профиля пользователя (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="2e02b-130">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="2e02b-131">Установка инфраструктуры виртуальных рабочих СТОЛОВ</span><span class="sxs-lookup"><span data-stu-id="2e02b-131">VDI installation</span></span>

<span data-ttu-id="2e02b-132">Ниже приведен процесс развертывания классического приложения группы.</span><span class="sxs-lookup"><span data-stu-id="2e02b-132">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="2e02b-133">Полное руководство по в разделе [группы для инфраструктуры виртуализации рабочего стола](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="2e02b-133">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="2e02b-134">Загрузите пакет MSI группами, с помощью одного из следующих ссылок в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="2e02b-134">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="2e02b-135">Мы рекомендуем 64-разрядная версия для виртуальной Машины инфраструктуры виртуальных рабочих СТОЛОВ с 64-разрядной операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2e02b-135">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="2e02b-136">32-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="2e02b-136">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="2e02b-137">64-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="2e02b-137">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="2e02b-138">Выполните следующую команду для установки MSI-файла для виртуальной Машины инфраструктуры виртуальных рабочих СТОЛОВ (или выполнить его обновление).</span><span class="sxs-lookup"><span data-stu-id="2e02b-138">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="2e02b-139">Это устанавливает группами Program Files.</span><span class="sxs-lookup"><span data-stu-id="2e02b-139">This installs Teams to Program Files.</span></span> <span data-ttu-id="2e02b-140">На этом этапе Настройка эталонные изображения завершена.</span><span class="sxs-lookup"><span data-stu-id="2e02b-140">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="2e02b-141">Следующего интерактивного входа в систему начинается групп и запрашивает учетные данные.</span><span class="sxs-lookup"><span data-stu-id="2e02b-141">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="2e02b-142">Обратите внимание на то, что не можно отключить автоматический запуск команд при установке групп с помощью свойства ALLUSER инфраструктуры виртуальных рабочих СТОЛОВ.</span><span class="sxs-lookup"><span data-stu-id="2e02b-142">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="2e02b-143">Выполните следующую команду, чтобы удалить MSI-файла из виртуальной Машины инфраструктуры виртуальных рабочих СТОЛОВ (или подготовки к их обновление).</span><span class="sxs-lookup"><span data-stu-id="2e02b-143">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="2e02b-144">Это удаление групп из Program Files.</span><span class="sxs-lookup"><span data-stu-id="2e02b-144">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="2e02b-145">Очистка и процедура повторного развертывания</span><span class="sxs-lookup"><span data-stu-id="2e02b-145">Clean up and redeployment procedure</span></span>

<span data-ttu-id="2e02b-146">Если пользователь удаляет команды из своего профиля пользователя, установщик MSI будет отслеживать, что пользователь отменил установку приложения группы и больше не установить групп для этого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e02b-146">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="2e02b-147">Повторное развертывание групп для этого пользователя на конкретном компьютере, где она была удалена, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2e02b-147">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="2e02b-148">Удаление группы приложения, установленные для каждого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e02b-148">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="2e02b-149">После удаления, удалите рекурсивно каталога в разделе % localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="2e02b-149">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="2e02b-150">Повторное развертывание пакета MSI для данного компьютера.</span><span class="sxs-lookup"><span data-stu-id="2e02b-150">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="2e02b-151">Наш сценарий [развертывания групп Майкрософт Очистка](scripts/Powershell-script-teams-deployment-clean-up.md) можно использовать для выполнения действия 1 и 2 с помощью SCCM.</span><span class="sxs-lookup"><span data-stu-id="2e02b-151">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="2e02b-152">Отключение автоматического запуска для установщика MSI</span><span class="sxs-lookup"><span data-stu-id="2e02b-152">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="2e02b-153">Поведения MSI-файла по умолчанию — установить клиент группы, как только пользователь входит в и автоматически запускать команды.</span><span class="sxs-lookup"><span data-stu-id="2e02b-153">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="2e02b-154">Можно изменить это поведение вместе с параметрами под следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2e02b-154">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="2e02b-155">Когда пользователь входит в в Windows, групп должны устанавливаться с помощью MSI-файла</span><span class="sxs-lookup"><span data-stu-id="2e02b-155">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="2e02b-156">Тем не менее клиент группы не будет запускаться, пока пользователь начинает группам вручную</span><span class="sxs-lookup"><span data-stu-id="2e02b-156">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="2e02b-157">Ярлык для запуска групп добавляются на рабочем столе пользователя</span><span class="sxs-lookup"><span data-stu-id="2e02b-157">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="2e02b-158">После запуска вручную, команды будет автоматический запуск каждый раз, когда пользователь входит в</span><span class="sxs-lookup"><span data-stu-id="2e02b-158">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="2e02b-159">Для 32-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="2e02b-159">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="2e02b-160">Для 64-разрядная версия</span><span class="sxs-lookup"><span data-stu-id="2e02b-160">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="2e02b-161">При выполнении MSI-файла вручную, необходимо запустить его с повышенным уровнем разрешений.</span><span class="sxs-lookup"><span data-stu-id="2e02b-161">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="2e02b-162">Даже при выполнении его с правами администратора без запуска с повышенным уровнем разрешений, программа установки будет не могут настроить параметр, чтобы отключить автоматический запуск.</span><span class="sxs-lookup"><span data-stu-id="2e02b-162">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
