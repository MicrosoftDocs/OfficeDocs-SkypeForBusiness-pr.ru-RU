---
title: 'Lync Server 2013: компоненты, необходимые для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895f2d4837eb465f0eead2b70cf1d603504699ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="03172-102">Компоненты, необходимые для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03172-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03172-103">_**Тема последнего изменения:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="03172-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="03172-104">Большинство пограничных компонентов развертывается в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="03172-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="03172-105">Следующие компоненты составляют топологию пограничного периметра сети.</span><span class="sxs-lookup"><span data-stu-id="03172-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="03172-106">За исключением случаев, когда отмечено иное, компоненты являются частью [сценариев доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) и находятся в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="03172-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="03172-107">К пограничным компонентам относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="03172-107">Edge components include the following:</span></span>

  - <span data-ttu-id="03172-108">Edge Servers</span><span class="sxs-lookup"><span data-stu-id="03172-108">Edge Servers</span></span>

  - <span data-ttu-id="03172-109">Reverse proxies</span><span class="sxs-lookup"><span data-stu-id="03172-109">Reverse proxies</span></span>

  - <span data-ttu-id="03172-110">Firewalls</span><span class="sxs-lookup"><span data-stu-id="03172-110">Firewalls</span></span>

  - <span data-ttu-id="03172-111">Директоры (не являются обязательными и логически расположены во внутренней сети);</span><span class="sxs-lookup"><span data-stu-id="03172-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="03172-112">Балансировка нагрузки для масштабируемых пограничных топологий (балансировка нагрузки DNS или подсистема аппаратной балансировки нагрузки)</span><span class="sxs-lookup"><span data-stu-id="03172-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="03172-p102">Использование в одном интерфейсе балансировки нагрузки через DNS, а в другом аппаратной балансировки нагрузки не поддерживается. Необходимо использовать либо ту, либо другую систему балансировки нагрузки для обоих интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="03172-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="03172-115">пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="03172-115">Edge Servers</span></span>

<span data-ttu-id="03172-116">Пограничные серверы отправляют и получают сетевой трафик для служб, предоставляемых внутренним развертыванием внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="03172-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="03172-117">На пограничном сервере выполняются следующие службы:</span><span class="sxs-lookup"><span data-stu-id="03172-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="03172-118">**Служба Edge Access**   служба Edge Access предоставляет единственную доверенную точку соединения для входящего и исходящего трафика протокола SIP.</span><span class="sxs-lookup"><span data-stu-id="03172-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="03172-119">**Служба Edge для веб-конференций**   служба EDGE позволяет внешним пользователям присоединяться к собраниям, размещенным во внутренней среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03172-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="03172-120">**Служба EDGE (/v**   ) служба EDGE обеспечивает доступ к аудио-и видеофайлам, приложениям и передачам файлов внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="03172-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="03172-121">Пользователи могут добавлять звуковые и видеозаписи для собраний, которые содержат внешних участников, и могут общаться с помощью аудио-и видеофайлов прямо с внешним пользователем в сеансах точка-точка.</span><span class="sxs-lookup"><span data-stu-id="03172-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="03172-122">Служба Edge/V также поддерживает общий доступ к рабочему столу и передачу файлов.</span><span class="sxs-lookup"><span data-stu-id="03172-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="03172-123">**Служба прокси-сервера КСМПП**   . прокси-служба КСМПП принимает и отправляет сообщения и протоколы КСМПП для КСМПП федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="03172-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="03172-124">Авторизованные внешние пользователи могут получить доступ к пограничным серверам, чтобы подключиться к внутренней среде Lync Server 2013, но пограничные серверы не предоставляют никаких средств для другого доступа к внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="03172-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03172-125">Пограничные серверы развертываются для предоставления подключений к включенным клиентам Lync и другим серверам Microsoft EDGE (как в сценариях Федерации).</span><span class="sxs-lookup"><span data-stu-id="03172-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="03172-126">Они не предназначены для разрешения подключений от других типов клиентов конечных точек или серверов.</span><span class="sxs-lookup"><span data-stu-id="03172-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="03172-127">Сервер шлюза КСМПП можно развернуть, чтобы разрешить подключения с настроенными партнерами КСМПП.</span><span class="sxs-lookup"><span data-stu-id="03172-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="03172-128">Пограничный сервер и шлюз КСМПП могут поддерживать только соединения конечных точек из этих клиентов и типов Федерации.</span><span class="sxs-lookup"><span data-stu-id="03172-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="03172-129">Обратный прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="03172-129">Reverse Proxy</span></span>

<span data-ttu-id="03172-130">Обратный прокси-сервер требуется для указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="03172-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="03172-131">Разрешение пользователям подключаться к собраниям или конференц-связи с телефонным подключением с помощью простого URL-адреса</span><span class="sxs-lookup"><span data-stu-id="03172-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="03172-132">Чтобы разрешить внешним пользователям загружать содержимое собрания</span><span class="sxs-lookup"><span data-stu-id="03172-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="03172-133">Предоставление внешним пользователям разрешения на развертывание групп рассылки</span><span class="sxs-lookup"><span data-stu-id="03172-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="03172-134">Предоставление пользователю разрешения на получение сертификата для проверки подлинности на основе сертификата клиента</span><span class="sxs-lookup"><span data-stu-id="03172-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="03172-135">Как разрешить удаленным пользователям загружать файлы с сервера адресной книги или отправлять запросы в службу веб-запросов к адресной книге.</span><span class="sxs-lookup"><span data-stu-id="03172-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="03172-136">Разрешение удаленным пользователям получать обновления программного обеспечения клиента и устройства</span><span class="sxs-lookup"><span data-stu-id="03172-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="03172-137">Использование мобильных устройств для автоматического доступа к серверам переднего плана, на котором предлагаются службы Mobility Service</span><span class="sxs-lookup"><span data-stu-id="03172-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="03172-138">Включение push-уведомлений для мобильных устройств из служб push-уведомлений Office 365 или Apple</span><span class="sxs-lookup"><span data-stu-id="03172-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="03172-139">Дополнительные сведения об обратном прокси и требованиях, которым должны соответствовать обратные прокси-серверы, приведены в разделе [требования к конфигурации для обратного прокси в Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="03172-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03172-140">Внешние пользователи не нуждаются в подключении к вашей организации через виртуальную частную сеть (VPN) для участия в обмене данными с помощью Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03172-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="03172-141">Если в вашей организации реализована технология VPN и пользователи используют VPN для Lync, трафик мультимедиа (например, видеоконференции) может негативно сказаться на нем.</span><span class="sxs-lookup"><span data-stu-id="03172-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="03172-142">Рекомендуется предоставлять трафик мультимедиа для подключения к службе AV EDGE и минуя VPN.</span><span class="sxs-lookup"><span data-stu-id="03172-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="03172-143">Дополнительные сведения можно найти в статье блога на NextHop, в <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>разделе Включение туннеля VPN в Lync Media</span><span class="sxs-lookup"><span data-stu-id="03172-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="03172-144">Брандмауэр</span><span class="sxs-lookup"><span data-stu-id="03172-144">Firewall</span></span>

<span data-ttu-id="03172-145">Вы можете развернуть топологию пограничного сервера только с помощью внешнего брандмауэра или внешних и внутренних брандмауэров.</span><span class="sxs-lookup"><span data-stu-id="03172-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="03172-146">Архитектурные сценарии включают два брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="03172-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="03172-147">Использование двух брандмауэров является рекомендуемым подходом, так как он обеспечивает строгую маршрутизацию из одной сети на другую и защищает внутреннее развертывание за счет двух уровней брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="03172-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="03172-148">Директор</span><span class="sxs-lookup"><span data-stu-id="03172-148">Director</span></span>

<span data-ttu-id="03172-149">Режиссер — это отдельная необязательная роль сервера в Lync Server 2013, которая не является домашней учетной записью пользователя, а также предоставление служб присутствия или конференций.</span><span class="sxs-lookup"><span data-stu-id="03172-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="03172-150">Она служит внутренним сервером следующего прыжка, на который пограничный сервер маршрутизирует входящий трафик SIP, предназначенный для внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="03172-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="03172-151">Режиссер выполняет предварительную проверку подлинности входящих запросов и перенаправляет их в домашнюю группу пользователя или на сервер.</span><span class="sxs-lookup"><span data-stu-id="03172-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="03172-152">С помощью предварительной проверки подлинности в режиссере можно удалять запросы из учетных записей пользователей, неизвестных для развертывания.</span><span class="sxs-lookup"><span data-stu-id="03172-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="03172-153">Режиссер помогает разрушить стандартные серверы выпусков и серверы переднего плана в пулах переднего плана Enterprise Edition из вредоносных данных, таких как атаки типа "отказ от обслуживания" (DoS).</span><span class="sxs-lookup"><span data-stu-id="03172-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="03172-154">Если при такой атаке сеть перегружается с недопустимым внешним трафиком, трафик завершается на режиссере.</span><span class="sxs-lookup"><span data-stu-id="03172-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="03172-155">Подробнее об использовании режиссеров можно узнать в разделе [сценарии для режиссера в Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="03172-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03172-156">См. также</span><span class="sxs-lookup"><span data-stu-id="03172-156">See Also</span></span>


[<span data-ttu-id="03172-157">Требования к подсистеме балансировки нагрузки оборудования для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03172-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

