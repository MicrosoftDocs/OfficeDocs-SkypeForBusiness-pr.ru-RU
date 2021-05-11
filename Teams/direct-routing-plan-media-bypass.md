---
title: Планирование обхода сервера-посредника с прямой маршрутизацией
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, как спланировать обход мультимедиа с помощью телефонная система прямой маршрутии, которая позволяет сократить путь к трафику мультимедиа и повысить производительность.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9b6624a81994c1d6797ed996fbcc233fe75f8907
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308358"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="e01f0-103">Планирование обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="e01f0-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="e01f0-104">Обход мультимедиа с прямой маршрутией</span><span class="sxs-lookup"><span data-stu-id="e01f0-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="e01f0-105">Обход мультимедиа позволяет сократить путь к трафику мультимедиа и уменьшить количество переходов в пути для улучшения производительности.</span><span class="sxs-lookup"><span data-stu-id="e01f0-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="e01f0-106">При обходе мультимедиа мультимедиа между контроллером границы сеанса (SBC) и клиентом хранятся мультимедиа, а не отправляются через Телефон (Майкрософт) системы.</span><span class="sxs-lookup"><span data-stu-id="e01f0-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="e01f0-107">Чтобы настроить обход мультимедиа, SBC и клиент должны быть в одном расположении или сети.</span><span class="sxs-lookup"><span data-stu-id="e01f0-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="e01f0-108">Вы можете управлять обходом мультимедиа для каждого SBC с помощью команды **Set-CSOnlinePSTNGateway** с параметром **-MediaBypass,** для параметра true или false.</span><span class="sxs-lookup"><span data-stu-id="e01f0-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="e01f0-109">Если включить обход мультимедиа, это не означает, что весь трафик мультимедиа будет оставаться в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="e01f0-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="e01f0-110">В этой статье описан поток зова в разных сценариях.</span><span class="sxs-lookup"><span data-stu-id="e01f0-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="e01f0-111">На схемах ниже показано, чем отличается поток вызовов как с обходом мультимедиа, так и без него.</span><span class="sxs-lookup"><span data-stu-id="e01f0-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="e01f0-112">Без обхода мультимедиа, когда клиент совершает или принимает звонок, сигнальный и поток мультимедиа между SBC, системой Телефон (Майкрософт) и клиентом Teams, как показано на схеме ниже:</span><span class="sxs-lookup"><span data-stu-id="e01f0-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e01f0-113">![Сигнальный поток и поток мультимедиа без обхода мультимедиа](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="e01f0-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="e01f0-114">Но предположим, что пользователь находится в том же здании или сети, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="e01f0-115">Например, предположим, что пользователь, который находится в здании в Области, звонит пользователю ННР:</span><span class="sxs-lookup"><span data-stu-id="e01f0-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="e01f0-116">**Без обхода мультимедиа** будут поступать через Залив или Dublin (где развернуты центра обработки данных Майкрософт) и обратно в SBC в Сша.</span><span class="sxs-lookup"><span data-stu-id="e01f0-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="e01f0-117">Центр обработки данных в Европе выбран, так как он находится в Европе, а корпорация Майкрософт использует центр обработки данных, ближайший к SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="e01f0-118">Хотя этот подход не влияет на качество зова из-за оптимизации потока трафика в сетях Майкрософт в большинстве географических данных, трафик имеет ненужный цикл.</span><span class="sxs-lookup"><span data-stu-id="e01f0-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="e01f0-119">**При обходе** мультимедиа хранятся непосредственно между Teams и SBC, как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="e01f0-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e01f0-120">![Сигнальный поток и поток мультимедиа с обходом мультимедиа](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="e01f0-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="e01f0-121">Обход мультимедиа использует протоколы под названием "Интерактивные подключения (ICE) в клиенте Teams и ICE lite на SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="e01f0-122">Эти протоколы позволяют прямой маршрутике использовать самый прямой маршрут мультимедиа для оптимального качества.</span><span class="sxs-lookup"><span data-stu-id="e01f0-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="e01f0-123">ICE и ICE Lite являются стандартами WebRTC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="e01f0-124">Подробные сведения об этих протоколах см. в описании протокола RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="e01f0-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="e01f0-125">Планирование потока вызовов и брандмауэра</span><span class="sxs-lookup"><span data-stu-id="e01f0-125">Call flow and firewall planning</span></span>

<span data-ttu-id="e01f0-126">Планирование потока присоединения к звонкам и брандмауэра зависит от того, имеет ли пользователь прямой доступ к общедоступным IP-адресам SBC и находится ли пользователь внутри или за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="e01f0-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="e01f0-127">Поток зова, если у пользователя есть прямой доступ к общедоступным IP-адресу SBC</span><span class="sxs-lookup"><span data-stu-id="e01f0-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="e01f0-128">Если у пользователя есть прямой доступ к общедоступным IP-адресам SBC, поток зовов будет следующим:</span><span class="sxs-lookup"><span data-stu-id="e01f0-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="e01f0-129">Для обхода мультимедиа Teams клиент должен иметь доступ к общедоступным IP-адресам SBC даже из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="e01f0-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="e01f0-130">Если прямая мультимедиа не требуется, они могут перетекать через ретрансляторы транспорта.</span><span class="sxs-lookup"><span data-stu-id="e01f0-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="e01f0-131">Это рекомендуемое решение, если пользователь находится в том же здании или сети, что и SBC, и удаляет компоненты Microsoft Cloud из пути мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e01f0-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="e01f0-132">Сигнальный сигнал всегда проходит через облако Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e01f0-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="e01f0-133">На следующей схеме показан поток зова, когда включен обход мультимедиа, клиент является внутренним, а клиент может получить доступ к общедоступным IP-адресам SBC (прямой мультимедиа):</span><span class="sxs-lookup"><span data-stu-id="e01f0-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="e01f0-134">Стрелки и числимые значения путей соответствуют Microsoft Teams [звонкам.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="e01f0-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="e01f0-135">Сигнальный трафик SIP всегда проходит по путям 4 и 4' (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="e01f0-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="e01f0-136">Media stays local and takes path 5b.</span><span class="sxs-lookup"><span data-stu-id="e01f0-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e01f0-137">![Отображает поток зовов с включенным обходом мультимедиа, клиент является внутренним](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="e01f0-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="e01f0-138">Поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресам SBC</span><span class="sxs-lookup"><span data-stu-id="e01f0-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="e01f0-139">Ниже описан поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресам SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="e01f0-140">Например, предположим, что пользователь является внешним, а администратор клиента решил не открывать общедоступный IP-адрес SBC для всех пользователей в Интернете, а только в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="e01f0-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="e01f0-141">Внутренние компоненты трафика могут перетекать через Teams транспорта.</span><span class="sxs-lookup"><span data-stu-id="e01f0-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="e01f0-142">Примите во внимание следующее:</span><span class="sxs-lookup"><span data-stu-id="e01f0-142">Consider the following:</span></span>

- <span data-ttu-id="e01f0-143">Teams Используются ретрансляторы транспорта.</span><span class="sxs-lookup"><span data-stu-id="e01f0-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="e01f0-144">Для обхода мультимедиа корпорация Майкрософт использует версию ретрансляторов транспорта, которая требует открытия портов от 50 000 до 59 999 между ретрансляторами транспорта Teams и SBC (в будущем планируется перейти на версию, которая требует портов 3478–3481).</span><span class="sxs-lookup"><span data-stu-id="e01f0-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires 3478-3481 ports).</span></span>


<span data-ttu-id="e01f0-145">На следующей схеме показан поток зова, когда включен обход мультимедиа, клиент является внешним и не может получить доступ к общедоступным IP-адресам контроллера границы сеанса (мультимедиа передаются Teams Transport Relay).</span><span class="sxs-lookup"><span data-stu-id="e01f0-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="e01f0-146">Стрелки и числимые значения путей соответствуют Microsoft Teams [звонкам.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="e01f0-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="e01f0-147">Мультимедиа передается по путям 3, 3', 4 и 4'</span><span class="sxs-lookup"><span data-stu-id="e01f0-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e01f0-148">![Отображает поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресам SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="e01f0-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="e01f0-149">Поток присоединения к звонкам, если пользователь находится за пределами сети и имеет доступ к общедоступным IP-адресам SBC</span><span class="sxs-lookup"><span data-stu-id="e01f0-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="e01f0-150">Такая конфигурация не рекомендуется, так как она не Teams ретрансляторов транспорта.</span><span class="sxs-lookup"><span data-stu-id="e01f0-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="e01f0-151">Вместо этого следует рассмотреть предыдущий сценарий, в котором у пользователя нет доступа к общедоступным IP-адресам SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="e01f0-152">На следующей схеме показан поток зова, когда включен обход мультимедиа, клиент внешний, а клиент может получить доступ к общедоступным IP-адресам SBC (прямого мультимедиа).</span><span class="sxs-lookup"><span data-stu-id="e01f0-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="e01f0-153">Стрелки и числимые значения путей соответствуют статье Microsoft Teams [потокам](./microsoft-teams-online-call-flows.md) зовов.</span><span class="sxs-lookup"><span data-stu-id="e01f0-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="e01f0-154">Сигнальный трафик SIP всегда проходит по путям 3 и 3' (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="e01f0-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="e01f0-155">Потоки мультимедиа, использующие путь 2.</span><span class="sxs-lookup"><span data-stu-id="e01f0-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e01f0-156">![Отображает поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресам SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="e01f0-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="e01f0-157">Использование процессоров мультимедиа и ретрансляторов транспорта</span><span class="sxs-lookup"><span data-stu-id="e01f0-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="e01f0-158">В Microsoft Cloud есть два компонента, которые могут быть в пути к трафику мультимедиа: процессоры мультимедиа и ретрансляторы транспорта.</span><span class="sxs-lookup"><span data-stu-id="e01f0-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="e01f0-159">Процессор мультимедиа — это общедоступный компонент, который обрабатывает мультимедиа в случаях без обхода и обрабатывает мультимедиа для голосовых приложений.</span><span class="sxs-lookup"><span data-stu-id="e01f0-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="e01f0-160">Процессоры мультимедиа всегда находятся в пути для конечных пользователей, но никогда не находятся в пути для обходных звонков.</span><span class="sxs-lookup"><span data-stu-id="e01f0-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="e01f0-161">Процессоры мультимедиа всегда находятся в пути для всех голосовых приложений, таких как "Парк вызовов", "Автоотправление организации" и "Очереди зовов".</span><span class="sxs-lookup"><span data-stu-id="e01f0-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="e01f0-162">Ретранслятор транспорта используется для подключения к ближайшей службе транспорта для отправки трафика в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="e01f0-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="e01f0-163">В зависимости от того, где находится пользователь и как настроена сеть, ретрансляторы транспорта могут оказаться в пути для обходных звонков ( от пользователей или от их маршрутов).</span><span class="sxs-lookup"><span data-stu-id="e01f0-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="e01f0-164">На следующей схеме показаны два потока зова: один с включенным обходом мультимедиа, второй — с отключенным обходом мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e01f0-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="e01f0-165">Схема показывает только трафик, относяющийся к конечным пользователям или направляющийся на него.</span><span class="sxs-lookup"><span data-stu-id="e01f0-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="e01f0-166">Контроллер мультимедиа — это микрослужба в Azure, которая назначает процессоры мультимедиа и создает предложения протокола SDP.</span><span class="sxs-lookup"><span data-stu-id="e01f0-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="e01f0-167">Прокси-сервер SIP — это компонент, который преобразует сигнальную сигнальную Teams HTTP REST в SIP.</span><span class="sxs-lookup"><span data-stu-id="e01f0-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e01f0-168">![Отображает потоки зовов с включенным и отключенным обходом мультимедиа](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="e01f0-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="e01f0-169">В таблице ниже приведена разница между процессорами мультимедиа и ретрансляторами транспорта.</span><span class="sxs-lookup"><span data-stu-id="e01f0-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="e01f0-170">Процессоры мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e01f0-170">Media Processors</span></span> | <span data-ttu-id="e01f0-171">Ретрансляторы транспорта</span><span class="sxs-lookup"><span data-stu-id="e01f0-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="e01f0-172">В канале мультимедиа для звонков, не обходимых для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="e01f0-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="e01f0-173">Всегда</span><span class="sxs-lookup"><span data-stu-id="e01f0-173">Always</span></span> | <span data-ttu-id="e01f0-174">Если клиенту не удается напрямую связаться с процессором мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e01f0-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="e01f0-175">В пути мультимедиа для обхода звонков для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="e01f0-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="e01f0-176">Нвер</span><span class="sxs-lookup"><span data-stu-id="e01f0-176">Never</span></span> | <span data-ttu-id="e01f0-177">Если клиенту не удается связаться с SBC по общедоступным IP-адресу</span><span class="sxs-lookup"><span data-stu-id="e01f0-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="e01f0-178">В пути мультимедиа для голосовых приложений</span><span class="sxs-lookup"><span data-stu-id="e01f0-178">In media path for voice applications</span></span> | <span data-ttu-id="e01f0-179">Всегда</span><span class="sxs-lookup"><span data-stu-id="e01f0-179">Always</span></span> | <span data-ttu-id="e01f0-180">Нвер</span><span class="sxs-lookup"><span data-stu-id="e01f0-180">Never</span></span> | 
<span data-ttu-id="e01f0-181">Может делать транскодинг (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="e01f0-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="e01f0-182">Да</span><span class="sxs-lookup"><span data-stu-id="e01f0-182">Yes</span></span> | <span data-ttu-id="e01f0-183">Нет, звук передается только между конечными точками.</span><span class="sxs-lookup"><span data-stu-id="e01f0-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="e01f0-184">Количество экземпляров и расположение в разных странах</span><span class="sxs-lookup"><span data-stu-id="e01f0-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="e01f0-185">10 итогов: 2 на востоке и западе США; 2 в области "Париж" и "Dublin"; 2 в Гонконге и Сингапуре; 2 в Японии; 2 в Восточной и Юго-Восточной Австралии</span><span class="sxs-lookup"><span data-stu-id="e01f0-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="e01f0-186">Несколько</span><span class="sxs-lookup"><span data-stu-id="e01f0-186">Multiple</span></span>

<span data-ttu-id="e01f0-187">Диапазоны IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="e01f0-187">The IP ranges are:</span></span>
- <span data-ttu-id="e01f0-188">52.112.0.0/14 (IP-адреса от 52.112.0.1 до 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="e01f0-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="e01f0-189">52.120.0.0/14 (IP-адреса от 52.120.0.1 до 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="e01f0-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="e01f0-190">\* Объяснение транскодинга:</span><span class="sxs-lookup"><span data-stu-id="e01f0-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="e01f0-191">Процессор мультимедиа — это B2BUA, что означает, что он может изменять кодеки (например, КОДЕКИ ОТ клиента Teams до MP и G.711 между MP и SBC).</span><span class="sxs-lookup"><span data-stu-id="e01f0-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="e01f0-192">Ретрансляторы транспорта не являются B2BUA, поэтому кодек никогда не меняется между клиентом и SBC, даже если трафик передается через ретрансляторы.</span><span class="sxs-lookup"><span data-stu-id="e01f0-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="e01f0-193">Использование процессоров Teams мультимедиа, если в канале настроен обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e01f0-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="e01f0-194">Teams Процессоры мультимедиа всегда вставляются в путь мультимедиа в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="e01f0-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="e01f0-195">Звонок перенается с 1:1 на групповой звонок</span><span class="sxs-lookup"><span data-stu-id="e01f0-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="e01f0-196">Звонок федератированному Teams пользователю</span><span class="sxs-lookup"><span data-stu-id="e01f0-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="e01f0-197">Звонок переадправлен или перенаправлен пользователю Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e01f0-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="e01f0-198">Убедитесь, что ваш SBC имеет доступ к диапазонам процессоров мультимедиа и ретрансляторов транспорта, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="e01f0-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="e01f0-199">Сигнальный SIP: FQDNs</span><span class="sxs-lookup"><span data-stu-id="e01f0-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="e01f0-200">Для сигнального законодательства SIP требования к FQDN и брандмауэру одинаковы, как и для случаев без обхода.</span><span class="sxs-lookup"><span data-stu-id="e01f0-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="e01f0-201">Прямая маршрутная маршрутия предоставляется в следующих Microsoft 365 или Office 365 средах:</span><span class="sxs-lookup"><span data-stu-id="e01f0-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="e01f0-202">Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="e01f0-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="e01f0-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="e01f0-203">Office 365 GCC</span></span>
- <span data-ttu-id="e01f0-204">Office 365 GCC высокая</span><span class="sxs-lookup"><span data-stu-id="e01f0-204">Office 365 GCC High</span></span>
- <span data-ttu-id="e01f0-205">Office 365 DoD Узнайте больше [о](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) Office 365 и государственных средах США, таких как GCC, GCC Высокая и DoD.</span><span class="sxs-lookup"><span data-stu-id="e01f0-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="e01f0-206">Microsoft 365, Office 365 и Office 365 GCC средах</span><span class="sxs-lookup"><span data-stu-id="e01f0-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="e01f0-207">Точки соединения для прямой маршрутии являются следующими тремя FQDNs:</span><span class="sxs-lookup"><span data-stu-id="e01f0-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="e01f0-208">**sip.pstnhub.microsoft.com** — глобальное FQDN — необходимо сначала опробовоть.</span><span class="sxs-lookup"><span data-stu-id="e01f0-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="e01f0-209">Когда SBC отправляет запрос на устранение этого имени, DNS-серверы Microsoft Azure возвращают IP-адрес, указывающий на основной центр обработки данных Azure, который назначен SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="e01f0-210">Назначение основано на метриках производительности центра обработки данных и географической близости к SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="e01f0-211">Возвращенный IP-адрес соответствует основному FQDN.</span><span class="sxs-lookup"><span data-stu-id="e01f0-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="e01f0-212">**sip2.pstnhub.microsoft.com** — дополнительное FQDN — географически сопоставить со вторым приоритетным регионом.</span><span class="sxs-lookup"><span data-stu-id="e01f0-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="e01f0-213">**sip3.pstnhub.microsoft.com** — tertiary FQDN — географически сопоставить с третьим приоритетным регионом.</span><span class="sxs-lookup"><span data-stu-id="e01f0-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="e01f0-214">Эти три FQDDNs необходимо разместить, чтобы:</span><span class="sxs-lookup"><span data-stu-id="e01f0-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="e01f0-215">Обеспечение оптимальной работы (меньше нагрузка и ближе всего к центру обработки данных SBC, назначенного с помощью запроса к первому FQDN).</span><span class="sxs-lookup"><span data-stu-id="e01f0-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="e01f0-216">Отбой в случае, если подключение из SBC установлено к центру обработки данных, который имеет временную проблему.</span><span class="sxs-lookup"><span data-stu-id="e01f0-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="e01f0-217">Дополнительные сведения см. в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="e01f0-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="e01f0-218">FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** и **sip3.pstnhub.microsoft.com** будут разрешены на один из следующих IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="e01f0-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="e01f0-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="e01f0-219">52.114.148.0</span></span>
- <span data-ttu-id="e01f0-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="e01f0-220">52.114.132.46</span></span> 
- <span data-ttu-id="e01f0-221">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="e01f0-221">52.114.75.24</span></span> 
- <span data-ttu-id="e01f0-222">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="e01f0-222">52.114.76.76</span></span> 
- <span data-ttu-id="e01f0-223">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="e01f0-223">52.114.7.24</span></span> 
- <span data-ttu-id="e01f0-224">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="e01f0-224">52.114.14.70</span></span>
- <span data-ttu-id="e01f0-225">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="e01f0-225">52.114.16.74</span></span>
- <span data-ttu-id="e01f0-226">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="e01f0-226">52.114.20.29</span></span>
- <span data-ttu-id="e01f0-227">52.114.36.156</span><span class="sxs-lookup"><span data-stu-id="e01f0-227">52.114.36.156</span></span> 
- <span data-ttu-id="e01f0-228">52.114.32.169</span><span class="sxs-lookup"><span data-stu-id="e01f0-228">52.114.32.169</span></span>

<span data-ttu-id="e01f0-229">Для сигнального трафика необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="e01f0-229">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="e01f0-230">Если брандмауэр поддерживает имена DNS,  имя FQDN sip-all.pstnhub.microsoft.com на все эти IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="e01f0-230">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="e01f0-231">Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="e01f0-231">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="e01f0-232">Точка соединения для прямой маршрутии имеет следующий FQDN:</span><span class="sxs-lookup"><span data-stu-id="e01f0-232">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="e01f0-233">**sip.pstnhub.dod.teams.microsoft.us** — глобальное FQDN.</span><span class="sxs-lookup"><span data-stu-id="e01f0-233">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="e01f0-234">Так как Office 365 DoD существует только в центрах обработки данных в США, дополнительные и дополнительные FQDNs не существует.</span><span class="sxs-lookup"><span data-stu-id="e01f0-234">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="e01f0-235">FQDNs — sip.pstnhub.dod.teams.microsoft.us будут разрешены на один из следующих IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="e01f0-235">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="e01f0-236">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="e01f0-236">52.127.64.33</span></span>
- <span data-ttu-id="e01f0-237">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="e01f0-237">52.127.68.34</span></span>

<span data-ttu-id="e01f0-238">Для сигнального трафика необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="e01f0-238">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="e01f0-239">Если брандмауэр поддерживает имена DNS, имя FQDN sip.pstnhub.dod.teams.microsoft.us на все эти IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="e01f0-239">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="e01f0-240">Office 365 GCC высокая среда</span><span class="sxs-lookup"><span data-stu-id="e01f0-240">Office 365 GCC High environment</span></span>

<span data-ttu-id="e01f0-241">Точка соединения для прямой маршрутии имеет следующий FQDN:</span><span class="sxs-lookup"><span data-stu-id="e01f0-241">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="e01f0-242">**sip.pstnhub.gov.teams.microsoft.us** — глобальное FQDN.</span><span class="sxs-lookup"><span data-stu-id="e01f0-242">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="e01f0-243">Так как среда GCC Высокая существует только в центрах обработки данных в США, дополнительные и дополнительные FQDNs не имеются.</span><span class="sxs-lookup"><span data-stu-id="e01f0-243">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="e01f0-244">FQDNs — sip.pstnhub.gov.teams.microsoft.us будут разрешены на один из следующих IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="e01f0-244">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="e01f0-245">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="e01f0-245">52.127.88.59</span></span>
- <span data-ttu-id="e01f0-246">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="e01f0-246">52.127.92.64</span></span>

<span data-ttu-id="e01f0-247">Для сигнального трафика необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="e01f0-247">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="e01f0-248">Если брандмауэр поддерживает имена DNS, имя FQDN sip.pstnhub.gov.teams.microsoft.us на все эти IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="e01f0-248">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="e01f0-249">Сигнальный SIP: порты</span><span class="sxs-lookup"><span data-stu-id="e01f0-249">SIP Signaling: Ports</span></span>

<span data-ttu-id="e01f0-250">Требования к переносу одинаковы для всех сред Office 365, где предлагается прямая маршрутная маршрутия:</span><span class="sxs-lookup"><span data-stu-id="e01f0-250">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="e01f0-251">Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="e01f0-251">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="e01f0-252">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="e01f0-252">Office 365 GCC</span></span>
- <span data-ttu-id="e01f0-253">Office 365 GCC высокая</span><span class="sxs-lookup"><span data-stu-id="e01f0-253">Office 365 GCC High</span></span>
- <span data-ttu-id="e01f0-254">Office 365 Dod</span><span class="sxs-lookup"><span data-stu-id="e01f0-254">Office 365 DoD</span></span>

<span data-ttu-id="e01f0-255">Необходимо использовать следующие порты:</span><span class="sxs-lookup"><span data-stu-id="e01f0-255">You must use the following ports:</span></span>

| <span data-ttu-id="e01f0-256">Трафика</span><span class="sxs-lookup"><span data-stu-id="e01f0-256">Traffic</span></span> | <span data-ttu-id="e01f0-257">От</span><span class="sxs-lookup"><span data-stu-id="e01f0-257">From</span></span> | <span data-ttu-id="e01f0-258">До</span><span class="sxs-lookup"><span data-stu-id="e01f0-258">To</span></span> | <span data-ttu-id="e01f0-259">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="e01f0-259">Source port</span></span> | <span data-ttu-id="e01f0-260">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="e01f0-260">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="e01f0-261">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="e01f0-261">SIP/TLS</span></span>| <span data-ttu-id="e01f0-262">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="e01f0-262">SIP Proxy</span></span> | <span data-ttu-id="e01f0-263">Sbc</span><span class="sxs-lookup"><span data-stu-id="e01f0-263">SBC</span></span> | <span data-ttu-id="e01f0-264">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="e01f0-264">1024 - 65535</span></span> | <span data-ttu-id="e01f0-265">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="e01f0-265">Defined on the SBC</span></span> |
| <span data-ttu-id="e01f0-266">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="e01f0-266">SIP/TLS</span></span> | <span data-ttu-id="e01f0-267">Sbc</span><span class="sxs-lookup"><span data-stu-id="e01f0-267">SBC</span></span> | <span data-ttu-id="e01f0-268">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="e01f0-268">SIP Proxy</span></span> | <span data-ttu-id="e01f0-269">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="e01f0-269">Defined on the SBC</span></span> | <span data-ttu-id="e01f0-270">5061</span><span class="sxs-lookup"><span data-stu-id="e01f0-270">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="e01f0-271">Трафик мультимедиа: диапазоны IP-адресов и портов</span><span class="sxs-lookup"><span data-stu-id="e01f0-271">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="e01f0-272">Трафик мультимедиа передается между клиентом SBC и клиентом Teams, если доступно прямое подключение, или через Teams, если клиент не может связаться с SBC с использованием общего IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="e01f0-272">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="e01f0-273">Требования для прямого трафика мультимедиа (между клиентом Teams и SBC)</span><span class="sxs-lookup"><span data-stu-id="e01f0-273">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="e01f0-274">У клиента должен быть доступ к указанным портам (см. таблицу) на общедоступный IP-адрес SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-274">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="e01f0-275">Если клиент находится во внутренней сети, мультимедиа перетекают на общедоступный IP-адрес SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-275">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="e01f0-276">Вы можете настроить закрепление ветвей на устройстве NAT, чтобы трафик никогда не покидает сетевое оборудование предприятия.</span><span class="sxs-lookup"><span data-stu-id="e01f0-276">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="e01f0-277">Трафика</span><span class="sxs-lookup"><span data-stu-id="e01f0-277">Traffic</span></span> | <span data-ttu-id="e01f0-278">От</span><span class="sxs-lookup"><span data-stu-id="e01f0-278">From</span></span> | <span data-ttu-id="e01f0-279">До</span><span class="sxs-lookup"><span data-stu-id="e01f0-279">To</span></span> | <span data-ttu-id="e01f0-280">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="e01f0-280">Source port</span></span> | <span data-ttu-id="e01f0-281">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="e01f0-281">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="e01f0-282">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="e01f0-282">UDP/SRTP</span></span> | <span data-ttu-id="e01f0-283">Клиент</span><span class="sxs-lookup"><span data-stu-id="e01f0-283">Client</span></span> | <span data-ttu-id="e01f0-284">Sbc</span><span class="sxs-lookup"><span data-stu-id="e01f0-284">SBC</span></span> | <span data-ttu-id="e01f0-285">3478-3481 и 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="e01f0-285">3478-3481 and 49152 – 53247</span></span>| <span data-ttu-id="e01f0-286">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="e01f0-286">Defined on the SBC</span></span> |
| <span data-ttu-id="e01f0-287">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="e01f0-287">UDP/SRTP</span></span> | <span data-ttu-id="e01f0-288">Sbc</span><span class="sxs-lookup"><span data-stu-id="e01f0-288">SBC</span></span> | <span data-ttu-id="e01f0-289">Клиент</span><span class="sxs-lookup"><span data-stu-id="e01f0-289">Client</span></span> | <span data-ttu-id="e01f0-290">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="e01f0-290">Defined on the SBC</span></span> | <span data-ttu-id="e01f0-291">3478-3481 и 49152 – 53247</span><span class="sxs-lookup"><span data-stu-id="e01f0-291">3478-3481 and 49152 – 53247</span></span>  |


> [!NOTE]
> <span data-ttu-id="e01f0-292">Если у вас есть сетевое устройство, которое преобразует исходные порты клиента, убедитесь, что переведенные порты открыты между сетевым оборудованием и SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-292">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="e01f0-293">Требования для использования ретрансляторов транспорта</span><span class="sxs-lookup"><span data-stu-id="e01f0-293">Requirements for using Transport Relays</span></span>

<span data-ttu-id="e01f0-294">Ретрансляторы транспорта находятся в том же диапазоне, что и процессоры мультимедиа (для случаев без обхода):</span><span class="sxs-lookup"><span data-stu-id="e01f0-294">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="e01f0-295">Microsoft 365, Office 365 и Office 365 GCC средах</span><span class="sxs-lookup"><span data-stu-id="e01f0-295">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="e01f0-296">52.112.0.0 /14 (IP-адреса от 52.112.0.1 до 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="e01f0-296">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="e01f0-297">Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="e01f0-297">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="e01f0-298">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="e01f0-298">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="e01f0-299">Office 365 GCC высокая среда</span><span class="sxs-lookup"><span data-stu-id="e01f0-299">Office 365 GCC High environment</span></span>

- <span data-ttu-id="e01f0-300">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="e01f0-300">52.127.88.0/21</span></span>


<span data-ttu-id="e01f0-301">Диапазон портов ретрансляторов Teams транспорта (применимо для всех сред) отображается в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="e01f0-301">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="e01f0-302">Трафика</span><span class="sxs-lookup"><span data-stu-id="e01f0-302">Traffic</span></span> | <span data-ttu-id="e01f0-303">От</span><span class="sxs-lookup"><span data-stu-id="e01f0-303">From</span></span> | <span data-ttu-id="e01f0-304">До</span><span class="sxs-lookup"><span data-stu-id="e01f0-304">To</span></span> | <span data-ttu-id="e01f0-305">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="e01f0-305">Source port</span></span> | <span data-ttu-id="e01f0-306">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="e01f0-306">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="e01f0-307">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="e01f0-307">UDP/SRTP</span></span> | <span data-ttu-id="e01f0-308">Ретранслятор транспорта</span><span class="sxs-lookup"><span data-stu-id="e01f0-308">Transport Relay</span></span> | <span data-ttu-id="e01f0-309">Sbc</span><span class="sxs-lookup"><span data-stu-id="e01f0-309">SBC</span></span> | <span data-ttu-id="e01f0-310">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="e01f0-310">50 000 -59 999</span></span>    | <span data-ttu-id="e01f0-311">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="e01f0-311">Defined on the SBC</span></span> |
| <span data-ttu-id="e01f0-312">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="e01f0-312">UDP/SRTP</span></span> | <span data-ttu-id="e01f0-313">Sbc</span><span class="sxs-lookup"><span data-stu-id="e01f0-313">SBC</span></span> | <span data-ttu-id="e01f0-314">Ретранслятор транспорта</span><span class="sxs-lookup"><span data-stu-id="e01f0-314">Transport Relay</span></span> | <span data-ttu-id="e01f0-315">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="e01f0-315">Defined on the SBC</span></span> | <span data-ttu-id="e01f0-316">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="e01f0-316">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="e01f0-317">Корпорация Майкрософт рекомендует не менее двух портов для одновременного вызова на SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-317">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="e01f0-318">Так как в корпорации Майкрософт есть две версии ретрансляторов транспорта, требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="e01f0-318">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="e01f0-319">V4, которая может работать только с диапазоном портов от 50 000 до 59 999</span><span class="sxs-lookup"><span data-stu-id="e01f0-319">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="e01f0-320">v6, которая работает с портами 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="e01f0-320">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="e01f0-321">В настоящее время обход мультимедиа поддерживает только версию ретрансляторов транспорта версии 4.</span><span class="sxs-lookup"><span data-stu-id="e01f0-321">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="e01f0-322">В будущем мы будем внедрять поддержку v6.</span><span class="sxs-lookup"><span data-stu-id="e01f0-322">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="e01f0-323">Для перехода необходимо открыть порты 3478 и 3479.</span><span class="sxs-lookup"><span data-stu-id="e01f0-323">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="e01f0-324">Когда корпорация Майкрософт введет поддержку ретрансляторов транспорта v6 с помощью обхода мультимедиа, вам не придется перенастроять сетевое оборудование или БСК.</span><span class="sxs-lookup"><span data-stu-id="e01f0-324">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="e01f0-325">Требования к использованию процессоров мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e01f0-325">Requirements for using media processors</span></span>

<span data-ttu-id="e01f0-326">Процессоры мультимедиа всегда находятся в пути мультимедиа для голосовых приложений и веб-клиентов (например, Teams клиентах в Edge или Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="e01f0-326">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="e01f0-327">Требования одинаковы для настройки без обхода.</span><span class="sxs-lookup"><span data-stu-id="e01f0-327">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="e01f0-328">Диапазон IP-адресов для трафика мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="e01f0-328">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="e01f0-329">Office 365 и Office 365 GCC средах</span><span class="sxs-lookup"><span data-stu-id="e01f0-329">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="e01f0-330">52.112.0.0 /14 (IP-адреса от 52.112.0.1 до 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="e01f0-330">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="e01f0-331">Office 365 GCC DoD</span><span class="sxs-lookup"><span data-stu-id="e01f0-331">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="e01f0-332">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="e01f0-332">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="e01f0-333">Office 365 GCC высокая среда</span><span class="sxs-lookup"><span data-stu-id="e01f0-333">Office 365 GCC High environment</span></span>

- <span data-ttu-id="e01f0-334">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="e01f0-334">52.127.88.0/21</span></span>

<span data-ttu-id="e01f0-335">Диапазон портов процессоров мультимедиа (применимо для всех сред) показан в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="e01f0-335">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="e01f0-336">Трафика</span><span class="sxs-lookup"><span data-stu-id="e01f0-336">Traffic</span></span> | <span data-ttu-id="e01f0-337">От</span><span class="sxs-lookup"><span data-stu-id="e01f0-337">From</span></span> | <span data-ttu-id="e01f0-338">До</span><span class="sxs-lookup"><span data-stu-id="e01f0-338">To</span></span> | <span data-ttu-id="e01f0-339">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="e01f0-339">Source port</span></span> | <span data-ttu-id="e01f0-340">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="e01f0-340">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="e01f0-341">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="e01f0-341">UDP/SRTP</span></span> | <span data-ttu-id="e01f0-342">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e01f0-342">Media Processor</span></span> | <span data-ttu-id="e01f0-343">Sbc</span><span class="sxs-lookup"><span data-stu-id="e01f0-343">SBC</span></span> | <span data-ttu-id="e01f0-344">3478, 3479 и 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="e01f0-344">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="e01f0-345">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="e01f0-345">Defined on the SBC</span></span> |
| <span data-ttu-id="e01f0-346">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="e01f0-346">UDP/SRTP</span></span> | <span data-ttu-id="e01f0-347">Sbc</span><span class="sxs-lookup"><span data-stu-id="e01f0-347">SBC</span></span> | <span data-ttu-id="e01f0-348">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e01f0-348">Media Processor</span></span> | <span data-ttu-id="e01f0-349">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="e01f0-349">Defined on the SBC</span></span> | <span data-ttu-id="e01f0-350">3478, 3479 и 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="e01f0-350">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="e01f0-351">Настройка отдельных каналов для обхода мультимедиа и обхода без мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e01f0-351">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="e01f0-352">Если вы хотите подтвердить функциональность перед переносом всех функций обхода мультимедиа в обход мультимедиа, вы можете создать отдельную магистраль и отдельную политику голосового маршрутирования Online для маршрутирования к каналу обхода мультимедиа и назначения определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="e01f0-352">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="e01f0-353">Шаги высокой настройки:</span><span class="sxs-lookup"><span data-stu-id="e01f0-353">High-level configuration steps:</span></span>

- <span data-ttu-id="e01f0-354">Определите пользователей, которые должны проверить обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e01f0-354">Identify users to test media bypass.</span></span>

- <span data-ttu-id="e01f0-355">Создайте две отдельные связи с разными FQDNs: одно из них включено для обхода мультимедиа; другой нет.</span><span class="sxs-lookup"><span data-stu-id="e01f0-355">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="e01f0-356">Обе стороны указывают на один и тот же SBC.</span><span class="sxs-lookup"><span data-stu-id="e01f0-356">Both trunks point to the same SBC.</span></span> <span data-ttu-id="e01f0-357">Порты для сигнального сигнала TLS SIP должны быть другими.</span><span class="sxs-lookup"><span data-stu-id="e01f0-357">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="e01f0-358">Порты мультимедиа должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="e01f0-358">The ports for media must be the same.</span></span>

- <span data-ttu-id="e01f0-359">Создайте политику маршрутирования голосовой связи в Интернете и назначьте канал обхода мультимедиа соответствующим маршрутам, связанным с использованием этой политики через ТСТС.</span><span class="sxs-lookup"><span data-stu-id="e01f0-359">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="e01f0-360">Назначьте новую политику маршрутирования голосовой почты в Интернете пользователям, для проверки обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e01f0-360">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="e01f0-361">Пример ниже иллюстрирует эту логику.</span><span class="sxs-lookup"><span data-stu-id="e01f0-361">The example below illustrates this logic.</span></span>

| <span data-ttu-id="e01f0-362">Набор пользователей</span><span class="sxs-lookup"><span data-stu-id="e01f0-362">Set of users</span></span> | <span data-ttu-id="e01f0-363">Количество пользователей</span><span class="sxs-lookup"><span data-stu-id="e01f0-363">Number of users</span></span> | <span data-ttu-id="e01f0-364">FQDN", присвоенное в OVRP</span><span class="sxs-lookup"><span data-stu-id="e01f0-364">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="e01f0-365">Включен обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e01f0-365">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="e01f0-366">Пользователи с обойденной службой без мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e01f0-366">Users with non-media bypass trunk</span></span> | <span data-ttu-id="e01f0-367">980</span><span class="sxs-lookup"><span data-stu-id="e01f0-367">980</span></span> | <span data-ttu-id="e01f0-368">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="e01f0-368">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="e01f0-369">false</span><span class="sxs-lookup"><span data-stu-id="e01f0-369">false</span></span> |
<span data-ttu-id="e01f0-370">Пользователи с обводом мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e01f0-370">Users with media bypass trunk</span></span> | <span data-ttu-id="e01f0-371">20</span><span class="sxs-lookup"><span data-stu-id="e01f0-371">20</span></span> | <span data-ttu-id="e01f0-372">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="e01f0-372">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="e01f0-373">true</span><span class="sxs-lookup"><span data-stu-id="e01f0-373">true</span></span> | 

<span data-ttu-id="e01f0-374">Обе связи могут указать на один и тот же SBC с одинаковым общедоступным IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="e01f0-374">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="e01f0-375">Сигнальные порты TLS на SBC должны быть другими, как показано на приведенной ниже схеме.</span><span class="sxs-lookup"><span data-stu-id="e01f0-375">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="e01f0-376">Обратите внимание, что сертификат должен поддерживать обе стороны.</span><span class="sxs-lookup"><span data-stu-id="e01f0-376">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="e01f0-377">В САН у вас должны быть два имена **(sbc1.contoso.com** и **sbc2.contoso.com**) или поддиз.сертификат.</span><span class="sxs-lookup"><span data-stu-id="e01f0-377">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e01f0-378">![Обе связи могут указать на один и тот же SBC с одинаковым общедоступным IP-адресом](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="e01f0-378">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="e01f0-379">Сведения о настройке двух телефонов на одном ИТ-сайте см. в документации поставщика SBC:</span><span class="sxs-lookup"><span data-stu-id="e01f0-379">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="e01f0-380">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="e01f0-380">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="e01f0-381">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="e01f0-381">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="e01f0-382">Документация по развертыванию коммуникаций на ленте</span><span class="sxs-lookup"><span data-stu-id="e01f0-382">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="e01f0-383">Документация по развертыванию TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="e01f0-383">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="e01f0-384">Клиентские конечные точки, поддерживаемые с обходом мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e01f0-384">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="e01f0-385">Обход мультимедиа поддерживается для всех автономных Teams классических клиентов, клиентов Android и iOS, а также Teams Телефон устройств.</span><span class="sxs-lookup"><span data-stu-id="e01f0-385">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="e01f0-386">Для всех остальных конечных точек, которые не поддерживают обход мультимедиа, мы преобразуем звонок в обход, даже если он начался как обходной вызов.</span><span class="sxs-lookup"><span data-stu-id="e01f0-386">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="e01f0-387">Это происходит автоматически и не требует действий от администратора.</span><span class="sxs-lookup"><span data-stu-id="e01f0-387">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="e01f0-388">К ним относятся телефоны Skype для бизнеса 3PIP и веб-клиенты Teams, поддерживаюющие прямые маршруты звонков (клиенты На основе WebRTC, работающие в Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="e01f0-388">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="e01f0-389">См. также</span><span class="sxs-lookup"><span data-stu-id="e01f0-389">See also</span></span>

[<span data-ttu-id="e01f0-390">Настройка обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="e01f0-390">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
