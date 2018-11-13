---
title: Настройка для live события в группами Майкрософт
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Узнайте, действия по настройке live для событий в Майкрософт для групп, включая подготовке сети, назначение лицензий, включение live события расписания для пользователей и настройка поставщика eCDN.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296382"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a><span data-ttu-id="979ca-103">Настройка для live события в группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="979ca-103">Set up for live events in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="979ca-104">При установке для событий в реальном времени, существует несколько этапов, которые необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="979ca-104">When you are setting up for live events, there are several steps that you must take:</span></span>

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a><span data-ttu-id="979ca-105">Этап 1: Настройка сети для live событий в группах Microsoft</span><span class="sxs-lookup"><span data-stu-id="979ca-105">Step 1: Set up your network for live events in Microsoft Teams</span></span>
<span data-ttu-id="979ca-106">События live краткое требуют по [подготовке сети вашей организации для групп Майкрософт](https://docs.microsoft.com/microsoftteams/prepare-network).</span><span class="sxs-lookup"><span data-stu-id="979ca-106">The quick start live events require you to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>  

## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="979ca-107">Шаг 2. Покупка и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="979ca-107">Step 2: Get and assign licenses</span></span>
<span data-ttu-id="979ca-108">Убедитесь, у вас есть правильные лицензии назначения для [пользователей, которые можно создавать и планирования событий в реальном времени?](#who-can-create-and-schedule-live-events) и [пользователей, которые можно посмотреть событий в реальном времени?](#who-can-watch-live-events).</span><span class="sxs-lookup"><span data-stu-id="979ca-108">Ensure you have correct license assignments for [Who can create and schedule live events?](#who-can-create-and-schedule-live-events) and [Who can watch live events?](#who-can-watch-live-events).</span></span>

## <a name="step-3-enable-live-event-scheduling-for-users"></a><span data-ttu-id="979ca-109">Шаг 3: Включите трансляция расписание для пользователей</span><span class="sxs-lookup"><span data-stu-id="979ca-109">Step 3: Enable live event scheduling for users</span></span>
<span data-ttu-id="979ca-110">Планирование Live события включен по умолчанию для группы пользователей, но если которым требуется пользователям планировать кодировщика внешних событий, которые существуют дополнительные действия, которые необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="979ca-110">Live event scheduling is enabled by default for Teams users but if you are wanting users to schedule external encoder events there are additional steps that you must do.</span></span>

### <a name="for-quick-start-events"></a><span data-ttu-id="979ca-111">Для события быстрого запуска</span><span class="sxs-lookup"><span data-stu-id="979ca-111">For quick start events</span></span>
<span data-ttu-id="979ca-112">Параметр *AllowBroadcastScheduling* в **TeamsMeetingBroadcastPolicy** в команды PowerShell для управления ли пользователь может создавать событий в реальном времени в группах, или нет.</span><span class="sxs-lookup"><span data-stu-id="979ca-112">Use the setting *AllowBroadcastScheduling* in **TeamsMeetingBroadcastPolicy** in Teams PowerShell to control whether the user can create live events in Teams or not.</span></span> <span data-ttu-id="979ca-113">Дополнительные сведения об управлении TeamsMeetingBroadcastPolicy [здесь](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="979ca-113">You can learn more about managing TeamsMeetingBroadcastPolicy [here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

 <span data-ttu-id="979ca-114">Если вы еще не пользовательскую политику, назначенная для пользователей, пользователи будут получать *глобальной* политики, которая имеет запись по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="979ca-114">If you haven't assigned a custom policy assigned to the users, the users will get the *Global* policy, which has recording enabled by default.</span></span>

<span data-ttu-id="979ca-115">Убедитесь, что параметр *AllowBroadcastScheduling* задано значение *True*:</span><span class="sxs-lookup"><span data-stu-id="979ca-115">Verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="979ca-116">Назначьте пользователя в *глобальную* политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-116">Then assign the user to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a><span data-ttu-id="979ca-117">Пользовательские сценарии</span><span class="sxs-lookup"><span data-stu-id="979ca-117">User scenarios</span></span>
<span data-ttu-id="979ca-118">**Требуется, чтобы все пользователи в вашей компании, чтобы иметь возможность создания событий в реальном времени.**</span><span class="sxs-lookup"><span data-stu-id="979ca-118">**You want all users in your company to be able to create live events.**</span></span>

<span data-ttu-id="979ca-119">Если пользователи которым назначена политика *Glocal* , запустите и убедитесь, что *AllowBroadcastScheduling* \* имеет значение *True*:</span><span class="sxs-lookup"><span data-stu-id="979ca-119">If users are assigned the *Glocal* policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="979ca-120">Если пользователи назначена политика, отличный от *глобальной* политики, выполните следующую команду и убедитесь, что *- AllowBroadcastScheduling* задано значение *True*:</span><span class="sxs-lookup"><span data-stu-id="979ca-120">If the users are assigned a policy other than the *Global* policy, run the following and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

<span data-ttu-id="979ca-121">**Требуется трансляция планирования, чтобы быть отключено 100% внутри организации.**</span><span class="sxs-lookup"><span data-stu-id="979ca-121">**You want live event scheduling to be 100% disabled across your organization.**</span></span>

<span data-ttu-id="979ca-122">Отключение широковещательного планирования, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-122">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="979ca-123">Назначение всех пользователей в вашей организации для *глобальной* политики, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-123">Assign all users in your organization to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="979ca-124">**Требуется большое число пользователи должны иметь возможность создания событий в реальном времени, но для предотвращения их создания группы пользователей.**</span><span class="sxs-lookup"><span data-stu-id="979ca-124">**You want a large number of users to be able to create live events, but want to prevent a set of users from creating them.**</span></span>

<span data-ttu-id="979ca-125">Назначение политики *Global* , с помощью **Grant-CsTeamsMeetingBroadcastPolicy** для некоторых пользователей (включено), но сначала выполните следующую команду и убедитесь, что *AllowBroadcastScheduling* задано значение *True*:</span><span class="sxs-lookup"><span data-stu-id="979ca-125">Assign the *Global* policy using the **Grant-CsTeamsMeetingBroadcastPolicy** for some of the users (that you want enabled) but first run the following and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="979ca-126">Назначьте одного или нескольких пользователей в *глобальную* политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-126">Then assign a user or users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="979ca-127">Создайте и назначьте политику для отключения планирования с помощью командлета **Grant-CsTeamsMeetingBroadcastPolicy** другим пользователям, (требуется выключить).</span><span class="sxs-lookup"><span data-stu-id="979ca-127">Create and assign a policy for disabling scheduling using the  **Grant-CsTeamsMeetingBroadcastPolicy** cmdlet to the other users (you want disabled).</span></span> 

<span data-ttu-id="979ca-128">Создание новой политики с ним этот параметр отключен, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-128">Create the new policy with it disabled, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
<span data-ttu-id="979ca-129">Отключить расписание, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-129">Disable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="979ca-130">Затем назначение пользователей для этой политики, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-130">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
<span data-ttu-id="979ca-131">**Хотите live события требуется запретить для большого числа пользователей, но требуется разрешить пользователям создавать их набор.**</span><span class="sxs-lookup"><span data-stu-id="979ca-131">**You want live events to be disabled for a large number of the users, but want to allow a set of users to create them.**</span></span>

<span data-ttu-id="979ca-132">Отключение широковещательного планирования, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-132">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="979ca-133">Назначьте этих пользователей в *глобальную* политику, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-133">Then assign those users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="979ca-134">Создание и назначение политики для включения планирования, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-134">Create and assign a policy for enabling scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="979ca-135">Включить расписание, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-135">Enable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="979ca-136">Затем назначение пользователей для этой политики, выполните:</span><span class="sxs-lookup"><span data-stu-id="979ca-136">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a><span data-ttu-id="979ca-137">Для кодирования внешних событий</span><span class="sxs-lookup"><span data-stu-id="979ca-137">For external encoder events</span></span>
<span data-ttu-id="979ca-138">Необходимо выполнить следующие действия, чтобы включить трансляция расписания для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="979ca-138">You must do the following to enable live event scheduling for those users.</span></span>

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a><span data-ttu-id="979ca-139">Шаг 1: Включение потока Майкрософт для пользователей в вашей организации \*\*</span><span class="sxs-lookup"><span data-stu-id="979ca-139">Step 1: Enable Microsoft Stream for users in your organization\*\*</span></span>
<span data-ttu-id="979ca-140">Поток Microsoft доступна как часть подходящими подписки на Office 365 или как автономную службу.</span><span class="sxs-lookup"><span data-stu-id="979ca-140">Microsoft Stream is available as part of eligible Office 365 subscriptions or as a standalone service.</span></span> <span data-ttu-id="979ca-141">В разделе [Общие сведения о лицензировании потока](https://docs.microsoft.com/stream/license-overview) более подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="979ca-141">See [Stream licensing overview](https://docs.microsoft.com/stream/license-overview) for more details.</span></span>

> <span data-ttu-id="979ca-142">! [ПРИМЕЧАНИЕ] Поток Майкрософт не включены в Business Essentials или бизнеса расширенный планов.</span><span class="sxs-lookup"><span data-stu-id="979ca-142">![NOTE] Microsoft Stream is not included in Business Essentials or Business Premium plans.</span></span>  

<span data-ttu-id="979ca-143">Дополнительные сведения о как обеспечить [Назначение лицензий для пользователей в Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) , чтобы пользователи могут получить доступ к потоку Microsoft.</span><span class="sxs-lookup"><span data-stu-id="979ca-143">Learn more about how you can [assign licenses to users in Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) so that users can access Microsoft Stream.</span></span> <span data-ttu-id="979ca-144">Убедитесь, что поток Microsoft не блокируются для пользователей, как определено в [этой статье](https://docs.microsoft.com/stream/disable-user-organization).</span><span class="sxs-lookup"><span data-stu-id="979ca-144">Ensure Microsoft Stream is not blocked for the users as defined in [this article](https://docs.microsoft.com/stream/disable-user-organization).</span></span>

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a><span data-ttu-id="979ca-145">Шаг 2: Убедитесь, что пользователи имеют разрешение создания live событий в Microsoft потока \*\*</span><span class="sxs-lookup"><span data-stu-id="979ca-145">Step 2: Ensure users have live event creation permission in Microsoft Stream\*\*</span></span>
<span data-ttu-id="979ca-146">По умолчанию администраторы могут создавать внешние кодировщика событий в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="979ca-146">By default, administrators can create external encoder live events.</span></span> <span data-ttu-id="979ca-147">Администратор Microsoft потока можно [Включить дополнительные пользователей для создания live события](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) в потоке.</span><span class="sxs-lookup"><span data-stu-id="979ca-147">Microsoft Stream administrator can [enable additional users for live event creation](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) in Stream.</span></span>  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a><span data-ttu-id="979ca-148">Шаг 3: Убедитесь live события, которое организаторов согласие политики в компании, задание с потока admin \*\*</span><span class="sxs-lookup"><span data-stu-id="979ca-148">Step 3: Ensure live event organizers have consented to the company policy set by Stream admin\*\*</span></span>
<span data-ttu-id="979ca-149">Если администратор Microsoft потока [Настройте политику рекомендации по организации](https://docs.microsoft.com/stream/company-policy-and-consent) и требует, чтобы сотрудники на прием данной политики перед сохранением контента, затем пользователей необходимо сделать перед созданием live события (с внешним кодировщика окончательные) в группах.</span><span class="sxs-lookup"><span data-stu-id="979ca-149">If a Microsoft Stream administrator has [set up a company guidelines policy](https://docs.microsoft.com/stream/company-policy-and-consent) and requires employees to accept this policy before saving content, then users must do so before creating a live event (with External Encoder production) in Teams.</span></span> <span data-ttu-id="979ca-150">Перед развертыванием функции событий в реальном времени в организации убедитесь, что пользователи, ответственных за создание участие в мероприятиях согласие в политике.</span><span class="sxs-lookup"><span data-stu-id="979ca-150">Before you rollout the live events feature in the organization, make sure users who will be creating these live events have consented to the policy.</span></span> 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a><span data-ttu-id="979ca-151">Шаг 4: Установка поставщика eCDN для live события в группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="979ca-151">Step 4: Set up eCDN provider for live events in Microsoft Teams</span></span> 
<span data-ttu-id="979ca-152">Воспроизведение видео трансляция использует адаптивный скорость потоковая передача (ABR), но это одноадресной рассылки потока, что означает, что каждый средства просмотра начало собственные потока видео из Интернета.</span><span class="sxs-lookup"><span data-stu-id="979ca-152">Playback of live event videos uses adaptive bitrate streaming (ABR) but it is a unicast stream, meaning every viewer is getting their own video stream from the internet.</span></span> <span data-ttu-id="979ca-153">Для событий в реальном времени или видео, отправляемые большей части организации может быть значительное пропускной способности сети, используемый службами средств просмотра.</span><span class="sxs-lookup"><span data-stu-id="979ca-153">For live events or videos sent out to large portions of your organization, there could be a significant amount of internet bandwidth consumed by viewers.</span></span> <span data-ttu-id="979ca-154">Для организаций, чтобы уменьшить трафик Интернета для событий в реальном времени live события, для которых интегрированных решений с корпорации Майкрософт доверенных партнеров доставки видео предлагают программного обеспечения определенные сетей (SDNs) или корпоративной сети доставки содержимого (eCDNs).</span><span class="sxs-lookup"><span data-stu-id="979ca-154">For organizations that want to reduce this internet traffic for live events, live events solutions are integrated with Microsoft's trusted video delivery partners offering software defined networks (SDNs) or enterprise content delivery networks (eCDNs).</span></span> <span data-ttu-id="979ca-155">Эти SDN аудио- и eCDN платформы позволяют организациям для оптимизации пропускной способности сети без ущерба для конечного пользователя Просмотр каждый раз.</span><span class="sxs-lookup"><span data-stu-id="979ca-155">These SDN / eCDN platforms enable organizations to optimize network bandwidth without sacrificing end user viewing experiences.</span></span> <span data-ttu-id="979ca-156">Наши партнеры могут помочь включение легче масштабируются и эффективного распределение видео в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="979ca-156">Our partners can help enable a more scalable and efficient video distribution across your enterprise network.</span></span>

<span data-ttu-id="979ca-157">**Покупки и настройка решения за пределами группами Майкрософт** Справка: экспертов масштабирование доставки видео с помощью надежных доставки видео партнеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="979ca-157">**Purchase & setup your solution outside of Microsoft Teams** Get expert help with scaling video delivery by leveraging Microsoft’s trusted video delivery partners.</span></span> <span data-ttu-id="979ca-158">Прежде чем включить поставщик видео доставки для использования с группами необходимо приобрести и настройка решения SDN/eCDN, находящиеся за пределами организации и отдельно от групп.</span><span class="sxs-lookup"><span data-stu-id="979ca-158">Before you can enable a video delivery provider to be used with Teams you must purchase and setup the SDN/eCDN solution outside and separate from Teams.</span></span>

<span data-ttu-id="979ca-159">Следующие решения SDN/eCDN предварительно встроенные и может быть программы установки для использования с Microsoft потока.</span><span class="sxs-lookup"><span data-stu-id="979ca-159">The following SDN/eCDN solutions are pre-integrated and can be setup to be used with Microsoft Stream.</span></span>

- <span data-ttu-id="979ca-160">**Куст потоковая передача** предоставляет мощные и простые решения для рассылки видео и по запросу enterprise.</span><span class="sxs-lookup"><span data-stu-id="979ca-160">**Hive Streaming** provides a simple and powerful solution for live and on-demand enterprise video distribution.</span></span> <span data-ttu-id="979ca-161">Куст — это программное решение, которое не требует дополнительного оборудования или пропускной способности и обеспечивает безопасный способ включения тысячи одновременных средства просмотра видео без воздействия на вашей сети.</span><span class="sxs-lookup"><span data-stu-id="979ca-161">Hive is a software-based solution that requires no additional hardware or bandwidth and provides a secure way to enable thousands of simultaneous video viewers without impact to your network.</span></span> <span data-ttu-id="979ca-162">Для клиентов, которым требуется понять, что наличие видео воздействия на своей сети перед приобретении решения на базе SDN/eCDN также куст потоковая передача предоставляет решения на основе браузера аналитики для клиентов корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="979ca-162">For customers looking to understand the impact video is having on their network prior to purchasing an SDN/eCDN solution, Hive Streaming also provides a browser-based analytics solution for Microsoft customers.</span></span> <span data-ttu-id="979ca-163">[Дополнительные сведения](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span><span class="sxs-lookup"><span data-stu-id="979ca-163">[Learn more](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span></span>
 
- <span data-ttu-id="979ca-164">**Kollective** — это облачная, смарт-авторами рассылки платформа, использующая инфраструктуры сети доставки содержимого, во многих формах, (live потоковое видео, видео по запросу, обновлений программного обеспечения, исправлений безопасности, и т.д.), быстрее надежно и с меньшей пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="979ca-164">**Kollective** is a cloud-based, smart peering distribution platform that leverages your existing network infrastructure to deliver content, in many forms, (live streaming video, on-demand video, software updates, security patches, etc.) faster, more reliably and with less bandwidth.</span></span> <span data-ttu-id="979ca-165">Наш безопасной платформы является надежным, с крупнейших финансовых учреждениях в мире и с без дополнительного оборудования, настройки и обслуживания можно без труда.</span><span class="sxs-lookup"><span data-stu-id="979ca-165">Our secure platform is trusted by the world’s largest financial institutions and with no additional hardware, setup and maintenance are easy.</span></span> <span data-ttu-id="979ca-166">[Дополнительные сведения](http://www.kollective.com).</span><span class="sxs-lookup"><span data-stu-id="979ca-166">[Learn more](http://www.kollective.com).</span></span>
 
- <span data-ttu-id="979ca-167">**OmniCache увеличения** предоставляет рассылки следующего поколения сети и гарантирует удобства доставки видео в глобальной глобальных, как помочь поставщики событий оптимизации пропускной способности сети и поддержки успешные live мероприятий и по запросу Потоковая передача.</span><span class="sxs-lookup"><span data-stu-id="979ca-167">**Ramp OmniCache** provides next-generation network distribution and ensures seamless delivery of video content across global WANs, helping event producers optimize network bandwidth and support successful live event broadcasts and on-demand streaming.</span></span> <span data-ttu-id="979ca-168">Поддержка для увеличения OmniCache краткое live событий в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="979ca-168">The support for Ramp OmniCache for quick start live events is coming soon.</span></span>  <span data-ttu-id="979ca-169">[Дополнительные сведения](http://www.ramp.com).</span><span class="sxs-lookup"><span data-stu-id="979ca-169">[Learn more](http://www.ramp.com).</span></span> 
 
> [!NOTE] 
> <span data-ttu-id="979ca-170">Решение выбранного eCDN зависит от выбранного **стороннего поставщика условия политики конфиденциальности и службы**, какие будут управляет использование поставщика eCDN решения.</span><span class="sxs-lookup"><span data-stu-id="979ca-170">Your chosen eCDN solution is subject to the selected **3rd party provider’s terms of service and privacy policy**, which will governs your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="979ca-171">Использование поставщика eCDN решение не будет использоваться условия лицензирования Майкрософт тома или Online Services терминов.</span><span class="sxs-lookup"><span data-stu-id="979ca-171">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="979ca-172">Если вы не согласны с **условиями стороннего поставщика**, не включите eCDN решения в группах.</span><span class="sxs-lookup"><span data-stu-id="979ca-172">If you do not agree to the **3rd party provider’s terms**, then don't enable the eCDN solution in Teams.</span></span> 

<span data-ttu-id="979ca-173">**Настройка eCDN «Быстрый запуск» событий в реальном времени** Можно настроить поставщика eCDN для событий в реальном времени в группах, с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="979ca-173">**Set up an eCDN for "Quick start" live events** You can configure eCDN provider for live events in Teams using PowerShell.</span></span> 

> [!NOTE] 
> <span data-ttu-id="979ca-174">Поставщик единого eCDN можно настроить для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="979ca-174">A single eCDN provider can be configured for your organization.</span></span> 

<span data-ttu-id="979ca-175">***Куст*** Командлет [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell можно использовать для настройки поставщика eCDN.</span><span class="sxs-lookup"><span data-stu-id="979ca-175">***Hive*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="979ca-176">Приобрести лицензии идентификатор и API URL-адрес шаблона от вашей куст контакта, затем выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="979ca-176">First obtain the license ID and API template URL from your Hive contact then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="979ca-177">***Kollective*** Командлет [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell можно использовать для настройки поставщика eCDN.</span><span class="sxs-lookup"><span data-stu-id="979ca-177">***Kollective*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="979ca-178">Сначала получить маркер API и URL-адрес шаблона API из Kollective контакт, а затем выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="979ca-178">First obtain the API token and the API template URL from your Kollective contact, then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="979ca-179">**Настройка eCDN для событий в реальном времени «Внешние кодировщика»**</span><span class="sxs-lookup"><span data-stu-id="979ca-179">**Set up an eCDN for "External encoder" live events**</span></span> 

<span data-ttu-id="979ca-180">Если планируется создание live событий, использующих внешний кодировщики, необходимо также [настроить поставщика eCDN с Microsoft потока](https://docs.microsoft.com/stream/network-caching) .</span><span class="sxs-lookup"><span data-stu-id="979ca-180">If you plan to create live events that use external encoders, you will need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching) as well.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="979ca-181">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="979ca-181">Next steps</span></span>
<span data-ttu-id="979ca-182">Перейдите к [группам Confgure события](configure-teams-live-events.md).</span><span class="sxs-lookup"><span data-stu-id="979ca-182">Go to [Confgure Teams live events](configure-teams-live-events.md).</span></span>
