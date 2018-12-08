---
title: Работа с клиентами для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Сведения об использовании различных клиентов недоступны для групп Майкрософт, которые включать web, рабочий стол (Windows и Mac) и мобильные устройства (Android и операций ввода-вывода).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: dfe4febe5d086af6914660bffb667942b9d00c25
ms.sourcegitcommit: ea6ee8ce28e82fcd7c07554c3428ae242d6f04da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "27201359"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="d0d58-103">Работа с клиентами для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d0d58-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="d0d58-104">Группами Майкрософт имеет клиентов для настольных компьютеров Windows и Mac, web и мобильных устройств (Android и операций ввода-вывода).</span><span class="sxs-lookup"><span data-stu-id="d0d58-104">Microsoft Teams has clients available for desktop (Windows and Mac), web, and mobile (Android and  iOS).</span></span> <span data-ttu-id="d0d58-105">Все они нуждаются в активном подключении к Интернету и не поддерживают автономный режим.</span><span class="sxs-lookup"><span data-stu-id="d0d58-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="d0d58-106">Эффективное 29 ноября 2018, вы больше не сможете использовать группами Майкрософт для приложения Windows 10 S (Предварительная версия), доступные из хранилища Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0d58-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="d0d58-107">Мы рекомендуем использовать одну из команд приложения, описанного ниже в этой статье после 29 ноября.</span><span class="sxs-lookup"><span data-stu-id="d0d58-107">We recommend that you use one of the Teams apps described below in this article after November 29.</span></span>

<a name="desktop-client"></a><span data-ttu-id="d0d58-108">Клиент рабочего стола</span><span class="sxs-lookup"><span data-stu-id="d0d58-108">Desktop client</span></span>
--------------

> [!Tip]
> <span data-ttu-id="d0d58-109">Просмотрите следующие сеанса, чтобы узнать о преимуществах рабочий стол Windows Client, планировании его и способе развертывания: [Группы Windows Desktop Client](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="d0d58-109">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="d0d58-110">Клиентское группами Майкрософт — это автономного приложения и в настоящее время не входит в Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="d0d58-110">The Microsoft Teams desktop client is a standalone application and currently not part of Office 365 ProPlus.</span></span> <span data-ttu-id="d0d58-111">Команды доступна для Windows (7 +), 32-разрядная и 64-разрядных версий и macOS (10.10 +).</span><span class="sxs-lookup"><span data-stu-id="d0d58-111">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and macOS (10.10+).</span></span> <span data-ttu-id="d0d58-112">В Windows группам требуется .NET Framework 4.5 или более поздней версии; Установщик команды будет предлагать установить ее автоматически, если она не была.</span><span class="sxs-lookup"><span data-stu-id="d0d58-112">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="d0d58-113">Настольных клиентов поддержки в режиме реального времени (аудио, видео и содержимого общего доступа) для группы собраний, вызывающий и частных индивидуального звонки из группы.</span><span class="sxs-lookup"><span data-stu-id="d0d58-113">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="d0d58-114">Настольных клиентов можно загрузить и установить конечными пользователями непосредственно из [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) при наличии соответствующих разрешений локального (права администратора не требуется для установки клиента групп на ПК, но требуется на компьютерах Mac).</span><span class="sxs-lookup"><span data-stu-id="d0d58-114">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="d0d58-115">ИТ-администраторов можно выбрать их предпочитаемый метод передавать файлы установки на компьютерах в своей организации, такие как System Center Configuration Manager (Windows) или Jamf Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="d0d58-115">IT admins can choose their preferred method to distribute the installation files to computers in their organization, such as System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="d0d58-116">Получение пакета MSI для рассылки Windows, видеть [Установка группами Майкрософт с помощью MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="d0d58-116">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d0d58-117">Распространение посредством этих механизмов подходит только для начальной установки клиентов Microsoft Team, но не для дальнейших обновлений.</span><span class="sxs-lookup"><span data-stu-id="d0d58-117">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="d0d58-118">Windows</span><span class="sxs-lookup"><span data-stu-id="d0d58-118">Windows</span></span>

<span data-ttu-id="d0d58-119">Установка Microsoft Teams для Windows предоставляет скачиваемые установщики для 32- и 64-разрядной архитектуры.</span><span class="sxs-lookup"><span data-stu-id="d0d58-119">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="d0d58-120">Архитектура (32-разрядная и 64-разрядная версия) группами Майкрософт не зависит от архитектуры Windows и Office, которая устанавливается.</span><span class="sxs-lookup"><span data-stu-id="d0d58-120">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="d0d58-121">Клиент Windows развертывается в папке AppData внутри профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="d0d58-121">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="d0d58-122">Развертывание в локальный профиль пользователя позволяет установить клиент без повышенных прав.</span><span class="sxs-lookup"><span data-stu-id="d0d58-122">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="d0d58-123">Клиент Windows использует следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="d0d58-123">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="d0d58-124">% LocalAppData %\\Microsoft\\групп</span><span class="sxs-lookup"><span data-stu-id="d0d58-124">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="d0d58-125">% LocalAppData %\\Microsoft\\TeamsMeetingsAddin</span><span class="sxs-lookup"><span data-stu-id="d0d58-125">%LocalAppData%\\Microsoft\\TeamsMeetingsAddin</span></span>

- <span data-ttu-id="d0d58-126">% AppData %\\Microsoft\\групп</span><span class="sxs-lookup"><span data-stu-id="d0d58-126">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="d0d58-127">% LocalAppData %\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="d0d58-127">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="d0d58-128">Когда пользователи впервые выполняют звонок через клиент Microsoft Teams, они могут заметить предупреждение с параметрами брандмауэра Windows, предлагающее пользователю разрешить взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="d0d58-128">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="d0d58-129">Следует ли игнорировать это сообщение, так как звонок будет работать, даже при закрытии предупреждение может проинструктировать пользователей.</span><span class="sxs-lookup"><span data-stu-id="d0d58-129">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Снимок экрана с диалоговом окном "Оповещение системы безопасности Windows".](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="d0d58-131">Конфигурация брандмауэра Windows будет изменена, даже если закрыть запрос, нажав кнопку "Отмена".</span><span class="sxs-lookup"><span data-stu-id="d0d58-131">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="d0d58-132">Создаются два правила входящего трафика для teams.exe с действием блокировки для протоколов TCP и UDP.</span><span class="sxs-lookup"><span data-stu-id="d0d58-132">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="d0d58-133">Mac</span><span class="sxs-lookup"><span data-stu-id="d0d58-133">Mac</span></span>

<span data-ttu-id="d0d58-134">Mac пользователи могут устанавливать групп с помощью файла установки PKG macOS компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d0d58-134">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="d0d58-135">Для установки клиента Mac требуется административный доступ.</span><span class="sxs-lookup"><span data-stu-id="d0d58-135">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="d0d58-136">Клиент macOS устанавливается в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="d0d58-136">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="d0d58-137">Установка группы с помощью файла PKG</span><span class="sxs-lookup"><span data-stu-id="d0d58-137">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="d0d58-138">Из, [Страница загрузки групп](https://teams.microsoft.com/downloads)в разделе **Mac**, нажмите кнопку **загрузить**.</span><span class="sxs-lookup"><span data-stu-id="d0d58-138">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="d0d58-139">Дважды щелкните файл PKG.</span><span class="sxs-lookup"><span data-stu-id="d0d58-139">Double click the PKG file.</span></span>
3. <span data-ttu-id="d0d58-140">Следуйте указаниям мастера установки для завершения установки.</span><span class="sxs-lookup"><span data-stu-id="d0d58-140">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="d0d58-141">Команды будет установлен в папку /Applications.</span><span class="sxs-lookup"><span data-stu-id="d0d58-141">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="d0d58-142">Это установки компьютера.</span><span class="sxs-lookup"><span data-stu-id="d0d58-142">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="d0d58-143">Во время установки PKG будет запрашивать учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="d0d58-143">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="d0d58-144">Пользователю необходимо ввести учетные данные администратора, независимо от того, является ли пользователь администратор.</span><span class="sxs-lookup"><span data-stu-id="d0d58-144">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="d0d58-145">Если в настоящее время установки на Рисунке рабочих групп и пользователя необходимо заменить ее установки PKG, пользователь должен:</span><span class="sxs-lookup"><span data-stu-id="d0d58-145">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="d0d58-146">Выйдите из приложения группы.</span><span class="sxs-lookup"><span data-stu-id="d0d58-146">Exit the Teams app.</span></span>
2. <span data-ttu-id="d0d58-147">Удаление приложения группы.</span><span class="sxs-lookup"><span data-stu-id="d0d58-147">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="d0d58-148">Установка файлов PKG.</span><span class="sxs-lookup"><span data-stu-id="d0d58-148">Install the PKG file.</span></span>

<span data-ttu-id="d0d58-149">ИТ-администраторов можно использовать управляемое развертывание групп передавать файлы установки для всех Макинтош в своей организации, такие как Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="d0d58-149">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="d0d58-150">При возникновении проблем при установке PKG свяжитесь с нами.</span><span class="sxs-lookup"><span data-stu-id="d0d58-150">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="d0d58-151">В разделе **свои отзывы и предложения** в конце этой статьи щелкните **отзыва о продукте**.</span><span class="sxs-lookup"><span data-stu-id="d0d58-151">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="d0d58-152">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="d0d58-152">Web client</span></span> 
----------

<span data-ttu-id="d0d58-153">Веб-клиент ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) — это полный функциональным клиент, который может использоваться с помощью различных браузерах.</span><span class="sxs-lookup"><span data-stu-id="d0d58-153">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="d0d58-154">Веб-клиент поддерживает звонков и собраний с помощью webRTC, поэтому нет не подключаемого модуля или загрузить, необходимые для выполнения команд в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="d0d58-154">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="d0d58-155">Браузер должен быть настроен отключена сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="d0d58-155">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="d0d58-156">Веб-клиент выполняет обнаружение версия браузера при подключении к [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="d0d58-156">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="d0d58-157">При обнаружении более версии Неподдерживаемый браузер, его можно было заблокируйте доступ к веб-интерфейс и Майкрософт рекомендует загружать пользователя клиента настольного компьютера или мобильного приложения.</span><span class="sxs-lookup"><span data-stu-id="d0d58-157">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="d0d58-158">Мобильные клиенты</span><span class="sxs-lookup"><span data-stu-id="d0d58-158">Mobile clients</span></span>
--------------

<span data-ttu-id="d0d58-159">Мобильных приложениях группами Майкрософт, доступны для Android и операций ввода-вывода и предназначены для пользователей по пути, участие в беседах по на основе чата и позволяют peer-to-peer голосовые вызовы.</span><span class="sxs-lookup"><span data-stu-id="d0d58-159">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="d0d58-160">Для мобильных приложений перейти в соответствующие хранилища мобильных устройств Google воспроизвести и в хранилище приложений Apple.</span><span class="sxs-lookup"><span data-stu-id="d0d58-160">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="d0d58-161">Удаленные приложения Windows Phone 20 июля 2018 видеть [здесь](https://support.microsoft.com/en-us/help/4230833/windows-phone-app-for-microsoft-teams-is-retiring) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="d0d58-161">The Windows Phone App was retired July 20, 2018 see [here](https://support.microsoft.com/en-us/help/4230833/windows-phone-app-for-microsoft-teams-is-retiring) for more information.</span></span>

<span data-ttu-id="d0d58-162">Для мобильных приложений Microsoft Teams поддерживаются следующие мобильные платформы:</span><span class="sxs-lookup"><span data-stu-id="d0d58-162">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="d0d58-163">**Android**: 4.4 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="d0d58-163">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="d0d58-164">**iOS**: 10.0 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="d0d58-164">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="d0d58-165">Мобильной версии должны быть доступны для просмотра в порядке рабочие группы могут работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="d0d58-165">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="d0d58-166">Мобильные приложения распространяются и обновляются только через магазин приложений соответствующей платформы и недоступны для распространения через решения по управлению мобильными устройствами (MDM), а также для загрузки в неопубликованном виде.</span><span class="sxs-lookup"><span data-stu-id="d0d58-166">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="d0d58-168">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="d0d58-168">Decision Point</span></span>         |<span data-ttu-id="d0d58-169">Существуют ли ограничения, мешающие пользователям установить на своих устройствах подходящий клиент Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="d0d58-169">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Значок дальнейших действий.](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="d0d58-171">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="d0d58-171">Next Steps</span></span>         |<span data-ttu-id="d0d58-172">Если ваша организация ограничивает установку программного обеспечения, убедитесь в совместимости данного механизма с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d0d58-172">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="d0d58-173">Примечание. Для установки клиента на Mac требуются права администратора, а на ПК — нет.</span><span class="sxs-lookup"><span data-stu-id="d0d58-173">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

<a name="client-update-management"></a><span data-ttu-id="d0d58-174">Управление обновлениями клиентов</span><span class="sxs-lookup"><span data-stu-id="d0d58-174">Client update management</span></span>
------------------------

<span data-ttu-id="d0d58-175">Сейчас клиенты обновляются службой Microsoft Teams автоматически и без вмешательства ИТ-администратора.</span><span class="sxs-lookup"><span data-stu-id="d0d58-175">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="d0d58-176">При выходе обновления клиент автоматически скачивает его, а после определенного периода неактивности приложения запускает процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="d0d58-176">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="d0d58-177">Конфигурации на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="d0d58-177">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="d0d58-178">Сейчас не существует способа для настройки клиента администратором клиента, а также с помощью PowerShell, объектов групповой политики или реестра.</span><span class="sxs-lookup"><span data-stu-id="d0d58-178">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="d0d58-179">Параметры уведомлений</span><span class="sxs-lookup"><span data-stu-id="d0d58-179">Notification settings</span></span>
----------------------------

<span data-ttu-id="d0d58-180">Сейчас не существует способа для настройки параметров уведомлений на стороне клиента ИТ-администраторами.</span><span class="sxs-lookup"><span data-stu-id="d0d58-180">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="d0d58-181">Все эти параметры задает пользователь.</span><span class="sxs-lookup"><span data-stu-id="d0d58-181">All notification options are set by the user.</span></span> <span data-ttu-id="d0d58-182">Приведенный ниже рисунок показывает параметры клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d0d58-182">The figure below outlines the default client settings.</span></span>

![Снимок экрана с параметрами уведомлений.](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a><span data-ttu-id="d0d58-184">Образец сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0d58-184">Sample PowerShell Script</span></span>
----------------------------

<span data-ttu-id="d0d58-185">Этот сценарий, необходимо запустить на клиентских компьютерах в контексте учетной записи администратора с повышенными привилегиями, создадим новое правило входящих брандмауэра для каждой папки пользователя, обнаруженных в c:\users.</span><span class="sxs-lookup"><span data-stu-id="d0d58-185">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="d0d58-186">Когда групп находит это правило, не даст приложения группы запросы пользователей для создания правила брандмауэра, если пользователи выполните их первый звонок из групп.</span><span class="sxs-lookup"><span data-stu-id="d0d58-186">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```
$users = Get-Childitem c:\users
foreach ($user in $users) 
{
    $Path = "c:\users\" + $user.Name + "\appdata\local\Microsoft\Teams\Current\Teams.exe"
    if (Test-Path $Path) 
    {
            $name = "teams.exe " + $user.Name
            if (!(Get-NetFirewallRule -DisplayName $name))
        {
                New-NetFirewallRule -DisplayName “teams.exe” -Direction Inbound -Profile Domain -Program $Path -Action Allow
        }
    }
}
<#
        .ABOUT THIS SCRIPT
        (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.

        Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 

        The script will create a new inbound firewall rule for each user folder found in c:\users. 

        Requires PowerShell 3.0
        
#>

```
