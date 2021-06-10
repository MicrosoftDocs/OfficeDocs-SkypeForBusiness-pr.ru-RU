---
title: Прямая маршрутизация телефонной системы
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888578"
---
# <a name="overview"></a><span data-ttu-id="41dd4-103">Обзор</span><span class="sxs-lookup"><span data-stu-id="41dd4-103">Overview</span></span>

<span data-ttu-id="41dd4-104">В этой статье описано, как прямая маршрутизирование поддерживает обход мультимедиа с помощью контроллера границы сеанса (SBC) для ICE Lite, как описано в [RFC 5245.](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="41dd4-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="41dd4-105">Эта статья предназначена для администраторов голосовой связи, которые отвечают за настройку подключения между локальной службой SBC и прокси-службой SIP.</span><span class="sxs-lookup"><span data-stu-id="41dd4-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="41dd4-106">В этой статье приводится обзор сценариев ICE Lite и требований для обеспечения взаимосвязи.</span><span class="sxs-lookup"><span data-stu-id="41dd4-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="41dd4-107">В этой статье описаны форматы сообщений и необходимые переходы между компьютерами для обеспечения надежного потока звонка и передачи мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="41dd4-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="41dd4-108">Терминологии</span><span class="sxs-lookup"><span data-stu-id="41dd4-108">Terminology</span></span>

- <span data-ttu-id="41dd4-109">First Hello — первые слова, произнесенные звонив и звонив.</span><span class="sxs-lookup"><span data-stu-id="41dd4-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="41dd4-110">Важно сделать все возможное, чтобы обеспечить надежное доставку первых пакетов с конечных точек в большинстве случаев использования.</span><span class="sxs-lookup"><span data-stu-id="41dd4-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="41dd4-111">Forking — предложение от вызываемой стороны может быть доставлено на несколько конечных точек, если вызывающий пользователь доступен на нескольких устройствах (например, пользователь Teams может быть подписан на Teams для Windows и Teams для Android или iPhone).</span><span class="sxs-lookup"><span data-stu-id="41dd4-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="41dd4-112">Временный ответ (183). Конечные точки для ускорения настройки звонка отправят ответ с кандидатами и ключами, необходимыми для настройки потока мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="41dd4-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="41dd4-113">Это делается в том случае, если пользователь может ответить на звонок (200OK) из определенного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="41dd4-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="41dd4-114">При помощи функции предварительного вызова вызывающий должен быть готов получить несколько предварительных ответов.</span><span class="sxs-lookup"><span data-stu-id="41dd4-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="41dd4-115">Re-Invite — предложение с конечными кандидатами, выбранными управляющей конечной точкой ICE.</span><span class="sxs-lookup"><span data-stu-id="41dd4-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="41dd4-116">Атрибут a=remote-candidate будет иметь атрибут a=remote-candidate, чтобы устранить любые условия соревнований при обработке нескольких вилок.</span><span class="sxs-lookup"><span data-stu-id="41dd4-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="41dd4-117">Teams Конечная точка: это может быть сервер (процессор мультимедиа, ретранслятор транспорта) или Teams сервер.</span><span class="sxs-lookup"><span data-stu-id="41dd4-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="41dd4-118">Формат сообщения</span><span class="sxs-lookup"><span data-stu-id="41dd4-118">Message format</span></span>

<span data-ttu-id="41dd4-119">Инфраструктура Teams за RFC 5245 для ICE-Lite.</span><span class="sxs-lookup"><span data-stu-id="41dd4-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="41dd4-120">Это подразумевает, что все сообщения STUN соответствуют [RFC 5389.](https://tools.ietf.org/html/rfc5389)</span><span class="sxs-lookup"><span data-stu-id="41dd4-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="41dd4-121">В SBCs, как требуется RFC 5389, необходимо игнорировать все атрибуты STUN, которые они не распознают, и продолжать обрабатывать сообщения с известными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="41dd4-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="41dd4-122">При получении неформатированной упаковки пакеты необходимо удалить, не влияя на сеанс мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="41dd4-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="41dd4-123">Требования ICE Lite</span><span class="sxs-lookup"><span data-stu-id="41dd4-123">ICE Lite requirements</span></span>

<span data-ttu-id="41dd4-124">В этом разделе кратко фиксироваться требования для ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="41dd4-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="41dd4-125">Соищание кандидатов</span><span class="sxs-lookup"><span data-stu-id="41dd4-125">Candidate gathering</span></span>

<span data-ttu-id="41dd4-126">В SBC должен быть только один кандидат, с который можно будет связаться с общественностью.</span><span class="sxs-lookup"><span data-stu-id="41dd4-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="41dd4-127">В настоящее время поддерживается только IPV4-кандидатов.</span><span class="sxs-lookup"><span data-stu-id="41dd4-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="41dd4-128">Проверки подключения</span><span class="sxs-lookup"><span data-stu-id="41dd4-128">Connectivity checks</span></span>

<span data-ttu-id="41dd4-129">Внедрение ICE Lite должно реагировать на все полученные проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="41dd4-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="41dd4-130">Конечная точка ICE Lite не должна отправлять запросы на проверку подключения.</span><span class="sxs-lookup"><span data-stu-id="41dd4-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="41dd4-131">(Если проверки подключения отправляются с нарушением, будет реагировать полная реализация, что может привести к обнаружению потенциальных кандидатов, которые не являются однорангами, и, возможно, привести к сбоям звонка.)</span><span class="sxs-lookup"><span data-stu-id="41dd4-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="41dd4-132">Номинациях</span><span class="sxs-lookup"><span data-stu-id="41dd4-132">Nominations</span></span>

<span data-ttu-id="41dd4-133">Конечной точкой полной реализации ICE всегда будет контрольная конечная точка, и она будет следовать за "обычными" наблюдениями за выбором конечных кандидатов, которые будут использоваться для потока мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="41dd4-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="41dd4-134">Конечная точка ICE Lite может использовать эти средства, чтобы завершить путь к использованию мультимедиа и завершить вызов.</span><span class="sxs-lookup"><span data-stu-id="41dd4-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="41dd4-135">Примечание. Если одноранговые конечные точки отправляют 183 предварительных ответа, SBC должен быть готов к реагированию на проверки с нескольких конечных точек, а также с нескольких конечных точек, если до 200 года произойдет такое же количество ответов.</span><span class="sxs-lookup"><span data-stu-id="41dd4-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="41dd4-136">В зависимости от сходимости компьютера ice к конечному пути и времени ответа пользователя, эти действия могут произойти до или после 200OK.</span><span class="sxs-lookup"><span data-stu-id="41dd4-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="41dd4-137">У SBC должна быть возможность обработки обоих случаев.</span><span class="sxs-lookup"><span data-stu-id="41dd4-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="41dd4-138">Сходящиеся для разгона</span><span class="sxs-lookup"><span data-stu-id="41dd4-138">Converging for forking</span></span>

<span data-ttu-id="41dd4-139">Если предложение SBC для нескольких конечных точек Teams, Teams могут отвечать с помощью предварительного ответа и запуска проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="41dd4-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="41dd4-140">SBC должен быть подготовлен к приему проверок подключения и реагированию на проверки подключения с нескольких конечных точек.</span><span class="sxs-lookup"><span data-stu-id="41dd4-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="41dd4-141">Например, можно Teams на рабочий стол и мобильный телефон.</span><span class="sxs-lookup"><span data-stu-id="41dd4-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="41dd4-142">Оба устройства будут уведомлены о входящий звонок и попытаются проверки подключения к SBC.</span><span class="sxs-lookup"><span data-stu-id="41dd4-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="41dd4-143">В конечном итоге только одна из конечных точек ответит на звонок (200OK).</span><span class="sxs-lookup"><span data-stu-id="41dd4-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="41dd4-144">Получив пакет 200OK, SBC может настроить контекст для обработки пакетов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="41dd4-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="41dd4-145">Scenarios</span><span class="sxs-lookup"><span data-stu-id="41dd4-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="41dd4-146">Входящий звонок из SBC</span><span class="sxs-lookup"><span data-stu-id="41dd4-146">Inbound call from SBC</span></span>

<span data-ttu-id="41dd4-147">В этом сценарии существует несколько конечных точек, которые должны обрабатываться СКА.</span><span class="sxs-lookup"><span data-stu-id="41dd4-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="41dd4-148">Как правило, конечные точки сервера отвечают напрямую с помощью 200OK.</span><span class="sxs-lookup"><span data-stu-id="41dd4-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="41dd4-149">Это полные конечные точки ICE, которые обычно участвуют в сценариях голосовой почты, очереди зовов и автоответчиков.</span><span class="sxs-lookup"><span data-stu-id="41dd4-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="41dd4-150">Клиентские конечные точки могут отправлять несколько предварительных ответов с разными тегами "От" и "На" (183), за которыми следует 200OK с конечной точки, которая отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="41dd4-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="41dd4-151">Это полные конечные точки ICE, которые обычно представляют клиенты конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="41dd4-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="41dd4-152">Другие конечные точки SBC.</span><span class="sxs-lookup"><span data-stu-id="41dd4-152">Other SBC endpoints.</span></span> <span data-ttu-id="41dd4-153">Это конечные точки ICE Lite, обычно участвующие в сценарии одновременных звонков на конечные точки клиента и другие телефонные номера.</span><span class="sxs-lookup"><span data-stu-id="41dd4-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="41dd4-154">SBC должен отвечать на все запросы проверки подключения, полученные от полных конечных точек ICE.</span><span class="sxs-lookup"><span data-stu-id="41dd4-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="41dd4-155">В RFC полные конечные точки ICE становятся контрольным конечными точками.</span><span class="sxs-lookup"><span data-stu-id="41dd4-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="41dd4-156">Конечные Teams (клиент или сервер) выполняют "обычные" проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="41dd4-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="41dd4-157">Итоговая 200Ok может быть либо с конечной точки, отправив раннее мультимедиа, либо с другой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="41dd4-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="41dd4-158">При получении 200Ok SBC должен настроить контекст для потока мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="41dd4-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="41dd4-159">Ранние мультимедиа</span><span class="sxs-lookup"><span data-stu-id="41dd4-159">Early media</span></span>

<span data-ttu-id="41dd4-160">Если имеется ранний поток мультимедиа, SBC должен быть защелковым к первой конечной точке, которая запускает потоковую передачу мультимедиа; Поток мультимедиа может начаться до того, как будут назначены кандидаты.</span><span class="sxs-lookup"><span data-stu-id="41dd4-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="41dd4-161">На этом этапе SBC должен поддерживать отправку DTMF, чтобы включить сценарии IVR и голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="41dd4-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="41dd4-162">В SBC следует использовать путь с наивысшим приоритетом, по которому он получает проверки, если не завершены проверки.</span><span class="sxs-lookup"><span data-stu-id="41dd4-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="41dd4-163">Исходящие вызовы на SBC</span><span class="sxs-lookup"><span data-stu-id="41dd4-163">Outbound call to SBC</span></span>

<span data-ttu-id="41dd4-164">Конечные Teams являются вызывающим в этом сценарии и будут контрольной конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="41dd4-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="41dd4-165">При получении предварительного ответа (183) или окончательного ответа (200OK) конечная точка Teams проверки подключения и переназначатся на обычные, чтобы завершить проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="41dd4-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="41dd4-166">Примечание. Если SBC отправляет предварительный ответ (183), он должен быть готов получать запросы на проверку подключения и, возможно, завершить проверку перед отправкой 200OK.</span><span class="sxs-lookup"><span data-stu-id="41dd4-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="41dd4-167">Если проверки и(или) проверки выполняются до 2000 г., то проверки и/или заве- иные проверки не будут выполняться повторно после 200 года.</span><span class="sxs-lookup"><span data-stu-id="41dd4-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="41dd4-168">SBC не должен изменять ice candidates, password и ufrag (фрагмент имени пользователя) между 183 и 200.</span><span class="sxs-lookup"><span data-stu-id="41dd4-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="41dd4-169">Чтобы поддерживать ранние передачи мультимедиа, SBC может начать потоковую передачу мультимедиа для однорангового соискца ICE с наивысшим приоритетом на основе полученных проверок подключения, даже если до того, как Teams конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="41dd4-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="41dd4-170">В SBC следует ожидать, что Teams со всех кандидатов, пока не будут завершены все кандидаты.</span><span class="sxs-lookup"><span data-stu-id="41dd4-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="41dd4-171">После того как будет назначен кандидат, SBC должен восстановить контекст, чтобы отправлять и получать пакеты мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="41dd4-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="41dd4-172">Требования к поддержке SRTP</span><span class="sxs-lookup"><span data-stu-id="41dd4-172">SRTP support requirements</span></span>

<span data-ttu-id="41dd4-173">SBC должен поддерживать шифрование шифров SRTP AES_CM_128_HMAC_SHA1_80 для предложения и ответа в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="41dd4-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="41dd4-174">Ниже приводится пример криптографа в предложении SDP из SBC:</span><span class="sxs-lookup"><span data-stu-id="41dd4-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="41dd4-175">Параметры MKI и Length не требуются.</span><span class="sxs-lookup"><span data-stu-id="41dd4-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="41dd4-176">Дополнительные сведения см. в разделе [RFC 4568(раздел 6.1).](https://tools.ietf.org/html/rfc4568#section-6.1)</span><span class="sxs-lookup"><span data-stu-id="41dd4-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="41dd4-177">Требования к поддержке SDES</span><span class="sxs-lookup"><span data-stu-id="41dd4-177">SDES support requirements</span></span>

<span data-ttu-id="41dd4-178">Устройство должно иметь возможность предлагать SDES в формате, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="41dd4-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="41dd4-179">Процессоры Microsoft Media Всегда предпочитают SDES.</span><span class="sxs-lookup"><span data-stu-id="41dd4-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="41dd4-180">При обходе без мультимедиа, даже если клиент поддерживает только DTLS, процессоры мультимедиа преобразуются в SDES.</span><span class="sxs-lookup"><span data-stu-id="41dd4-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="41dd4-181">При обходе мультимедиа, если клиент только DTLS (будущий штат Google Chrome), Прямая маршрутия вставит MP в путь, преобразуя звонок из обхода мультимедиа в обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="41dd4-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="41dd4-182">Между компонентом SBC и процессором мультимедиа direct Routing всегда используется SDES.</span><span class="sxs-lookup"><span data-stu-id="41dd4-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="41dd4-183">В настоящее время клиент Teams, который предлагает только DTLS, не существует. Однако Google объявил, что в какой-то момент времени прекратит поддержку SDES.</span><span class="sxs-lookup"><span data-stu-id="41dd4-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="41dd4-184">Формат предложения из SBC в режиме обхода</span><span class="sxs-lookup"><span data-stu-id="41dd4-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="41dd4-185">Предложение должно содержать SDES и может содержать необязательный DTLS в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="41dd4-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="41dd4-186">Формат ответа, содержащего SDES в SBC</span><span class="sxs-lookup"><span data-stu-id="41dd4-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="41dd4-187">Формат предложения от Teams до SBC</span><span class="sxs-lookup"><span data-stu-id="41dd4-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="41dd4-188">Формат SDES предлагается только SBC</span><span class="sxs-lookup"><span data-stu-id="41dd4-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

