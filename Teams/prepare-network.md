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
ms.openlocfilehash: b6b95da8ee416d4f64d22a8c0622acd417b7bb1d
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742850"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="7ddc8-104">Подготовка сети организации к использованию Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7ddc8-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

> [!Tip]
> <span data-ttu-id="7ddc8-105">Просмотрите следующие сеанса, чтобы узнать, как группы использует сети и лучше всего планированию для оптимизации сетевого подключения: [Планирование сети групп](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="7ddc8-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="7ddc8-106">Teams сочетает в себе три формы трафика:</span><span class="sxs-lookup"><span data-stu-id="7ddc8-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="7ddc8-107">Трафик данных между интернет-средой Office 365 и клиентом Teams (сигналы, присутствие, чат, отправка и скачивание файлов, синхронизация с OneNote).</span><span class="sxs-lookup"><span data-stu-id="7ddc8-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="7ddc8-108">Трафик однорангового взаимодействия в реальном времени (звук, видео, демонстрация рабочего стола).</span><span class="sxs-lookup"><span data-stu-id="7ddc8-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="7ddc8-109">Трафик конференц-связи в реальном времени (звук, видео, демонстрация рабочего стола).</span><span class="sxs-lookup"><span data-stu-id="7ddc8-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="7ddc8-110">Это затрагивает сеть на двух уровнях: одноранговый трафик протекает напрямую между клиентами Microsoft Teams, а во время собраний трафик протекает между клиентами Microsoft Teams и средой Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-110">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="7ddc8-111">Чтобы оптимизировать поток трафика, следует обеспечить его протекание как между внутренними сегментами сети (например, между сайтами через глобальную сеть), так и между узлами сети и Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-111">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="7ddc8-112">Закрытие или блокировка определенных портов приведет к ухудшению работы.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-112">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="7ddc8-113">Собрания поддерживаются в iOS и Android мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="7ddc8-114">Чтобы обеспечить в Microsoft Teams оптимальную работу с мультимедиа в реальном времени, нужно обеспечить соответствие сетей требованиям для Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-114">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the networking requirements for Office 365.</span></span> <span data-ttu-id="7ddc8-115">Дополнительные сведения: [Качество медиаданных и производительность сетевого подключения в Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="7ddc8-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="7ddc8-116">Для двух определение сегментов сети (клиент для пограничного сервера Microsoft) и граница клиента для пограничного сервера Microsoft необходимо учитывать следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="7ddc8-117">Значение</span><span class="sxs-lookup"><span data-stu-id="7ddc8-117">Value</span></span>  |<span data-ttu-id="7ddc8-118">Между программой-клиентом и периметром Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7ddc8-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="7ddc8-119">Между периметром заказчика и периметром Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7ddc8-119">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7ddc8-120">**Задержка (в одну сторону)**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-120">**Latency (one way)**</span></span>     |<span data-ttu-id="7ddc8-121">< 50 мс</span><span class="sxs-lookup"><span data-stu-id="7ddc8-121">< 50ms</span></span>          |<span data-ttu-id="7ddc8-122">< 30 мс</span><span class="sxs-lookup"><span data-stu-id="7ddc8-122">< 30ms</span></span>          |
|<span data-ttu-id="7ddc8-123">**Задержка (время кругового пути)**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-123">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="7ddc8-124">< 100 мс</span><span class="sxs-lookup"><span data-stu-id="7ddc8-124">< 100ms</span></span>         |<span data-ttu-id="7ddc8-125">< 60 мс</span><span class="sxs-lookup"><span data-stu-id="7ddc8-125">< 60ms</span></span>         |
|<span data-ttu-id="7ddc8-126">**Серийная потеря пакетов**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-126">**Burst packet loss**</span></span>    |<span data-ttu-id="7ddc8-127"><10 % за любой интервал в 200 мс</span><span class="sxs-lookup"><span data-stu-id="7ddc8-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="7ddc8-128"><1% за любой интервал в 200 мс</span><span class="sxs-lookup"><span data-stu-id="7ddc8-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="7ddc8-129">**Потеря пакетов**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-129">**Packet loss**</span></span>     |<span data-ttu-id="7ddc8-130"><1 % за любой интервал в 15 с</span><span class="sxs-lookup"><span data-stu-id="7ddc8-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="7ddc8-131"><0,1% за любой интервал в 15 с</span><span class="sxs-lookup"><span data-stu-id="7ddc8-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="7ddc8-132">**Дрожание между получением пакетов**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="7ddc8-133"><30 мс за любой интервал в 15 с</span><span class="sxs-lookup"><span data-stu-id="7ddc8-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="7ddc8-134"><15 мс за любой интервал в 15 с</span><span class="sxs-lookup"><span data-stu-id="7ddc8-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="7ddc8-135">**Изменение порядка пакетов**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-135">**Packet reorder**</span></span>    |<span data-ttu-id="7ddc8-136"><0,05 % пакетов с нарушением порядка</span><span class="sxs-lookup"><span data-stu-id="7ddc8-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="7ddc8-137"><0,01% пакетов с нарушением порядка</span><span class="sxs-lookup"><span data-stu-id="7ddc8-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="7ddc8-138">Для тестирования обоих сегментов сети воспользуйтесь инструментом [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="7ddc8-138">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="7ddc8-139">Вы можете развернуть его как непосредственно на клиентском компьютере, так и на компьютере, подключенном к периметру сети клиента.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-139">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="7ddc8-140">Это средство поставляется с ограниченной документацией, более подробные сведения о его использовании см. в статье: [Оценка готовности сети](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="7ddc8-140">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="7ddc8-141">Запустив эту оценку, вы можете проверить готовность своей сети к выполнению мультимедийных приложений реального времени, таких как Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-141">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="7ddc8-142">Эту же оценку готовности сети рекомендуется выполнять заказчикам, собирающимся развернуть Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-142">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="7ddc8-143">Требования к пропускной способности</span><span class="sxs-lookup"><span data-stu-id="7ddc8-143">Bandwidth requirements</span></span>
----------

<span data-ttu-id="7ddc8-144">Расчеты пропускной способности для Microsoft Teams довольно сложны, поэтому был создан соответствующий калькулятор.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-144">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="7ddc8-145">Для доступа к калькулятору перейдите в раздел [Network Planner](https://aka.ms/bwcalc/) (планировщик сети) в MyAdvisor.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-145">To access the calculator, go to [Network Planner in MyAdvisor](https://aka.ms/bwcalc/).</span></span>

> [!NOTE]
> <span data-ttu-id="7ddc8-146">Команды обработки пропускной способности позволяет повысить Скайп для бизнеса в Интернет: для высокое качество вызов или приглашения качества (с аудио-, видео и общий доступ к), группами требует только 1.2 Мбит/с.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-146">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="7ddc8-147">Также можно масштабировать до дальнейшую super высокое качество при наличии достаточную пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-147">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="7ddc8-148">Когда запрос группы обнаруживает условие низкой пропускной способности сети, групп можно быстро перенастроить использование пропускной способности для адаптации к пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-148">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="7ddc8-149">Дополнительные рекомендации относительно сети</span><span class="sxs-lookup"><span data-stu-id="7ddc8-149">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="7ddc8-150">**Внешнее разрешение имен**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-150">**External Name Resolution**</span></span>

<span data-ttu-id="7ddc8-151">Все клиентские компьютеры, где работает клиент Teams, должны быть способны разрешать внешние запросы DNS для обнаружения служб, предоставляемых Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-151">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="7ddc8-152">**Размер пула NAT**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-152">**NAT Pool Size**</span></span>

<span data-ttu-id="7ddc8-153">Когда множество пользователей или устройств обращаются к Office 365 с помощью преобразования сетевых адресов (NAT) или преобразования адресов портов (PAT), вам нужно следить за тем, чтобы число устройств, скрытых за каждым из общедоступных маршрутизируемых IP-адресов, не превышало поддерживаемого значения.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-153">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="7ddc8-154">Чтобы снизить риск, назначьте пулам NAT подходящие общедоступные IP-адреса для предотвращения нехватки портов.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-154">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="7ddc8-155">Нехватка портов приведет к тому, что внутренние пользователи и устройства столкнутся с проблемами при подключении к службам Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-155">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="7ddc8-156">Дополнительные сведения: [Поддержка NAT в Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="7ddc8-156">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="7ddc8-157">**Указания по обнаружению атак и предотвращению вторжений**</span><span class="sxs-lookup"><span data-stu-id="7ddc8-157">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="7ddc8-158">Если в вашей среде для дополнительной защиты исходящих подключений развернута система обнаружения атак и (или) предотвращения вторжений (IDS/IPS), весь трафик, передаваемый на URL-адреса Office 365, должен быть включен в список разрешений.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-158">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="7ddc8-159">Определение работоспособности сети</span><span class="sxs-lookup"><span data-stu-id="7ddc8-159">Network health determination</span></span>
-----------------

<span data-ttu-id="7ddc8-160">При планировании внедрения Microsoft Teams в сети вам нужно обеспечить требуемую пропускную способность и доступ ко всем необходимым IP-адресам, открыть нужные порты и выполнить требования к производительности для передачи медиаданных в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-160">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="7ddc8-161">При невыполнении этих условий работа конечных пользователей с Teams будет неоптимальной из-за низкого качества связи во время звонков и собраний.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-161">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="7ddc8-162">Если данные условия не выполняются, рекомендуется приостановить проект и обеспечить их выполнение.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-162">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="7ddc8-164">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="7ddc8-164">Decision Point</span></span>         |<span data-ttu-id="7ddc8-165">Оценили ли вы возможности своей сети для поддержки мультимедиа реального времени?</span><span class="sxs-lookup"><span data-stu-id="7ddc8-165">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="7ddc8-166">Если ваша сеть не была оценена должным образом или не поддерживает мультимедиа реального времени, отключите ли вы функции видеосвязи и демонстрации экрана для улучшения работы сети и взаимодействия с Teams?</span><span class="sxs-lookup"><span data-stu-id="7ddc8-166">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Значок дальнейших действий.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="7ddc8-168">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7ddc8-168">Next Steps</span></span>         |<span data-ttu-id="7ddc8-169">При неизвестном качестве сети: следуйте указаниям руководства [Оценка готовности сети](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness), чтобы определить готовность сети к работе с мультимедиа в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-169">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="7ddc8-170">При низком качестве сети: предпримите меры по исправлению сети, чтобы создать подходящую среду для высококачественного мультимедиа реального времени.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-170">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="7ddc8-171">При удовлетворительном качестве сети: обеспечьте доступность всех IP-адресов и портов.</span><span class="sxs-lookup"><span data-stu-id="7ddc8-171">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="7ddc8-172">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7ddc8-172">Related Topics</span></span>

[<span data-ttu-id="7ddc8-173">Видео: Планирование сети</span><span class="sxs-lookup"><span data-stu-id="7ddc8-173">Video: Network Planning</span></span>](https://aka.ms/teams-networking)