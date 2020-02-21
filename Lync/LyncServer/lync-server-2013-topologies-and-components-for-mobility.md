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
ms.openlocfilehash: 9ccce5823e997cafc5e8c8e7555df18bc67d1fe6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="3671d-102">Топологии и компоненты для мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3671d-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3671d-103">_**Последнее изменение темы:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="3671d-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="3671d-104">Для поддержки мобильных приложений Lync на мобильных устройствах Lync Server 2013 предоставляет три службы: Lync Server 2013 MCX Mobility Service, служба автообнаружения Lync Server 2013 и Служба push-уведомлений Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3671d-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="3671d-105">Накопительные пакеты обновления для Lync Server 2013: Февраль 2013 Добавление бесплатной, но расширенной службы для мобильных клиентов Lync 2013 — поддержка мобильных устройств с помощью веб-API объединенных коммуникаций или UCWA.</span><span class="sxs-lookup"><span data-stu-id="3671d-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="3671d-106">В этом разделе кратко описываются эти компоненты и определяются топологии Lync Server 2013, поддерживающие мобильность.</span><span class="sxs-lookup"><span data-stu-id="3671d-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3671d-107">Службы мобильной связи также доступны в гибридных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="3671d-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="3671d-108">Если все пользователи вашей организации подключены к сети, вам не требуется развертывать службы для поддержки возможностей мобильной связи.</span><span class="sxs-lookup"><span data-stu-id="3671d-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="3671d-109">Необходимо определить параметр для службы автообнаружения, чтобы разрешить мобильным пользователям находить свои сетевые удостоверения.</span><span class="sxs-lookup"><span data-stu-id="3671d-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3671d-110">При планировании подключения внешних пользователей (например, Федерации, внешнего доступа пользователей или функций мобильности) необходимо использовать пограничные серверы с сервером Standard Edition и сервером переднего плана или интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="3671d-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="3671d-111">На сервере Standard Edition и сервере переднего плана или интерфейсном пуле отсутствуют необходимые компоненты, чтобы разрешить внешним пользователям получать доступ к внутреннему развертыванию или для внутреннего развертывания для взаимодействия с внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="3671d-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="3671d-112">Для всех сценариев, включающих внешние пользователи, взаимодействующие с внутренними пользователями, в том числе мобильность, необходимо развернуть хотя бы один пограничный сервер и один обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="3671d-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="3671d-113"><EM>Push-уведомления</EM> использует тип Федерации для служб Lync Online, в котором размещается Клиринговый дом push-уведомлений (PNCH).</span><span class="sxs-lookup"><span data-stu-id="3671d-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="3671d-114">Push-уведомления — это звуковые оповещения, оповещения на экране (текст) и эмблемы, помещенные приложениями в Apple iPhone, iPad и Windows Phone, когда мобильное устройство неактивно.</span><span class="sxs-lookup"><span data-stu-id="3671d-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="3671d-115">PNCH получает push-уведомления от Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3671d-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="3671d-116">Когда PNCH получает уведомление о сообщении, PNCH пересылает уведомление мобильным клиентам через службу push-уведомлений Apple или службу push-уведомлений Lync Server 2013, основываясь на мобильном клиенте, для которого предназначено сообщение.</span><span class="sxs-lookup"><span data-stu-id="3671d-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="3671d-117">PNCH является обязательной службой для этих мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="3671d-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="3671d-118">Чтобы создать федерацию для Lync Online, PNCH использует пограничные серверы и сертификаты для обеспечения конфиденциальности и проверки подлинности, политик и правильно настроенных записей службы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="3671d-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="3671d-119">Клиенты Nokia Symbian и Lync Mobile на основе Android не используют PNCH.</span><span class="sxs-lookup"><span data-stu-id="3671d-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="3671d-120">Для получения дополнительных сведений о планировании и развертывании пограничных серверов ознакомьтесь со статьей <A href="lync-server-2013-planning-for-external-user-access.md">Планирование доступа внешних пользователей в Lync server 2013</A> и <A href="lync-server-2013-deploying-external-user-access.md">развертывание доступа внешних пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3671d-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="3671d-121">Мобильные клиенты Lync 2013 для устройств Apple, выпущенные с помощью накопительных обновлений для Lync Server 2013: Февраль 2013, больше не используют push-уведомления или клиринговый PNCH push-уведомлений ().</span><span class="sxs-lookup"><span data-stu-id="3671d-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="3671d-122">Мобильные клиенты Lync 2013 на Windows Phone по-прежнему используют push-уведомления и (PNCH).</span><span class="sxs-lookup"><span data-stu-id="3671d-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="3671d-123">Компоненты, предназначенные для поддержки мобильной связи</span><span class="sxs-lookup"><span data-stu-id="3671d-123">Mobility Components</span></span>

<span data-ttu-id="3671d-124">Службы, поддерживающие мобильную связь:</span><span class="sxs-lookup"><span data-stu-id="3671d-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="3671d-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   предоставляет службы для связи в режиме реального времени с мобильными и веб-клиентами в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3671d-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="3671d-126">При развертывании накопительных обновлений для Lync Server 2013: Февраль 2013 на интерфейсном сервере и директоре, установка создает виртуальный каталог во внутренних и внешних веб-службах (Ucwa).</span><span class="sxs-lookup"><span data-stu-id="3671d-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="3671d-127">Веб-компонент, который входит в состав виртуального каталога Ucwa, принимает вызовы от клиентов, поддерживающих UCWA.</span><span class="sxs-lookup"><span data-stu-id="3671d-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="3671d-128">Клиентские приложения взаимодействуют через интерфейс REST для сведений о присутствии, контактах, обмене мгновенными сообщениями, VoIP, видеоконференций и совместной работе.</span><span class="sxs-lookup"><span data-stu-id="3671d-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="3671d-129">UCWA использует канал на основе протокола P — GET для отправки событий, таких как входящий вызов, входящее сообщение или сообщение, в клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="3671d-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3671d-130">Передача состояния <EM>REST</EM> или Presentation — это программный стиль распределенных систем, который широко применяется во многих формах и хорошо подходит для требований веб-служб в целом.</span><span class="sxs-lookup"><span data-stu-id="3671d-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="3671d-131">**Lync Server 2013 Mobility Service (MCX)**   эта служба поддерживает функциональные возможности Lync, такие как обмен мгновенными сообщениями, сведения о присутствии и контакты, на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="3671d-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="3671d-132">Служба Mobility Service устанавливается на каждом сервере переднего плана в каждом пуле, который поддерживает функциональность Lync на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="3671d-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="3671d-133">При установке Lync Server 2013 новый виртуальный каталог (MCX) создается как на внутреннем веб-сайте, так и на внешнем веб-сайте на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="3671d-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3671d-134">Lync Server 2013 с накопительными обновлениями для Lync Server 2013: Февраль 2013 поддерживает как службу Mobility Service, появившуюся в накопительном пакете обновления для Lync Server 2010: Ноябрь 2011, который обычно называется MCX, и веб-компонент UCWA.</span><span class="sxs-lookup"><span data-stu-id="3671d-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="3671d-135">Сочетание этих двух служб Mobility Services обеспечивает взаимодействие и использование пользователями Lync 2010 Mobile и Lync 2013 Mobile для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3671d-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="3671d-136">**Lync Server 2013 служба**   автообнаружения Эта служба определяет расположение пользователя и позволяет мобильным устройствам и другим клиентам Lync искать ресурсы, такие как внутренний и внешний URL-адрес для веб-служб Lync Server 2013, а также URL-адрес для MCX или UCWA, независимо от расположения в сети.</span><span class="sxs-lookup"><span data-stu-id="3671d-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="3671d-137">Автоматическое обнаружение использует жестко заданные имена узлов (lyncdiscoverinternal для пользователей в сети, lyncdiscover для пользователей за пределами сети) и домен SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="3671d-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="3671d-138">Он поддерживает клиентские подключения, использующие HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3671d-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="3671d-139">Служба автообнаружения устанавливается на каждом сервере переднего плана и каждом директоре в каждом пуле, поддерживающем функциональность Lync на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="3671d-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="3671d-140">При установке службы автообнаружения новый виртуальный каталог (автообнаружение) создается как на внутреннем веб-сайте, так и на внешнем веб-сайте как на серверах переднего плана, так и в директориях.</span><span class="sxs-lookup"><span data-stu-id="3671d-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3671d-141">Служба автообнаружения указана здесь, так как она остается критическим компонентом при предоставлении клиентских служб для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="3671d-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="3671d-142">Роль автообнаружения в Lync Server 2013 была расширена для предоставления служб для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="3671d-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="3671d-143">Более подробную информацию о планировании службы автообнаружения можно узнать <A href="lync-server-2013-planning-for-autodiscover.md">в статье Планирование автообнаружения в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3671d-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="3671d-144">**Служба push-уведомлений**   эта служба является облачной службой, расположенной в центре обработки данных Lync Online.</span><span class="sxs-lookup"><span data-stu-id="3671d-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="3671d-145">Если мобильное приложение Lync на поддерживаемом устройстве Apple iOS или Windows Phone неактивно, оно не может реагировать на новые события, такие как приглашение на обмен мгновенными сообщениями, пропущенное мгновенное сообщение, пропущенный вызов или Голосовая почта, так как эти устройства не поддерживаются. Мобильные приложения, работающие в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="3671d-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="3671d-146">В таких случаях уведомление о новом событии, которое называется Push- *уведомлением*, отправляется на мобильное устройство.</span><span class="sxs-lookup"><span data-stu-id="3671d-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="3671d-147">Служба Mobility Service отправляет уведомление в облачную службу push-уведомлений, которая отправляет уведомление либо в службу push-уведомлений Apple (для поддерживаемых устройств Apple iOS), либо на службу push-уведомлений Майкрософт (MPNS ) (для Windows Phone), который затем отправляет его на мобильное устройство.</span><span class="sxs-lookup"><span data-stu-id="3671d-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="3671d-148">Затем пользователь может ответить на уведомление на мобильном устройстве, чтобы активировать приложение.</span><span class="sxs-lookup"><span data-stu-id="3671d-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="3671d-149">Устройства Lync 2010 Mobile на устройствах Apple и Windows Phone используют push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="3671d-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="3671d-150">Мобильный клиент Lync 2013 для устройств Apple, представленных в накопительных пакетах обновления для Lync Server 2013: Февраль 2013, больше не использует push-уведомления или клиринговый дом push-уведомлений (PNCH).</span><span class="sxs-lookup"><span data-stu-id="3671d-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="3671d-151">На следующей схеме показано, как служба push-уведомлений находится в топологии Lync Server 2013, в которой используются мобильные клиенты UCWA и Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3671d-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="3671d-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="3671d-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="3671d-153">Представлено в накопительном обновлении для Lync Server 2010: Ноябрь 2011, служба MCX предоставляет службы для мобильных клиентов Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="3671d-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="3671d-154">На следующей схеме показана служба push-уведомлений, которая применяется к топологии с помощью MCX и Lync 2010 Mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="3671d-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="3671d-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="3671d-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="3671d-156">Поддерживаемые топологии</span><span class="sxs-lookup"><span data-stu-id="3671d-156">Supported Topologies</span></span>

<span data-ttu-id="3671d-157">Применение накопительных обновлений для Lync Server 2013: в феврале 2013 добавляется веб-компоненты UCWA для поддержки мобильных функций мобильных клиентов для Lync 2013 в следующих топологиях:</span><span class="sxs-lookup"><span data-stu-id="3671d-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="3671d-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3671d-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="3671d-159">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="3671d-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="3671d-160">Пограничный сервер может быть пограничным сервером Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3671d-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="3671d-161">Развертывание Lync Server 2013 без накопительных обновлений для Lync Server 2013: Февраль 2013 будет использовать службу Mobility MCX и сможет предоставлять службы только для Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="3671d-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3671d-162">Служба Mobility Service поддерживается на серверах переднего плана, размещенных с помощью роли сервера-посредника с двумя сетевыми интерфейсами, но для настройки интерфейсов необходимо выполнить соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="3671d-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="3671d-163">Необходимо назначить IP-адреса конкретному интерфейсу, который будет взаимодействовать с сервером-посредником, а также IP-адресом сетевого интерфейса, который будет взаимодействовать как сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="3671d-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="3671d-164">Это можно сделать в построителе топологий, выбрав правильный IP-адрес для каждой службы, вместо использования по умолчанию <STRONG>использовать все настроенные IP-адреса</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3671d-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3671d-165">См. также</span><span class="sxs-lookup"><span data-stu-id="3671d-165">See Also</span></span>


[<span data-ttu-id="3671d-166">Планирование доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3671d-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="3671d-167">Развертывание доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3671d-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="3671d-168">Планирование автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3671d-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

