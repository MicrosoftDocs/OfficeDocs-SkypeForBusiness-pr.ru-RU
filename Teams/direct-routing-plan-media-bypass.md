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
description: В этой статье рассказывается, как запланировать обход мультимедиа с прямой маршрутизацией телефонной системы.
ms.openlocfilehash: 98f09d00960615c09dca8dcd78275a418d650f3e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835979"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="c5a39-103">Планирование обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="c5a39-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="c5a39-104">Обход мультимедиа с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="c5a39-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="c5a39-105">Обход мультимедиа позволяет сократить путь к мультимедийному трафику и уменьшить число прыжков на пути для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="c5a39-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="c5a39-106">При обходе мультимедиа мультимедиа хранится между контроллером границ сеанса (SBC) и клиентом, а не отправкой через телефонную систему Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5a39-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="c5a39-107">Чтобы настроить обход мультимедиа, SBC и клиент должны находиться в одном месте или в сети.</span><span class="sxs-lookup"><span data-stu-id="c5a39-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="c5a39-108">Вы можете управлять обходом мультимедиа для каждого SBC с помощью команды **Set-ксонлинепстнгатевай** с параметром **-медиабипасс** , для которого установлено значение true или false.</span><span class="sxs-lookup"><span data-stu-id="c5a39-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="c5a39-109">Если включить обход мультимедиа, это не значит, что весь трафик мультимедиа останется в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="c5a39-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="c5a39-110">В этой статье описаны потоки звонков в разных сценариях.</span><span class="sxs-lookup"><span data-stu-id="c5a39-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="c5a39-111">На приведенных ниже схемах показано различие в потоке звонков с обходом мультимедиа и без него.</span><span class="sxs-lookup"><span data-stu-id="c5a39-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="c5a39-112">При отсутствии пропуска мультимедиа, когда клиент выполняет или получает вызов, как на рисунке, так и на устройстве с интерфейсом SBC, в системе Microsoft Phone и клиенте Teams, как показано на приведенной ниже схеме.</span><span class="sxs-lookup"><span data-stu-id="c5a39-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![Показывает сигнализацию и поток мультимедиа без обхода мультимедиа](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="c5a39-114">Но предположим, что пользователь в той же сборке или сети, что и SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="c5a39-115">Например, предположим, что пользователь, который входит в состав здания в Франкфурт, осуществляет звонок пользователю PSTN:</span><span class="sxs-lookup"><span data-stu-id="c5a39-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="c5a39-116">**Без**обобщения мультимедиа мультимедиа будет перетекать через Амстердам или Дублин (там, где развернут центры обработки данных Майкрософт) и обратно на SBC в Франкфурт.</span><span class="sxs-lookup"><span data-stu-id="c5a39-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="c5a39-117">Центр обработки данных в Европе выбран, так как SBC находится в Европе, а Microsoft использует центр обработки данных, ближайший к SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="c5a39-118">Хотя этот подход не влияет на качество связи в связи с оптимизацией потока трафика в сетях Microsoft в большинстве географических регионов, трафик имеет ненужное зацикливание.</span><span class="sxs-lookup"><span data-stu-id="c5a39-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="c5a39-119">**При обходе мультимедиа**мультимедиа сохраняется непосредственно между пользователем Teams и SBC, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="c5a39-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![Показывает сигнализацию и поток мультимедиа с обходом мультимедиа](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="c5a39-121">Обход мультимедиа использует протоколы, называемые интерактивным подключением (ICE) в клиенте Teams, и Lite на SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="c5a39-122">Эти протоколы обеспечивают прямую маршрутизацию для использования наиболее подходящих путей к мультимедиа для оптимального качества.</span><span class="sxs-lookup"><span data-stu-id="c5a39-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="c5a39-123">ICE и ICE Lite — это Вебртк стандарты.</span><span class="sxs-lookup"><span data-stu-id="c5a39-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="c5a39-124">Подробные сведения об этих протоколах можно найти в RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="c5a39-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="c5a39-125">Потоки звонков и планирование брандмауэра</span><span class="sxs-lookup"><span data-stu-id="c5a39-125">Call flow and firewall planning</span></span>

<span data-ttu-id="c5a39-126">Потоки звонков и планирование в брандмауэре зависят от того, есть ли у пользователя прямой доступ к общедоступному IP-адресу объекта SBC, а также от того, входит ли пользователь в сеть или за ее пределы.</span><span class="sxs-lookup"><span data-stu-id="c5a39-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="c5a39-127">Поток звонков, если пользователь имеет прямой доступ к общедоступному IP-адресу объекта SBC</span><span class="sxs-lookup"><span data-stu-id="c5a39-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="c5a39-128">Если у пользователя есть прямой доступ к общедоступному IP-адресу объекта SBC, поток вызова выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c5a39-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="c5a39-129">Для обхода мультимедиа клиент Teams должен иметь доступ к общедоступному IP-адресу SBC, даже из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="c5a39-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="c5a39-130">Если прямое мультимедиа не требуется, мультимедиа может перетекать через реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="c5a39-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="c5a39-131">Это рекомендуемое решение, если пользователь в той же сборке и (или) сети, что и SBC — удаление облачных компонентов Microsoft из пути к носителю.</span><span class="sxs-lookup"><span data-stu-id="c5a39-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="c5a39-132">Передача сигналов всегда проходит через Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="c5a39-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="c5a39-133">На приведенной ниже схеме показан поток звонков, когда включена поддержка мультимедиа, клиент является внутренним, а клиент может получить доступ к публичному IP-адресу SBC (Direct Media):</span><span class="sxs-lookup"><span data-stu-id="c5a39-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="c5a39-134">Стрелки и числовые значения пути в соответствии со статьей [потоки вызовов Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="c5a39-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="c5a39-135">Сигнал SIP всегда принимает пути 4 и 4 (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="c5a39-135">The SIP signaling always takes paths 4 and 4’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="c5a39-136">Мультимедиа останется на локальном компьютере, и его путь — 5b.</span><span class="sxs-lookup"><span data-stu-id="c5a39-136">Media stays local and takes path 5b.</span></span>

![Показывает поток звонков с включенным пропуском мультимедиа, клиент является внутренним](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="c5a39-138">Поток звонков, если пользователь не имеет доступа к общедоступному IP-адресу SBC</span><span class="sxs-lookup"><span data-stu-id="c5a39-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="c5a39-139">Ниже приведено описание потока вызова, если пользователь не имеет доступа к общедоступному IP-адресу SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="c5a39-140">Например, предположим, что пользователь является внешним, а администратор клиента решил не открывать общедоступный IP-адрес SBC для всех пользователей в Интернете, но только в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="c5a39-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="c5a39-141">Внутренние компоненты трафика могут перетекать через реле транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="c5a39-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="c5a39-142">Это рекомендуемая конфигурация для пользователей за пределами корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="c5a39-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="c5a39-143">Рассмотрим следующее:</span><span class="sxs-lookup"><span data-stu-id="c5a39-143">Consider the following:</span></span>

- <span data-ttu-id="c5a39-144">Используются реле транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="c5a39-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="c5a39-145">Для обхода мультимедиа Корпорация Майкрософт использует версию реле транспорта, для которой требуется открыть порты 50 000 для 59 999 между ретранслятором транспорта групп и SBC (в будущем мы планируем переход на версию, для которой требуется только 3478 и 3479).</span><span class="sxs-lookup"><span data-stu-id="c5a39-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="c5a39-146">Для целей оптимизации мультимедиа Корпорация Майкрософт рекомендует открывать общедоступный IP-адрес SBC только для ретрансляции транспорта Teams.</span><span class="sxs-lookup"><span data-stu-id="c5a39-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="c5a39-147">Для клиентов за пределами корпоративной сети Корпорация Майкрософт рекомендует использовать реле транспорта вместо того, чтобы обращаться к публичному IP-адресу SBC напрямую.</span><span class="sxs-lookup"><span data-stu-id="c5a39-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="c5a39-148">На приведенной ниже схеме показан поток вызова, если включен обход мультимедиа, клиент является внешним, а клиент не может связаться с общедоступным IP-адресом контроллера границ сеанса (поток ретранслируется транспортом транспорта Team Relay).</span><span class="sxs-lookup"><span data-stu-id="c5a39-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="c5a39-149">Стрелки и числовые значения пути в соответствии со статьей [потоки вызовов Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="c5a39-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="c5a39-150">Мультимедиа ретранслируется с помощью путей 3, 3, 4 и 4.</span><span class="sxs-lookup"><span data-stu-id="c5a39-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![Показывает поток вызова, если пользователь не имеет доступа к общедоступному IP-адресу объекта SBC](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="c5a39-152">Поток звонков, если пользователь находится за пределами сети и имеет доступ к общедоступному IP-адресу SBC</span><span class="sxs-lookup"><span data-stu-id="c5a39-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="c5a39-153">Это не рекомендуемая конфигурация, так как она не использует возможности ретрансляции транспорта для Teams.</span><span class="sxs-lookup"><span data-stu-id="c5a39-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="c5a39-154">Вместо этого следует рассмотреть предыдущий сценарий, в котором у пользователя нет доступа к общедоступному IP-адресу SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="c5a39-155">На приведенной ниже схеме показан поток звонков, если включен обход мультимедиа, клиент является внешним, а клиент может получить доступ к общевидимому IP-адресу SBC (Direct Media).</span><span class="sxs-lookup"><span data-stu-id="c5a39-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="c5a39-156">Стрелки и числовые значения пути в соответствии со статьей [потоки вызовов Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .</span><span class="sxs-lookup"><span data-stu-id="c5a39-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="c5a39-157">Сигнал SIP всегда принимает пути 3 и 3 (в зависимости от направления трафика).</span><span class="sxs-lookup"><span data-stu-id="c5a39-157">The SIP signaling always takes paths 3 and 3’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="c5a39-158">Потоки мультимедиа, использующие путь 2.</span><span class="sxs-lookup"><span data-stu-id="c5a39-158">Media flows using path 2.</span></span>

![Показывает поток вызова, если пользователь не имеет доступа к общедоступному IP-адресу объекта SBC](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="c5a39-160">Использование мультимедийных процессоров и реле транспортировки</span><span class="sxs-lookup"><span data-stu-id="c5a39-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="c5a39-161">В облаке Microsoft есть два компонента, которые могут находиться в пути к мультимедийному трафику: процессоры мультимедиа и реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="c5a39-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="c5a39-162">Процессор мультимедиа — это общедоступный компонент, который обрабатывает мультимедиа в необходных случаях и обрабатывает носители для голосовых приложений.</span><span class="sxs-lookup"><span data-stu-id="c5a39-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="c5a39-163">Обработчики мультимедиа всегда находятся в пути для вызовов конечных пользователей, но никогда не в пути к пропускным звонкам.</span><span class="sxs-lookup"><span data-stu-id="c5a39-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="c5a39-164">Процессоры мультимедиа всегда находятся в пути для всех голосовых приложений, таких как приостановка звонков, автоматический секретарь Организации и очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="c5a39-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="c5a39-165">Транспортный ретранслятор используется для подключения к ближайшей транспортной службе для отправки трафика в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="c5a39-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="c5a39-166">Ретрансляция транспорта может быть или не включена в путь для конечных вызовов, в зависимости от того, где находится пользователь и как настроена сеть.</span><span class="sxs-lookup"><span data-stu-id="c5a39-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="c5a39-167">На приведенной ниже схеме показаны два потока звонков — один с включенным пропуском мультимедиа, а второй — без отключения мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c5a39-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="c5a39-168">Обратите внимание, что схема показывает только трафик, направленный от конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c5a39-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="c5a39-169">Контроллер мультимедиа — это микрослужба в Azure, которая назначает мультимедийные процессоры и создает предлагаемые протоколы описания сеансов (SDP).</span><span class="sxs-lookup"><span data-stu-id="c5a39-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="c5a39-170">Прокси-сервер SIP — компонент, который преобразует сигналы HTTP RESTFUL, используемые в Teams, в SIP.</span><span class="sxs-lookup"><span data-stu-id="c5a39-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![Показывает потоки звонков с включенным и отключенным пропуском мультимедиа](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="c5a39-172">В приведенной ниже таблице показано различие между процессорами мультимедиа и реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="c5a39-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="c5a39-173">Процессоры мультимедиа</span><span class="sxs-lookup"><span data-stu-id="c5a39-173">Media Processors</span></span> | <span data-ttu-id="c5a39-174">Реле транспорта</span><span class="sxs-lookup"><span data-stu-id="c5a39-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="c5a39-175">В пути к носителю для пользователей, не пропускаемых за пределами Skype</span><span class="sxs-lookup"><span data-stu-id="c5a39-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="c5a39-176">Любой</span><span class="sxs-lookup"><span data-stu-id="c5a39-176">Always</span></span> | <span data-ttu-id="c5a39-177">Висеть</span><span class="sxs-lookup"><span data-stu-id="c5a39-177">Never</span></span> | 
<span data-ttu-id="c5a39-178">В пути к носителю для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="c5a39-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="c5a39-179">Висеть</span><span class="sxs-lookup"><span data-stu-id="c5a39-179">Never</span></span> | <span data-ttu-id="c5a39-180">Если клиент не может связаться с SBC на общедоступном IP-адресе</span><span class="sxs-lookup"><span data-stu-id="c5a39-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="c5a39-181">В пути к файлам мультимедиа для голосовых приложений</span><span class="sxs-lookup"><span data-stu-id="c5a39-181">In media path for voice applications</span></span> | <span data-ttu-id="c5a39-182">Любой</span><span class="sxs-lookup"><span data-stu-id="c5a39-182">Always</span></span> | <span data-ttu-id="c5a39-183">Висеть</span><span class="sxs-lookup"><span data-stu-id="c5a39-183">Never</span></span> | 
<span data-ttu-id="c5a39-184">Возможность перекодирования (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="c5a39-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="c5a39-185">Да</span><span class="sxs-lookup"><span data-stu-id="c5a39-185">Yes</span></span> | <span data-ttu-id="c5a39-186">Нет, ретрансляция звука между конечными точками</span><span class="sxs-lookup"><span data-stu-id="c5a39-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="c5a39-187">Количество экземпляров по всему миру и расположению</span><span class="sxs-lookup"><span data-stu-id="c5a39-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="c5a39-188">8, всего: 2 в США и Западная; 2 в Амстердам и Дублин; 2 в Гонконг и Сингапур; 2 в Японии (добавляется в Q1CY2019)</span><span class="sxs-lookup"><span data-stu-id="c5a39-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan (being added in Q1CY2019)</span></span>  | <span data-ttu-id="c5a39-189">Сервер</span><span class="sxs-lookup"><span data-stu-id="c5a39-189">Multiple</span></span>

<span data-ttu-id="c5a39-190">Диапазон IP-адресов — 52.112.0.0/14 (IP-адреса из 52.112.0.1 в 52.115.255.254).</span><span class="sxs-lookup"><span data-stu-id="c5a39-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="c5a39-191">\*Описание перекодирования:</span><span class="sxs-lookup"><span data-stu-id="c5a39-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="c5a39-192">Процессор мультимедиа — B2BUA, то есть он может изменить кодеки (например, SILK из клиента Teams на MP и G. 711 между MP и SBC).</span><span class="sxs-lookup"><span data-stu-id="c5a39-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="c5a39-193">Реле транспорта не B2BUA, что означает, что кодек никогда не изменится между клиентом и SBC, даже если трафик проходит через реле.</span><span class="sxs-lookup"><span data-stu-id="c5a39-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="c5a39-194">Использование процессоров Teams при настройке магистрали для обхода файлов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="c5a39-194">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="c5a39-195">Обработчики мультимедиа в Teams всегда вставляются в путь к носителю в перечисленных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="c5a39-195">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="c5a39-196">Звонок эскалируется от 1:1 до группового звонка</span><span class="sxs-lookup"><span data-stu-id="c5a39-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="c5a39-197">Звонок пользователю федеративных групп</span><span class="sxs-lookup"><span data-stu-id="c5a39-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="c5a39-198">Звонок пересылается или передается пользователю Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c5a39-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="c5a39-199">Убедитесь в том, что SBC имеет доступ к процессорам мультимедиа и диапазонам реле транспорта, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="c5a39-199">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="c5a39-200">Сигнализация SIP: полные доменные имена</span><span class="sxs-lookup"><span data-stu-id="c5a39-200">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="c5a39-201">Для сигнализации SIP требования к полному доменному имени и требованиям брандмауэра одинаковы для случаев, когда не используются другие варианты.</span><span class="sxs-lookup"><span data-stu-id="c5a39-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="c5a39-202">Прямая маршрутизация предоставляется в следующих средах Office 365:</span><span class="sxs-lookup"><span data-stu-id="c5a39-202">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="c5a39-203">Office 365</span><span class="sxs-lookup"><span data-stu-id="c5a39-203">Office 365</span></span>
- <span data-ttu-id="c5a39-204">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="c5a39-204">Office 365 GCC</span></span>
- <span data-ttu-id="c5a39-205">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="c5a39-205">Office 365 GCC High</span></span>
- <span data-ttu-id="c5a39-206">Office 365 для нескорой информации Узнайте больше о [офисных средах office 365 и США](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) , таких как GCC, GCC High и DOD.</span><span class="sxs-lookup"><span data-stu-id="c5a39-206">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="c5a39-207">Среды Office 365 и Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="c5a39-207">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="c5a39-208">Для прямой маршрутизации используются следующие три полных доменных имен:</span><span class="sxs-lookup"><span data-stu-id="c5a39-208">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="c5a39-209">**SIP.pstnhub.Microsoft.com** — глобальное полное доменное имя — необходимо попытаться сначала.</span><span class="sxs-lookup"><span data-stu-id="c5a39-209">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="c5a39-210">Когда SBC отправляет запрос для разрешения этого имени, DNS-серверы Microsoft Azure возвращают IP-адрес, указывающий на основной центр обработки данных Azure, назначенный для SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-210">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="c5a39-211">Назначение основывается на метриках производительности центров обработки данных и географических расположений, близких к SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-211">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="c5a39-212">Возвращенный IP-адрес соответствует основному доменному имени.</span><span class="sxs-lookup"><span data-stu-id="c5a39-212">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="c5a39-213">**sip2.pstnhub.Microsoft.com** — дополнительное полное доменное имя — географически сопоставляется со вторым регионом приоритета.</span><span class="sxs-lookup"><span data-stu-id="c5a39-213">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="c5a39-214">**SIP3.pstnhub.Microsoft.com** — ТРЕТИЧНОЕ полное доменное имя — географически сопоставляется с третьим регионом приоритета.</span><span class="sxs-lookup"><span data-stu-id="c5a39-214">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="c5a39-215">Эти три полных доменных имен необходимо разместить в указанных ниже целях.</span><span class="sxs-lookup"><span data-stu-id="c5a39-215">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="c5a39-216">Обеспечьте оптимальную работу (менее загруженные и близкие к центру обработки данных, назначенному с помощью запроса первого полного доменного имени).</span><span class="sxs-lookup"><span data-stu-id="c5a39-216">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="c5a39-217">Отработка отказа при установке соединения из SBC с помощью центра обработки данных, на котором возникла временная проблема.</span><span class="sxs-lookup"><span data-stu-id="c5a39-217">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="c5a39-218">Дополнительные сведения можно найти в разделе механизм отработки отказа ниже.</span><span class="sxs-lookup"><span data-stu-id="c5a39-218">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="c5a39-219">Полные доменные имена **SIP.pstnhub.Microsoft.com**, **sip2.pstnhub.Microsoft.com**и **SIP3.pstnhub.Microsoft.com** будут разрешены на один из указанных ниже IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="c5a39-219">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="c5a39-220">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="c5a39-220">52.114.148.0</span></span>
- <span data-ttu-id="c5a39-221">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="c5a39-221">52.114.132.46</span></span>
- <span data-ttu-id="c5a39-222">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="c5a39-222">52.114.75.24</span></span>
- <span data-ttu-id="c5a39-223">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="c5a39-223">52.114.76.76</span></span>
- <span data-ttu-id="c5a39-224">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="c5a39-224">52.114.7.24</span></span>
- <span data-ttu-id="c5a39-225">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="c5a39-225">52.114.14.70</span></span>

<span data-ttu-id="c5a39-226">Чтобы разрешить входящий и исходящий трафик для отправки сигналов, необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="c5a39-226">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="c5a39-227">Если брандмауэр поддерживает DNS-имена, полное доменное имя **SIP-ALL.pstnhub.Microsoft.com** разрешается всем этим IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="c5a39-227">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="c5a39-228">Среда Microsoft 365 GCC с неиспользуемой по требованию</span><span class="sxs-lookup"><span data-stu-id="c5a39-228">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="c5a39-229">Точка соединения для прямой маршрутизации — это следующее полное доменное имя:</span><span class="sxs-lookup"><span data-stu-id="c5a39-229">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="c5a39-230">**SIP.pstnhub.DOD.Teams.Microsoft.US** — глобальное полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="c5a39-230">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="c5a39-231">Так как среда Microsoft Office 365 с несовпадением существует только в центрах данных США, дополнительные и третичные полные доменные имена не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="c5a39-231">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="c5a39-232">Полные доменные имена — sip.pstnhub.dod.teams.microsoft.us будут разрешены на один из указанных ниже IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="c5a39-232">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="c5a39-233">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="c5a39-233">52.127.64.33</span></span>
- <span data-ttu-id="c5a39-234">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="c5a39-234">52.127.68.34</span></span>

<span data-ttu-id="c5a39-235">Чтобы разрешить входящий и исходящий трафик для отправки сигналов, необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="c5a39-235">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="c5a39-236">Если брандмауэр поддерживает DNS-имена, полное доменное имя sip.pstnhub.dod.teams.microsoft.us разрешается всем этим IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="c5a39-236">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="c5a39-237">Office 365 GCC High (среда)</span><span class="sxs-lookup"><span data-stu-id="c5a39-237">Office 365 GCC High environment</span></span>

<span data-ttu-id="c5a39-238">Точка соединения для прямой маршрутизации — это следующее полное доменное имя:</span><span class="sxs-lookup"><span data-stu-id="c5a39-238">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="c5a39-239">**SIP.pstnhub.gov.Teams.Microsoft.US** — глобальное полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="c5a39-239">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="c5a39-240">Как и в случае высокой среды GCC, только в центрах обработки данных США, дополнительные и третичные полные доменные имена не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="c5a39-240">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="c5a39-241">Полные доменные имена — sip.pstnhub.gov.teams.microsoft.us будут разрешены на один из указанных ниже IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="c5a39-241">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="c5a39-242">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="c5a39-242">52.127.88.59</span></span>
- <span data-ttu-id="c5a39-243">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="c5a39-243">52.127.92.64</span></span>

<span data-ttu-id="c5a39-244">Чтобы разрешить входящий и исходящий трафик для отправки сигналов, необходимо открыть порты для всех этих IP-адресов в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="c5a39-244">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="c5a39-245">Если брандмауэр поддерживает DNS-имена, полное доменное имя sip.pstnhub.gov.teams.microsoft.us разрешается всем этим IP-адресам.</span><span class="sxs-lookup"><span data-stu-id="c5a39-245">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="c5a39-246">Сигнализация SIP: порты</span><span class="sxs-lookup"><span data-stu-id="c5a39-246">SIP Signaling: Ports</span></span>

<span data-ttu-id="c5a39-247">Требования к портам одинаковы для всех сред Office 365, в которых предлагается прямая маршрутизация:</span><span class="sxs-lookup"><span data-stu-id="c5a39-247">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="c5a39-248">Office 365</span><span class="sxs-lookup"><span data-stu-id="c5a39-248">Office 365</span></span>
- <span data-ttu-id="c5a39-249">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="c5a39-249">Office 365 GCC</span></span>
- <span data-ttu-id="c5a39-250">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="c5a39-250">Office 365 GCC High</span></span>
- <span data-ttu-id="c5a39-251">Office 365, DoD</span><span class="sxs-lookup"><span data-stu-id="c5a39-251">Office 365 DoD</span></span>

<span data-ttu-id="c5a39-252">Необходимо использовать следующие порты:</span><span class="sxs-lookup"><span data-stu-id="c5a39-252">You must use the following ports:</span></span>

| <span data-ttu-id="c5a39-253">Дорож</span><span class="sxs-lookup"><span data-stu-id="c5a39-253">Traffic</span></span> | <span data-ttu-id="c5a39-254">От</span><span class="sxs-lookup"><span data-stu-id="c5a39-254">From</span></span> | <span data-ttu-id="c5a39-255">До</span><span class="sxs-lookup"><span data-stu-id="c5a39-255">To</span></span> | <span data-ttu-id="c5a39-256">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="c5a39-256">Source port</span></span> | <span data-ttu-id="c5a39-257">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="c5a39-257">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="c5a39-258">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="c5a39-258">SIP/TLS</span></span>| <span data-ttu-id="c5a39-259">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="c5a39-259">SIP Proxy</span></span> | <span data-ttu-id="c5a39-260">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="c5a39-260">SBC</span></span> | <span data-ttu-id="c5a39-261">1024-65535</span><span class="sxs-lookup"><span data-stu-id="c5a39-261">1024 - 65535</span></span> | <span data-ttu-id="c5a39-262">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="c5a39-262">Defined on the SBC</span></span> |
| <span data-ttu-id="c5a39-263">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="c5a39-263">SIP/TLS</span></span> | <span data-ttu-id="c5a39-264">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="c5a39-264">SBC</span></span> | <span data-ttu-id="c5a39-265">Прокси-сервер SIP</span><span class="sxs-lookup"><span data-stu-id="c5a39-265">SIP Proxy</span></span> | <span data-ttu-id="c5a39-266">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="c5a39-266">Defined on the SBC</span></span> | <span data-ttu-id="c5a39-267">5061</span><span class="sxs-lookup"><span data-stu-id="c5a39-267">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="c5a39-268">Трафик мультимедиа: IP-адреса и диапазоны портов</span><span class="sxs-lookup"><span data-stu-id="c5a39-268">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="c5a39-269">Трафик мультимедиа между SBC и клиентом Teams, если он доступен, или посредством ретрансляции транспорта группы, если клиент не может достичь SBC с помощью общедоступного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="c5a39-269">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="c5a39-270">Требования к прямому трафику мультимедиа (между клиентом Teams и SBC)</span><span class="sxs-lookup"><span data-stu-id="c5a39-270">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="c5a39-271">Клиент должен иметь доступ к указанным портам (см. таблицу) на общедоступном IP-адресе SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-271">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="c5a39-272">Примечание. Если клиент находится во внутренней сети, он перетекает на общедоступный IP-адрес SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-272">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="c5a39-273">Вы можете настроить закрепление на устройстве NAT таким образом, чтобы трафик никогда не покидает сетевое оборудование предприятия.</span><span class="sxs-lookup"><span data-stu-id="c5a39-273">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="c5a39-274">Дорож</span><span class="sxs-lookup"><span data-stu-id="c5a39-274">Traffic</span></span> | <span data-ttu-id="c5a39-275">От</span><span class="sxs-lookup"><span data-stu-id="c5a39-275">From</span></span> | <span data-ttu-id="c5a39-276">До</span><span class="sxs-lookup"><span data-stu-id="c5a39-276">To</span></span> | <span data-ttu-id="c5a39-277">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="c5a39-277">Source port</span></span> | <span data-ttu-id="c5a39-278">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="c5a39-278">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="c5a39-279">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c5a39-279">UDP/SRTP</span></span> | <span data-ttu-id="c5a39-280">Клиент</span><span class="sxs-lookup"><span data-stu-id="c5a39-280">Client</span></span> | <span data-ttu-id="c5a39-281">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="c5a39-281">SBC</span></span> | <span data-ttu-id="c5a39-282">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="c5a39-282">50 000 – 50 019</span></span>  | <span data-ttu-id="c5a39-283">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="c5a39-283">Defined on the SBC</span></span> |
| <span data-ttu-id="c5a39-284">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c5a39-284">UDP/SRTP</span></span> | <span data-ttu-id="c5a39-285">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="c5a39-285">SBC</span></span> | <span data-ttu-id="c5a39-286">Клиент</span><span class="sxs-lookup"><span data-stu-id="c5a39-286">Client</span></span> | <span data-ttu-id="c5a39-287">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="c5a39-287">Defined on the SBC</span></span> | <span data-ttu-id="c5a39-288">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="c5a39-288">50 000 – 50 019</span></span>  |


<span data-ttu-id="c5a39-289">Примечание. Если у вас есть сетевое устройство, преобразующее исходные порты клиента, убедитесь, что переведенные порты открыты между сетевым оборудованием и SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-289">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="c5a39-290">Требования для использования ретрансляции транспорта</span><span class="sxs-lookup"><span data-stu-id="c5a39-290">Requirements for using Transport Relays</span></span>

<span data-ttu-id="c5a39-291">Транспортные ретрансляции находятся в том же диапазоне, что и процессоры мультимедиа (для случаев, когда не обходится):</span><span class="sxs-lookup"><span data-stu-id="c5a39-291">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="c5a39-292">Среды Office 365 и Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="c5a39-292">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="c5a39-293">-52.112.0.0/14 (IP-адреса из 52.112.0.1 в 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="c5a39-293">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="c5a39-294">Среда Microsoft 365 GCC с неиспользуемой по требованию</span><span class="sxs-lookup"><span data-stu-id="c5a39-294">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="c5a39-295">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="c5a39-295">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="c5a39-296">Office 365 GCC High (среда)</span><span class="sxs-lookup"><span data-stu-id="c5a39-296">Office 365 GCC High environment</span></span>

- <span data-ttu-id="c5a39-297">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="c5a39-297">52.127.88.0/21</span></span>


<span data-ttu-id="c5a39-298">Диапазон портов для реле транспорта Teams (применимо ко всем средам) приведен в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="c5a39-298">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="c5a39-299">Дорож</span><span class="sxs-lookup"><span data-stu-id="c5a39-299">Traffic</span></span> | <span data-ttu-id="c5a39-300">От</span><span class="sxs-lookup"><span data-stu-id="c5a39-300">From</span></span> | <span data-ttu-id="c5a39-301">До</span><span class="sxs-lookup"><span data-stu-id="c5a39-301">To</span></span> | <span data-ttu-id="c5a39-302">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="c5a39-302">Source port</span></span> | <span data-ttu-id="c5a39-303">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="c5a39-303">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="c5a39-304">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c5a39-304">UDP/SRTP</span></span> | <span data-ttu-id="c5a39-305">Транспортные ретрансляции</span><span class="sxs-lookup"><span data-stu-id="c5a39-305">Transport Relay</span></span> | <span data-ttu-id="c5a39-306">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="c5a39-306">SBC</span></span> | <span data-ttu-id="c5a39-307">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="c5a39-307">50 000 -59 999</span></span>    | <span data-ttu-id="c5a39-308">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="c5a39-308">Defined on the SBC</span></span> |
| <span data-ttu-id="c5a39-309">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c5a39-309">UDP/SRTP</span></span> | <span data-ttu-id="c5a39-310">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="c5a39-310">SBC</span></span> | <span data-ttu-id="c5a39-311">Транспортные ретрансляции</span><span class="sxs-lookup"><span data-stu-id="c5a39-311">Transport Relay</span></span> | <span data-ttu-id="c5a39-312">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="c5a39-312">Defined on the SBC</span></span> | <span data-ttu-id="c5a39-313">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="c5a39-313">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="c5a39-314">Примечание. Корпорация Microsoft рекомендует по крайней мере два порта для одновременных звонков на SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-314">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="c5a39-315">Так как корпорация Майкрософт использует две версии реле транспорта, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c5a39-315">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="c5a39-316">V4, которая может работать только с диапазоном портов 50 000 – 59 999</span><span class="sxs-lookup"><span data-stu-id="c5a39-316">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="c5a39-317">V6, которые работают с портами 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="c5a39-317">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="c5a39-318">В настоящее время обход мультимедиа поддерживает только версию v4 для реле транспорта.</span><span class="sxs-lookup"><span data-stu-id="c5a39-318">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="c5a39-319">Мы будем поддерживать версию V6 в будущем.</span><span class="sxs-lookup"><span data-stu-id="c5a39-319">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="c5a39-320">Для перехода вам нужно открыть порты 3478 и 3479.</span><span class="sxs-lookup"><span data-stu-id="c5a39-320">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="c5a39-321">Если корпорация Майкрософт предоставляет поддержку для ретрансляции протокола V6 с пропуском мультимедиа, вам не нужно будет перенастраивать сетевое оборудование или SBCs.</span><span class="sxs-lookup"><span data-stu-id="c5a39-321">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="c5a39-322">Требования для использования процессоров мультимедиа</span><span class="sxs-lookup"><span data-stu-id="c5a39-322">Requirements for using media processors</span></span>

<span data-ttu-id="c5a39-323">Процессоры мультимедиа всегда находятся в пути к файлам мультимедиа для голосовых приложений и веб-клиентов (например, клиенты Teams в EDGE или Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="c5a39-323">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="c5a39-324">Требования те же, что и для конфигурации без обхода.</span><span class="sxs-lookup"><span data-stu-id="c5a39-324">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="c5a39-325">Диапазон IP-адресов для мультимедийного трафика:</span><span class="sxs-lookup"><span data-stu-id="c5a39-325">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="c5a39-326">Среды Office 365 и Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="c5a39-326">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="c5a39-327">-52.112.0.0/14 (IP-адреса из 52.112.0.1 в 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="c5a39-327">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="c5a39-328">Среда Microsoft 365 GCC с неиспользуемой по требованию</span><span class="sxs-lookup"><span data-stu-id="c5a39-328">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="c5a39-329">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="c5a39-329">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="c5a39-330">Office 365 GCC High (среда)</span><span class="sxs-lookup"><span data-stu-id="c5a39-330">Office 365 GCC High environment</span></span>

- <span data-ttu-id="c5a39-331">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="c5a39-331">52.127.88.0/21</span></span>

<span data-ttu-id="c5a39-332">В приведенной ниже таблице указаны диапазон портов для процессоров мультимедиа (применимо ко всем средам).</span><span class="sxs-lookup"><span data-stu-id="c5a39-332">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="c5a39-333">Дорож</span><span class="sxs-lookup"><span data-stu-id="c5a39-333">Traffic</span></span> | <span data-ttu-id="c5a39-334">От</span><span class="sxs-lookup"><span data-stu-id="c5a39-334">From</span></span> | <span data-ttu-id="c5a39-335">До</span><span class="sxs-lookup"><span data-stu-id="c5a39-335">To</span></span> | <span data-ttu-id="c5a39-336">Исходный порт</span><span class="sxs-lookup"><span data-stu-id="c5a39-336">Source port</span></span> | <span data-ttu-id="c5a39-337">Конечный порт</span><span class="sxs-lookup"><span data-stu-id="c5a39-337">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="c5a39-338">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c5a39-338">UDP/SRTP</span></span> | <span data-ttu-id="c5a39-339">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="c5a39-339">Media Processor</span></span> | <span data-ttu-id="c5a39-340">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="c5a39-340">SBC</span></span> | <span data-ttu-id="c5a39-341">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="c5a39-341">49 152 – 53 247</span></span>    | <span data-ttu-id="c5a39-342">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="c5a39-342">Defined on the SBC</span></span> |
| <span data-ttu-id="c5a39-343">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c5a39-343">UDP/SRTP</span></span> | <span data-ttu-id="c5a39-344">БАЙТОВ</span><span class="sxs-lookup"><span data-stu-id="c5a39-344">SBC</span></span> | <span data-ttu-id="c5a39-345">Процессор мультимедиа</span><span class="sxs-lookup"><span data-stu-id="c5a39-345">Media Processor</span></span> | <span data-ttu-id="c5a39-346">Определено для SBC</span><span class="sxs-lookup"><span data-stu-id="c5a39-346">Defined on the SBC</span></span> | <span data-ttu-id="c5a39-347">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="c5a39-347">49 152 – 53 247</span></span>     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a><span data-ttu-id="c5a39-348">Что нужно знать, если у вас есть телефоны Skype для бизнеса в сети</span><span class="sxs-lookup"><span data-stu-id="c5a39-348">Considerations if you have Skype for Business phones in your network</span></span>  

<span data-ttu-id="c5a39-349">Если у вас есть конечные точки Skype для бизнеса в сети, в которой используется прямая маршрутизация (например, у пользователя Teams может быть телефон 3PIP, основанный на клиенте Skype для бизнеса) — обход мультимедиа на магистральной магистрали, которая служит для отключения этих пользователей, должна быть отключена.</span><span class="sxs-lookup"><span data-stu-id="c5a39-349">If you have any Skype for Business end points in your network that are using Direct Routing--for example, a Teams user can have a 3PIP phone that is based on Skype for Business client--the media bypass on the trunk that serves these users must be turned off.</span></span>

<span data-ttu-id="c5a39-350">Вы можете создать отдельную магистральную систему для этих пользователей и назначить ей политику сетевой голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="c5a39-350">You can create a separate trunk for these users and assign it an Online Voice Routing policy.</span></span>

<span data-ttu-id="c5a39-351">Этапы настройки высокого уровня:</span><span class="sxs-lookup"><span data-stu-id="c5a39-351">High-level configuration steps:</span></span>

- <span data-ttu-id="c5a39-352">Разделение пользователей по типу — в зависимости от того, есть ли у пользователя телефон 3PIP или нет.</span><span class="sxs-lookup"><span data-stu-id="c5a39-352">Split users by type – depending on whether the user has a 3PIP phone or not.</span></span>

- <span data-ttu-id="c5a39-353">Создайте два канала для разных полных доменных имен: один включен для обхода мультимедиа. другой not.</span><span class="sxs-lookup"><span data-stu-id="c5a39-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="c5a39-354">Оба канала указывают на один и тот же SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="c5a39-355">Сигналы порта для TLS SIP должны быть разными.</span><span class="sxs-lookup"><span data-stu-id="c5a39-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="c5a39-356">Порты для мультимедиа должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="c5a39-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="c5a39-357">Назначьте правильный магистрали в зависимости от типа пользователя в политике голосовой маршрутизации в сети.</span><span class="sxs-lookup"><span data-stu-id="c5a39-357">Assign the correct trunk depending on the type of the user in the Online Voice Routing policy.</span></span>

<span data-ttu-id="c5a39-358">В примере ниже показана эта логика.</span><span class="sxs-lookup"><span data-stu-id="c5a39-358">The example below illustrates this logic.</span></span>

| <span data-ttu-id="c5a39-359">Набор пользователей</span><span class="sxs-lookup"><span data-stu-id="c5a39-359">Set of users</span></span> | <span data-ttu-id="c5a39-360">Количество пользователей</span><span class="sxs-lookup"><span data-stu-id="c5a39-360">Number of users</span></span> | <span data-ttu-id="c5a39-361">Полные доменные имена для магистрали, назначенные в ОВРП</span><span class="sxs-lookup"><span data-stu-id="c5a39-361">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="c5a39-362">Обход мультимедиа включен</span><span class="sxs-lookup"><span data-stu-id="c5a39-362">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="c5a39-363">Пользователи с клиентами Teams и 3PIPными телефонами</span><span class="sxs-lookup"><span data-stu-id="c5a39-363">Users with Teams clients and 3PIP phones</span></span> | <span data-ttu-id="c5a39-364">средняя</span><span class="sxs-lookup"><span data-stu-id="c5a39-364">20</span></span> | <span data-ttu-id="c5a39-365">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="c5a39-365">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="c5a39-366">false</span><span class="sxs-lookup"><span data-stu-id="c5a39-366">false</span></span> | 
<span data-ttu-id="c5a39-367">Пользователи, у которых есть только конечные точки групп (в том числе новые телефоны, сертифицированные для Teams)</span><span class="sxs-lookup"><span data-stu-id="c5a39-367">Users with only Teams end points (including new phones certified for Teams)</span></span> | <span data-ttu-id="c5a39-368">980</span><span class="sxs-lookup"><span data-stu-id="c5a39-368">980</span></span> | <span data-ttu-id="c5a39-369">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="c5a39-369">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="c5a39-370">true</span><span class="sxs-lookup"><span data-stu-id="c5a39-370">true</span></span>

<span data-ttu-id="c5a39-371">Обе магистральные линии могут указывать на один и тот же SBC с одинаковым общим IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="c5a39-371">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="c5a39-372">Порты TLS-сигналов на SBC должны отличаться, как показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="c5a39-372">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="c5a39-373">Примечание. необходимо убедиться, что ваш сертификат поддерживает обе магистральные линии.</span><span class="sxs-lookup"><span data-stu-id="c5a39-373">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="c5a39-374">В сети SAN необходимо иметь два имени (**sbc1.contoso.com** и **sbc2.contoso.com**) или использовать подстановочный сертификат.</span><span class="sxs-lookup"><span data-stu-id="c5a39-374">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![Обе магистральные линии могут указывать на один и тот же SBC с одинаковым общим IP-адресом.](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="c5a39-376">Сведения о том, как настроить две магистральные линии на одном SBC, можно найти в документации, предоставленной вашим поставщиком SBC.</span><span class="sxs-lookup"><span data-stu-id="c5a39-376">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="c5a39-377">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="c5a39-377">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="c5a39-378">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="c5a39-378">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="c5a39-379">Документация по развертыванию связи с лентой</span><span class="sxs-lookup"><span data-stu-id="c5a39-379">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="c5a39-380">Документация по развертыванию системы TE (аниноде)</span><span class="sxs-lookup"><span data-stu-id="c5a39-380">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="c5a39-381">Конечные точки клиента, поддерживаемые при обходе мультимедиа</span><span class="sxs-lookup"><span data-stu-id="c5a39-381">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="c5a39-382">Обход мультимедиа поддерживается всеми конечными точками Teams.</span><span class="sxs-lookup"><span data-stu-id="c5a39-382">Media bypass is supported with all Teams endpoints.</span></span>

<span data-ttu-id="c5a39-383">Примечание для веб-клиентов (Teams Web App в Microsoft EDGE, Google Chrome или Mozilla Firefox) мы будем переключаться на вызов без обобщения даже в том случае, если он был запущен как обходной вызов.</span><span class="sxs-lookup"><span data-stu-id="c5a39-383">Note for web clients (Teams Web app in Microsoft Edge, Google Chrome or Mozilla Firefox) we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="c5a39-384">Это происходит автоматически и не требует каких – либо действий от администратора.</span><span class="sxs-lookup"><span data-stu-id="c5a39-384">This happens automatically and does not require any actions from the administrator.</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="c5a39-385">См. также</span><span class="sxs-lookup"><span data-stu-id="c5a39-385">See also</span></span>

[<span data-ttu-id="c5a39-386">Настройка обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="c5a39-386">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



