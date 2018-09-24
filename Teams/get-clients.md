---
title: Работа с клиентами для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vichau, majafry
localization_priority: Normal
search.appverid: MET150
description: Сведения об использовании различных клиентов, доступных для Microsoft Teams, включая веб-клиент, классический клиент (Windows и Mac), а также мобильный клиент (Android, iOS и Windows Phone).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9caef93f2303458d20c2d7e2142579edaae69748
ms.sourcegitcommit: c864a4b5337960deed01ff8c481326dbbd23c960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2018
ms.locfileid: "24975118"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="085f5-103">Работа с клиентами для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="085f5-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="085f5-104">Группами Майкрософт имеет клиентов для настольных компьютеров Windows и Mac, web и мобильных устройств (Android, iOS и Windows Phone).</span><span class="sxs-lookup"><span data-stu-id="085f5-104">Microsoft Teams has clients available for desktop (Windows and Mac), web, and mobile (Android,  iOS, and Windows Phone).</span></span> <span data-ttu-id="085f5-105">Все они нуждаются в активном подключении к Интернету и не поддерживают автономный режим.</span><span class="sxs-lookup"><span data-stu-id="085f5-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

<a name="desktop-client"></a><span data-ttu-id="085f5-106">Клиент рабочего стола</span><span class="sxs-lookup"><span data-stu-id="085f5-106">Desktop client</span></span>
--------------

> [!Tip]
> <span data-ttu-id="085f5-107">Просмотрите следующие сеанса, чтобы узнать о преимуществах рабочий стол Windows Client, планировании его и способе развертывания: [Группы Windows Desktop Client](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="085f5-107">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="085f5-108">Клиентское группами Майкрософт — это автономного приложения и в настоящее время не входит в Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="085f5-108">The Microsoft Teams desktop client is a standalone application and currently not part of Office 365 ProPlus.</span></span> <span data-ttu-id="085f5-109">Команды доступна для Windows (7 +), 32-разрядная и 64-разрядных версий и macOS (10.10 +).</span><span class="sxs-lookup"><span data-stu-id="085f5-109">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and macOS (10.10+).</span></span> <span data-ttu-id="085f5-110">В Windows группам требуется .NET Framework 4.5 или более поздней версии; Установщик команды будет предлагать установить ее автоматически, если она не была.</span><span class="sxs-lookup"><span data-stu-id="085f5-110">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="085f5-111">Настольных клиентов поддержки в режиме реального времени (аудио, видео и содержимого общего доступа) для группы собраний, вызывающий и частных индивидуального звонки из группы.</span><span class="sxs-lookup"><span data-stu-id="085f5-111">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="085f5-112">Настольных клиентов можно загрузить и установить конечными пользователями непосредственно из [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) при наличии соответствующих разрешений локального (права администратора не требуется для установки клиента групп на ПК, но требуется на компьютерах Mac).</span><span class="sxs-lookup"><span data-stu-id="085f5-112">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="085f5-113">ИТ-администраторов можно выбрать их предпочитаемый метод передавать файлы установки на компьютерах в своей организации, такие как System Center Configuration Manager (Windows) или Jamf Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="085f5-113">IT admins can choose their preferred method to distribute the installation files to computers in their organization, such as System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="085f5-114">Получение пакета MSI для рассылки Windows, видеть [Установка группами Майкрософт с помощью MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="085f5-114">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="085f5-115">Распространение посредством этих механизмов подходит только для начальной установки клиентов Microsoft Team, но не для дальнейших обновлений.</span><span class="sxs-lookup"><span data-stu-id="085f5-115">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="085f5-116">Windows</span><span class="sxs-lookup"><span data-stu-id="085f5-116">Windows</span></span>

<span data-ttu-id="085f5-117">Установка Microsoft Teams для Windows предоставляет скачиваемые установщики для 32- и 64-разрядной архитектуры.</span><span class="sxs-lookup"><span data-stu-id="085f5-117">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="085f5-118">Архитектура (32-разрядная и 64-разрядная версия) группами Майкрософт не зависит от архитектуры Windows и Office, которая устанавливается.</span><span class="sxs-lookup"><span data-stu-id="085f5-118">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="085f5-119">Клиент Windows развертывается в папке AppData внутри профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="085f5-119">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="085f5-120">Развертывание в локальный профиль пользователя позволяет установить клиент без повышенных прав.</span><span class="sxs-lookup"><span data-stu-id="085f5-120">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="085f5-121">Клиент Windows использует следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="085f5-121">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="085f5-122">% LocalAppData %\\Microsoft\\групп</span><span class="sxs-lookup"><span data-stu-id="085f5-122">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="085f5-123">% LocalAppData %\\Microsoft\\TeamsMeetingsAddin</span><span class="sxs-lookup"><span data-stu-id="085f5-123">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span></span>

- <span data-ttu-id="085f5-124">% AppData %\\Microsoft\\групп</span><span class="sxs-lookup"><span data-stu-id="085f5-124">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="085f5-125">% LocalAppData %\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="085f5-125">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="085f5-126">Когда пользователи впервые выполняют звонок через клиент Microsoft Teams, они могут заметить предупреждение с параметрами брандмауэра Windows, предлагающее пользователю разрешить взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="085f5-126">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="085f5-127">Следует ли игнорировать это сообщение, так как звонок будет работать, даже при закрытии предупреждение может проинструктировать пользователей.</span><span class="sxs-lookup"><span data-stu-id="085f5-127">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Снимок экрана с диалоговом окном "Оповещение системы безопасности Windows".](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="085f5-129">Конфигурация брандмауэра Windows будет изменена, даже если закрыть запрос, нажав кнопку "Отмена".</span><span class="sxs-lookup"><span data-stu-id="085f5-129">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="085f5-130">Создаются два правила входящего трафика для teams.exe с действием блокировки для протоколов TCP и UDP.</span><span class="sxs-lookup"><span data-stu-id="085f5-130">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="085f5-131">Mac</span><span class="sxs-lookup"><span data-stu-id="085f5-131">Mac</span></span>

<span data-ttu-id="085f5-132">Mac пользователи могут устанавливать групп с помощью файла установки PKG macOS компьютеров.</span><span class="sxs-lookup"><span data-stu-id="085f5-132">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="085f5-133">Для установки клиента Mac требуется административный доступ.</span><span class="sxs-lookup"><span data-stu-id="085f5-133">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="085f5-134">Клиент macOS устанавливается в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="085f5-134">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="085f5-135">Установка группы с помощью файла PKG</span><span class="sxs-lookup"><span data-stu-id="085f5-135">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="085f5-136">Из, [Страница загрузки групп](https://teams.microsoft.com/downloads)в разделе **Mac**, нажмите кнопку **загрузить**.</span><span class="sxs-lookup"><span data-stu-id="085f5-136">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="085f5-137">Дважды щелкните файл PKG.</span><span class="sxs-lookup"><span data-stu-id="085f5-137">Double click the PKG file.</span></span>
3. <span data-ttu-id="085f5-138">Следуйте указаниям мастера установки для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="085f5-138">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="085f5-139">Команды будет установлен в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="085f5-139">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="085f5-140">Это установки компьютера.</span><span class="sxs-lookup"><span data-stu-id="085f5-140">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="085f5-141">Во время установки PKG будет запрашивать учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="085f5-141">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="085f5-142">Пользователю необходимо ввести учетные данные администратора, независимо от того, является ли пользователь администратор.</span><span class="sxs-lookup"><span data-stu-id="085f5-142">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="085f5-143">Если в настоящее время установки на Рисунке рабочих групп и пользователя необходимо заменить ее установки PKG, пользователь должен:</span><span class="sxs-lookup"><span data-stu-id="085f5-143">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="085f5-144">Выйдите из приложения группы.</span><span class="sxs-lookup"><span data-stu-id="085f5-144">Exit the Teams app.</span></span>
2. <span data-ttu-id="085f5-145">Удаление приложения группы.</span><span class="sxs-lookup"><span data-stu-id="085f5-145">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="085f5-146">Установка файлов PKG.</span><span class="sxs-lookup"><span data-stu-id="085f5-146">Install the PKG file.</span></span>

<span data-ttu-id="085f5-147">ИТ-администраторов можно использовать управляемое развертывание групп передавать файлы установки для всех Макинтош в своей организации, такие как Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="085f5-147">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="085f5-148">При возникновении проблем при установке PKG свяжитесь с нами.</span><span class="sxs-lookup"><span data-stu-id="085f5-148">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="085f5-149">В разделе **свои отзывы и предложения** в конце этой статьи щелкните **отзыва о продукте**.</span><span class="sxs-lookup"><span data-stu-id="085f5-149">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="085f5-150">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="085f5-150">Web client</span></span> 
----------

<span data-ttu-id="085f5-151">Веб-клиент ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) — это полный функциональным клиент, который может использоваться с помощью различных браузерах.</span><span class="sxs-lookup"><span data-stu-id="085f5-151">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="085f5-152">Веб-клиент поддерживает звонков и собраний с помощью webRTC, поэтому нет не подключаемого модуля или загрузить, необходимые для выполнения команд в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="085f5-152">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="085f5-153">Браузер должен быть настроен отключена сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="085f5-153">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="085f5-154">Веб-клиент выполняет обнаружение версия браузера при подключении к [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="085f5-154">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="085f5-155">При обнаружении более версии Неподдерживаемый браузер, его можно было заблокируйте доступ к веб-интерфейс и Майкрософт рекомендует загружать пользователя клиента настольного компьютера или мобильного приложения.</span><span class="sxs-lookup"><span data-stu-id="085f5-155">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="085f5-156">Мобильные клиенты</span><span class="sxs-lookup"><span data-stu-id="085f5-156">Mobile clients</span></span>
--------------

<span data-ttu-id="085f5-157">Мобильные приложения Microsoft Teams доступны для Android, iOS и Windows Phone и предназначены для пользователей, участвующих в беседах на основе чата и выполняющих одноранговые звонки во время поездок.</span><span class="sxs-lookup"><span data-stu-id="085f5-157">The Microsoft Teams mobile apps are available for Android, iOS, and Windows Phones, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="085f5-158">Для мобильных приложений следует использовать соответствующий магазин: Google Play, Apple App Store или Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="085f5-158">For mobile apps, go to the relevant mobile store for Google Play, Apple App Store, and Microsoft Store.</span></span>

<span data-ttu-id="085f5-159">Для мобильных приложений Microsoft Teams поддерживаются следующие мобильные платформы:</span><span class="sxs-lookup"><span data-stu-id="085f5-159">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="085f5-160">**Android**: 4.4 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="085f5-160">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="085f5-161">**iOS**: 10.0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="085f5-161">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="085f5-162">Мобильной версии должны быть доступны для просмотра в порядке рабочие группы могут работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="085f5-162">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="085f5-163">Мобильные приложения распространяются и обновляются только через магазин приложений соответствующей платформы и недоступны для распространения через решения по управлению мобильными устройствами (MDM), а также для загрузки в неопубликованном виде.</span><span class="sxs-lookup"><span data-stu-id="085f5-163">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="085f5-165">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="085f5-165">Decision Point</span></span>         |<span data-ttu-id="085f5-166">Существуют ли ограничения, мешающие пользователям установить на своих устройствах подходящий клиент Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="085f5-166">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Значок дальнейших действий.](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="085f5-168">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="085f5-168">Next Steps</span></span>         |<span data-ttu-id="085f5-169">Если ваша организация ограничивает установку программного обеспечения, убедитесь в совместимости данного механизма с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="085f5-169">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="085f5-170">Примечание. Для установки клиента на Mac требуются права администратора, а на ПК — нет.</span><span class="sxs-lookup"><span data-stu-id="085f5-170">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |


  <span data-ttu-id="085f5-171"><span id="_Hlk477176062" class="anchor"></span>  Точка принятия решений. Существуют ли ограничения, мешающие пользователям установить на своих устройствах подходящий клиент Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="085f5-171"><span id="_Hlk477176062" class="anchor"></span>  Decision Point   Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>

<a name="client-update-management"></a><span data-ttu-id="085f5-172">Управление обновлениями клиентов</span><span class="sxs-lookup"><span data-stu-id="085f5-172">Client update management</span></span>
------------------------

<span data-ttu-id="085f5-173">Сейчас клиенты обновляются службой Microsoft Teams автоматически и без вмешательства ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="085f5-173">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="085f5-174">При выходе обновления клиент автоматически скачивает его, а после определенного периода неактивности приложения запускает процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="085f5-174">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="085f5-175">Конфигурации на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="085f5-175">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="085f5-176">Сейчас не существует способа для настройки клиента администратором клиента, а также с помощью PowerShell, объектов групповой политики или реестра.</span><span class="sxs-lookup"><span data-stu-id="085f5-176">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="085f5-177">Параметры уведомлений</span><span class="sxs-lookup"><span data-stu-id="085f5-177">Notification settings</span></span>
----------------------------

<span data-ttu-id="085f5-178">Сейчас не существует способа для настройки параметров уведомлений на стороне клиента ИТ-администраторами.</span><span class="sxs-lookup"><span data-stu-id="085f5-178">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="085f5-179">Все эти параметры задает пользователь.</span><span class="sxs-lookup"><span data-stu-id="085f5-179">All notification options are set by the user.</span></span> <span data-ttu-id="085f5-180">Приведенный ниже рисунок показывает параметры клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="085f5-180">The figure below outlines the default client settings.</span></span>

![Снимок экрана с параметрами уведомлений.](media/Get_clients_for_Microsoft_Teams_image6.png)
