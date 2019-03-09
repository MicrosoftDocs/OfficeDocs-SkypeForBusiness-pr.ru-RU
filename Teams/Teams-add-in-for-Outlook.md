---
title: Использование надстройки "Собрание Microsoft Teams" в Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams устанавливает в Outlook надстройку, которая позволяет пользователям планировать собрания Microsoft Teams из Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbe0b72c03d8e85deff538924c17dac8f0d3773c
ms.sourcegitcommit: daf65bf09ca57554da744602d2551db53caedde5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "30512991"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="62153-103">Использование надстройки "Собрание Teams" в Outlook</span><span class="sxs-lookup"><span data-stu-id="62153-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="62153-104">Надстройка "Собрание Teams" автоматически устанавливается для пользователей Windows, на компьютерах которых есть Microsoft Teams и Office 2013 либо Office 2016.</span><span class="sxs-lookup"><span data-stu-id="62153-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="62153-105">Надстройка "Собрание Teams" отображается в ленте "Календарь Outlook".</span><span class="sxs-lookup"><span data-stu-id="62153-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Снимок экрана с надстройкой Microsoft Teams в ленте Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> <span data-ttu-id="62153-107">Пользователи Windows 7 необходимо установить [обновление для универсальных среды выполнения C в Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) для надстройки собраний группы для работы.</span><span class="sxs-lookup"><span data-stu-id="62153-107">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>

<span data-ttu-id="62153-108">Если надстройка "Собрание Teams" не отображается, попросите пользователей закрыть Outlook и Microsoft Teams, затем перезапустить клиент Microsoft Teams, войти в него и перезапустить клиент Outlook (именно в таком порядке).</span><span class="sxs-lookup"><span data-stu-id="62153-108">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="62153-109">Надстройка "Собрание Teams" для Outlook в настоящее время недоступна для пользователей Mac.</span><span class="sxs-lookup"><span data-stu-id="62153-109">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="62153-110">Требования к проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="62153-110">Authentication requirements</span></span>

<span data-ttu-id="62153-111">Чтобы использовать надстройку "Собрание Teams", пользователи должны войти в Microsoft Teams с помощью современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="62153-111">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="62153-112">Если не использовать этот метод проверки подлинности для входа, работа с клиентом Microsoft Teams будет возможна, но нельзя будет планировать собрания Microsoft Teams по сети с помощью настройки Outlook.</span><span class="sxs-lookup"><span data-stu-id="62153-112">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="62153-113">Решить эту проблему можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="62153-113">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="62153-114">Если для вашей организации не настроена современная проверка подлинности, настройте ее.</span><span class="sxs-lookup"><span data-stu-id="62153-114">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="62153-115">Если современная проверка подлинности настроена, но отключена в диалоговом окне, попросите пользователей повторить вход с помощью многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="62153-115">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="62153-116">Дополнительные сведения о настройке проверки подлинности: [Модели удостоверений и проверка подлинности в Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="62153-116">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="62153-117">Активация частных собраний</span><span class="sxs-lookup"><span data-stu-id="62153-117">Enable private meetings</span></span>

<span data-ttu-id="62153-118">Разрешить планирование для частных собраний должна быть включена в центре администрирования группами Майкрософт для подключаемого модуля получить развернут.</span><span class="sxs-lookup"><span data-stu-id="62153-118">Allow scheduling for private meetings must be enabled in the Microsoft Teams admin center for the plug-in to get deployed.</span></span> <span data-ttu-id="62153-119">В центре администрирования перейдите к **собраниям** > **Политик собраний**и в разделе **Общие** включения и отключения **Разрешить планирование частных собраний** для на.)</span><span class="sxs-lookup"><span data-stu-id="62153-119">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Снимок экрана с параметрами в центре администрирования группами Майкрософт.](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="62153-121">Клиент Microsoft Teams устанавливает нужную надстройку, определяя, требуется ли пользователям 32- или 64-разрядная версия.</span><span class="sxs-lookup"><span data-stu-id="62153-121">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="62153-122">Для получения новейшей версии надстройки пользователям может потребоваться перезапустить Outlook после установки или обновления Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="62153-122">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="62153-123">Другие особенности</span><span class="sxs-lookup"><span data-stu-id="62153-123">Other considerations</span></span>

<span data-ttu-id="62153-124">Разработка функционала надстройки "Собрание Teams" продолжается, так что помните о следующем:</span><span class="sxs-lookup"><span data-stu-id="62153-124">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="62153-125">Некоторые функции собраний по сети, такие как запись, опрос и доска, пока недоступны.</span><span class="sxs-lookup"><span data-stu-id="62153-125">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="62153-126">Параметры собрания сейчас недоступны.</span><span class="sxs-lookup"><span data-stu-id="62153-126">Meeting options are currently not available.</span></span>
- <span data-ttu-id="62153-127">Сейчас вы можете приглашать в собрания только участников из своей компании, но не внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="62153-127">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="62153-128">Надстройка предназначена для запланированных собраний с конкретными участниками, а не для собраний в канале.</span><span class="sxs-lookup"><span data-stu-id="62153-128">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="62153-129">Собрания в канале нужно планировать в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="62153-129">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="62153-130">Надстройка "Собрание Teams" в Outlook сейчас доступна только пользователям Windows, но в ближайшее время будет реализована поддержка Mac.</span><span class="sxs-lookup"><span data-stu-id="62153-130">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="62153-131">Надстройка не будет работать, если прокси-сервер проверки подлинности находится по сетевому пути пользовательского ПК и служб Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="62153-131">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="62153-132">Надстройки предназначенных для развертывания постепенного и может быть недоступна для вашей организации еще.</span><span class="sxs-lookup"><span data-stu-id="62153-132">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="62153-133">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="62153-133">Troubleshooting</span></span>

<span data-ttu-id="62153-134">Если не удается получить собрания команды надстройки для Outlook для установки, попробуйте выполните следующие действия по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="62153-134">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="62153-135">Убедитесь, что были применены все доступные обновления для настольных компьютеров клиента Outlook</span><span class="sxs-lookup"><span data-stu-id="62153-135">Ensure all available updates for Outlook desktop client have been applied</span></span> 
- <span data-ttu-id="62153-136">Перезапустите клиент рабочего стола группами.</span><span class="sxs-lookup"><span data-stu-id="62153-136">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="62153-137">Выход и выполните вход на клиентском группами.</span><span class="sxs-lookup"><span data-stu-id="62153-137">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="62153-138">Перезапуск рабочего стола клиента Outlook.</span><span class="sxs-lookup"><span data-stu-id="62153-138">Restart the Outlook desktop client.</span></span> <span data-ttu-id="62153-139">(Убедитесь, что Outlook не будет работать в режиме администратора.)</span><span class="sxs-lookup"><span data-stu-id="62153-139">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="62153-140">Убедитесь, что имя учетной записи пользователя, выполнившего вход не содержит пробелов.</span><span class="sxs-lookup"><span data-stu-id="62153-140">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="62153-141">(Это известная проблема и будет исправлена в дальнейшем.)</span><span class="sxs-lookup"><span data-stu-id="62153-141">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="62153-142">Убедитесь, что включен единый вход (SSO).</span><span class="sxs-lookup"><span data-stu-id="62153-142">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="62153-143">Общие указания по отключению надстроек: [Просмотр и установка надстроек, а также управление ими в приложениях Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="62153-143">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="62153-144">Получите дополнительные сведения о [собраниях и звонках в Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="62153-144">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

