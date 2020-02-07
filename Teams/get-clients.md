---
title: Работа с клиентами для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Сведения об использовании различных клиентов, доступных для Microsoft Teams, включая веб-клиент, классический клиент (Windows и Mac), а также мобильный клиент (Android и iOS).
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4abae267bf1a8c0c770eebf1c1b12018a6c7deb
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833769"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="f2bc2-103">Работа с клиентами для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2bc2-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="f2bc2-104">В Microsoft Teams доступны клиенты для настольных компьютеров (Windows, Mac и Linux), веб-сайтов и мобильных устройств (Android и iOS).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="f2bc2-105">Все они нуждаются в активном подключении к Интернету и не поддерживают автономный режим.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="f2bc2-106">С 29 ноября 2018 г. вы больше не сможете использовать приложение Microsoft Teams для Windows 10 S (предварительная версия), доступное в Магазине Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="f2bc2-107">Вместо этого теперь вы можете скачать и установить классический клиент Teams на устройствах с Windows 10 в S-режиме.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="f2bc2-108">Чтобы скачать классический клиент, перейдите по ссылке [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="f2bc2-109">Сборки MSI для классического клиента Teams пока недоступны на устройствах с Windows 10 в S-режиме.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="f2bc2-110">Дополнительные сведения о Windows 10 в S-режиме см. в статье [Знакомство с Windows 10 в S-режиме](https://www.microsoft.com/windows/s-mode).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="f2bc2-111">Классический клиент</span><span class="sxs-lookup"><span data-stu-id="f2bc2-111">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="f2bc2-112">Просмотрите следующий сеанс, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="f2bc2-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="f2bc2-113">Классический клиент Microsoft Teams представляет собой автономное приложение, а также [входит в состав Office 365 профессиональный плюс](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="f2bc2-114">Teams поддерживается для Windows (7 +), Windows Server (2012 R2 +), 32-bit и 64-bit Versions, macOS (10.10 +) и Linux (in `.deb` и `.rpm` formats).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-114">Teams is available for Windows (7+), Windows Server (2012 R2+), both 32-bit and 64-bit versions, macOS (10.10+), and Linux (in `.deb` and `.rpm` formats.).</span></span> <span data-ttu-id="f2bc2-115">В Windows для Teams требуется платформа .NET Framework 4.5 или более поздней версии; установщик Teams предложит установить ее, если она отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="f2bc2-116">В Linux диспетчеры пакетов, такие как Апт и Юм, будут пытаться установить любые требования.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-116">On Linux, package managers such as apt and yum will try to install any requirements for you.</span></span> <span data-ttu-id="f2bc2-117">Однако в противном случае вам потребуется установить любые требования, предъявляемые перед установкой Teams в Linux.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="f2bc2-118">Классические клиенты поддерживают взаимодействие в реальном времени (звук, видео и общий доступ к контенту) для собраний команды, групповых звонков и частных индивидуальных звонков.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="f2bc2-119">При наличии подходящих локальных разрешений (для установки клиента Teams на Mac требуются права администратора, а на ПК — нет) пользователи могут скачать и установить классические клиенты прямо со страницы [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="f2bc2-120">ИТ — администраторы могут выбрать предпочтительный способ распространения установочных файлов на компьютеры в своей организации.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-120">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="f2bc2-121">Некоторые примеры включают диспетчер конфигурации конечных точек Майкрософт (Windows) или Жамф Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-121">Some examples include Microsoft Endpoint Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="f2bc2-122">Сведения о получении MSI-пакета для распространения в Windows см. в статье [Установка Microsoft Teams с помощью MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-122">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="f2bc2-123">Распространение посредством этих механизмов подходит только для начальной установки клиентов Microsoft Team, но не для дальнейших обновлений.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-123">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="f2bc2-124">Windows</span><span class="sxs-lookup"><span data-stu-id="f2bc2-124">Windows</span></span>

<span data-ttu-id="f2bc2-125">Установка Microsoft Teams для Windows предоставляет скачиваемые установщики для 32- и 64-разрядной архитектуры.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-125">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="f2bc2-126">Архитектура Microsoft Teams (32- или 64-разрядная) не зависит от архитектуры Windows или установленного набора Office.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-126">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="f2bc2-127">Клиент Windows развертывается в папке AppData внутри профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-127">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="f2bc2-128">Развертывание в локальный профиль пользователя позволяет установить клиент без повышенных прав.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-128">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="f2bc2-129">Клиент Windows использует следующие расположения:</span><span class="sxs-lookup"><span data-stu-id="f2bc2-129">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="f2bc2-130">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="f2bc2-130">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="f2bc2-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="f2bc2-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="f2bc2-132">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="f2bc2-132">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="f2bc2-133">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="f2bc2-133">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="f2bc2-134">Когда пользователи впервые выполняют звонок через клиент Microsoft Teams, они могут заметить предупреждение с параметрами брандмауэра Windows, предлагающее пользователю разрешить взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-134">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="f2bc2-135">Можно попросить пользователей игнорировать это сообщение, так как звонок будет работать даже при закрытии предупреждения.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-135">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Снимок экрана с диалоговом окном "Оповещение системы безопасности Windows".](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="f2bc2-137">Конфигурация брандмауэра Windows будет изменена, даже если закрыть запрос, нажав кнопку "Отмена".</span><span class="sxs-lookup"><span data-stu-id="f2bc2-137">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="f2bc2-138">Создаются два правила входящего трафика для teams.exe с действием блокировки для протоколов TCP и UDP.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-138">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="f2bc2-139">Mac</span><span class="sxs-lookup"><span data-stu-id="f2bc2-139">Mac</span></span>

<span data-ttu-id="f2bc2-140">Пользователи Mac могут установить Teams с помощью файла установки PKG для компьютеров macOS.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-140">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="f2bc2-141">Для установки клиента Mac требуется административный доступ.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-141">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="f2bc2-142">Клиент macOS устанавливается в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-142">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="f2bc2-143">Установка Teams с помощью PKG-файла</span><span class="sxs-lookup"><span data-stu-id="f2bc2-143">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="f2bc2-144">На [странице скачивания Teams](https://teams.microsoft.com/downloads) в разделе **Mac** нажмите кнопку **Скачать**.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-144">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="f2bc2-145">Дважды щелкните PKG-файл.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-145">Double click the PKG file.</span></span>
3. <span data-ttu-id="f2bc2-146">Для завершения установки следуйте инструкциям мастера.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-146">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="f2bc2-147">Teams установится в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-147">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="f2bc2-148">Это установка на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-148">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="f2bc2-149">Во время установки PKG запросит учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-149">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="f2bc2-150">Пользователю потребуется ввести учетные данные администратора независимо от того, является ли он администратором.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-150">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="f2bc2-151">Если пользователь в настоящее время использует установку DMG приложения Teams и хочет заменить ее установкой PKG, следует сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="f2bc2-151">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="f2bc2-152">Выйти из приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-152">Exit the Teams app.</span></span>
2. <span data-ttu-id="f2bc2-153">Удалить приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-153">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="f2bc2-154">Установить PKG-файл.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-154">Install the PKG file.</span></span>

<span data-ttu-id="f2bc2-155">ИТ-администраторы могут использовать средство управляемого развертывания Teams для распространения установочных файлов на все компьютеры Mac в организации, например Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-155">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="f2bc2-156">Сообщите нам, если у вас возникают проблемы при установке PKG.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-156">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="f2bc2-157">В разделе **Обратная связь** в конце этой статьи нажмите кнопку **Отзыв о продукте**.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-157">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="f2bc2-158">Linux</span><span class="sxs-lookup"><span data-stu-id="f2bc2-158">Linux</span></span>

<span data-ttu-id="f2bc2-159">Пользователи смогут устанавливать собственные пакеты Linux в `.deb` и `.rpm` форматах.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-159">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="f2bc2-160">При установке пакета DEB или RPM будет автоматически установлена база данных пакетов.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-160">Installing the DEB or RPM package will automatically install the package repository</span></span>
- <span data-ttu-id="f2bc2-161">DEB`https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="f2bc2-161">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="f2bc2-162">ОБОРОТ`https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="f2bc2-162">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="f2bc2-163">Ключ подписи, позволяющий включить автоматическое обновление с помощью диспетчера пакетов системы, устанавливается автоматически.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-163">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="f2bc2-164">Однако ее также можно найти по адресу (https://packages.microsoft.com/keys/microsoft.asc).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-164">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="f2bc2-165">Microsoft Teams ежемесячно обновляется, и если репозиторий установлен правильно, диспетчер пакетов системы должен обрабатывать автоматическое обновление таким же образом, как и другие пакеты в системе.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-165">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="f2bc2-166">Если обнаружена ошибка, отправьте ее с помощью `Report a Problem` клиента.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-166">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="f2bc2-167">Известные проблемы можно найти в разделе [Известные проблемы](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-167">For known issues, see [Known Issues](Known-issues.md).</span></span>
> <span data-ttu-id="f2bc2-168">Для поддержки Teams для Linux вы можете использовать [канал поддержки форумов Linux в Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-168">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span></span> <span data-ttu-id="f2bc2-169">Не забудьте использовать `teams-linux` тег при отправке вопросов.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-169">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="f2bc2-170">Установка Teams с помощью пакета DEB</span><span class="sxs-lookup"><span data-stu-id="f2bc2-170">Install Teams using DEB package</span></span>

1. <span data-ttu-id="f2bc2-171">Скачайте пакет https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-171">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="f2bc2-172">Установите одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-172">Install using one of the following:</span></span>  
    - <span data-ttu-id="f2bc2-173">Откройте средство для управления пакетом и пройдите по установке самоуправляемого приложения для Linux.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-173">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="f2bc2-174">Или, если вы любите контакт, введите:`sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="f2bc2-174">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="f2bc2-175">Вы можете запускать команды с помощью действий или через терминал, `Teams`вводя текст.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-175">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="f2bc2-176">Установка Teams с помощью пакета RPM</span><span class="sxs-lookup"><span data-stu-id="f2bc2-176">Install Teams using RPM package</span></span>

1. <span data-ttu-id="f2bc2-177">Скачайте пакет https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-177">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="f2bc2-178">Установите одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-178">Install using one of the following:</span></span>
    - <span data-ttu-id="f2bc2-179">Откройте средство для управления пакетом и пройдите по установке самоуправляемого приложения для Linux.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-179">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="f2bc2-180">Или, если вы любите контакт, введите:`sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="f2bc2-180">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="f2bc2-181">Вы можете запускать команды с помощью действий или через терминал, `Teams`вводя текст.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-181">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="f2bc2-182">Установка вручную из командной строки</span><span class="sxs-lookup"><span data-stu-id="f2bc2-182">Install manually from the command line</span></span>

<span data-ttu-id="f2bc2-183">Установка вручную в Debian и Ubuntu:</span><span class="sxs-lookup"><span data-stu-id="f2bc2-183">Install manually on Debian and Ubuntu distributions:</span></span>
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

<span data-ttu-id="f2bc2-184">Установка вручную на основе РХЕЛ, Fedora и Центос для дистрибутивов:</span><span class="sxs-lookup"><span data-stu-id="f2bc2-184">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="f2bc2-185">Кроме того, чтобы использовать Юм вместо ДНФ, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-185">Alternatively, to use yum instead of dnf:</span></span>
```
yum check-update
sudo yum install teams
```

<span data-ttu-id="f2bc2-186">Установка вручную в дистрибутивах на базе openSUSE:</span><span class="sxs-lookup"><span data-stu-id="f2bc2-186">Install manually on openSUSE based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="f2bc2-187">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="f2bc2-187">Web client</span></span> 

<span data-ttu-id="f2bc2-188">Веб-клиент ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) представляет собой полнофункциональный клиент, который можно использовать в различных браузерах.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-188">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="f2bc2-189">Веб-клиент поддерживает звонки и собрания с помощью webRTC, поэтому не требуется подключаемый модуль или скачивание для запуска Teams в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-189">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="f2bc2-190">В браузере должно быть разрешено использование сторонних файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-190">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="f2bc2-191">Веб-клиент определяет версию браузера при подключении к сайту [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="f2bc2-191">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="f2bc2-192">В случае обнаружения неподдерживаемой версии блокируется доступ к веб-интерфейсу и пользователю рекомендуется скачать классический клиент или мобильное приложение.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-192">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="f2bc2-193">Мобильные клиенты</span><span class="sxs-lookup"><span data-stu-id="f2bc2-193">Mobile clients</span></span>

<span data-ttu-id="f2bc2-194">Мобильные приложения Microsoft Teams доступны для Android и iOS и предназначены для пользователей, участвующих в беседах на основе чата и выполняющих одноранговые звонки во время поездок.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-194">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="f2bc2-195">Для мобильных приложений следует использовать соответствующий магазин: Google Play и Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-195">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="f2bc2-196">Приложение Windows Phone перестало поддерживаться 20 июля 2018 г. и может перестать работать.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-196">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="f2bc2-197">Для мобильных приложений Microsoft Teams поддерживаются следующие мобильные платформы:</span><span class="sxs-lookup"><span data-stu-id="f2bc2-197">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="f2bc2-198">**Android**: поддержка ограничена последними основными версиями Android.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-198">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="f2bc2-199">Если выпущена новая старшая версия Android, официально поддерживаются новая версия и три предыдущие версии.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-199">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

-   <span data-ttu-id="f2bc2-200">**iOS**: поддержка ограничена двумя последними основными версиями iOS.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-200">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="f2bc2-201">При выпуске новой основной версии iOS официально поддерживаются новая версия iOS и Предыдущая версия.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-201">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="f2bc2-202">Мобильная версия должна быть общедоступной, чтобы приложение Teams работало правильно.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-202">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="f2bc2-203">Мобильные приложения распространяются и обновляются только через магазин приложений для соответствующей мобильной платформы.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-203">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="f2bc2-204">Распространение мобильных приложений через MDM и загрузка неопубликованных приложений не поддерживаются корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-204">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="f2bc2-205">Как только мобильное приложение Teams будет установлено на поддерживаемой мобильной платформе, оно само будет поддерживаться, при условии что с момента выпуска текущей версии прошло не более трех месяцев.   </span><span class="sxs-lookup"><span data-stu-id="f2bc2-205">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![Значок, изображающий точку принятия решения](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="f2bc2-207">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="f2bc2-207">Decision Point</span></span>         |<span data-ttu-id="f2bc2-208">Существуют ли ограничения, мешающие пользователям установить на своих устройствах подходящий клиент Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="f2bc2-208">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Значок, изображающий дальнейшие действия](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="f2bc2-210">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f2bc2-210">Next Steps</span></span>         |<span data-ttu-id="f2bc2-211">Если ваша организация ограничивает установку программного обеспечения, убедитесь в совместимости данного механизма с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-211">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="f2bc2-212">Примечание. Для установки клиента на Mac требуются права администратора, а на ПК — нет.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-212">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="f2bc2-213">Управление обновлениями клиентов</span><span class="sxs-lookup"><span data-stu-id="f2bc2-213">Client update management</span></span>

<span data-ttu-id="f2bc2-214">Сейчас клиенты обновляются службой Microsoft Teams автоматически и без вмешательства ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-214">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="f2bc2-215">При выходе обновления клиент автоматически скачивает его, а после определенного периода неактивности приложения начинает процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-215">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="f2bc2-216">Конфигурации на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="f2bc2-216">Client-side configurations</span></span>

<span data-ttu-id="f2bc2-217">Сейчас не существует способа для настройки клиента администратором клиента, а также с помощью PowerShell, объектов групповой политики или реестра.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-217">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="f2bc2-218">Параметры уведомлений</span><span class="sxs-lookup"><span data-stu-id="f2bc2-218">Notification settings</span></span>

<span data-ttu-id="f2bc2-219">Сейчас не существует способа для настройки параметров уведомлений на стороне клиента ИТ-администраторами.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-219">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="f2bc2-220">Все эти параметры задает пользователь.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-220">All notification options are set by the user.</span></span> <span data-ttu-id="f2bc2-221">Приведенный ниже рисунок показывает параметры клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-221">The figure below outlines the default client settings.</span></span>

![Снимок экрана с параметрами уведомлений.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a><span data-ttu-id="f2bc2-223">Пример скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2bc2-223">Sample PowerShell Script</span></span>

<span data-ttu-id="f2bc2-224">Этот пример скрипта, который нужно запускать на клиентских компьютерах в контексте учетной записи администратора с повышенными правами, создает правило входящих подключений брандмауэра для каждой папки пользователя, находящейся в c:\users.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-224">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="f2bc2-225">Если Teams обнаруживает это правило, блокируется запрос для пользователей на создание правил брандмауэра, когда пользователи выполняют первый звонок из Teams.</span><span class="sxs-lookup"><span data-stu-id="f2bc2-225">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
