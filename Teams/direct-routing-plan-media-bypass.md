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
ms.openlocfilehash: f5e053149670804e585d0cd61522f67a922b2b47
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918698"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="6af2f-103">Планирование обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="6af2f-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="6af2f-104">Обход мультимедиа с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="6af2f-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="6af2f-105">Обход мультимедиа позволяет сократить путь к мультимедийному трафику и уменьшить число прыжков на пути для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="6af2f-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="6af2f-106">При обходе мультимедиа мультимедиа хранится между контроллером границ сеанса (SBC) и клиентом, а не отправкой через телефонную систему Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6af2f-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="6af2f-107">Чтобы настроить обход мультимедиа, SBC и клиент должны находиться в одном месте или в сети.</span><span class="sxs-lookup"><span data-stu-id="6af2f-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="6af2f-108">Вы можете управлять обходом мультимедиа для каждого SBC с помощью команды **Set-CSOnlinePSTNGateway** с параметром **-MediaBypass** , для которого установлено значение true или false.</span><span class="sxs-lookup"><span data-stu-id="6af2f-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="6af2f-109">Если включить обход мультимедиа, это не значит, что весь трафик мультимедиа останется в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="6af2f-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="6af2f-110">В этой статье описаны потоки звонков в разных сценариях.</span><span class="sxs-lookup"><span data-stu-id="6af2f-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="6af2f-111">На приведенных ниже схемах показано различие в потоке звонков с обходом мультимедиа и без него.</span><span class="sxs-lookup"><span data-stu-id="6af2f-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="6af2f-112">При отсутствии пропуска мультимедиа, когда клиент выполняет или получает вызов, как на рисунке, так и на устройстве с интерфейсом SBC, в системе Microsoft Phone и клиенте Teams, как показано на приведенной ниже схеме.</span><span class="sxs-lookup"><span data-stu-id="6af2f-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![Показывает сигнализацию и поток мультимедиа без обхода мультимедиа](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="6af2f-114">Но предположим, что пользователь в той же сборке или сети, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="6af2f-115">Например, предположим, что пользователь, который входит в состав здания в Frankfurt, осуществляет звонок пользователю PSTN:</span><span class="sxs-lookup"><span data-stu-id="6af2f-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="6af2f-116">**Без**обобщения мультимедиа мультимедиа будет перетекать через Амстердам или Дублин (там, где развернут центры обработки данных Майкрософт) и обратно на SBC в Frankfurt.</span><span class="sxs-lookup"><span data-stu-id="6af2f-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="6af2f-117">Центр обработки данных в Европе выбран, так как SBC находится в Европе, а Microsoft использует центр обработки данных, ближайший к SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="6af2f-118">Хотя этот подход не влияет на качество связи в связи с оптимизацией потока трафика в сетях Microsoft в большинстве географических регионов, трафик имеет ненужное зацикливание.</span><span class="sxs-lookup"><span data-stu-id="6af2f-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="6af2f-119">**При обходе мультимедиа**мультимедиа сохраняется непосредственно между пользователем Teams и SBC, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="6af2f-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![Показывает сигнализацию и поток мультимедиа с обходом мультимедиа](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="6af2f-121">Обход мультимедиа использует протоколы, называемые интерактивным подключением (ICE) в клиенте Teams, и Lite на SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="6af2f-122">Эти протоколы обеспечивают прямую маршрутизацию для использования наиболее подходящих путей к мультимедиа для оптимального качества.</span><span class="sxs-lookup"><span data-stu-id="6af2f-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="6af2f-123">ICE и ICE Lite — это WebRTC стандарты.</span><span class="sxs-lookup"><span data-stu-id="6af2f-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="6af2f-124">Подробные сведения об этих протоколах можно найти в RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="6af2f-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="6af2f-125">Потоки звонков и планирование брандмауэра</span><span class="sxs-lookup"><span data-stu-id="6af2f-125">Call flow and firewall planning</span></span>

<span data-ttu-id="6af2f-126">Потоки звонков и планирование в брандмауэре зависят от того, есть ли у пользователя прямой доступ к общедоступному IP-адресу объекта SBC, а также от того, входит ли пользователь в сеть или за ее пределы.</span><span class="sxs-lookup"><span data-stu-id="6af2f-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="6af2f-127">Поток звонков, если пользователь имеет прямой доступ к общедоступному IP-адресу объекта SBC</span><span class="sxs-lookup"><span data-stu-id="6af2f-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="6af2f-128">Если у пользователя есть прямой доступ к общедоступному IP-адресу объекта SBC, поток вызова выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6af2f-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="6af2f-129">Для обхода мультимедиа клиент Teams должен иметь доступ к общедоступному IP-адресу SBC, даже из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="6af2f-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="6af2f-130">Если прямое мультимедиа не требуется, мультимедиа может перетекать через реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="6af2f-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="6af2f-131">Это рекомендуемое решение, если пользователь в той же сборке и (или) сети, что и SBC — удаление облачных компонентов Microsoft из пути к носителю.</span><span class="sxs-lookup"><span data-stu-id="6af2f-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="6af2f-132">Передача сигналов всегда проходит через Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="6af2f-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="6af2f-133">На приведенной ниже схеме показан поток звонков, когда включена поддержка мультимедиа, клиент является внутренним, а клиент может получить доступ к публичному IP-адресу SBC (Direct Media):</span><span class="sxs-lookup"><span data-stu-id="6af2f-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="6af2f-134">Стрелки и числовые значения пути в соответствии со статьей [потоки вызовов Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="6af2f-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="6af2f-135">Сигнал SIP всегда принимает пути 4 и 4 (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="6af2f-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="6af2f-136">Мультимедиа останется на локальном компьютере, и его путь — 5b.</span><span class="sxs-lookup"><span data-stu-id="6af2f-136">Media stays local and takes path 5b.</span></span>

![Показывает поток звонков с включенным пропуском мультимедиа, клиент является внутренним](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="6af2f-138">Поток звонков, если пользователь не имеет доступа к общедоступному IP-адресу SBC</span><span class="sxs-lookup"><span data-stu-id="6af2f-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="6af2f-139">Ниже приведено описание потока вызова, если пользователь не имеет доступа к общедоступному IP-адресу SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="6af2f-140">Например, предположим, что пользователь является внешним, а администратор клиента решил не открывать общедоступный IP-адрес SBC для всех пользователей в Интернете, но только в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="6af2f-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="6af2f-141">Внутренние компоненты трафика могут перетекать через реле транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="6af2f-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="6af2f-142">Это рекомендуемая конфигурация для пользователей за пределами корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="6af2f-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="6af2f-143">Примите во внимание следующее:</span><span class="sxs-lookup"><span data-stu-id="6af2f-143">Consider the following:</span></span>

- <span data-ttu-id="6af2f-144">Используются реле транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="6af2f-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="6af2f-145">Для обхода мультимедиа Корпорация Майкрософт использует версию реле транспорта, для которой требуется открыть порты 50 000 для 59 999 между ретранслятором транспорта групп и SBC (в будущем мы планируем переход на версию, для которой требуется только 3478 и 3479).</span><span class="sxs-lookup"><span data-stu-id="6af2f-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="6af2f-146">Для целей оптимизации мультимедиа Корпорация Майкрософт рекомендует открывать общедоступный IP-адрес SBC только для ретрансляции транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="6af2f-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="6af2f-147">Для клиентов за пределами корпоративной сети Корпорация Майкрософт рекомендует использовать реле транспорта вместо того, чтобы обращаться к публичному IP-адресу SBC напрямую.</span><span class="sxs-lookup"><span data-stu-id="6af2f-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="6af2f-148">На приведенной ниже схеме показан поток вызова, если включен обход мультимедиа, клиент является внешним, а клиент не может связаться с общедоступным IP-адресом контроллера границ сеанса (поток ретранслируется транспортом транспорта Team Relay).</span><span class="sxs-lookup"><span data-stu-id="6af2f-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="6af2f-149">Стрелки и числовые значения пути в соответствии со статьей [потоки вызовов Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="6af2f-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="6af2f-150">Мультимедиа ретранслируется с помощью путей 3, 3, 4 и 4.</span><span class="sxs-lookup"><span data-stu-id="6af2f-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![Показывает поток вызова, если пользователь не имеет доступа к общедоступному IP-адресу объекта SBC](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="6af2f-152">Поток звонков, если пользователь находится за пределами сети и имеет доступ к общедоступному IP-адресу SBC</span><span class="sxs-lookup"><span data-stu-id="6af2f-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="6af2f-153">Это не рекомендуемая конфигурация, так как она не использует возможности ретрансляции транспорта для Teams.</span><span class="sxs-lookup"><span data-stu-id="6af2f-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="6af2f-154">Вместо этого следует рассмотреть предыдущий сценарий, в котором у пользователя нет доступа к общедоступному IP-адресу SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="6af2f-155">На приведенной ниже схеме показан поток звонков, если включен обход мультимедиа, клиент является внешним, а клиент может получить доступ к общевидимому IP-адресу SBC (Direct Media).</span><span class="sxs-lookup"><span data-stu-id="6af2f-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="6af2f-156">Стрелки и числовые значения пути в соответствии со статьей [потоки вызовов Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="6af2f-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="6af2f-157">Сигнал SIP всегда принимает пути 3 и 3 (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="6af2f-157">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="6af2f-158">Потоки мультимедиа, использующие путь 2.</span><span class="sxs-lookup"><span data-stu-id="6af2f-158">Media flows using path 2.</span></span>

![Показывает поток вызова, если пользователь не имеет доступа к общедоступному IP-адресу объекта SBC](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="6af2f-160">Использование мультимедийных процессоров и реле транспортировки</span><span class="sxs-lookup"><span data-stu-id="6af2f-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="6af2f-161">В облаке Microsoft есть два компонента, которые могут находиться в пути к мультимедийному трафику: процессоры мультимедиа и реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="6af2f-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="6af2f-162">Процессор мультимедиа — это общедоступный компонент, который обрабатывает мультимедиа в необходных случаях и обрабатывает носители для голосовых приложений.</span><span class="sxs-lookup"><span data-stu-id="6af2f-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="6af2f-163">Обработчики мультимедиа всегда находятся в пути для вызовов конечных пользователей, но никогда не в пути к пропускным звонкам.</span><span class="sxs-lookup"><span data-stu-id="6af2f-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="6af2f-164">Процессоры мультимедиа всегда находятся в пути для всех голосовых приложений, таких как приостановка звонков, автоматический секретарь Организации и очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="6af2f-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="6af2f-165">Транспортный ретранслятор используется для подключения к ближайшей транспортной службе для отправки трафика в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="6af2f-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="6af2f-166">Ретрансляция транспорта может быть или не включена в путь для конечных вызовов, в зависимости от того, где находится пользователь и как настроена сеть.</span><span class="sxs-lookup"><span data-stu-id="6af2f-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="6af2f-167">На приведенной ниже схеме показаны два потока звонков — один с включенным пропуском мультимедиа, а второй — без отключения мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="6af2f-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="6af2f-168">Обратите внимание, что схема показывает только трафик, направленный от конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="6af2f-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="6af2f-169">Контроллер мультимедиа — это микрослужба в Azure, которая назначает мультимедийные процессоры и создает предлагаемые протоколы описания сеансов (SDP).</span><span class="sxs-lookup"><span data-stu-id="6af2f-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="6af2f-170">Прокси-сервер SIP — компонент, который преобразует сигналы HTTP RESTFUL, используемые в Teams, в SIP.</span><span class="sxs-lookup"><span data-stu-id="6af2f-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![Показывает потоки звонков с включенным и отключенным пропуском мультимедиа](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="6af2f-172">В приведенной ниже таблице показано различие между процессорами мультимедиа и реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="6af2f-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="6af2f-173">Процессоры мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6af2f-173">Media Processors</span></span> | <span data-ttu-id="6af2f-174">Реле транспорта</span><span class="sxs-lookup"><span data-stu-id="6af2f-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="6af2f-175">В пути к носителю для пользователей, не пропускаемых за пределами Skype</span><span class="sxs-lookup"><span data-stu-id="6af2f-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="6af2f-176">Любой</span><span class="sxs-lookup"><span data-stu-id="6af2f-176">Always</span></span> | <span data-ttu-id="6af2f-177">Висеть</span><span class="sxs-lookup"><span data-stu-id="6af2f-177">Never</span></span> | 
<span data-ttu-id="6af2f-178">В пути к носителю для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="6af2f-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="6af2f-179">Висеть</span><span class="sxs-lookup"><span data-stu-id="6af2f-179">Never</span></span> | <span data-ttu-id="6af2f-180">Если клиент не может связаться с SBC на общедоступном IP-адресе</span><span class="sxs-lookup"><span data-stu-id="6af2f-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="6af2f-181">В пути к файлам мультимедиа для голосовых приложений</span><span class="sxs-lookup"><span data-stu-id="6af2f-181">In media path for voice applications</span></span> | <span data-ttu-id="6af2f-182">Любой</span><span class="sxs-lookup"><span data-stu-id="6af2f-182">Always</span></span> | <span data-ttu-id="6af2f-183">Висеть</span><span class="sxs-lookup"><span data-stu-id="6af2f-183">Never</span></span> | 
<span data-ttu-id="6af2f-184">Возможность перекодирования (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="6af2f-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="6af2f-185">Да</span><span class="sxs-lookup"><span data-stu-id="6af2f-185">Yes</span></span> | <span data-ttu-id="6af2f-186">Нет, ретрансляция звука между конечными точками</span><span class="sxs-lookup"><span data-stu-id="6af2f-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="6af2f-187">Количество экземпляров по всему миру и расположению</span><span class="sxs-lookup"><span data-stu-id="6af2f-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="6af2f-188">8, всего: 2 в США и Западная; 2 в Амстердам и Дублин; 2 в Гонконг и Сингапур; 2 в Японии</span><span class="sxs-lookup"><span data-stu-id="6af2f-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan</span></span>  | <span data-ttu-id="6af2f-189">Сервер</span><span class="sxs-lookup"><span data-stu-id="6af2f-189">Multiple</span></span>

<span data-ttu-id="6af2f-190">Диапазон IP-адресов — 52.112.0.0/14 (IP-адреса из 52.112.0.1 в 52.115.255.254).</span><span class="sxs-lookup"><span data-stu-id="6af2f-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="6af2f-191">\*Описание перекодирования:</span><span class="sxs-lookup"><span data-stu-id="6af2f-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="6af2f-192">Процессор мультимедиа — B2BUA, то есть он может изменить кодеки (например, SILK из клиента Teams на MP и G. 711 между MP и SBC).</span><span class="sxs-lookup"><span data-stu-id="6af2f-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="6af2f-193">Реле транспорта не B2BUA, что означает, что кодек никогда не изменится между клиентом и SBC, даже если трафик проходит через реле.</span><span class="sxs-lookup"><span data-stu-id="6af2f-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="6af2f-194">Использование процессоров Teams при настройке магистрали для обхода файлов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6af2f-194">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="6af2f-195">Обработчики мультимедиа в Teams всегда вставляются в путь к носителю в перечисленных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="6af2f-195">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="6af2f-196">Звонок эскалируется от 1:1 до группового звонка</span><span class="sxs-lookup"><span data-stu-id="6af2f-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="6af2f-197">Звонок пользователю федеративных групп</span><span class="sxs-lookup"><span data-stu-id="6af2f-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="6af2f-198">Звонок пересылается или передается пользователю Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6af2f-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="6af2f-199">Убедитесь в том, что SBC имеет доступ к процессорам мультимедиа и диапазонам реле транспорта, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="6af2f-199">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="6af2f-200">Сигнализация SIP: полные доменные имена</span><span class="sxs-lookup"><span data-stu-id="6af2f-200">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="6af2f-201">Для сигнализации SIP требования к полному доменному имени и требованиям брандмауэра одинаковы для случаев, когда не используются другие варианты.</span><span class="sxs-lookup"><span data-stu-id="6af2f-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="6af2f-202">Прямая маршрутизация предоставляется в следующих средах Office 365:</span><span class="sxs-lookup"><span data-stu-id="6af2f-202">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="6af2f-203">Office 365</span><span class="sxs-lookup"><span data-stu-id="6af2f-203">Office 365</span></span>
- <span data-ttu-id="6af2f-204">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6af2f-204">Office 365 GCC</span></span>
- <span data-ttu-id="6af2f-205">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6af2f-205">Office 365 GCC High</span></span>
- <span data-ttu-id="6af2f-206">Office 365 для нескорой информации Узнайте больше о [офисных средах office 365 и США](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) , таких как GCC, GCC High и DOD.</span><span class="sxs-lookup"><span data-stu-id="6af2f-206">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6af2f-207">Среды Office 365 и Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6af2f-207">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="6af2f-208">Для прямой маршрутизации используются следующие три полных доменных имен:</span><span class="sxs-lookup"><span data-stu-id="6af2f-208">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="6af2f-209">**SIP.pstnhub.Microsoft.com** — глобальное полное доменное имя — необходимо попытаться сначала.</span><span class="sxs-lookup"><span data-stu-id="6af2f-209">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="6af2f-210">Когда SBC отправляет запрос для разрешения этого имени, DNS-серверы Microsoft Azure возвращают IP-адрес, указывающий на основной центр обработки данных Azure, назначенный для SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-210">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="6af2f-211">Назначение основывается на метриках производительности центров обработки данных и географических расположений, близких к SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-211">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="6af2f-212">Возвращенный IP-адрес соответствует основному доменному имени.</span><span class="sxs-lookup"><span data-stu-id="6af2f-212">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="6af2f-213">**sip2.pstnhub.Microsoft.com** — дополнительное полное доменное имя — географически сопоставляется со вторым регионом приоритета.</span><span class="sxs-lookup"><span data-stu-id="6af2f-213">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="6af2f-214">**SIP3.pstnhub.Microsoft.com** — ТРЕТИЧНОЕ полное доменное имя — географически сопоставляется с третьим регионом приоритета.</span><span class="sxs-lookup"><span data-stu-id="6af2f-214">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="6af2f-215">Эти три полных доменных имен необходимо разместить в указанных ниже целях.</span><span class="sxs-lookup"><span data-stu-id="6af2f-215">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="6af2f-216">Обеспечьте оптимальную работу (менее загруженные и близкие к центру обработки данных, назначенному с помощью запроса первого полного доменного имени).</span><span class="sxs-lookup"><span data-stu-id="6af2f-216">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="6af2f-217">Отработка отказа при установке соединения из SBC с помощью центра обработки данных, на котором возникла временная проблема.</span><span class="sxs-lookup"><span data-stu-id="6af2f-217">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="6af2f-218">Дополнительные сведения можно найти в разделе механизм отработки отказа ниже.</span><span class="sxs-lookup"><span data-stu-id="6af2f-218">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="6af2f-219">Полные доменные имена **SIP.pstnhub.Microsoft.com**, **sip2.pstnhub.Microsoft.com**и **SIP3.pstnhub.Microsoft.com** будут разрешены на один из указанных ниже IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="6af2f-219">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="6af2f-220">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="6af2f-220">52.114.148.0</span></span>
- <span data-ttu-id="6af2f-221">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="6af2f-221">52.114.132.46</span></span>
- <span data-ttu-id="6af2f-222">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="6af2f-222">52.114.75.24</span></span>
- <span data-ttu-id="6af2f-223">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="6af2f-223">52.114.76.76</span></span>
- <span data-ttu-id="6af2f-224">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="6af2f-224">52.114.7.24</span></span>
- <span data-ttu-id="6af2f-225">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="6af2f-225">52.114.14.70</span></span>

<span data-ttu-id="6af2f-226">Чтобы разрешить входящий и исходящий трафик для отправки сигналов, необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="6af2f-226">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="6af2f-227">Если брандмауэр поддерживает DNS-имена, полное доменное имя **SIP-ALL.pstnhub.Microsoft.com** разрешается всем этим IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="6af2f-227">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6af2f-228">Среда Microsoft 365 GCC с неиспользуемой по требованию</span><span class="sxs-lookup"><span data-stu-id="6af2f-228">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="6af2f-229">Точка соединения для прямой маршрутизации — это следующее полное доменное имя:</span><span class="sxs-lookup"><span data-stu-id="6af2f-229">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="6af2f-230">**SIP.pstnhub.DOD.Teams.Microsoft.US** — глобальное полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="6af2f-230">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="6af2f-231">Так как среда Microsoft Office 365 с несовпадением существует только в центрах данных США, дополнительные и третичные полные доменные имена не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="6af2f-231">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="6af2f-232">Полные доменные имена — sip.pstnhub.dod.teams.microsoft.us будут разрешены на один из указанных ниже IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="6af2f-232">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="6af2f-233">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="6af2f-233">52.127.64.33</span></span>
- <span data-ttu-id="6af2f-234">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="6af2f-234">52.127.68.34</span></span>

<span data-ttu-id="6af2f-235">Чтобы разрешить входящий и исходящий трафик для отправки сигналов, необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="6af2f-235">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="6af2f-236">Если брандмауэр поддерживает DNS-имена, полное доменное имя sip.pstnhub.dod.teams.microsoft.us разрешается всем этим IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="6af2f-236">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6af2f-237">Office 365 GCC High (среда)</span><span class="sxs-lookup"><span data-stu-id="6af2f-237">Office 365 GCC High environment</span></span>

<span data-ttu-id="6af2f-238">Точка соединения для прямой маршрутизации — это следующее полное доменное имя:</span><span class="sxs-lookup"><span data-stu-id="6af2f-238">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="6af2f-239">**SIP.pstnhub.gov.Teams.Microsoft.US** — глобальное полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="6af2f-239">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="6af2f-240">Как и в случае высокой среды GCC, только в центрах обработки данных США, дополнительные и третичные полные доменные имена не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="6af2f-240">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="6af2f-241">Полные доменные имена — sip.pstnhub.gov.teams.microsoft.us будут разрешены на один из указанных ниже IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="6af2f-241">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="6af2f-242">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="6af2f-242">52.127.88.59</span></span>
- <span data-ttu-id="6af2f-243">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="6af2f-243">52.127.92.64</span></span>

<span data-ttu-id="6af2f-244">Чтобы разрешить входящий и исходящий трафик для отправки сигналов, необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="6af2f-244">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="6af2f-245">Если брандмауэр поддерживает DNS-имена, полное доменное имя sip.pstnhub.gov.teams.microsoft.us разрешается всем этим IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="6af2f-245">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="6af2f-246">Сигнализация SIP: порты</span><span class="sxs-lookup"><span data-stu-id="6af2f-246">SIP Signaling: Ports</span></span>

<span data-ttu-id="6af2f-247">Требования к портам одинаковы для всех сред Office 365, в которых предлагается прямая маршрутизация:</span><span class="sxs-lookup"><span data-stu-id="6af2f-247">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="6af2f-248">Office 365</span><span class="sxs-lookup"><span data-stu-id="6af2f-248">Office 365</span></span>
- <span data-ttu-id="6af2f-249">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6af2f-249">Office 365 GCC</span></span>
- <span data-ttu-id="6af2f-250">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="6af2f-250">Office 365 GCC High</span></span>
- <span data-ttu-id="6af2f-251">Office 365, DoD</span><span class="sxs-lookup"><span data-stu-id="6af2f-251">Office 365 DoD</span></span>

<span data-ttu-id="6af2f-252">Необходимо использовать следующие порты:</span><span class="sxs-lookup"><span data-stu-id="6af2f-252">You must use the following ports:</span></span>

| <span data-ttu-id="6af2f-253">Дорож</span><span class="sxs-lookup"><span data-stu-id="6af2f-253">Traffic</span></span> | <span data-ttu-id="6af2f-254">От</span><span class="sxs-lookup"><span data-stu-id="6af2f-254">From</span></span> | <span data-ttu-id="6af2f-255">До</span><span class="sxs-lookup"><span data-stu-id="6af2f-255">To</span></span> | <span data-ttu-id="6af2f-256">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="6af2f-256">Source port</span></span> | <span data-ttu-id="6af2f-257">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="6af2f-257">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6af2f-258">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="6af2f-258">SIP/TLS</span></span>| <span data-ttu-id="6af2f-259">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="6af2f-259">SIP Proxy</span></span> | <span data-ttu-id="6af2f-260">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="6af2f-260">SBC</span></span> | <span data-ttu-id="6af2f-261">1024-65535</span><span class="sxs-lookup"><span data-stu-id="6af2f-261">1024 - 65535</span></span> | <span data-ttu-id="6af2f-262">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="6af2f-262">Defined on the SBC</span></span> |
| <span data-ttu-id="6af2f-263">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="6af2f-263">SIP/TLS</span></span> | <span data-ttu-id="6af2f-264">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="6af2f-264">SBC</span></span> | <span data-ttu-id="6af2f-265">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="6af2f-265">SIP Proxy</span></span> | <span data-ttu-id="6af2f-266">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="6af2f-266">Defined on the SBC</span></span> | <span data-ttu-id="6af2f-267">5061</span><span class="sxs-lookup"><span data-stu-id="6af2f-267">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="6af2f-268">Трафик мультимедиа: IP-адреса и диапазоны портов</span><span class="sxs-lookup"><span data-stu-id="6af2f-268">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="6af2f-269">Трафик мультимедиа между SBC и клиентом Teams, если он доступен, или посредством ретрансляции транспорта группы, если клиент не может достичь SBC с помощью общедоступного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="6af2f-269">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="6af2f-270">Требования к прямому трафику мультимедиа (между клиентом Teams и SBC)</span><span class="sxs-lookup"><span data-stu-id="6af2f-270">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="6af2f-271">Клиент должен иметь доступ к указанным портам (см. таблицу) на общедоступном IP-адресе SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-271">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="6af2f-272">Примечание. Если клиент находится во внутренней сети, он перетекает на общедоступный IP-адрес SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-272">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="6af2f-273">Вы можете настроить закрепление на устройстве NAT таким образом, чтобы трафик никогда не покидает сетевое оборудование предприятия.</span><span class="sxs-lookup"><span data-stu-id="6af2f-273">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="6af2f-274">Дорож</span><span class="sxs-lookup"><span data-stu-id="6af2f-274">Traffic</span></span> | <span data-ttu-id="6af2f-275">От</span><span class="sxs-lookup"><span data-stu-id="6af2f-275">From</span></span> | <span data-ttu-id="6af2f-276">До</span><span class="sxs-lookup"><span data-stu-id="6af2f-276">To</span></span> | <span data-ttu-id="6af2f-277">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="6af2f-277">Source port</span></span> | <span data-ttu-id="6af2f-278">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="6af2f-278">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6af2f-279">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6af2f-279">UDP/SRTP</span></span> | <span data-ttu-id="6af2f-280">Клиент</span><span class="sxs-lookup"><span data-stu-id="6af2f-280">Client</span></span> | <span data-ttu-id="6af2f-281">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="6af2f-281">SBC</span></span> | <span data-ttu-id="6af2f-282">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="6af2f-282">50 000 – 50 019</span></span>  | <span data-ttu-id="6af2f-283">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="6af2f-283">Defined on the SBC</span></span> |
| <span data-ttu-id="6af2f-284">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6af2f-284">UDP/SRTP</span></span> | <span data-ttu-id="6af2f-285">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="6af2f-285">SBC</span></span> | <span data-ttu-id="6af2f-286">Клиент</span><span class="sxs-lookup"><span data-stu-id="6af2f-286">Client</span></span> | <span data-ttu-id="6af2f-287">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="6af2f-287">Defined on the SBC</span></span> | <span data-ttu-id="6af2f-288">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="6af2f-288">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="6af2f-289">Если у вас есть сетевое устройство, преобразующее исходные порты клиента, убедитесь, что переведенные порты открыты между сетевым оборудованием и SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-289">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="6af2f-290">Требования для использования ретрансляции транспорта</span><span class="sxs-lookup"><span data-stu-id="6af2f-290">Requirements for using Transport Relays</span></span>

<span data-ttu-id="6af2f-291">Транспортные ретрансляции находятся в том же диапазоне, что и процессоры мультимедиа (для случаев, когда не обходится):</span><span class="sxs-lookup"><span data-stu-id="6af2f-291">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6af2f-292">Среды Office 365 и Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6af2f-292">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="6af2f-293">52.112.0.0/14 (IP-адреса из 52.112.0.1 в 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="6af2f-293">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6af2f-294">Среда Microsoft 365 GCC с неиспользуемой по требованию</span><span class="sxs-lookup"><span data-stu-id="6af2f-294">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="6af2f-295">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="6af2f-295">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6af2f-296">Office 365 GCC High (среда)</span><span class="sxs-lookup"><span data-stu-id="6af2f-296">Office 365 GCC High environment</span></span>

- <span data-ttu-id="6af2f-297">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="6af2f-297">52.127.88.0/21</span></span>


<span data-ttu-id="6af2f-298">Диапазон портов для реле транспорта Teams (применимо ко всем средам) приведен в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="6af2f-298">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="6af2f-299">Дорож</span><span class="sxs-lookup"><span data-stu-id="6af2f-299">Traffic</span></span> | <span data-ttu-id="6af2f-300">От</span><span class="sxs-lookup"><span data-stu-id="6af2f-300">From</span></span> | <span data-ttu-id="6af2f-301">До</span><span class="sxs-lookup"><span data-stu-id="6af2f-301">To</span></span> | <span data-ttu-id="6af2f-302">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="6af2f-302">Source port</span></span> | <span data-ttu-id="6af2f-303">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="6af2f-303">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6af2f-304">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6af2f-304">UDP/SRTP</span></span> | <span data-ttu-id="6af2f-305">Транспортные ретрансляции</span><span class="sxs-lookup"><span data-stu-id="6af2f-305">Transport Relay</span></span> | <span data-ttu-id="6af2f-306">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="6af2f-306">SBC</span></span> | <span data-ttu-id="6af2f-307">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="6af2f-307">50 000 -59 999</span></span>    | <span data-ttu-id="6af2f-308">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="6af2f-308">Defined on the SBC</span></span> |
| <span data-ttu-id="6af2f-309">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6af2f-309">UDP/SRTP</span></span> | <span data-ttu-id="6af2f-310">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="6af2f-310">SBC</span></span> | <span data-ttu-id="6af2f-311">Транспортные ретрансляции</span><span class="sxs-lookup"><span data-stu-id="6af2f-311">Transport Relay</span></span> | <span data-ttu-id="6af2f-312">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="6af2f-312">Defined on the SBC</span></span> | <span data-ttu-id="6af2f-313">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="6af2f-313">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="6af2f-314">Корпорация Майкрософт рекомендует по крайней мере два порта для одновременных звонков на SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-314">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="6af2f-315">Так как корпорация Майкрософт использует две версии реле транспорта, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6af2f-315">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="6af2f-316">V4, которая может работать только с диапазоном портов 50 000 – 59 999</span><span class="sxs-lookup"><span data-stu-id="6af2f-316">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="6af2f-317">V6, которые работают с портами 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="6af2f-317">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="6af2f-318">В настоящее время обход мультимедиа поддерживает только версию v4 для реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="6af2f-318">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="6af2f-319">Мы будем поддерживать версию V6 в будущем.</span><span class="sxs-lookup"><span data-stu-id="6af2f-319">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="6af2f-320">Для перехода вам нужно открыть порты 3478 и 3479.</span><span class="sxs-lookup"><span data-stu-id="6af2f-320">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="6af2f-321">Если корпорация Майкрософт предоставляет поддержку для ретрансляции протокола V6 с пропуском мультимедиа, вам не нужно будет перенастраивать сетевое оборудование или SBCs.</span><span class="sxs-lookup"><span data-stu-id="6af2f-321">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="6af2f-322">Требования для использования процессоров мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6af2f-322">Requirements for using media processors</span></span>

<span data-ttu-id="6af2f-323">Процессоры мультимедиа всегда находятся в пути к файлам мультимедиа для голосовых приложений и веб-клиентов (например, клиенты Teams в EDGE или Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="6af2f-323">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="6af2f-324">Требования те же, что и для конфигурации без обхода.</span><span class="sxs-lookup"><span data-stu-id="6af2f-324">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="6af2f-325">Диапазон IP-адресов для мультимедийного трафика:</span><span class="sxs-lookup"><span data-stu-id="6af2f-325">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="6af2f-326">Среды Office 365 и Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="6af2f-326">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="6af2f-327">52.112.0.0/14 (IP-адреса из 52.112.0.1 в 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="6af2f-327">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="6af2f-328">Среда Microsoft 365 GCC с неиспользуемой по требованию</span><span class="sxs-lookup"><span data-stu-id="6af2f-328">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="6af2f-329">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="6af2f-329">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="6af2f-330">Office 365 GCC High (среда)</span><span class="sxs-lookup"><span data-stu-id="6af2f-330">Office 365 GCC High environment</span></span>

- <span data-ttu-id="6af2f-331">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="6af2f-331">52.127.88.0/21</span></span>

<span data-ttu-id="6af2f-332">В приведенной ниже таблице указаны диапазон портов для процессоров мультимедиа (применимо ко всем средам).</span><span class="sxs-lookup"><span data-stu-id="6af2f-332">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="6af2f-333">Дорож</span><span class="sxs-lookup"><span data-stu-id="6af2f-333">Traffic</span></span> | <span data-ttu-id="6af2f-334">От</span><span class="sxs-lookup"><span data-stu-id="6af2f-334">From</span></span> | <span data-ttu-id="6af2f-335">До</span><span class="sxs-lookup"><span data-stu-id="6af2f-335">To</span></span> | <span data-ttu-id="6af2f-336">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="6af2f-336">Source port</span></span> | <span data-ttu-id="6af2f-337">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="6af2f-337">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="6af2f-338">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6af2f-338">UDP/SRTP</span></span> | <span data-ttu-id="6af2f-339">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6af2f-339">Media Processor</span></span> | <span data-ttu-id="6af2f-340">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="6af2f-340">SBC</span></span> | <span data-ttu-id="6af2f-341">3478, 3479 и 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="6af2f-341">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="6af2f-342">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="6af2f-342">Defined on the SBC</span></span> |
| <span data-ttu-id="6af2f-343">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="6af2f-343">UDP/SRTP</span></span> | <span data-ttu-id="6af2f-344">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="6af2f-344">SBC</span></span> | <span data-ttu-id="6af2f-345">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6af2f-345">Media Processor</span></span> | <span data-ttu-id="6af2f-346">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="6af2f-346">Defined on the SBC</span></span> | <span data-ttu-id="6af2f-347">3478, 3479 и 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="6af2f-347">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="6af2f-348">Настройка отдельных каналов для обхода файлов мультимедиа и обхода файлов без мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6af2f-348">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="6af2f-349">Если вы перейдете на мультимедийный обход из-за отсутствия мультимедиа и хотите подтвердить выполнение всех функций, прежде чем переносить все использование в мультимедиа, вы можете создать отдельную магистральную и отдельную политику голосовой маршрутизации, чтобы направлять ее в режим мультимедиа и назначать конкретным пользователям.</span><span class="sxs-lookup"><span data-stu-id="6af2f-349">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="6af2f-350">Этапы настройки высокого уровня:</span><span class="sxs-lookup"><span data-stu-id="6af2f-350">High-level configuration steps:</span></span>

- <span data-ttu-id="6af2f-351">Определение пользователей для проверки пропуска мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="6af2f-351">Identify users to test media bypass.</span></span>

- <span data-ttu-id="6af2f-352">Создайте два канала для разных полных доменных имен: один включен для обхода мультимедиа. другой not.</span><span class="sxs-lookup"><span data-stu-id="6af2f-352">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="6af2f-353">Оба канала указывают на один и тот же SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-353">Both trunks point to the same SBC.</span></span> <span data-ttu-id="6af2f-354">Сигналы порта для TLS SIP должны быть разными.</span><span class="sxs-lookup"><span data-stu-id="6af2f-354">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="6af2f-355">Порты для мультимедиа должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="6af2f-355">The ports for media must be the same.</span></span>

- <span data-ttu-id="6af2f-356">Создайте новую политику голосовой маршрутизации в сети и назначьте ее для соответствующих маршрутов, связанных с использованием КТСОП для этой политики.</span><span class="sxs-lookup"><span data-stu-id="6af2f-356">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="6af2f-357">Назначение новой политики голосовой маршрутизации через Интернет пользователям, которые вы определили для пропуска тестов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="6af2f-357">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="6af2f-358">В примере ниже показана эта логика.</span><span class="sxs-lookup"><span data-stu-id="6af2f-358">The example below illustrates this logic.</span></span>

| <span data-ttu-id="6af2f-359">Набор пользователей</span><span class="sxs-lookup"><span data-stu-id="6af2f-359">Set of users</span></span> | <span data-ttu-id="6af2f-360">Количество пользователей</span><span class="sxs-lookup"><span data-stu-id="6af2f-360">Number of users</span></span> | <span data-ttu-id="6af2f-361">Полные доменные имена для магистрали, назначенные в OVRP</span><span class="sxs-lookup"><span data-stu-id="6af2f-361">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="6af2f-362">Обход мультимедиа включен</span><span class="sxs-lookup"><span data-stu-id="6af2f-362">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="6af2f-363">Пользователи с магистральной магистрали без мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6af2f-363">Users with non-media bypass trunk</span></span> | <span data-ttu-id="6af2f-364">980</span><span class="sxs-lookup"><span data-stu-id="6af2f-364">980</span></span> | <span data-ttu-id="6af2f-365">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="6af2f-365">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="6af2f-366">true</span><span class="sxs-lookup"><span data-stu-id="6af2f-366">true</span></span>
<span data-ttu-id="6af2f-367">Пользователи с магистральным пропуском мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6af2f-367">Users with media bypass trunk</span></span> | <span data-ttu-id="6af2f-368">средняя</span><span class="sxs-lookup"><span data-stu-id="6af2f-368">20</span></span> | <span data-ttu-id="6af2f-369">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="6af2f-369">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="6af2f-370">false</span><span class="sxs-lookup"><span data-stu-id="6af2f-370">false</span></span> | 

<span data-ttu-id="6af2f-371">Обе магистральные линии могут указывать на один и тот же SBC с одинаковым общим IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="6af2f-371">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="6af2f-372">Порты TLS-сигналов на SBC должны отличаться, как показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="6af2f-372">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="6af2f-373">Примечание. необходимо убедиться, что ваш сертификат поддерживает обе магистральные линии.</span><span class="sxs-lookup"><span data-stu-id="6af2f-373">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="6af2f-374">В сети SAN необходимо иметь два имени (**sbc1.contoso.com** и **sbc2.contoso.com**) или использовать подстановочный сертификат.</span><span class="sxs-lookup"><span data-stu-id="6af2f-374">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![Обе магистральные линии могут указывать на один и тот же SBC с одинаковым общим IP-адресом.](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="6af2f-376">Сведения о том, как настроить две магистральные линии на одном SBC, можно найти в документации, предоставленной вашим поставщиком SBC.</span><span class="sxs-lookup"><span data-stu-id="6af2f-376">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="6af2f-377">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="6af2f-377">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="6af2f-378">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="6af2f-378">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="6af2f-379">Документация по развертыванию связи с лентой</span><span class="sxs-lookup"><span data-stu-id="6af2f-379">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="6af2f-380">Документация по развертыванию системы TE (anynode)</span><span class="sxs-lookup"><span data-stu-id="6af2f-380">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="6af2f-381">Конечные точки клиента, поддерживаемые при обходе мультимедиа</span><span class="sxs-lookup"><span data-stu-id="6af2f-381">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="6af2f-382">Обход мультимедиа поддерживается всеми настольными клиентами Teams и телефонными устройствами Teams.</span><span class="sxs-lookup"><span data-stu-id="6af2f-382">Media bypass is supported with all Teams Desktop clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="6af2f-383">Для всех остальных конечных точек, не поддерживающих обход мультимедиа, мы будем переключаться на вызов без обобщения даже в том случае, если он был запущен как обходной вызов.</span><span class="sxs-lookup"><span data-stu-id="6af2f-383">For all other endpoints that do not support media bypass, we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="6af2f-384">Это происходит автоматически и не требует каких – либо действий от администратора.</span><span class="sxs-lookup"><span data-stu-id="6af2f-384">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="6af2f-385">Сюда входят телефоны Skype для бизнеса 3PIP и веб-клиенты Teams, которые поддерживают прямую маршрутизацию (новый Microsoft EDGE на базе Chromium, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="6af2f-385">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (New Microsoft Edge based on Chromium, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="6af2f-386">См. также</span><span class="sxs-lookup"><span data-stu-id="6af2f-386">See also</span></span>

[<span data-ttu-id="6af2f-387">Настройка обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="6af2f-387">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



