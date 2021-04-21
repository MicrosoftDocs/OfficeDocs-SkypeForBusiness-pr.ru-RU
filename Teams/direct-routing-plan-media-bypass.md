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
description: Узнайте, как спланировать обход мультимедиа с помощью прямой маршрутии телефонной системы, которая позволяет сократить путь к трафику мультимедиа и повысить производительность.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2cbe739a567588b44bef87f7b852ed8de965ad3
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899100"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="6030a-103">Планирование обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="6030a-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="6030a-104">Обход мультимедиа с прямой маршрутией</span><span class="sxs-lookup"><span data-stu-id="6030a-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="6030a-105">Обход мультимедиа позволяет сократить путь к трафику мультимедиа и уменьшить количество переходов в пути для улучшения производительности.</span><span class="sxs-lookup"><span data-stu-id="6030a-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="6030a-106">При обходе мультимедиа мультимедиа между SBC и клиентом хранятся мультимедиа, а не через телефонную систему Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6030a-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="6030a-107">Чтобы настроить обход мультимедиа, SBC и клиент должны быть в одном расположении или сети.</span><span class="sxs-lookup"><span data-stu-id="6030a-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="6030a-108">Вы можете управлять обходом мультимедиа для каждого SBC с помощью команды **Set-CSOnlinePSTNGateway** с параметром **-MediaBypass,** для параметра true или false.</span><span class="sxs-lookup"><span data-stu-id="6030a-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="6030a-109">Если включить обход мультимедиа, это не означает, что весь трафик мультимедиа будет оставаться в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="6030a-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="6030a-110">В этой статье описан поток зова в разных сценариях.</span><span class="sxs-lookup"><span data-stu-id="6030a-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="6030a-111">На схемах ниже показано, чем отличается поток вызовов как с обходом мультимедиа, так и без него.</span><span class="sxs-lookup"><span data-stu-id="6030a-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="6030a-112">Без обхода мультимедиа, когда клиент совершает или принимает звонок, сигнальный и поток мультимедиа между SBC, телефонной системой Майкрософт и клиентом Teams, как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="6030a-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6030a-113">![Сигнальный поток и поток мультимедиа без обхода мультимедиа](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="6030a-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="6030a-114">Но предположим, что пользователь находится в том же здании или сети, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="6030a-115">Например, предположим, что пользователь, который находится в здании в Области, звонит пользователю ННР:</span><span class="sxs-lookup"><span data-stu-id="6030a-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="6030a-116">**Без обхода мультимедиа** будут поступать через Залив или Dublin (где развернуты центра обработки данных Майкрософт) и обратно в SBC в Сша.</span><span class="sxs-lookup"><span data-stu-id="6030a-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="6030a-117">Центр обработки данных в Европе выбран, так как он находится в Европе, а корпорация Майкрософт использует центр обработки данных, ближайший к SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="6030a-118">Хотя этот подход не влияет на качество зова из-за оптимизации потока трафика в сетях Майкрософт в большинстве географических данных, трафик имеет ненужный цикл.</span><span class="sxs-lookup"><span data-stu-id="6030a-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="6030a-119">**При обходе** мультимедиа хранятся непосредственно между пользователем Teams и SBC, как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="6030a-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="6030a-120">![Сигнальный поток и поток мультимедиа с обходом мультимедиа](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="6030a-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="6030a-121">Обход мультимедиа использует протоколы, называемые интерактивными подключениями (ICE) в клиенте Teams и ICE lite на SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="6030a-122">Эти протоколы позволяют прямой маршрутике использовать самый прямой маршрут мультимедиа для оптимального качества.</span><span class="sxs-lookup"><span data-stu-id="6030a-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="6030a-123">ICE и ICE Lite являются стандартами WebRTC.</span><span class="sxs-lookup"><span data-stu-id="6030a-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="6030a-124">Подробные сведения об этих протоколах см. в описании протокола RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="6030a-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="6030a-125">Планирование потока вызовов и брандмауэра</span><span class="sxs-lookup"><span data-stu-id="6030a-125">Call flow and firewall planning</span></span>

<span data-ttu-id="6030a-126">Планирование потока присоединения к звонкам и брандмауэра зависит от того, имеет ли пользователь прямой доступ к общедоступным IP-адресам SBC и находится ли пользователь внутри или за пределами сети.</span><span class="sxs-lookup"><span data-stu-id="6030a-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="6030a-127">Поток зова, если у пользователя есть прямой доступ к общедоступным IP-адресу SBC</span><span class="sxs-lookup"><span data-stu-id="6030a-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="6030a-128">Если у пользователя есть прямой доступ к общедоступным IP-адресам SBC, поток зовов будет следующим:</span><span class="sxs-lookup"><span data-stu-id="6030a-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="6030a-129">Для обхода мультимедиа клиент Teams должен иметь доступ к общедоступным IP-адресам SBC даже из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="6030a-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="6030a-130">Если прямая мультимедиа не требуется, они могут перетекать через ретрансляторы транспорта.</span><span class="sxs-lookup"><span data-stu-id="6030a-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="6030a-131">Это рекомендуемое решение, если пользователь находится в том же здании или сети, что и SBC, и удаляет компоненты Microsoft Cloud из пути мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="6030a-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="6030a-132">Сигнальный сигнал всегда проходит через облако Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6030a-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="6030a-133">На следующей схеме показан поток зова, когда включен обход мультимедиа, клиент является внутренним, а клиент может получить доступ к общедоступным IP-адресам SBC (прямой мультимедиа):</span><span class="sxs-lookup"><span data-stu-id="6030a-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="6030a-134">Стрелки и числимые значения путей соответствуют потокам вызовов [Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="6030a-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="6030a-135">Сигнальный трафик SIP всегда проходит по путям 4 и 4' (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="6030a-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="6030a-136">Media stays local and takes path 5b.</span><span class="sxs-lookup"><span data-stu-id="6030a-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6030a-137">![Отображает поток зовов с включенным обходом мультимедиа, клиент является внутренним](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="6030a-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="6030a-138">Поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресам SBC</span><span class="sxs-lookup"><span data-stu-id="6030a-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="6030a-139">Ниже описан поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресам SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="6030a-140">Например, предположим, что пользователь является внешним, а администратор клиента решил не открывать общедоступный IP-адрес SBC для всех пользователей в Интернете, а только в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="6030a-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="6030a-141">Внутренние компоненты трафика могут перетекать через ретрансляторы транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="6030a-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="6030a-142">Примите во внимание следующее:</span><span class="sxs-lookup"><span data-stu-id="6030a-142">Consider the following:</span></span>

- <span data-ttu-id="6030a-143">Используются ретрансляторы транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="6030a-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="6030a-144">Для обхода мультимедиа корпорация Майкрософт использует версию ретрансляторов транспорта, которая требует открывать порты от 50 000 до 59 999 между ретрансляторами транспорта Teams и SBC (в будущем планируется перейти на версию, которая требует только 3478 и 3479 портов).</span><span class="sxs-lookup"><span data-stu-id="6030a-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="6030a-145">На следующей схеме показан поток зова, когда включен обход мультимедиа, клиент является внешним и не может получить доступ к общедоступным IP-адресам контроллера границы сеанса (мультимедиа ретранслются ретранслятором транспорта Teams).</span><span class="sxs-lookup"><span data-stu-id="6030a-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="6030a-146">Стрелки и числимые значения путей соответствуют потокам вызовов [Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="6030a-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="6030a-147">Мультимедиа передается по путям 3, 3', 4 и 4'</span><span class="sxs-lookup"><span data-stu-id="6030a-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6030a-148">![Отображает поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресам SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="6030a-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="6030a-149">Поток присоединения к звонкам, если пользователь находится за пределами сети и имеет доступ к общедоступным IP-адресам SBC</span><span class="sxs-lookup"><span data-stu-id="6030a-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="6030a-150">Такая конфигурация не рекомендуется, так как она не имеет преимуществ в ретрансляторах транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="6030a-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="6030a-151">Вместо этого следует рассмотреть предыдущий сценарий, в котором у пользователя нет доступа к общедоступным IP-адресам SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="6030a-152">На следующей схеме показан поток зова, когда включен обход мультимедиа, клиент внешний, а клиент может получить доступ к общедоступным IP-адресам SBC (прямого мультимедиа).</span><span class="sxs-lookup"><span data-stu-id="6030a-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="6030a-153">Стрелки и числимые значения путей соответствуют статье Потоки вызовов [Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="6030a-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="6030a-154">Сигнальный трафик SIP всегда проходит по путям 3 и 3' (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="6030a-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="6030a-155">Потоки мультимедиа, использующие путь 2.</span><span class="sxs-lookup"><span data-stu-id="6030a-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6030a-156">![Отображает поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресам SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="6030a-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="6030a-157">Использование процессоров мультимедиа и ретрансляторов транспорта</span><span class="sxs-lookup"><span data-stu-id="6030a-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="6030a-158">В Microsoft Cloud есть два компонента, которые могут быть в пути к трафику мультимедиа: процессоры мультимедиа и ретрансляторы транспорта.</span><span class="sxs-lookup"><span data-stu-id="6030a-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="6030a-159">Процессор мультимедиа — это общедоступный компонент, который обрабатывает мультимедиа в случаях без обхода и обрабатывает мультимедиа для голосовых приложений.</span><span class="sxs-lookup"><span data-stu-id="6030a-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="6030a-160">Процессоры мультимедиа всегда находятся в пути для конечных пользователей, но никогда не находятся в пути для обходных звонков.</span><span class="sxs-lookup"><span data-stu-id="6030a-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="6030a-161">Процессоры мультимедиа всегда находятся в пути для всех голосовых приложений, таких как "Парк вызовов", "Автоотправление организации" и "Очереди зовов".</span><span class="sxs-lookup"><span data-stu-id="6030a-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="6030a-162">Ретранслятор транспорта используется для подключения к ближайшей службе транспорта для отправки трафика в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="6030a-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="6030a-163">В зависимости от того, где находится пользователь и как настроена сеть, ретрансляторы транспорта могут оказаться в пути для обходных звонков ( от пользователей или от их маршрутов).</span><span class="sxs-lookup"><span data-stu-id="6030a-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="6030a-164">На следующей схеме показаны два потока зова: один с включенным обходом мультимедиа, второй — с отключенным обходом мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="6030a-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="6030a-165">Схема показывает только трафик, относяющийся к конечным пользователям или направляющийся на него.</span><span class="sxs-lookup"><span data-stu-id="6030a-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="6030a-166">Контроллер мультимедиа — это микрослужба в Azure, которая назначает процессоры мультимедиа и создает предложения протокола SDP.</span><span class="sxs-lookup"><span data-stu-id="6030a-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="6030a-167">Прокси-сервер SIP — это компонент, который преобразует сигналы HTTP REST, используемые в Teams, в SIP.</span><span class="sxs-lookup"><span data-stu-id="6030a-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6030a-168">![Отображает потоки зовов с включенным и отключенным обходом мультимедиа](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="6030a-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="6030a-169">В таблице ниже приведена разница между процессорами мультимедиа и ретрансляторами транспорта.</span><span class="sxs-lookup"><span data-stu-id="6030a-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="6030a-170">Процессоры мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6030a-170">Media Processors</span></span> | <span data-ttu-id="6030a-171">Ретрансляторы транспорта</span><span class="sxs-lookup"><span data-stu-id="6030a-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="6030a-172">В канале мультимедиа для звонков, не обходимых для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="6030a-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="6030a-173">Всегда</span><span class="sxs-lookup"><span data-stu-id="6030a-173">Always</span></span> | <span data-ttu-id="6030a-174">Если клиенту не удается напрямую связаться с процессором мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6030a-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="6030a-175">В пути мультимедиа для обхода звонков для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="6030a-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="6030a-176">Нвер</span><span class="sxs-lookup"><span data-stu-id="6030a-176">Never</span></span> | <span data-ttu-id="6030a-177">Если клиенту не удается связаться с SBC по общедоступным IP-адресу</span><span class="sxs-lookup"><span data-stu-id="6030a-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="6030a-178">В пути мультимедиа для голосовых приложений</span><span class="sxs-lookup"><span data-stu-id="6030a-178">In media path for voice applications</span></span> | <span data-ttu-id="6030a-179">Всегда</span><span class="sxs-lookup"><span data-stu-id="6030a-179">Always</span></span> | <span data-ttu-id="6030a-180">Нвер</span><span class="sxs-lookup"><span data-stu-id="6030a-180">Never</span></span> | 
<span data-ttu-id="6030a-181">Может делать транскодинг (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="6030a-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="6030a-182">Да</span><span class="sxs-lookup"><span data-stu-id="6030a-182">Yes</span></span> | <span data-ttu-id="6030a-183">Нет, звук передается только между конечными точками.</span><span class="sxs-lookup"><span data-stu-id="6030a-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="6030a-184">Количество экземпляров и расположение в разных странах</span><span class="sxs-lookup"><span data-stu-id="6030a-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="6030a-185">10 итогов: 2 на востоке и западе США; 2 в области "Париж" и "Dublin"; 2 в Гонконге и Сингапуре; 2 в Японии; 2 в Восточной и Юго-Восточной Австралии</span><span class="sxs-lookup"><span data-stu-id="6030a-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="6030a-186">Несколько</span><span class="sxs-lookup"><span data-stu-id="6030a-186">Multiple</span></span>

<span data-ttu-id="6030a-187">Диапазоны IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="6030a-187">The IP ranges are:</span></span>
- <span data-ttu-id="6030a-188">52.112.0.0/14 (IP-адреса от 52.112.0.1 до 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="6030a-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="6030a-189">52.120.0.0/14 (IP-адреса от 52.120.0.1 до 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="6030a-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="6030a-190">\* Объяснение транскодинга:</span><span class="sxs-lookup"><span data-stu-id="6030a-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="6030a-191">Процессор мультимедиа — это B2BUA, то есть он может изменять кодеки (например, ТЕКСТ ИЗ клиента Teams в MP и G.711 между MP и SBC).</span><span class="sxs-lookup"><span data-stu-id="6030a-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="6030a-192">Ретрансляторы транспорта не являются B2BUA, поэтому кодек никогда не меняется между клиентом и SBC, даже если трафик передается через ретрансляторы.</span><span class="sxs-lookup"><span data-stu-id="6030a-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="6030a-193">Использование процессоров мультимедиа Teams, если в канале настроен обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6030a-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="6030a-194">Процессоры мультимедиа Teams всегда вставляются в путь мультимедиа в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="6030a-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="6030a-195">Звонок перенается с 1:1 на групповой звонок</span><span class="sxs-lookup"><span data-stu-id="6030a-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="6030a-196">Звонок федератированному пользователю Teams</span><span class="sxs-lookup"><span data-stu-id="6030a-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="6030a-197">Звонок переадправлен или перенаправлен пользователю Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6030a-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="6030a-198">Убедитесь, что ваш SBC имеет доступ к диапазонам процессоров мультимедиа и ретрансляторов транспорта, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="6030a-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="6030a-199">Сигнальный SIP: FQDNs</span><span class="sxs-lookup"><span data-stu-id="6030a-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="6030a-200">Для сигнального законодательства SIP требования к FQDN и брандмауэру одинаковы, как и для случаев без обхода.</span><span class="sxs-lookup"><span data-stu-id="6030a-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="6030a-201">Прямая маршрутия предоставляется в следующих средах Microsoft 365 или Office 365:</span><span class="sxs-lookup"><span data-stu-id="6030a-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="6030a-202">Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="6030a-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="6030a-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6030a-203">Office 365 GCC</span></span>
- <span data-ttu-id="6030a-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6030a-204">Office 365 GCC High</span></span>
- <span data-ttu-id="6030a-205">Office 365 DoD Узнайте больше о средах [Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) и государственных государственных органов США, таких как GCC, GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="6030a-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6030a-206">Среды Microsoft 365, Office 365 и GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="6030a-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="6030a-207">Точки соединения для прямой маршрутии являются следующими тремя FQDNs:</span><span class="sxs-lookup"><span data-stu-id="6030a-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="6030a-208">**sip.pstnhub.microsoft.com** — глобальное FQDN — необходимо сначала опробовоть.</span><span class="sxs-lookup"><span data-stu-id="6030a-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="6030a-209">Когда SBC отправляет запрос на устранение этого имени, DNS-серверы Microsoft Azure возвращают IP-адрес, указывающий на основной центр обработки данных Azure, который назначен SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="6030a-210">Назначение основано на метриках производительности центра обработки данных и географической близости к SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="6030a-211">Возвращенный IP-адрес соответствует основному FQDN.</span><span class="sxs-lookup"><span data-stu-id="6030a-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="6030a-212">**sip2.pstnhub.microsoft.com** — дополнительное FQDN — географически сопоставить со вторым приоритетным регионом.</span><span class="sxs-lookup"><span data-stu-id="6030a-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="6030a-213">**sip3.pstnhub.microsoft.com** — tertiary FQDN — географически сопоставить с третьим приоритетным регионом.</span><span class="sxs-lookup"><span data-stu-id="6030a-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="6030a-214">Эти три FQDDNs необходимо разместить, чтобы:</span><span class="sxs-lookup"><span data-stu-id="6030a-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="6030a-215">Обеспечение оптимальной работы (меньше нагрузка и ближе всего к центру обработки данных SBC, назначенного с помощью запроса к первому FQDN).</span><span class="sxs-lookup"><span data-stu-id="6030a-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="6030a-216">Отбой в случае, если подключение из SBC установлено к центру обработки данных, который имеет временную проблему.</span><span class="sxs-lookup"><span data-stu-id="6030a-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="6030a-217">Дополнительные сведения см. в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="6030a-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="6030a-218">FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** и **sip3.pstnhub.microsoft.com** будут разрешены на один из следующих IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="6030a-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="6030a-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="6030a-219">52.114.148.0</span></span>
- <span data-ttu-id="6030a-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="6030a-220">52.114.132.46</span></span>
- <span data-ttu-id="6030a-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="6030a-221">52.114.16.74</span></span>
- <span data-ttu-id="6030a-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="6030a-222">52.114.20.29</span></span>
- <span data-ttu-id="6030a-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="6030a-223">52.114.75.24</span></span>
- <span data-ttu-id="6030a-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="6030a-224">52.114.76.76</span></span>
- <span data-ttu-id="6030a-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="6030a-225">52.114.7.24</span></span>
- <span data-ttu-id="6030a-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="6030a-226">52.114.14.70</span></span>

<span data-ttu-id="6030a-227">Для сигнального трафика необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="6030a-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="6030a-228">Если брандмауэр поддерживает имена DNS,  имя FQDN sip-all.pstnhub.microsoft.com на все эти IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="6030a-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6030a-229">Среда DoD для GCC в Office 365</span><span class="sxs-lookup"><span data-stu-id="6030a-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="6030a-230">Точка соединения для прямой маршрутии имеет следующий FQDN:</span><span class="sxs-lookup"><span data-stu-id="6030a-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="6030a-231">**sip.pstnhub.dod.teams.microsoft.us** — глобальное FQDN.</span><span class="sxs-lookup"><span data-stu-id="6030a-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="6030a-232">Так как среда DoD Office 365 существует только в центрах обработки данных в США, дополнительных итериарных FQDNs не существует.</span><span class="sxs-lookup"><span data-stu-id="6030a-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="6030a-233">FQDNs — sip.pstnhub.dod.teams.microsoft.us будут разрешены на один из следующих IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="6030a-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="6030a-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="6030a-234">52.127.64.33</span></span>
- <span data-ttu-id="6030a-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="6030a-235">52.127.68.34</span></span>

<span data-ttu-id="6030a-236">Для сигнального трафика необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="6030a-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="6030a-237">Если брандмауэр поддерживает имена DNS, имя FQDN sip.pstnhub.dod.teams.microsoft.us на все эти IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="6030a-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6030a-238">Среда Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6030a-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="6030a-239">Точка соединения для прямой маршрутии имеет следующий FQDN:</span><span class="sxs-lookup"><span data-stu-id="6030a-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="6030a-240">**sip.pstnhub.gov.teams.microsoft.us** — глобальное FQDN.</span><span class="sxs-lookup"><span data-stu-id="6030a-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="6030a-241">Так как среда GCC High существует только в центрах обработки данных США, дополнительные и дополнительные FQDNs не имеются.</span><span class="sxs-lookup"><span data-stu-id="6030a-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="6030a-242">FQDNs — sip.pstnhub.gov.teams.microsoft.us будут разрешены на один из следующих IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="6030a-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="6030a-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="6030a-243">52.127.88.59</span></span>
- <span data-ttu-id="6030a-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="6030a-244">52.127.92.64</span></span>

<span data-ttu-id="6030a-245">Для сигнального трафика необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="6030a-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="6030a-246">Если брандмауэр поддерживает имена DNS, имя FQDN sip.pstnhub.gov.teams.microsoft.us на все эти IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="6030a-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="6030a-247">Сигнальный SIP: порты</span><span class="sxs-lookup"><span data-stu-id="6030a-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="6030a-248">Требования к портам одинаковы для всех сред Office 365, в которых предлагается прямая маршрутная маршрутия:</span><span class="sxs-lookup"><span data-stu-id="6030a-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="6030a-249">Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="6030a-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="6030a-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6030a-250">Office 365 GCC</span></span>
- <span data-ttu-id="6030a-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6030a-251">Office 365 GCC High</span></span>
- <span data-ttu-id="6030a-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="6030a-252">Office 365 DoD</span></span>

<span data-ttu-id="6030a-253">Необходимо использовать следующие порты:</span><span class="sxs-lookup"><span data-stu-id="6030a-253">You must use the following ports:</span></span>

| <span data-ttu-id="6030a-254">Трафика</span><span class="sxs-lookup"><span data-stu-id="6030a-254">Traffic</span></span> | <span data-ttu-id="6030a-255">От</span><span class="sxs-lookup"><span data-stu-id="6030a-255">From</span></span> | <span data-ttu-id="6030a-256">До</span><span class="sxs-lookup"><span data-stu-id="6030a-256">To</span></span> | <span data-ttu-id="6030a-257">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="6030a-257">Source port</span></span> | <span data-ttu-id="6030a-258">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="6030a-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6030a-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="6030a-259">SIP/TLS</span></span>| <span data-ttu-id="6030a-260">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="6030a-260">SIP Proxy</span></span> | <span data-ttu-id="6030a-261">Sbc</span><span class="sxs-lookup"><span data-stu-id="6030a-261">SBC</span></span> | <span data-ttu-id="6030a-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="6030a-262">1024 - 65535</span></span> | <span data-ttu-id="6030a-263">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="6030a-263">Defined on the SBC</span></span> |
| <span data-ttu-id="6030a-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="6030a-264">SIP/TLS</span></span> | <span data-ttu-id="6030a-265">Sbc</span><span class="sxs-lookup"><span data-stu-id="6030a-265">SBC</span></span> | <span data-ttu-id="6030a-266">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="6030a-266">SIP Proxy</span></span> | <span data-ttu-id="6030a-267">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="6030a-267">Defined on the SBC</span></span> | <span data-ttu-id="6030a-268">5061</span><span class="sxs-lookup"><span data-stu-id="6030a-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="6030a-269">Трафик мультимедиа: диапазоны IP-адресов и портов</span><span class="sxs-lookup"><span data-stu-id="6030a-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="6030a-270">Трафик мультимедиа передается между клиентом SBC и Teams, если доступно прямое подключение, или через ретрансляторы транспорта Teams, если клиент не может связаться с SBC с использованием общего IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="6030a-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="6030a-271">Требования для прямого трафика мультимедиа (между клиентом Teams и SBC)</span><span class="sxs-lookup"><span data-stu-id="6030a-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="6030a-272">У клиента должен быть доступ к указанным портам (см. таблицу) на общедоступный IP-адрес SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="6030a-273">Если клиент находится во внутренней сети, мультимедиа перетекают на общедоступный IP-адрес SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-273">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="6030a-274">Вы можете настроить закрепление ветвей на устройстве NAT, чтобы трафик никогда не покидает сетевое оборудование предприятия.</span><span class="sxs-lookup"><span data-stu-id="6030a-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="6030a-275">Трафика</span><span class="sxs-lookup"><span data-stu-id="6030a-275">Traffic</span></span> | <span data-ttu-id="6030a-276">От</span><span class="sxs-lookup"><span data-stu-id="6030a-276">From</span></span> | <span data-ttu-id="6030a-277">До</span><span class="sxs-lookup"><span data-stu-id="6030a-277">To</span></span> | <span data-ttu-id="6030a-278">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="6030a-278">Source port</span></span> | <span data-ttu-id="6030a-279">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="6030a-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6030a-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6030a-280">UDP/SRTP</span></span> | <span data-ttu-id="6030a-281">Клиент</span><span class="sxs-lookup"><span data-stu-id="6030a-281">Client</span></span> | <span data-ttu-id="6030a-282">Sbc</span><span class="sxs-lookup"><span data-stu-id="6030a-282">SBC</span></span> | <span data-ttu-id="6030a-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="6030a-283">50 000 – 50 019</span></span>  | <span data-ttu-id="6030a-284">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="6030a-284">Defined on the SBC</span></span> |
| <span data-ttu-id="6030a-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6030a-285">UDP/SRTP</span></span> | <span data-ttu-id="6030a-286">Sbc</span><span class="sxs-lookup"><span data-stu-id="6030a-286">SBC</span></span> | <span data-ttu-id="6030a-287">Клиент</span><span class="sxs-lookup"><span data-stu-id="6030a-287">Client</span></span> | <span data-ttu-id="6030a-288">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="6030a-288">Defined on the SBC</span></span> | <span data-ttu-id="6030a-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="6030a-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="6030a-290">Если у вас есть сетевое устройство, которое преобразует исходные порты клиента, убедитесь, что переведенные порты открыты между сетевым оборудованием и SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="6030a-291">Требования для использования ретрансляторов транспорта</span><span class="sxs-lookup"><span data-stu-id="6030a-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="6030a-292">Ретрансляторы транспорта находятся в том же диапазоне, что и процессоры мультимедиа (для случаев без обхода):</span><span class="sxs-lookup"><span data-stu-id="6030a-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6030a-293">Среды Microsoft 365, Office 365 и GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="6030a-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="6030a-294">52.112.0.0 /14 (IP-адреса от 52.112.0.1 до 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="6030a-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6030a-295">Среда DoD для GCC в Office 365</span><span class="sxs-lookup"><span data-stu-id="6030a-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="6030a-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="6030a-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6030a-297">Среда Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6030a-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="6030a-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="6030a-298">52.127.88.0/21</span></span>


<span data-ttu-id="6030a-299">Диапазон портов ретрансляторов транспорта Teams (применимо для всех сред) показан в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="6030a-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="6030a-300">Трафика</span><span class="sxs-lookup"><span data-stu-id="6030a-300">Traffic</span></span> | <span data-ttu-id="6030a-301">От</span><span class="sxs-lookup"><span data-stu-id="6030a-301">From</span></span> | <span data-ttu-id="6030a-302">До</span><span class="sxs-lookup"><span data-stu-id="6030a-302">To</span></span> | <span data-ttu-id="6030a-303">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="6030a-303">Source port</span></span> | <span data-ttu-id="6030a-304">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="6030a-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6030a-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6030a-305">UDP/SRTP</span></span> | <span data-ttu-id="6030a-306">Ретранслятор транспорта</span><span class="sxs-lookup"><span data-stu-id="6030a-306">Transport Relay</span></span> | <span data-ttu-id="6030a-307">Sbc</span><span class="sxs-lookup"><span data-stu-id="6030a-307">SBC</span></span> | <span data-ttu-id="6030a-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="6030a-308">50 000 -59 999</span></span>    | <span data-ttu-id="6030a-309">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="6030a-309">Defined on the SBC</span></span> |
| <span data-ttu-id="6030a-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6030a-310">UDP/SRTP</span></span> | <span data-ttu-id="6030a-311">Sbc</span><span class="sxs-lookup"><span data-stu-id="6030a-311">SBC</span></span> | <span data-ttu-id="6030a-312">Ретранслятор транспорта</span><span class="sxs-lookup"><span data-stu-id="6030a-312">Transport Relay</span></span> | <span data-ttu-id="6030a-313">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="6030a-313">Defined on the SBC</span></span> | <span data-ttu-id="6030a-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="6030a-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="6030a-315">Корпорация Майкрософт рекомендует не менее двух портов для одновременного вызова на SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="6030a-316">Так как в корпорации Майкрософт есть две версии ретрансляторов транспорта, требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="6030a-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="6030a-317">V4, которая может работать только с диапазоном портов от 50 000 до 59 999</span><span class="sxs-lookup"><span data-stu-id="6030a-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="6030a-318">v6, которая работает с портами 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="6030a-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="6030a-319">В настоящее время обход мультимедиа поддерживает только версию ретрансляторов транспорта версии 4.</span><span class="sxs-lookup"><span data-stu-id="6030a-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="6030a-320">В будущем мы будем внедрять поддержку v6.</span><span class="sxs-lookup"><span data-stu-id="6030a-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="6030a-321">Для перехода необходимо открыть порты 3478 и 3479.</span><span class="sxs-lookup"><span data-stu-id="6030a-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="6030a-322">Когда корпорация Майкрософт введет поддержку ретрансляторов транспорта v6 с помощью обхода мультимедиа, вам не придется перенастроять сетевое оборудование или БСК.</span><span class="sxs-lookup"><span data-stu-id="6030a-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="6030a-323">Требования к использованию процессоров мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6030a-323">Requirements for using media processors</span></span>

<span data-ttu-id="6030a-324">Процессоры мультимедиа всегда находятся в пути мультимедиа для голосовых приложений и веб-клиентов (например, клиентов Teams в Edge или Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="6030a-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="6030a-325">Требования одинаковы для настройки без обхода.</span><span class="sxs-lookup"><span data-stu-id="6030a-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="6030a-326">Диапазон IP-адресов для трафика мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="6030a-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6030a-327">Среды GCC Office 365 и Office 365</span><span class="sxs-lookup"><span data-stu-id="6030a-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="6030a-328">52.112.0.0 /14 (IP-адреса от 52.112.0.1 до 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="6030a-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6030a-329">Среда DoD для GCC в Office 365</span><span class="sxs-lookup"><span data-stu-id="6030a-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="6030a-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="6030a-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6030a-331">Среда Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6030a-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="6030a-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="6030a-332">52.127.88.0/21</span></span>

<span data-ttu-id="6030a-333">Диапазон портов процессоров мультимедиа (применимо для всех сред) показан в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="6030a-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="6030a-334">Трафика</span><span class="sxs-lookup"><span data-stu-id="6030a-334">Traffic</span></span> | <span data-ttu-id="6030a-335">От</span><span class="sxs-lookup"><span data-stu-id="6030a-335">From</span></span> | <span data-ttu-id="6030a-336">До</span><span class="sxs-lookup"><span data-stu-id="6030a-336">To</span></span> | <span data-ttu-id="6030a-337">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="6030a-337">Source port</span></span> | <span data-ttu-id="6030a-338">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="6030a-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6030a-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6030a-339">UDP/SRTP</span></span> | <span data-ttu-id="6030a-340">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6030a-340">Media Processor</span></span> | <span data-ttu-id="6030a-341">Sbc</span><span class="sxs-lookup"><span data-stu-id="6030a-341">SBC</span></span> | <span data-ttu-id="6030a-342">3478, 3479 и 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="6030a-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="6030a-343">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="6030a-343">Defined on the SBC</span></span> |
| <span data-ttu-id="6030a-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6030a-344">UDP/SRTP</span></span> | <span data-ttu-id="6030a-345">Sbc</span><span class="sxs-lookup"><span data-stu-id="6030a-345">SBC</span></span> | <span data-ttu-id="6030a-346">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6030a-346">Media Processor</span></span> | <span data-ttu-id="6030a-347">Определено в SBC</span><span class="sxs-lookup"><span data-stu-id="6030a-347">Defined on the SBC</span></span> | <span data-ttu-id="6030a-348">3478, 3479 и 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="6030a-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="6030a-349">Настройка отдельных каналов для обхода мультимедиа и обхода без мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6030a-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="6030a-350">Если вы хотите подтвердить функциональность перед переносом всех функций обхода мультимедиа в обход мультимедиа, вы можете создать отдельную магистраль и отдельную политику голосового маршрутирования Online для маршрутирования к каналу обхода мультимедиа и назначения определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="6030a-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="6030a-351">Шаги высокой настройки:</span><span class="sxs-lookup"><span data-stu-id="6030a-351">High-level configuration steps:</span></span>

- <span data-ttu-id="6030a-352">Определите пользователей, которые должны проверить обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="6030a-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="6030a-353">Создайте две отдельные связи с разными FQDNs: одно из них включено для обхода мультимедиа; другой нет.</span><span class="sxs-lookup"><span data-stu-id="6030a-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="6030a-354">Обе стороны указывают на один и тот же SBC.</span><span class="sxs-lookup"><span data-stu-id="6030a-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="6030a-355">Порты для сигнального сигнала TLS SIP должны быть другими.</span><span class="sxs-lookup"><span data-stu-id="6030a-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="6030a-356">Порты мультимедиа должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="6030a-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="6030a-357">Создайте политику маршрутирования голосовой связи в Интернете и назначьте канал обхода мультимедиа соответствующим маршрутам, связанным с использованием этой политики через ТСТС.</span><span class="sxs-lookup"><span data-stu-id="6030a-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="6030a-358">Назначьте новую политику маршрутирования голосовой почты в Интернете пользователям, для проверки обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="6030a-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="6030a-359">Пример ниже иллюстрирует эту логику.</span><span class="sxs-lookup"><span data-stu-id="6030a-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="6030a-360">Набор пользователей</span><span class="sxs-lookup"><span data-stu-id="6030a-360">Set of users</span></span> | <span data-ttu-id="6030a-361">Количество пользователей</span><span class="sxs-lookup"><span data-stu-id="6030a-361">Number of users</span></span> | <span data-ttu-id="6030a-362">FQDN", присвоенное в OVRP</span><span class="sxs-lookup"><span data-stu-id="6030a-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="6030a-363">Включен обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6030a-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="6030a-364">Пользователи с обойденной службой без мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6030a-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="6030a-365">980</span><span class="sxs-lookup"><span data-stu-id="6030a-365">980</span></span> | <span data-ttu-id="6030a-366">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="6030a-366">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="6030a-367">false</span><span class="sxs-lookup"><span data-stu-id="6030a-367">false</span></span> |
<span data-ttu-id="6030a-368">Пользователи с обводом мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6030a-368">Users with media bypass trunk</span></span> | <span data-ttu-id="6030a-369">20</span><span class="sxs-lookup"><span data-stu-id="6030a-369">20</span></span> | <span data-ttu-id="6030a-370">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="6030a-370">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="6030a-371">true</span><span class="sxs-lookup"><span data-stu-id="6030a-371">true</span></span> | 

<span data-ttu-id="6030a-372">Обе связи могут указать на один и тот же SBC с одинаковым общедоступным IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="6030a-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="6030a-373">Сигнальные порты TLS на SBC должны быть другими, как показано на приведенной ниже схеме.</span><span class="sxs-lookup"><span data-stu-id="6030a-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="6030a-374">Обратите внимание, что сертификат должен поддерживать обе стороны.</span><span class="sxs-lookup"><span data-stu-id="6030a-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="6030a-375">В САН у вас должны быть два имена **(sbc1.contoso.com** и **sbc2.contoso.com**) или поддиз.сертификат.</span><span class="sxs-lookup"><span data-stu-id="6030a-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6030a-376">![Обе связи могут указать на один и тот же SBC с одинаковым общедоступным IP-адресом](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="6030a-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="6030a-377">Сведения о настройке двух телефонов на одном ИТ-сайте см. в документации поставщика SBC:</span><span class="sxs-lookup"><span data-stu-id="6030a-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="6030a-378">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="6030a-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="6030a-379">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="6030a-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="6030a-380">Документация по развертыванию коммуникаций на ленте</span><span class="sxs-lookup"><span data-stu-id="6030a-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="6030a-381">Документация по развертыванию TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="6030a-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="6030a-382">Клиентские конечные точки, поддерживаемые с обходом мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6030a-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="6030a-383">Обход мультимедиа поддерживается для всех автономных классических клиентов Teams, клиентов Android и iOS и телефонных устройств Teams.</span><span class="sxs-lookup"><span data-stu-id="6030a-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="6030a-384">Для всех остальных конечных точек, которые не поддерживают обход мультимедиа, мы преобразуем звонок в обход, даже если он начался как обходной вызов.</span><span class="sxs-lookup"><span data-stu-id="6030a-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="6030a-385">Это происходит автоматически и не требует действий от администратора.</span><span class="sxs-lookup"><span data-stu-id="6030a-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="6030a-386">К ним относятся телефоны 3PIP Skype для бизнеса и веб-клиенты Teams, поддерживаюющие прямые маршруты звонков (клиенты На основе WebRTC, работающие в Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="6030a-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="6030a-387">См. также</span><span class="sxs-lookup"><span data-stu-id="6030a-387">See also</span></span>

[<span data-ttu-id="6030a-388">Настройка обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="6030a-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
