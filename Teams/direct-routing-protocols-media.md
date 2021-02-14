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
# <a name="overview"></a><span data-ttu-id="9bd2c-103">Обзор</span><span class="sxs-lookup"><span data-stu-id="9bd2c-103">Overview</span></span>

<span data-ttu-id="9bd2c-104">В этой статье описывается, как direct Routing поддерживает обход мультимедиа с помощью граничного контроллера сеанса (SBC) для ICE Lite, как описано в [RFC 5245.](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="9bd2c-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="9bd2c-105">Эта статья предназначена для администраторов голосовой связи, отвечающих за настройку подключения между локальной SBC и прокси-службой SIP.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="9bd2c-106">В этой статье приводится обзор сценариев работы ICE Lite и требований для обеспечения связи.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="9bd2c-107">В этой статье описаны форматы сообщений и необходимые переходы государственного компьютера для обеспечения надежного потока звонка и передачи мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="9bd2c-108">Терминология</span><span class="sxs-lookup"><span data-stu-id="9bd2c-108">Terminology</span></span>

- <span data-ttu-id="9bd2c-109">First Hello — первые слова, произнесенные звонив и вызываемой звоня.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="9bd2c-110">Важно сделать все возможное, чтобы обеспечить доставку первых пакетов с конечных точек в большинстве случаев.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="9bd2c-111">Forking — предложение от вызываемой команды может быть доставлено на несколько конечных точек, если вызываемая команда доступна на нескольких устройствах (например, пользователь Teams может быть подписан в Teams для Windows и Teams для Android или iPhone).</span><span class="sxs-lookup"><span data-stu-id="9bd2c-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="9bd2c-112">Предварительный ответ (183) — конечные точки, которые ускоряют настройку звонка, отправляют ответ соиск и ключи, необходимые для настройки потока мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="9bd2c-113">Это делается с учетом того, что пользователь может ответить на звонок (200OK) из этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="9bd2c-114">Благодаря функции размыкажения звоняющий должен быть готов получить несколько предварительных ответов.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="9bd2c-115">Re-Invite – предложение с окончательными кандидатами, выбранными управляющей конечной точкой ICE.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="9bd2c-116">Атрибут a=remote-candidate будет иметь атрибут a=remote-candidate для устранения любых условий гонок от обработки нескольких вилок.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="9bd2c-117">Конечная точка Teams — это может быть сервер (процессор мультимедиа, ретранслятор транспорта) или клиент Teams.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="9bd2c-118">Формат сообщения</span><span class="sxs-lookup"><span data-stu-id="9bd2c-118">Message format</span></span>

<span data-ttu-id="9bd2c-119">Инфраструктура Teams следует за RFC 5245 для ICE-Lite.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="9bd2c-120">Это подразумевает, что все сообщения STUN соответствуют [требованиям RFC 5389.](https://tools.ietf.org/html/rfc5389)</span><span class="sxs-lookup"><span data-stu-id="9bd2c-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="9bd2c-121">Для этого SBCs, требуемая для RFC 5389, должен игнорировать все атрибуты STUN, которые они не распознают, и продолжать обрабатывать сообщения с известными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="9bd2c-122">При получении неформатированной формы пакеты необходимо удалить, не влияя на установку сеанса мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="9bd2c-123">Требования ICE Lite</span><span class="sxs-lookup"><span data-stu-id="9bd2c-123">ICE Lite requirements</span></span>

<span data-ttu-id="9bd2c-124">В этом разделе кратко фиксироваться требования для ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="9bd2c-125">Соищание</span><span class="sxs-lookup"><span data-stu-id="9bd2c-125">Candidate gathering</span></span>

<span data-ttu-id="9bd2c-126">SBC должен предлагать только одну соисковую соисковую информацию.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="9bd2c-127">В настоящее время поддерживаются только кандидаты по IPV4.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="9bd2c-128">Проверки подключения</span><span class="sxs-lookup"><span data-stu-id="9bd2c-128">Connectivity checks</span></span>

<span data-ttu-id="9bd2c-129">Внедрение ICE Lite должно реагировать на все полученные проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="9bd2c-130">Конечная точка ICE Lite не должна отправлять запросы на проверку подключения.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="9bd2c-131">(Если проверки подключения отправляются с нарушением, будет реагировать полная реализация, что может привести к обнаружению потенциальных кандидатов с непредвиденным одноранговой связью и сбоям в звонках.)</span><span class="sxs-lookup"><span data-stu-id="9bd2c-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="9bd2c-132">Беты</span><span class="sxs-lookup"><span data-stu-id="9bd2c-132">Nominations</span></span>

<span data-ttu-id="9bd2c-133">Конечной точкой полной реализации ICE всегда является контрольная конечная точка, и она будет следовать за обычными сроками выбора конечных кандидатов, которые будут использоваться для потока мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="9bd2c-134">Конечная точка ICE Lite может использовать эти средства, чтобы завершить путь к использованию мультимедиа и завершить установку звонка.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="9bd2c-135">Примечание. Если вы хотите использовать одноранговые конечные точки, отправляя 183 предварительных ответа, SBC должен быть готов к реагированию на проверки с нескольких конечных точек, а также с несколькими конечными точками, если до 200OK произойдет такое количество лицензий.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="9bd2c-136">В зависимости от сходимости компьютера ICE по конечному пути и времени ответа пользователя, срок действия лицензии может быть не раньше 2000 года.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="9bd2c-137">У SBC должна быть возможность обработки обоих случаев.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="9bd2c-138">Сходящиеся для разминания</span><span class="sxs-lookup"><span data-stu-id="9bd2c-138">Converging for forking</span></span>

<span data-ttu-id="9bd2c-139">Если предложение SBC предлагает несколько конечных точек Teams, конечные точки Teams могут отвечать с помощью предварительного ответа и начала проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="9bd2c-140">Необходимо подготовиться к приему проверок подключения и реагированию на проверки подключения с нескольких одноранговых конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="9bd2c-141">Например, для пользователя Teams можно использовать как рабочий стол, так и мобильный телефон.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="9bd2c-142">Оба устройства будут уведомлены о входящий звонок и попытаются проверки подключения с SBC.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="9bd2c-143">В конечном итоге на звонок ответит только одна из конечных точек (200OK).</span><span class="sxs-lookup"><span data-stu-id="9bd2c-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="9bd2c-144">При получении пакета 200OK можно настроить контекст для обработки пакетов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="9bd2c-145">Scenarios</span><span class="sxs-lookup"><span data-stu-id="9bd2c-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="9bd2c-146">Входящий звонок из SBC</span><span class="sxs-lookup"><span data-stu-id="9bd2c-146">Inbound call from SBC</span></span>

<span data-ttu-id="9bd2c-147">В этом сценарии существует несколько одноранговых конечных точек, которые должны обрабатываться СКА:</span><span class="sxs-lookup"><span data-stu-id="9bd2c-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="9bd2c-148">Конечные точки сервера обычно реагируют непосредственно в 200OK.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="9bd2c-149">Это полные конечные точки ICE, которые обычно участвуют в сценариях голосовой почты, очереди вызовов и автоответа.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="9bd2c-150">Клиентские конечные точки могут отправлять несколько предварительных ответов с разными тегами "От" и "На" (183), за которыми следует 200OK с конечной точки, которая отвечает на звонок.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="9bd2c-151">Это полные конечные точки ICE, которые обычно представляют клиенты конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="9bd2c-152">Другие конечные точки SBC.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-152">Other SBC endpoints.</span></span> <span data-ttu-id="9bd2c-153">Это конечные точки ICE Lite, которые обычно участвуют в сценарии одновременного звонка клиентских конечных точек и других номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="9bd2c-154">SBC должен отвечать на все допустимые запросы проверки подключения, полученные с полных конечных точек ICE.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="9bd2c-155">При RFC полные конечные точки ICE становятся конечными точками управления.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="9bd2c-156">Конечные точки Teams (клиент-сервер) выполняют обычные проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="9bd2c-157">Итоговая точка 200Ok может быть либо с конечной точки, которая отправила мультимедиа раньше, либо с другой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="9bd2c-158">При получении 200Ok SBC должен настроить правильный контекст для потока мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="9bd2c-159">Ранние мультимедиа</span><span class="sxs-lookup"><span data-stu-id="9bd2c-159">Early media</span></span>

<span data-ttu-id="9bd2c-160">Если имеется ранний поток мультимедиа, SBC должен быть прищелковым к первой конечной точке, которая запускает потоковую передачу мультимедиа; Поток мультимедиа может начаться до того, как будут назначены кандидаты.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="9bd2c-161">Чтобы включить сценарии IVR и голосовой почты, на этом этапе УАЦ должна поддерживать отправку DTMF.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="9bd2c-162">Следует использовать путь с наивысшим приоритетом, по которому она получает проверки, если не завершены задачи по проверке.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="9bd2c-163">Исходящие вызовы на SBC</span><span class="sxs-lookup"><span data-stu-id="9bd2c-163">Outbound call to SBC</span></span>

<span data-ttu-id="9bd2c-164">Конечные точки Teams являются вызывающим (для этого сценария) и будут контрольной конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="9bd2c-165">При получении предварительного (183) или конечного ответа (200OK) конечная точка Teams начнет проверки подключения и переходит к обычным проверкам связи.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="9bd2c-166">Примечание. Если SBC отправляет предварительный ответ (183), он должен быть готов получать запросы на проверку подключения и потенциально завершить проверку до отправки запроса 200OK.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="9bd2c-167">Если проверки и/или проверки выполнены до 2000 года, проверки и/или проверки не будут выполняться повторно после 200OK.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="9bd2c-168">Код SBC не должен изменять данные ICE candidates, password и ufrag (фрагмент имени пользователя) в период с 183 по 200.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="9bd2c-169">Для поддержки ранних сетей SBC может начать потоковую передачу мультимедиа с одноранговым кандидатом НА ICE с наивысшим приоритетом на основе полученных проверок подключения, еще до того, как конечные точки Teams завершили передачу данных.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="9bd2c-170">В SBC следует ожидать, что мультимедиа из Teams будут у всех кандидатов до тех пор, пока не будут завершены процесс перенастройки.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="9bd2c-171">После того как соискитель является кандидатом, ему необходимо восстановить контекст для отправки и получения пакетов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="9bd2c-172">Требования к поддержке SRTP</span><span class="sxs-lookup"><span data-stu-id="9bd2c-172">SRTP support requirements</span></span>

<span data-ttu-id="9bd2c-173">Код SBC должен поддерживать шифрование SRTP AES_CM_128_HMAC_SHA1_80 для предложения и ответа в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="9bd2c-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="9bd2c-174">Ниже приводится пример атрибута crypto в предложении SDP от SBC:</span><span class="sxs-lookup"><span data-stu-id="9bd2c-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="9bd2c-175">Параметры MKI и Length не требуются.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="9bd2c-176">Дополнительные сведения см. в разделе [6.1 RFC 4568.](https://tools.ietf.org/html/rfc4568#section-6.1)</span><span class="sxs-lookup"><span data-stu-id="9bd2c-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="9bd2c-177">Требования к поддержке SDES</span><span class="sxs-lookup"><span data-stu-id="9bd2c-177">SDES support requirements</span></span>

<span data-ttu-id="9bd2c-178">Устройство должно иметь возможность предлагать SDES в формате, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="9bd2c-179">Процессоры Microsoft Media всегда предпочитают SDES.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="9bd2c-180">В случае обхода без мультимедиа, даже если клиент поддерживает только DTLS, процессоры мультимедиа преобразуются в SDES.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="9bd2c-181">При обходе мультимедиа, если клиент только DTLS (будущий штат Google Chrome), Direct Routing вставляет в путь MP, преобразуя вызов из обхода мультимедиа в обход без мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="9bd2c-182">Между SBC и компонентом процессора мультимедиа Direct Routing всегда используется SDES.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="9bd2c-183">В настоящее время клиент Teams не предлагает только DTLS. Однако Компания Google объявила, что со временем поддержка SDES перестанет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="9bd2c-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="9bd2c-184">Формат предложения из SBC в режиме обхода</span><span class="sxs-lookup"><span data-stu-id="9bd2c-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="9bd2c-185">Предложение должно содержать SDES и может содержать необязательный DTLS в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="9bd2c-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="9bd2c-186">Формат ответа, содержащего SDES в SBC</span><span class="sxs-lookup"><span data-stu-id="9bd2c-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="9bd2c-187">Формат предложения от Teams к SBC</span><span class="sxs-lookup"><span data-stu-id="9bd2c-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="9bd2c-188">Формат для SDES предлагается только для SBC</span><span class="sxs-lookup"><span data-stu-id="9bd2c-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

