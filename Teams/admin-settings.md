---
title: Параметры администратора для приложений в Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Узнайте о политиках и параметрах, которые можно использовать для управления приложениями для Организации в Microsoft Teams.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
f1.keywords:
- CSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6235352b845898c194e82f3ec292539904a7f61c
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582446"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="b51d5-103">Параметры администратора для приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b51d5-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="b51d5-104">Приложения предоставляют вам готовые инструменты для работы с более коллегами в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b51d5-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="b51d5-105">Эти приложения объединяют функции вкладок, расширения для сообщений, соединителей и ботов, предоставляемые корпорацией Майкрософт, разработанные сторонними разработчиками или разработчиков вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b51d5-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="b51d5-106">Вы управляете приложениями для своей организации в **приложениях Teams** в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="b51d5-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="b51d5-107">(Дополнительные сведения о том, как получить роли администраторов и разрешения, можно найти [в разделе Использование ролей администратора Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) .) Например, вы можете разрешать или блокировать приложения на уровне Организации, устанавливать политики, чтобы управлять приложениями, доступными для пользователей Teams, и настраивать группы, закреплять наиболее важные для ваших пользователей приложения.</span><span class="sxs-lookup"><span data-stu-id="b51d5-107">(See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="b51d5-108">Мы постоянно улучшаем взаимодействие приложений в Teams и добавляйте функции и функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="b51d5-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="b51d5-109">С течением времени мы будем создавать дополнительные возможности управления приложениями, поэтому проверяйте последнюю информацию о политиках приложений.</span><span class="sxs-lookup"><span data-stu-id="b51d5-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="b51d5-110">Управление приложениями</span><span class="sxs-lookup"><span data-stu-id="b51d5-110">Manage apps</span></span>

<span data-ttu-id="b51d5-111">Страница **Управление приложениями** используется для просмотра всех приложений Teams в каталоге приложений организации и управления ими.</span><span class="sxs-lookup"><span data-stu-id="b51d5-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="b51d5-112">Вы можете просматривать состояние и свойства приложения, блокировать или разрешать приложения на уровне Организации, добавлять новые пользовательские приложения в каталог клиентов и управлять параметрами приложения в масштабе организации.</span><span class="sxs-lookup"><span data-stu-id="b51d5-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="b51d5-113">На странице **Управление приложениями** вы можете просмотреть все доступные приложения в каталоге клиентов, предоставив вам необходимые сведения, чтобы решить, какие приложения разрешены или заблокированы в Организации.</span><span class="sxs-lookup"><span data-stu-id="b51d5-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="b51d5-114">Затем вы можете использовать [политики разрешений приложения](#app-permission-policies), [политики настройки приложений](#app-setup-policies)и [политики и параметры пользовательских приложений](#custom-app-policies-and-settings) , чтобы настроить взаимодействие с приложением для конкретных пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="b51d5-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="b51d5-115">Дополнительные сведения можно найти [в разделе Управление приложениями в Teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="b51d5-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="b51d5-116">Политики разрешений приложений</span><span class="sxs-lookup"><span data-stu-id="b51d5-116">App permission policies</span></span>

<span data-ttu-id="b51d5-117">С помощью политик разрешений для приложений вы можете управлять тем, какие приложения доступны конкретным пользователям в Организации.</span><span class="sxs-lookup"><span data-stu-id="b51d5-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="b51d5-118">Вы можете разрешить или заблокировать все приложения или отдельные приложения, опубликованные корпорацией Майкрософт, сторонними организациями и вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="b51d5-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="b51d5-119">Например, можно использовать политики разрешений приложений для следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b51d5-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="b51d5-120">Постепенно выполняйте развертывание новых сторонних или пользовательских приложений, созданных для конкретных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b51d5-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="b51d5-121">Упростите взаимодействие с пользователем, особенно при развертывании Teams в Организации.</span><span class="sxs-lookup"><span data-stu-id="b51d5-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="b51d5-122">Дополнительные сведения можно найти в статье [Управление политиками разрешений на доступ к приложениям в Teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b51d5-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="b51d5-123">Политики настройки приложений</span><span class="sxs-lookup"><span data-stu-id="b51d5-123">App setup policies</span></span>

<span data-ttu-id="b51d5-124">Политики настройки приложений позволяют настраивать взаимодействие с приложениями для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b51d5-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="b51d5-125">Вы выбираете приложения, которые вы хотите закрепить на панели приложения в клиентах Teams и в том порядке, в котором они отображаются, на веб-сайте, настольном компьютере и мобильных клиентах.</span><span class="sxs-lookup"><span data-stu-id="b51d5-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="b51d5-126">Ниже приведены примеры использования политик настройки приложений.</span><span class="sxs-lookup"><span data-stu-id="b51d5-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="b51d5-127">Сведения о поддержке дисков и их внедрение в основные приложения.</span><span class="sxs-lookup"><span data-stu-id="b51d5-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="b51d5-128">Например, закрепление собственного приложения для управления набором персонала и руководителей для пользователей в команде отдела кадров.</span><span class="sxs-lookup"><span data-stu-id="b51d5-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="b51d5-129">Выборочно закрепление основных функциональных возможностей Teams, таких как чат, Teams и звонки.</span><span class="sxs-lookup"><span data-stu-id="b51d5-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="b51d5-130">Это поможет вам убедиться в том, что пользователи будут вовлечены в определенные действия в Teams.</span><span class="sxs-lookup"><span data-stu-id="b51d5-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="b51d5-131">Дополнительные сведения можно найти в статье [Управление политиками настройки приложений в Teams](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b51d5-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="b51d5-132">Пользовательские политики и параметры приложений</span><span class="sxs-lookup"><span data-stu-id="b51d5-132">Custom app policies and settings</span></span>

<span data-ttu-id="b51d5-133">Teams позволяет разработчикам в вашей организации создавать, тестировать и развертывать пользовательские приложения для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="b51d5-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="b51d5-134">Пользовательские приложения можно добавить в Teams, отправив пакет приложения в ZIP-файл непосредственно команде или в личном контексте.</span><span class="sxs-lookup"><span data-stu-id="b51d5-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="b51d5-135">Политики настройки приложений можно использовать для управления тем, кто в вашей организации может отправлять пользовательские приложения.</span><span class="sxs-lookup"><span data-stu-id="b51d5-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="b51d5-136">Вы также можете настроить параметры организации, чтобы управлять тем, могут ли пользователи взаимодействовать с определенными пользовательскими приложениями.</span><span class="sxs-lookup"><span data-stu-id="b51d5-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="b51d5-137">Дополнительные сведения можно найти в статье [Управление политиками и параметрами настраиваемых приложений в Teams](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b51d5-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
