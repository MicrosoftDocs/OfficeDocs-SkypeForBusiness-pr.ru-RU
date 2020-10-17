---
title: 'Lync Server 2013: изменения в Lync Server, влияющие на планирование пограничных серверов'
description: 'Lync Server 2013: изменения в Lync Server, затрагивающие планирование пограничных серверов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660a281d858cf92a48d5eaed6d5caf3141b3817
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543755"
---
# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="ce0ca-103">Изменения в Lync Server 2013, затрагивающие планирование пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="ce0ca-103">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce0ca-104">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ce0ca-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ce0ca-105">Lync Server 2013 содержит новые функции, расширяющие возможности и методы связи для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-105">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="ce0ca-106">Кроме того, Lync Server 2013 вводит изменения в существующие службы для улучшения интеграции и расширения служб, доступных в Организации.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-106">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="ce0ca-107">Ниже приведена сводка изменений, которые могут повлиять на планирование и развертывание служб пограничного сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-107">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="ce0ca-108">Поддержка IPv6-адресации</span><span class="sxs-lookup"><span data-stu-id="ce0ca-108">Support for IPv6 Addressing</span></span>

<span data-ttu-id="ce0ca-109">Lync Server 2013 поддерживает IPv6-адресацию для всех служб пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-109">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="ce0ca-110">Если вы предоставили IPv6-адреса для интерфейсов с помощью конфигурации в Windows Server, вы можете использовать IPv6-адреса в конфигурации пограничного сервера через конфигурацию IP-адресов в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-110">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="ce0ca-111">Кроме того, IPv6-адреса поддерживаются протоколом XMPP.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-111">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="ce0ca-112">Дополнительной настройки не требуется.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-112">No additional configuration is required.</span></span> <span data-ttu-id="ce0ca-113">Если в топологии настроена IPv6-адресация, протокол XMPP будет использовать ее, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-113">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="ce0ca-114">Добавленные требования для поддержки IPv6 в Lync Server 2013 — создание записей системы доменных имен для записей, которые должны быть обнаружены и разрешены в IPv6-адресе.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-114">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="ce0ca-115">Служба DNS для IPv6 использует записи узла, называемые **AAAA** (quad-A).</span><span class="sxs-lookup"><span data-stu-id="ce0ca-115">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="ce0ca-116">Другие типы записей аналогичны соответствующим записям IPv4.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-116">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="ce0ca-117">Поддержка развертывания протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="ce0ca-117">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="ce0ca-118">Пограничный сервер содержит полностью интегрированный прокси-сервер XMPP (развернутый на пограничных серверах) и шлюз XMPP (развернут на серверах переднего плана).</span><span class="sxs-lookup"><span data-stu-id="ce0ca-118">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="ce0ca-119">Вы можете развернуть федерацию XMPP как дополнительный компонент.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-119">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="ce0ca-120">Добавляя и настраивая прокси-сервер XMPP и шлюз XMPP, вы можете разрешить пользователям Microsoft Lync 2013 добавлять контакты из партнеров на основе XMPP для обмена мгновенными сообщениями и сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-120">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce0ca-121">В настоящее время службы XMPP на пограничном сервере обеспечивают обмен мгновенными сообщениями и сведения о присутствии между клиентами Lync Server и контактами на XMPP.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-121">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="ce0ca-122">Кроме того, XMPP размещается только в одном узле.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-122">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ce0ca-123">Функция XMPP Lync Server 2013 тестируется и поддерживается корпорацией Майкрософт для федерации обмена мгновенными сообщениями с Google говорите.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-123">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="ce0ca-124">Для любой другой системы XMPP обратитесь к сторонним поставщикам, чтобы убедиться, что они поддерживают Федерацию с Lync Server 2013, а также рекомендации по развертыванию и устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-124">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="ce0ca-125">Поддержка  развертывание сертификатов проверки подлинности аудио и видео и проверки подлинности между серверами</span><span class="sxs-lookup"><span data-stu-id="ce0ca-125">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="ce0ca-p107">Сертификат используется для создания маркеров, которые выдаются клиентам и другим потребителям службы проверки подлинности аудио и видео, а также для проверки подлинности между серверами. Тип сертификата проверки подлинности аудио и видео — *AudioVideoAuthentication*, а тип сертификата проверки подлинности между серверами — *OAuthTokenIssuer*.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-p107">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication. The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="ce0ca-p108">Применительно к проверке подлинности аудио и видео маркеры  используются для запросов выделения портов и кэшируются на срок до 8 часов — это срок жизни маркера по умолчанию. При обычных условиях работы это очень надежный метод создания и распространения материалов проверки подлинности между потребителями аудио и видео. Однако сертификаты имеют ограниченный срок службы, который заканчивается в предварительно заданное время (на основе даты создания и политик, примененных в центре сертификации, выдавшем сертификат: как правило, 2 года для этого типа сертификата). Когда срок действия сертификата истекает, любые маркеры, создаваемые этим сертификатом и кэшированные потребителями, становятся недопустимыми. Любые попытки использовать маркер, созданный сертификатом с истекшим сроком действия, приводит к сбою ретрансляции мультимедиа, что приведет к невозможности формирования аудио- и видеосеансов. Клиент должен получить новый маркер, созданный допустимым сертификатом, чтобы восстановить утраченные функции аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-p108">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token. Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers. However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate). When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid. Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail. The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="ce0ca-134">Проверка подлинности между серверами управляется глобальным сертификатом, который запрашивается и применяется на всех серверах в развертывании.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-134">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="ce0ca-135">Сертификат отвечает за проверку подлинности серверов в Lync Server 2013, а также проверку подлинности в Exchange 2013 и Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-135">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="ce0ca-136">Дополнительные сведения о том, как работает проверка подлинности серверов и серверов, можно найти [в статье Управление межсерверной проверкой подлинности (OAuth) и партнерских приложений в Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span><span class="sxs-lookup"><span data-stu-id="ce0ca-136">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="ce0ca-137">Одно очень важное отличие между проверкой подлинности аудио и видео и проверкой подлинности между серверами заключается в сроке службы проверки подлинности или маркеров.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-137">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="ce0ca-138">Для проверки подлинности аудио и видео срок службы маркеров составляет восемь часов.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-138">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="ce0ca-139">Для проверки подлинности между серверами срок службы маркеров составляет 24 часа.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-139">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="ce0ca-140">В соответствии с этим следует планировать развертывание каждого типа сертификата.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-140">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="ce0ca-141">Новая возможность для Lync Server 2013 — это возможность поэтапного замены сертификата проверки подлинности аудио-и видеоданных и сервера на сертификат проверки подлинности сервера в течение срока действия текущего сертификата.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-141">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="ce0ca-142">После этого новый сертификат используется для создания новых маркеров или запросов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-142">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="ce0ca-143">но сохраняет старый сертификат для проверки текущих сеансов и проверки подлинности..</span><span class="sxs-lookup"><span data-stu-id="ce0ca-143">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="ce0ca-144">Это достигается благодаря эффективному предотвращению почти всех сбоев из-за истечения срока действия маркеров и сертификатов.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-144">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="ce0ca-145">Подробные сведения об этой функции и ее настройке можно найти в разделе [промежуточное хранение и сертификаты OAuth в Lync Server 2013 using in Set — CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="ce0ca-145">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="ce0ca-146">Снижение зависимости от определения сходства на основе файлов Cookie</span><span class="sxs-lookup"><span data-stu-id="ce0ca-146">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="ce0ca-147">В предыдущих версиях Lync Server и Office Communications Server веб-службы использовали сходство на основе файлов cookie, чтобы убедиться, что состояние сеансов клиента и веб-служб было сохранено.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-147">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="ce0ca-148">Lync Server 2013 веб-службы используют встроенный механизм сходства, который исключает большинство требований для сходства на основе файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-148">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ce0ca-149">Клиент Microsoft Lync 2010 Mobile по-прежнему должен использовать сходство на основе файлов cookie и потребует настройки сходства на основе файлов cookie, пока все клиенты не будут перенесены в предстоящие клиенты Microsoft Lync Mobile (Дата выпуска еще не определена).</span><span class="sxs-lookup"><span data-stu-id="ce0ca-149">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="ce0ca-150">Сведения о сходстве на основе файлов cookie в Lync Server 2013 приведены в статье [компоненты, необходимые для доступа внешних пользователей в Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ce0ca-150">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="ce0ca-151">Улучшения автоматического обнаружения</span><span class="sxs-lookup"><span data-stu-id="ce0ca-151">AutoDiscover Enhancements</span></span>

<span data-ttu-id="ce0ca-152">Функция автообнаружения в Lync Server 2013 позволяет клиентам искать дополнительные функции, доступные для взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-152">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="ce0ca-153">Функция автообнаружения впервые появилась в накопительном пакете обновления для Lync Server 2010: Ноябрь 2011 для мобильных устройств и Microsoft Lync 2010 для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-153">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="ce0ca-154">Функция автообнаружения (также известная с помощью имен записей DNS LyncDiscover и LyncDiscoverInternal) позволяет клиентам искать и использовать службы Mobility Service (для мобильных клиентов Microsoft Lync 2010), веб-приложение Microsoft Lync и веб-планировщик Lync, а также связь с Microsoft Exchange Server и SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-154">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="ce0ca-155">Автообнаружение устанавливается как обычная часть установки и развертывания инфраструктуры и серверов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-155">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="ce0ca-156">В построителе топологий и мастере развертывания Lync Server устранена большая часть задач настройки, которые были необходимы в накопительном обновлении для Lync Server 2010: Ноябрь 2011.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-156">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="ce0ca-157">Службы для мобильных клиентов</span><span class="sxs-lookup"><span data-stu-id="ce0ca-157">Services for Mobile Clients</span></span>

<span data-ttu-id="ce0ca-158">В накопительном пакете обновления для Lync Server 2010: Ноябрь 2011, службы Mobility Services в Lync Server 2013 позволяют мобильным телефонам, работающим на Lync Mobile и планшетных устройствах, использовать поддерживаемые мобильные устройства Apple iOS, Android, Windows Phone и Nokia для выполнения таких действий, как отправка и получение мгновенных сообщений, просмотр контактов и Просмотр сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-158">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="ce0ca-159">Кроме того, мобильные устройства поддерживают некоторые функции корпоративной голосовой связи, такие как присоединение к собранию одним щелчком, "Позвонить с рабочего", звонок с одного номера, голосовая почта и уведомление о пропущенных вызовах.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-159">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce0ca-160">Службы Mobility Services используются обратный прокси-сервер и опубликованные службы, развернутые на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-160">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="ce0ca-161">Вносить изменения в пограничные серверы не требуется.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-161">No changes are required to Edge Servers.</span></span> <span data-ttu-id="ce0ca-162">Необходимо как минимум исходящий трафик SIP/TCP/5061from сервер, на котором работает служба пограничного доступа Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-162">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="ce0ca-163">Роль Директора необязательна</span><span class="sxs-lookup"><span data-stu-id="ce0ca-163">Director Role is Optional</span></span>

<span data-ttu-id="ce0ca-164">Роль сервера директор в топологии Lync Server 2013 не изменилась.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-164">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="ce0ca-165">Она все так же служит для размещения веб-служб, предварительной проверки подлинности входящих пользовательских запросов и направления внешних пользователей в домашний пул.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-165">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="ce0ca-166">Изменив роль директора на необязательную роль, корпорация Майкрософт не планирует уменьшить значение директора.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-166">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="ce0ca-167">Цель — уменьшить количество серверов и другие требования к оборудованию (например, подсистемы балансировки нагрузки для директоров) без ослабления функциональных возможностей и функций.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-167">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="ce0ca-168">Так как серверы переднего плана могут выполнять те же задачи, что и директор, не влияя на предоставляемые службы, вы можете развернуть директора, если вы решили.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-168">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="ce0ca-169">Вы можете безопасно исключить директора, чтобы серверы переднего плана предоставляли те же службы на месте директора.</span><span class="sxs-lookup"><span data-stu-id="ce0ca-169">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

