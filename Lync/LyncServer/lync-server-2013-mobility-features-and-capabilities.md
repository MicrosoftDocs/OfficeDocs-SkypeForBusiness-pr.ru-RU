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
ms.openlocfilehash: 3e00274e62cc0fe7cf55c45e11a49670c7f1e6a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="f712d-102">Функции и возможности мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f712d-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f712d-103">_**Тема последнего изменения:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="f712d-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="f712d-104">Функция мобильной связи, представленная в накопительных обновлениях для Lync Server 2013: Февраль 2013 поддерживает функции мобильных клиентов Lync 2010 Mobile и Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f712d-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="f712d-105">При развертывании службы Lync Server 2013 Mobility Service пользователи могут использовать поддерживаемые устройства Apple iOS, Android и Windows Phone или Nokia Symbian на мобильных устройствах для выполнения таких операций, как отправка и получение мгновенных сообщений, просмотр контактов и Просмотр сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="f712d-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="f712d-106">Кроме того, некоторые мобильные устройства поддерживают такие функции службы "Корпоративная голосовая связь", как присоединение к конференции одним щелчком, звонки с рабочего телефона, доступ по одному номеру, голосовая почта и пропущенные звонки.</span><span class="sxs-lookup"><span data-stu-id="f712d-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="f712d-107">Новые функции, представленные в накопительных обновлениях для Lync Server 2013: Февраль 2013 включают возможности голосовой связи по протоколу IP (VoIP) и видео (H. 264) для участника собрания.</span><span class="sxs-lookup"><span data-stu-id="f712d-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="f712d-108">Функция мобильной связи, представленная в накопительных обновлениях для Lync Server 2013: Февраль 2013 поддерживает функции мобильных клиентов Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f712d-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="f712d-109">Накопительные обновления для Lync Server 2013: Февраль 2013 установите веб-API единой системы обмена сообщениями или УКВА.</span><span class="sxs-lookup"><span data-stu-id="f712d-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="f712d-110">УКВА является компонентом, используемым для мобильных клиентов Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f712d-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="f712d-111">В Lync Server 2013 МККС используется для мобильных клиентов Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="f712d-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="f712d-112">Накопительные обновления для Lync Server 2013: Февраль 2013 вводят УКВА как новую точку входа для служб Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="f712d-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="f712d-113">Lync Server 2013 параллельно реализует службу Mobility Service (МККС), которая представлена в накопительных обновлениях для Lync Server 2010: Ноябрь 2011, и обеспечивает поддержку Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="f712d-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="f712d-114">При развертывании накопительных обновлений для Lync Server 2013: Февраль 2013, пользователи могут использовать поддерживаемые мобильные устройства Apple iOS, Android и Windows Phone для выполнения таких действий, как:</span><span class="sxs-lookup"><span data-stu-id="f712d-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f712d-115">Возможности, поддерживаемые службой Mobility Service из накопительных обновлений для Lync Server 2010: Ноябрь 2011 отмечены вместе с (МККС).</span><span class="sxs-lookup"><span data-stu-id="f712d-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="f712d-116">Все перечисленные функции поддерживаются УКВА, представленными в накопительных обновлениях для Lync Server 2013: Февраль 2013.</span><span class="sxs-lookup"><span data-stu-id="f712d-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="f712d-117">Отправка и получение мгновенных сообщений (МККС)</span><span class="sxs-lookup"><span data-stu-id="f712d-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="f712d-118">Просмотр сведений о присутствии (МККС)</span><span class="sxs-lookup"><span data-stu-id="f712d-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="f712d-119">Просмотр контактов (МККС)</span><span class="sxs-lookup"><span data-stu-id="f712d-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="f712d-120">Щелкните, чтобы присоединиться к Конференции (МККС)</span><span class="sxs-lookup"><span data-stu-id="f712d-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="f712d-121">Позвонить с помощью работы (МККС)</span><span class="sxs-lookup"><span data-stu-id="f712d-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="f712d-122">Однозначный номер (МККС)</span><span class="sxs-lookup"><span data-stu-id="f712d-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="f712d-123">Голосовая почта (МККС)</span><span class="sxs-lookup"><span data-stu-id="f712d-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="f712d-124">Уведомление о пропущенном звонке (МККС)</span><span class="sxs-lookup"><span data-stu-id="f712d-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="f712d-125">Протокол VoIP</span><span class="sxs-lookup"><span data-stu-id="f712d-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="f712d-126">Видео участника (H.264)</span><span class="sxs-lookup"><span data-stu-id="f712d-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f712d-127">Lync 2010 Mobile предоставил клиента для устройств Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="f712d-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="f712d-128">Lync 2013 Mobile не будет иметь клиента для устройств на базе Symbian Nokia.</span><span class="sxs-lookup"><span data-stu-id="f712d-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="f712d-129">Пользователи Apple iPad смогут получить доступ к расширенным возможностям.</span><span class="sxs-lookup"><span data-stu-id="f712d-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="f712d-130">После присоединения к собранию с помощью голосового звонка пользователь iPad сможет просматривать загруженные презентации Microsoft PowerPoint в собрании, совместно использовать приложения и настольные компьютеры, просматривать список участников собрания и получать уведомления о других типах контента. Общий доступ в собрании.</span><span class="sxs-lookup"><span data-stu-id="f712d-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f712d-131">При наличии одного номера пользователь принимает звонки на мобильный телефон, набираемый на рабочий номер.</span><span class="sxs-lookup"><span data-stu-id="f712d-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="f712d-132">С помощью функции "звонок через Work" пользователь походит на исходящий звонок из клиента Lync Mobile, используя рабочий телефон, а не номер мобильного телефона.</span><span class="sxs-lookup"><span data-stu-id="f712d-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="f712d-133">При использовании удаленного доступа клиент отправляет запрос на МККС или УКВА (на основе версии Lync Mobile) для осуществления звонка.</span><span class="sxs-lookup"><span data-stu-id="f712d-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="f712d-134">Сервер инициирует звонок, а затем снова вызывает пользователя на мобильном телефоне.</span><span class="sxs-lookup"><span data-stu-id="f712d-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="f712d-135">После того как пользователь ответит, сервер завершает звонок, набрав другого абонента.</span><span class="sxs-lookup"><span data-stu-id="f712d-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="f712d-136">Используя функцию "звонок с помощью работы", пользователи могут сохранять свою работу во время звонка, что означает, что получатель звонка не видит номер мобильного телефона вызывающего абонента, и вызывающий объект не позволяет устранить подлинность исходящих звонков.</span><span class="sxs-lookup"><span data-stu-id="f712d-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f712d-137">Некоторые функции работают одинаково на всех мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="f712d-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="f712d-138">Дополнительные сведения о функциях, поддерживаемых на мобильных устройствах, можно найти в таблице сравнения <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="f712d-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="f712d-139">Подробные сведения о поддерживаемых устройствах и операционных системах можно найти в разделах требования в разделе <A href="lync-server-2013-planning-for-mobile-clients.md">планирование для мобильных клиентов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f712d-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f712d-140">Если вы используете функцию автообнаружения Lync Server 2013, мобильные приложения смогут автоматически находить веб-службы Lync Server 2013, не требуя вручную вводить URL-адреса в параметры устройства.</span><span class="sxs-lookup"><span data-stu-id="f712d-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="f712d-141">Кроме того, в параметрах мобильного устройства поддерживается ввод URL-адресов вручную, в основном для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="f712d-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f712d-142">МККС и УКВА — это бесплатные услуги, и они развертываются для поддержки мобильных клиентов Lync 2010 для мобильных устройств и Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f712d-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="f712d-143">Lync 2013 Mobile не сможет войти в развертывание Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f712d-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="f712d-144">Lync 2010 Mobile и Lync 2013 Mobile также смогут использовать развертывание Lync Server 2013 с накопительными обновлениями для Lync Server 2013: применено обновлений за Февраль 2013 г.</span><span class="sxs-lookup"><span data-stu-id="f712d-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="f712d-145">Функция Mobility также поддерживает *Push-уведомления* для мобильных устройств, которые не поддерживают приложения, работающие в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="f712d-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="f712d-146">Push-уведомление — это передаваемое на мобильное устройство уведомление о событии, которое произошло в то время, когда мобильное приложение было неактивно.</span><span class="sxs-lookup"><span data-stu-id="f712d-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="f712d-147">Например, сообщение с приглашением на обмен мгновенными сообщениями может привести к появлению push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="f712d-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="f712d-148">МККС, УКВА, служба автообнаружения и поддержка push-уведомлений предоставляются в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f712d-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="f712d-149">Обновленные функции клиента, возможности и использование УКВА в качестве точки входа для мобильных устройств представлены в накопительных обновлениях для Lync Server 2013: Февраль 2013.</span><span class="sxs-lookup"><span data-stu-id="f712d-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

