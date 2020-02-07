---
title: Подготовка сети организации к использованию Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
audience: admin
description: Сведения о подготовке сети Microsoft Teams и управлении ею. Здесь приведены требования к сети и пропускной способности, а также дополнительные рекомендации.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d331a063feacbaea5cb510c316d2b27d982eb03
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834639"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="c7dc7-104">Подготовка сети организации к использованию Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c7dc7-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="c7dc7-105">Teams сочетает в себе три формы трафика:</span><span class="sxs-lookup"><span data-stu-id="c7dc7-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="c7dc7-106">Трафик данных между интернет-средой Office 365 и клиентом Teams (сигналы, присутствие, чат, отправка и скачивание файлов, синхронизация с OneNote).</span><span class="sxs-lookup"><span data-stu-id="c7dc7-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="c7dc7-107">Трафик однорангового взаимодействия в реальном времени (звук, видео, демонстрация рабочего стола).</span><span class="sxs-lookup"><span data-stu-id="c7dc7-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="c7dc7-108">Трафик конференц-связи в реальном времени (звук, видео, демонстрация рабочего стола).</span><span class="sxs-lookup"><span data-stu-id="c7dc7-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="c7dc7-109">Это затрагивает сеть на двух уровнях: одноранговый трафик протекает напрямую между клиентами Microsoft Teams, а во время собраний трафик протекает между клиентами Microsoft Teams и средой Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-109">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="c7dc7-110">Чтобы оптимизировать поток трафика, следует обеспечить его протекание как между внутренними сегментами сети (например, между сайтами через глобальную сеть), так и между узлами сети и Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-110">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="c7dc7-111">Закрытие или блокировка определенных портов приведет к ухудшению работы.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-111">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>


<span data-ttu-id="c7dc7-112">Для оптимальной работы с мультимедиа в режиме реального времени в Microsoft Teams ваша сеть должна соответствовать требованиям к сети для Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-112">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="c7dc7-113">Дополнительные сведения можно найти в разделе [качество мультимедиа и производительность сетевого подключения для Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="c7dc7-113">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="c7dc7-114">Для двух определяющих сегментов сети (от клиента до Microsoft EDGE и клиента в Microsoft EDGE) учитывайте следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-114">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="c7dc7-115">Значение</span><span class="sxs-lookup"><span data-stu-id="c7dc7-115">Value</span></span>  |<span data-ttu-id="c7dc7-116">Клиент в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c7dc7-116">Client to Microsoft Edge</span></span>  |<span data-ttu-id="c7dc7-117">Клиент EDGE в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c7dc7-117">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="c7dc7-118">**Задержка (один из способов)**\*</span><span class="sxs-lookup"><span data-stu-id="c7dc7-118">**Latency (one way)** \*</span></span>  |<span data-ttu-id="c7dc7-119">< 50ms</span><span class="sxs-lookup"><span data-stu-id="c7dc7-119">< 50ms</span></span>          |<span data-ttu-id="c7dc7-120">< 30ms</span><span class="sxs-lookup"><span data-stu-id="c7dc7-120">< 30ms</span></span>         |
|<span data-ttu-id="c7dc7-121">**Задержка (время приема-передачи или круговой путь)**\*</span><span class="sxs-lookup"><span data-stu-id="c7dc7-121">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="c7dc7-122">< 100ms</span><span class="sxs-lookup"><span data-stu-id="c7dc7-122">< 100ms</span></span>   |<span data-ttu-id="c7dc7-123">< 60ms</span><span class="sxs-lookup"><span data-stu-id="c7dc7-123">< 60ms</span></span> |
|<span data-ttu-id="c7dc7-124">**Пакетная потеря пакетов**</span><span class="sxs-lookup"><span data-stu-id="c7dc7-124">**Burst packet loss**</span></span>    |<span data-ttu-id="c7dc7-125"><10% во время любого интервала 200ms</span><span class="sxs-lookup"><span data-stu-id="c7dc7-125"><10% during any 200ms interval</span></span>         |<span data-ttu-id="c7dc7-126"><1% в любой интервал 200ms</span><span class="sxs-lookup"><span data-stu-id="c7dc7-126"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="c7dc7-127">**Потеря пакетов**</span><span class="sxs-lookup"><span data-stu-id="c7dc7-127">**Packet loss**</span></span>     |<span data-ttu-id="c7dc7-128"><1% в любой интервал 15S</span><span class="sxs-lookup"><span data-stu-id="c7dc7-128"><1% during any 15s interval</span></span>          |<span data-ttu-id="c7dc7-129"><0,1% в любой интервал 15S</span><span class="sxs-lookup"><span data-stu-id="c7dc7-129"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="c7dc7-130">**Нарушение связей между поступлением пакетов**</span><span class="sxs-lookup"><span data-stu-id="c7dc7-130">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="c7dc7-131"><30ms в любой интервал 15S</span><span class="sxs-lookup"><span data-stu-id="c7dc7-131"><30ms during any 15s interval</span></span>         |<span data-ttu-id="c7dc7-132"><15ms в любой интервал 15S</span><span class="sxs-lookup"><span data-stu-id="c7dc7-132"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="c7dc7-133">**Изменение порядка пакетов**</span><span class="sxs-lookup"><span data-stu-id="c7dc7-133">**Packet reorder**</span></span>    |<span data-ttu-id="c7dc7-134"><пакеты, выходящие за заказ 0,05%</span><span class="sxs-lookup"><span data-stu-id="c7dc7-134"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="c7dc7-135"><пакеты, выходящие за заказ 0,01%</span><span class="sxs-lookup"><span data-stu-id="c7dc7-135"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="c7dc7-136">\*Цели метрики задержки предполагают, что ваш сайт Организации или сайты, а края Майкрософт находятся в одном континенте.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-136">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="c7dc7-137">Подключение сайта Организации к сети Microsoft Network Edge включает в себя первый доступ к сети, который может быть Wi-Fi или другим беспроводным технологиям.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-137">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="c7dc7-138">Для целей производительности сети подразумевается правильная пропускная способность и/или [планирование QoS](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="c7dc7-138">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="c7dc7-139">Другими словами, требования применяются непосредственно к мультимедийному трафику в реальном времени, если сетевое подключение находится в максимальной нагрузке.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-139">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="c7dc7-140">Дополнительные сведения о подготовке сети для Teams можно найти в [планировщике сети](https://docs.microsoft.com/microsoftteams/network-planner).</span><span class="sxs-lookup"><span data-stu-id="c7dc7-140">For more help with preparing your network for Teams, check out [Network Planner](https://docs.microsoft.com/microsoftteams/network-planner).</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="c7dc7-141">Требования к пропускной способности</span><span class="sxs-lookup"><span data-stu-id="c7dc7-141">Bandwidth requirements</span></span>
<span data-ttu-id="c7dc7-142">Microsoft Teams обеспечивает наилучшее качество звука, видео и содержимого вне зависимости от условий сети.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-142">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="c7dc7-143">С помощью переменных кодеков мультимедиа можно согласовать в среде с ограниченной пропускной способностью с минимальным влиянием.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-143">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="c7dc7-144">Но если пропускная способность не очень важна, вы можете оптимизировать качество изображения, в том числе до секунду для видео и 15fps, а также для высококачественной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-144">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a><span data-ttu-id="c7dc7-145">Дополнительные рекомендации относительно сети</span><span class="sxs-lookup"><span data-stu-id="c7dc7-145">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="c7dc7-146">Внешнее разрешение имен</span><span class="sxs-lookup"><span data-stu-id="c7dc7-146">External Name Resolution</span></span>

<span data-ttu-id="c7dc7-147">Убедитесь, что все клиентские компьютеры, на которых работает клиент Teams, могут разрешать внешние запросы DNS для выяснения служб, предоставленных Office 365, а также о том, что брандмауэр не препятствует доступу.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-147">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="c7dc7-148">Сведения о настройке портов брандмауэра можно найти в [адресах URL Office 365 и диапазонах IP-](office-365-urls-ip-address-ranges.md)адресов.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-148">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="c7dc7-149">Размер пула NAT</span><span class="sxs-lookup"><span data-stu-id="c7dc7-149">NAT Pool Size</span></span>

<span data-ttu-id="c7dc7-150">Когда несколько пользователей и устройств получают доступ к Office 365 с помощью преобразования сетевых адресов (NAT) или преобразования адресных адресов (PAT), необходимо убедиться, что устройства, скрытые за каждым IP-адресом с общедоступным маршрутизацией, не превышают поддерживаемый номер.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-150">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="c7dc7-151">Чтобы устранить этот риск, убедитесь, что для пулов NAT назначены соответствующие общедоступные IP-адреса, чтобы избежать исчерпания портов.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-151">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="c7dc7-152">Исчерпание порта вызовет проблемы внутренних конечных пользователей и устройств при подключении к службам Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-152">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="c7dc7-153">Дополнительные сведения можно найти [в разделе поддержка NAT в Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="c7dc7-153">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="c7dc7-154">**Руководство по обнаружению вторжений и предотвращению проблем**</span><span class="sxs-lookup"><span data-stu-id="c7dc7-154">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="c7dc7-155">Если в вашей среде есть система обнаружения вторжения и (или) системы защиты (ИДЕНТИФИКАТОРы и IP-адреса), развернутая для дополнительной защиты исходящих подключений, убедитесь в том, что весь трафик с URL-адресом назначения Office 365 — список разрешений.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-155">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="c7dc7-156">Определение работоспособности сети</span><span class="sxs-lookup"><span data-stu-id="c7dc7-156">Network health determination</span></span>
-----------------

<span data-ttu-id="c7dc7-157">При планировании реализации Microsoft Teams в сети вы должны убедиться, что у вас есть нужная пропускная способность, у вас есть доступ ко всем необходимым IP-адресам, нужные порты открыты и вы собираетесь использовать требования к производительности для мультимедиа в режиме реального времени. .</span><span class="sxs-lookup"><span data-stu-id="c7dc7-157">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="c7dc7-158">Если вы знаете, что вы не отвечаете на эти условия, конечные пользователи не будут получать оптимальную работу в Teams из-за плохого качества во время звонков и собраний.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-158">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="c7dc7-159">Если вы не отвечаете на эти условия, вы можете приостановить проект, чтобы убедиться, что вы отвечаете на эти условия, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-159">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Значок, представляющий точку принятия решения](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="c7dc7-161">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="c7dc7-161">Decision Point</span></span>         |<span data-ttu-id="c7dc7-162">Были ли вы оценены возможности сети для поддержки мультимедиа в реальном времени?</span><span class="sxs-lookup"><span data-stu-id="c7dc7-162">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="c7dc7-163">Если ваша сеть не была правильно оценена или вы знаете, что она не поддерживает носители в реальном времени, отключите функцию демонстрации видео и экрана, чтобы снизить влияние на работу сети и плохое взаимодействие с другими участниками команды.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-163">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Значок, представляющий следующие шаги](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="c7dc7-165">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="c7dc7-165">Next Steps</span></span>         |<span data-ttu-id="c7dc7-166">Качество сети неизвестно: Проведите оценку готовности сети, чтобы определить, готова ли ваша сеть к работе с мультимедиа в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-166">Network Quality Unknown: Perform a Network Readiness Assessment to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="c7dc7-167">Качество сети плохое: выполните действия по устранению неполадок сети, чтобы обеспечить правильную среду для высококачественного мультимедиа в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-167">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="c7dc7-168">Удовлетворительная сеть: Убедитесь, что все IP-адреса и порты правильно доступны.</span><span class="sxs-lookup"><span data-stu-id="c7dc7-168">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="c7dc7-169">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c7dc7-169">Related Topics</span></span>

[<span data-ttu-id="c7dc7-170">Видео: планирование сети</span><span class="sxs-lookup"><span data-stu-id="c7dc7-170">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
