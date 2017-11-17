---
title: "Параметры администратора для приложений в Microsoft Teams | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о том, как разрешить и включить приложения в Microsoft Teams, включая загрузку неопубликованных внешних приложений."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 3e385c1a9a3175d4aaef6ea0eb52d6278c538d94
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2017
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="bbab9-103">Параметры администратора для приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbab9-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="bbab9-104">Этот раздел посвящен вкладкам, соединителям и ботам, а также любым сочетаниям этих возможностей, предоставляемым сторонней службой в качестве приложений.</span><span class="sxs-lookup"><span data-stu-id="bbab9-104">In this section, we refer to tabs, connectors, and bots, or any combination of these capabilities, provided by a single third-party service as Apps.</span></span> <span data-ttu-id="bbab9-105">Настроить разрешенные внешние приложения сторонних разработчиков можно с помощью политик администрирования на портале администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbab9-105">There are Admin policies that can be configured in the Office 365 Admin Portal to control which external third-party apps are allowed.</span></span> <span data-ttu-id="bbab9-106">Они позволяют указать, какие приложения разрешены и запрещены, как работать с внешними приложениями и разрешена ли загрузка неопубликованных приложений.</span><span class="sxs-lookup"><span data-stu-id="bbab9-106">These policies let you specify which apps are allowed and disallowed, new external App behavior, as well as whether side-loading apps is allowed.</span></span>

<span data-ttu-id="bbab9-107">**Allow external apps in Microsoft Teams (Разрешить внешние приложения в Microsoft Teams)**</span><span class="sxs-lookup"><span data-stu-id="bbab9-107">**Allow external apps in Microsoft Teams**</span></span>

<span data-ttu-id="bbab9-108">По умолчанию в Microsoft Teams разрешены все внешние приложения.</span><span class="sxs-lookup"><span data-stu-id="bbab9-108">By default, allow external apps in Microsoft Teams is enabled with all apps selected.</span></span> <span data-ttu-id="bbab9-109">Если задать для этой политики значение **"Отключено"**, то все внешние приложения сторонних разработчиков будут запрещены.</span><span class="sxs-lookup"><span data-stu-id="bbab9-109">When turning this policy to **“Off”**, then all external third-party apps are disabled.</span></span> <span data-ttu-id="bbab9-110">Вы можете настроить этот аспект более детально, разрешая и запрещая внешние приложения в индивидуальном порядке.</span><span class="sxs-lookup"><span data-stu-id="bbab9-110">You can get more granular and allow external apps to be enabled and uncheck specific apps that you want to disable on an individual basis.</span></span>

<span data-ttu-id="bbab9-111">**Enable new external apps by default (Разрешать новые внешние приложения по умолчанию)**</span><span class="sxs-lookup"><span data-stu-id="bbab9-111">**Enable new external apps by default**</span></span>

<span data-ttu-id="bbab9-112">Эта политика определяет, доступны ли пользователям этого клиента новые приложения, отправляемые в каталог приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="bbab9-112">Whenever new apps are submitted to the Teams App Catalog, this switch controls whether they are available for users in this tenant.</span></span> <span data-ttu-id="bbab9-113">По умолчанию для нее задано значение **"Включено"**, то есть пользователи получают доступ к приложениям сразу после добавления последних в каталог приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="bbab9-113">By default, this policy is set to **“On”** which allows users to have access to apps as soon as they are added to the Team’s app catalog.</span></span> <span data-ttu-id="bbab9-114">Если вы хотите проверять приложения перед использованием в Teams, задайте значение **"Отключено"**.</span><span class="sxs-lookup"><span data-stu-id="bbab9-114">If you would prefer to validate apps before allowing them to be utilized in Teams, then set this policy to **Off.**</span></span> <span data-ttu-id="bbab9-115">При использовании значения **"Отключено"** не забывайте регулярно оценивать вновь добавляемые приложения, чтобы предоставить пользователям доступ к актуальным и инновационным функциям.</span><span class="sxs-lookup"><span data-stu-id="bbab9-115">Just remember, if you set this to **"Off",** you should evaluate newly added apps on a regular basis to make sure your users benefit from the latest innovations and additions of apps.</span></span>

<span data-ttu-id="bbab9-116">**Allow side-loading of external apps (Разрешить загрузку неопубликованных внешних приложений)**</span><span class="sxs-lookup"><span data-stu-id="bbab9-116">**Allow side-loading of external apps**</span></span>

<span data-ttu-id="bbab9-117">Загружать неопубликованные приложения в Microsoft Teams могут только владельцы команд или участники с соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="bbab9-117">Only Team owners or members who are granted permissions, can side-load apps into Microsoft Teams.</span></span> <span data-ttu-id="bbab9-118">Ниже представлены некоторые преимущества такой загрузки:</span><span class="sxs-lookup"><span data-stu-id="bbab9-118">Some benefits of side-loading apps into Microsoft Teams are:</span></span>

-   <span data-ttu-id="bbab9-119">Возможность протестировать приложения перед отправкой в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bbab9-119">Ability to test apps prior to submitting to Microsoft</span></span>

-   <span data-ttu-id="bbab9-120">Возможность предоставить приложение напрямую пользователям организации, минуя Магазин Office.</span><span class="sxs-lookup"><span data-stu-id="bbab9-120">Provide apps directly to users within your organization without having to submit to the Office Store.</span></span>

<span data-ttu-id="bbab9-121">Дополнительные сведения о загрузке неопубликованных приложений в Microsoft Teams см. в статье: [Загрузка неопубликованных приложений в команду](https://go.microsoft.com/fwlink/?linkid=854631).</span><span class="sxs-lookup"><span data-stu-id="bbab9-121">To learn more about side loading apps into Microsoft Teams, visit: [Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631).</span></span>

![Снимок экрана с разделом приложений в параметрах Microsoft Teams.](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
