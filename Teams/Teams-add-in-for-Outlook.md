---
title: "Использование надстройки \"Собрание Microsoft Teams\" в Outlook"
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 01/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: "Microsoft Teams устанавливает в Outlook надстройку, которая позволяет пользователям планировать собрания Microsoft Teams из Outlook."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8c8930787d74fdc0dddf2b7987a967e130721d2
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="e18c6-103">Использование надстройки "Собрание Teams" в Outlook</span><span class="sxs-lookup"><span data-stu-id="e18c6-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="e18c6-104">Надстройка "Собрание Teams" автоматически устанавливается для пользователей Windows, на компьютерах которых есть Microsoft Teams и Office 2013 либо Office 2016.</span><span class="sxs-lookup"><span data-stu-id="e18c6-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="e18c6-105">Надстройка "Собрание Teams" отображается в ленте "Календарь Outlook".</span><span class="sxs-lookup"><span data-stu-id="e18c6-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Снимок экрана с надстройкой Microsoft Teams в ленте Outlook.](media/Teams-add-in-for-Outlook.png)

<span data-ttu-id="e18c6-107">Если надстройка "Собрание Teams" не отображается, попросите пользователей закрыть Outlook и Microsoft Teams, затем перезапустить клиент Microsoft Teams, войти в него и перезапустить клиент Outlook (именно в таком порядке).</span><span class="sxs-lookup"><span data-stu-id="e18c6-107">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="e18c6-108">Надстройка "Собрание Teams" для Outlook в настоящее время недоступна для пользователей Mac.</span><span class="sxs-lookup"><span data-stu-id="e18c6-108">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="e18c6-109">Требования к проверке подлинности</span><span class="sxs-lookup"><span data-stu-id="e18c6-109">Authentication requirements</span></span>

<span data-ttu-id="e18c6-110">Чтобы использовать надстройку "Собрание Teams", пользователи должны войти в Microsoft Teams с помощью современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e18c6-110">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="e18c6-111">Если не использовать этот метод проверки подлинности для входа, работа с клиентом Microsoft Teams будет возможна, но нельзя будет планировать собрания Microsoft Teams по сети с помощью настройки Outlook.</span><span class="sxs-lookup"><span data-stu-id="e18c6-111">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="e18c6-112">Решить эту проблему можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="e18c6-112">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="e18c6-113">Если для вашей организации не настроена современная проверка подлинности, настройте ее.</span><span class="sxs-lookup"><span data-stu-id="e18c6-113">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="e18c6-114">Если современная проверка подлинности настроена, но отключена в диалоговом окне, попросите пользователей повторить вход с помощью многофакторной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e18c6-114">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="e18c6-115">Дополнительные сведения о настройке проверки подлинности: [Модели удостоверений и проверка подлинности в Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e18c6-115">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="e18c6-116">Активация частных собраний</span><span class="sxs-lookup"><span data-stu-id="e18c6-116">Enable private meetings</span></span>

<span data-ttu-id="e18c6-117">Для развертывания подключаемого модуля нужно разрешить планирование частных собраний в [Центре администрирования Office 365](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="e18c6-117">Allow scheduling for private meetings must be enabled from the [Office 365 admin center](https://portal.office.com/adminportal/home) for the plug-in to get deployed.</span></span>

![Снимок экрана с параметрами раздела "Звонки и собрания" в Центре администрирования Office 365.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="e18c6-119">Клиент Microsoft Teams устанавливает нужную надстройку, определяя, требуется ли пользователям 32- или 64-разрядная версия.</span><span class="sxs-lookup"><span data-stu-id="e18c6-119">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="e18c6-120">Для получения новейшей версии надстройки пользователям может потребоваться перезапустить Outlook после установки или обновления Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e18c6-120">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="e18c6-121">Другие особенности</span><span class="sxs-lookup"><span data-stu-id="e18c6-121">Other planning considerations</span></span>

<span data-ttu-id="e18c6-122">Разработка функционала надстройки "Собрание Teams" продолжается, так что помните о следующем:</span><span class="sxs-lookup"><span data-stu-id="e18c6-122">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="e18c6-123">Некоторые функции собраний по сети, такие как запись, опрос и доска, пока недоступны.</span><span class="sxs-lookup"><span data-stu-id="e18c6-123">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="e18c6-124">Параметры собрания сейчас недоступны.</span><span class="sxs-lookup"><span data-stu-id="e18c6-124">Meeting options are currently not available.</span></span>
- <span data-ttu-id="e18c6-125">Сейчас вы можете приглашать в собрания только участников из своей компании, но не внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="e18c6-125">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="e18c6-126">Надстройка предназначена для запланированных собраний с конкретными участниками, а не для собраний в канале.</span><span class="sxs-lookup"><span data-stu-id="e18c6-126">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="e18c6-127">Собрания в канале нужно планировать в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e18c6-127">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="e18c6-128">Надстройка "Собрание Teams" в Outlook сейчас доступна только пользователям Windows, но в ближайшее время будет реализована поддержка Mac.</span><span class="sxs-lookup"><span data-stu-id="e18c6-128">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="e18c6-129">Надстройка не будет работать, если прокси-сервер проверки подлинности находится по сетевому пути пользовательского ПК и служб Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e18c6-129">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>

<span data-ttu-id="e18c6-130">Чтобы скрыть от пользователей надстройку "Собрание Teams", вы можете удалить ее.</span><span class="sxs-lookup"><span data-stu-id="e18c6-130">If you do not want the Teams Meeting add-in to appear for users, you can remove it.</span></span> <span data-ttu-id="e18c6-131">Общие указания по отключению надстроек: [Просмотр и установка надстроек, а также управление ими в приложениях Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="e18c6-131">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="e18c6-132">Получите дополнительные сведения о [собраниях и звонках в Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="e18c6-132">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

