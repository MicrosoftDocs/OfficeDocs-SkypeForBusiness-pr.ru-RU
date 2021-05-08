---
title: Руководство пользователя по ретрансляции IP-адресов, Канада
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: None
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: Использование учетной записи ретрансляции IP для Канады.
ms.openlocfilehash: b7f276bdf921fdc721ef1df883d3c5d714e4a94f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238671"
---
# <a name="ip-relay-in-canada---user-guide"></a><span data-ttu-id="e4c8f-103">IP-ретрансляция в Канаде — руководство пользователя</span><span class="sxs-lookup"><span data-stu-id="e4c8f-103">IP Relay in Canada - user guide</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="e4c8f-104">Описание службы ретрансляции IP-сообщений от Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="e4c8f-104">Description of the IP Message Relay service from Microsoft:</span></span>

## <a name="scenario-a"></a><span data-ttu-id="e4c8f-105">Сценарий A</span><span class="sxs-lookup"><span data-stu-id="e4c8f-105">Scenario A</span></span>
<span data-ttu-id="e4c8f-106">Если человек с нарушениями слуха или голосовой связью хочет связаться с человеком с нарушениями слуха, он "общается" через специальный веб-клиент с агентом, который называется "Принимать вызовы".</span><span class="sxs-lookup"><span data-stu-id="e4c8f-106">If a hearing- or voice-impaired person wishes to contact a non-impaired individual, they “chat” via a special web-based client to an agent called a Call Taker.</span></span>

<span data-ttu-id="e4c8f-107">Затем вызываемая звонок общается с человеком с нарушениями слуха или голосовой связи через сеанс чата и при необходимости общается с ним по телефонной сети в Канаде или США.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-107">The Call Taker then communicates with the hearing- or voice-impaired person via the chat session and contacts the non-impaired person through the telephone network anywhere in Canada or the United States, as required.</span></span>

## <a name="scenario-b"></a><span data-ttu-id="e4c8f-108">Сценарий Б</span><span class="sxs-lookup"><span data-stu-id="e4c8f-108">Scenario B</span></span>
<span data-ttu-id="e4c8f-109">Если человек с нарушениями слуха или голосовой функцией хочет пообщаться с зарегистрированным пользователем, он звонит на бесплатный номер, предоставленный корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-109">If a non-impaired person wishes to talk to a registered hearing- or voice-impaired user, they call the toll-free number as provided by Microsoft.</span></span>

<span data-ttu-id="e4c8f-110">Затем вызываемая звонок общается с человеком без нарушения слуха и общается с человеком с нарушениями слуха или голосовой связью через чат и общается друг с другом.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-110">The Call Taker then communicates with the non-impaired person and contacts the hearing- or voice-impaired person via chat and communicates back and forth.</span></span>

<span data-ttu-id="e4c8f-111">Если человек с нарушениями слуха или голосовой почты не находится в сети в программе чата, при наличии адреса электронной почты вызываемая звонок отправляет сообщение электронной почты человеку с нарушениями слуха или голосовой почты по запросу вызываемого лица.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-111">Should the hearing- or voice-impaired person not be online in the chat program, if an email address is available the Call Taker will send an email to the hearing- or voice-impaired person, if requested by the caller.</span></span>

## <a name="scenario-c"></a><span data-ttu-id="e4c8f-112">Сценарий C</span><span class="sxs-lookup"><span data-stu-id="e4c8f-112">Scenario C</span></span>
<span data-ttu-id="e4c8f-113">Если человеку с нарушениями слуха или голосовой функции требуется экстренная помощь, он может нажать соответствующую кнопку: 911 – Политика / 911 – Fire / 911 – Несрочные.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-113">If an hearing- or voice-impaired person requires emergency assistance, he or she may select the appropriate button:  911 – Police / 911 – Fire / 911 – Ambulance.</span></span>

<span data-ttu-id="e4c8f-114">При этом операторам ретрансляции IP-адресов для северной части будет отправляться уведомление о чрезвычайной ситуации, и они получат доступ к учетной записи 911, предназначенной для этой цели.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-114">This will send an emergency notification to the Northern IP Relay operators, who will then access the 911 account designed for this purpose.</span></span> <span data-ttu-id="e4c8f-115">После того как звонок подтвердит свой адрес, он свяжется с соответствующей psAP и будет оставаться в строке в течение необходимого времени.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-115">Once the Call Taker has confirmed his or her address, they will contact the appropriate PSAP and stay on the line for as long as required.</span></span>

## <a name="how-to-place-a-text-chat-to-voice-call"></a><span data-ttu-id="e4c8f-116">Как разместить текстовый чат в Голосовой звонок</span><span class="sxs-lookup"><span data-stu-id="e4c8f-116">How to place a Text chat to Voice call</span></span>

https://aka.ms/IPRelay

<span data-ttu-id="e4c8f-117">Чтобы начать голосовой звонок, перейдите к URL-адресу выше и войдите в систему, указав имя пользователя и пароль ретрансляции IP-сообщений.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-117">To initiate a text to voice call, go to the above URL and log in with your IP Message Relay Username and Password.</span></span>

<span data-ttu-id="e4c8f-118">После входа вы увидите инструкции в левой части экрана.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-118">Once logged in, you will see instructions displayed on the left side of your screen.</span></span>

### <a name="how-to-make-a-text-to-voice-call"></a><span data-ttu-id="e4c8f-119">Как сделать голосовой звонок с текстом:</span><span class="sxs-lookup"><span data-stu-id="e4c8f-119">How to make a Text to Voice call:</span></span>
1. <span data-ttu-id="e4c8f-120">В правом нижнем углу экрана нажмите кнопку **Чат**.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-120">In the lower-right corner of screen, click **Chat**.</span></span>
2. <span data-ttu-id="e4c8f-121">Щелкните **пользователя IPRelay.**</span><span class="sxs-lookup"><span data-stu-id="e4c8f-121">Click the **IPRelay** user.</span></span>
3. <span data-ttu-id="e4c8f-122">В нижней части нового окна введите сообщение.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-122">In the bottom of the new box that pops up, type your message.</span></span>

### <a name="how-to-receive-a-voice-to-text-call"></a><span data-ttu-id="e4c8f-123">Как принимать голосовые и текстовые вызовы:</span><span class="sxs-lookup"><span data-stu-id="e4c8f-123">How to receive a Voice to Text call:</span></span>
- <span data-ttu-id="e4c8f-124">Пользователи голосовой почты должны знать ваше имя пользователя ретрансляции IP-сообщений, чтобы сделать голосовой звонок.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-124">Voice users will need to know your IP Message Relay Username in order to place a voice to text call.</span></span>
- <span data-ttu-id="e4c8f-125">Пользователи голосовой связи могут звонить по телефону (866) 660-8613 для подключения с помощью оператора ретрансляции IP-сообщений.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-125">Voice users can call (866) 660-8613 to connect with an IP Message Relay operator.</span></span>
- <span data-ttu-id="e4c8f-126">Для получения звонков или чатов необходимо войти на портал ретрансляции IP-сообщений.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-126">You must be logged in to the IP Message Relay portal to receive calls or chats.</span></span>

### <a name="how-to-place-a-911-call"></a><span data-ttu-id="e4c8f-127">Как сделать звонок 911:</span><span class="sxs-lookup"><span data-stu-id="e4c8f-127">How to place a 911 call:</span></span>
<span data-ttu-id="e4c8f-128">Если вы испытываете экстренные ситуации, вы можете нажать соответствующую кнопку в нижней части экрана (как показано ниже).</span><span class="sxs-lookup"><span data-stu-id="e4c8f-128">If you experience an emergency, you may select the appropriate emergency button located at the bottom of your screen (as shown below).</span></span>

![Кнопки для экстренного вызова](../images/ip-relay-emergency-buttons.png)

<span data-ttu-id="e4c8f-130">Оператор ретрансляции IP-сообщений свяжусь с оператором 911, подтвердит ваш адрес и переведет его в различные центры экстренной помощи, пока он не будет больше не требуется, а соответствующий отдел будет отправлен в ваше расположение.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-130">The IP Message Relay Operator will contact 911, confirm your address and translate with various emergency centers until he or she is no longer required, and the appropriate department has been dispatched to your location.</span></span>

> [!WARNING]
> <span data-ttu-id="e4c8f-131">Не проверяйте эту службу, так как соответствующее учреждение свяжуется с ним и, возможно, отправляется, даже если вы указываете, что это просто проверка, и с вас может взиматься ложный сбор за отправку из экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-131">Please do not test this service, as the appropriate agency will be contacted and possibly dispatched even if you indicate it is simply a test, and you may be charged a false dispatch fee from the emergency agency.</span></span>

#### <a name="customer-support"></a><span data-ttu-id="e4c8f-132">Служба поддержки клиентов:</span><span class="sxs-lookup"><span data-stu-id="e4c8f-132">Customer Support:</span></span>
<span data-ttu-id="e4c8f-133">Обратитесь в [](mailto:specialprojects@northern911.com) специальную specialprojects@northern911.com (705) 222-1733.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-133">Please contact Special Projects at [specialprojects@northern911.com](mailto:specialprojects@northern911.com) or (705) 222-1733.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4c8f-134">Northern911 управляет службой ретрансляции IP-адресов от имени корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e4c8f-134">Northern911 manages the IP relay service on behalf of Microsoft.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e4c8f-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e4c8f-135">Related topics</span></span>

[<span data-ttu-id="e4c8f-136">IP-ретрансляция в Канаде — регистрация</span><span class="sxs-lookup"><span data-stu-id="e4c8f-136">IP Relay in Canada - sign up</span></span>](ip-relay-canada-email-signup.md)






