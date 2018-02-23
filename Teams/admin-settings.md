---
title: "Параметры администратора для приложений в Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 01/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "Сведения о том, как разрешить и включить приложения в Microsoft Teams, включая загрузку неопубликованных внешних приложений."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4cdca98cca13ffb49575b808a5cfa82f784d1752
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="8c679-103">Параметры администратора для приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c679-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="8c679-104">Приложения — это предоставляемые сторонними службами вкладки, соединители, боты или любое их сочетание.</span><span class="sxs-lookup"><span data-stu-id="8c679-104">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="8c679-105">Центр администрирования Office 365 позволяет настроить политики администрирования Microsoft Teams, которые определяют разрешенные внешние сторонние приложения.</span><span class="sxs-lookup"><span data-stu-id="8c679-105">There are Admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="8c679-106">В них вы можете указать, какие программы следует разрешать, а какие — блокировать, как работать с новыми внешними приложениями и можно ли загружать неопубликованные приложения.</span><span class="sxs-lookup"><span data-stu-id="8c679-106">These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="8c679-107">Настройки администрирования для приложений Teams находятся в центре администрирования Office 365 в разделе **Параметры**  >  **Службы и надстройки** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="8c679-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="8c679-108">Если вы вошли как администратор Office 365, воспользуйтесь ссылкой</span><span class="sxs-lookup"><span data-stu-id="8c679-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> <span data-ttu-id="8c679-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="8c679-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span> 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="8c679-110">Разрешение внешних приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c679-110">Allow external apps in Microsoft Teams</span></span>

<span data-ttu-id="8c679-111">По умолчанию параметр **Allow external apps in Microsoft Teams** (Разрешить внешние приложения в Microsoft Teams) включен и выбраны все приложения.</span><span class="sxs-lookup"><span data-stu-id="8c679-111">By default, allow external apps in Microsoft Teams is enabled with all apps selected.</span></span>  <span data-ttu-id="8c679-112">Если отключить этот параметр, все внешние сторонние приложения будут запрещены.</span><span class="sxs-lookup"><span data-stu-id="8c679-112">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="8c679-113">Включение новых внешних приложений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8c679-113">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="8c679-114">:trophy: Рекомендация: управление внешними приложениями по отдельности</span><span class="sxs-lookup"><span data-stu-id="8c679-114">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="8c679-115">Чтобы включить определенные приложения и отключить другие, отключите параметр **Allow sideloading of external apps** (Разрешить загрузку неопубликованных внешних приложений).</span><span class="sxs-lookup"><span data-stu-id="8c679-115">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="8c679-116">Затем отключите те приложения, доступ к которым следует запретить.</span><span class="sxs-lookup"><span data-stu-id="8c679-116">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="8c679-117">Необязательно: отключите параметр **Enable new external apps by default** (Включить новые внешние приложения по умолчанию), если вы хотите контролировать новые приложения.</span><span class="sxs-lookup"><span data-stu-id="8c679-117">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

<span data-ttu-id="8c679-118">Если этот параметр включен, пользователи могут активировать новые приложения сразу после их добавления в каталог приложений Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c679-118">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="8c679-119">Чтобы открыть каталог приложений Microsoft Teams, выберите пункт **Магазин** в нижней части Microsoft Teams и щелкните **Приложения**.</span><span class="sxs-lookup"><span data-stu-id="8c679-119">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="8c679-120">Если вы хотите контролировать, какие будут доступны приложения, отключите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="8c679-120">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="8c679-121">В этом случае не забывайте периодически просматривать новые приложения, чтобы ваша организация не пропустила появление новых интересных программ.</span><span class="sxs-lookup"><span data-stu-id="8c679-121">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="8c679-122">Загрузка неопубликованного приложения — это возможность добавить приложение в Microsoft Teams, непосредственно отправив в команду ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="8c679-122">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="8c679-123">Загрузка неопубликованного приложения позволяет тестировать приложение в процессе его разработки.</span><span class="sxs-lookup"><span data-stu-id="8c679-123">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="8c679-124">Она также позволяет создать приложение только для внутреннего пользования и поделиться им с командой, не отправляя программу в каталог приложений Microsoft Teams в Магазине Office.</span><span class="sxs-lookup"><span data-stu-id="8c679-124">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="8c679-125">Загружать неопубликованные приложения в Microsoft Teams могут только владельцы команд или участники с соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="8c679-125">Only Team owners or members who are granted permissions, can side-load apps into Microsoft Teams.</span></span>  

![Снимок экрана с разделом приложений в параметрах Microsoft Teams.](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png) 

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="8c679-127">Создание и отправка пакетов приложений</span><span class="sxs-lookup"><span data-stu-id="8c679-127">Creating and uploading app packages</span></span> 

<span data-ttu-id="8c679-128">Дополнительные сведения о приложениях: [Develop apps for Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview)(Разработка приложений для Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="8c679-128">To learn more about apps, read [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



