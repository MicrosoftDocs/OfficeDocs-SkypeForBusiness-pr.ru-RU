---
title: Работа с клиентами для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Сведения об использовании различных клиентов, доступных для Microsoft Teams, включая веб-клиент, классический клиент (Windows и Mac), а также мобильный клиент (Android и iOS).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43344ac9ea00c15bcb4fb7518d727ccc9cff92de
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934717"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="0fd77-103">Работа с клиентами для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0fd77-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="0fd77-104">В Microsoft Teams доступен классический клиент (Windows и Mac), веб-клиент и мобильный клиент (Android и iOS).</span><span class="sxs-lookup"><span data-stu-id="0fd77-104">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android, iOS, and Windows Phone).</span></span> <span data-ttu-id="0fd77-105">Все они нуждаются в активном подключении к Интернету и не поддерживают автономный режим.</span><span class="sxs-lookup"><span data-stu-id="0fd77-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="0fd77-106">С 29 ноября 2018 г. вы больше не сможете использовать приложение Microsoft Teams для Windows 10 S (предварительная версия), доступное в Магазине Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="0fd77-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="0fd77-107">После 29 ноября рекомендуется использовать одно из приложений Teams, описанных ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0fd77-107">We recommend that you use one of the Teams apps described below in this article after November 29.</span></span>

<a name="desktop-client"></a><span data-ttu-id="0fd77-108">Классический клиент</span><span class="sxs-lookup"><span data-stu-id="0fd77-108">Desktop client</span></span>
--------------

> [!Tip]
> <span data-ttu-id="0fd77-109">Просмотрите следующий сеанс, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="0fd77-109">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="0fd77-110">Классический клиент Microsoft Teams представляет собой автономное приложение и сейчас не входит в состав Office 365 профессиональный плюс.</span><span class="sxs-lookup"><span data-stu-id="0fd77-110">Microsoft Teams desktop client is a standalone application and currently not part of Office Pro Plus.</span></span> <span data-ttu-id="0fd77-111">Teams доступен как для 32- и 64-разрядных версий Windows (7+), так и для macOS (10.10+).</span><span class="sxs-lookup"><span data-stu-id="0fd77-111">Microsoft Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and MacOS (10.10+).</span></span> <span data-ttu-id="0fd77-112">В Windows для Teams требуется платформа .NET Framework 4.5 или более поздней версии; установщик Teams предложит установить ее, если она отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0fd77-112">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="0fd77-113">Классические клиенты поддерживают взаимодействие в реальном времени (звук, видео и общий доступ к контенту) для собраний команды, групповых звонков и частных индивидуальных звонков.</span><span class="sxs-lookup"><span data-stu-id="0fd77-113">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling and private one-on-one calls.</span></span>

<span data-ttu-id="0fd77-114">При наличии подходящих локальных разрешений (для установки клиента Teams на Mac требуются права администратора, а на ПК — нет) пользователи могут скачать и установить классические клиенты прямо со страницы [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="0fd77-114">Desktop clients can be downloaded and installed by end users directly from https://teams.microsoft.com/downloads if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="0fd77-115">ИТ-администраторы могут использовать предпочитаемый способ распространения установочных файлов на компьютеры в своей организации, например System Center Configuration Manager (Windows) или Jamf Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="0fd77-115">IT admins can choose their preferred method to distribute the installation files to machines in their organization such as System Center Configuration Manager (Windows) or Casper Suite (MacOS).</span></span> <span data-ttu-id="0fd77-116">Сведения о получении MSI-пакета для распространения в Windows см. в статье [Установка Microsoft Teams с помощью MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="0fd77-116">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0fd77-117">Распространение посредством этих механизмов подходит только для начальной установки клиентов Microsoft Team, но не для дальнейших обновлений.</span><span class="sxs-lookup"><span data-stu-id="0fd77-117">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="0fd77-118">Windows</span><span class="sxs-lookup"><span data-stu-id="0fd77-118">Windows</span></span>

<span data-ttu-id="0fd77-119">Установка Microsoft Teams для Windows предоставляет скачиваемые установщики для 32- и 64-разрядной архитектуры.</span><span class="sxs-lookup"><span data-stu-id="0fd77-119">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="0fd77-120">Архитектура Microsoft Teams (32- или 64-разрядная) не зависит от архитектуры Windows или установленного набора Office.</span><span class="sxs-lookup"><span data-stu-id="0fd77-120">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Office that is installed.</span></span>

<span data-ttu-id="0fd77-121">Клиент Windows развертывается в папке AppData внутри профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fd77-121">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="0fd77-122">Развертывание в локальный профиль пользователя позволяет установить клиент без повышенных прав.</span><span class="sxs-lookup"><span data-stu-id="0fd77-122">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="0fd77-123">Клиент Windows использует следующие расположения:</span><span class="sxs-lookup"><span data-stu-id="0fd77-123">The Windows client is installed in the following locations:</span></span>

- <span data-ttu-id="0fd77-124">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="0fd77-124">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="0fd77-125">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span><span class="sxs-lookup"><span data-stu-id="0fd77-125">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span></span>

- <span data-ttu-id="0fd77-126">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="0fd77-126">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="0fd77-127">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="0fd77-127">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="0fd77-128">Когда пользователи впервые выполняют звонок через клиент Microsoft Teams, они могут заметить предупреждение с параметрами брандмауэра Windows, предлагающее пользователю разрешить взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="0fd77-128">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="0fd77-129">Можно попросить пользователей игнорировать это сообщение, так как звонок будет работать даже при закрытии предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0fd77-129">Users may be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Снимок экрана с диалоговом окном "Оповещение системы безопасности Windows".](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="0fd77-131">Конфигурация брандмауэра Windows будет изменена, даже если закрыть запрос, нажав кнопку "Отмена".</span><span class="sxs-lookup"><span data-stu-id="0fd77-131">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="0fd77-132">Создаются два правила входящего трафика для teams.exe с действием блокировки для протоколов TCP и UDP.</span><span class="sxs-lookup"><span data-stu-id="0fd77-132">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="0fd77-133">Mac</span><span class="sxs-lookup"><span data-stu-id="0fd77-133">Mac</span></span>

<span data-ttu-id="0fd77-134">Пользователи Mac могут установить Teams с помощью файла установки PKG для компьютеров macOS.</span><span class="sxs-lookup"><span data-stu-id="0fd77-134">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="0fd77-135">Для установки клиента Mac требуется административный доступ.</span><span class="sxs-lookup"><span data-stu-id="0fd77-135">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="0fd77-136">Клиент macOS устанавливается в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="0fd77-136">The Mac OSX client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="0fd77-137">Установка Teams с помощью PKG-файла</span><span class="sxs-lookup"><span data-stu-id="0fd77-137">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="0fd77-138">На [странице скачивания Teams](https://teams.microsoft.com/downloads) в разделе **Mac** нажмите кнопку **Скачать**.</span><span class="sxs-lookup"><span data-stu-id="0fd77-138">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="0fd77-139">Дважды щелкните PKG-файл.</span><span class="sxs-lookup"><span data-stu-id="0fd77-139">Double click the PKG file.</span></span>
3. <span data-ttu-id="0fd77-140">Для завершения установки следуйте инструкциям мастера.</span><span class="sxs-lookup"><span data-stu-id="0fd77-140">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="0fd77-141">Teams установится в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="0fd77-141">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="0fd77-142">Это установка на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="0fd77-142">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="0fd77-143">Во время установки PKG запросит учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="0fd77-143">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="0fd77-144">Пользователю потребуется ввести учетные данные администратора независимо от того, является ли он администратором.</span><span class="sxs-lookup"><span data-stu-id="0fd77-144">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="0fd77-145">Если пользователь в настоящее время использует установку DMG приложения Teams и хочет заменить ее установкой PKG, следует сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="0fd77-145">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="0fd77-146">Выйти из приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="0fd77-146">Exit the Teams app.</span></span>
2. <span data-ttu-id="0fd77-147">Удалить приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="0fd77-147">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="0fd77-148">Установить PKG-файл.</span><span class="sxs-lookup"><span data-stu-id="0fd77-148">Install the PKG file.</span></span>

<span data-ttu-id="0fd77-149">ИТ-администраторы могут использовать средство управляемого развертывания Teams для распространения установочных файлов на все компьютеры Mac в организации, например Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="0fd77-149">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="0fd77-150">Сообщите нам, если у вас возникают проблемы при установке PKG.</span><span class="sxs-lookup"><span data-stu-id="0fd77-150">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="0fd77-151">В разделе **Обратная связь** в конце этой статьи нажмите кнопку **Отзыв о продукте**.</span><span class="sxs-lookup"><span data-stu-id="0fd77-151">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="0fd77-152">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="0fd77-152">Web client</span></span> 
----------

<span data-ttu-id="0fd77-153">Веб-клиент ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) представляет собой полнофункциональный клиент, который можно использовать в различных браузерах.</span><span class="sxs-lookup"><span data-stu-id="0fd77-153">The web client (https://teams.microsoft.com) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="0fd77-154">Веб-клиент поддерживает звонки и собрания с помощью webRTC, поэтому не требуется подключаемый модуль или скачивание для запуска Teams в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="0fd77-154">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="0fd77-155">В браузере должно быть разрешено использование сторонних файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="0fd77-155">The browser must also be configured to allow 3rd-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="0fd77-156">Веб-клиент определяет версию браузера при подключении к сайту [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="0fd77-156">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="0fd77-157">В случае обнаружения неподдерживаемой версии блокируется доступ к веб-интерфейсу и пользователю рекомендуется скачать классический клиент или мобильное приложение.</span><span class="sxs-lookup"><span data-stu-id="0fd77-157">The Web client performs browser version detection upon connecting to https://teams.microsoft.com and if an unsupported browser version is detected, it will block access to the Web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="0fd77-158">Мобильные клиенты</span><span class="sxs-lookup"><span data-stu-id="0fd77-158">Mobile clients</span></span>
--------------

<span data-ttu-id="0fd77-159">Мобильные приложения Microsoft Teams доступны для Android и iOS и предназначены для пользователей, участвующих в беседах на основе чата и выполняющих одноранговые звонки во время поездок.</span><span class="sxs-lookup"><span data-stu-id="0fd77-159">The Microsoft Teams mobile apps are available for Android, iOS, and Windows Phones, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="0fd77-160">Для мобильных приложений следует использовать соответствующий магазин: Google Play и Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="0fd77-160">For mobile apps, go to the relevant mobile store for Google Play, Apple App Store, and Microsoft Store.</span></span> <span data-ttu-id="0fd77-161">Приложение Windows Phone перестало поддерживаться 20 июля 2018 г. и может перестать работать.</span><span class="sxs-lookup"><span data-stu-id="0fd77-161">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="0fd77-162">Для мобильных приложений Microsoft Teams поддерживаются следующие мобильные платформы:</span><span class="sxs-lookup"><span data-stu-id="0fd77-162">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="0fd77-163">**Android**: 4.4 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="0fd77-163">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="0fd77-164">**iOS**: 10.0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="0fd77-164">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="0fd77-165">Мобильная версия должна быть общедоступной, чтобы приложение Teams работало правильно.</span><span class="sxs-lookup"><span data-stu-id="0fd77-165">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="0fd77-166">Мобильные приложения распространяются и обновляются только через магазин приложений соответствующей платформы и недоступны для распространения через решения по управлению мобильными устройствами (MDM), а также для загрузки в неопубликованном виде.</span><span class="sxs-lookup"><span data-stu-id="0fd77-166">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="0fd77-168">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="0fd77-168">Decision Point</span></span>         |<span data-ttu-id="0fd77-169">Существуют ли ограничения, мешающие пользователям установить на своих устройствах подходящий клиент Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="0fd77-169">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Значок дальнейших действий.](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="0fd77-171">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="0fd77-171">Next Steps</span></span>         |<span data-ttu-id="0fd77-172">Если ваша организация ограничивает установку программного обеспечения, убедитесь в совместимости данного механизма с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0fd77-172">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="0fd77-173">Примечание. Для установки клиента на Mac требуются права администратора, а на ПК — нет.</span><span class="sxs-lookup"><span data-stu-id="0fd77-173">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

<a name="client-update-management"></a><span data-ttu-id="0fd77-174">Управление обновлениями клиентов</span><span class="sxs-lookup"><span data-stu-id="0fd77-174">Client update management</span></span>
------------------------

<span data-ttu-id="0fd77-175">Сейчас клиенты обновляются службой Microsoft Teams автоматически и без вмешательства ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="0fd77-175">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="0fd77-176">При выходе обновления клиент автоматически скачивает его, а после определенного периода неактивности приложения запускает процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="0fd77-176">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="0fd77-177">Конфигурации на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="0fd77-177">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="0fd77-178">Сейчас не существует способа для настройки клиента администратором клиента, а также с помощью PowerShell, объектов групповой политики или реестра.</span><span class="sxs-lookup"><span data-stu-id="0fd77-178">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="0fd77-179">Параметры уведомлений</span><span class="sxs-lookup"><span data-stu-id="0fd77-179">Notification settings</span></span>
----------------------------

<span data-ttu-id="0fd77-180">Сейчас не существует способа для настройки параметров уведомлений на стороне клиента ИТ-администраторами.</span><span class="sxs-lookup"><span data-stu-id="0fd77-180">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="0fd77-181">Все эти параметры задает пользователь.</span><span class="sxs-lookup"><span data-stu-id="0fd77-181">All notification options are set by the user.</span></span> <span data-ttu-id="0fd77-182">Приведенный ниже рисунок показывает параметры клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0fd77-182">The figure below outlines the default client settings.</span></span>

![Снимок экрана с параметрами уведомлений.](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a><span data-ttu-id="0fd77-184">Пример скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="0fd77-184">Sample PowerShell Script</span></span>
----------------------------

<span data-ttu-id="0fd77-185">Этот пример скрипта, который нужно запускать на клиентских компьютерах в контексте учетной записи администратора с повышенными правами, создает правило входящих подключений брандмауэра для каждой папки пользователя, находящейся в c:\users.</span><span class="sxs-lookup"><span data-stu-id="0fd77-185">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="0fd77-186">Если Teams обнаруживает это правило, блокируется запрос для пользователей на создание правил брандмауэра, когда пользователи выполняют первый звонок из Teams.</span><span class="sxs-lookup"><span data-stu-id="0fd77-186">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

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
