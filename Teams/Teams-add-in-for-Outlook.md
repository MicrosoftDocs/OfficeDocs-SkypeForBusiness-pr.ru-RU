---
title: Использование надстройки "Собрание Microsoft Teams" в Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Priority
search.appverid: MET150
description: Microsoft Teams устанавливает в Outlook надстройку, которая позволяет пользователям планировать собрания Microsoft Teams из Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f465b03aacbaa1c7cd3cd835d279a112d0f87891
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856875"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="f6075-103">Использование надстройки "Собрание Teams" в Outlook</span><span class="sxs-lookup"><span data-stu-id="f6075-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f6075-104">Надстройка "Собрание Teams" автоматически устанавливается для пользователей Windows, на компьютерах которых есть Microsoft Teams и Office 2013 либо Office 2016.</span><span class="sxs-lookup"><span data-stu-id="f6075-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="f6075-105">Надстройка "Собрание Teams" отображается в ленте "Календарь Outlook".</span><span class="sxs-lookup"><span data-stu-id="f6075-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Снимок экрана с надстройкой Microsoft Teams в ленте Outlook.](media/Teams-add-in-for-Outlook.png)

<span data-ttu-id="f6075-107">Если надстройка "Собрание Teams" не отображается, попросите пользователей закрыть Outlook и Microsoft Teams, затем перезапустить клиент Microsoft Teams, войти в него и перезапустить клиент Outlook (именно в таком порядке).</span><span class="sxs-lookup"><span data-stu-id="f6075-107">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="f6075-108">Надстройка "Собрание Teams" для Outlook в настоящее время недоступна для пользователей Mac.</span><span class="sxs-lookup"><span data-stu-id="f6075-108">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="f6075-109">Требования к проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="f6075-109">Authentication requirements</span></span>

<span data-ttu-id="f6075-110">Чтобы использовать надстройку "Собрание Teams", пользователи должны войти в Microsoft Teams с помощью современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f6075-110">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="f6075-111">Если не использовать этот метод проверки подлинности для входа, работа с клиентом Microsoft Teams будет возможна, но нельзя будет планировать собрания Microsoft Teams по сети с помощью настройки Outlook.</span><span class="sxs-lookup"><span data-stu-id="f6075-111">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="f6075-112">Решить эту проблему можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="f6075-112">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="f6075-113">Если для вашей организации не настроена современная проверка подлинности, настройте ее.</span><span class="sxs-lookup"><span data-stu-id="f6075-113">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="f6075-114">Если современная проверка подлинности настроена, но отключена в диалоговом окне, попросите пользователей повторить вход с помощью многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f6075-114">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="f6075-115">Дополнительные сведения о настройке проверки подлинности: [Модели удостоверений и проверка подлинности в Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f6075-115">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="f6075-116">Активация частных собраний</span><span class="sxs-lookup"><span data-stu-id="f6075-116">Enable private meetings</span></span>

<span data-ttu-id="f6075-117">Для развертывания подключаемого модуля нужно разрешить планирование частных собраний в [Центре администрирования Office 365](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="f6075-117">Allow scheduling for private meetings must be enabled from the [Office 365 admin center](https://portal.office.com/adminportal/home) for the plug-in to get deployed.</span></span>

![Снимок экрана с параметрами раздела "Звонки и собрания" в Центре администрирования Office 365.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="f6075-119">Клиент Microsoft Teams устанавливает нужную надстройку, определяя, требуется ли пользователям 32- или 64-разрядная версия.</span><span class="sxs-lookup"><span data-stu-id="f6075-119">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="f6075-120">Для получения новейшей версии надстройки пользователям может потребоваться перезапустить Outlook после установки или обновления Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6075-120">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="f6075-121">Другие особенности</span><span class="sxs-lookup"><span data-stu-id="f6075-121">Other considerations</span></span>

<span data-ttu-id="f6075-122">Разработка функционала надстройки "Собрание Teams" продолжается, так что помните о следующем:</span><span class="sxs-lookup"><span data-stu-id="f6075-122">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="f6075-123">Некоторые функции собраний по сети, такие как запись, опрос и доска, пока недоступны.</span><span class="sxs-lookup"><span data-stu-id="f6075-123">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="f6075-124">Параметры собрания сейчас недоступны.</span><span class="sxs-lookup"><span data-stu-id="f6075-124">Meeting options are currently not available.</span></span>
- <span data-ttu-id="f6075-125">Сейчас вы можете приглашать в собрания только участников из своей компании, но не внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="f6075-125">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="f6075-126">Надстройка предназначена для запланированных собраний с конкретными участниками, а не для собраний в канале.</span><span class="sxs-lookup"><span data-stu-id="f6075-126">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="f6075-127">Собрания в канале нужно планировать в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6075-127">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="f6075-128">Надстройка "Собрание Teams" в Outlook сейчас доступна только пользователям Windows, но в ближайшее время будет реализована поддержка Mac.</span><span class="sxs-lookup"><span data-stu-id="f6075-128">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="f6075-129">Надстройка не будет работать, если прокси-сервер проверки подлинности находится по сетевому пути пользовательского ПК и служб Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f6075-129">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="f6075-130">Надстройки предназначенных для развертывания постепенного и может быть недоступна для вашей организации еще.</span><span class="sxs-lookup"><span data-stu-id="f6075-130">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f6075-131">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f6075-131">Troubleshooting</span></span>

<span data-ttu-id="f6075-132">Если не удается получить собрания команды надстройки для Outlook для установки, попробуйте выполните следующие действия по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="f6075-132">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="f6075-133">Перезапустите клиент рабочего стола группами.</span><span class="sxs-lookup"><span data-stu-id="f6075-133">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="f6075-134">Выход и выполните вход на клиентском группами.</span><span class="sxs-lookup"><span data-stu-id="f6075-134">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="f6075-135">Перезапуск рабочего стола клиента Outlook.</span><span class="sxs-lookup"><span data-stu-id="f6075-135">Restart the Outlook desktop client.</span></span> <span data-ttu-id="f6075-136">(Убедитесь, что Outlook не будет работать в режиме администратора.)</span><span class="sxs-lookup"><span data-stu-id="f6075-136">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="f6075-137">Убедитесь, что имя учетной записи пользователя, выполнившего вход не содержит пробелов.</span><span class="sxs-lookup"><span data-stu-id="f6075-137">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="f6075-138">(Это известная проблема и будет исправлена в дальнейшем.)</span><span class="sxs-lookup"><span data-stu-id="f6075-138">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="f6075-139">Убедитесь, что включен единый вход (SSO).</span><span class="sxs-lookup"><span data-stu-id="f6075-139">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="f6075-140">Общие указания по отключению надстроек: [Просмотр и установка надстроек, а также управление ими в приложениях Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="f6075-140">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="f6075-141">Получите дополнительные сведения о [собраниях и звонках в Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="f6075-141">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

