---
title: Мониторинг и повышение качества вызова в Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Используйте параметры качества обслуживания (QoS), а затем аналитические данные о звонках и панель мониторинга качества параметров в Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62e687de154fadffd6ac95bd628fec6f9454cc51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162686"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="884c3-103">Мониторинг и повышение качества вызова в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="884c3-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="884c3-104">В этой статье ключевых инструментов, которые можно использовать для отслеживания, устранения неполадок, управления и улучшения качества звонка в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="884c3-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="884c3-105">Панель мониторинга качества звонка **(CQD):** для анализа тенденций или проблем во всей организации необходимо повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="884c3-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="884c3-106">**Аналитика вызовов:** анализ звонка и качества собраний для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="884c3-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="884c3-107">**Качество обслуживания (QoS):** расставить приоритеты для важного сетевого трафика</span><span class="sxs-lookup"><span data-stu-id="884c3-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="884c3-108">Отслеживание и устранение неполадок с качеством вызова</span><span class="sxs-lookup"><span data-stu-id="884c3-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="884c3-109">Используйте аналитические данные  о звонках  для каждого пользователя и панель мониторинга качества звонка для поиска и устранения неполадок с качеством звонка, которые возникают в ходе текущей работы.</span><span class="sxs-lookup"><span data-stu-id="884c3-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="884c3-110">Это позволяет улучшить производительность сети.</span><span class="sxs-lookup"><span data-stu-id="884c3-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="884c3-111">Оба этих средства находятся в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="884c3-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="884c3-112">**В средстве аналитики** звонков для каждого пользователя Teams \*\*\*\* показана подробная информация об устройствах, сетях и подключениях, связанных с конкретными звонками и собраниями.</span><span class="sxs-lookup"><span data-stu-id="884c3-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  **_specific calls and meetings_** for each user in Teams.</span></span> <span data-ttu-id="884c3-113">Эти сведения используются администратором Teams и агентом службы справки для устранения неполадок с качеством звонка и соединением во время конкретного звонка.</span><span class="sxs-lookup"><span data-stu-id="884c3-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="884c3-114">Для получения дополнительных данных ознакомьтесь со средством аналитики [вызовов](set-up-call-analytics.md) и используйте его для устранения [неполадок с качеством звонка.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="884c3-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="884c3-115">Панель мониторинга качества звонка **(CQD)** позволяет просматривать качество звонка в масштабе всей сети организации. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="884c3-115">**Call Quality Dashboard (CQD)** gives you a **_network-wide view_** of call quality across your organization.</span></span> <span data-ttu-id="884c3-116">Сведения CQD помогут вам выявить и устранить проблемы.</span><span class="sxs-lookup"><span data-stu-id="884c3-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="884c3-117">[Во-первых, настройка CQD.](turning-on-and-using-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="884c3-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="884c3-118">Затем читайте ["Управление звонбом и качеством собраний в Teams".](quality-of-experience-review-guide.md)</span><span class="sxs-lookup"><span data-stu-id="884c3-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="884c3-119">Аналитика вызовов и CQD запускаются параллельно и могут использоваться независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="884c3-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="884c3-120">Например, если специалист службы поддержки связи определяет, что ему нужна дополнительная помощь в устранении неполадок со звонком пользователя, звонок передается специалисту службы поддержки связи, у которого есть доступ к дополнительным сведениям о вызове.</span><span class="sxs-lookup"><span data-stu-id="884c3-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="884c3-121">В свою очередь, инженер службы поддержки связи оповещает сетевого инженера о возможной проблеме, связанной с сайтом, которые он заметил в средстве аналитики вызовов.</span><span class="sxs-lookup"><span data-stu-id="884c3-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="884c3-122">Сетевой инженер проверяет CQD на наличие общей проблемы, связанной с сайтом, которая может одной из причин возникновения проблемы со звонками пользователя.</span><span class="sxs-lookup"><span data-stu-id="884c3-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="884c3-123">Расставить приоритеты для важного сетевого трафика с помощью QoS</span><span class="sxs-lookup"><span data-stu-id="884c3-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="884c3-124">Когда пользователи начинают использовать Teams для звонков и собраний, они могут испытывать разговение или вырезание голосового звонка из звонка или собрания.</span><span class="sxs-lookup"><span data-stu-id="884c3-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="884c3-125">Общее видео может полностью зависать или провисать.</span><span class="sxs-lookup"><span data-stu-id="884c3-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="884c3-126">Это связано с IP-пакетами, которые представляют трафик голосовой и видеосвязи, который перегружен сетью и выходит из последовательности или вообще не передается.</span><span class="sxs-lookup"><span data-stu-id="884c3-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="884c3-127">В этом случае (или во избежание этого) используйте качество обслуживания **(QoS).**</span><span class="sxs-lookup"><span data-stu-id="884c3-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="884c3-128">С помощью QoS вы настроили приоритет сетевого трафика с задержкой (например, голосового или видеопотока), позволяя ему "вырезать в прямом" направлении перед менее конфиденциальным трафиком (например, загрузка нового приложения, где дополнительная секунда для скачивания не имеет большого дела).</span><span class="sxs-lookup"><span data-stu-id="884c3-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="884c3-129">QoS позволяет выявлять и пометить все пакеты в потоках реального времени с помощью объектов групповой политики Windows и функции маршрутизация, которая называется списками управления доступом на основе порта, которая позволяет сети передавать голосовые и видеозвонки и делиться экранами с собственной выделенной пропускной способностью сети.</span><span class="sxs-lookup"><span data-stu-id="884c3-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="884c3-130">Лучше всего внедрить QoS во внутреннюю сеть, готовясь к внедрению Teams, но это можно сделать в любое время.</span><span class="sxs-lookup"><span data-stu-id="884c3-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="884c3-131">Если у вас маленький размер, возможно, QoS не нужен.</span><span class="sxs-lookup"><span data-stu-id="884c3-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="884c3-132">Когда все будет готово, прочитайте статью "Реализация качества обслуживания [(QoS) в Microsoft Teams".](QoS-in-Teams.md)</span><span class="sxs-lookup"><span data-stu-id="884c3-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="884c3-133">Чтобы использовать QoS для управления трафиком собраний, ознакомьтесь с настройками для обработки трафика мультимедиа в режиме реального времени для [собраний Teams.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)</span><span class="sxs-lookup"><span data-stu-id="884c3-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="884c3-134">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="884c3-134">Related Topics</span></span>

[<span data-ttu-id="884c3-135">Настройка аналитики вызовов</span><span class="sxs-lookup"><span data-stu-id="884c3-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="884c3-136">Использование аналитики звонков для устранения проблем с качеством звонка</span><span class="sxs-lookup"><span data-stu-id="884c3-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="884c3-137">Настройка CQD</span><span class="sxs-lookup"><span data-stu-id="884c3-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="884c3-138">Управление звонбом и качеством собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="884c3-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="884c3-139">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="884c3-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)