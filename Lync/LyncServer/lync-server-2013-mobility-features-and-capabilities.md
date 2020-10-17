---
title: 'Lync Server 2013: функции и возможности мобильной работы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3eecf3d55ba3bb8e8629d41a9a924c65ac7a4c0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516136"
---
# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="4ebe6-102">Функции и возможности мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ebe6-102">Mobility features and capabilities in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ebe6-103">_**Последнее изменение темы:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="4ebe6-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="4ebe6-104">Функция Mobility, появившаяся в накопительных пакетах обновления для Lync Server 2013: Февраль 2013, поддерживает функции Lync 2010 Mobile и Lync 2013 Mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="4ebe6-105">При развертывании службы мобильности Lync Server 2013 пользователи могут использовать поддерживаемые мобильные устройства Apple iOS, Android, Windows Phone или Nokia Symbian для выполнения таких действий, как отправка и получение мгновенных сообщений, просмотр контактов и Просмотр сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="4ebe6-106">Кроме того, мобильными устройствами поддерживаются некоторые возможности корпоративной голосовой связи (Enterprise Voice), такие как присоединение к конференции по щелчку, звонок с работы (Call via Work), многосторонняя связь по одному номеру, голосовая почта и пропущенные вызовы.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="4ebe6-107">Новые возможности, реализованные в накопительных обновлениях для Lync Server 2013:2013 февраля включают возможность передачи голоса по протоколу IP (VoIP) и видео (H. 264) для участника собрания.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="4ebe6-108">Функция Mobility, появившаяся в накопительных пакетах обновления для Lync Server 2013: Февраль 2013, поддерживает функции мобильных клиентов Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="4ebe6-109">Накопительные пакеты обновления для Lync Server 2013: Февраль 2013 установите веб-API единой системы обмена сообщениями или UCWA.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="4ebe6-110">UCWA — это компонент, используемый для мобильных клиентов Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="4ebe6-111">В Lync Server 2013 MCX используется для мобильных клиентов Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="4ebe6-112">Накопительные пакеты обновления для Lync Server 2013: Февраль 2013 Представьте UCWA в качестве новой точки входа для служб Mobility Services.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="4ebe6-113">Lync Server 2013 параллельно реализует службу Mobility Service (MCX), которая представлена в накопительных пакетах обновления для Lync Server 2010: Ноябрь 2011, и обеспечивает поддержку Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="4ebe6-114">При развертывании накопительных обновлений для Lync Server 2013: Февраль 2013, пользователи могут использовать поддерживаемые мобильные устройства Apple iOS, Android и Windows Phone для выполнения таких действий, как:</span><span class="sxs-lookup"><span data-stu-id="4ebe6-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4ebe6-115">Функции, поддерживаемые службой Mobility Service из накопительных обновлений для Lync Server 2010: Ноябрь 2011 отмечены с (MCX).</span><span class="sxs-lookup"><span data-stu-id="4ebe6-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="4ebe6-116">Все перечисленные функции поддерживаются UCWA, представленные в накопительных пакетах обновления для Lync Server 2013: Февраль 2013.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="4ebe6-117">Отправка и получение мгновенных сообщений (MCX)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="4ebe6-118">Просмотр сведений о присутствии (MCX)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="4ebe6-119">Просмотр контактов (MCX)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="4ebe6-120">Щелкните, чтобы присоединиться к Конференции (MCX)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="4ebe6-121">Звонок через Work (MCX)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="4ebe6-122">Один номер доступа (MCX)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="4ebe6-123">Голосовая почта (MCX)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="4ebe6-124">Уведомление о пропущенном звонке (MCX)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="4ebe6-125">Передача голоса по IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="4ebe6-126">Видео участника (H. 264)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ebe6-127">Lync 2010 Mobile предоставил клиент для устройств Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="4ebe6-128">Lync 2013 Mobile не будет иметь клиента для устройств на базе Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="4ebe6-129">Пользователи Apple iPad имеют доступ к расширенным возможностям.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="4ebe6-130">После присоединения к собранию с помощью голосового звонка пользователь iPad сможет просматривать загруженные презентации Microsoft PowerPoint в собрании, совместно использовать приложения и настольные компьютеры, просматривать список участников собрания и получать уведомления о других типах контента, к которым предоставлен общий доступ в собрании.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4ebe6-131">При достижении одного номера пользователь получает звонки на мобильный телефон, набираемый с рабочим номером.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="4ebe6-132">С помощью функции "позвонить с рабочего" пользователь помещает исходящий звонок от клиента Lync Mobile, используя рабочий номер вместо номера мобильного телефона.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="4ebe6-133">При исходящих звонках клиент отправляет запрос на MCX или UCWA (на основе версии Lync Mobile), чтобы выполнить вызов для них.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="4ebe6-134">Сервер инициирует вызов, а затем вызывает его обратно на мобильном телефоне.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="4ebe6-135">Когда пользователь ответит, сервер выполняет вызов, набираемый другой стороной.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="4ebe6-136">Используя функцию "позвонить с рабочего", пользователи могут сохранять свои рабочие идентификаторы во время вызова, что означает, что получатель вызова не видит мобильный телефон абонента, а вызывающая сторона не позволяет избежать появления исходящих звонков.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4ebe6-137">Не все функции работают одинаково на всех мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="4ebe6-138">Для получения дополнительных сведений о функциях, поддерживаемых на мобильных устройствах, обратитесь к таблицам сравнения мобильных клиентов по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A> .</span><span class="sxs-lookup"><span data-stu-id="4ebe6-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="4ebe6-139">Дополнительные сведения о поддерживаемых устройствах и операционных системах приведены в разделах, посвященных <A href="lync-server-2013-planning-for-mobile-clients.md">планированию мобильных клиентов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="4ebe6-140">При использовании функции автообнаружения Lync Server 2013 мобильные приложения могут автоматически искать веб-службы Lync Server 2013, не требуя от пользователей вручную вводить URL-адреса в параметрах устройства.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="4ebe6-141">Ввод URL-адресов вручную в параметрах мобильного устройства также поддерживается в первую очередь для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4ebe6-142">MCX и UCWA — это бесплатные службы, которые развертываются для поддержки мобильных клиентов Lync 2010 Mobile и Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="4ebe6-143">Lync 2013 Mobile не сможет войти в развертывания Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="4ebe6-144">Lync 2010 Mobile и Lync 2013 Mobile могут использовать развертывание Lync Server 2013 с накопительными пакетами обновления для Lync Server 2013: применено февраля 2013.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="4ebe6-145">Функция Mobility также поддерживает *Push-уведомления* для мобильных устройств, которые не поддерживают приложения, работающие в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="4ebe6-146">Push-уведомление — это уведомление, которое отправляется на мобильное устройство, связанное с событием, которое происходит, когда мобильное приложение неактивно.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="4ebe6-147">Например, сообщение о пропущенном приглашении на обмен мгновенными сообщениями может привести к Push-уведомлению.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="4ebe6-148">MCX, UCWA, служба автообнаружения и поддержка push-уведомлений предоставлены в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="4ebe6-149">Обновленные функции клиентов, возможности и использование UCWA в качестве точки входа для мобильности представлены в накопительных пакетах обновления для Lync Server 2013: Февраль 2013.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

