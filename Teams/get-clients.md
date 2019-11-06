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
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f7a1cd3002135e2327ca4953ddfbb5b0393242d
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "37979702"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="7d153-103">Работа с клиентами для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d153-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="7d153-104">В Microsoft Teams доступны клиенты для настольных компьютеров (Windows, Mac и Linux), веб-сайтов и мобильных устройств (Android и iOS).</span><span class="sxs-lookup"><span data-stu-id="7d153-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="7d153-105">Все они нуждаются в активном подключении к Интернету и не поддерживают автономный режим.</span><span class="sxs-lookup"><span data-stu-id="7d153-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="7d153-106">С 29 ноября 2018 г. вы больше не сможете использовать приложение Microsoft Teams для Windows 10 S (предварительная версия), доступное в Магазине Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="7d153-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="7d153-107">Вместо этого теперь вы можете скачать и установить классический клиент Teams на устройствах с Windows 10 в S-режиме.</span><span class="sxs-lookup"><span data-stu-id="7d153-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="7d153-108">Чтобы скачать классический клиент, перейдите по ссылке [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="7d153-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="7d153-109">Сборки MSI для классического клиента Teams пока недоступны на устройствах с Windows 10 в S-режиме.</span><span class="sxs-lookup"><span data-stu-id="7d153-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="7d153-110">Дополнительные сведения о Windows 10 в S-режиме см. в статье [Знакомство с Windows 10 в S-режиме](https://www.microsoft.com/windows/s-mode).</span><span class="sxs-lookup"><span data-stu-id="7d153-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="7d153-111">Классический клиент</span><span class="sxs-lookup"><span data-stu-id="7d153-111">Desktop client</span></span>

> [!Tip]
> <span data-ttu-id="7d153-112">Просмотрите следующий сеанс, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="7d153-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="7d153-113">Классический клиент Microsoft Teams представляет собой автономное приложение, а также [входит в состав Office 365 профессиональный плюс](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="7d153-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="7d153-114">Teams поддерживается для Windows (7 +), 32-bit и 64-bit Versions, macOS (10.10 +) и Linux (in `.deb` и `.rpm` formats).</span><span class="sxs-lookup"><span data-stu-id="7d153-114">Teams is available for Windows (7+), both 32-bit and 64-bit versions, macOS (10.10+), and Linux (in `.deb` and `.rpm` formats.).</span></span> <span data-ttu-id="7d153-115">В Windows для Teams требуется платформа .NET Framework 4.5 или более поздней версии; установщик Teams предложит установить ее, если она отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d153-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="7d153-116">В Linux диспетчеры пакетов, такие как Апт и Юм, будут пытаться установить любые требования.</span><span class="sxs-lookup"><span data-stu-id="7d153-116">On Linux, package managers such as apt and yum will try to install any requirements for you.</span></span> <span data-ttu-id="7d153-117">Однако в противном случае вам потребуется установить любые требования, предъявляемые перед установкой Teams в Linux.</span><span class="sxs-lookup"><span data-stu-id="7d153-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="7d153-118">Классические клиенты поддерживают взаимодействие в реальном времени (звук, видео и общий доступ к контенту) для собраний команды, групповых звонков и частных индивидуальных звонков.</span><span class="sxs-lookup"><span data-stu-id="7d153-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="7d153-119">При наличии подходящих локальных разрешений (для установки клиента Teams на Mac требуются права администратора, а на ПК — нет) пользователи могут скачать и установить классические клиенты прямо со страницы [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="7d153-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="7d153-120">ИТ — администраторы могут выбрать предпочтительный способ распространения установочных файлов на компьютеры в своей организации.</span><span class="sxs-lookup"><span data-stu-id="7d153-120">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="7d153-121">Некоторые примеры включают System Center Configuration Manager (Windows) или Жамф Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="7d153-121">Some examples include System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="7d153-122">Сведения о получении MSI-пакета для распространения в Windows см. в статье [Установка Microsoft Teams с помощью MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="7d153-122">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="7d153-123">Распространение посредством этих механизмов подходит только для начальной установки клиентов Microsoft Team, но не для дальнейших обновлений.</span><span class="sxs-lookup"><span data-stu-id="7d153-123">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="7d153-124">Windows</span><span class="sxs-lookup"><span data-stu-id="7d153-124">Windows</span></span>

<span data-ttu-id="7d153-125">Установка Microsoft Teams для Windows предоставляет скачиваемые установщики для 32- и 64-разрядной архитектуры.</span><span class="sxs-lookup"><span data-stu-id="7d153-125">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="7d153-126">Архитектура Microsoft Teams (32- или 64-разрядная) не зависит от архитектуры Windows или установленного набора Office.</span><span class="sxs-lookup"><span data-stu-id="7d153-126">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="7d153-127">Клиент Windows развертывается в папке AppData внутри профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d153-127">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="7d153-128">Развертывание в локальный профиль пользователя позволяет установить клиент без повышенных прав.</span><span class="sxs-lookup"><span data-stu-id="7d153-128">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="7d153-129">Клиент Windows использует следующие расположения:</span><span class="sxs-lookup"><span data-stu-id="7d153-129">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="7d153-130">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="7d153-130">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="7d153-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="7d153-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="7d153-132">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="7d153-132">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="7d153-133">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="7d153-133">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="7d153-134">Когда пользователи впервые выполняют звонок через клиент Microsoft Teams, они могут заметить предупреждение с параметрами брандмауэра Windows, предлагающее пользователю разрешить взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="7d153-134">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="7d153-135">Можно попросить пользователей игнорировать это сообщение, так как звонок будет работать даже при закрытии предупреждения.</span><span class="sxs-lookup"><span data-stu-id="7d153-135">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Снимок экрана с диалоговом окном "Оповещение системы безопасности Windows".](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="7d153-137">Конфигурация брандмауэра Windows будет изменена, даже если закрыть запрос, нажав кнопку "Отмена".</span><span class="sxs-lookup"><span data-stu-id="7d153-137">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="7d153-138">Создаются два правила входящего трафика для teams.exe с действием блокировки для протоколов TCP и UDP.</span><span class="sxs-lookup"><span data-stu-id="7d153-138">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="7d153-139">Mac</span><span class="sxs-lookup"><span data-stu-id="7d153-139">Mac</span></span>

<span data-ttu-id="7d153-140">Пользователи Mac могут установить Teams с помощью файла установки PKG для компьютеров macOS.</span><span class="sxs-lookup"><span data-stu-id="7d153-140">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="7d153-141">Для установки клиента Mac требуется административный доступ.</span><span class="sxs-lookup"><span data-stu-id="7d153-141">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="7d153-142">Клиент macOS устанавливается в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="7d153-142">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="7d153-143">Установка Teams с помощью PKG-файла</span><span class="sxs-lookup"><span data-stu-id="7d153-143">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="7d153-144">На [странице скачивания Teams](https://teams.microsoft.com/downloads) в разделе **Mac** нажмите кнопку **Скачать**.</span><span class="sxs-lookup"><span data-stu-id="7d153-144">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="7d153-145">Дважды щелкните PKG-файл.</span><span class="sxs-lookup"><span data-stu-id="7d153-145">Double click the PKG file.</span></span>
3. <span data-ttu-id="7d153-146">Для завершения установки следуйте инструкциям мастера.</span><span class="sxs-lookup"><span data-stu-id="7d153-146">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="7d153-147">Teams установится в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="7d153-147">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="7d153-148">Это установка на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="7d153-148">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="7d153-149">Во время установки PKG запросит учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="7d153-149">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="7d153-150">Пользователю потребуется ввести учетные данные администратора независимо от того, является ли он администратором.</span><span class="sxs-lookup"><span data-stu-id="7d153-150">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="7d153-151">Если пользователь в настоящее время использует установку DMG приложения Teams и хочет заменить ее установкой PKG, следует сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="7d153-151">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="7d153-152">Выйти из приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="7d153-152">Exit the Teams app.</span></span>
2. <span data-ttu-id="7d153-153">Удалить приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="7d153-153">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="7d153-154">Установить PKG-файл.</span><span class="sxs-lookup"><span data-stu-id="7d153-154">Install the PKG file.</span></span>

<span data-ttu-id="7d153-155">ИТ-администраторы могут использовать средство управляемого развертывания Teams для распространения установочных файлов на все компьютеры Mac в организации, например Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="7d153-155">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="7d153-156">Сообщите нам, если у вас возникают проблемы при установке PKG.</span><span class="sxs-lookup"><span data-stu-id="7d153-156">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="7d153-157">В разделе **Обратная связь** в конце этой статьи нажмите кнопку **Отзыв о продукте**.</span><span class="sxs-lookup"><span data-stu-id="7d153-157">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="7d153-158">Linux</span><span class="sxs-lookup"><span data-stu-id="7d153-158">Linux</span></span>

<span data-ttu-id="7d153-159">Пользователи смогут устанавливать собственные пакеты Linux в `.deb` и `.rpm` форматах.</span><span class="sxs-lookup"><span data-stu-id="7d153-159">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>

> [!NOTE] 
> <span data-ttu-id="7d153-160">Клиент Teams для Linux доступен в ограниченном предварительном просмотре.</span><span class="sxs-lookup"><span data-stu-id="7d153-160">The Teams on Linux client is available in limited preview.</span></span> <span data-ttu-id="7d153-161">Отправлять ошибки с `Report a Problem` помощью клиента.</span><span class="sxs-lookup"><span data-stu-id="7d153-161">Submit bugs using `Report a Problem` from within the client.</span></span> <span data-ttu-id="7d153-162">Известные проблемы можно найти в разделе [Известные проблемы](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7d153-162">For known issues, see [Known Issues](Known-issues.md).</span></span>

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="7d153-163">Установка Teams с помощью пакета DEB</span><span class="sxs-lookup"><span data-stu-id="7d153-163">Install Teams using DEB package</span></span>

1. <span data-ttu-id="7d153-164">Скачайте пакет https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="7d153-164">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="7d153-165">(Предварительная версия клиента Linux ограничена, и он будет запущен в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="7d153-165">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="7d153-166">Если вы не видите клиент Linux на странице Загружаемые файлы, он пока еще не запущен.)</span><span class="sxs-lookup"><span data-stu-id="7d153-166">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="7d153-167">Установите одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="7d153-167">Install using one of the following:</span></span>  
    - <span data-ttu-id="7d153-168">Откройте средство для управления пакетом и пройдите по установке самоуправляемого приложения для Linux.</span><span class="sxs-lookup"><span data-stu-id="7d153-168">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="7d153-169">Или, если вы любите контакт, введите:`sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="7d153-169">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="7d153-170">Вы можете запускать команды с помощью действий или через терминал, `Teams`вводя текст.</span><span class="sxs-lookup"><span data-stu-id="7d153-170">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="7d153-171">Установка Teams с помощью пакета RPM</span><span class="sxs-lookup"><span data-stu-id="7d153-171">Install Teams using RPM package</span></span>

1. <span data-ttu-id="7d153-172">Скачайте пакет https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="7d153-172">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="7d153-173">(Предварительная версия клиента Linux ограничена, и он будет запущен в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="7d153-173">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="7d153-174">Если вы не видите клиент Linux на странице Загружаемые файлы, он пока еще не запущен.)</span><span class="sxs-lookup"><span data-stu-id="7d153-174">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="7d153-175">Установите одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="7d153-175">Install using one of the following:</span></span>
    - <span data-ttu-id="7d153-176">Откройте средство для управления пакетом и пройдите по установке самоуправляемого приложения для Linux.</span><span class="sxs-lookup"><span data-stu-id="7d153-176">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="7d153-177">Или, если вы любите контакт, введите:`sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="7d153-177">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="7d153-178">Вы можете запускать команды с помощью действий или через терминал, `Teams`вводя текст.</span><span class="sxs-lookup"><span data-stu-id="7d153-178">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

## <a name="web-client"></a><span data-ttu-id="7d153-179">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="7d153-179">Web client</span></span> 

<span data-ttu-id="7d153-180">Веб-клиент ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) представляет собой полнофункциональный клиент, который можно использовать в различных браузерах.</span><span class="sxs-lookup"><span data-stu-id="7d153-180">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="7d153-181">Веб-клиент поддерживает звонки и собрания с помощью webRTC, поэтому не требуется подключаемый модуль или скачивание для запуска Teams в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="7d153-181">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="7d153-182">В браузере должно быть разрешено использование сторонних файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="7d153-182">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="7d153-183">Веб-клиент определяет версию браузера при подключении к сайту [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="7d153-183">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="7d153-184">В случае обнаружения неподдерживаемой версии блокируется доступ к веб-интерфейсу и пользователю рекомендуется скачать классический клиент или мобильное приложение.</span><span class="sxs-lookup"><span data-stu-id="7d153-184">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="7d153-185">Мобильные клиенты</span><span class="sxs-lookup"><span data-stu-id="7d153-185">Mobile clients</span></span>

<span data-ttu-id="7d153-186">Мобильные приложения Microsoft Teams доступны для Android и iOS и предназначены для пользователей, участвующих в беседах на основе чата и выполняющих одноранговые звонки во время поездок.</span><span class="sxs-lookup"><span data-stu-id="7d153-186">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="7d153-187">Для мобильных приложений следует использовать соответствующий магазин: Google Play и Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="7d153-187">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="7d153-188">Приложение Windows Phone перестало поддерживаться 20 июля 2018 г. и может перестать работать.</span><span class="sxs-lookup"><span data-stu-id="7d153-188">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="7d153-189">Для мобильных приложений Microsoft Teams поддерживаются следующие мобильные платформы:</span><span class="sxs-lookup"><span data-stu-id="7d153-189">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="7d153-190">**Android**: 4.4 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="7d153-190">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="7d153-191">**iOS**: 10.0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="7d153-191">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="7d153-192">Мобильная версия должна быть общедоступной, чтобы приложение Teams работало правильно.</span><span class="sxs-lookup"><span data-stu-id="7d153-192">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="7d153-193">Мобильные приложения распространяются и обновляются только через магазин приложений для соответствующей мобильной платформы.</span><span class="sxs-lookup"><span data-stu-id="7d153-193">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="7d153-194">Распространение мобильных приложений через MDM и загрузка неопубликованных приложений не поддерживаются корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7d153-194">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="7d153-195">Как только мобильное приложение Teams будет установлено на поддерживаемой мобильной платформе, оно само будет поддерживаться, при условии что с момента выпуска текущей версии прошло не более трех месяцев.   </span><span class="sxs-lookup"><span data-stu-id="7d153-195">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![Значок, изображающий точку принятия решения](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="7d153-197">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="7d153-197">Decision Point</span></span>         |<span data-ttu-id="7d153-198">Существуют ли ограничения, мешающие пользователям установить на своих устройствах подходящий клиент Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="7d153-198">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Значок, изображающий дальнейшие действия](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="7d153-200">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7d153-200">Next Steps</span></span>         |<span data-ttu-id="7d153-201">Если ваша организация ограничивает установку программного обеспечения, убедитесь в совместимости данного механизма с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7d153-201">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="7d153-202">Примечание. Для установки клиента на Mac требуются права администратора, а на ПК — нет.</span><span class="sxs-lookup"><span data-stu-id="7d153-202">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="7d153-203">Управление обновлениями клиентов</span><span class="sxs-lookup"><span data-stu-id="7d153-203">Client update management</span></span>

<span data-ttu-id="7d153-204">Сейчас клиенты обновляются службой Microsoft Teams автоматически и без вмешательства ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="7d153-204">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="7d153-205">При выходе обновления клиент автоматически скачивает его, а после определенного периода неактивности приложения начинает процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="7d153-205">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="7d153-206">Конфигурации на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="7d153-206">Client-side configurations</span></span>

<span data-ttu-id="7d153-207">Сейчас не существует способа для настройки клиента администратором клиента, а также с помощью PowerShell, объектов групповой политики или реестра.</span><span class="sxs-lookup"><span data-stu-id="7d153-207">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="7d153-208">Параметры уведомлений</span><span class="sxs-lookup"><span data-stu-id="7d153-208">Notification settings</span></span>

<span data-ttu-id="7d153-209">Сейчас не существует способа для настройки параметров уведомлений на стороне клиента ИТ-администраторами.</span><span class="sxs-lookup"><span data-stu-id="7d153-209">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="7d153-210">Все эти параметры задает пользователь.</span><span class="sxs-lookup"><span data-stu-id="7d153-210">All notification options are set by the user.</span></span> <span data-ttu-id="7d153-211">Приведенный ниже рисунок показывает параметры клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7d153-211">The figure below outlines the default client settings.</span></span>

![Снимок экрана с параметрами уведомлений.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a><span data-ttu-id="7d153-213">Пример скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d153-213">Sample PowerShell Script</span></span>

<span data-ttu-id="7d153-214">Этот пример скрипта, который нужно запускать на клиентских компьютерах в контексте учетной записи администратора с повышенными правами, создает правило входящих подключений брандмауэра для каждой папки пользователя, находящейся в c:\users.</span><span class="sxs-lookup"><span data-stu-id="7d153-214">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="7d153-215">Если Teams обнаруживает это правило, блокируется запрос для пользователей на создание правил брандмауэра, когда пользователи выполняют первый звонок из Teams.</span><span class="sxs-lookup"><span data-stu-id="7d153-215">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
