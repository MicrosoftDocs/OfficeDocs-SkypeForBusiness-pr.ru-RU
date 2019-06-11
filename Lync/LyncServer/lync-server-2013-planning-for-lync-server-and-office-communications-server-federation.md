---
title: Планирование интеграции Lync Server и Office Communications Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c683092b61d278d380ad68cef86795d496498fbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="1ed84-102">Планирование для Lync Server 2013 и Office Communications Server Federation</span><span class="sxs-lookup"><span data-stu-id="1ed84-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ed84-103">_**Тема последнего изменения:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="1ed84-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="1ed84-104">Федерация между Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server поддерживает одноранговые и многосторонние коммуникации.</span><span class="sxs-lookup"><span data-stu-id="1ed84-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="1ed84-105">Одноранговые беседы могут быть переданы в беседы с несколькими участниками, что позволяет проводить нерегламентированные собрания.</span><span class="sxs-lookup"><span data-stu-id="1ed84-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="1ed84-106">Собрания: веб-конференции или звуковые и визуальные конференции — можно запланировать включение контактов внутри организации, а также контактов в партнерах, с которыми вы хотите выполнить федерацию.</span><span class="sxs-lookup"><span data-stu-id="1ed84-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="1ed84-107">Федерация впервые появилась в Microsoft Office Live Communications Server 2005 и поддерживала один и тот же вариант интеграции, прямая Федерация.</span><span class="sxs-lookup"><span data-stu-id="1ed84-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="1ed84-108">Прямая Федерация требует узнать домен SIP и полное доменное имя партнера (FQDN) для пограничного сервера участника.</span><span class="sxs-lookup"><span data-stu-id="1ed84-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="1ed84-109">Сервер Live Communications Server 2005 с пакетом обновления 1 (SP1) предлагает дополнительные типы Федерации, которые должны быть опубликованы федеративным партнером для поиска пограничного сервера в службе доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="1ed84-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="1ed84-110">Терминология для этого выпуска:</span><span class="sxs-lookup"><span data-stu-id="1ed84-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="1ed84-111">*Открыть улучшенную Федерацию*: Принимайте доменные имена SIP и используйте DNS SRV для поиска пограничного сервера партнера</span><span class="sxs-lookup"><span data-stu-id="1ed84-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="1ed84-112">*Улучшенная федерация*: Настройте имя домена SIP партнера как партнера Федерации для своей организации и используйте DNS SRV для поиска пограничного сервера партнера.</span><span class="sxs-lookup"><span data-stu-id="1ed84-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="1ed84-113">*Прямая Федерация*: Настройте имя домена SIP партнера и FQDN на пограничный сервер партнера.</span><span class="sxs-lookup"><span data-stu-id="1ed84-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="1ed84-114">*Список разрешенных серверов*: принимать любой домен, использовать DNS SRV для поиска пограничного сервера поставщика услуг размещения или общедоступного службы обмена мгновенными сообщениями (IM)</span><span class="sxs-lookup"><span data-stu-id="1ed84-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="1ed84-115">Microsoft Office Communications Server 2007 представил обновленные наименования для типов Федерации, чтобы лучше определить, что именно обеспечивается для каждого типа Федерации.</span><span class="sxs-lookup"><span data-stu-id="1ed84-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="1ed84-116">Открыть улучшенную Федерацию, которая стала известна как *обнаруженный домен партнера*</span><span class="sxs-lookup"><span data-stu-id="1ed84-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="1ed84-117">Улучшенная Федерация стала известна как *разрешенный домен партнера*</span><span class="sxs-lookup"><span data-stu-id="1ed84-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="1ed84-118">Прямая Федерация стала известна как *разрешенный сервер-партнер*</span><span class="sxs-lookup"><span data-stu-id="1ed84-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="1ed84-119">Список разрешенных серверов стал известным поставщиком *услуг размещения* и общедоступным *поставщиком мгновенных сообщений*</span><span class="sxs-lookup"><span data-stu-id="1ed84-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="1ed84-120">Microsoft Lync Server 2010 предлагает более узкое определение поставщика услуг размещения в соответствии с Microsoft Lync Online 2010 и Microsoft Office 365, а также сделал его допустимым списком разрешенных доменных доменов разрешенных партнеров.</span><span class="sxs-lookup"><span data-stu-id="1ed84-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="1ed84-121">При включении Федерации между Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server для обеспечения правил и разрешенных доменных доменов используются пограничные серверы и обратные прокси-серверы.</span><span class="sxs-lookup"><span data-stu-id="1ed84-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="1ed84-122">С точки зрения планирования, в которой вы планируете использовать другие серверы Lync Server, для Office Communications Server требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="1ed84-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="1ed84-123">Включите Федерацию в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="1ed84-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="1ed84-124">Подробные сведения можно найти в разделе Развертывание [: Настройка Федерации SIP, КСМПП Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="1ed84-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="1ed84-125">Определите требования для обнаружения федеративного домена.</span><span class="sxs-lookup"><span data-stu-id="1ed84-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="1ed84-126">Для ручной настройки федерации необходимо иметь полное доменное имя (FQDN) сервера граничного и доменного имени партнера или доменного имени, которое вводится на панели управления Lync Server, **Федерации и внешнего доступа**, **SIP Федеративные домены**.</span><span class="sxs-lookup"><span data-stu-id="1ed84-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="1ed84-127">Создание **новой** политики или **изменение** существующей политики для разрешения или блокировки доменов по полному доменному имени.</span><span class="sxs-lookup"><span data-stu-id="1ed84-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="1ed84-128">Ручная настройка пограничного сервера партнера Федерации может привести к сбою в событии, которое партнер изменяет IP-адрес пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="1ed84-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="1ed84-129">Для <STRONG>новых федеративных доменов SIP</STRONG>необходимо указать <STRONG>доменное имя (или FQDN)</STRONG> для Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ed84-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="1ed84-130">Для Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server также необходимо предоставить <STRONG>службу пограничного доступа (FQDN)</STRONG></span><span class="sxs-lookup"><span data-stu-id="1ed84-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="1ed84-131">Для обнаруженной Федерации партнеров, где партнеры могут найти пограничный сервер, вы создаете запись SRV в внешней службе DNS \_-сипфедератионтлс. \_TCP.contoso.com – это указывает на порт 5061 и запись узла (A) пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="1ed84-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="1ed84-132">Если вы используете клиент Microsoft Lync Mobile на Windows Phone или Apple iPhone, iPad и других устройствах Apple, а также используете службу push-уведомлений или службу push-уведомлений, вы должны спланировать использование _сипфедератионтлс. _tcp.</span><span class="sxs-lookup"><span data-stu-id="1ed84-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="1ed84-133">&lt;SRV-&gt; записи домена SIP для каждого домена SIP, на котором установлены мобильные клиенты Lync.</span><span class="sxs-lookup"><span data-stu-id="1ed84-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="1ed84-134">Для Android и Nokia Symbian Lync Mobile не следует использовать push-уведомления и не подвергаться этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="1ed84-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="1ed84-135">Настройка политик доступа внешних пользователей для поддержки федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="1ed84-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="1ed84-136">Откройте порты брандмауэра для протокола запуска сеансов (SIP), веб-конференций, аудио-и видеосвязи, чтобы включить в нее Федерацию или контакты.</span><span class="sxs-lookup"><span data-stu-id="1ed84-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="1ed84-137">Подробности можно найти в статье [Определение внешних параметров брандмауэра/V и портов для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="1ed84-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="1ed84-138">Ниже приведены сведения, которые помогут вам определить требования к сертификатам, портам и протоколам и DNS для Федерации с Microsoft Lync Server 2013 и Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1ed84-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="1ed84-139">Планирование сертификатов, брандмауэров и требований к портам и протоколам и требованиям DNS обычно является прямым перенаправленным процессом, если вы планируете или развернули сервер Microsoft Lync Server 2013 Edge.</span><span class="sxs-lookup"><span data-stu-id="1ed84-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="1ed84-140">Поскольку Федерация — это дополнительная функция, использующая существующий пограничный сервер, требования к планированию обычно выполняются планированием и развертыванием пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="1ed84-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="1ed84-141">Для определения соответствия требованиям и внесения изменений в порт/протокол и DNS следует использовать приведенные ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="1ed84-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1ed84-142">Если у вас есть пул пограничных серверов и вы используете сервер Lync Server 2013 или Lync Server 2010, вы можете использовать либо балансировку нагрузки DNS, либо подсистему балансировки нагрузки для оборудования на внутренних и внешних сторонах пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="1ed84-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="1ed84-143">Если вы предоставляете Федерацию с Office Communications Server 2007 или Office Communications Server 2007 R2, аппаратная балансировка нагрузки обеспечивает поддержку перехода на другой ресурс в случае пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="1ed84-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="1ed84-144">Office Communications Server 2007 и Office Communications Server 2007 R2 не поддерживают балансировку нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="1ed84-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="1ed84-145">Пограничные серверы партнеров будут устанавливать связь с первым пограничным сервером в пуле, который отвечает.</span><span class="sxs-lookup"><span data-stu-id="1ed84-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="1ed84-146">Если пограничный сервер завершается сбоем, Обмен данными не выполняется автоматически.</span><span class="sxs-lookup"><span data-stu-id="1ed84-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="1ed84-147">Требования к сертификатам обычно выполняются с помощью планирования сертификатов для выбранного пограничного сервера или плана пограничного сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="1ed84-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1ed84-148">Содержание</span><span class="sxs-lookup"><span data-stu-id="1ed84-148">In This Section</span></span>

  - [<span data-ttu-id="1ed84-149">Общие сведения о сертификате: SIP, Федерация КСМПП и общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed84-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="1ed84-150">Общие сведения о портах: SIP, Федерация КСМПП и общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed84-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="1ed84-151">Сводка DNS-SIP, Федерация КСМПП и общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed84-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ed84-152">См. также</span><span class="sxs-lookup"><span data-stu-id="1ed84-152">See Also</span></span>


[<span data-ttu-id="1ed84-153">Настройка политик управления доступом федеративных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed84-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="1ed84-154">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed84-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="1ed84-155">Определение требований к внешнему брандмауэру аудио- и видеосвязи и портам для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed84-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="1ed84-156">Определение требований DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed84-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="1ed84-157">Управление конфигурацией пограничного сервера в организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed84-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="1ed84-158">Управление федеративными доменами SIP для организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed84-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="1ed84-159">Управление федеративными поставщиками SIP в организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ed84-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

