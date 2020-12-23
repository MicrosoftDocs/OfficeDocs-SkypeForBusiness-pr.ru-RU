---
title: Работа с клиентами для Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
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
ms.openlocfilehash: 2cb28295b0a9700a0eb7531111022a9498517d93
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611593"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="21efd-103">Работа с клиентами для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="21efd-103">Get clients for Microsoft Teams</span></span> 

<span data-ttu-id="21efd-104">У Microsoft Teams есть клиенты, доступные для настольных компьютеров (Windows, Mac и Linux), веб-сайтов и мобильных устройств (Android и iOS).</span><span class="sxs-lookup"><span data-stu-id="21efd-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="21efd-105">Все они нуждаются в активном подключении к Интернету и не поддерживают автономный режим.</span><span class="sxs-lookup"><span data-stu-id="21efd-105">These clients all require an active internet connection and do not support an offline mode.</span></span> 

> [!Note]
> <span data-ttu-id="21efd-106">Подробные сведения о возможностях каждого клиента на разных платформах см. в различных [платформах Teams.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="21efd-106">For details about each clients' capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

> [!NOTE]
> <span data-ttu-id="21efd-107">С 29 ноября 2018 г. вы больше не сможете использовать приложение Microsoft Teams для Windows 10 S (предварительная версия), доступное в Магазине Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="21efd-107">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="21efd-108">Вместо этого теперь вы можете скачать и установить классический клиент Teams на устройствах с Windows 10 в S-режиме.</span><span class="sxs-lookup"><span data-stu-id="21efd-108">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="21efd-109">Чтобы скачать классический клиент, перейдите по ссылке [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="21efd-109">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="21efd-110">Сборки MSI для классического клиента Teams пока недоступны на устройствах с Windows 10 в S-режиме.</span><span class="sxs-lookup"><span data-stu-id="21efd-110">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="21efd-111">Дополнительные сведения о Windows 10 в S-режиме см. в статье [Знакомство с Windows 10 в S-режиме](https://www.microsoft.com/windows/s-mode).</span><span class="sxs-lookup"><span data-stu-id="21efd-111">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="21efd-112">Классический клиент</span><span class="sxs-lookup"><span data-stu-id="21efd-112">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="21efd-113">Просмотрите следующий сеанс, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="21efd-113">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="21efd-114">Клиент Microsoft Teams для настольных ПК — это приложение, которое также доступно в приложениях [Microsoft 365 корпоративный.](https://docs.microsoft.com/deployoffice/teams-install)</span><span class="sxs-lookup"><span data-stu-id="21efd-114">The Microsoft Teams desktop client is a standalone application and is also [available in Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="21efd-115">Teams доступен для 32- и 64-битных версий Windows (8.1 или более поздней версии), ARM64 для Windows 10 в ARM и Windows Server (2012 R2 или более поздней версии), а также для macOS и Linux (в `.deb` и `.rpm` формате).</span><span class="sxs-lookup"><span data-stu-id="21efd-115">Teams is available for 32-bit and 64-bit versions of Windows (8.1 or later), ARM64 for Windows 10 on ARM, and Windows Server (2012 R2 or later), as well as for macOS and Linux (in `.deb` and `.rpm` formats).</span></span> <span data-ttu-id="21efd-116">В Windows для Teams требуется платформа .NET Framework 4.5 или более поздней версии; установщик Teams предложит установить ее, если она отсутствует.</span><span class="sxs-lookup"><span data-stu-id="21efd-116">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="21efd-117">В Linux, диспетчеры пакетов, такие как `apt` и `yum`, пытаются установить любые требования.</span><span class="sxs-lookup"><span data-stu-id="21efd-117">On Linux, package managers such as `apt` and `yum` will try to install any requirements for you.</span></span> <span data-ttu-id="21efd-118">Однако, если этого не произойдет, вам нужно будет установить все заявленные требования перед установкой Teams в Linux.</span><span class="sxs-lookup"><span data-stu-id="21efd-118">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="21efd-119">Классические клиенты поддерживают взаимодействие в реальном времени (звук, видео и общий доступ к контенту) для собраний команды, групповых звонков и частных индивидуальных звонков.</span><span class="sxs-lookup"><span data-stu-id="21efd-119">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="21efd-120">При наличии подходящих локальных разрешений (для установки клиента Teams на Mac требуются права администратора, а на ПК — нет) пользователи могут скачать и установить классические клиенты прямо со страницы [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="21efd-120">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

> [!NOTE]
> <span data-ttu-id="21efd-121">Дополнительные сведения об установке Teams на [](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)хромбуке см. в Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="21efd-121">For more details about installing Teams on a Chromebook, please see [How to install and run Microsoft Office on a Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).</span></span>

<span data-ttu-id="21efd-122">ИТ-администраторы могут выбрать предпочтительный способ распространения установочных файлов на компьютеры в своей организации.</span><span class="sxs-lookup"><span data-stu-id="21efd-122">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="21efd-123">Некоторые примеры включают Microsoft Endpoint Configuration Manager (Windows) или Jamf Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="21efd-123">Some examples include Microsoft Endpoint Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="21efd-124">Сведения о получении MSI-пакета для распространения в Windows см. в статье [Установка Microsoft Teams с помощью MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="21efd-124">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="21efd-125">Распространение посредством этих механизмов подходит только для начальной установки клиентов Microsoft Team, но не для дальнейших обновлений.</span><span class="sxs-lookup"><span data-stu-id="21efd-125">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="21efd-126">Windows</span><span class="sxs-lookup"><span data-stu-id="21efd-126">Windows</span></span>

<span data-ttu-id="21efd-127">Установка Microsoft Teams для Windows предоставляет скачиваемые установщики для 32- и 64-разрядной архитектуры.</span><span class="sxs-lookup"><span data-stu-id="21efd-127">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="21efd-128">Архитектура Microsoft Teams (32- или 64-разрядная) не зависит от архитектуры Windows или установленного набора Office.</span><span class="sxs-lookup"><span data-stu-id="21efd-128">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="21efd-129">Клиент Windows развертывается в папке AppData внутри профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="21efd-129">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="21efd-130">Развертывание в локальный профиль пользователя позволяет установить клиент без повышенных прав.</span><span class="sxs-lookup"><span data-stu-id="21efd-130">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="21efd-131">Клиент Windows использует следующие расположения:</span><span class="sxs-lookup"><span data-stu-id="21efd-131">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="21efd-132">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="21efd-132">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="21efd-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="21efd-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="21efd-134">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="21efd-134">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="21efd-135">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="21efd-135">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="21efd-136">Когда пользователи впервые выполняют звонок через клиент Microsoft Teams, они могут заметить предупреждение с параметрами брандмауэра Windows, предлагающее пользователю разрешить взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="21efd-136">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="21efd-137">Можно попросить пользователей игнорировать это сообщение, так как звонок будет работать даже при закрытии предупреждения.</span><span class="sxs-lookup"><span data-stu-id="21efd-137">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Снимок экрана с диалоговом окном "Оповещение системы безопасности Windows".](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="21efd-139">Конфигурация брандмауэра Windows будет изменена, даже если закрыть запрос, нажав кнопку "Отмена".</span><span class="sxs-lookup"><span data-stu-id="21efd-139">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="21efd-140">Два входящие правила для teams.exe будут созданы с действием Allow для протоколов TCP и UDP.</span><span class="sxs-lookup"><span data-stu-id="21efd-140">Two inbound rules for teams.exe will be created with Allow action for both TCP and UDP protocols.</span></span>

<span data-ttu-id="21efd-141">Если вы хотите запретить Пользователям Teams создавать правила брандмауэра при первом звонке из Teams, воспользуйтесь образцом сценария [PowerShell—](#sample-powershell-script---inbound-firewall-rule) правилом входящий брандмауэр ниже.</span><span class="sxs-lookup"><span data-stu-id="21efd-141">If you want to prevent Teams from prompting users to create firewall rules when the users make their first call from Teams, use the [Sample PowerShell script - inbound firewall rule](#sample-powershell-script---inbound-firewall-rule) below.</span></span> 

### <a name="mac"></a><span data-ttu-id="21efd-142">Mac</span><span class="sxs-lookup"><span data-stu-id="21efd-142">Mac</span></span>

<span data-ttu-id="21efd-143">Пользователи Mac могут установить Teams с помощью файла установки PKG для компьютеров macOS.</span><span class="sxs-lookup"><span data-stu-id="21efd-143">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="21efd-144">Для установки клиента Mac требуется административный доступ.</span><span class="sxs-lookup"><span data-stu-id="21efd-144">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="21efd-145">Клиент macOS устанавливается в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="21efd-145">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="21efd-146">Установка Teams с помощью PKG-файла</span><span class="sxs-lookup"><span data-stu-id="21efd-146">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="21efd-147">На [странице скачивания Teams](https://teams.microsoft.com/downloads) в разделе **Mac** нажмите кнопку **Скачать**.</span><span class="sxs-lookup"><span data-stu-id="21efd-147">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="21efd-148">Дважды щелкните PKG-файл.</span><span class="sxs-lookup"><span data-stu-id="21efd-148">Double click the PKG file.</span></span>
3. <span data-ttu-id="21efd-149">Для завершения установки следуйте инструкциям мастера.</span><span class="sxs-lookup"><span data-stu-id="21efd-149">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="21efd-150">Teams установится в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="21efd-150">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="21efd-151">Это установка на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="21efd-151">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="21efd-152">Во время установки PKG запросит учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="21efd-152">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="21efd-153">Пользователю потребуется ввести учетные данные администратора независимо от того, является ли он администратором.</span><span class="sxs-lookup"><span data-stu-id="21efd-153">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="21efd-154">Если пользователь в настоящее время использует установку DMG приложения Teams и хочет заменить ее установкой PKG, следует сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="21efd-154">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="21efd-155">Выйти из приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="21efd-155">Exit the Teams app.</span></span>
2. <span data-ttu-id="21efd-156">Удалить приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="21efd-156">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="21efd-157">Установить PKG-файл.</span><span class="sxs-lookup"><span data-stu-id="21efd-157">Install the PKG file.</span></span>

<span data-ttu-id="21efd-158">ИТ-администраторы могут использовать средство управляемого развертывания Teams для распространения установочных файлов на все компьютеры Mac в организации, например Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="21efd-158">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="21efd-159">Сообщите нам, если у вас возникают проблемы при установке PKG.</span><span class="sxs-lookup"><span data-stu-id="21efd-159">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="21efd-160">В разделе **Обратная связь** в конце этой статьи нажмите кнопку **Отзыв о продукте**.</span><span class="sxs-lookup"><span data-stu-id="21efd-160">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="21efd-161">Linux</span><span class="sxs-lookup"><span data-stu-id="21efd-161">Linux</span></span>

<span data-ttu-id="21efd-162">Пользователи смогут установить собственные пакеты Linux в форматах `.deb` и `.rpm`.</span><span class="sxs-lookup"><span data-stu-id="21efd-162">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="21efd-163">При установке пакета DEB или RPM автоматически устанавливается репозиторий пакетов.</span><span class="sxs-lookup"><span data-stu-id="21efd-163">Installing the DEB or RPM package will automatically install the package repository.</span></span>
- <span data-ttu-id="21efd-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="21efd-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="21efd-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="21efd-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="21efd-166">Ключ подписи для автоматического обновления с помощью системного менеджера пакетов устанавливается автоматически.</span><span class="sxs-lookup"><span data-stu-id="21efd-166">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="21efd-167">Однако его также можно найти по адресу: (https://packages.microsoft.com/keys/microsoft.asc).</span><span class="sxs-lookup"><span data-stu-id="21efd-167">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="21efd-168">Microsoft Teams поставляется ежемесячно, и если репозиторий был установлен правильно, ваш системный менеджер пакетов должен обрабатывать автоматическое обновление так же, как и другие пакеты в системе.</span><span class="sxs-lookup"><span data-stu-id="21efd-168">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="21efd-169">Если вы нашли ошибку, отправьте ее, используя `Report a Problem` из клиента.</span><span class="sxs-lookup"><span data-stu-id="21efd-169">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="21efd-170">Известные проблемы см. [в службе поддержки Teams в вашей организации.](Known-issues.md)</span><span class="sxs-lookup"><span data-stu-id="21efd-170">For known issues, see [Support Teams in your organization](Known-issues.md).</span></span>
> <span data-ttu-id="21efd-171">В Teams для Linux можно использовать канал поддержки форума [Linux в Microsoft Вопросы и ответы](https://docs.microsoft.com/answers/topics/teams.html).</span><span class="sxs-lookup"><span data-stu-id="21efd-171">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span></span> <span data-ttu-id="21efd-172">При размещении вопросов используйте тег `teams-linux`.</span><span class="sxs-lookup"><span data-stu-id="21efd-172">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="21efd-173">Установить команды, используя пакет DEB</span><span class="sxs-lookup"><span data-stu-id="21efd-173">Install Teams using DEB package</span></span>

1. <span data-ttu-id="21efd-174">Скачайте пакет из https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="21efd-174">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="21efd-175">Установите с помощью одного из следующих:</span><span class="sxs-lookup"><span data-stu-id="21efd-175">Install using one of the following:</span></span>  
    - <span data-ttu-id="21efd-176">Откройте соответствующий инструмент управления пакетами и пройдите процедуру самостоятельной установки приложений Linux.</span><span class="sxs-lookup"><span data-stu-id="21efd-176">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="21efd-177">Или, если вы любите Терминал, введите: `sudo dpkg -i **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="21efd-177">Or if you love Terminal, type: `sudo dpkg -i **teams download file**`</span></span>

<span data-ttu-id="21efd-178">Вы можете запустить Teams через Действия или через Терминал, набрав `teams`.</span><span class="sxs-lookup"><span data-stu-id="21efd-178">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="21efd-179">Установите Команды, используя пакет RPM</span><span class="sxs-lookup"><span data-stu-id="21efd-179">Install Teams using RPM package</span></span>

1. <span data-ttu-id="21efd-180">Скачайте пакет из https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="21efd-180">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="21efd-181">Установите с помощью одного из следующих:</span><span class="sxs-lookup"><span data-stu-id="21efd-181">Install using one of the following:</span></span>
    - <span data-ttu-id="21efd-182">Откройте соответствующий инструмент управления пакетами и пройдите процедуру самостоятельной установки приложений Linux.</span><span class="sxs-lookup"><span data-stu-id="21efd-182">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="21efd-183">Или, если вы любите Терминал, введите: `sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="21efd-183">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="21efd-184">Вы можете запустить Teams через Действия или через Терминал, набрав `teams`.</span><span class="sxs-lookup"><span data-stu-id="21efd-184">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="21efd-185">Установить вручную из командной строки</span><span class="sxs-lookup"><span data-stu-id="21efd-185">Install manually from the command line</span></span>

<span data-ttu-id="21efd-186">Установите вручную в дистрибутивах Debian и Ubuntu:</span><span class="sxs-lookup"><span data-stu-id="21efd-186">Install manually on Debian and Ubuntu distributions:</span></span>

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

<span data-ttu-id="21efd-187">Установите вручную в дистрибутивах на основе RHEL, Fedora и CentOS:</span><span class="sxs-lookup"><span data-stu-id="21efd-187">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="21efd-188">Также можно использовать yum вместо dnf:</span><span class="sxs-lookup"><span data-stu-id="21efd-188">Alternatively, to use yum instead of dnf:</span></span>

```bash
yum check-update
sudo yum install teams
```

<span data-ttu-id="21efd-189">Установите вручную в дистрибутивах на основе openSUSE:</span><span class="sxs-lookup"><span data-stu-id="21efd-189">Install manually on openSUSE based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="21efd-190">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="21efd-190">Web client</span></span> 

<span data-ttu-id="21efd-191">Веб-клиент ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) представляет собой полнофункциональный клиент, который можно использовать в различных браузерах.</span><span class="sxs-lookup"><span data-stu-id="21efd-191">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="21efd-192">Веб-клиент поддерживает звонки и собрания с помощью webRTC, поэтому не требуется подключаемый модуль или скачивание для запуска Teams в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="21efd-192">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="21efd-193">В браузере должно быть разрешено использование сторонних файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="21efd-193">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="21efd-194">Веб-клиент определяет версию браузера при подключении к сайту [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="21efd-194">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="21efd-195">В случае обнаружения неподдерживаемой версии блокируется доступ к веб-интерфейсу и пользователю рекомендуется скачать классический клиент или мобильное приложение.</span><span class="sxs-lookup"><span data-stu-id="21efd-195">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="21efd-196">Мобильные клиенты</span><span class="sxs-lookup"><span data-stu-id="21efd-196">Mobile clients</span></span>

<span data-ttu-id="21efd-197">Мобильные приложения Microsoft Teams доступны для Android и iOS и предназначены для пользователей, участвующих в беседах на основе чата и выполняющих одноранговые звонки во время поездок.</span><span class="sxs-lookup"><span data-stu-id="21efd-197">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="21efd-198">Для мобильных приложений следует использовать соответствующий магазин: Google Play и Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="21efd-198">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="21efd-199">Приложение Windows Phone перестало поддерживаться 20 июля 2018 г. и может перестать работать.</span><span class="sxs-lookup"><span data-stu-id="21efd-199">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="21efd-200">В Китае вот как [получить Teams для Android](get-teams-android-in-china.md).</span><span class="sxs-lookup"><span data-stu-id="21efd-200">In China, here's how to [get Teams for Android](get-teams-android-in-china.md).</span></span> 

<span data-ttu-id="21efd-201">Для мобильных приложений Microsoft Teams поддерживаются следующие мобильные платформы:</span><span class="sxs-lookup"><span data-stu-id="21efd-201">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="21efd-202">**Android**: поддержка ограничена последними четырьмя основными версиями Android.</span><span class="sxs-lookup"><span data-stu-id="21efd-202">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="21efd-203">Когда выпущена новая основная версия Android, официально поддерживается новая версия и предыдущие три версии.</span><span class="sxs-lookup"><span data-stu-id="21efd-203">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

-   <span data-ttu-id="21efd-204">**iOS**: поддержка ограничена двумя последними основными версиями iOS.</span><span class="sxs-lookup"><span data-stu-id="21efd-204">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="21efd-205">Когда выпущена новая основная версия iOS, официально поддерживается новая версия iOS и предыдущая версия.</span><span class="sxs-lookup"><span data-stu-id="21efd-205">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="21efd-206">Мобильная версия должна быть общедоступной, чтобы приложение Teams работало правильно.</span><span class="sxs-lookup"><span data-stu-id="21efd-206">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="21efd-207">Мобильные приложения распространяются и обновляются только через магазин приложений для соответствующей мобильной платформы.</span><span class="sxs-lookup"><span data-stu-id="21efd-207">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="21efd-208">Распространение мобильных приложений через MDM и загрузка неопубликованных приложений не поддерживаются корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="21efd-208">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="21efd-209">Как только мобильное приложение Teams будет установлено на поддерживаемой мобильной платформе, оно само будет поддерживаться, при условии что с момента выпуска текущей версии прошло не более трех месяцев.   </span><span class="sxs-lookup"><span data-stu-id="21efd-209">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![Значок, изображающий точку принятия решения](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="21efd-211">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="21efd-211">Decision Point</span></span>         |<span data-ttu-id="21efd-212">Существуют ли ограничения, мешающие пользователям установить на своих устройствах подходящий клиент Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="21efd-212">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Значок, изображающий дальнейшие действия](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="21efd-214">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="21efd-214">Next Steps</span></span>         |<span data-ttu-id="21efd-215">Если ваша организация ограничивает установку программного обеспечения, убедитесь в совместимости данного механизма с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="21efd-215">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="21efd-216">Примечание. Для установки клиента на Mac требуются права администратора, а на ПК — нет.</span><span class="sxs-lookup"><span data-stu-id="21efd-216">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="21efd-217">Управление обновлениями клиентов</span><span class="sxs-lookup"><span data-stu-id="21efd-217">Client update management</span></span>

<span data-ttu-id="21efd-218">Сейчас клиенты обновляются службой Microsoft Teams автоматически и без вмешательства ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="21efd-218">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="21efd-219">При выходе обновления клиент автоматически скачивает его, а после определенного периода неактивности приложения начинает процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="21efd-219">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="21efd-220">Конфигурации на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="21efd-220">Client-side configurations</span></span>

<span data-ttu-id="21efd-221">Сейчас не существует способа для настройки клиента администратором клиента, а также с помощью PowerShell, объектов групповой политики или реестра.</span><span class="sxs-lookup"><span data-stu-id="21efd-221">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="21efd-222">Параметры уведомлений</span><span class="sxs-lookup"><span data-stu-id="21efd-222">Notification settings</span></span>

<span data-ttu-id="21efd-223">Сейчас не существует способа для настройки параметров уведомлений на стороне клиента ИТ-администраторами.</span><span class="sxs-lookup"><span data-stu-id="21efd-223">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="21efd-224">Все эти параметры задает пользователь.</span><span class="sxs-lookup"><span data-stu-id="21efd-224">All notification options are set by the user.</span></span> <span data-ttu-id="21efd-225">Приведенный ниже рисунок показывает параметры клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="21efd-225">The figure below outlines the default client settings.</span></span>

![Снимок экрана с параметрами уведомлений.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a><span data-ttu-id="21efd-227">Пример сценария PowerShell — правило входящий брандмауэр</span><span class="sxs-lookup"><span data-stu-id="21efd-227">Sample PowerShell script - inbound firewall rule</span></span>

<span data-ttu-id="21efd-228">Этот пример скрипта, который нужно запускать на клиентских компьютерах в контексте учетной записи администратора с повышенными правами, создает правило входящих подключений брандмауэра для каждой папки пользователя, находящейся в c:\users.</span><span class="sxs-lookup"><span data-stu-id="21efd-228">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="21efd-229">Если Teams обнаруживает это правило, блокируется запрос для пользователей на создание правил брандмауэра, когда пользователи выполняют первый звонок из Teams.</span><span class="sxs-lookup"><span data-stu-id="21efd-229">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

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
