---
title: Подготовка сети организации к использованию Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: Сведения о подготовке сети Microsoft Teams и управлении ею. Здесь приведены требования к сети и пропускной способности, а также дополнительные рекомендации.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3af825b28f1c6c4abc202bb343c80b50176de16e
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205677"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="7fb08-104">Подготовка сети организации к использованию Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7fb08-104">Prepare your organization's network for Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="7fb08-105">Просмотрите следующие сеанса, чтобы узнать, как группы использует сети и лучше всего планированию для оптимизации сетевого подключения: [Планирование сети групп](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="7fb08-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="7fb08-106">Teams сочетает в себе три формы трафика:</span><span class="sxs-lookup"><span data-stu-id="7fb08-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="7fb08-107">Трафик данных между интернет-средой Office 365 и клиентом Teams (сигналы, присутствие, чат, отправка и скачивание файлов, синхронизация с OneNote).</span><span class="sxs-lookup"><span data-stu-id="7fb08-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="7fb08-108">Трафик однорангового взаимодействия в реальном времени (звук, видео, демонстрация рабочего стола).</span><span class="sxs-lookup"><span data-stu-id="7fb08-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="7fb08-109">Трафик конференц-связи в реальном времени (звук, видео, демонстрация рабочего стола).</span><span class="sxs-lookup"><span data-stu-id="7fb08-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="7fb08-110">Это затрагивает сеть на двух уровнях: одноранговый трафик протекает напрямую между клиентами Microsoft Teams, а во время собраний трафик протекает между клиентами Microsoft Teams и средой Office 365.</span><span class="sxs-lookup"><span data-stu-id="7fb08-110">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="7fb08-111">Чтобы оптимизировать поток трафика, следует обеспечить его протекание как между внутренними сегментами сети (например, между сайтами через глобальную сеть), так и между узлами сети и Office 365.</span><span class="sxs-lookup"><span data-stu-id="7fb08-111">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="7fb08-112">Закрытие или блокировка определенных портов приведет к ухудшению работы.</span><span class="sxs-lookup"><span data-stu-id="7fb08-112">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="7fb08-113">Собрания поддерживаются в iOS и Android мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="7fb08-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="7fb08-114">Чтобы обеспечить в Microsoft Teams оптимальную работу с мультимедиа в реальном времени, нужно обеспечить соответствие сетей требованиям для Office 365.</span><span class="sxs-lookup"><span data-stu-id="7fb08-114">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the networking requirements for Office 365.</span></span> <span data-ttu-id="7fb08-115">Дополнительные сведения: [Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="7fb08-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="7fb08-116">Для двух определение сегментов сети (клиент для пограничного сервера Microsoft) и граница клиента для пограничного сервера Microsoft необходимо учитывать следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="7fb08-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="7fb08-117">Значение</span><span class="sxs-lookup"><span data-stu-id="7fb08-117">Value</span></span>  |<span data-ttu-id="7fb08-118">Между программой-клиентом и периметром Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7fb08-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="7fb08-119">Между периметром заказчика и периметром Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7fb08-119">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="7fb08-120">**Задержка (в одну сторону)** \*</span><span class="sxs-lookup"><span data-stu-id="7fb08-120">**Latency (one way)** \*</span></span>  |<span data-ttu-id="7fb08-121">< 50 мс</span><span class="sxs-lookup"><span data-stu-id="7fb08-121">< 50ms</span></span>          |<span data-ttu-id="7fb08-122">< 30 мс</span><span class="sxs-lookup"><span data-stu-id="7fb08-122">< 30ms</span></span>         |
|<span data-ttu-id="7fb08-123">**Задержка (время кругового пути)** \*</span><span class="sxs-lookup"><span data-stu-id="7fb08-123">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="7fb08-124">< 100 мс</span><span class="sxs-lookup"><span data-stu-id="7fb08-124">< 100ms</span></span>   |<span data-ttu-id="7fb08-125">< 60 мс</span><span class="sxs-lookup"><span data-stu-id="7fb08-125">< 60ms</span></span> |
|<span data-ttu-id="7fb08-126">**Серийная потеря пакетов**</span><span class="sxs-lookup"><span data-stu-id="7fb08-126">**Burst packet loss**</span></span>    |<span data-ttu-id="7fb08-127"><10 % за любой интервал в 200 мс</span><span class="sxs-lookup"><span data-stu-id="7fb08-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="7fb08-128"><1% за любой интервал в 200 мс</span><span class="sxs-lookup"><span data-stu-id="7fb08-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="7fb08-129">**Потеря пакетов**</span><span class="sxs-lookup"><span data-stu-id="7fb08-129">**Packet loss**</span></span>     |<span data-ttu-id="7fb08-130"><1 % за любой интервал в 15 с</span><span class="sxs-lookup"><span data-stu-id="7fb08-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="7fb08-131"><0,1% за любой интервал в 15 с</span><span class="sxs-lookup"><span data-stu-id="7fb08-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="7fb08-132">**Дрожание между получением пакетов**</span><span class="sxs-lookup"><span data-stu-id="7fb08-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="7fb08-133"><30 мс за любой интервал в 15 с</span><span class="sxs-lookup"><span data-stu-id="7fb08-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="7fb08-134"><15 мс за любой интервал в 15 с</span><span class="sxs-lookup"><span data-stu-id="7fb08-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="7fb08-135">**Изменение порядка пакетов**</span><span class="sxs-lookup"><span data-stu-id="7fb08-135">**Packet reorder**</span></span>    |<span data-ttu-id="7fb08-136"><0,05 % пакетов с нарушением порядка</span><span class="sxs-lookup"><span data-stu-id="7fb08-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="7fb08-137"><0,01% пакетов с нарушением порядка</span><span class="sxs-lookup"><span data-stu-id="7fb08-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="7fb08-138">\*Метрики целевых значений задержки предполагается сайта компании или сайтов и их края Microsoft на одном континент.</span><span class="sxs-lookup"><span data-stu-id="7fb08-138">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="7fb08-139">Подключение к сайту вашей компании в пограничной сети Microsoft включает в себя первый прыжка доступ к сети, который может быть WiFi или другой беспроводной технологии.</span><span class="sxs-lookup"><span data-stu-id="7fb08-139">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="7fb08-140">Целевые показатели производительности сети предполагается надлежащему пропускной способности и/или [Планирование качества обслуживания](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="7fb08-140">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="7fb08-141">Другими словами требования относятся непосредственно к группам трафика мультимедиа в режиме реального времени при сетевого подключения при пиковой нагрузке.</span><span class="sxs-lookup"><span data-stu-id="7fb08-141">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="7fb08-142">Для тестирования обоих сегментов сети воспользуйтесь инструментом [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="7fb08-142">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="7fb08-143">Вы можете развернуть его как непосредственно на клиентском компьютере, так и на компьютере, подключенном к периметру сети клиента.</span><span class="sxs-lookup"><span data-stu-id="7fb08-143">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="7fb08-144">Это средство поставляется с ограниченной документацией, более подробные сведения о его использовании см. в статье: [Оценка готовности сети](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="7fb08-144">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="7fb08-145">Запустив эту оценку, вы можете проверить готовность своей сети к выполнению мультимедийных приложений реального времени, таких как Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7fb08-145">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="7fb08-146">Эту же оценку готовности сети рекомендуется выполнять заказчикам, собирающимся развернуть Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7fb08-146">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="7fb08-147">Требования к пропускной способности</span><span class="sxs-lookup"><span data-stu-id="7fb08-147">Bandwidth requirements</span></span>

<span data-ttu-id="7fb08-148">Расчеты пропускной способности для Microsoft Teams довольно сложны, поэтому был создан соответствующий калькулятор.</span><span class="sxs-lookup"><span data-stu-id="7fb08-148">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="7fb08-149">Для доступа к калькулятора, перейдите к [Планировщик работы сети](https://aka.ms/bwcalc/) в MyAdvisor.</span><span class="sxs-lookup"><span data-stu-id="7fb08-149">To access the calculator, go to [Network Planner](https://aka.ms/bwcalc/)  in MyAdvisor.</span></span>

> [!NOTE]
> <span data-ttu-id="7fb08-150">Команды обработки пропускной способности позволяет повысить Скайп для бизнеса в Интернет: для высокое качество вызов или приглашения качества (с аудио-, видео и общий доступ к), группами требует только 1.2 Мбит/с.</span><span class="sxs-lookup"><span data-stu-id="7fb08-150">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="7fb08-151">Также можно масштабировать до дальнейшую super высокое качество при наличии достаточную пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="7fb08-151">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="7fb08-152">Когда запрос группы обнаруживает условие низкой пропускной способности сети, групп можно быстро перенастроить использование пропускной способности для адаптации к пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="7fb08-152">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="7fb08-153">Дополнительные рекомендации относительно сети</span><span class="sxs-lookup"><span data-stu-id="7fb08-153">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="7fb08-154">Внешнее разрешение имен</span><span class="sxs-lookup"><span data-stu-id="7fb08-154">External Name Resolution</span></span>

<span data-ttu-id="7fb08-155">Убедитесь, что все клиентские компьютеры под управлением группы клиента можно устранить внешних DNS-запросов для обнаружения службы, предоставляемые Office 365 и что брандмауэров не препятствуют доступа.</span><span class="sxs-lookup"><span data-stu-id="7fb08-155">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="7fb08-156">Сведения о настройке порты брандмауэра перейдите к [Office 365 URL-адреса и диапазоны IP-адресов](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="7fb08-156">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="7fb08-157">Размер пула NAT</span><span class="sxs-lookup"><span data-stu-id="7fb08-157">NAT Pool Size</span></span>

<span data-ttu-id="7fb08-158">Когда множество пользователей или устройств обращаются к Office 365 с помощью преобразования сетевых адресов (NAT) или преобразования адресов портов (PAT), вам нужно следить за тем, чтобы число устройств, скрытых за каждым из общедоступных маршрутизируемых IP-адресов, не превышало поддерживаемого значения.</span><span class="sxs-lookup"><span data-stu-id="7fb08-158">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="7fb08-159">Чтобы снизить риск, назначьте пулам NAT подходящие общедоступные IP-адреса для предотвращения нехватки портов.</span><span class="sxs-lookup"><span data-stu-id="7fb08-159">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="7fb08-160">Нехватка портов приведет к тому, что внутренние пользователи и устройства столкнутся с проблемами при подключении к службам Office 365.</span><span class="sxs-lookup"><span data-stu-id="7fb08-160">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="7fb08-161">Дополнительные сведения: [Поддержка NAT в Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="7fb08-161">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="7fb08-162">**Указания по обнаружению атак и предотвращению вторжений**</span><span class="sxs-lookup"><span data-stu-id="7fb08-162">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="7fb08-163">Если в вашей среде для дополнительной защиты исходящих подключений развернута система обнаружения атак и (или) предотвращения вторжений (IDS/IPS), весь трафик, передаваемый на URL-адреса Office 365, должен быть включен в список разрешений.</span><span class="sxs-lookup"><span data-stu-id="7fb08-163">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="7fb08-164">Определение работоспособности сети</span><span class="sxs-lookup"><span data-stu-id="7fb08-164">Network health determination</span></span>
-----------------

<span data-ttu-id="7fb08-165">При планировании внедрения Microsoft Teams в сети вам нужно обеспечить требуемую пропускную способность и доступ ко всем необходимым IP-адресам, открыть нужные порты и выполнить требования к производительности для передачи медиаданных в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="7fb08-165">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="7fb08-166">При невыполнении этих условий работа конечных пользователей с Teams будет неоптимальной из-за низкого качества связи во время звонков и собраний.</span><span class="sxs-lookup"><span data-stu-id="7fb08-166">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="7fb08-167">Если данные условия не выполняются, рекомендуется приостановить проект и обеспечить их выполнение.</span><span class="sxs-lookup"><span data-stu-id="7fb08-167">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="7fb08-169">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="7fb08-169">Decision Point</span></span>         |<span data-ttu-id="7fb08-170">Оценили ли вы возможности своей сети для поддержки мультимедиа реального времени?</span><span class="sxs-lookup"><span data-stu-id="7fb08-170">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="7fb08-171">Если ваша сеть не была оценена должным образом или не поддерживает мультимедиа реального времени, отключите ли вы функции видеосвязи и демонстрации экрана для улучшения работы сети и взаимодействия с Teams?</span><span class="sxs-lookup"><span data-stu-id="7fb08-171">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Значок дальнейших действий.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="7fb08-173">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7fb08-173">Next Steps</span></span>         |<span data-ttu-id="7fb08-174">При неизвестном качестве сети: следуйте указаниям руководства [Оценка готовности сети](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness), чтобы определить готовность сети к работе с мультимедиа в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="7fb08-174">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="7fb08-175">При низком качестве сети: предпримите меры по исправлению сети, чтобы создать подходящую среду для высококачественного мультимедиа реального времени.</span><span class="sxs-lookup"><span data-stu-id="7fb08-175">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="7fb08-176">При удовлетворительном качестве сети: обеспечьте доступность всех IP-адресов и портов.</span><span class="sxs-lookup"><span data-stu-id="7fb08-176">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="7fb08-177">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7fb08-177">Related Topics</span></span>

[<span data-ttu-id="7fb08-178">Видео: Планирование сети</span><span class="sxs-lookup"><span data-stu-id="7fb08-178">Video: Network Planning</span></span>](https://aka.ms/teams-networking)