---
title: Настройка вебинары в Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Узнайте, как управлять политиками веб-Teams собраний.
ms.openlocfilehash: 14452b0caeee33f90b59f6581b6fccf4d5e0311b
ms.sourcegitcommit: 4a039550bc5c3a497b6b52c7fed08cadf8268b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926751"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="26243-103">Настройка вебинары в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="26243-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="26243-104">Эта статья поможет вам настроить вебинары для организации.</span><span class="sxs-lookup"><span data-stu-id="26243-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="26243-105">Что такое вебинары?</span><span class="sxs-lookup"><span data-stu-id="26243-105">What are webinars?</span></span>

<span data-ttu-id="26243-106">Вебинары — это структурированные собрания, на которых у участников и участников есть четкие роли, которые часто используются для обучения или для подготовки по продажам и маркетингу.</span><span class="sxs-lookup"><span data-stu-id="26243-106">Webinars are structured meetings where presenters and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="26243-107">После настройки вебинары в организации пользователи могут планировать вебинары и открывать регистрацию для участников.</span><span class="sxs-lookup"><span data-stu-id="26243-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="26243-108">В отличие от традиционных собраний, включавших множество обсуждений и заданий задач, вебинары предназначены для интерактивных презентаций и предоставляют инструменты для анализа участников.</span><span class="sxs-lookup"><span data-stu-id="26243-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="26243-109">Разрешить пользователям планировать вебинары с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="26243-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="26243-110">Чтобы настроить вебинары в Teams, можно использовать следующие атрибуты Windows PowerShell **Set-CsTeamsMeetingPolicy:**</span><span class="sxs-lookup"><span data-stu-id="26243-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="26243-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="26243-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="26243-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="26243-112">WhoCanRegister</span></span>
- <span data-ttu-id="26243-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="26243-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="26243-114">Дополнительные сведения о cmdlet см. в документе [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="26243-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="26243-115">Перед запуском этих cmdlets необходимо подключение к Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26243-115">Before you can run these cmdlets you must be connected to Microsoft Teams PowerShell.</span></span> <span data-ttu-id="26243-116">Дополнительные сведения см. в [Teams помощью Microsoft Teams PowerShell.](/microsoftteams/teams-powershell-managing-teams)</span><span class="sxs-lookup"><span data-stu-id="26243-116">For more information, see [Manage Teams with Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="26243-117">Разрешить пользователям планировать вебинары</span><span class="sxs-lookup"><span data-stu-id="26243-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="26243-118">Вы можете ограничить регистрацию только пользователями в организации или открыть ее для всех пользователей в клиенте и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="26243-118">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="26243-119">По умолчанию **whoCanRegister** включен и установлено значение **Все**.</span><span class="sxs-lookup"><span data-stu-id="26243-119">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="26243-120">Если вы хотите отключить регистрацию на собрании, установите **для allowMeetingRegistration (РазрешитьMeetingRegistration)** false **(Ложь).**</span><span class="sxs-lookup"><span data-stu-id="26243-120">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26243-121">Чтобы разрешитьMeetingRegistration, задайте для  **allowPrivateMeetingMeetingScheduling** (Планирование планирования событий **allowPrivateMeetingScheduling)** true.</span><span class="sxs-lookup"><span data-stu-id="26243-121">**AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="26243-122">Кроме того, списки Майкрософт необходимо настроить в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="26243-122">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="26243-123">Дополнительные новости см. в [параметрах управления списками Майкрософт.](/sharepoint/control-lists)</span><span class="sxs-lookup"><span data-stu-id="26243-123">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

1. <span data-ttu-id="26243-124">Включить регистрацию собраний</span><span class="sxs-lookup"><span data-stu-id="26243-124">Turn on meeting registration</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. <span data-ttu-id="26243-125">Включить планирование частных собраний</span><span class="sxs-lookup"><span data-stu-id="26243-125">Turn on private meeting scheduling</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. <span data-ttu-id="26243-126">Настройка пользователей, которые могут регистрироваться на вебинары</span><span class="sxs-lookup"><span data-stu-id="26243-126">Configure who can register for webinars</span></span>

<span data-ttu-id="26243-127">**Разрешить *только* пользователям в организации регистрироваться для вебинары**</span><span class="sxs-lookup"><span data-stu-id="26243-127">**Allow *only* users in your organization to register for webinars**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="26243-128">**Чтобы разрешить всем пользователям, в том числе анонимным пользователям, регистрироваться в вебинары, запустите:**</span><span class="sxs-lookup"><span data-stu-id="26243-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> <span data-ttu-id="26243-129">Если анонимное присоединиться отключено в параметрах собрания, анонимные пользователи не смогут присоединяться к вебинасам.</span><span class="sxs-lookup"><span data-stu-id="26243-129">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="26243-130">Дополнительные узнать и включить этот параметр см. в [Teams.](meeting-settings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="26243-130">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="26243-131">Сбор участия в собраниях</span><span class="sxs-lookup"><span data-stu-id="26243-131">Collect meeting attendance</span></span>

<span data-ttu-id="26243-132">Если вы хотите, чтобы организаторы проанализировали, кто зарегистрировал вебинары и участвовал в них, необходимо включить политику **AllowEngagementReport.**</span><span class="sxs-lookup"><span data-stu-id="26243-132">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="26243-133">Для этого в PowerShell запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="26243-133">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="26243-134">Настройка параметров вебинара</span><span class="sxs-lookup"><span data-stu-id="26243-134">Configure webinar settings</span></span>

<span data-ttu-id="26243-135">После включения вашей среды для вебинары больше не требуется управление администраторами.</span><span class="sxs-lookup"><span data-stu-id="26243-135">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="26243-136">Политика управляет тем, какие параметры будут доступны организаторам вебинаров.</span><span class="sxs-lookup"><span data-stu-id="26243-136">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="26243-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="26243-137">Related topics</span></span>

- [<span data-ttu-id="26243-138">Политики собраний в Teams - общие</span><span class="sxs-lookup"><span data-stu-id="26243-138">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="26243-139">Документация по Set-CsTeamsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="26243-139">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
