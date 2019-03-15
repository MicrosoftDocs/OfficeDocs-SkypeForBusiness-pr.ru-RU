---
title: Подготовка сети организации к использованию Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: Сведения о подготовке сети Microsoft Teams и управлении ею. Здесь приведены требования к сети и пропускной способности, а также дополнительные рекомендации.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640732"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="43fa9-104">Подготовка сети организации к использованию Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43fa9-104">Prepare your organization's network for Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="43fa9-105">Просмотрите следующие сеанса, чтобы узнать, как группы использует сети и лучше всего планированию для оптимизации сетевого подключения: [Планирование сети групп](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="43fa9-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="43fa9-106">Команды объединяет трех видов трафика:</span><span class="sxs-lookup"><span data-stu-id="43fa9-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="43fa9-107">Данные трафика между средой Office 365 online и клиентских групп (сигналы, сведения о присутствии, чата, отправка файла и загрузка, синхронизация OneNote).</span><span class="sxs-lookup"><span data-stu-id="43fa9-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="43fa9-108">Трафик связи в режиме реального времени Peer-to-peer (аудио, видео, рабочего стола общего доступа).</span><span class="sxs-lookup"><span data-stu-id="43fa9-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="43fa9-109">Трафик в режиме реального времени конференц-связи (аудио, видео, рабочего стола общего доступа).</span><span class="sxs-lookup"><span data-stu-id="43fa9-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="43fa9-110">Это влияет на сети на двух уровнях: трафик будет поток между клиентами группами Майкрософт непосредственно для сценариев peer-to-peer, и трафик будет поток между клиентами группами Майкрософт и средой Office 365 к собранию сценариев.</span><span class="sxs-lookup"><span data-stu-id="43fa9-110">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="43fa9-111">Чтобы обеспечить оптимальную трафик, трафик необходимо разрешить располагаться и между сегменты внутренней сети (например, между сайтами по глобальной сети), а также как между сетевыми узлами и Office 365.</span><span class="sxs-lookup"><span data-stu-id="43fa9-111">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="43fa9-112">Не открывать порты или активно блокировка определенных портов приведет к снижению производительности взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="43fa9-112">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="43fa9-113">Собрания поддерживаются в iOS и Android мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="43fa9-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="43fa9-114">Для получения оптимального взаимодействия с мультимедиа режиме реального времени в рамках группами Майкрософт, сети должны соответствовать требования к сети для Office 365.</span><span class="sxs-lookup"><span data-stu-id="43fa9-114">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="43fa9-115">Дополнительные сведения см в [качестве мультимедиа и производительность подключения к сети для Скайп для бизнеса в Интернет](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="43fa9-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="43fa9-116">Для двух определение сегментов сети (клиент для пограничного сервера Microsoft) и граница клиента для пограничного сервера Microsoft необходимо учитывать следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="43fa9-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="43fa9-117">Значение</span><span class="sxs-lookup"><span data-stu-id="43fa9-117">Value</span></span>  |<span data-ttu-id="43fa9-118">Клиент для пограничного сервера Microsoft</span><span class="sxs-lookup"><span data-stu-id="43fa9-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="43fa9-119">Граница клиента для пограничного сервера Microsoft</span><span class="sxs-lookup"><span data-stu-id="43fa9-119">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="43fa9-120">**Задержка (одним из способов)**\*</span><span class="sxs-lookup"><span data-stu-id="43fa9-120">**Latency (one way)** \*</span></span>  |<span data-ttu-id="43fa9-121">< 50 мс</span><span class="sxs-lookup"><span data-stu-id="43fa9-121">< 50ms</span></span>          |<span data-ttu-id="43fa9-122">< 30ms</span><span class="sxs-lookup"><span data-stu-id="43fa9-122">< 30ms</span></span>         |
|<span data-ttu-id="43fa9-123">**Задержка (круговой путь или время приема-передачи)**\*</span><span class="sxs-lookup"><span data-stu-id="43fa9-123">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="43fa9-124">< 100 мс</span><span class="sxs-lookup"><span data-stu-id="43fa9-124">< 100ms</span></span>   |<span data-ttu-id="43fa9-125">< 60 мс</span><span class="sxs-lookup"><span data-stu-id="43fa9-125">< 60ms</span></span> |
|<span data-ttu-id="43fa9-126">**Повторы пакетов потери пакетов**</span><span class="sxs-lookup"><span data-stu-id="43fa9-126">**Burst packet loss**</span></span>    |<span data-ttu-id="43fa9-127">% <10 любой период 200 мс</span><span class="sxs-lookup"><span data-stu-id="43fa9-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="43fa9-128">% <1 любой период 200 мс</span><span class="sxs-lookup"><span data-stu-id="43fa9-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="43fa9-129">**Потеря пакетов**</span><span class="sxs-lookup"><span data-stu-id="43fa9-129">**Packet loss**</span></span>     |<span data-ttu-id="43fa9-130">% <1 во время любого сумм, равных 15 интервал</span><span class="sxs-lookup"><span data-stu-id="43fa9-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="43fa9-131"><0.1% во время любого сумм, равных 15 интервал</span><span class="sxs-lookup"><span data-stu-id="43fa9-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="43fa9-132">**Дрожание между поступления пакетов**</span><span class="sxs-lookup"><span data-stu-id="43fa9-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="43fa9-133"><30ms во время любого сумм, равных 15 интервал</span><span class="sxs-lookup"><span data-stu-id="43fa9-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="43fa9-134"><15ms во время любого сумм, равных 15 интервал</span><span class="sxs-lookup"><span data-stu-id="43fa9-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="43fa9-135">**Повторный пакет**</span><span class="sxs-lookup"><span data-stu-id="43fa9-135">**Packet reorder**</span></span>    |<span data-ttu-id="43fa9-136">пакеты <0.05% ожидания заказа</span><span class="sxs-lookup"><span data-stu-id="43fa9-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="43fa9-137">пакеты <0.01% ожидания заказа</span><span class="sxs-lookup"><span data-stu-id="43fa9-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="43fa9-138">\*Метрики целевых значений задержки предполагается сайта компании или сайтов и их края Microsoft на одном континент.</span><span class="sxs-lookup"><span data-stu-id="43fa9-138">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="43fa9-139">Подключение к сайту вашей компании в пограничной сети Microsoft включает в себя первый прыжка доступ к сети, который может быть WiFi или другой беспроводной технологии.</span><span class="sxs-lookup"><span data-stu-id="43fa9-139">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="43fa9-140">Целевые показатели производительности сети предполагается надлежащему пропускной способности и/или [Планирование качества обслуживания](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="43fa9-140">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="43fa9-141">Другими словами требования относятся непосредственно к группам трафика мультимедиа в режиме реального времени при сетевого подключения при пиковой нагрузке.</span><span class="sxs-lookup"><span data-stu-id="43fa9-141">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="43fa9-142">Чтобы протестировать оба сегментов сети, можно использовать [Средство оценки производительности сети](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="43fa9-142">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="43fa9-143">Это средство можно развернуть на обоих клиентских ПК, непосредственно и на ПК, подключенных к пограничной сети клиента.</span><span class="sxs-lookup"><span data-stu-id="43fa9-143">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="43fa9-144">Средство включает в себя документация, но более подробные документации решения об использовании средства можно найти здесь: [Оценки готовности сети](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="43fa9-144">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="43fa9-145">Выполнив оценки готовности к сети, можно проверить готовность к сети для запуска приложения в режиме реального времени мультимедиа, такие как группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="43fa9-145">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="43fa9-146">Это же оценки готовности сети, рекомендуется использовать для запуска для клиентов, которым нужны для успешного развертывания Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="43fa9-146">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="43fa9-147">Требования к пропускной способности</span><span class="sxs-lookup"><span data-stu-id="43fa9-147">Bandwidth requirements</span></span>

<span data-ttu-id="43fa9-148">Расчет пропускной способности для групп Майкрософт сложны и помогающее это, был создан калькулятор.</span><span class="sxs-lookup"><span data-stu-id="43fa9-148">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="43fa9-149">Для доступа к калькулятора, перейдите к [Планировщик работы сети](https://aka.ms/bwcalc/) в MyAdvisor.</span><span class="sxs-lookup"><span data-stu-id="43fa9-149">To access the calculator, go to [Network Planner](https://aka.ms/bwcalc/)  in MyAdvisor.</span></span>

> [!NOTE]
> <span data-ttu-id="43fa9-150">Команды обработки пропускной способности позволяет повысить Скайп для бизнеса в Интернет: для высокое качество вызов или приглашения качества (с аудио-, видео и общий доступ к), группами требует только 1.2 Мбит/с.</span><span class="sxs-lookup"><span data-stu-id="43fa9-150">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="43fa9-151">Также можно масштабировать до дальнейшую super высокое качество при наличии достаточную пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="43fa9-151">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="43fa9-152">Когда запрос группы обнаруживает условие низкой пропускной способности сети, групп можно быстро перенастроить использование пропускной способности для адаптации к пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="43fa9-152">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="43fa9-153">Дополнительные сетевые параметры</span><span class="sxs-lookup"><span data-stu-id="43fa9-153">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="43fa9-154">Разрешение внешних имен</span><span class="sxs-lookup"><span data-stu-id="43fa9-154">External Name Resolution</span></span>

<span data-ttu-id="43fa9-155">Убедитесь, что все клиентские компьютеры под управлением группы клиента можно устранить внешних DNS-запросов для обнаружения службы, предоставляемые Office 365 и что брандмауэров не препятствуют доступа.</span><span class="sxs-lookup"><span data-stu-id="43fa9-155">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="43fa9-156">Сведения о настройке порты брандмауэра перейдите к [Office 365 URL-адреса и диапазоны IP-адресов](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="43fa9-156">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="43fa9-157">Размер пула NAT</span><span class="sxs-lookup"><span data-stu-id="43fa9-157">NAT Pool Size</span></span>

<span data-ttu-id="43fa9-158">Когда несколько пользователей/устройств доступа к Office 365 с помощью преобразования сетевых адресов (NAT) или перевода адрес порта (PAT), необходимо убедитесь, что устройства, скрыт за каждого открыто маршрутизируемыми IP-адреса превышает поддерживаемые номер.</span><span class="sxs-lookup"><span data-stu-id="43fa9-158">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="43fa9-159">Чтобы снизить риск, убедитесь, достаточное количество общедоступный IP-адресов назначенные пулы преобразования сетевых адресов для предотвращения нехватка порт.</span><span class="sxs-lookup"><span data-stu-id="43fa9-159">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="43fa9-160">Нехватка порт будет отображено внутренних конечных пользователей и устройств сети проблемы при подключении к службам Office 365.</span><span class="sxs-lookup"><span data-stu-id="43fa9-160">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="43fa9-161">Для получения дополнительных сведений см [NAT с помощью Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="43fa9-161">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="43fa9-162">**Обнаружение вторжений и предотвращения руководство**</span><span class="sxs-lookup"><span data-stu-id="43fa9-162">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="43fa9-163">Если в среде существует обнаружение вторжений и/или системы защиты (Идентификаторы/IP-адреса) развертываются для дополнительный уровень безопасности для исходящих подключений, убедитесь, что любые трафика с конечный URL-адреса Office 365 является whitelisted.</span><span class="sxs-lookup"><span data-stu-id="43fa9-163">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="43fa9-164">Определения состояния сети</span><span class="sxs-lookup"><span data-stu-id="43fa9-164">Network health determination</span></span>
-----------------

<span data-ttu-id="43fa9-165">При планировании реализации группами Майкрософт в сети, необходимо убедиться, у вас есть необходимые пропускной способности, у вас есть доступ для всех IP-адресов, открывается, порты и собраний требований к производительности для мультимедиа в режиме реального времени .</span><span class="sxs-lookup"><span data-stu-id="43fa9-165">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="43fa9-166">Если вы знаете, что будет не отвечают этим условиям, конечных пользователей не может получить обеспечения оптимального взаимодействия из групп из-за качество во время звонков и собрания.</span><span class="sxs-lookup"><span data-stu-id="43fa9-166">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="43fa9-167">Должен ли на не отвечают этим условиям, это время необходимо рассмотреть Приостановка проект, чтобы убедиться, что перед продолжением соответствуют требованиям.</span><span class="sxs-lookup"><span data-stu-id="43fa9-167">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="43fa9-169">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="43fa9-169">Decision Point</span></span>         |<span data-ttu-id="43fa9-170">Оценили ли вы возможности вашей сети для поддержки мультимедиа в режиме реального времени?</span><span class="sxs-lookup"><span data-stu-id="43fa9-170">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="43fa9-171">Если вашей сети не был правильно оценки, или вы знаете, что не могут использовать мультимедиа в режиме реального времени, будет отключена видео и совместного использования возможностей для уменьшения воздействия на сеть и низкого уровня каждый раз группами экрана?</span><span class="sxs-lookup"><span data-stu-id="43fa9-171">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Значок дальнейших действий.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="43fa9-173">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="43fa9-173">Next Steps</span></span>         |<span data-ttu-id="43fa9-174">Сеть качества неизвестный: следуйте рекомендациям в статье [Оценки готовности сети](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) для определения, если сеть готова для мультимедиа в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="43fa9-174">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="43fa9-175">Низкое качество сетевого: Выполните действия исправления сеть для обеспечения правильной среды для высокое качество мультимедиа в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="43fa9-175">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="43fa9-176">Удовлетворительно сети: Убедитесь, все IP-адреса и порты должным образом доступны.</span><span class="sxs-lookup"><span data-stu-id="43fa9-176">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="43fa9-177">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="43fa9-177">Related Topics</span></span>

[<span data-ttu-id="43fa9-178">Видео: Планирование сети</span><span class="sxs-lookup"><span data-stu-id="43fa9-178">Video: Network Planning</span></span>](https://aka.ms/teams-networking)