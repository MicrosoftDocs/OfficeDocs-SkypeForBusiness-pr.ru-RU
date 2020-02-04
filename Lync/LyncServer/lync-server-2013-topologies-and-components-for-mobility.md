---
title: 'Lync Server 2013: топологии и компоненты для мобильной работы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739deecf47e25e57ca0175c29a2721e509f8dbe2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="ce8f1-102">Топологии и компоненты для мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce8f1-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce8f1-103">_**Тема последнего изменения:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="ce8f1-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="ce8f1-104">Для поддержки мобильных приложений Lync на мобильных устройствах Lync Server 2013 предоставляет три службы: Lync Server 2013 МККС Mobility Service, служба автообнаружения для Lync Server 2013 и Служба push-уведомлений Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="ce8f1-105">Накопительные обновления для Lync Server 2013: Февраль 2013 добавлены бесплатное, но расширенное обслуживание для мобильных клиентов Lync 2013 — поддержка мобильных устройств с помощью веб-интерфейса единой системы обмена сообщениями или УКВА.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="ce8f1-106">В этом разделе кратко описаны эти компоненты и указаны топологии Lync Server 2013, поддерживающие мобильность.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce8f1-107">Услуги мобильной связи также доступны в гибридных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="ce8f1-108">Если пользователи подключены к сети, вам не нужно развертывать службы для поддержки мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="ce8f1-109">Вам необходимо определить параметр для службы автообнаружения, чтобы позволить мобильным пользователям находить свои сетевые удостоверения.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ce8f1-110">Если вы планируете подключение внешних пользователей (например, Федерация, доступ к внешним пользователям или мобильным функциям), вы должны использовать пограничные серверы с сервером Standard Edition, сервер переднего плана и пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="ce8f1-111">На сервере Standard Edition и на сервере переднего плана или пуле переднего плана отсутствуют необходимые компоненты, чтобы предоставить внешним пользователям доступ к внутреннему развернутому или внутреннему развертыванию для связи с внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="ce8f1-112">Для всех сценариев, в которых есть внешние пользователи, взаимодействующие с внутренними пользователями, в том числе мобильность, необходимо развернуть хотя бы один пограничный сервер и один обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="ce8f1-113"><EM>Push-уведомление</EM> использует тип Федерации для служб Lync Online, в котором размещается Клиринговый дом push-уведомлений (ПНЧ).</span><span class="sxs-lookup"><span data-stu-id="ce8f1-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="ce8f1-114">Push-уведомлением называют звуковое оповещение, оповещения на экране (текст) и эмблемы, появляющиеся приложениями на устройствах Apple iPhone, iPad и Windows Phone, если мобильное устройство неактивно.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="ce8f1-115">ПНЧ получает push-уведомления от сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="ce8f1-116">Когда ПНЧ получает уведомление о сообщении, ПНЧ пересылает уведомление на мобильные клиенты через службы push-уведомлений Apple или Lync Server 2013, в зависимости от мобильного клиента, для которого предназначено сообщение.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="ce8f1-117">ПНЧ — это обязательная служба для мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="ce8f1-118">Чтобы включить федерацию в Lync Online, ПНЧ использует пограничные серверы и сертификаты для обеспечения конфиденциальности и проверки подлинности, политик и правильности настройки DNS-записей.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="ce8f1-119">Клиенты на платформе Nokia Symbian и Android не используют ПНЧ для Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="ce8f1-120">Сведения о планировании и развертывании пограничных серверов можно найти <A href="lync-server-2013-planning-for-external-user-access.md">в разделе Планирование доступа внешних пользователей в Lync server 2013</A> и <A href="lync-server-2013-deploying-external-user-access.md">развертывание внешних пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="ce8f1-121">Мобильные клиенты Lync 2013 для устройств Apple, представленные в накопительных обновлениях для Lync Server 2013: Февраль 2013, больше не используют push-уведомление или клиринговый номер pushd Notification (ПНЧ).</span><span class="sxs-lookup"><span data-stu-id="ce8f1-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="ce8f1-122">Мобильные клиенты Lync 2013 на устройстве с Windows Phone все еще используют push-уведомления и (ПНЧ).</span><span class="sxs-lookup"><span data-stu-id="ce8f1-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="ce8f1-123">Мобильные компоненты</span><span class="sxs-lookup"><span data-stu-id="ce8f1-123">Mobility Components</span></span>

<span data-ttu-id="ce8f1-124">Ниже перечислены службы, поддерживающие мобильную связь.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="ce8f1-125">**Веб-интерфейс API единой системы обмена сообщениями Lync Server 2013 (Уква)**   предоставляет службы для обмена данными в реальном времени с мобильными и веб-клиентами в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="ce8f1-126">При развертывании накопительных обновлений для Lync Server 2013: Февраль 2013 для сервера переднего плана и режиссера, при установке создается виртуальный каталог во внутренней и внешней веб-службах (Уква).</span><span class="sxs-lookup"><span data-stu-id="ce8f1-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="ce8f1-127">Веб-компонент, который входит в состав виртуального каталога Уква, принимает вызовы от клиентов, поддерживающих УКВА.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="ce8f1-128">Клиентские приложения обмениваются данными через интерфейс RESTFUL для присутствия, контактов, обмена мгновенными сообщениями, VoIP, видеоконференций и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="ce8f1-129">УКВА использует канал с интерфейсом P-GET для отправки событий, таких как входящий вызов, входящее сообщение или сообщение, в клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ce8f1-130">Пересылка данных о состоянии <EM>остатка</EM> и повторного представления — это архитектурный стиль программного обеспечения для распределенных систем, широко применяемый в разных формах, и который хорошо подходит для требований веб-служб в целом.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="ce8f1-131">**Служба Lync Server 2013 Mobility Service (МККС)**   эта служба поддерживает функции Lync, такие как обмен мгновенными сообщениями, сведения о присутствии и контакты, на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="ce8f1-132">Служба Mobility Service устанавливается на каждый сервер переднего плана в каждом пуле, поддерживающий функциональность Lync на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="ce8f1-133">При установке Lync Server 2013 новый виртуальный каталог (МККС) создается как на внутреннем веб-сайте, так и на внешнем веб-сайте на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ce8f1-134">Lync Server 2013 с накопительными обновлениями для Lync Server 2013: Февраль 2013 поддерживается как служба Mobility Service, представленная в накопительном обновлении для Lync Server 2010: Ноябрь 2011, которые обычно называют МККС и веб-компонент УКВА.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="ce8f1-135">Сочетание этих двух служб Mobility Service обеспечивает взаимодействие и использование пользователями Lync 2010 Mobile и Lync 2013 для мобильных клиентов на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="ce8f1-136">**Служба автообнаружения Lync Server 2013**   . Эта служба определяет расположение пользователя и позволяет мобильным устройствам и другим клиентам Lync находить ресурсы, такие как внутренние и внешние URL-адреса для служб Lync Server 2013, а также URL-адрес для МККС или Уква, независимо от расположения в сети.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="ce8f1-137">Автоматическое обнаружение использует жестко закодированные имена узлов (линкдисковеринтернал для пользователей в сети; lyncdiscover для пользователей за пределами сети) и домен SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="ce8f1-138">It supports client connections that use either HTTP or HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="ce8f1-139">Служба автообнаружения устанавливается на каждый сервер переднего плана и каждый из режиссеров в каждом пуле, поддерживающих функциональность Lync на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="ce8f1-140">При установке службы автообнаружения новый виртуальный каталог (автообнаружения) создается как на внутреннем, так и на внешнем веб-сайте, а также на серверах и режиссерах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ce8f1-141">Здесь указана служба автообнаружения, так как она остается критическим компонентом при предоставлении мобильных клиентских служб.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="ce8f1-142">Роль автообнаружения в Lync Server 2013 была расширена для предоставления служб для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="ce8f1-143">Подробные сведения о планировании службы автообнаружения можно найти <A href="lync-server-2013-planning-for-autodiscover.md">в разделе Планирование автообнаружения в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="ce8f1-144">**Служба push-уведомлений**   эта служба является облачной службой, которая находится в центре обработки данных Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="ce8f1-145">Если мобильное приложение Lync на поддерживаемом устройстве Apple iOS или Windows Phone неактивно, оно не может отвечать на новые события, такие как приглашение на обмен мгновенными сообщениями, пропущенные мгновенные сообщения, пропущенные звонки и голосовую почту, так как эти устройства не поддерживаются. Мобильные приложения, работающие в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="ce8f1-146">В этих случаях уведомление о новом событии, которое называется Push- *уведомлением*, отправляется на мобильное устройство.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="ce8f1-147">Служба Mobility Service отправляет уведомление в облачную службу push-уведомлений, которая затем отправляет уведомление либо в службу извещающих уведомлений Apple (APNS) (для поддерживаемых устройств Apple iOS), либо в службу push-уведомлений Майкрософт (MPNS). ) (для Windows Phone), который затем отправляет его на мобильное устройство.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="ce8f1-148">Затем пользователь может ответить на уведомление на мобильном устройстве, чтобы активировать приложение.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="ce8f1-149">Мобильный телефон Lync 2010 на устройствах Apple и Windows Phone использует push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="ce8f1-150">Мобильная клиентская программа Lync 2013 для устройств Apple, представленная в накопительных обновлениях для Lync Server 2013: Февраль 2013, больше не использует push-уведомление или клиринговый номер принудительного уведомления (ПНЧ).</span><span class="sxs-lookup"><span data-stu-id="ce8f1-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="ce8f1-151">На приведенной ниже схеме показано, как служба push-уведомлений попадает в топологию сервера Lync Server 2013, в которой используются мобильные клиенты УКВА и Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="ce8f1-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="ce8f1-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="ce8f1-153">Введено в накопительном обновлении для Lync Server 2010: Ноябрь 2011, служба МККС предоставляет услуги для мобильных клиентов Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="ce8f1-154">На приведенной ниже схеме показана служба push-уведомлений, применяемая к топологии с помощью мобильных клиентов МККС и Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="ce8f1-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="ce8f1-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="ce8f1-156">Поддерживаемые топологии</span><span class="sxs-lookup"><span data-stu-id="ce8f1-156">Supported Topologies</span></span>

<span data-ttu-id="ce8f1-157">Применение накопительных обновлений для Lync Server 2013: Февраль 2013 добавляет веб-компоненты УКВА для поддержки мобильных функций мобильных клиентов Lync 2013 в указанных ниже топологиях.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="ce8f1-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ce8f1-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="ce8f1-159">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ce8f1-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="ce8f1-160">Пограничный сервер может быть сервером Lync Server 2010 Edge.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="ce8f1-161">Развертывание Lync Server 2013 без накопительных обновлений для Lync Server 2013: Февраль 2013 использует службу МККС Mobility Service и может предоставлять услуги только для Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ce8f1-162">Служба Mobility Service поддерживается на серверах переднего плана, размещенных с помощью роли сервера «исправления» с двумя сетевыми интерфейсами, но для настройки интерфейсов необходимо выполнить соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="ce8f1-163">Необходимо назначить IP-адреса определенному интерфейсу, который будет взаимодействовать как сервер-посредник, и IP-адрес сетевого интерфейса, который будет взаимодействовать как сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="ce8f1-164">Это можно сделать в построителе топологии путем выбора IP-адреса для каждой службы вместо использования по умолчанию <STRONG>всех настроенных IP-адресов</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ce8f1-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce8f1-165">См. также</span><span class="sxs-lookup"><span data-stu-id="ce8f1-165">See Also</span></span>


[<span data-ttu-id="ce8f1-166">Планирование доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce8f1-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="ce8f1-167">Развертывание доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce8f1-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="ce8f1-168">Планирование автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce8f1-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

