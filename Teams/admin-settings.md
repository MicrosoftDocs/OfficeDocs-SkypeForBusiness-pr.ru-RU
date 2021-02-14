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
description: Узнайте о политиках и параметрах, которые можно использовать для управления приложениями для организации в Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb824c7082679591b3fa39a1c8a4b13152e0cc75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532526"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="a3dc5-103">Параметры администратора для приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a3dc5-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="a3dc5-104">Приложения предоставляют вам все необходимые инструменты для работы с Teams.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="a3dc5-105">В этих приложениях доступны вкладки, расширения для обмена сообщениями, соединители и боты, предоставляемые корпорацией Майкрософт, сторонними разработчиками или сторонними разработчиками.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="a3dc5-106">Вы управляете приложениями для своей организации в **приложениях Teams** в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="a3dc5-107">[(См. статью "Использование](https://docs.microsoft.com/microsoftteams/using-admin-roles) ролей администратора Teams для управления Teams", чтобы ознакомиться с получением ролей и разрешений администраторов.) Например, вы можете разрешить или заблокировать приложения на уровне организации, настроить политики для управления приложениями, доступными пользователям Teams, и настроить Teams, закрепление наиболее важных приложений для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-107">(See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="a3dc5-108">Мы постоянно улучшаем приложение в Teams и добавляем функции и функции.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="a3dc5-109">Со временем мы будем строить дополнительные возможности управления приложениями, поэтому ознакомьтесь с самой информацией о политиках приложений.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="a3dc5-110">Управление приложениями</span><span class="sxs-lookup"><span data-stu-id="a3dc5-110">Manage apps</span></span>

<span data-ttu-id="a3dc5-111">На странице **"Управление приложениями"** можно просматривать и управлять всеми приложениями Teams в каталоге приложений организации.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="a3dc5-112">Вы можете посмотреть состояние и свойства приложений на уровне организации, заблокировать или разрешить приложения на уровне организации, добавить новые пользовательские приложения в каталог клиентов и управлять настройками приложений для всей организации.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="a3dc5-113">На **странице "Управление** приложениями" вы можете просмотреть все доступные приложения в каталоге клиента, предоставив информацию, необходимую для решения о том, какие приложения следует разрешить или заблокировать в организации.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="a3dc5-114">Затем вы можете использовать политики разрешений [приложений,](#app-permission-policies)политики настройки [приложений,](#app-setup-policies)а также настраиваемые политики и параметры приложений для настройки работы с приложениями для определенных пользователей в организации. [](#custom-app-policies-and-settings)</span><span class="sxs-lookup"><span data-stu-id="a3dc5-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="a3dc5-115">Дополнительные узнать см. в [подмносях "Управление приложениями" в Teams.](manage-apps.md)</span><span class="sxs-lookup"><span data-stu-id="a3dc5-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="a3dc5-116">Политики разрешений приложений</span><span class="sxs-lookup"><span data-stu-id="a3dc5-116">App permission policies</span></span>

<span data-ttu-id="a3dc5-117">С помощью политик разрешений приложений вы можете управлять приложениями, доступными определенным пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="a3dc5-118">Вы можете разрешить или заблокировать все приложения или определенные приложения, опубликованные Microsoft, сторонними организациями и вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="a3dc5-119">Например, с помощью политик разрешений приложений можно:</span><span class="sxs-lookup"><span data-stu-id="a3dc5-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="a3dc5-120">Постепенно размыкать новые сторонние или пользовательские встроенные приложения для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="a3dc5-121">Упростите пользовательский интерфейс, особенно если вы начнете развертывание Teams в организации.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="a3dc5-122">Чтобы узнать больше, перейдите к [управлению политиками разрешений приложений в Teams.](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a3dc5-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="a3dc5-123">Политики настройки приложений</span><span class="sxs-lookup"><span data-stu-id="a3dc5-123">App setup policies</span></span>

<span data-ttu-id="a3dc5-124">С помощью политик настройки приложений можно настраивать параметры приложения для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="a3dc5-125">Вы можете выбрать приложения, которые нужно закрепить на панели приложений в клиентах Teams, и порядок их появления в веб-версии, на компьютере и в мобильных клиентах.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="a3dc5-126">Вот несколько примеров использования политик настройки приложений:</span><span class="sxs-lookup"><span data-stu-id="a3dc5-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="a3dc5-127">Информирование и внедрение основных приложений.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="a3dc5-128">Например, закрепите пользовательское приложение для подбора персонала и управления персоналом для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="a3dc5-129">Выборочная закрепление основных функций Teams, таких как чат, команды и вызовы.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="a3dc5-130">Это помогает обеспечить вовлечение пользователей в определенные действия в Teams.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="a3dc5-131">Дополнительные узнать об этом можно в [области "Управление политиками настройки приложений" в Teams.](teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a3dc5-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="a3dc5-132">Настраиваемые политики и параметры приложений</span><span class="sxs-lookup"><span data-stu-id="a3dc5-132">Custom app policies and settings</span></span>

<span data-ttu-id="a3dc5-133">Teams позволяет разработчикам в вашей организации создавать, тестировать и развертывать пользовательские приложения для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="a3dc5-134">Пользовательские приложения можно добавить в Teams, загрузив пакет приложения в ZIP-файле напрямую в группу или в личном контексте.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="a3dc5-135">С помощью политик настройки приложений вы можете контролировать, кто из вашей организации может загружать пользовательские приложения.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="a3dc5-136">Вы также можете настроить параметры для всей организации, чтобы контролировать, могут ли пользователи работать с определенными пользовательскими приложениями.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="a3dc5-137">Чтобы узнать больше, перейдите к [управлению настраиваемой политикой и](teams-custom-app-policies-and-settings.md)настройками приложений в Teams.</span><span class="sxs-lookup"><span data-stu-id="a3dc5-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
