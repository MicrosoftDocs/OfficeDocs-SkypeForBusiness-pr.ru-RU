---
title: Управление группами Майкрософт возможностями в организации Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Узнайте, как включить или отключить группами Майкрософт приложений в организации Office 365, включая вкладки, соединители, программы-роботы или любое сочетание трех.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0ff482ccd6486fcab836565033a0cf7e02517717
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965622"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="4e954-103">Управление группами Майкрософт возможностями в организации Office 365</span><span class="sxs-lookup"><span data-stu-id="4e954-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="4e954-104">Все параметры команды скоро перемещаются в новый группами Майкрософт & Скайп по центру администрирования бизнес.</span><span class="sxs-lookup"><span data-stu-id="4e954-104">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="4e954-105">Только группы компонент, который управляется в центре администрирования Office 365 — приложения.</span><span class="sxs-lookup"><span data-stu-id="4e954-105">The only Teams feature that is managed in the Office 365 admin center is Apps.</span></span> 

<span data-ttu-id="4e954-106">Если не указано иное, по умолчанию для параметра установлено значение "Включено".</span><span class="sxs-lookup"><span data-stu-id="4e954-106">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="4e954-107">Настройки администрирования для Microsoft Teams находятся в Центре администрирования Office 365 в разделе **Параметры**  >  **Службы и надстройки** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="4e954-107">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="4e954-108">Если вы вошли как администратор Office 365, воспользуйтесь ссылкой</span><span class="sxs-lookup"><span data-stu-id="4e954-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="4e954-109">Параметры Office 365 на уровне клиента</span><span class="sxs-lookup"><span data-stu-id="4e954-109">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="4e954-110">В **Параметры на уровне клиента**можно включить или отключить приложений.</span><span class="sxs-lookup"><span data-stu-id="4e954-110">In **Tenant-wide settings**, you can turn on or turn off Apps.</span></span>

<span data-ttu-id="4e954-111">Чтобы изменить в Teams **параметры уровня клиента**, зайдите в Центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e954-111">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="4e954-112">Выберите **Settings (Параметры)** > **Services & add-ins (Службы и надстройки)** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="4e954-112">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

## <a name="apps"></a><span data-ttu-id="4e954-113">Приложения</span><span class="sxs-lookup"><span data-stu-id="4e954-113">Apps</span></span>

<span data-ttu-id="4e954-114">Приложения — это предоставляемые сторонними службами вкладки, соединители, боты или любое их сочетание.</span><span class="sxs-lookup"><span data-stu-id="4e954-114">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="4e954-115">Центр администрирования Office 365 позволяет настроить политики администрирования Microsoft Teams, которые определяют разрешенные внешние сторонние приложения.</span><span class="sxs-lookup"><span data-stu-id="4e954-115">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="4e954-116">Эти политики позволяют указать, какие приложения могут и не разрешены, новое поведение внешнего приложения и разрешено ли загрузка со стороны приложений.</span><span class="sxs-lookup"><span data-stu-id="4e954-116">These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="4e954-117">В разделе **Приложения** вы можете настроить для своей организации следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4e954-117">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![Снимок экрана с разделом приложений.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="4e954-119">**Allow external apps in Microsoft Teams** (Разрешить внешние приложения в Microsoft Teams). Когда этот параметр включен, пользователи могут добавлять вкладки и боты, доступные для клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e954-119">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![Снимок экрана с параметром "Allow external apps control" (Разрешить управление внешними приложениями) в разделе приложений.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="4e954-121">**Enable new external apps by default** (Включить новые внешние приложения по умолчанию). Если этот параметр включен, пользователи могут активировать новые приложения сразу после их добавления в каталог приложений Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4e954-121">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="4e954-122">Если вы хотите контролировать новые приложения, отключите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="4e954-122">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="4e954-123">В этом случае не забывайте периодически просматривать новые приложения, чтобы ваша организация не пропустила появление новых интересных программ.</span><span class="sxs-lookup"><span data-stu-id="4e954-123">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="4e954-124">**Allow sideloading of external apps** (Разрешить загрузку неопубликованных внешних приложений). Когда этот параметр включен, пользователи могут устанавливать и активировать настраиваемые вкладки и боты.</span><span class="sxs-lookup"><span data-stu-id="4e954-124">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="4e954-125">Подробнее см. в статье [Параметры администратора для приложений в Microsoft Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4e954-125">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 

