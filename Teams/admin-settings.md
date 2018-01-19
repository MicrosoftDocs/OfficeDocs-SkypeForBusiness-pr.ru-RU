---
title: "Параметры администратора для приложений в Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о том, как разрешить и включить приложения в Microsoft Teams, включая загрузку неопубликованных внешних приложений."
ms.openlocfilehash: 4265866bb346da1aa773d337d02fc1c11149f579
ms.sourcegitcommit: ee1c79b6d6d73e5fc702fe55b9e5aee8a7aae793
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="13da0-103">Параметры администратора для приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13da0-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="13da0-104">Приложения — это предоставляемые сторонними службами вкладки, соединители, боты или любое их сочетание.</span><span class="sxs-lookup"><span data-stu-id="13da0-104">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="13da0-105">Центр администрирования Office 365 позволяет настроить политики разрешений для внешних сторонних приложений.</span><span class="sxs-lookup"><span data-stu-id="13da0-105">There are Admin policies that can be configured in the Office 365 Admin Portal to control which external third-party apps are allowed.</span></span> <span data-ttu-id="13da0-106">В них вы можете указать, какие программы следует разрешать, а какие — блокировать, как работать с новыми внешними приложениями и можно ли загружать неопубликованные приложения.</span><span class="sxs-lookup"><span data-stu-id="13da0-106">These policies let you specify which apps are allowed and disallowed, new external App behavior, as well as whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="13da0-107">Настройки администрирования для приложений Teams находятся в центре администрирования Office 365 в разделе **Параметры**  >  **Службы и надстройки** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="13da0-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="13da0-108">Если вы вошли как администратор Office 365, воспользуйтесь ссылкой</span><span class="sxs-lookup"><span data-stu-id="13da0-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> <span data-ttu-id="13da0-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="13da0-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span> 

<span data-ttu-id="13da0-110">**Allow external apps in Microsoft Teams (Разрешить внешние приложения в Microsoft Teams)**</span><span class="sxs-lookup"><span data-stu-id="13da0-110">**Allow external apps in Microsoft Teams**</span></span>

<span data-ttu-id="13da0-111">По умолчанию в Microsoft Teams разрешены все внешние приложения.</span><span class="sxs-lookup"><span data-stu-id="13da0-111">By default, allow external apps in Microsoft Teams is enabled with all apps selected.</span></span> <span data-ttu-id="13da0-112">Если задать для этой политики значение **"Отключено"**, то все внешние приложения сторонних разработчиков будут запрещены.</span><span class="sxs-lookup"><span data-stu-id="13da0-112">When turning this policy to **“Off”**, then all external third-party apps are disabled.</span></span> <span data-ttu-id="13da0-113">Вы можете настроить этот аспект более детально, разрешая и запрещая внешние приложения в индивидуальном порядке.</span><span class="sxs-lookup"><span data-stu-id="13da0-113">You can get more granular and allow external apps to be enabled and uncheck specific apps that you want to disable on an individual basis.</span></span>

<span data-ttu-id="13da0-114">**Enable new external apps by default (Разрешать новые внешние приложения по умолчанию)**</span><span class="sxs-lookup"><span data-stu-id="13da0-114">**Enable new external apps by default**</span></span>

<span data-ttu-id="13da0-115">Эта политика определяет, доступны ли пользователям этого клиента новые приложения, отправляемые в каталог приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="13da0-115">Whenever new apps are submitted to the Teams App Catalog, this switch controls whether they are available for users in this tenant.</span></span> <span data-ttu-id="13da0-116">По умолчанию для нее задано значение **"Включено"**, то есть пользователи получают доступ к приложениям сразу после добавления последних в каталог приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="13da0-116">By default, this policy is set to **“On”** which allows users to have access to apps as soon as they are added to the Team’s app catalog.</span></span> <span data-ttu-id="13da0-117">Если вы хотите проверять приложения перед использованием в Teams, задайте значение **"Отключено"**.</span><span class="sxs-lookup"><span data-stu-id="13da0-117">If you would prefer to validate apps before allowing them to be utilized in Teams, then set this policy to **Off.**</span></span> <span data-ttu-id="13da0-118">При использовании значения **"Отключено"** не забывайте регулярно оценивать вновь добавляемые приложения, чтобы предоставить пользователям доступ к актуальным и инновационным функциям.</span><span class="sxs-lookup"><span data-stu-id="13da0-118">Just remember, if you set this to **"Off",** you should evaluate newly added apps on a regular basis to make sure your users benefit from the latest innovations and additions of apps.</span></span>

<span data-ttu-id="13da0-119">**Allow side-loading of external apps (Разрешить загрузку неопубликованных внешних приложений)**</span><span class="sxs-lookup"><span data-stu-id="13da0-119">**Allow side-loading of external apps**</span></span>

<span data-ttu-id="13da0-120">Загружать неопубликованные приложения в Microsoft Teams могут только владельцы команд или участники с соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="13da0-120">Only Team owners or members who are granted permissions, can side-load apps into Microsoft Teams.</span></span> <span data-ttu-id="13da0-121">Ниже представлены некоторые преимущества такой загрузки:</span><span class="sxs-lookup"><span data-stu-id="13da0-121">Some benefits of side-loading apps into Microsoft Teams are:</span></span>

-   <span data-ttu-id="13da0-122">Возможность протестировать приложения перед отправкой в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="13da0-122">Ability to test apps prior to submitting to Microsoft</span></span>

-   <span data-ttu-id="13da0-123">Возможность предоставить приложение напрямую пользователям организации, минуя Магазин Office.</span><span class="sxs-lookup"><span data-stu-id="13da0-123">Provide apps directly to users within your organization without having to submit to the Office Store.</span></span>

<span data-ttu-id="13da0-124">Дополнительные сведения о загрузке неопубликованных приложений в Microsoft Teams см. в статье: [Загрузка неопубликованных приложений в команду](https://go.microsoft.com/fwlink/?linkid=854631).</span><span class="sxs-lookup"><span data-stu-id="13da0-124">To learn more about side loading apps into Microsoft Teams, visit: [Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631).</span></span>

![Снимок экрана с разделом приложений в параметрах Microsoft Teams.](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
