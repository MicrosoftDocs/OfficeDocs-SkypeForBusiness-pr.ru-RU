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
ms.openlocfilehash: bbd31a62bf6ebcd481a3cdafeabaf29bb4767f2d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115597"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="5ce91-103">Планирование обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="5ce91-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="5ce91-104">Обход мультимедиа с прямой маршрутией</span><span class="sxs-lookup"><span data-stu-id="5ce91-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="5ce91-105">Обход мультимедиа позволяет сократить путь трафика мультимедиа и сократить количество переходов для улучшения производительности.</span><span class="sxs-lookup"><span data-stu-id="5ce91-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="5ce91-106">При обходе мультимедиа между контроллером границы сеанса (SBC) и клиентом хранятся мультимедиа, а не через телефонную систему Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5ce91-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="5ce91-107">Чтобы настроить обход мультимедиа, SBC и клиент должны быть в одном расположении или в одной сети.</span><span class="sxs-lookup"><span data-stu-id="5ce91-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="5ce91-108">Вы можете настроить обход мультимедиа для каждого SBC с помощью команды **Set-CSOnlinePSTNGateway,** для параметра **-MediaBypass** задано true или false.</span><span class="sxs-lookup"><span data-stu-id="5ce91-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="5ce91-109">Если включить обход мультимедиа, это не означает, что весь трафик мультимедиа будет оставаться в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="5ce91-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="5ce91-110">В этой статье описан поток зовов в разных сценариях.</span><span class="sxs-lookup"><span data-stu-id="5ce91-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="5ce91-111">На рисунках ниже показано, чем отличается поток вызовов как с обходом мультимедиа, так и без него.</span><span class="sxs-lookup"><span data-stu-id="5ce91-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="5ce91-112">Без обхода мультимедиа, когда клиент совершает или принимает звонок, сигнальный и поток мультимедиа между SBC, телефонной системой Майкрософт и клиентом Teams, как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="5ce91-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ce91-113">![Сигнальный поток и поток мультимедиа без обхода мультимедиа](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="5ce91-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="5ce91-114">Однако предположим, что пользователь находится в том же здании или в сети, что и УАЦ.</span><span class="sxs-lookup"><span data-stu-id="5ce91-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="5ce91-115">Предположим, например, что пользователь, который находится в здании в Москве, звонит пользователю ННР:</span><span class="sxs-lookup"><span data-stu-id="5ce91-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="5ce91-116">**Без обхода** мультимедиа мультимедиа будут переходить через Дублин или Майкрософт (где развернуты центр обработки данных Майкрософт) и обратно в SBC в Facebook.</span><span class="sxs-lookup"><span data-stu-id="5ce91-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="5ce91-117">Центр обработки данных в Европе выбран, так как он находится в Европе, а корпорация Майкрософт использует ближайший к нему центр.</span><span class="sxs-lookup"><span data-stu-id="5ce91-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="5ce91-118">Хотя этот подход не влияет на качество зовов из-за оптимизации потока трафика в сетях Майкрософт в большинстве географических регионах, он имеет ненужный цикл.</span><span class="sxs-lookup"><span data-stu-id="5ce91-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="5ce91-119">**При обходе** мультимедиа хранятся непосредственно между пользователем Teams и SBC, как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="5ce91-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="5ce91-120">![Сигнальный поток и поток мультимедиа с обходом мультимедиа](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="5ce91-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="5ce91-121">Обход мультимедиа использует протоколы под названием "Интерактивная установка подключения (ICE) на клиенте Teams и ICE lite на SBC."</span><span class="sxs-lookup"><span data-stu-id="5ce91-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="5ce91-122">Эти протоколы обеспечивают прямую маршрутику, чтобы использовать самый прямой путь к мультимедиа для обеспечения оптимального качества.</span><span class="sxs-lookup"><span data-stu-id="5ce91-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="5ce91-123">ICE и ICE Lite — это стандарты WebRTC.</span><span class="sxs-lookup"><span data-stu-id="5ce91-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="5ce91-124">Подробные сведения об этих протоколах см. в RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="5ce91-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="5ce91-125">Планирование потока вызовов и брандмауэра</span><span class="sxs-lookup"><span data-stu-id="5ce91-125">Call flow and firewall planning</span></span>

<span data-ttu-id="5ce91-126">Планирование потока присоединения к звонкам и брандмауэра зависит от того, есть ли у пользователя прямой доступ к общедоступным IP-адресам SBC и находится ли пользователь внутри сети или за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="5ce91-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="5ce91-127">Поток присоединения к звонкам, если у пользователя есть прямой доступ к общедоступным IP-адресу SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="5ce91-128">Если у пользователя есть прямой доступ к общедоступным IP-адресу SBC, поток присоединения будет следующим:</span><span class="sxs-lookup"><span data-stu-id="5ce91-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="5ce91-129">Для обхода мультимедиа клиент Teams должен иметь доступ к общедоступным IP-адресам SBC даже из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="5ce91-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="5ce91-130">Если прямая мультимедиа не требуется, они могут передаются через ретрансляторы транспорта.</span><span class="sxs-lookup"><span data-stu-id="5ce91-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="5ce91-131">Это рекомендуемое решение, если пользователь находится в том же здании или сети, что и SBC, и удалить компоненты Microsoft Cloud из пути мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="5ce91-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="5ce91-132">Сигнальный сигнал всегда проходит через облако Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5ce91-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="5ce91-133">На следующей схеме показан поток зовов, когда включен обход мультимедиа, клиент является внутренним, а клиент может связаться с общедоступным IP-адресом SBC (прямой мультимедиа):</span><span class="sxs-lookup"><span data-stu-id="5ce91-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="5ce91-134">Стрелки и числимые значения путей соответствуют потокам вызовов [Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="5ce91-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="5ce91-135">Сигнальный трафик SIP всегда проходит по путям 4 и 4' (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="5ce91-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="5ce91-136">Media stays local and takes path 5b.</span><span class="sxs-lookup"><span data-stu-id="5ce91-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ce91-137">![Поток зовов с включенным обходом мультимедиа, клиент внутренний](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="5ce91-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="5ce91-138">Поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресу SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="5ce91-139">Ниже описан поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресу SBC.</span><span class="sxs-lookup"><span data-stu-id="5ce91-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="5ce91-140">Предположим, пользователь является внешним, и администратор клиента решил не открывать общедоступный IP-адрес SBC для всех пользователей в Интернете, а только для Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="5ce91-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="5ce91-141">Внутренние компоненты трафика могут перетекать через ретрансляторы транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="5ce91-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="5ce91-142">Примите во внимание следующее:</span><span class="sxs-lookup"><span data-stu-id="5ce91-142">Consider the following:</span></span>

- <span data-ttu-id="5ce91-143">Используются ретрансляторы транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="5ce91-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="5ce91-144">Для обхода мультимедиа Майкрософт использует версию ретрансляторов транспорта, которая требует открытия портов от 50 000 до 59 999 между ретрансляторами транспорта Teams и SBC (в будущем мы планируем перейти на версию, которая требует только 3478 и 3479 портов).</span><span class="sxs-lookup"><span data-stu-id="5ce91-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="5ce91-145">На следующей схеме показан поток зовов, когда включен обход мультимедиа, клиент является внешним и клиент не может связаться с общедоступным IP-адресом граничного контроллера сеанса (мультимедиа ретранслются ретранслятором транспорта Teams).</span><span class="sxs-lookup"><span data-stu-id="5ce91-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="5ce91-146">Стрелки и числимые значения путей соответствуют потокам вызовов [Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="5ce91-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="5ce91-147">Media is relayed through paths 3, 3', 4 and 4'</span><span class="sxs-lookup"><span data-stu-id="5ce91-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ce91-148">![Отображает поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресам SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="5ce91-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="5ce91-149">Поток вызовов, если пользователь находится за пределами сети и имеет доступ к общедоступным IP-адресам SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="5ce91-150">Такая конфигурация не рекомендуется, так как она не имеет преимуществ в ретрансляторах транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="5ce91-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="5ce91-151">Вместо этого следует рассмотреть предыдущий сценарий, в котором у пользователя нет доступа к общедоступным IP-адресу SBC.</span><span class="sxs-lookup"><span data-stu-id="5ce91-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="5ce91-152">На следующей схеме показан поток зовов, когда включен обход мультимедиа, клиент является внешним, а клиент может связаться с общедоступным IP-адресом SBC (прямой мультимедиа).</span><span class="sxs-lookup"><span data-stu-id="5ce91-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="5ce91-153">Стрелки и числимые значения путей соответствуют статье о потоках вызовов [Microsoft Teams.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="5ce91-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="5ce91-154">Сигнальный трафик SIP всегда проходит по путям 3 и 3' (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="5ce91-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="5ce91-155">Потоки мультимедиа, использующие путь 2.</span><span class="sxs-lookup"><span data-stu-id="5ce91-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ce91-156">![Отображает поток присоединения к звонкам, если у пользователя нет доступа к общедоступным IP-адресам SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="5ce91-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="5ce91-157">Использование процессоров мультимедиа и ретрансляторов транспорта</span><span class="sxs-lookup"><span data-stu-id="5ce91-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="5ce91-158">В Microsoft Cloud есть два компонента, которые могут быть на пути трафика мультимедиа: процессоры мультимедиа и ретрансляторы транспорта.</span><span class="sxs-lookup"><span data-stu-id="5ce91-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="5ce91-159">Процессор мультимедиа — это общедоступный компонент, который обрабатывает мультимедиа в случаях без обхода и обрабатывает мультимедиа для голосовых приложений.</span><span class="sxs-lookup"><span data-stu-id="5ce91-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="5ce91-160">Процессоры мультимедиа всегда находятся в пути для конечных пользователей, но никогда не находятся в пути для обходных звонков.</span><span class="sxs-lookup"><span data-stu-id="5ce91-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="5ce91-161">Процессоры мультимедиа всегда находятся на пути для всех голосовых приложений, таких как "Парк вызовов", "Автосекретарь организации" и "Очереди вызовов".</span><span class="sxs-lookup"><span data-stu-id="5ce91-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="5ce91-162">Ретранслятор транспорта используется для подключения к ближайшей службе транспорта для отправки трафика в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="5ce91-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="5ce91-163">В зависимости от того, где находится пользователь и как настроена сеть, ретрансляторы транспорта могут не оказаться в пути для обходных звонков: от пользователей или от их маршрутов до конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5ce91-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="5ce91-164">На следующей схеме показаны два потока вызова: один с включенным обходом мультимедиа, а второй с отключенным обходом мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="5ce91-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="5ce91-165">Обратите внимание на то, что схема только иллюстрирует трафик, направляющийся с конечных пользователей или направляющийся в него.</span><span class="sxs-lookup"><span data-stu-id="5ce91-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="5ce91-166">Контроллер мультимедиа — это микрослужба в Azure, которая назначает процессоры мультимедиа и создает предложения протокола SDP.</span><span class="sxs-lookup"><span data-stu-id="5ce91-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="5ce91-167">Прокси-сервер SIP — это компонент, который преобразует сигнал HTTP REST, используемый в Teams, в SIP.</span><span class="sxs-lookup"><span data-stu-id="5ce91-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ce91-168">![Потоки вызовов с включенным и отключенным обходом мультимедиа](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="5ce91-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="5ce91-169">В таблице ниже приведена разница между процессорами мультимедиа и ретрансляторами транспорта.</span><span class="sxs-lookup"><span data-stu-id="5ce91-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="5ce91-170">Процессоры мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5ce91-170">Media Processors</span></span> | <span data-ttu-id="5ce91-171">Transport Relays</span><span class="sxs-lookup"><span data-stu-id="5ce91-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="5ce91-172">В пути мультимедиа для вызовов без обхода для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="5ce91-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="5ce91-173">Всегда</span><span class="sxs-lookup"><span data-stu-id="5ce91-173">Always</span></span> | <span data-ttu-id="5ce91-174">Если клиенту не удается напрямую связаться с медиапереработчиком</span><span class="sxs-lookup"><span data-stu-id="5ce91-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="5ce91-175">В пути мультимедиа для обойденных звонков для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="5ce91-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="5ce91-176">Никогда</span><span class="sxs-lookup"><span data-stu-id="5ce91-176">Never</span></span> | <span data-ttu-id="5ce91-177">Если клиенту не удается связаться с SBC по адресу общего IP-адреса</span><span class="sxs-lookup"><span data-stu-id="5ce91-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="5ce91-178">В пути мультимедиа для голосовых приложений</span><span class="sxs-lookup"><span data-stu-id="5ce91-178">In media path for voice applications</span></span> | <span data-ttu-id="5ce91-179">Всегда</span><span class="sxs-lookup"><span data-stu-id="5ce91-179">Always</span></span> | <span data-ttu-id="5ce91-180">Никогда</span><span class="sxs-lookup"><span data-stu-id="5ce91-180">Never</span></span> | 
<span data-ttu-id="5ce91-181">Может делать транскодинг (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="5ce91-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="5ce91-182">Да</span><span class="sxs-lookup"><span data-stu-id="5ce91-182">Yes</span></span> | <span data-ttu-id="5ce91-183">Нет, только ретрансляции звука между конечными точками</span><span class="sxs-lookup"><span data-stu-id="5ce91-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="5ce91-184">Количество экземпляров по всему миру и его местонахождение</span><span class="sxs-lookup"><span data-stu-id="5ce91-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="5ce91-185">10 итогов: 2 в восточной и западной части США; 2 в Ирландии и Ирландии; 2 в Гонконге и Сингапуре; 2 в Японии; 2 в Восточной и Юго-Восточной Австралии</span><span class="sxs-lookup"><span data-stu-id="5ce91-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="5ce91-186">Несколько</span><span class="sxs-lookup"><span data-stu-id="5ce91-186">Multiple</span></span>

<span data-ttu-id="5ce91-187">Диапазоны IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="5ce91-187">The IP ranges are:</span></span>
- <span data-ttu-id="5ce91-188">52.112.0.0/14 (IP-адреса от 52.112.0.1 до 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="5ce91-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="5ce91-189">52.120.0.0/14 (IP-адреса от 52.120.0.1 до 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="5ce91-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="5ce91-190">\* Объяснение транскодинга:</span><span class="sxs-lookup"><span data-stu-id="5ce91-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="5ce91-191">Процессор мультимедиа — это B2BUA, то есть он может изменить кодеки (например, SILK из клиента Teams в MP и G.711 между MP и SBC).</span><span class="sxs-lookup"><span data-stu-id="5ce91-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="5ce91-192">Ретрансляторы транспорта не являются B2BUA, то есть кодек никогда не меняется между клиентом и SBC, даже если трафик передается через ретрансляции.</span><span class="sxs-lookup"><span data-stu-id="5ce91-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="5ce91-193">Использование процессоров мультимедиа Teams, если для настройки обхода мультимедиа настроена возможность обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5ce91-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="5ce91-194">Процессоры мультимедиа Teams всегда вставляются в медиапереклады в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="5ce91-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="5ce91-195">Звонок перенается из 1:1 в групповой звонок</span><span class="sxs-lookup"><span data-stu-id="5ce91-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="5ce91-196">Звонок идет федераированному пользователю Teams</span><span class="sxs-lookup"><span data-stu-id="5ce91-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="5ce91-197">Переадправление или переадправление звонка пользователю Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5ce91-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="5ce91-198">Убедитесь, что у вашего SBC есть доступ к процессорам мультимедиа и диапазонам ретрансляторов транспорта, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="5ce91-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="5ce91-199">Сигнальный SIP: FQDNs</span><span class="sxs-lookup"><span data-stu-id="5ce91-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="5ce91-200">Для сигнального управления SIP требования к FQDN и брандмауэру одинаковы, как и для дел, не влияющих на обход.</span><span class="sxs-lookup"><span data-stu-id="5ce91-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="5ce91-201">Прямая маршрутия предоставляется в следующих средах Microsoft 365 или Office 365:</span><span class="sxs-lookup"><span data-stu-id="5ce91-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="5ce91-202">Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="5ce91-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="5ce91-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="5ce91-203">Office 365 GCC</span></span>
- <span data-ttu-id="5ce91-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="5ce91-204">Office 365 GCC High</span></span>
- <span data-ttu-id="5ce91-205">Office 365 DoD Подробнее об средах [Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) и государственных органов США, таких как GCC, GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="5ce91-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5ce91-206">Среды Microsoft 365, Office 365 и GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="5ce91-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="5ce91-207">Ниже точки соединения для прямой маршрутии связаны с тремя FQDNs.</span><span class="sxs-lookup"><span data-stu-id="5ce91-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="5ce91-208">**sip.pstnhub.microsoft.com** — глобальное FQDN — необходимо сначала пройти процесс.</span><span class="sxs-lookup"><span data-stu-id="5ce91-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="5ce91-209">Когда SBC отправляет запрос на устранение этого имени, DNS-серверы Microsoft Azure возвращают IP-адрес, указывающий на основной центр обработки данных Azure, который назначен SBC.</span><span class="sxs-lookup"><span data-stu-id="5ce91-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="5ce91-210">Назначение основано на метриках производительности центра обработки данных и географической близости к SBC.</span><span class="sxs-lookup"><span data-stu-id="5ce91-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="5ce91-211">Возвращаемый IP-адрес соответствует основному FQDN.</span><span class="sxs-lookup"><span data-stu-id="5ce91-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="5ce91-212">**sip2.pstnhub.microsoft.com** — дополнительное FQDN — географически сопоставить со вторым приоритетом регион.</span><span class="sxs-lookup"><span data-stu-id="5ce91-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="5ce91-213">**sip3.pstnhub.microsoft.com** — tertiary FQDN — географически сопоставить с третьим приоритетом регион.</span><span class="sxs-lookup"><span data-stu-id="5ce91-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="5ce91-214">Эти три FQDNs необходимо разместить, чтобы:</span><span class="sxs-lookup"><span data-stu-id="5ce91-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="5ce91-215">Обеспечение оптимальной работы (менее загружена и ближе всего к центру обработки данных SBC, назначенного с помощью запроса первого FQDN).</span><span class="sxs-lookup"><span data-stu-id="5ce91-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="5ce91-216">Отбой в случае подключения с SBC к центру обработки данных, который имеет временную проблему.</span><span class="sxs-lookup"><span data-stu-id="5ce91-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="5ce91-217">Дополнительные сведения см. ниже в механизме failover.</span><span class="sxs-lookup"><span data-stu-id="5ce91-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="5ce91-218">FQDNs sip.pstnhub.microsoft.com, **sip2.pstnhub.microsoft.com** **и** sip3.pstnhub.microsoft.com будут разрешены на один из следующих IP-адресов: </span><span class="sxs-lookup"><span data-stu-id="5ce91-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="5ce91-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="5ce91-219">52.114.148.0</span></span>
- <span data-ttu-id="5ce91-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="5ce91-220">52.114.132.46</span></span>
- <span data-ttu-id="5ce91-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="5ce91-221">52.114.16.74</span></span>
- <span data-ttu-id="5ce91-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="5ce91-222">52.114.20.29</span></span>
- <span data-ttu-id="5ce91-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="5ce91-223">52.114.75.24</span></span>
- <span data-ttu-id="5ce91-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="5ce91-224">52.114.76.76</span></span>
- <span data-ttu-id="5ce91-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="5ce91-225">52.114.7.24</span></span>
- <span data-ttu-id="5ce91-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="5ce91-226">52.114.14.70</span></span>

<span data-ttu-id="5ce91-227">Для сигнального трафика необходимо открыть в брандмауэре порты для всех этих IP-адресов, чтобы разрешить входящий и исходяющий трафик, который будет входящие и исходяющие сообщения с адресов для сигнального трафика.</span><span class="sxs-lookup"><span data-stu-id="5ce91-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="5ce91-228">Если брандмауэр поддерживает имена DNS,  доменные sip-all.pstnhub.microsoft.com будут разрешать их все IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="5ce91-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5ce91-229">Среда DoD "GCC" в Office 365</span><span class="sxs-lookup"><span data-stu-id="5ce91-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="5ce91-230">Точка соединения для прямой маршрутки имеет следующее FQDN:</span><span class="sxs-lookup"><span data-stu-id="5ce91-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="5ce91-231">**sip.pstnhub.dod.teams.microsoft.us** — глобальное FQDN.</span><span class="sxs-lookup"><span data-stu-id="5ce91-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="5ce91-232">Так как среда DoD Office 365 существует только в центрах обработки данных в США, дополнительные и триадные FQDNs не существуют.</span><span class="sxs-lookup"><span data-stu-id="5ce91-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="5ce91-233">FQDNs — sip.pstnhub.dod.teams.microsoft.us будут разрешены на один из следующих IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="5ce91-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="5ce91-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="5ce91-234">52.127.64.33</span></span>
- <span data-ttu-id="5ce91-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="5ce91-235">52.127.68.34</span></span>

<span data-ttu-id="5ce91-236">Для сигнального трафика необходимо открыть в брандмауэре порты для всех этих IP-адресов, чтобы разрешить входящий и исходяющий трафик, который будет входящие и исходяющие сообщения с адресов для сигнального трафика.</span><span class="sxs-lookup"><span data-stu-id="5ce91-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="5ce91-237">Если брандмауэр поддерживает имена DNS, доменные sip.pstnhub.dod.teams.microsoft.us будут разрешать их все IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="5ce91-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5ce91-238">Среда Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="5ce91-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="5ce91-239">Точка соединения для прямой маршрутки имеет следующее FQDN:</span><span class="sxs-lookup"><span data-stu-id="5ce91-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="5ce91-240">**sip.pstnhub.gov.teams.microsoft.us** — глобальное FQDN.</span><span class="sxs-lookup"><span data-stu-id="5ce91-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="5ce91-241">Так как среда GCC High существует только в центрах обработки данных в США, дополнительные и дополнительные FQDNs не существуют.</span><span class="sxs-lookup"><span data-stu-id="5ce91-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="5ce91-242">FQDNs — sip.pstnhub.gov.teams.microsoft.us будут разрешены на один из следующих IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="5ce91-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="5ce91-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="5ce91-243">52.127.88.59</span></span>
- <span data-ttu-id="5ce91-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="5ce91-244">52.127.92.64</span></span>

<span data-ttu-id="5ce91-245">Для сигнального трафика необходимо открыть в брандмауэре порты для всех этих IP-адресов, чтобы разрешить входящий и исходяющий трафик, который будет входящие и исходяющие сообщения с адресов для сигнального трафика.</span><span class="sxs-lookup"><span data-stu-id="5ce91-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="5ce91-246">Если брандмауэр поддерживает имена DNS, доменные sip.pstnhub.gov.teams.microsoft.us будут разрешать их все IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="5ce91-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="5ce91-247">Сигнальный SIP: порты</span><span class="sxs-lookup"><span data-stu-id="5ce91-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="5ce91-248">Требования к переносу одинаковы для всех сред Office 365, в которых предлагается прямая маршрутия:</span><span class="sxs-lookup"><span data-stu-id="5ce91-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="5ce91-249">Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="5ce91-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="5ce91-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="5ce91-250">Office 365 GCC</span></span>
- <span data-ttu-id="5ce91-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="5ce91-251">Office 365 GCC High</span></span>
- <span data-ttu-id="5ce91-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="5ce91-252">Office 365 DoD</span></span>

<span data-ttu-id="5ce91-253">Необходимо использовать следующие порты:</span><span class="sxs-lookup"><span data-stu-id="5ce91-253">You must use the following ports:</span></span>

| <span data-ttu-id="5ce91-254">Трафик</span><span class="sxs-lookup"><span data-stu-id="5ce91-254">Traffic</span></span> | <span data-ttu-id="5ce91-255">От</span><span class="sxs-lookup"><span data-stu-id="5ce91-255">From</span></span> | <span data-ttu-id="5ce91-256">До</span><span class="sxs-lookup"><span data-stu-id="5ce91-256">To</span></span> | <span data-ttu-id="5ce91-257">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="5ce91-257">Source port</span></span> | <span data-ttu-id="5ce91-258">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="5ce91-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5ce91-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="5ce91-259">SIP/TLS</span></span>| <span data-ttu-id="5ce91-260">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="5ce91-260">SIP Proxy</span></span> | <span data-ttu-id="5ce91-261">SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-261">SBC</span></span> | <span data-ttu-id="5ce91-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="5ce91-262">1024 - 65535</span></span> | <span data-ttu-id="5ce91-263">Определяется в SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-263">Defined on the SBC</span></span> |
| <span data-ttu-id="5ce91-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="5ce91-264">SIP/TLS</span></span> | <span data-ttu-id="5ce91-265">SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-265">SBC</span></span> | <span data-ttu-id="5ce91-266">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="5ce91-266">SIP Proxy</span></span> | <span data-ttu-id="5ce91-267">Определяется в SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-267">Defined on the SBC</span></span> | <span data-ttu-id="5ce91-268">5061</span><span class="sxs-lookup"><span data-stu-id="5ce91-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="5ce91-269">Трафик мультимедиа: диапазоны IP-адресов и портов</span><span class="sxs-lookup"><span data-stu-id="5ce91-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="5ce91-270">Трафик мультимедиа передается между клиентом SBC и Teams, если доступно прямое подключение, или через ретрансляторы транспорта Teams, если клиент не может связаться с SBC, используя общедоступный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="5ce91-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="5ce91-271">Требования для прямого трафика мультимедиа (между клиентом Teams и SBC)</span><span class="sxs-lookup"><span data-stu-id="5ce91-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="5ce91-272">У клиента должен быть доступ к указанным портам (см. таблицу) на общедоступный IP-адрес SBC.</span><span class="sxs-lookup"><span data-stu-id="5ce91-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="5ce91-273">Примечание. Если клиент находится во внутренней сети, потоки мультимедиа перетекают в общедоступный IP-адрес SBC.</span><span class="sxs-lookup"><span data-stu-id="5ce91-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="5ce91-274">Вы можете настроить закрепление ветвей на устройстве NAT, чтобы трафик никогда не покидает оборудование корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="5ce91-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="5ce91-275">Трафик</span><span class="sxs-lookup"><span data-stu-id="5ce91-275">Traffic</span></span> | <span data-ttu-id="5ce91-276">От</span><span class="sxs-lookup"><span data-stu-id="5ce91-276">From</span></span> | <span data-ttu-id="5ce91-277">До</span><span class="sxs-lookup"><span data-stu-id="5ce91-277">To</span></span> | <span data-ttu-id="5ce91-278">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="5ce91-278">Source port</span></span> | <span data-ttu-id="5ce91-279">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="5ce91-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5ce91-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ce91-280">UDP/SRTP</span></span> | <span data-ttu-id="5ce91-281">Клиент</span><span class="sxs-lookup"><span data-stu-id="5ce91-281">Client</span></span> | <span data-ttu-id="5ce91-282">SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-282">SBC</span></span> | <span data-ttu-id="5ce91-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="5ce91-283">50 000 – 50 019</span></span>  | <span data-ttu-id="5ce91-284">Определяется в SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-284">Defined on the SBC</span></span> |
| <span data-ttu-id="5ce91-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ce91-285">UDP/SRTP</span></span> | <span data-ttu-id="5ce91-286">SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-286">SBC</span></span> | <span data-ttu-id="5ce91-287">Клиент</span><span class="sxs-lookup"><span data-stu-id="5ce91-287">Client</span></span> | <span data-ttu-id="5ce91-288">Определяется в SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-288">Defined on the SBC</span></span> | <span data-ttu-id="5ce91-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="5ce91-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="5ce91-290">Если у вас есть сетевое устройство, которое преобразует исходные порты клиента, убедитесь, что открыты переведенные порты между сетевым оборудованием и SBC.</span><span class="sxs-lookup"><span data-stu-id="5ce91-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="5ce91-291">Требования для использования ретрансляторов транспорта</span><span class="sxs-lookup"><span data-stu-id="5ce91-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="5ce91-292">Ретрансляторы транспорта находятся в том же диапазоне, что и процессоры мультимедиа (для случаев без обхода):</span><span class="sxs-lookup"><span data-stu-id="5ce91-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5ce91-293">Среды Microsoft 365, Office 365 и GCC Office 365</span><span class="sxs-lookup"><span data-stu-id="5ce91-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="5ce91-294">52.112.0.0 /14 (IP-адреса от 52.112.0.1 до 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="5ce91-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5ce91-295">Среда DoD "GCC" в Office 365</span><span class="sxs-lookup"><span data-stu-id="5ce91-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="5ce91-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5ce91-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5ce91-297">Среда Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="5ce91-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="5ce91-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="5ce91-298">52.127.88.0/21</span></span>


<span data-ttu-id="5ce91-299">Диапазон портов ретрансляторов транспорта Teams (применимо для всех сред) показан в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="5ce91-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="5ce91-300">Трафик</span><span class="sxs-lookup"><span data-stu-id="5ce91-300">Traffic</span></span> | <span data-ttu-id="5ce91-301">От</span><span class="sxs-lookup"><span data-stu-id="5ce91-301">From</span></span> | <span data-ttu-id="5ce91-302">До</span><span class="sxs-lookup"><span data-stu-id="5ce91-302">To</span></span> | <span data-ttu-id="5ce91-303">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="5ce91-303">Source port</span></span> | <span data-ttu-id="5ce91-304">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="5ce91-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5ce91-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ce91-305">UDP/SRTP</span></span> | <span data-ttu-id="5ce91-306">Transport Relay</span><span class="sxs-lookup"><span data-stu-id="5ce91-306">Transport Relay</span></span> | <span data-ttu-id="5ce91-307">SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-307">SBC</span></span> | <span data-ttu-id="5ce91-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="5ce91-308">50 000 -59 999</span></span>    | <span data-ttu-id="5ce91-309">Определяется в SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-309">Defined on the SBC</span></span> |
| <span data-ttu-id="5ce91-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ce91-310">UDP/SRTP</span></span> | <span data-ttu-id="5ce91-311">SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-311">SBC</span></span> | <span data-ttu-id="5ce91-312">Transport Relay</span><span class="sxs-lookup"><span data-stu-id="5ce91-312">Transport Relay</span></span> | <span data-ttu-id="5ce91-313">Определяется в SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-313">Defined on the SBC</span></span> | <span data-ttu-id="5ce91-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="5ce91-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="5ce91-315">Корпорация Майкрософт рекомендует по крайней мере два порта для одного одновременного звонка на SBC.</span><span class="sxs-lookup"><span data-stu-id="5ce91-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="5ce91-316">Так как у корпорации Майкрософт есть две версии ретрансляторов транспорта, требуются следующие:</span><span class="sxs-lookup"><span data-stu-id="5ce91-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="5ce91-317">v4, который может работать только с диапазоном от 50 000 до 59 999</span><span class="sxs-lookup"><span data-stu-id="5ce91-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="5ce91-318">v6, который работает с портами 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="5ce91-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="5ce91-319">В настоящее время обход мультимедиа поддерживает только 4-ю версию ретрансляторов транспорта.</span><span class="sxs-lookup"><span data-stu-id="5ce91-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="5ce91-320">В будущем мы введем поддержку v6.</span><span class="sxs-lookup"><span data-stu-id="5ce91-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="5ce91-321">Для перехода необходимо открыть порты 3478 и 3479.</span><span class="sxs-lookup"><span data-stu-id="5ce91-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="5ce91-322">Если корпорация Майкрософт введет поддержку ретрансляторов транспорта v6 с помощью обхода мультимедиа, вам не придется перенастроять сетевое оборудование или SBCs.</span><span class="sxs-lookup"><span data-stu-id="5ce91-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="5ce91-323">Требования для использования процессоров мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5ce91-323">Requirements for using media processors</span></span>

<span data-ttu-id="5ce91-324">Процессоры мультимедиа всегда находятся в пути мультимедиа для голосовых приложений и веб-клиентов (например, клиентов Teams в Edge или Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="5ce91-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="5ce91-325">Требования одинаковы для настройки без обхода.</span><span class="sxs-lookup"><span data-stu-id="5ce91-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="5ce91-326">Диапазон IP-адресов для трафика мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="5ce91-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5ce91-327">Среды Office 365 и Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="5ce91-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="5ce91-328">52.112.0.0 /14 (IP-адреса от 52.112.0.1 до 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="5ce91-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5ce91-329">Среда DoD "GCC" в Office 365</span><span class="sxs-lookup"><span data-stu-id="5ce91-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="5ce91-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5ce91-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5ce91-331">Среда Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="5ce91-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="5ce91-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="5ce91-332">52.127.88.0/21</span></span>

<span data-ttu-id="5ce91-333">Диапазон портов процессоров мультимедиа (применимо для всех сред) отображается в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="5ce91-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="5ce91-334">Трафик</span><span class="sxs-lookup"><span data-stu-id="5ce91-334">Traffic</span></span> | <span data-ttu-id="5ce91-335">От</span><span class="sxs-lookup"><span data-stu-id="5ce91-335">From</span></span> | <span data-ttu-id="5ce91-336">До</span><span class="sxs-lookup"><span data-stu-id="5ce91-336">To</span></span> | <span data-ttu-id="5ce91-337">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="5ce91-337">Source port</span></span> | <span data-ttu-id="5ce91-338">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="5ce91-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5ce91-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ce91-339">UDP/SRTP</span></span> | <span data-ttu-id="5ce91-340">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5ce91-340">Media Processor</span></span> | <span data-ttu-id="5ce91-341">SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-341">SBC</span></span> | <span data-ttu-id="5ce91-342">3478, 3479 и 49 152–53 247</span><span class="sxs-lookup"><span data-stu-id="5ce91-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="5ce91-343">Определяется в SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-343">Defined on the SBC</span></span> |
| <span data-ttu-id="5ce91-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5ce91-344">UDP/SRTP</span></span> | <span data-ttu-id="5ce91-345">SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-345">SBC</span></span> | <span data-ttu-id="5ce91-346">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5ce91-346">Media Processor</span></span> | <span data-ttu-id="5ce91-347">Определяется в SBC</span><span class="sxs-lookup"><span data-stu-id="5ce91-347">Defined on the SBC</span></span> | <span data-ttu-id="5ce91-348">3478, 3479 и 49 152–53 247</span><span class="sxs-lookup"><span data-stu-id="5ce91-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="5ce91-349">Настройка отдельных магистральных каналов для обхода мультимедиа и обхода без мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5ce91-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="5ce91-350">Если вы хотите подтвердить функциональность перед переносом всех функций обхода мультимедиа в обход мультимедиа, вы можете создать отдельную магистраль и отдельную политику маршрутирования голосовой маршрутии Online, чтобы назначить ее определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="5ce91-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="5ce91-351">Шаги высокой конфигурации:</span><span class="sxs-lookup"><span data-stu-id="5ce91-351">High-level configuration steps:</span></span>

- <span data-ttu-id="5ce91-352">Определите пользователей, которые должны тестировать обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="5ce91-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="5ce91-353">Создание двух отдельных видов связи с разными FQDNs: одно из них включено для обхода мультимедиа; другой не.</span><span class="sxs-lookup"><span data-stu-id="5ce91-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="5ce91-354">Обе ленты указывают на один и тот же SBC.</span><span class="sxs-lookup"><span data-stu-id="5ce91-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="5ce91-355">Порты для сигнального сигнала TLS SIP должны быть другими.</span><span class="sxs-lookup"><span data-stu-id="5ce91-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="5ce91-356">Порты для мультимедиа должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="5ce91-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="5ce91-357">Создайте политику маршрутирования голосовой связи в Интернете и назначьте канал обхода мультимедиа соответствующим маршрутам, связанным с использованием этой политики ТСТС.</span><span class="sxs-lookup"><span data-stu-id="5ce91-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="5ce91-358">Назначьте новую политику маршрутирования голосовой почты Online пользователям, для проверки обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="5ce91-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="5ce91-359">Пример ниже иллюстрирует эту логику.</span><span class="sxs-lookup"><span data-stu-id="5ce91-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="5ce91-360">Набор пользователей</span><span class="sxs-lookup"><span data-stu-id="5ce91-360">Set of users</span></span> | <span data-ttu-id="5ce91-361">Количество пользователей</span><span class="sxs-lookup"><span data-stu-id="5ce91-361">Number of users</span></span> | <span data-ttu-id="5ce91-362">FQDN для магистрали, назначенное в OVRP</span><span class="sxs-lookup"><span data-stu-id="5ce91-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="5ce91-363">Включен обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5ce91-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="5ce91-364">Пользователи с обойденной магистралью без мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5ce91-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="5ce91-365">980</span><span class="sxs-lookup"><span data-stu-id="5ce91-365">980</span></span> | <span data-ttu-id="5ce91-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="5ce91-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="5ce91-367">true</span><span class="sxs-lookup"><span data-stu-id="5ce91-367">true</span></span>
<span data-ttu-id="5ce91-368">Пользователи с обойденной медиауловиной связи</span><span class="sxs-lookup"><span data-stu-id="5ce91-368">Users with media bypass trunk</span></span> | <span data-ttu-id="5ce91-369">20</span><span class="sxs-lookup"><span data-stu-id="5ce91-369">20</span></span> | <span data-ttu-id="5ce91-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="5ce91-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="5ce91-371">false</span><span class="sxs-lookup"><span data-stu-id="5ce91-371">false</span></span> | 

<span data-ttu-id="5ce91-372">Обе связи могут указывают на один и тот же SBC с одинаковым общедоступным IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="5ce91-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="5ce91-373">Сигнальные порты TLS на SBC должны быть другими, как показано на приведенной ниже схеме.</span><span class="sxs-lookup"><span data-stu-id="5ce91-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="5ce91-374">Обратите внимание, что ваш сертификат должен поддерживать обе службы.</span><span class="sxs-lookup"><span data-stu-id="5ce91-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="5ce91-375">В САН у вас должны быть два имена **(sbc1.contoso.com** и **sbc2.contoso.com)** или поддиавный сертификат.</span><span class="sxs-lookup"><span data-stu-id="5ce91-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5ce91-376">![Обе связи могут указать на один и тот же SBC с одинаковым общедоступным IP-адресом](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="5ce91-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="5ce91-377">Сведения о том, как настроить две магистрали на одной телефонной телефонной телефонии, см. в документации вашего поставщика SBC:</span><span class="sxs-lookup"><span data-stu-id="5ce91-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="5ce91-378">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="5ce91-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="5ce91-379">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="5ce91-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="5ce91-380">Документация по развертыванию информационного сообщения на ленте</span><span class="sxs-lookup"><span data-stu-id="5ce91-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="5ce91-381">Документация по развертыванию TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="5ce91-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="5ce91-382">Конечные точки клиента, поддерживаемые обходом мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5ce91-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="5ce91-383">Обход мультимедиа поддерживается для всех автономных классических клиентов Teams, клиентов Android и iOS, а также устройств Teams Phone.</span><span class="sxs-lookup"><span data-stu-id="5ce91-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="5ce91-384">Для всех других конечных точек, которые не поддерживают обход мультимедиа, мы преобразуем звонок в обход, даже если он начался как обходной звонок.</span><span class="sxs-lookup"><span data-stu-id="5ce91-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="5ce91-385">Это происходит автоматически и не требует действий от администратора.</span><span class="sxs-lookup"><span data-stu-id="5ce91-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="5ce91-386">К ним относятся телефоны 3PIP Skype для бизнеса и веб-клиенты Teams, которые поддерживают прямые маршруты звонков (клиенты на основе WebRTC, работающие в Microsoft Edge, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="5ce91-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="5ce91-387">См. также</span><span class="sxs-lookup"><span data-stu-id="5ce91-387">See also</span></span>

[<span data-ttu-id="5ce91-388">Настройка обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="5ce91-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)