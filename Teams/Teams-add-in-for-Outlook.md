---
title: Использование надстройки "Собрание Microsoft Teams" в Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
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
ms.openlocfilehash: 801c4f43e9aafa7fe8331d85b601afd584505164
ms.sourcegitcommit: e5cb24ad166268392e692d3d1b92125646e5d66e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2019
ms.locfileid: "34417445"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="a30db-103">Использование надстройки "Собрание Teams" в Outlook</span><span class="sxs-lookup"><span data-stu-id="a30db-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="a30db-104">Надстройка "Собрание Teams" автоматически устанавливается для пользователей Windows, на компьютерах которых есть Microsoft Teams и Office 2013 либо Office 2016.</span><span class="sxs-lookup"><span data-stu-id="a30db-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="a30db-105">Надстройка "Собрание Teams" отображается в ленте "Календарь Outlook".</span><span class="sxs-lookup"><span data-stu-id="a30db-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Снимок экрана с надстройкой Microsoft Teams в ленте Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> <span data-ttu-id="a30db-107">Пользователи Windows 7 должны установить [Обновление для универсальной среды выполнения C в Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) для надстройки "собрание Teams" для работы.</span><span class="sxs-lookup"><span data-stu-id="a30db-107">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>

<span data-ttu-id="a30db-108">Если надстройка "Собрание Teams" не отображается, попросите пользователей закрыть Outlook и Microsoft Teams, затем перезапустить клиент Microsoft Teams, войти в него и перезапустить клиент Outlook (именно в таком порядке).</span><span class="sxs-lookup"><span data-stu-id="a30db-108">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="a30db-109">Кнопка "собрание Teams" в Outlook для Mac появится на ленте Outlook для Mac, если в Outlook используется рабочая сборка 16,20 и более поздние версии.</span><span class="sxs-lookup"><span data-stu-id="a30db-109">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running Production Build 16.20 and later.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="a30db-110">Требования к проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="a30db-110">Authentication requirements</span></span>

<span data-ttu-id="a30db-111">Чтобы использовать надстройку "Собрание Teams", пользователи должны войти в Microsoft Teams с помощью современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a30db-111">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="a30db-112">Если не использовать этот метод проверки подлинности для входа, работа с клиентом Microsoft Teams будет возможна, но нельзя будет планировать собрания Microsoft Teams по сети с помощью настройки Outlook.</span><span class="sxs-lookup"><span data-stu-id="a30db-112">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="a30db-113">Решить эту проблему можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="a30db-113">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="a30db-114">Если для вашей организации не настроена современная проверка подлинности, настройте ее.</span><span class="sxs-lookup"><span data-stu-id="a30db-114">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="a30db-115">Если современная проверка подлинности настроена, но отключена в диалоговом окне, попросите пользователей повторить вход с помощью многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a30db-115">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="a30db-116">Дополнительные сведения о настройке проверки подлинности: [Модели удостоверений и проверка подлинности в Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a30db-116">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="a30db-117">Активация частных собраний</span><span class="sxs-lookup"><span data-stu-id="a30db-117">Enable private meetings</span></span>

<span data-ttu-id="a30db-118">Вы **можете включить планирование для закрытых собраний** в центре администрирования Microsoft Teams, чтобы обеспечить развертывание надстройки.</span><span class="sxs-lookup"><span data-stu-id="a30db-118">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the plug-in to get deployed.</span></span> <span data-ttu-id="a30db-119">В центре администрирования перейдите \*\*\*\* > в раздел**политики собраний**по собраниям, а затем в разделе **Общие** нажмите переключатель **Разрешить планирование личных собраний** .</span><span class="sxs-lookup"><span data-stu-id="a30db-119">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Снимок экрана: параметры в центре администрирования Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="a30db-121">Клиент Microsoft Teams устанавливает нужную надстройку, определяя, требуется ли пользователям 32- или 64-разрядная версия.</span><span class="sxs-lookup"><span data-stu-id="a30db-121">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="a30db-122">Для получения новейшей версии надстройки пользователям может потребоваться перезапустить Outlook после установки или обновления Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a30db-122">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="a30db-123">Другие особенности</span><span class="sxs-lookup"><span data-stu-id="a30db-123">Other considerations</span></span>

<span data-ttu-id="a30db-124">Разработка функционала надстройки "Собрание Teams" продолжается, так что помните о следующем:</span><span class="sxs-lookup"><span data-stu-id="a30db-124">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="a30db-125">Опрос пока недоступен.</span><span class="sxs-lookup"><span data-stu-id="a30db-125">Polling isn't yet available.</span></span>
- <span data-ttu-id="a30db-126">Начинается развертывание доски.</span><span class="sxs-lookup"><span data-stu-id="a30db-126">Whiteboard is starting to roll out.</span></span>
- <span data-ttu-id="a30db-127">Параметры собрания сейчас недоступны.</span><span class="sxs-lookup"><span data-stu-id="a30db-127">Meeting options are currently not available.</span></span>
- <span data-ttu-id="a30db-128">Сейчас вы можете приглашать в собрания только участников из своей компании, но не внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="a30db-128">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="a30db-129">Надстройка предназначена для запланированных собраний с конкретными участниками, а не для собраний в канале.</span><span class="sxs-lookup"><span data-stu-id="a30db-129">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="a30db-130">Собрания в канале нужно планировать в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a30db-130">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="a30db-131">Надстройка "Собрание Teams" в Outlook сейчас доступна только пользователям Windows, но в ближайшее время будет реализована поддержка Mac.</span><span class="sxs-lookup"><span data-stu-id="a30db-131">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="a30db-132">Надстройка не будет работать, если прокси-сервер проверки подлинности находится по сетевому пути пользовательского ПК и служб Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a30db-132">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="a30db-133">Развертывание надстройки выполняется постепенно и может быть недоступно для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a30db-133">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a30db-134">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="a30db-134">Troubleshooting</span></span>

<span data-ttu-id="a30db-135">Если вы не можете установить надстройку "собрание Teams" для Outlook, воспользуйтесь приведенными ниже инструкциями по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="a30db-135">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="a30db-136">Убедитесь, что все доступные обновления для настольного клиента Outlook были применены.</span><span class="sxs-lookup"><span data-stu-id="a30db-136">Ensure all available updates for Outlook desktop client have been applied</span></span> 
- <span data-ttu-id="a30db-137">Перезапустите клиент Teams для настольных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="a30db-137">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="a30db-138">Выйдите из системы, а затем снова войдите в классическое приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="a30db-138">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="a30db-139">Перезапустите клиент Outlook для настольных систем.</span><span class="sxs-lookup"><span data-stu-id="a30db-139">Restart the Outlook desktop client.</span></span> <span data-ttu-id="a30db-140">(Убедитесь, что Outlook не работает в режиме администратора.)</span><span class="sxs-lookup"><span data-stu-id="a30db-140">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="a30db-141">Убедитесь в том, что имя учетной записи пользователя, выполнившего вход, не содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="a30db-141">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="a30db-142">(Это известная проблема, которая будет устранена в следующем обновлении.)</span><span class="sxs-lookup"><span data-stu-id="a30db-142">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="a30db-143">Убедитесь, что включен единый вход (SSO).</span><span class="sxs-lookup"><span data-stu-id="a30db-143">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="a30db-144">Общие указания по отключению надстроек: [Просмотр и установка надстроек, а также управление ими в приложениях Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="a30db-144">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="a30db-145">Получите дополнительные сведения о [собраниях и звонках в Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="a30db-145">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

