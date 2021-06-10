---
title: Прямая маршрутизация телефонной системы
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Протоколы прямой маршрутии
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569207"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="724a0-103">Прямая маршрутная маршрутия: определения и стандарты RFC</span><span class="sxs-lookup"><span data-stu-id="724a0-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="724a0-104">В этой статье описано Телефон (Майкрософт) как в системе Direct Routing реализованы стандартные протоколы RFC.</span><span class="sxs-lookup"><span data-stu-id="724a0-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="724a0-105">Эта статья предназначена для администраторов голосовой связи, которые отвечают за настройку подключения между локальной службой пограничного контроллера сеанса (SBC) и прокси-службой SIP.</span><span class="sxs-lookup"><span data-stu-id="724a0-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="724a0-106">Интерфейс SBC клиента со следующими компонентами в Microsoft Teams интерфейса:</span><span class="sxs-lookup"><span data-stu-id="724a0-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="724a0-107">**Прокси-сервер SIP** для сигнального сигнала.</span><span class="sxs-lookup"><span data-stu-id="724a0-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="724a0-108">Это интернет-компонент прямой маршрутики, обрабатывающий подключения SIP (TLS) между SBCs и Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="724a0-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="724a0-109">**Процессоры мультимедиа** для мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="724a0-109">**The media processors** for media.</span></span> <span data-ttu-id="724a0-110">Это интернет-компонент прямой маршрутии, обрабатывающий трафик мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="724a0-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="724a0-111">Этот компонент использует протоколы SRTP и SRTCP.</span><span class="sxs-lookup"><span data-stu-id="724a0-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="724a0-112">Дополнительные сведения о прямой маршрутике см. в телефонная система [Прямой маршрут.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="724a0-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="724a0-113">Дополнительные сведения о внедрении протокола SIP direct Routing см. в этой [ссылке.](direct-routing-protocols-sip.md)</span><span class="sxs-lookup"><span data-stu-id="724a0-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="724a0-114">Стандарты RFC</span><span class="sxs-lookup"><span data-stu-id="724a0-114">RFC standards</span></span>

<span data-ttu-id="724a0-115">Прямая маршрутная маршрутия соответствует стандартам RFC.</span><span class="sxs-lookup"><span data-stu-id="724a0-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="724a0-116">SBC, подключенный к прямой маршрутике, также должен соответствовать следующим запросам (или их последователям).</span><span class="sxs-lookup"><span data-stu-id="724a0-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="724a0-117">Стандарты, применимые к устройствам, поддерживаюным режим обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="724a0-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="724a0-118">Следующие стандарты применимы к устройствам, которые поддерживают только режим обхода мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="724a0-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="724a0-119">[SIP RFC 3261:](https://tools.ietf.org/html/rfc3261)протокол session Initiation Protocol</span><span class="sxs-lookup"><span data-stu-id="724a0-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="724a0-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="724a0-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="724a0-121">Частное расширение протокола инициирования сеанса для утверждения удостоверений в доверенных сетях— разделы об обработке заглавных заглавных личных данных С.</span><span class="sxs-lookup"><span data-stu-id="724a0-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="724a0-122">Прямая маршрутная маршрутия отправляет P-Изядле-удостоверение с заглавными идентификаторами конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="724a0-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="724a0-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Расширение протокола SIP для необходимых сведений об истории.</span><span class="sxs-lookup"><span data-stu-id="724a0-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="724a0-124">Дополнительные сведения см. в описании протокола SIP.</span><span class="sxs-lookup"><span data-stu-id="724a0-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="724a0-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Механизм управления протоколом Referred-By сеанса</span><span class="sxs-lookup"><span data-stu-id="724a0-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="724a0-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Заглавный заглавный протокол SIP заменяет</span><span class="sxs-lookup"><span data-stu-id="724a0-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="724a0-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Использование модели предложений и ответов протоколом SIP.</span><span class="sxs-lookup"><span data-stu-id="724a0-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="724a0-128">См. раздел "Отклонения от RFC".</span><span class="sxs-lookup"><span data-stu-id="724a0-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="724a0-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) и [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="724a0-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="724a0-130">Защитите трафик RTP с помощью SRTP.</span><span class="sxs-lookup"><span data-stu-id="724a0-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="724a0-131">SBC должен иметь возможность устанавливать ключи с помощью SDES.</span><span class="sxs-lookup"><span data-stu-id="724a0-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="724a0-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Уточнения предложений и ответов по протоколу SDP для мультиплексинга RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="724a0-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="724a0-133">Стандарты, применимые к устройствам, поддерживаюным режим обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="724a0-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="724a0-134">В дополнение к стандартам, которые перечислены как применимые к режиму обхода, для режима обхода мультимедиа используются следующие стандарты:</span><span class="sxs-lookup"><span data-stu-id="724a0-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="724a0-135">[RFC 5245 Interactive Connectivity Connectivity Уайлдент (ICE) для обхода мультимедиа](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="724a0-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="724a0-136">SBC должен поддерживать следующие следующую поддержку:</span><span class="sxs-lookup"><span data-stu-id="724a0-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="724a0-137">ICE Lite — клиенты Teams являются полными клиентами ICE</span><span class="sxs-lookup"><span data-stu-id="724a0-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="724a0-138">[Ice Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="724a0-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="724a0-139">Дополнительные статью о перезапусках ICE: использование досье и примеры в ice Restart: обход мультимедиа, перенесенный на конечную точку, которая не поддерживает обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="724a0-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="724a0-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="724a0-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="724a0-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), см. разделы 3.1, Forking и 3.2, "Генерация сигнала звонка"</span><span class="sxs-lookup"><span data-stu-id="724a0-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="724a0-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="724a0-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="724a0-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="724a0-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="724a0-144">Стандарты, применимые к поддержке передачи сведений о расположении поставщикам E911</span><span class="sxs-lookup"><span data-stu-id="724a0-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="724a0-145">RFC 6442, передает расположение для протокола session initiation Protocol</span><span class="sxs-lookup"><span data-stu-id="724a0-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="724a0-146">Отклонения от RFC</span><span class="sxs-lookup"><span data-stu-id="724a0-146">Deviations from the RFC's</span></span>

<span data-ttu-id="724a0-147">В следующей таблице перечислены разделы RFC, в которых внедрение SIP или стека мультимедиа отклоняется от стандарта:</span><span class="sxs-lookup"><span data-stu-id="724a0-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="724a0-148">RFC и разделы</span><span class="sxs-lookup"><span data-stu-id="724a0-148">RFC and sections</span></span> | <span data-ttu-id="724a0-149">Описание</span><span class="sxs-lookup"><span data-stu-id="724a0-149">Description</span></span> | <span data-ttu-id="724a0-150">Отклонение</span><span class="sxs-lookup"><span data-stu-id="724a0-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="724a0-151">RFC 6337, раздел 5.3 Удержание и возобновление работы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="724a0-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="724a0-152">С помощью RFC можно использовать "a=inactive", "a=sendonly", a=reclyly" для удержания звонка.</span><span class="sxs-lookup"><span data-stu-id="724a0-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="724a0-153">Прокси-сервер SIP поддерживает только "a=inactive" и не понимает, отправляет ли SBC "a=sendonly" или "a=reclyly".</span><span class="sxs-lookup"><span data-stu-id="724a0-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="724a0-154">RFC 6337, раздел 5.4 "Поведение при получении SDP с c=0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="724a0-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="724a0-155">[Для RFC3264](https://tools.ietf.org/html/rfc3264) требуется, чтобы агент мог принимать SDP с адресом подключения 0.0.0.0. В этом случае ни RTP, ни RTCP не должны быть отправлены на одноранговую связь.</span><span class="sxs-lookup"><span data-stu-id="724a0-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="724a0-156">Прокси-сервер SIP не поддерживает этот параметр.</span><span class="sxs-lookup"><span data-stu-id="724a0-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="724a0-157">Рабочие режимы</span><span class="sxs-lookup"><span data-stu-id="724a0-157">Operational modes</span></span>

<span data-ttu-id="724a0-158">Существует два режима прямой маршрутации:</span><span class="sxs-lookup"><span data-stu-id="724a0-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="724a0-159">**Без обхода мультимедиа,** при котором весь трафик RTP Teams клиент, процессоры мультимедиа и SBC.</span><span class="sxs-lookup"><span data-stu-id="724a0-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="724a0-160">**С обходом мультимедиа,** при котором все потоки мультимедиа RTP Teams конечными точками и SBC.</span><span class="sxs-lookup"><span data-stu-id="724a0-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="724a0-161">Обратите внимание, что трафик SIP всегда проходит через прокси-сервер SIP.</span><span class="sxs-lookup"><span data-stu-id="724a0-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="724a0-162">Dtmf</span><span class="sxs-lookup"><span data-stu-id="724a0-162">DTMF</span></span>
<span data-ttu-id="724a0-163">In-band DTMF is not supported by media stack.</span><span class="sxs-lookup"><span data-stu-id="724a0-163">In-band DTMF is not supported by media stack.</span></span>
