---
title: 'Lync Server 2013: изменения Lync Server, затрагивающие планирование пограничного сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d13b40430455c87a60c0fadc20980df5a8aa1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="2d1fd-102">Изменения Lync Server 2013, затрагивающие планирование пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2d1fd-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d1fd-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2d1fd-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2d1fd-104">В Lync Server 2013 появились новые функции, расширяющие возможности и способы связи для пользователей.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="2d1fd-105">Кроме того, Lync Server 2013 предлагает изменения в существующих службах для лучшей интеграции и продления служб, доступных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="2d1fd-106">Ниже приведена сводка изменений, которые могут повлиять на планирование и развертывание служб сервера Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="2d1fd-107">Поддержка адресации IPv6</span><span class="sxs-lookup"><span data-stu-id="2d1fd-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="2d1fd-108">Lync Server 2013 поддерживает адресацию IPv6 для всех служб пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="2d1fd-109">Если вы указали IPv6-адреса для интерфейсов с помощью конфигурации в Windows Server, вы можете использовать IPv6-адреса в конфигурации пограничного сервера с помощью конфигурации IP Address Builder в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="2d1fd-110">Кроме того, расширенный протокол обмена сообщениями и присутствия (КСМПП) поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="2d1fd-111">Дополнительная настройка не требуется.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-111">No additional configuration is required.</span></span> <span data-ttu-id="2d1fd-112">Если в топологии настроен IPv6, КСМПП будет использовать IPv6 (там, где это необходимо).</span><span class="sxs-lookup"><span data-stu-id="2d1fd-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="2d1fd-113">Дополнительным требованием для поддержки IPv6 в Lync Server 2013 является создание записей системы доменных имен для записей, которые должны быть обнаружены и разрешены в IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="2d1fd-114">DNS-протокол IPv6 использует записи узла, определенные как **AAAA** и называемые "четырьмя-а".</span><span class="sxs-lookup"><span data-stu-id="2d1fd-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="2d1fd-115">Другие типы записей согласуются с их аналогами IPv4.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="2d1fd-116">Поддержка развертывания расширенного протокола передачи сообщений и КСМПП</span><span class="sxs-lookup"><span data-stu-id="2d1fd-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="2d1fd-117">Пограничный сервер представляет полностью интегрированный прокси-сервер КСМПП (развернутый на пограничном сервере) и шлюз КСМПП (развернутый на серверах переднего плана).</span><span class="sxs-lookup"><span data-stu-id="2d1fd-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="2d1fd-118">Вы можете развернуть КСМПП Федерацию как дополнительный компонент.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="2d1fd-119">Добавляя и настраивая прокси-сервер КСМПП и шлюз КСМПП, вы можете предоставить пользователям Microsoft Lync 2013 доступ к контактам в обмене мгновенными сообщениями (IM) и присутствии на основе КСМПП.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d1fd-120">В настоящее время службы КСМПП на пограничном сервере обеспечивают обмен мгновенными сообщениями и сведения о присутствии между клиентами Lync Server и контактами на КСМПП.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="2d1fd-121">Кроме того, КСМПП размещается только на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2d1fd-p106">Возможность XMPP сервера Lync Server 2013 была протестирована корпорацией Microsoft и поддерживается в части федеративного обмена мгновенными сообщениями с использованием Google Talk. По вопросам использования других XMPP-систем обращайтесь к сторонним поставщикам, чтобы выяснить, поддерживают ли они федерацию с Lync Server 2013, а также чтобы получить рекомендации по вопросам, связанным с устранением неполадок и развертыванием.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="2d1fd-124">Поддержка последовательной проверки подлинности звука, видео и сервера</span><span class="sxs-lookup"><span data-stu-id="2d1fd-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="2d1fd-125">Сертификат используется для создания маркеров, которые выдаются клиентам и другим потребителям службы проверки подлинности A/V и для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-125">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication.</span></span> <span data-ttu-id="2d1fd-126">Сертификат для проверки подлинности звука и видео имеет тип *аудиовидеоаусентикатион* , а сертификат проверки подлинности сервера и сервера имеет тип *оаустокениссуер*.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-126">The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="2d1fd-127">Для проверки подлинности звука и видео маркеры используются для проверки подлинности запросов на выделение портов и кэширования маркеров в течение 8 часов — по умолчанию срока действия маркера.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-127">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token.</span></span> <span data-ttu-id="2d1fd-128">В разделе нормальная работа — это очень надежный метод создания и распространения материалов проверки подлинности для потребителей/V.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-128">Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers.</span></span> <span data-ttu-id="2d1fd-129">Тем не менее, срок действия сертификатов ограничен и истекает предопределенную дату и время (в зависимости от даты создания и политики, принудительно примененные в центре сертификации, который создал сертификат) (обычно 2 года для этого типа сертификата).</span><span class="sxs-lookup"><span data-stu-id="2d1fd-129">However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate).</span></span> <span data-ttu-id="2d1fd-130">После истечения срока действия сертификата все маркеры, созданные с истекшим сроком действия сертификата и кэшированные клиентами, становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-130">When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid.</span></span> <span data-ttu-id="2d1fd-131">При попытке использования маркера, созданного с истекшим сроком действия, произойдет сбой выделения ресурсов ретрансляции мультимедиа, а все текущие аудио-и видеосеансы завершатся сбоем.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-131">Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail.</span></span> <span data-ttu-id="2d1fd-132">Клиенту потребуется получить новый маркер, созданный действительным сертификатом, чтобы возобновить нормальную работу звука и видео.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-132">The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="2d1fd-133">Проверка подлинности между сервером и сервером осуществляется с помощью глобального сертификата, который запрашивается и применяется ко всем серверам в развертывании.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="2d1fd-134">Сертификат отвечает за проверку подлинности серверов в Lync Server 2013, а также проверку подлинности в Exchange 2013 и Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="2d1fd-135">Дополнительные сведения о том, как работает проверка подлинности сервера, можно найти [в разделе Управление приложениями для проверки подлинности серверов (OAuth) и партнеров в Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span><span class="sxs-lookup"><span data-stu-id="2d1fd-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="2d1fd-136">Одной из важных различий между процессом проверки подлинности звука и видео и процессом проверки подлинности сервера является жизненный цикл проверки подлинности или маркеров.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="2d1fd-137">Для проверки подлинности звука и видео срок действия истекает через 8 часов.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="2d1fd-138">Проверка подлинности между сервером имеет продолжительность не более 24 часов.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="2d1fd-139">Для каждого типа сертификатов необходимо планировать соответствующие планы.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="2d1fd-140">Новинка для Lync Server 2013 — это возможность размещения замещающего сертификата для проверки подлинности звука и видео, а также сертификата проверки подлинности сервера в течение срока действия текущего сертификата.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="2d1fd-141">Затем новый сертификат используется для создания новых маркеров или запросов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="2d1fd-142">но сохраняет старый сертификат для проверки текущих сеансов и проверки подлинности...</span><span class="sxs-lookup"><span data-stu-id="2d1fd-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="2d1fd-143">Что это может сделать, чтобы избежать практически всех сбоев из-за истечения срока действия маркера и сертификата.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="2d1fd-144">Подробные сведения об этой функции и о том, как ее настроить, можно найти в разделе промежуточная версия [сертификата AV и OAuth в Lync Server 2013 с помощью Set-ксцертификате](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="2d1fd-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="2d1fd-145">Сокращенная зависимость от схожести на основе файлов cookie</span><span class="sxs-lookup"><span data-stu-id="2d1fd-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="2d1fd-146">В предыдущих версиях Lync Server и Office Communications Server веб-службы использовали схожесть на основе файлов cookie, чтобы убедиться в том, что состояние сеанса клиента и веб-служб поддерживалось.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="2d1fd-147">Веб-службы Lync Server 2013 используют встроенный механизм сходства, который устраняет большинство требований для сходства на основе файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2d1fd-148">В мобильном клиенте Microsoft Lync 2010 по-прежнему необходимо использовать сходство на основе файлов cookie и требовать настройки сходства на основе файлов cookie, пока вы не перейдете все клиенты в предстоящие клиенты Microsoft Lync Mobile (Дата выпуска еще не определена).</span><span class="sxs-lookup"><span data-stu-id="2d1fd-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="2d1fd-149">Сведения о сходстве на основе файлов cookie в Lync Server 2013 можно найти в разделе [компоненты, необходимые для доступа внешних пользователей в Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2d1fd-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="2d1fd-150">Усовершенствования автообнаружения</span><span class="sxs-lookup"><span data-stu-id="2d1fd-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="2d1fd-151">Функция автообнаружения в Lync Server 2013 позволяет клиентам находить дополнительные возможности, доступные для общения.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="2d1fd-152">В накопительном обновлении для Lync Server 2010: Ноябрь 2011 для мобильных устройств и Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="2d1fd-153">Функция автообнаружения (также называемая именами DNS-записей LyncDiscover и Линкдисковеринтернал) позволяет клиентам находить и использовать службы Mobility Service (для мобильных клиентов Microsoft Lync 2010), Microsoft Lync Web App и веб-планировщика Lync, а также связь с сервером Microsoft Exchange Server и сервером SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="2d1fd-154">Автообнаружения устанавливаются как обычные части настройки и развертывания инфраструктуры и серверов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="2d1fd-155">Построитель топологии и мастер развертывания Lync Server устраняют большинство задач настройки, которые требовались в накопительном обновлении для Lync Server 2010: Ноябрь 2011.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="2d1fd-156">Услуги для мобильных клиентов</span><span class="sxs-lookup"><span data-stu-id="2d1fd-156">Services for Mobile Clients</span></span>

<span data-ttu-id="2d1fd-157">Представлено в накопительном обновлении для Lync Server 2010: Ноябрь 2011, Услуги мобильной связи в Lync Server 2013. Включите мобильные телефоны, на которых работают мобильные и планшетные устройства с Lync, Android, Windows Phone или Nokia на мобильных устройствах для выполнения такие действия, как отправка и получение мгновенных сообщений, просмотр контактов и Просмотр сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="2d1fd-158">Кроме того, мобильные устройства поддерживают некоторые корпоративные функции голосовой связи, например, для присоединения к Конференции, звонков по каналам связи с одним числом, а также голосовую почту и уведомление о пропущенных звонках.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d1fd-159">В службах Mobility Service используются обратные прокси-серверы и опубликованные службы, развернутые на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="2d1fd-160">Пограничные серверы не требуют изменений.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="2d1fd-161">Как минимум требуется исходящий SIP/TCP/5061from сервер, на котором работает служба Edge Access (Lync Server).</span><span class="sxs-lookup"><span data-stu-id="2d1fd-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="2d1fd-162">Роль режиссера необязательна</span><span class="sxs-lookup"><span data-stu-id="2d1fd-162">Director Role is Optional</span></span>

<span data-ttu-id="2d1fd-163">Роль директора сервера в топологии Lync Server 2013 не изменилась.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="2d1fd-164">Он по-прежнему содержит веб-службы, выполняет предварительную проверку подлинности входящих запросов пользователя и направляет внешних пользователей в свой личный пул.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="2d1fd-165">Изменив директорию от рекомендованной роли до дополнительной роли, корпорация Майкрософт не сможет уменьшить значение режиссера.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="2d1fd-166">Цель — сократить количество серверов и другие требования к оборудованию (например, подсистемы балансировки нагрузки для режиссера), не нарушая функциональность и функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="2d1fd-167">Так как сервер переднего плана может выполнять те же задачи, что и режиссер, но не влияет на предоставленные услуги, вы можете развернуть режиссеров, если вы выберете.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="2d1fd-168">Вы можете безопасно исключить режиссера, чтобы серверный интерфейс предоставил вам те же услуги, что и для режиссера.</span><span class="sxs-lookup"><span data-stu-id="2d1fd-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

