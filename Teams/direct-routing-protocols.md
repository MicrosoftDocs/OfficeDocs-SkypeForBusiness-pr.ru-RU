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
description: Протоколы прямой маршрутизации
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569207"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="194f0-103">Прямая маршрутизация - Определения и стандарты RFC</span><span class="sxs-lookup"><span data-stu-id="194f0-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="194f0-104">В этой статье описывается, Телефон (Майкрософт) система Direct Routing реализует стандартные протоколы RFC.</span><span class="sxs-lookup"><span data-stu-id="194f0-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="194f0-105">Эта статья предназначена для голосовых администраторов, которые отвечают за настройку связи между на-предупосылок сессии пограничного контроллера (SBC) и протокол сессии (SIP) прокси-сервис.</span><span class="sxs-lookup"><span data-stu-id="194f0-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="194f0-106">Клиент SBC взаимодействует со следующими компонентами в Microsoft Teams бэкэнда:</span><span class="sxs-lookup"><span data-stu-id="194f0-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="194f0-107">**Прокси SIP для** сигнализации.</span><span class="sxs-lookup"><span data-stu-id="194f0-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="194f0-108">Это компонент прямой маршрутизации, который обрабатывает соединения SIP (TLS) между SBCs и Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="194f0-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="194f0-109">**Медиа-процессоры для** мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="194f0-109">**The media processors** for media.</span></span> <span data-ttu-id="194f0-110">Это интернет-компонент Direct Routing, который обрабатывает медиа-трафик.</span><span class="sxs-lookup"><span data-stu-id="194f0-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="194f0-111">Этот компонент использует протоколы SRTP и SRTCP.</span><span class="sxs-lookup"><span data-stu-id="194f0-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="194f0-112">Для получения дополнительной информации о прямой маршрутизации, [телефонная система Прямая маршрутизация](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="194f0-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="194f0-113">Для получения дополнительной информации о том, как Direct Routing реализует протокол SIP, [см.](direct-routing-protocols-sip.md)</span><span class="sxs-lookup"><span data-stu-id="194f0-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="194f0-114">Стандарты RFC</span><span class="sxs-lookup"><span data-stu-id="194f0-114">RFC standards</span></span>

<span data-ttu-id="194f0-115">Прямая маршрутизация соответствует стандартам RFC.</span><span class="sxs-lookup"><span data-stu-id="194f0-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="194f0-116">SBC, подключенный к Direct Routing, должен также соответствовать следующим RFCs (или их преемникам).</span><span class="sxs-lookup"><span data-stu-id="194f0-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="194f0-117">Стандарты, применимые к устройствам, ехавя на устройства, такие как несохуденяемый режим обхода</span><span class="sxs-lookup"><span data-stu-id="194f0-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="194f0-118">Следующие стандарты применимы к устройствам, которые поддерживают только не мультимедиа режим обхода:</span><span class="sxs-lookup"><span data-stu-id="194f0-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="194f0-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Протокол инициирования сессии</span><span class="sxs-lookup"><span data-stu-id="194f0-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="194f0-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="194f0-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="194f0-121">Частное расширение протокола инициирования сессии для утверждений идентификации в доверенных сетях --Разделы об обработке заголовка P-Asserted-Identity.</span><span class="sxs-lookup"><span data-stu-id="194f0-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="194f0-122">Прямая маршрутизация отправляет P-Asserted-Identity с головами Privacy ID.</span><span class="sxs-lookup"><span data-stu-id="194f0-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="194f0-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Расширение Протокола инициации сессии (SIP) для получения необходимой информации по истории.</span><span class="sxs-lookup"><span data-stu-id="194f0-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="194f0-124">Смотрите также: Описание протокола маршрутизации SIP для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="194f0-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="194f0-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Механизм протокола инициации Referred-By сессии</span><span class="sxs-lookup"><span data-stu-id="194f0-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="194f0-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Протокол посвящения сессии (SIP) "Заменяет" заголовок</span><span class="sxs-lookup"><span data-stu-id="194f0-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="194f0-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Протокол инициации сеанса (SIP) Использование модели предложения/ответа.</span><span class="sxs-lookup"><span data-stu-id="194f0-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="194f0-128">Смотрите раздел "Отклонения от RFC".</span><span class="sxs-lookup"><span data-stu-id="194f0-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="194f0-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) и [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="194f0-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="194f0-130">Защитите трафик RTP с помощью SRTP.</span><span class="sxs-lookup"><span data-stu-id="194f0-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="194f0-131">SBC должен быть в состоянии установить ключи с помощью SDES.</span><span class="sxs-lookup"><span data-stu-id="194f0-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="194f0-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Протокол описания сессии (SDP) Предложение/Ответ Разъяснения для МУЛЬТИП/RTCP Multiplexing</span><span class="sxs-lookup"><span data-stu-id="194f0-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="194f0-133">Стандарты, применимые к устройствам, ехавам в режиме обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="194f0-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="194f0-134">В дополнение к стандартам, перечисленным в режиме необвода, для режима обхода мультимедиа используются следующие стандарты:</span><span class="sxs-lookup"><span data-stu-id="194f0-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="194f0-135">[RFC 5245 Интерактивная связь создание (ICE) для средств массовой информации обойти](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="194f0-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="194f0-136">SBC должен поддерживать следующее:</span><span class="sxs-lookup"><span data-stu-id="194f0-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="194f0-137">ICE Lite - Teams клиенты являются полноправными клиентами ICE</span><span class="sxs-lookup"><span data-stu-id="194f0-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="194f0-138">[ICE перезапускает](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="194f0-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="194f0-139">Подробнее о перезапуске ICE случая использования и примеров в ICE Restart: Медиа-обход вызова перенесен в конечную точку, которая не поддерживает обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="194f0-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="194f0-140">[RFC RFC 5589 Протокол инициирования сессии (SIP) Управление вызовом - Передача](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="194f0-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="194f0-141">[RFC 3960 Ранние средства массовой информации и звон тон поколения в протоколе инициации сессии (SIP)](https://tools.ietf.org/html/rfc3960), см. разделы 3.1, Forking, и 3.2, Звенящий тон поколения</span><span class="sxs-lookup"><span data-stu-id="194f0-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="194f0-142">RFC 5389 Сессия Обход Утилиты для NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="194f0-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="194f0-143">RFC 5766 Обход с использованием ретрансляторов вокруг NAT (TURN): Реле Расширения сессии Обход Утилиты для NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="194f0-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="194f0-144">Стандарты, применимые к поддержке передачи информации о местоположении поставщикам E911</span><span class="sxs-lookup"><span data-stu-id="194f0-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="194f0-145">RFC 6442, Транспортировка местонахождения для Протокола инициации сессии</span><span class="sxs-lookup"><span data-stu-id="194f0-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="194f0-146">Отклонения от RFC</span><span class="sxs-lookup"><span data-stu-id="194f0-146">Deviations from the RFC's</span></span>

<span data-ttu-id="194f0-147">В следующей таблице перечислены разделы RFC (ы), в которых реализация Microsoft SIP или медиа-стека отклоняется от стандарта:</span><span class="sxs-lookup"><span data-stu-id="194f0-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="194f0-148">RFC и разделы</span><span class="sxs-lookup"><span data-stu-id="194f0-148">RFC and sections</span></span> | <span data-ttu-id="194f0-149">Описание</span><span class="sxs-lookup"><span data-stu-id="194f0-149">Description</span></span> | <span data-ttu-id="194f0-150">отклонение</span><span class="sxs-lookup"><span data-stu-id="194f0-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="194f0-151">RFC 6337, раздел 5.3 Удержание и возобновление СМИ</span><span class="sxs-lookup"><span data-stu-id="194f0-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="194f0-152">RFC позволяет использовать "a'inactive", "a'sendonly", a'recvonly", чтобы позвонить на удержание.</span><span class="sxs-lookup"><span data-stu-id="194f0-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="194f0-153">Прокси-сервер SIP поддерживает только "a'inactive" и не понимает, отправляет ли SBC "a'sendonly" или "a'recvonly".</span><span class="sxs-lookup"><span data-stu-id="194f0-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="194f0-154">RFC 6337, раздел 5.4 "Поведение при приеме СДП с c'0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="194f0-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="194f0-155">[RFC3264](https://tools.ietf.org/html/rfc3264) требует, чтобы агент был способен получать SDP с адресом соединения 0.0.0.0, и это означает, что ни RTP, ни RTCP не должны быть отправлены сверстнику.</span><span class="sxs-lookup"><span data-stu-id="194f0-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="194f0-156">Прокси SIP не поддерживает эту опцию.</span><span class="sxs-lookup"><span data-stu-id="194f0-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="194f0-157">Режимы работы</span><span class="sxs-lookup"><span data-stu-id="194f0-157">Operational modes</span></span>

<span data-ttu-id="194f0-158">Существует два режима работы для прямой маршрутизации:</span><span class="sxs-lookup"><span data-stu-id="194f0-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="194f0-159">**Без средств массовой** информации обойти, в котором все потоки трафика RTP Teams клиентом, медиа-процессоров и SBC.</span><span class="sxs-lookup"><span data-stu-id="194f0-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="194f0-160">**С обходом средств** массовой информации, в котором все средства массовой информации TEAMS конечных точек и SBC.</span><span class="sxs-lookup"><span data-stu-id="194f0-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="194f0-161">Обратите внимание, что sip трафик всегда течет через прокси SIP.</span><span class="sxs-lookup"><span data-stu-id="194f0-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="194f0-162">DTMF</span><span class="sxs-lookup"><span data-stu-id="194f0-162">DTMF</span></span>
<span data-ttu-id="194f0-163">In-диапазон DTMF не поддерживается медиа стеком.</span><span class="sxs-lookup"><span data-stu-id="194f0-163">In-band DTMF is not supported by media stack.</span></span>
