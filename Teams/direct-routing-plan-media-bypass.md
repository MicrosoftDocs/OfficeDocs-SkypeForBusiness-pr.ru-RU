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
description: Сведения о том, как планировать обход мультимедиа с помощью прямой маршрутизации на телефонную систему, что позволяет сократить путь к мультимедийному трафику и повысить производительность.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cabbfd62ecc1a86d6e893d8d26ecdbe6cbbe7dbb
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469585"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="19315-103">Планирование обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="19315-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="19315-104">Обход мультимедиа с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="19315-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="19315-105">Обход мультимедиа позволяет сократить путь к мультимедийному трафику и уменьшить число прыжков на пути для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="19315-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="19315-106">При обходе мультимедиа мультимедиа хранится между контроллером границ сеанса (SBC) и клиентом, а не отправкой через телефонную систему Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19315-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="19315-107">Чтобы настроить обход мультимедиа, SBC и клиент должны находиться в одном месте или в сети.</span><span class="sxs-lookup"><span data-stu-id="19315-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="19315-108">Вы можете управлять обходом мультимедиа для каждого SBC с помощью команды **Set-CSOnlinePSTNGateway** с параметром **-MediaBypass** , для которого установлено значение true или false.</span><span class="sxs-lookup"><span data-stu-id="19315-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="19315-109">Если включить обход мультимедиа, это не значит, что весь трафик мультимедиа останется в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="19315-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="19315-110">В этой статье описаны потоки звонков в разных сценариях.</span><span class="sxs-lookup"><span data-stu-id="19315-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="19315-111">На приведенных ниже схемах показано различие в потоке звонков с обходом мультимедиа и без него.</span><span class="sxs-lookup"><span data-stu-id="19315-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="19315-112">При отсутствии пропуска мультимедиа, когда клиент выполняет или получает вызов, как на рисунке, так и на устройстве с интерфейсом SBC, в системе Microsoft Phone и клиенте Teams, как показано на приведенной ниже схеме.</span><span class="sxs-lookup"><span data-stu-id="19315-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19315-113">![Показывает сигнализацию и поток мультимедиа без обхода мультимедиа](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="19315-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="19315-114">Но предположим, что пользователь в той же сборке или сети, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="19315-115">Например, предположим, что пользователь, который входит в состав здания в Frankfurt, осуществляет звонок пользователю PSTN:</span><span class="sxs-lookup"><span data-stu-id="19315-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="19315-116">**Без**обобщения мультимедиа мультимедиа будет перетекать через Амстердам или Дублин (там, где развернут центры обработки данных Майкрософт) и обратно на SBC в Frankfurt.</span><span class="sxs-lookup"><span data-stu-id="19315-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="19315-117">Центр обработки данных в Европе выбран, так как SBC находится в Европе, а Microsoft использует центр обработки данных, ближайший к SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="19315-118">Хотя этот подход не влияет на качество связи в связи с оптимизацией потока трафика в сетях Microsoft в большинстве географических регионов, трафик имеет ненужное зацикливание.</span><span class="sxs-lookup"><span data-stu-id="19315-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="19315-119">**При обходе мультимедиа**мультимедиа сохраняется непосредственно между пользователем Teams и SBC, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="19315-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="19315-120">![Показывает сигнализацию и поток мультимедиа с обходом мультимедиа](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="19315-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="19315-121">Обход мультимедиа использует протоколы, называемые интерактивным подключением (ICE) в клиенте Teams, и Lite на SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="19315-122">Эти протоколы обеспечивают прямую маршрутизацию для использования наиболее подходящих путей к мультимедиа для оптимального качества.</span><span class="sxs-lookup"><span data-stu-id="19315-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="19315-123">ICE и ICE Lite — это WebRTC стандарты.</span><span class="sxs-lookup"><span data-stu-id="19315-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="19315-124">Подробные сведения об этих протоколах можно найти в RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="19315-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="19315-125">Потоки звонков и планирование брандмауэра</span><span class="sxs-lookup"><span data-stu-id="19315-125">Call flow and firewall planning</span></span>

<span data-ttu-id="19315-126">Потоки звонков и планирование в брандмауэре зависят от того, есть ли у пользователя прямой доступ к общедоступному IP-адресу объекта SBC, а также от того, входит ли пользователь в сеть или за ее пределы.</span><span class="sxs-lookup"><span data-stu-id="19315-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="19315-127">Поток звонков, если пользователь имеет прямой доступ к общедоступному IP-адресу объекта SBC</span><span class="sxs-lookup"><span data-stu-id="19315-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="19315-128">Если у пользователя есть прямой доступ к общедоступному IP-адресу объекта SBC, поток вызова выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="19315-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="19315-129">Для обхода мультимедиа клиент Teams должен иметь доступ к общедоступному IP-адресу SBC, даже из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="19315-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="19315-130">Если прямое мультимедиа не требуется, мультимедиа может перетекать через реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="19315-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="19315-131">Это рекомендуемое решение, если пользователь в той же сборке и (или) сети, что и SBC — удаление облачных компонентов Microsoft из пути к носителю.</span><span class="sxs-lookup"><span data-stu-id="19315-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="19315-132">Передача сигналов всегда проходит через Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="19315-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="19315-133">На приведенной ниже схеме показан поток звонков, когда включена поддержка мультимедиа, клиент является внутренним, а клиент может получить доступ к публичному IP-адресу SBC (Direct Media):</span><span class="sxs-lookup"><span data-stu-id="19315-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="19315-134">Стрелки и числовые значения путей в соответствии с [потоками вызовов Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span><span class="sxs-lookup"><span data-stu-id="19315-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="19315-135">Сигнал SIP всегда принимает пути 4 и 4 (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="19315-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="19315-136">Мультимедиа останется на локальном компьютере, и его путь — 5b.</span><span class="sxs-lookup"><span data-stu-id="19315-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19315-137">![Показывает поток звонков с включенным пропуском мультимедиа, клиент является внутренним](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="19315-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="19315-138">Поток звонков, если пользователь не имеет доступа к общедоступному IP-адресу SBC</span><span class="sxs-lookup"><span data-stu-id="19315-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="19315-139">Ниже приведено описание потока вызова, если пользователь не имеет доступа к общедоступному IP-адресу SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="19315-140">Например, предположим, что пользователь является внешним, а администратор клиента решил не открывать общедоступный IP-адрес SBC для всех пользователей в Интернете, но только в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="19315-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="19315-141">Внутренние компоненты трафика могут перетекать через реле транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="19315-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="19315-142">Примите во внимание следующее:</span><span class="sxs-lookup"><span data-stu-id="19315-142">Consider the following:</span></span>

- <span data-ttu-id="19315-143">Используются реле транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="19315-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="19315-144">Для обхода мультимедиа Корпорация Майкрософт использует версию реле транспорта, для которой требуется открыть порты 50 000 для 59 999 между ретранслятором транспорта групп и SBC (в будущем мы планируем переход на версию, для которой требуется только 3478 и 3479).</span><span class="sxs-lookup"><span data-stu-id="19315-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="19315-145">На приведенной ниже схеме показан поток вызова, если включен обход мультимедиа, клиент является внешним, а клиент не может связаться с общедоступным IP-адресом контроллера границ сеанса (поток ретранслируется транспортом транспорта Team Relay).</span><span class="sxs-lookup"><span data-stu-id="19315-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="19315-146">Стрелки и числовые значения путей в соответствии с [потоками вызовов Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span><span class="sxs-lookup"><span data-stu-id="19315-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="19315-147">Мультимедиа ретранслируется с помощью путей 3, 3, 4 и 4.</span><span class="sxs-lookup"><span data-stu-id="19315-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19315-148">![Показывает поток вызова, если пользователь не имеет доступа к общедоступному IP-адресу объекта SBC](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="19315-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="19315-149">Поток звонков, если пользователь находится за пределами сети и имеет доступ к общедоступному IP-адресу SBC</span><span class="sxs-lookup"><span data-stu-id="19315-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="19315-150">Это не рекомендуемая конфигурация, так как она не использует возможности ретрансляции транспорта для Teams.</span><span class="sxs-lookup"><span data-stu-id="19315-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="19315-151">Вместо этого следует рассмотреть предыдущий сценарий, в котором у пользователя нет доступа к общедоступному IP-адресу SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="19315-152">На приведенной ниже схеме показан поток звонков, если включен обход мультимедиа, клиент является внешним, а клиент может получить доступ к общевидимому IP-адресу SBC (Direct Media).</span><span class="sxs-lookup"><span data-stu-id="19315-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="19315-153">Стрелки и числовые значения пути в соответствии со статьей [потоки вызовов Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="19315-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="19315-154">Сигнал SIP всегда принимает пути 3 и 3 (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="19315-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="19315-155">Потоки мультимедиа, использующие путь 2.</span><span class="sxs-lookup"><span data-stu-id="19315-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19315-156">![Показывает поток вызова, если пользователь не имеет доступа к общедоступному IP-адресу объекта SBC](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="19315-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="19315-157">Использование мультимедийных процессоров и реле транспортировки</span><span class="sxs-lookup"><span data-stu-id="19315-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="19315-158">В облаке Microsoft есть два компонента, которые могут находиться в пути к мультимедийному трафику: процессоры мультимедиа и реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="19315-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="19315-159">Процессор мультимедиа — это общедоступный компонент, который обрабатывает мультимедиа в необходных случаях и обрабатывает носители для голосовых приложений.</span><span class="sxs-lookup"><span data-stu-id="19315-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="19315-160">Обработчики мультимедиа всегда находятся в пути для вызовов конечных пользователей, но никогда не в пути к пропускным звонкам.</span><span class="sxs-lookup"><span data-stu-id="19315-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="19315-161">Процессоры мультимедиа всегда находятся в пути для всех голосовых приложений, таких как приостановка звонков, автоматический секретарь Организации и очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="19315-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="19315-162">Транспортный ретранслятор используется для подключения к ближайшей транспортной службе для отправки трафика в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="19315-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="19315-163">Ретрансляция транспорта может быть или не включена в путь для конечных вызовов, в зависимости от того, где находится пользователь и как настроена сеть.</span><span class="sxs-lookup"><span data-stu-id="19315-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="19315-164">На приведенной ниже схеме показаны два потока звонков — один с включенным пропуском мультимедиа, а второй — без отключения мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="19315-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="19315-165">Обратите внимание, что схема показывает только трафик, направленный от конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="19315-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="19315-166">Контроллер мультимедиа — это микрослужба в Azure, которая назначает мультимедийные процессоры и создает предлагаемые протоколы описания сеансов (SDP).</span><span class="sxs-lookup"><span data-stu-id="19315-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="19315-167">Прокси-сервер SIP — компонент, который преобразует сигналы HTTP RESTFUL, используемые в Teams, в SIP.</span><span class="sxs-lookup"><span data-stu-id="19315-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19315-168">![Показывает потоки звонков с включенным и отключенным пропуском мультимедиа](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="19315-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="19315-169">В приведенной ниже таблице показано различие между процессорами мультимедиа и реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="19315-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="19315-170">Процессоры мультимедиа</span><span class="sxs-lookup"><span data-stu-id="19315-170">Media Processors</span></span> | <span data-ttu-id="19315-171">Реле транспорта</span><span class="sxs-lookup"><span data-stu-id="19315-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="19315-172">В пути к носителю для пользователей, не пропускаемых за пределами Skype</span><span class="sxs-lookup"><span data-stu-id="19315-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="19315-173">Любой</span><span class="sxs-lookup"><span data-stu-id="19315-173">Always</span></span> | <span data-ttu-id="19315-174">Висеть</span><span class="sxs-lookup"><span data-stu-id="19315-174">Never</span></span> | 
<span data-ttu-id="19315-175">В пути к носителю для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="19315-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="19315-176">Висеть</span><span class="sxs-lookup"><span data-stu-id="19315-176">Never</span></span> | <span data-ttu-id="19315-177">Если клиент не может связаться с SBC на общедоступном IP-адресе</span><span class="sxs-lookup"><span data-stu-id="19315-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="19315-178">В пути к файлам мультимедиа для голосовых приложений</span><span class="sxs-lookup"><span data-stu-id="19315-178">In media path for voice applications</span></span> | <span data-ttu-id="19315-179">Любой</span><span class="sxs-lookup"><span data-stu-id="19315-179">Always</span></span> | <span data-ttu-id="19315-180">Висеть</span><span class="sxs-lookup"><span data-stu-id="19315-180">Never</span></span> | 
<span data-ttu-id="19315-181">Возможность перекодирования (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="19315-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="19315-182">Да</span><span class="sxs-lookup"><span data-stu-id="19315-182">Yes</span></span> | <span data-ttu-id="19315-183">Нет, ретрансляция звука между конечными точками</span><span class="sxs-lookup"><span data-stu-id="19315-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="19315-184">Количество экземпляров по всему миру и расположению</span><span class="sxs-lookup"><span data-stu-id="19315-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="19315-185">10, всего: 2 на АМЕРИКАНСКом Востоке и Запад; 2 в Амстердам и Дублин; 2 в Гонконг и Сингапур; 2 в Японии; 2 в Австралии на Восток и Юго-Восток</span><span class="sxs-lookup"><span data-stu-id="19315-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="19315-186">Сервер</span><span class="sxs-lookup"><span data-stu-id="19315-186">Multiple</span></span>

<span data-ttu-id="19315-187">Диапазоны IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="19315-187">The IP ranges are:</span></span>
- <span data-ttu-id="19315-188">52.112.0.0/14 (IP-адреса из 52.112.0.1 в 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="19315-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="19315-189">52.120.0.0/14 (IP-адреса из 52.120.0.1 в 52.123.255.254)</span><span class="sxs-lookup"><span data-stu-id="19315-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="19315-190">\* Описание перекодирования:</span><span class="sxs-lookup"><span data-stu-id="19315-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="19315-191">Процессор мультимедиа — B2BUA, то есть он может изменить кодеки (например, SILK из клиента Teams на MP и G. 711 между MP и SBC).</span><span class="sxs-lookup"><span data-stu-id="19315-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="19315-192">Реле транспорта не B2BUA, что означает, что кодек никогда не изменится между клиентом и SBC, даже если трафик проходит через реле.</span><span class="sxs-lookup"><span data-stu-id="19315-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="19315-193">Использование процессоров Teams при настройке магистрали для обхода файлов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="19315-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="19315-194">Обработчики мультимедиа в Teams всегда вставляются в путь к носителю в перечисленных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="19315-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="19315-195">Звонок эскалируется от 1:1 до группового звонка</span><span class="sxs-lookup"><span data-stu-id="19315-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="19315-196">Звонок пользователю федеративных групп</span><span class="sxs-lookup"><span data-stu-id="19315-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="19315-197">Звонок пересылается или передается пользователю Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="19315-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="19315-198">Убедитесь в том, что SBC имеет доступ к процессорам мультимедиа и диапазонам реле транспорта, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="19315-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="19315-199">Сигнализация SIP: полные доменные имена</span><span class="sxs-lookup"><span data-stu-id="19315-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="19315-200">Для сигнализации SIP требования к полному доменному имени и требованиям брандмауэра одинаковы для случаев, когда не используются другие варианты.</span><span class="sxs-lookup"><span data-stu-id="19315-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="19315-201">Прямая маршрутизация предоставляется в следующих средах Microsoft 365 или Office 365:</span><span class="sxs-lookup"><span data-stu-id="19315-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="19315-202">Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="19315-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="19315-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="19315-203">Office 365 GCC</span></span>
- <span data-ttu-id="19315-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="19315-204">Office 365 GCC High</span></span>
- <span data-ttu-id="19315-205">Office 365 для нескорой информации Узнайте больше о [офисных средах office 365 и США](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) , таких как GCC, GCC High и DOD.</span><span class="sxs-lookup"><span data-stu-id="19315-205">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="19315-206">Microsoft 365, Office 365 и Office 365 для более GCC среды</span><span class="sxs-lookup"><span data-stu-id="19315-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="19315-207">Для прямой маршрутизации используются следующие три полных доменных имен:</span><span class="sxs-lookup"><span data-stu-id="19315-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="19315-208">**SIP.pstnhub.Microsoft.com** — глобальное полное доменное имя — необходимо попытаться сначала.</span><span class="sxs-lookup"><span data-stu-id="19315-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="19315-209">Когда SBC отправляет запрос для разрешения этого имени, DNS-серверы Microsoft Azure возвращают IP-адрес, указывающий на основной центр обработки данных Azure, назначенный для SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="19315-210">Назначение основывается на метриках производительности центров обработки данных и географических расположений, близких к SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="19315-211">Возвращенный IP-адрес соответствует основному доменному имени.</span><span class="sxs-lookup"><span data-stu-id="19315-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="19315-212">**sip2.pstnhub.Microsoft.com** — дополнительное полное доменное имя — географически сопоставляется со вторым регионом приоритета.</span><span class="sxs-lookup"><span data-stu-id="19315-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="19315-213">**SIP3.pstnhub.Microsoft.com** — ТРЕТИЧНОЕ полное доменное имя — географически сопоставляется с третьим регионом приоритета.</span><span class="sxs-lookup"><span data-stu-id="19315-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="19315-214">Эти три полных доменных имен необходимо разместить в указанных ниже целях.</span><span class="sxs-lookup"><span data-stu-id="19315-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="19315-215">Обеспечьте оптимальную работу (менее загруженные и близкие к центру обработки данных, назначенному с помощью запроса первого полного доменного имени).</span><span class="sxs-lookup"><span data-stu-id="19315-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="19315-216">Отработка отказа при установке соединения из SBC с помощью центра обработки данных, на котором возникла временная проблема.</span><span class="sxs-lookup"><span data-stu-id="19315-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="19315-217">Дополнительные сведения можно найти в разделе механизм отработки отказа ниже.</span><span class="sxs-lookup"><span data-stu-id="19315-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="19315-218">Полные доменные имена **SIP.pstnhub.Microsoft.com**, **sip2.pstnhub.Microsoft.com**и **SIP3.pstnhub.Microsoft.com** будут разрешены на один из указанных ниже IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="19315-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="19315-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="19315-219">52.114.148.0</span></span>
- <span data-ttu-id="19315-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="19315-220">52.114.132.46</span></span>
- <span data-ttu-id="19315-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="19315-221">52.114.16.74</span></span>
- <span data-ttu-id="19315-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="19315-222">52.114.20.29</span></span>
- <span data-ttu-id="19315-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="19315-223">52.114.75.24</span></span>
- <span data-ttu-id="19315-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="19315-224">52.114.76.76</span></span>
- <span data-ttu-id="19315-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="19315-225">52.114.7.24</span></span>
- <span data-ttu-id="19315-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="19315-226">52.114.14.70</span></span>

<span data-ttu-id="19315-227">Чтобы разрешить входящий и исходящий трафик для отправки сигналов, необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="19315-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="19315-228">Если брандмауэр поддерживает DNS-имена, полное доменное имя **SIP-ALL.pstnhub.Microsoft.com** разрешается всем этим IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="19315-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="19315-229">Среда Microsoft 365 GCC с неиспользуемой по требованию</span><span class="sxs-lookup"><span data-stu-id="19315-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="19315-230">Точка соединения для прямой маршрутизации — это следующее полное доменное имя:</span><span class="sxs-lookup"><span data-stu-id="19315-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="19315-231">**SIP.pstnhub.DOD.Teams.Microsoft.US** — глобальное полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="19315-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="19315-232">Так как среда Microsoft Office 365 с несовпадением существует только в центрах данных США, дополнительные и третичные полные доменные имена не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="19315-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="19315-233">Полные доменные имена — sip.pstnhub.dod.teams.microsoft.us будут разрешены на один из указанных ниже IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="19315-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="19315-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="19315-234">52.127.64.33</span></span>
- <span data-ttu-id="19315-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="19315-235">52.127.68.34</span></span>

<span data-ttu-id="19315-236">Чтобы разрешить входящий и исходящий трафик для отправки сигналов, необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="19315-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="19315-237">Если брандмауэр поддерживает DNS-имена, полное доменное имя sip.pstnhub.dod.teams.microsoft.us разрешается всем этим IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="19315-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="19315-238">Office 365 GCC High (среда)</span><span class="sxs-lookup"><span data-stu-id="19315-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="19315-239">Точка соединения для прямой маршрутизации — это следующее полное доменное имя:</span><span class="sxs-lookup"><span data-stu-id="19315-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="19315-240">**SIP.pstnhub.gov.Teams.Microsoft.US** — глобальное полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="19315-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="19315-241">Как и в случае высокой среды GCC, только в центрах обработки данных США, дополнительные и третичные полные доменные имена не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="19315-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="19315-242">Полные доменные имена — sip.pstnhub.gov.teams.microsoft.us будут разрешены на один из указанных ниже IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="19315-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="19315-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="19315-243">52.127.88.59</span></span>
- <span data-ttu-id="19315-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="19315-244">52.127.92.64</span></span>

<span data-ttu-id="19315-245">Чтобы разрешить входящий и исходящий трафик для отправки сигналов, необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="19315-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="19315-246">Если брандмауэр поддерживает DNS-имена, полное доменное имя sip.pstnhub.gov.teams.microsoft.us разрешается всем этим IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="19315-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="19315-247">Сигнализация SIP: порты</span><span class="sxs-lookup"><span data-stu-id="19315-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="19315-248">Требования к портам одинаковы для всех сред Office 365, в которых предлагается прямая маршрутизация:</span><span class="sxs-lookup"><span data-stu-id="19315-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="19315-249">Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="19315-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="19315-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="19315-250">Office 365 GCC</span></span>
- <span data-ttu-id="19315-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="19315-251">Office 365 GCC High</span></span>
- <span data-ttu-id="19315-252">Office 365, DoD</span><span class="sxs-lookup"><span data-stu-id="19315-252">Office 365 DoD</span></span>

<span data-ttu-id="19315-253">Необходимо использовать следующие порты:</span><span class="sxs-lookup"><span data-stu-id="19315-253">You must use the following ports:</span></span>

| <span data-ttu-id="19315-254">Дорож</span><span class="sxs-lookup"><span data-stu-id="19315-254">Traffic</span></span> | <span data-ttu-id="19315-255">От</span><span class="sxs-lookup"><span data-stu-id="19315-255">From</span></span> | <span data-ttu-id="19315-256">До</span><span class="sxs-lookup"><span data-stu-id="19315-256">To</span></span> | <span data-ttu-id="19315-257">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="19315-257">Source port</span></span> | <span data-ttu-id="19315-258">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="19315-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="19315-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="19315-259">SIP/TLS</span></span>| <span data-ttu-id="19315-260">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="19315-260">SIP Proxy</span></span> | <span data-ttu-id="19315-261">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="19315-261">SBC</span></span> | <span data-ttu-id="19315-262">1024-65535</span><span class="sxs-lookup"><span data-stu-id="19315-262">1024 - 65535</span></span> | <span data-ttu-id="19315-263">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="19315-263">Defined on the SBC</span></span> |
| <span data-ttu-id="19315-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="19315-264">SIP/TLS</span></span> | <span data-ttu-id="19315-265">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="19315-265">SBC</span></span> | <span data-ttu-id="19315-266">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="19315-266">SIP Proxy</span></span> | <span data-ttu-id="19315-267">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="19315-267">Defined on the SBC</span></span> | <span data-ttu-id="19315-268">5061</span><span class="sxs-lookup"><span data-stu-id="19315-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="19315-269">Трафик мультимедиа: IP-адреса и диапазоны портов</span><span class="sxs-lookup"><span data-stu-id="19315-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="19315-270">Трафик мультимедиа между SBC и клиентом Teams, если он доступен, или посредством ретрансляции транспорта группы, если клиент не может достичь SBC с помощью общедоступного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="19315-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="19315-271">Требования к прямому трафику мультимедиа (между клиентом Teams и SBC)</span><span class="sxs-lookup"><span data-stu-id="19315-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="19315-272">Клиент должен иметь доступ к указанным портам (см. таблицу) на общедоступном IP-адресе SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="19315-273">Примечание. Если клиент находится во внутренней сети, он перетекает на общедоступный IP-адрес SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="19315-274">Вы можете настроить закрепление на устройстве NAT таким образом, чтобы трафик никогда не покидает сетевое оборудование предприятия.</span><span class="sxs-lookup"><span data-stu-id="19315-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="19315-275">Дорож</span><span class="sxs-lookup"><span data-stu-id="19315-275">Traffic</span></span> | <span data-ttu-id="19315-276">От</span><span class="sxs-lookup"><span data-stu-id="19315-276">From</span></span> | <span data-ttu-id="19315-277">До</span><span class="sxs-lookup"><span data-stu-id="19315-277">To</span></span> | <span data-ttu-id="19315-278">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="19315-278">Source port</span></span> | <span data-ttu-id="19315-279">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="19315-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="19315-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="19315-280">UDP/SRTP</span></span> | <span data-ttu-id="19315-281">Клиент</span><span class="sxs-lookup"><span data-stu-id="19315-281">Client</span></span> | <span data-ttu-id="19315-282">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="19315-282">SBC</span></span> | <span data-ttu-id="19315-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="19315-283">50 000 – 50 019</span></span>  | <span data-ttu-id="19315-284">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="19315-284">Defined on the SBC</span></span> |
| <span data-ttu-id="19315-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="19315-285">UDP/SRTP</span></span> | <span data-ttu-id="19315-286">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="19315-286">SBC</span></span> | <span data-ttu-id="19315-287">Клиент</span><span class="sxs-lookup"><span data-stu-id="19315-287">Client</span></span> | <span data-ttu-id="19315-288">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="19315-288">Defined on the SBC</span></span> | <span data-ttu-id="19315-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="19315-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="19315-290">Если у вас есть сетевое устройство, преобразующее исходные порты клиента, убедитесь, что переведенные порты открыты между сетевым оборудованием и SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="19315-291">Требования для использования ретрансляции транспорта</span><span class="sxs-lookup"><span data-stu-id="19315-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="19315-292">Транспортные ретрансляции находятся в том же диапазоне, что и процессоры мультимедиа (для случаев, когда не обходится):</span><span class="sxs-lookup"><span data-stu-id="19315-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="19315-293">Microsoft 365, Office 365 и Office 365 для более GCC среды</span><span class="sxs-lookup"><span data-stu-id="19315-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="19315-294">52.112.0.0/14 (IP-адреса из 52.112.0.1 в 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="19315-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="19315-295">Среда Microsoft 365 GCC с неиспользуемой по требованию</span><span class="sxs-lookup"><span data-stu-id="19315-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="19315-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="19315-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="19315-297">Office 365 GCC High (среда)</span><span class="sxs-lookup"><span data-stu-id="19315-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="19315-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="19315-298">52.127.88.0/21</span></span>


<span data-ttu-id="19315-299">Диапазон портов для реле транспорта Teams (применимо ко всем средам) приведен в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="19315-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="19315-300">Дорож</span><span class="sxs-lookup"><span data-stu-id="19315-300">Traffic</span></span> | <span data-ttu-id="19315-301">От</span><span class="sxs-lookup"><span data-stu-id="19315-301">From</span></span> | <span data-ttu-id="19315-302">До</span><span class="sxs-lookup"><span data-stu-id="19315-302">To</span></span> | <span data-ttu-id="19315-303">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="19315-303">Source port</span></span> | <span data-ttu-id="19315-304">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="19315-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="19315-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="19315-305">UDP/SRTP</span></span> | <span data-ttu-id="19315-306">Транспортные ретрансляции</span><span class="sxs-lookup"><span data-stu-id="19315-306">Transport Relay</span></span> | <span data-ttu-id="19315-307">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="19315-307">SBC</span></span> | <span data-ttu-id="19315-308">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="19315-308">50 000 -59 999</span></span>    | <span data-ttu-id="19315-309">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="19315-309">Defined on the SBC</span></span> |
| <span data-ttu-id="19315-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="19315-310">UDP/SRTP</span></span> | <span data-ttu-id="19315-311">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="19315-311">SBC</span></span> | <span data-ttu-id="19315-312">Транспортные ретрансляции</span><span class="sxs-lookup"><span data-stu-id="19315-312">Transport Relay</span></span> | <span data-ttu-id="19315-313">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="19315-313">Defined on the SBC</span></span> | <span data-ttu-id="19315-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="19315-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="19315-315">Корпорация Майкрософт рекомендует по крайней мере два порта для одновременных звонков на SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="19315-316">Так как корпорация Майкрософт использует две версии реле транспорта, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="19315-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="19315-317">V4, которая может работать только с диапазоном портов 50 000 – 59 999</span><span class="sxs-lookup"><span data-stu-id="19315-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="19315-318">V6, которые работают с портами 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="19315-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="19315-319">В настоящее время обход мультимедиа поддерживает только версию v4 для реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="19315-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="19315-320">Мы будем поддерживать версию V6 в будущем.</span><span class="sxs-lookup"><span data-stu-id="19315-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="19315-321">Для перехода вам нужно открыть порты 3478 и 3479.</span><span class="sxs-lookup"><span data-stu-id="19315-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="19315-322">Если корпорация Майкрософт предоставляет поддержку для ретрансляции протокола V6 с пропуском мультимедиа, вам не нужно будет перенастраивать сетевое оборудование или SBCs.</span><span class="sxs-lookup"><span data-stu-id="19315-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="19315-323">Требования для использования процессоров мультимедиа</span><span class="sxs-lookup"><span data-stu-id="19315-323">Requirements for using media processors</span></span>

<span data-ttu-id="19315-324">Процессоры мультимедиа всегда находятся в пути к файлам мультимедиа для голосовых приложений и веб-клиентов (например, клиенты Teams в EDGE или Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="19315-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="19315-325">Требования те же, что и для конфигурации без обхода.</span><span class="sxs-lookup"><span data-stu-id="19315-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="19315-326">Диапазон IP-адресов для мультимедийного трафика:</span><span class="sxs-lookup"><span data-stu-id="19315-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="19315-327">Среды Office 365 и Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="19315-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="19315-328">52.112.0.0/14 (IP-адреса из 52.112.0.1 в 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="19315-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="19315-329">Среда Microsoft 365 GCC с неиспользуемой по требованию</span><span class="sxs-lookup"><span data-stu-id="19315-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="19315-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="19315-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="19315-331">Office 365 GCC High (среда)</span><span class="sxs-lookup"><span data-stu-id="19315-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="19315-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="19315-332">52.127.88.0/21</span></span>

<span data-ttu-id="19315-333">В приведенной ниже таблице указаны диапазон портов для процессоров мультимедиа (применимо ко всем средам).</span><span class="sxs-lookup"><span data-stu-id="19315-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="19315-334">Дорож</span><span class="sxs-lookup"><span data-stu-id="19315-334">Traffic</span></span> | <span data-ttu-id="19315-335">От</span><span class="sxs-lookup"><span data-stu-id="19315-335">From</span></span> | <span data-ttu-id="19315-336">До</span><span class="sxs-lookup"><span data-stu-id="19315-336">To</span></span> | <span data-ttu-id="19315-337">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="19315-337">Source port</span></span> | <span data-ttu-id="19315-338">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="19315-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="19315-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="19315-339">UDP/SRTP</span></span> | <span data-ttu-id="19315-340">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="19315-340">Media Processor</span></span> | <span data-ttu-id="19315-341">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="19315-341">SBC</span></span> | <span data-ttu-id="19315-342">3478, 3479 и 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="19315-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="19315-343">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="19315-343">Defined on the SBC</span></span> |
| <span data-ttu-id="19315-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="19315-344">UDP/SRTP</span></span> | <span data-ttu-id="19315-345">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="19315-345">SBC</span></span> | <span data-ttu-id="19315-346">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="19315-346">Media Processor</span></span> | <span data-ttu-id="19315-347">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="19315-347">Defined on the SBC</span></span> | <span data-ttu-id="19315-348">3478, 3479 и 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="19315-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="19315-349">Настройка отдельных каналов для обхода файлов мультимедиа и обхода файлов без мультимедиа</span><span class="sxs-lookup"><span data-stu-id="19315-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="19315-350">Если вы перейдете на мультимедийный обход из-за отсутствия мультимедиа и хотите подтвердить выполнение всех функций, прежде чем переносить все использование в мультимедиа, вы можете создать отдельную магистральную и отдельную политику голосовой маршрутизации, чтобы направлять ее в режим мультимедиа и назначать конкретным пользователям.</span><span class="sxs-lookup"><span data-stu-id="19315-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="19315-351">Этапы настройки высокого уровня:</span><span class="sxs-lookup"><span data-stu-id="19315-351">High-level configuration steps:</span></span>

- <span data-ttu-id="19315-352">Определение пользователей для проверки пропуска мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="19315-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="19315-353">Создайте два канала для разных полных доменных имен: один включен для обхода мультимедиа. другой not.</span><span class="sxs-lookup"><span data-stu-id="19315-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="19315-354">Оба канала указывают на один и тот же SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="19315-355">Сигналы порта для TLS SIP должны быть разными.</span><span class="sxs-lookup"><span data-stu-id="19315-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="19315-356">Порты для мультимедиа должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="19315-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="19315-357">Создайте новую политику голосовой маршрутизации в сети и назначьте ее для соответствующих маршрутов, связанных с использованием КТСОП для этой политики.</span><span class="sxs-lookup"><span data-stu-id="19315-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="19315-358">Назначение новой политики голосовой маршрутизации через Интернет пользователям, которые вы определили для пропуска тестов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="19315-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="19315-359">В примере ниже показана эта логика.</span><span class="sxs-lookup"><span data-stu-id="19315-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="19315-360">Набор пользователей</span><span class="sxs-lookup"><span data-stu-id="19315-360">Set of users</span></span> | <span data-ttu-id="19315-361">Количество пользователей</span><span class="sxs-lookup"><span data-stu-id="19315-361">Number of users</span></span> | <span data-ttu-id="19315-362">Полные доменные имена для магистрали, назначенные в OVRP</span><span class="sxs-lookup"><span data-stu-id="19315-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="19315-363">Обход мультимедиа включен</span><span class="sxs-lookup"><span data-stu-id="19315-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="19315-364">Пользователи с магистральной магистрали без мультимедиа</span><span class="sxs-lookup"><span data-stu-id="19315-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="19315-365">980</span><span class="sxs-lookup"><span data-stu-id="19315-365">980</span></span> | <span data-ttu-id="19315-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="19315-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="19315-367">true</span><span class="sxs-lookup"><span data-stu-id="19315-367">true</span></span>
<span data-ttu-id="19315-368">Пользователи с магистральным пропуском мультимедиа</span><span class="sxs-lookup"><span data-stu-id="19315-368">Users with media bypass trunk</span></span> | <span data-ttu-id="19315-369">средняя</span><span class="sxs-lookup"><span data-stu-id="19315-369">20</span></span> | <span data-ttu-id="19315-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="19315-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="19315-371">false</span><span class="sxs-lookup"><span data-stu-id="19315-371">false</span></span> | 

<span data-ttu-id="19315-372">Обе магистральные линии могут указывать на один и тот же SBC с одинаковым общим IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="19315-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="19315-373">Порты TLS-сигналов на SBC должны отличаться, как показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="19315-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="19315-374">Примечание. необходимо убедиться, что ваш сертификат поддерживает обе магистральные линии.</span><span class="sxs-lookup"><span data-stu-id="19315-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="19315-375">В сети SAN необходимо иметь два имени (**sbc1.contoso.com** и **sbc2.contoso.com**) или использовать подстановочный сертификат.</span><span class="sxs-lookup"><span data-stu-id="19315-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19315-376">![Обе магистральные линии могут указывать на один и тот же SBC с одинаковым общим IP-адресом.](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="19315-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="19315-377">Сведения о том, как настроить две магистральные линии на одном SBC, можно найти в документации, предоставленной вашим поставщиком SBC.</span><span class="sxs-lookup"><span data-stu-id="19315-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="19315-378">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="19315-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="19315-379">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="19315-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="19315-380">Документация по развертыванию связи с лентой</span><span class="sxs-lookup"><span data-stu-id="19315-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="19315-381">Документация по развертыванию системы TE (anynode)</span><span class="sxs-lookup"><span data-stu-id="19315-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="19315-382">Конечные точки клиента, поддерживаемые при обходе мультимедиа</span><span class="sxs-lookup"><span data-stu-id="19315-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="19315-383">Обход мультимедиа поддерживается всеми настольными клиентами Teams и телефонными устройствами Teams.</span><span class="sxs-lookup"><span data-stu-id="19315-383">Media bypass is supported with all Teams Desktop clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="19315-384">Для всех остальных конечных точек, не поддерживающих обход мультимедиа, мы будем переключаться на вызов без обобщения даже в том случае, если он был запущен как обходной вызов.</span><span class="sxs-lookup"><span data-stu-id="19315-384">For all other endpoints that do not support media bypass, we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="19315-385">Это происходит автоматически и не требует каких – либо действий от администратора.</span><span class="sxs-lookup"><span data-stu-id="19315-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="19315-386">Сюда входят телефоны Skype для бизнеса 3PIP и веб-клиенты Teams, которые поддерживают прямую маршрутизацию (новый Microsoft EDGE на базе Chromium, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="19315-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (New Microsoft Edge based on Chromium, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="19315-387">См. также</span><span class="sxs-lookup"><span data-stu-id="19315-387">See also</span></span>

[<span data-ttu-id="19315-388">Настройка обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="19315-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)


