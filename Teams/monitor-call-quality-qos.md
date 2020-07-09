---
title: Мониторинг и улучшение качества связи в Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Используйте параметры качества обслуживания (QoS), а затем — панель мониторинга качества службы аналитики и звонков в Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085941"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="566f0-103">Мониторинг и улучшение качества связи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="566f0-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="566f0-104">В этой статье описаны три ключевых средства, которые можно использовать для отслеживания и устранения неисправностей, управления и улучшения качества связи в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="566f0-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="566f0-105">**Панель мониторинга качества звонков (CQD)**: анализ тенденций и проблем, связанных с организационными масштабами, и улучшенная производительность</span><span class="sxs-lookup"><span data-stu-id="566f0-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="566f0-106">**Аналитика звонков**: для анализа качества звонков и собраний для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="566f0-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="566f0-107">**Качество обслуживания (QoS)**: назначение приоритета для важного сетевого трафика</span><span class="sxs-lookup"><span data-stu-id="566f0-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="566f0-108">Мониторинг качества связи и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="566f0-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="566f0-109">Для поиска и устранения проблем с качеством связи, которые возникают в ходе текущей работы, вы будете использовать панель мониторинга **звонков** и **качества связи** для пользователей.</span><span class="sxs-lookup"><span data-stu-id="566f0-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="566f0-110">Это позволяет повысить производительность в сети.</span><span class="sxs-lookup"><span data-stu-id="566f0-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="566f0-111">Оба этих средства находятся в центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="566f0-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="566f0-112">В средстве **аналитики звонков** выводятся подробные сведения о устройствах, сетях и подключениях, связанных с ***конкретными звонками и собраниями*** для каждого пользователя в Teams.</span><span class="sxs-lookup"><span data-stu-id="566f0-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in Teams.</span></span> <span data-ttu-id="566f0-113">Агенты администратора и службы поддержки Teams будут использовать эту информацию для устранения проблем с качеством связи и подключением в ходе определенного звонка.</span><span class="sxs-lookup"><span data-stu-id="566f0-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="566f0-114">Дополнительные сведения можно найти в статье [Настройка средства аналитики звонков](set-up-call-analytics.md) и [использование средств аналитики звонков для устранения](use-call-analytics-to-troubleshoot-poor-call-quality.md)некачественной связи.</span><span class="sxs-lookup"><span data-stu-id="566f0-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="566f0-115">**Панель мониторинга качества звонков (CQD)** дает вам возможность видеть качество связи в вашей организации по ***всей сети*** .</span><span class="sxs-lookup"><span data-stu-id="566f0-115">**Call Quality Dashboard (CQD)** gives you a ***network-wide view*** of call quality across your organization.</span></span> <span data-ttu-id="566f0-116">Используйте сведения CQD, которые помогут вам найти и устранить проблемы.</span><span class="sxs-lookup"><span data-stu-id="566f0-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="566f0-117">Сначала [Настройте CQD](turning-on-and-using-call-quality-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="566f0-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="566f0-118">Затем прочтите [Управление качеством звонков и собраний в Teams](quality-of-experience-review-guide.md).</span><span class="sxs-lookup"><span data-stu-id="566f0-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="566f0-119">Анализ звонков и CQD выполняются параллельно и могут использоваться независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="566f0-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="566f0-120">Например, если специалист по поддержке связи определит, что ему нужна дополнительная помощь по устранению неполадок, возникающих при вызове пользователя, они будут переданы специалистам службы поддержки по связи, у кого есть доступ к дополнительным сведениям о звонке.</span><span class="sxs-lookup"><span data-stu-id="566f0-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="566f0-121">В свою очередь специалист службы поддержки связи предупреждает инженера сети о возможной неполадке, связанной с сайтом, в службе аналитики звонков.</span><span class="sxs-lookup"><span data-stu-id="566f0-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="566f0-122">Сетевой инженер проверяет, может ли общая проблема, связанная с веб-сайтом, выCQD проблему с вызовом пользователя.</span><span class="sxs-lookup"><span data-stu-id="566f0-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="566f0-123">Определение приоритетов для важных сетевых трафиков с помощью QoS</span><span class="sxs-lookup"><span data-stu-id="566f0-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="566f0-124">Поскольку пользователи применяют команды для звонков и собраний, они могут столкнуться с голосовым звонком вызывающего абонента или за его пределами, а также за них или на собрании.</span><span class="sxs-lookup"><span data-stu-id="566f0-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="566f0-125">Общее видео может зависать или Pixelate или вообще не работать.</span><span class="sxs-lookup"><span data-stu-id="566f0-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="566f0-126">Это обусловлено тем, что IP-пакеты, обозначающие голосовой и видеотрафик, сталкиваются с перегрузкой сети и поступающими из нее.</span><span class="sxs-lookup"><span data-stu-id="566f0-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="566f0-127">Если это случится (или не допустить, чтобы оно происходило на первом случае), используйте **службу качества обслуживания (QoS)**.</span><span class="sxs-lookup"><span data-stu-id="566f0-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="566f0-128">С помощью QoS вы определяете приоритет сетевого трафика с задержкой (например, голосовых и видеопотоков), позволяя ему обходить в линии в начале трафика с меньшими секретами (например, загружать новое приложение, где дополнительная секунда для скачивания не является серьезной).</span><span class="sxs-lookup"><span data-stu-id="566f0-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="566f0-129">QoS определяет и помечает все пакеты в потоках в реальном времени с помощью объектов групповой политики Windows и функцию маршрутизации, которая называется списком управления доступом на основе порта, что указывает сети для предоставления голосового, видеосигнала и экрана доступа к собственной выделенной пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="566f0-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="566f0-130">В идеале вы будете реализовывать качество обслуживания во внутренней сети во время подготовки к развертыванию групп, но вы можете сделать это в любое время.</span><span class="sxs-lookup"><span data-stu-id="566f0-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="566f0-131">Если вы занимаетесь небольшим объемом, возможно, вам не нужна служба QoS.</span><span class="sxs-lookup"><span data-stu-id="566f0-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="566f0-132">Когда вы будете готовы, ознакомьтесь [со статьей реализация качества обслуживания (QoS) в Microsoft Teams](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="566f0-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="566f0-133">Чтобы использовать службу QoS для управления трафиком собрания, прочтите файл [Настройка того, как вы хотите обрабатывать трафик мультимедиа в реальном времени для собраний Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span><span class="sxs-lookup"><span data-stu-id="566f0-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="566f0-134">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="566f0-134">Related Topics</span></span>

[<span data-ttu-id="566f0-135">Настройка средства аналитики звонков</span><span class="sxs-lookup"><span data-stu-id="566f0-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="566f0-136">Использование аналитики звонков для устранения проблем с качеством звонка</span><span class="sxs-lookup"><span data-stu-id="566f0-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="566f0-137">Настройка CQD</span><span class="sxs-lookup"><span data-stu-id="566f0-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="566f0-138">Управление качеством звонков и собраний в Teams</span><span class="sxs-lookup"><span data-stu-id="566f0-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="566f0-139">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="566f0-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

