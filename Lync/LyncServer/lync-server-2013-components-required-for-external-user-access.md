---
title: 'Lync Server 2013: компоненты, необходимые для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca81e26e6a4b634b7b1f861ddfb0e0aedebca23f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="9f735-102">Компоненты, необходимые для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f735-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f735-103">_**Последнее изменение темы:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="9f735-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="9f735-104">Большинство пограничных компонентов развертывается в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="9f735-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="9f735-105">Указанные ниже компоненты составляют пограничную топологию этой сети.</span><span class="sxs-lookup"><span data-stu-id="9f735-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="9f735-106">За исключением случаев, когда отмечено, компоненты являются частью [сценариев доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) и находятся в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="9f735-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="9f735-107">К пограничным компонентам относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="9f735-107">Edge components include the following:</span></span>

  - <span data-ttu-id="9f735-108">Пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="9f735-108">Edge Servers</span></span>

  - <span data-ttu-id="9f735-109">Обратные прокси-серверы</span><span class="sxs-lookup"><span data-stu-id="9f735-109">Reverse proxies</span></span>

  - <span data-ttu-id="9f735-110">Брандмауэров</span><span class="sxs-lookup"><span data-stu-id="9f735-110">Firewalls</span></span>

  - <span data-ttu-id="9f735-111">Режиссеры (необязательные и логически расположенные во внутренней сети)</span><span class="sxs-lookup"><span data-stu-id="9f735-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="9f735-112">Балансировка нагрузки для масштабируемых пограничных топологий (балансировка нагрузки DNS или подсистема аппаратной балансировки нагрузки)</span><span class="sxs-lookup"><span data-stu-id="9f735-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9f735-p102">Использование балансировки нагрузки DNS в одном интерфейсе и аппаратной балансировки нагрузки в другом не поддерживается. Вам следует использовать для обоих интерфейсов аппаратную балансировку нагрузки либо балансировку нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="9f735-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="9f735-115">Пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="9f735-115">Edge Servers</span></span>

<span data-ttu-id="9f735-116">Пограничные серверы отправляют и получают сетевой трафик для служб, предоставляемых внутренним развертыванием внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="9f735-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="9f735-117">На пограничном сервере выполняются следующие службы:</span><span class="sxs-lookup"><span data-stu-id="9f735-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="9f735-118">**Служба**   пограничного доступа служба пограничного доступа предоставляет единую надежную точку подключения для исходящего и входящего трафика протокола SIP.</span><span class="sxs-lookup"><span data-stu-id="9f735-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="9f735-119">**Пограничная служба**   веб-конференций пограничная служба веб-конференций позволяет внешним пользователям присоединяться к собраниям, размещенным во внутреннем развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f735-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="9f735-120">**Пограничная служба**   аудио-и видеоданных, пограничная служба аудио, видео, общего доступа к приложениям и передачи файлов доступна внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="9f735-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="9f735-121">Ваши пользователи могут добавлять звук и видео в собрания, включающие в себя внешних участников, кроме того, они могут использовать звук и/или видео при прямом взаимодействии с внешним пользователем в рамках сеансов точка-точка.</span><span class="sxs-lookup"><span data-stu-id="9f735-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="9f735-122">Пограничная служба обработки аудио- и видеоданных также предоставляет поддержку совместного доступа к рабочему столу и передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="9f735-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="9f735-123">**Служба прокси-сервера XMPP**   служба прокси-сервера XMPP принимает и отправляет сообщения о протоколе расширения и из настроенных XMPP федеративным партнерам.</span><span class="sxs-lookup"><span data-stu-id="9f735-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="9f735-124">Авторизованные внешние пользователи могут получить доступ к пограничным серверам, чтобы подключиться к внутреннему развертыванию Lync Server 2013, но пограничные серверы не предоставляют никаких средств для любого другого доступа к внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="9f735-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f735-125">Пограничные серверы развертываются для предоставления подключений для включенных клиентов Lync и других пограничных серверов Microsoft (как в сценариях Федерации).</span><span class="sxs-lookup"><span data-stu-id="9f735-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="9f735-126">Они не предназначены для разрешения подключений от других типов клиентов или серверов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9f735-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="9f735-127">Чтобы разрешить подключения с настроенными партнерами XMPP, можно развернуть сервер шлюза XMPP.</span><span class="sxs-lookup"><span data-stu-id="9f735-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="9f735-128">Пограничный сервер и шлюз XMPP могут поддерживать подключения конечных точек только от этих типов клиентов и Федерации.</span><span class="sxs-lookup"><span data-stu-id="9f735-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="9f735-129">Обратный прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="9f735-129">Reverse Proxy</span></span>

<span data-ttu-id="9f735-130">Обратный прокси-сервер выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="9f735-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="9f735-131">Предоставление пользователям возможности подключения к собраниям или конференциям с телефонным подключением с помощью простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="9f735-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="9f735-132">Предоставление внешним пользователям возможности загружать содержимое собраний.</span><span class="sxs-lookup"><span data-stu-id="9f735-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="9f735-133">Предоставление внешним пользователям возможности расширять группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="9f735-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="9f735-134">Предоставление пользователю возможности получить пользовательский сертификат для проверки подлинности клиентов на основе сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9f735-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="9f735-135">Предоставление внешним пользователям возможности загружать файлы с сервера адресной книги или отправлять запросы в службу веб-запросов адресной книги.</span><span class="sxs-lookup"><span data-stu-id="9f735-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="9f735-136">Предоставление внешним пользователям возможности получать обновления для клиента и программного оборудования устройств.</span><span class="sxs-lookup"><span data-stu-id="9f735-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="9f735-137">Чтобы разрешить мобильным устройствам автоматически обнаруживать серверы переднего плана с мобильными службами</span><span class="sxs-lookup"><span data-stu-id="9f735-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="9f735-138">Обеспечение передачи push-уведомлений на мобильные устройства из служб push-уведомлений Office 365 или Apple</span><span class="sxs-lookup"><span data-stu-id="9f735-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="9f735-139">Дополнительные сведения о обратных прокси-серверах и требованиях, которым должны соответствовать обратные прокси-серверы, можно узнать в статье [требования к конфигурации для обратного прокси-сервера в Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="9f735-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f735-140">Внешним пользователям не требуется подключение к Организации виртуальной частной сети (VPN) для участия в связи с использованием Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f735-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="9f735-141">Если в организации реализована технология VPN, а пользователи используют VPN-подключение для Lync, трафик мультимедиа (например, видеоконференций) может быть неблагоприятно затронуты.</span><span class="sxs-lookup"><span data-stu-id="9f735-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="9f735-142">Вам рекомендуется предоставить средства, с помощью которых трафик мультимедиа может взаимодействовать непосредственно с пограничной службой обработки аудио- и видеоданных в обход VPN.</span><span class="sxs-lookup"><span data-stu-id="9f735-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="9f735-143">Дополнительные сведения можно найти в статье по веб-журналу NextHop: "Включение поддержки VPN-туннеля в Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>Media" по адресу.</span><span class="sxs-lookup"><span data-stu-id="9f735-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="9f735-144">Брандмауэра</span><span class="sxs-lookup"><span data-stu-id="9f735-144">Firewall</span></span>

<span data-ttu-id="9f735-p107">Вы можете развернуть свою пограничную топологию только с внутренним брандмауэром или как с внешним, так и с внутренним брандмауэром. Архитектуры в данном сценарии содержат два брандмауэра. Рекомендуется использовать два брандмауэра, так как при этом обеспечивается строгая маршрутизация с одной границы сети до другой, а также защита внутреннего развертывания двумя уровнями брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="9f735-p107">You can deploy your edge topology with only an external firewall or both external and internal firewalls. The scenario architectures include two firewalls. Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="9f735-148">Режиссер</span><span class="sxs-lookup"><span data-stu-id="9f735-148">Director</span></span>

<span data-ttu-id="9f735-149">Директор — это отдельная, необязательная роль сервера в Lync Server 2013, не являющиеся домашними учетными записями пользователей, или предоставление услуг по присутствию или конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="9f735-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="9f735-150">Он выступает в качестве внутреннего сервера следующего прыжка, на который пограничный сервер направляет входящий трафик SIP, предназначенный для внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="9f735-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="9f735-151">Директор выполняет предварительную проверку подлинности входящих запросов и перенаправляет их в домашний пул или на сервер пользователя.</span><span class="sxs-lookup"><span data-stu-id="9f735-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="9f735-152">Благодаря предварительной проверке подлинности в Директоре вы можете сбрасывать запросы от учетных записей пользователей, которые неизвестны развертыванию.</span><span class="sxs-lookup"><span data-stu-id="9f735-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="9f735-153">Директор помогает разделяют серверы Standard Edition и серверы переднего плана в интерфейсных пулах Enterprise Edition от вредоносного трафика, например из-за атак типа "отказ в обслуживании" (DoS).</span><span class="sxs-lookup"><span data-stu-id="9f735-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="9f735-154">Если при такой атаке сеть передается с недопустимым внешним трафиком, трафик завершается в директоре.</span><span class="sxs-lookup"><span data-stu-id="9f735-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="9f735-155">Сведения об использовании директоров приведены [в статье сценарии для директора в Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="9f735-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9f735-156">См. также</span><span class="sxs-lookup"><span data-stu-id="9f735-156">See Also</span></span>


[<span data-ttu-id="9f735-157">Требования к аппаратному подсистеме балансировки нагрузки для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f735-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

