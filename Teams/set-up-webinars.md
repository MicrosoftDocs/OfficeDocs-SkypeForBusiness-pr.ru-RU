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
ms.openlocfilehash: bc1460f93259a9dd3095cf764c38b56ab703bba0
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656052"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="cbfd0-103">Настройка вебинары в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cbfd0-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="cbfd0-104">Эта статья поможет вам настроить вебинары для организации.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="cbfd0-105">Что такое вебинары?</span><span class="sxs-lookup"><span data-stu-id="cbfd0-105">What are webinars?</span></span>

<span data-ttu-id="cbfd0-106">Вебинары — это структурированные собрания, на которых преподаватели и участники имеют четкие роли, которые часто используются для обучения или для подготовки по продажам и маркетингу.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-106">Webinars are structured meetings where instructors and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="cbfd0-107">После настройки вебинары в организации пользователи могут планировать вебинары и открывать регистрацию для участников.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="cbfd0-108">В отличие от традиционных собраний, включавших множество обсуждений и заданий задач, вебинары предназначены для интерактивных презентаций и предоставляют инструменты для анализа участников.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="cbfd0-109">Разрешить пользователям планировать вебинары с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbfd0-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="cbfd0-110">Чтобы настроить вебинары в Teams, можно использовать следующие атрибуты Windows PowerShell **Set-CsTeamsMeetingPolicy:**</span><span class="sxs-lookup"><span data-stu-id="cbfd0-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="cbfd0-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="cbfd0-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="cbfd0-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="cbfd0-112">WhoCanRegister</span></span>
- <span data-ttu-id="cbfd0-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="cbfd0-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="cbfd0-114">Дополнительные сведения о cmdlet см. в документе [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="cbfd0-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="cbfd0-115">Перед запуском этих cmdlets необходимо подключение к Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-115">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="cbfd0-116">Дополнительные сведения см. в Skype для бизнеса Online с [помощью Microsoft 365 или Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="cbfd0-116">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="cbfd0-117">Разрешить пользователям планировать вебинары</span><span class="sxs-lookup"><span data-stu-id="cbfd0-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="cbfd0-118">Чтобы разрешить пользователям в организации планировать вебинары, запустите:</span><span class="sxs-lookup"><span data-stu-id="cbfd0-118">To allow users in your organization to schedule webinars, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration True
```
### <a name="configure-who-can-register-for-webinars"></a><span data-ttu-id="cbfd0-119">Настройка пользователей, которые могут регистрироваться на вебинары</span><span class="sxs-lookup"><span data-stu-id="cbfd0-119">Configure who can register for webinars</span></span>

<span data-ttu-id="cbfd0-120">Вы можете ограничить регистрацию только пользователями в организации или открыть ее для всех пользователей в клиенте и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-120">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="cbfd0-121">По умолчанию **whoCanRegister** включен и установлено значение **Все**.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-121">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="cbfd0-122">Если вы хотите отключить регистрацию на собрании, установите **для allowMeetingRegistration (РазрешитьMeetingRegistration)** false **(Ложь).**</span><span class="sxs-lookup"><span data-stu-id="cbfd0-122">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cbfd0-123">Имейте в виду, что для  **allowMeetingRegistration для allowMeetingRegistration** должно быть установлено разрешение True. </span><span class="sxs-lookup"><span data-stu-id="cbfd0-123">Keep in mind that **AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="cbfd0-124">Кроме того, списки Майкрософт необходимо настроить в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-124">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="cbfd0-125">Дополнительные параметры см. [в параметрах управления списками Майкрософт.](/sharepoint/control-lists)</span><span class="sxs-lookup"><span data-stu-id="cbfd0-125">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

<span data-ttu-id="cbfd0-126">**Чтобы разрешить *только* пользователям в вашей организации регистрироваться для вебинары, запустите:**</span><span class="sxs-lookup"><span data-stu-id="cbfd0-126">**To allow *only* users in your organization to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

<span data-ttu-id="cbfd0-127">Затем запустите:</span><span class="sxs-lookup"><span data-stu-id="cbfd0-127">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="cbfd0-128">**Чтобы разрешить всем пользователям, в том числе анонимным пользователям, регистрироваться в вебинары, запустите:**</span><span class="sxs-lookup"><span data-stu-id="cbfd0-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

<span data-ttu-id="cbfd0-129">Затем запустите:</span><span class="sxs-lookup"><span data-stu-id="cbfd0-129">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> <span data-ttu-id="cbfd0-130">Если анонимное присоединиться отключено в параметрах собрания, анонимные пользователи не смогут присоединяться к вебинасам.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-130">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="cbfd0-131">Дополнительные узнать и включить этот параметр см. в [Teams.](meeting-settings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="cbfd0-131">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="cbfd0-132">Сбор участия в собраниях</span><span class="sxs-lookup"><span data-stu-id="cbfd0-132">Collect meeting attendance</span></span>

<span data-ttu-id="cbfd0-133">Если вы хотите, чтобы организаторы проанализировали, кто зарегистрировал вебинары и участвовал в них, необходимо включить политику **AllowEngagementReport.**</span><span class="sxs-lookup"><span data-stu-id="cbfd0-133">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="cbfd0-134">Для этого в PowerShell запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cbfd0-134">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="cbfd0-135">Настройка параметров вебинара</span><span class="sxs-lookup"><span data-stu-id="cbfd0-135">Configure webinar settings</span></span>

<span data-ttu-id="cbfd0-136">После включения вашей среды для вебинаеров больше не требуется управление администраторами.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-136">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="cbfd0-137">Политика управляет тем, какие параметры будут доступны организаторам вебинаров.</span><span class="sxs-lookup"><span data-stu-id="cbfd0-137">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cbfd0-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cbfd0-138">Related topics</span></span>

- [<span data-ttu-id="cbfd0-139">Политики собраний в Teams - общие</span><span class="sxs-lookup"><span data-stu-id="cbfd0-139">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="cbfd0-140">Документация по Set-CsTeamsMeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="cbfd0-140">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
