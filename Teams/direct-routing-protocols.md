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
description: Протоколы прямой маршрутизации
appliesto:
- Microsoft Teams
ms.openlocfilehash: a470c402ebfd4e70955f4e864d45dbaaca476dfd
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065629"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="58cdb-103">Прямые маршруты — определения и стандарты RFC</span><span class="sxs-lookup"><span data-stu-id="58cdb-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="58cdb-104">В этой статье объясняется, как в Microsoft Direct Routing System реализовано использование стандартных протоколов RFC.</span><span class="sxs-lookup"><span data-stu-id="58cdb-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="58cdb-105">Эта статья предназначена для администраторов голосовой связи, которые отвечают за настройку соединения между локальным контроллером границ сеанса (SBC) и прокси-службой протокола запуска сеансов (SIP).</span><span class="sxs-lookup"><span data-stu-id="58cdb-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="58cdb-106">SBC клиента интерфейсов со следующими компонентами в серверной части Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="58cdb-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="58cdb-107">**Прокси-сервер SIP** для сигнализации.</span><span class="sxs-lookup"><span data-stu-id="58cdb-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="58cdb-108">Это Интернет-компонент прямой маршрутизации, который обрабатывает соединения SIP (TLS) между SBCs и прямой маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="58cdb-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="58cdb-109">Мультимедийные **процессоры** .</span><span class="sxs-lookup"><span data-stu-id="58cdb-109">**The media processors** for media.</span></span> <span data-ttu-id="58cdb-110">Это Интернет-компонент прямой маршрутизации, который обрабатывает трафик мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="58cdb-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="58cdb-111">Этот компонент использует протоколы SRTP и СРТКП.</span><span class="sxs-lookup"><span data-stu-id="58cdb-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="58cdb-112">Дополнительные сведения о прямой маршрутизации можно найти в разделе прямая маршрутизация [телефонной системы](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="58cdb-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="58cdb-113">Дополнительные сведения о том, как прямая маршрутизация реализует протокол SIP, можно найти по [протоколу Direct Routing-SIP](direct-routing-protocols-sip.md).</span><span class="sxs-lookup"><span data-stu-id="58cdb-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="58cdb-114">Стандарты RFC</span><span class="sxs-lookup"><span data-stu-id="58cdb-114">RFC standards</span></span>

<span data-ttu-id="58cdb-115">Прямая маршрутизация соответствует стандартам RFC.</span><span class="sxs-lookup"><span data-stu-id="58cdb-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="58cdb-116">SBC, подключенный к прямой маршрутизации, также должен соответствовать следующим документам RFC (или их последователей).</span><span class="sxs-lookup"><span data-stu-id="58cdb-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="58cdb-117">Стандарты, применимые к устройствам, которые поддерживают режим обхода не мультимедиа</span><span class="sxs-lookup"><span data-stu-id="58cdb-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="58cdb-118">Следующие стандарты применимы к устройствам, которые поддерживают только режим обхода не мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="58cdb-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="58cdb-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): протокол запуска сеанса</span><span class="sxs-lookup"><span data-stu-id="58cdb-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="58cdb-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="58cdb-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="58cdb-121">Личное расширение протокола инициирования сеанса для утвержденных удостоверений в доверенных сетях — разделы об обработке заголовков P-Assert-Identity.</span><span class="sxs-lookup"><span data-stu-id="58cdb-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="58cdb-122">Прямая маршрутизация отправляет P-утвержденные идентификационные данные с ИДЕНТИФИКАЦИОНными заголовками.</span><span class="sxs-lookup"><span data-stu-id="58cdb-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="58cdb-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Расширение протокола SIP для необходимых сведений о журнале.</span><span class="sxs-lookup"><span data-stu-id="58cdb-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="58cdb-124">Дополнительные сведения можно найти в описании протокола SIP "Маршрутизация".</span><span class="sxs-lookup"><span data-stu-id="58cdb-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="58cdb-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Механизм запуска сеанса, на который ссылается протокол</span><span class="sxs-lookup"><span data-stu-id="58cdb-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="58cdb-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Заголовок "заменяет протоколом запуска сеансов (SIP)"</span><span class="sxs-lookup"><span data-stu-id="58cdb-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="58cdb-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Использование протокола SIP для модели предложения и ответа.</span><span class="sxs-lookup"><span data-stu-id="58cdb-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="58cdb-128">Ознакомьтесь с разделом "отклонение от RFC".</span><span class="sxs-lookup"><span data-stu-id="58cdb-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="58cdb-129">[Rfc 3711](https://tools.ietf.org/html/rfc3711) и [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="58cdb-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="58cdb-130">Защитите трафик RTP с помощью SRTP.</span><span class="sxs-lookup"><span data-stu-id="58cdb-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="58cdb-131">SBC должен иметь возможность устанавливать клавиши с помощью СДЕС.</span><span class="sxs-lookup"><span data-stu-id="58cdb-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="58cdb-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Уточнение и ответные сведения о протоколе описания сеансов (SDP) для мультиплексирования RTP/РТКП</span><span class="sxs-lookup"><span data-stu-id="58cdb-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="58cdb-133">Стандарты, применимые к устройствам, которые поддерживают режим обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="58cdb-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="58cdb-134">В дополнение к стандартам, перечисленным в режиме без обхода, для режима обхода мультимедиа используются следующие стандарты:</span><span class="sxs-lookup"><span data-stu-id="58cdb-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="58cdb-135">[RFC 5245 (ICE) для пропуска мультимедийного](https://tools.ietf.org/html/rfc5245)взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="58cdb-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="58cdb-136">SBC должен поддерживать следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="58cdb-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="58cdb-137">ICE Lite — клиенты Teams являются полноценными клиентами ICE</span><span class="sxs-lookup"><span data-stu-id="58cdb-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="58cdb-138">[Перезапускам Ice](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="58cdb-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="58cdb-139">Дополнительные сведения о возможностях повторного запуска ICE: функция "использовать вариант" и примеры в разделе "перезагрузка". вызов обхода мультимедиа переключен на конечную точку, не поддерживающую обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="58cdb-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="58cdb-140">[Управление вызовами по протоколу SIP rfc 5589 – передача](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="58cdb-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="58cdb-141">[RFC 3960 Early Media и Звонок в протоколе SIP](https://tools.ietf.org/html/rfc3960)— разделы 3,1, разветвления и 3,2, создание звукового звонка</span><span class="sxs-lookup"><span data-stu-id="58cdb-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="58cdb-142">Служебные программы обхода сеанса RFC 5389 для NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="58cdb-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="58cdb-143">Обходные номера для RFC 5766 с помощью ретрансляций в NAT (включение): ретрансляция расширений в служебные программы обхода сеансов для NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="58cdb-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="58cdb-144">Стандарты, применимые для поддержки передачи сведений о расположении поставщикам услуг E911</span><span class="sxs-lookup"><span data-stu-id="58cdb-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="58cdb-145">RFC 6442, передача местоположений для протокола инициирования сеанса</span><span class="sxs-lookup"><span data-stu-id="58cdb-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="58cdb-146">Отклонения от RFC</span><span class="sxs-lookup"><span data-stu-id="58cdb-146">Deviations from the RFC's</span></span>

<span data-ttu-id="58cdb-147">В приведенной ниже таблице перечислены разделы документов RFC, в которых реализация модуля SIP или мультимедийного стека корпорацией Майкрософт отличается от стандарта.</span><span class="sxs-lookup"><span data-stu-id="58cdb-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="58cdb-148">RFC и разделы</span><span class="sxs-lookup"><span data-stu-id="58cdb-148">RFC and sections</span></span> | <span data-ttu-id="58cdb-149">Описание</span><span class="sxs-lookup"><span data-stu-id="58cdb-149">Description</span></span> | <span data-ttu-id="58cdb-150">Отклонение</span><span class="sxs-lookup"><span data-stu-id="58cdb-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="58cdb-151">RFC 6337, раздел 5,3 Хранение и возобновление мультимедиа</span><span class="sxs-lookup"><span data-stu-id="58cdb-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="58cdb-152">RFC допускает использование "a = неактивен", "a = сендонли", a = реквонли "для помещения звонка на удержание.</span><span class="sxs-lookup"><span data-stu-id="58cdb-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="58cdb-153">Прокси-сервер SIP поддерживает только "a = неактивен" и не понимает, отправляет ли SBC "a = сендонли" или "a = реквонли".</span><span class="sxs-lookup"><span data-stu-id="58cdb-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="58cdb-154">RFC 6337, раздел 5,4 "поведение при получении SDP с помощью c = 0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="58cdb-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="58cdb-155">[RFC3264](https://tools.ietf.org/html/rfc3264) требует, чтобы агент получал SDP с адресом соединения 0.0.0.0, в этом случае это означает, что одноранговый канал и рткп не должны отправляться.</span><span class="sxs-lookup"><span data-stu-id="58cdb-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="58cdb-156">Прокси-сервер SIP не поддерживает этот параметр.</span><span class="sxs-lookup"><span data-stu-id="58cdb-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="58cdb-157">Рабочие режимы</span><span class="sxs-lookup"><span data-stu-id="58cdb-157">Operational modes</span></span>

<span data-ttu-id="58cdb-158">Существует два рабочих режима прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="58cdb-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="58cdb-159">**Без пропуска мультимедиа** , в котором весь трафик RTP проходит между клиентом Teams, мультимедийными процессорами и SBC.</span><span class="sxs-lookup"><span data-stu-id="58cdb-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="58cdb-160">**С пропуском мультимедийного содержимого** , в котором все RTP проходит между конечными точками группы и SBC.</span><span class="sxs-lookup"><span data-stu-id="58cdb-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="58cdb-161">Обратите внимание, что трафик SIP всегда проходит через прокси-сервер SIP.</span><span class="sxs-lookup"><span data-stu-id="58cdb-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   
