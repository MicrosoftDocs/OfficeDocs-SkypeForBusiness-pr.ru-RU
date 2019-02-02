---
title: Параметры администратора для приложений в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag
description: Сведения о том, как разрешить и включить приложения в Microsoft Teams, включая загрузку неопубликованных внешних приложений.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: da73768f69159c32543d0843139facc2b9ef4f9a
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706357"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="8c0a2-103">Параметры администратора для приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c0a2-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="8c0a2-104">Приложения, вкладок, соединители, программы-роботы или любое сочетание трех следующих элементов, предоставляются по группам (основном приложения и также известной как приложения по умолчанию) или по сторонних производителей (также известные как внешние приложения).</span><span class="sxs-lookup"><span data-stu-id="8c0a2-104">Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, and also known as default apps) or by a third-party (also known as external apps).</span></span> <span data-ttu-id="8c0a2-105">В центре администрирования Microsoft 365 можно включить и отключить приложений по умолчанию и настроить параметры для управления внешнего приложения.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-105">In the Microsoft 365 admin center, you can enable and disable default apps and configure settings to control external apps.</span></span> <span data-ttu-id="8c0a2-106">Эти параметры позволяют указать какие внешнего приложения разрешенных и не разрешены, новое поведение внешнего приложения и разрешено ли загрузка со стороны приложений.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-106">These settings let you specify which external apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

 <span data-ttu-id="8c0a2-107">Для управления параметрами администрирования для приложений в группах, перейдите в центр администрирования Microsoft 365 и выберите команду **Параметры** > **надстроек & служб** > **Группами Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-107">To manage admin settings for apps in Teams, go to the Microsoft 365 admin center and choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="8c0a2-108">Если вы вошли с правами администратора Office 365, воспользуйтесь ссылкой:</span><span class="sxs-lookup"><span data-stu-id="8c0a2-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="8c0a2-109">Дополнительные сведения о настройках администрирования приложений см. в следующем видео.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="8c0a2-110">Настройка приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c0a2-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="8c0a2-111">Разрешение внешних приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c0a2-111">Allow external apps in Teams</span></span>

<span data-ttu-id="8c0a2-112">По умолчанию параметр **Allow external apps in Microsoft Teams** (Разрешить внешние приложения в Microsoft Teams) включен и выбраны все приложения.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="8c0a2-113">Если отключить этот параметр, будут отключены все внешние приложения сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-113">If you turn off this setting, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="8c0a2-114">Включение новых внешних приложений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8c0a2-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="8c0a2-115">:trophy: Рекомендация: управление внешними приложениями по отдельности</span><span class="sxs-lookup"><span data-stu-id="8c0a2-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="8c0a2-116">Чтобы включить определенные приложения и отключить другие, отключите параметр **Allow sideloading of external apps** (Разрешить загрузку неопубликованных внешних приложений).</span><span class="sxs-lookup"><span data-stu-id="8c0a2-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="8c0a2-117">Затем отключите те приложения, доступ к которым следует запретить.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="8c0a2-118">Необязательно: отключите параметр **Enable new external apps by default** (Включить новые внешние приложения по умолчанию), если вы хотите контролировать новые приложения.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="8c0a2-119">Параметр **Включить новые внешние приложения по умолчанию** не повлияет на приложения по умолчанию, например, разработанных корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span> <span data-ttu-id="8c0a2-120">Новые приложения включены по умолчанию после выпуска корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-120">New apps are enabled by default when released by Microsoft.</span></span>

<span data-ttu-id="8c0a2-121">Если этот параметр включен, пользователи могут активировать новые приложения, как только они добавляются в каталог приложений группами.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-121">When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="8c0a2-122">Чтобы открыть каталог приложений Microsoft Teams, выберите пункт **Магазин** в нижней части Microsoft Teams и щелкните **Приложения**.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-122">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="8c0a2-123">Если вы хотите контролировать, какие приложения доступны, отключите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-123">If you want to control which apps are available, turn off this setting.</span></span> <span data-ttu-id="8c0a2-124">В этом случае не забывайте периодически просматривать новые приложения, чтобы ваша организация не пропустила появление новых интересных программ.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-124">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="8c0a2-125">Загрузка неопубликованного приложения — это возможность добавить приложение в Microsoft Teams, непосредственно отправив в команду ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-125">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="8c0a2-126">Загрузка неопубликованного приложения позволяет тестировать приложение в процессе его разработки.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-126">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="8c0a2-127">Она также позволяет создать приложение только для внутреннего пользования и поделиться им с командой, не отправляя программу в каталог приложений Microsoft Teams в Магазине Office.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-127">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="8c0a2-128">Загружать неопубликованные приложения в Microsoft Teams могут только владельцы команд или участники с соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="8c0a2-128">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

<span data-ttu-id="8c0a2-129">![Изображение разделе развернутой внешнего приложения.] (media/teams-tenant-wide-settings-external-apps.png "Снимок экрана раздела расширенное внешних приложений, отражающая внешних приложений")</span><span class="sxs-lookup"><span data-stu-id="8c0a2-129">![Screen shot of the expanded External Apps section.](media/teams-tenant-wide-settings-external-apps.png "Screen shot of the expanded External Apps section showing external apps")</span></span>

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="8c0a2-130">Создание и отправка пакетов приложений</span><span class="sxs-lookup"><span data-stu-id="8c0a2-130">Creating and uploading app packages</span></span> 

<span data-ttu-id="8c0a2-131">Дополнительные сведения о приложениях разделе [Разработка приложений для группы](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="8c0a2-131">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



