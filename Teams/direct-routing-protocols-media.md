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
description: Протоколы прямой маршрутизации
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08b022799b2c8bf80ee30cbb0a5ef3e74f0a29e1
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065669"
---
# <a name="overview"></a><span data-ttu-id="51a3a-103">Обзор</span><span class="sxs-lookup"><span data-stu-id="51a3a-103">Overview</span></span>

<span data-ttu-id="51a3a-104">В этой статье рассказывается о том, как прямая маршрутизация поддерживает обход мультимедиа с помощью одноименного контроллера границ (SBC), включенного для функции ICE Lite, как описано в [RFC 5245](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="51a3a-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="51a3a-105">Эта статья предназначена для администраторов голосовой связи, которые отвечают за настройку соединения между локальным SBC и прокси-службой SIP.</span><span class="sxs-lookup"><span data-stu-id="51a3a-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="51a3a-106">В этой статье приводятся общие сведения о сценариях ICE Lite и требованиях для взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="51a3a-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="51a3a-107">В этой статье описаны форматы сообщений и требования к переходам конечного автомата для обеспечения надежного потока звонков и мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="51a3a-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="51a3a-108">Терминологии</span><span class="sxs-lookup"><span data-stu-id="51a3a-108">Terminology</span></span>

- <span data-ttu-id="51a3a-109">Первый Привет — первые слова, произносимые вызывающим абонентом и вызываемым.</span><span class="sxs-lookup"><span data-stu-id="51a3a-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="51a3a-110">Важно, чтобы первые пакеты из конечных точек гарантированно доставлялись для большинства вариантов использования.</span><span class="sxs-lookup"><span data-stu-id="51a3a-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="51a3a-111">Разветвление — предложение из вызывающего абонента может доставляться в несколько конечных точек вызывающего абонента, если вызываемый объект доступен на нескольких устройствах (например, пользователь Teams может войти в Teams для Windows и Teams для Android или iPhone).</span><span class="sxs-lookup"><span data-stu-id="51a3a-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="51a3a-112">Ответ на предварительную подсылку (183) — конечные точки вызываемого абонента для более быстрой настройки звонков. отправьте ответ с кандидатами и ключами, необходимыми для создания мультимедийного потока.</span><span class="sxs-lookup"><span data-stu-id="51a3a-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="51a3a-113">Это делается в том случае, если пользователь может ответить на вызов (200OK) из определенного экземпляра вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="51a3a-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="51a3a-114">С помощью разветвления вызывающий абонент должен подготовиться к приему нескольких решений для подготовки.</span><span class="sxs-lookup"><span data-stu-id="51a3a-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="51a3a-115">Повторно пригласить — предложение с конечными кандидатами, выбранными конечной точкой управления ICE.</span><span class="sxs-lookup"><span data-stu-id="51a3a-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="51a3a-116">У него есть атрибут a = Remote-кандидатов для разрешения каких-либо условий состязания для обработки нескольких разветвлений.</span><span class="sxs-lookup"><span data-stu-id="51a3a-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="51a3a-117">Конечная точка Teams — это может быть сервер (процессор мультимедиа, транспорт ретрансляции) или клиент Teams.</span><span class="sxs-lookup"><span data-stu-id="51a3a-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="51a3a-118">Формат сообщения</span><span class="sxs-lookup"><span data-stu-id="51a3a-118">Message format</span></span>

<span data-ttu-id="51a3a-119">Инфраструктура Teams соответствует спецификации RFC 5245 для ICE – Lite.</span><span class="sxs-lookup"><span data-stu-id="51a3a-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="51a3a-120">Это означает, что все сообщения STUN будут соответствовать стандартам [RFC 5389](https://tools.ietf.org/html/rfc5389).</span><span class="sxs-lookup"><span data-stu-id="51a3a-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="51a3a-121">SBCs в соответствии со стандартом RFC 5389 должны игнорировать любые атрибуты STUN, которые они не распознают, и продолжать обработку сообщений с помощью известных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="51a3a-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="51a3a-122">Если все неверно сформированные пакеты будут получены, пакеты должны быть удалены без воздействия на сеанс мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="51a3a-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="51a3a-123">Требования для упрощенной Lite</span><span class="sxs-lookup"><span data-stu-id="51a3a-123">ICE Lite requirements</span></span>

<span data-ttu-id="51a3a-124">Этот раздел служит для краткого захвата требований для ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="51a3a-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="51a3a-125">Сбор кандидатов</span><span class="sxs-lookup"><span data-stu-id="51a3a-125">Candidate gathering</span></span>

<span data-ttu-id="51a3a-126">SBC должен предоставлять только один кандидат, который доступен для общего доступа.</span><span class="sxs-lookup"><span data-stu-id="51a3a-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="51a3a-127">В настоящее время поддерживаются только кандидаты IPV4.</span><span class="sxs-lookup"><span data-stu-id="51a3a-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="51a3a-128">Проверки подключения</span><span class="sxs-lookup"><span data-stu-id="51a3a-128">Connectivity checks</span></span>

<span data-ttu-id="51a3a-129">Реализация ICE Lite должна отвечать на любые полученные проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="51a3a-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="51a3a-130">Конечная точка ICE Lite не должна отправлять запросы на проверку подключения.</span><span class="sxs-lookup"><span data-stu-id="51a3a-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="51a3a-131">(Если проверки подключения отправляются в нарушениех, вся реализация будет отвечать на запросы, что может привести к неожиданным результатам, производным от одноранговых элементов, которые могут привести к ошибкам вызова.)</span><span class="sxs-lookup"><span data-stu-id="51a3a-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="51a3a-132">номинатионс</span><span class="sxs-lookup"><span data-stu-id="51a3a-132">Nominations</span></span>

<span data-ttu-id="51a3a-133">Конечная точка внутренней реализации ICE всегда будет управляющей конечной точкой и будет соответствовать стандарту "Regular" номинатионс для выбора конечных кандидатов, используемых для потока мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="51a3a-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="51a3a-134">Конечная точка ICE Lite может использовать номинатионс, чтобы завершить путь, который будет использоваться для мультимедиа и полных звонков.</span><span class="sxs-lookup"><span data-stu-id="51a3a-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="51a3a-135">Примечание. в случае разветвления с конечными точками одноранговой сети, отправляющей ответы 183, этот SBC должен быть готов к ответу на проверки из нескольких конечных точек, а также номинатионс из нескольких конечных точек, если номинатионс происходит перед 200OK.</span><span class="sxs-lookup"><span data-stu-id="51a3a-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="51a3a-136">В зависимости от конвергенции конечного автомата ICE на конечном пути и времени ответа пользователя номинатионс может происходить до или после 200OK.</span><span class="sxs-lookup"><span data-stu-id="51a3a-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="51a3a-137">Этот SBC должен поддерживать оба случая.</span><span class="sxs-lookup"><span data-stu-id="51a3a-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="51a3a-138">Схождение для разветвления</span><span class="sxs-lookup"><span data-stu-id="51a3a-138">Converging for forking</span></span>

<span data-ttu-id="51a3a-139">Если предложение из SBC разделяется на несколько конечных точек Teams, конечные точки Teams могут отвечать на запросы предварительной обработки и запускать проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="51a3a-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="51a3a-140">SBC должен быть подготовлен для получения проверки подключения и ответа на проверки подключения из нескольких одноранговых конечных точек.</span><span class="sxs-lookup"><span data-stu-id="51a3a-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="51a3a-141">Например, пользователь Teams может войти на Настольный компьютер и сотовый телефон.</span><span class="sxs-lookup"><span data-stu-id="51a3a-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="51a3a-142">Оба устройства будут уведомлены о входящем звонке и будут пытаться проверить связь с помощью SBC.</span><span class="sxs-lookup"><span data-stu-id="51a3a-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="51a3a-143">В конечном итоге только одна из конечных точек ответит на звонок (200OK).</span><span class="sxs-lookup"><span data-stu-id="51a3a-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="51a3a-144">Получив 200OK, SBC может настроить правый контекст для обработки пакетов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="51a3a-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="51a3a-145">Scenarios</span><span class="sxs-lookup"><span data-stu-id="51a3a-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="51a3a-146">Входящий звонок из SBC</span><span class="sxs-lookup"><span data-stu-id="51a3a-146">Inbound call from SBC</span></span>

<span data-ttu-id="51a3a-147">Для этого сценария существует несколько возможных конечных точек одноранговых элементов, которые должен обрабатывать SBC.</span><span class="sxs-lookup"><span data-stu-id="51a3a-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="51a3a-148">Конечные точки сервера обычно реагируют непосредственно с помощью 200OK.</span><span class="sxs-lookup"><span data-stu-id="51a3a-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="51a3a-149">Это полные конечные точки, которые обычно участвуют в голосовой почте, очереди звонков и сценариях автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="51a3a-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="51a3a-150">Конечные точки клиента могут отправлять несколько предварительных ответов с разными тегами from/to (183), за которыми следует 200OK из конечной точки, которая отвечает за вызов.</span><span class="sxs-lookup"><span data-stu-id="51a3a-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="51a3a-151">Это полные конечные точки, обычно представляющие клиентов конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="51a3a-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="51a3a-152">Другие конечные точки SBC.</span><span class="sxs-lookup"><span data-stu-id="51a3a-152">Other SBC endpoints.</span></span> <span data-ttu-id="51a3a-153">Эти конечные точки ICE Lite обычно участвуют в сценарии одновременного звонка конечным точкам клиента и другим телефонным номерам.</span><span class="sxs-lookup"><span data-stu-id="51a3a-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="51a3a-154">Этот SBC должен отвечать на все допустимые запросы проверки подключения, полученные от полных конечных точек ICE.</span><span class="sxs-lookup"><span data-stu-id="51a3a-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="51a3a-155">В соответствии с RFC полные конечные точки ICE станут управляющими конечными точками.</span><span class="sxs-lookup"><span data-stu-id="51a3a-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="51a3a-156">Конечные точки Teams (клиент/сервер) выполняют "регулярные" номинатионс для завершения проверок подключения.</span><span class="sxs-lookup"><span data-stu-id="51a3a-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="51a3a-157">Конечный 200Ok может быть из конечной точки, которая отправила раннее мультимедиа или из другой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="51a3a-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="51a3a-158">Когда вы получаете 200Ok, SBC должен настроить правый контекст для потока мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="51a3a-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="51a3a-159">Ранний мультимедиа</span><span class="sxs-lookup"><span data-stu-id="51a3a-159">Early media</span></span>

<span data-ttu-id="51a3a-160">Если вы выполняете более раннюю схему мультимедиа, этот SBC должен быть заблокирован до первой конечной точки, которая запускает потоковую передачу мультимедиа; поток мультимедиа может начинаться, прежде чем присвоены варианты.</span><span class="sxs-lookup"><span data-stu-id="51a3a-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="51a3a-161">Для включения сценариев интерактивный автоответчик/голосовой почты SBC должен поддерживать пересылку DTMF на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="51a3a-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="51a3a-162">SBC должен использовать путь с наивысшим приоритетом, по которому получается проверка, если номинатионс не завершился.</span><span class="sxs-lookup"><span data-stu-id="51a3a-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="51a3a-163">Исходящий звонок на SBC</span><span class="sxs-lookup"><span data-stu-id="51a3a-163">Outbound call to SBC</span></span>

<span data-ttu-id="51a3a-164">Конечные точки Teams — это вызывающий объект для этого сценария и будет управляющей конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="51a3a-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="51a3a-165">При получении ответа на предварительный запрос (183) или последнего ответа (200OK) конечная точка Teams начнет проверку подключения и затем перейти к регулярному номинатионсу для завершения проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="51a3a-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="51a3a-166">Примечание. Если SBC отправляет предустановленный ответ (183), он должен быть готов к получению запросов проверки подключения и, возможно, завершить номинатионс, прежде чем 200OK отправляется с помощью SBC.</span><span class="sxs-lookup"><span data-stu-id="51a3a-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="51a3a-167">Если проверки и (или) номинатионс выполняются перед получением 200OK, проверки и/или номинатионс не будут выполняться повторно после получения 200OK.</span><span class="sxs-lookup"><span data-stu-id="51a3a-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="51a3a-168">SBC не должен изменять кандидатов на ICE, пароль и уфраг (фрагмент имени пользователя) между 183 и 200.</span><span class="sxs-lookup"><span data-stu-id="51a3a-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="51a3a-169">Чтобы обеспечить поддержку раннего мультимедиа, SBC может начать потоковую передачу мультимедиа на одноранговый кандидат, используя наивысший приоритет в соответствии с полученными проверками подключения, даже перед тем, как номинатионс завершается конечной точкой Teams.</span><span class="sxs-lookup"><span data-stu-id="51a3a-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="51a3a-170">Этот SBC должен ожидать передачи мультимедиа от Teams на любой кандидат, пока номинатионс не завершится.</span><span class="sxs-lookup"><span data-stu-id="51a3a-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="51a3a-171">После того как кандидат приступит, для отправки и получения пакетов мультимедиа необходимо сбросить SBC в правый контекст.</span><span class="sxs-lookup"><span data-stu-id="51a3a-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="51a3a-172">Требования поддержки SRTP</span><span class="sxs-lookup"><span data-stu-id="51a3a-172">SRTP support requirements</span></span>

<span data-ttu-id="51a3a-173">SBC должен поддерживать шифр SRTP Encryption AES_CM_128_HMAC_SHA1_80 для предложения и ответа в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="51a3a-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="51a3a-174">Ниже приведен пример атрибута шифрования в предложении SDP из SBC:</span><span class="sxs-lookup"><span data-stu-id="51a3a-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="51a3a-175">Параметры МКИ и Length не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="51a3a-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="51a3a-176">Дополнительные сведения можно найти в [статье RFC 4568, раздел 6,1](https://tools.ietf.org/html/rfc4568#section-6.1).</span><span class="sxs-lookup"><span data-stu-id="51a3a-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="51a3a-177">Требования поддержки СДЕС</span><span class="sxs-lookup"><span data-stu-id="51a3a-177">SDES support requirements</span></span>

<span data-ttu-id="51a3a-178">Устройство должно поддерживать СДЕС в формате, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="51a3a-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="51a3a-179">Процессоры Microsoft Media всегда предпочитают СДЕС.</span><span class="sxs-lookup"><span data-stu-id="51a3a-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="51a3a-180">Если не использовать мультимедиа, даже если клиент поддерживает ДТЛС, то процессоры мультимедиа будут преобразовываться в СДЕС.</span><span class="sxs-lookup"><span data-stu-id="51a3a-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="51a3a-181">Если у клиента есть только ДТЛС (будущее рабочее состояние Google), прямая маршрутизация вставит в путь точку управления, преобразуя вызов из режима мультимедиа в режим обхода без мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="51a3a-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="51a3a-182">Между однокомпонентным процессором SBC и Media, СДЕС всегда используется.</span><span class="sxs-lookup"><span data-stu-id="51a3a-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="51a3a-183">В настоящее время нет клиента Teams, предлагающего только ДТЛС; Несмотря на то что компания Google объявила о том, что в какой – либо момент она прекратит поддерживать СДЕС.</span><span class="sxs-lookup"><span data-stu-id="51a3a-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="51a3a-184">Формат предложения из SBC в режиме обхода</span><span class="sxs-lookup"><span data-stu-id="51a3a-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="51a3a-185">Предложение должно содержать СДЕС и может содержать ДТЛС необязательно в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="51a3a-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="51a3a-186">Формат ответа, содержащего СДЕС, в SBC</span><span class="sxs-lookup"><span data-stu-id="51a3a-186">Format for answer containing SDES to SBC</span></span>

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="51a3a-187">Формат предложения из Teams в SBC</span><span class="sxs-lookup"><span data-stu-id="51a3a-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="51a3a-188">Формат для СДЕС только предложением для SBC</span><span class="sxs-lookup"><span data-stu-id="51a3a-188">Format for SDES only offer to SBC</span></span>

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

