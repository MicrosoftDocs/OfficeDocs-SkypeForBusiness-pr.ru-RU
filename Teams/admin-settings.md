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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1a7d10be12c75b3d25737aa770c94e5a540e683
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881919"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="a21c3-103">Параметры администратора для приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a21c3-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="a21c3-104">Приложения — это предоставляемые сторонними службами вкладки, соединители, боты или любое их сочетание.</span><span class="sxs-lookup"><span data-stu-id="a21c3-104">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="a21c3-105">Центр администрирования Office 365 позволяет настроить политики администрирования Microsoft Teams, которые определяют разрешенные внешние сторонние приложения.</span><span class="sxs-lookup"><span data-stu-id="a21c3-105">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="a21c3-106">Эти политики позволяют указать, какие приложения могут и не разрешены, новое поведение внешнего приложения и разрешено ли загрузка со стороны приложений.</span><span class="sxs-lookup"><span data-stu-id="a21c3-106">These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="a21c3-107">Настройки администрирования для приложений Teams находятся в центре администрирования Office 365 в разделе **Параметры**  >  **Службы и надстройки** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="a21c3-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="a21c3-108">Если вы вошли как администратор Office 365, воспользуйтесь ссылкой</span><span class="sxs-lookup"><span data-stu-id="a21c3-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="a21c3-109">Дополнительные сведения о настройках администрирования приложений см. в следующем видео.</span><span class="sxs-lookup"><span data-stu-id="a21c3-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="a21c3-110">Настройка приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a21c3-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="a21c3-111">Разрешение внешних приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a21c3-111">Allow external apps in Teams</span></span>

<span data-ttu-id="a21c3-112">По умолчанию параметр **Allow external apps in Microsoft Teams** (Разрешить внешние приложения в Microsoft Teams) включен и выбраны все приложения.</span><span class="sxs-lookup"><span data-stu-id="a21c3-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="a21c3-113">Если отключить этот параметр, все внешние сторонние приложения будут запрещены.</span><span class="sxs-lookup"><span data-stu-id="a21c3-113">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="a21c3-114">Включение новых внешних приложений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a21c3-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="a21c3-115">:trophy: Рекомендация: управление внешними приложениями по отдельности</span><span class="sxs-lookup"><span data-stu-id="a21c3-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="a21c3-116">Чтобы включить определенные приложения и отключить другие, отключите параметр **Allow sideloading of external apps** (Разрешить загрузку неопубликованных внешних приложений).</span><span class="sxs-lookup"><span data-stu-id="a21c3-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="a21c3-117">Затем отключите те приложения, доступ к которым следует запретить.</span><span class="sxs-lookup"><span data-stu-id="a21c3-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="a21c3-118">Необязательно: отключите параметр **Enable new external apps by default** (Включить новые внешние приложения по умолчанию), если вы хотите контролировать новые приложения.</span><span class="sxs-lookup"><span data-stu-id="a21c3-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="a21c3-119">Параметр **Включить новые внешние приложения по умолчанию** не повлияет на приложения по умолчанию, например, разработанных корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a21c3-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span> <span data-ttu-id="a21c3-120">Новые приложения включены по умолчанию после выпуска корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a21c3-120">New apps are enabled by default when released by Microsoft.</span></span>

<span data-ttu-id="a21c3-121">Если этот параметр включен, пользователи могут активировать новые приложения сразу после их добавления в каталог приложений Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a21c3-121">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="a21c3-122">Чтобы открыть каталог приложений Microsoft Teams, выберите пункт **Магазин** в нижней части Microsoft Teams и щелкните **Приложения**.</span><span class="sxs-lookup"><span data-stu-id="a21c3-122">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="a21c3-123">Если вы хотите контролировать, какие будут доступны приложения, отключите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="a21c3-123">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="a21c3-124">В этом случае не забывайте периодически просматривать новые приложения, чтобы ваша организация не пропустила появление новых интересных программ.</span><span class="sxs-lookup"><span data-stu-id="a21c3-124">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="a21c3-125">Загрузка неопубликованного приложения — это возможность добавить приложение в Microsoft Teams, непосредственно отправив в команду ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="a21c3-125">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="a21c3-126">Загрузка неопубликованного приложения позволяет тестировать приложение в процессе его разработки.</span><span class="sxs-lookup"><span data-stu-id="a21c3-126">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="a21c3-127">Она также позволяет создать приложение только для внутреннего пользования и поделиться им с командой, не отправляя программу в каталог приложений Microsoft Teams в Магазине Office.</span><span class="sxs-lookup"><span data-stu-id="a21c3-127">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="a21c3-128">Загружать неопубликованные приложения в Microsoft Teams могут только владельцы команд или участники с соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="a21c3-128">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

![Снимок экрана с расширенной раздел приложения в параметры на уровне клиента.](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="a21c3-130">Создание и отправка пакетов приложений</span><span class="sxs-lookup"><span data-stu-id="a21c3-130">Creating and uploading app packages</span></span> 

<span data-ttu-id="a21c3-131">Дополнительные сведения о приложениях разделе [Разработка приложений для группы](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="a21c3-131">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



