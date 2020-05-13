---
title: Планирование Федерации Lync Server и Office Communications Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dad03a196b6909d2657b7dbc8463653bb004a310
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="af88f-102">Планирование интеграции Lync Server 2013 и Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="af88f-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af88f-103">_**Последнее изменение темы:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="af88f-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="af88f-104">Федерация между Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server поддерживает одноранговые и многосторонние подключения.</span><span class="sxs-lookup"><span data-stu-id="af88f-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="af88f-105">Одноранговые беседы можно преобразовать в беседы с несколькими участниками, создавая импровизированные собрания по сети.</span><span class="sxs-lookup"><span data-stu-id="af88f-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="af88f-106">Собрания — это веб-конференции или аудио- и видеоконференции, которые можно планировать для включения в них контактов, находящихся как в вашей организации, так и в организациях партнеров, с которыми настроена федерация.</span><span class="sxs-lookup"><span data-stu-id="af88f-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="af88f-107">Федерация впервые появилась в Microsoft Office Live Communications Server 2005 и поддерживала один вид Федерации, прямая Федерация.</span><span class="sxs-lookup"><span data-stu-id="af88f-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="af88f-108">Непосредственная Федерация требовалось знать домен SIP и полное доменное имя (FQDN) пограничного сервера партнера (SIP).</span><span class="sxs-lookup"><span data-stu-id="af88f-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="af88f-109">Live Communications Server 2005 с пакетом обновления 1 (SP1) предоставила дополнительные типы Федерации, все необходимые записи SRV DNS, которые должны быть опубликованы федеративным партнером для обнаружения их пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="af88f-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="af88f-110">Терминология для этого выпуска:</span><span class="sxs-lookup"><span data-stu-id="af88f-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="af88f-111">*Откройте расширенную Федерацию*: примите любое имя домена SIP и используйте DNS SRV, чтобы определить расположение пограничного сервера партнера</span><span class="sxs-lookup"><span data-stu-id="af88f-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="af88f-112">*Расширенная Федерация*: Настройте имя домена SIP партнера в качестве партнера Федерации для вашей организации и используйте DNS SRV для поиска пограничного сервера партнера</span><span class="sxs-lookup"><span data-stu-id="af88f-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="af88f-113">*Прямая Федерация*: Настройте имя домена SIP и полное доменное имя партнера на пограничный сервер партнера.</span><span class="sxs-lookup"><span data-stu-id="af88f-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="af88f-114">*Список разрешенных серверов*: Примите любой домен, используйте DNS SRV, чтобы найти пограничный сервер поставщика услуг хостинга или поставщика услуг подключения к общедоступному мгновенным сообщениям (IM).</span><span class="sxs-lookup"><span data-stu-id="af88f-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="af88f-115">Microsoft Office Communications Server 2007 представил обновленное именование для типов Федерации, чтобы лучше определить, что именно делает каждый тип Федерации:</span><span class="sxs-lookup"><span data-stu-id="af88f-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="af88f-116">Открытая Расширенная Федерация стала известна как *обнаруженный домен партнера*</span><span class="sxs-lookup"><span data-stu-id="af88f-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="af88f-117">Расширенная Федерация стала известна как *разрешенный домен партнера*</span><span class="sxs-lookup"><span data-stu-id="af88f-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="af88f-118">Прямая Федерация стала известна как *разрешенный сервер-партнер*</span><span class="sxs-lookup"><span data-stu-id="af88f-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="af88f-119">Список разрешенных серверов стал известен как *поставщик услуг хостинга* и *общедоступный поставщик обмена мгновенными сообщениями*</span><span class="sxs-lookup"><span data-stu-id="af88f-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="af88f-120">Microsoft Lync Server 2010 предоставила более узкое определение поставщика услуг размещения в соответствии с Microsoft Lync Online 2010 и Microsoft Office 365, а также применяет к тому же списку разрешенных, который определяется разрешенным типом Федерации доменных партнеров.</span><span class="sxs-lookup"><span data-stu-id="af88f-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="af88f-121">Включение федерации между Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server использует пограничные серверы и обратные прокси-серверы для применения правил и разрешенных доменов-партнеров, которые вы определяете.</span><span class="sxs-lookup"><span data-stu-id="af88f-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="af88f-122">С точки зрения планирования, Федерации с другим сервером Lync Server, Office Communications Server необходимы следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="af88f-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="af88f-123">Включите Федерацию в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="af88f-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="af88f-124">Дополнительные сведения см. в разделе Deployment [: Настройка Федерации SIP, Федерации XMPP и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="af88f-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="af88f-125">Определите требования для обнаружения федеративного домена.</span><span class="sxs-lookup"><span data-stu-id="af88f-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="af88f-126">Для ручной настройки федерации необходимо иметь полное доменное имя (FQDN) пограничного сервера и доменного имени партнера или доменное имя домена, которое вводится в панели управления Lync Server, **Федерации и внешнего доступа**, **федеративных доменов SIP**.</span><span class="sxs-lookup"><span data-stu-id="af88f-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="af88f-127">Создайте **новую** политику или **измените** существующую, чтобы разрешить или заблокировать домены по полному доменному имени.</span><span class="sxs-lookup"><span data-stu-id="af88f-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="af88f-128">Ручная настройка пограничного сервера партнера Федерации может привести к сбою в случае, если партнер изменит IP-адрес пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="af88f-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="af88f-129">Для <STRONG>новых федеративных доменов SIP</STRONG>необходимо указать <STRONG>доменное имя (или полное доменное имя)</STRONG> для Microsoft Lync Online и microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="af88f-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online and Microsoft 365 or Office 365.</span></span> <span data-ttu-id="af88f-130">Для Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server также необходимо предоставить <STRONG>службу пограничного доступа (полное доменное имя)</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="af88f-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="af88f-131">Для обнаруженной Федерации Федерации, где партнеры могут обнаруживать пограничный сервер, вы создаете запись SRV во внешней службе DNS- \_ сипфедератионтлс. \_ tcp.contoso.com —, который указывает на порт 5061 и запись узла (A) пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="af88f-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="af88f-132">Если вы поддерживаете клиентов Microsoft Lync Mobile на Windows Phone или Apple iPhone, iPad или других устройствах Apple, и используете службу push-уведомлений или службу push-уведомлений, необходимо запланировать _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="af88f-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="af88f-133">&lt;&gt;Записи SRV для доменов SIP для каждого домена SIP, в котором у вас есть клиенты Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="af88f-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="af88f-134">Android и Nokia Symbian Lync Mobile не используют push-уведомления и не подчиняются этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="af88f-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="af88f-135">Настройка политик доступа внешних пользователей для поддержки федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="af88f-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="af88f-136">Откройте порты брандмауэра для протокола SIP, веб-конференций и аудио-и видеосвязи, чтобы обеспечить поддержку Федерации или контактов.</span><span class="sxs-lookup"><span data-stu-id="af88f-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="af88f-137">Дополнительные сведения: [Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="af88f-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="af88f-138">Приведенные ниже сведения помогут вам определить требования к сертификатам, портам, протоколам и DNS для Федерации с Microsoft Lync Server 2013 и Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="af88f-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="af88f-139">Планирование сертификатов, брандмауэров, требований к портам и протоколам и требованиям DNS обычно является прямым пересылкой, если вы планируете или развернули пограничные серверы Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af88f-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="af88f-140">Так как Федерация является дополнительным компонентом, использующим существующий пограничный сервер, требования к планированию обычно выполняются при планировании и развертывании пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="af88f-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="af88f-141">Используйте приведенные ниже таблицы, чтобы определить, выполнены ли требования, и внесите изменения в порт/протокол и DNS соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="af88f-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="af88f-142">Если у вас есть пул пограничных серверов, которые включаются в Федерацию с участниками Lync Server 2013 или Lync Server 2010, вы можете использовать балансировку нагрузки на DNS или аппаратные подсистемы балансировки нагрузки на внутренних и внешних сторонах пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="af88f-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="af88f-143">Если вы представляете Федерацию с Office Communications Server 2007 или Office Communications Server 2007 R2, аппаратная балансировка нагрузки обеспечит поддержку отработки отказа в случае пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="af88f-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="af88f-144">Office Communications Server 2007 и Office Communications Server 2007 R2 не поддерживают балансировку нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="af88f-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="af88f-145">Пограничные серверы партнеров будут устанавливать связь с первым пограничным сервером в пуле, который отвечает.</span><span class="sxs-lookup"><span data-stu-id="af88f-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="af88f-146">Если этот пограничный сервер завершается с ошибкой, соединение не отменяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="af88f-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="af88f-147">Требования к сертификатам обычно выполняются при планировании сертификатов для выбранного пограничного сервера или плана пограничного сервера пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="af88f-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="af88f-148">Содержание</span><span class="sxs-lookup"><span data-stu-id="af88f-148">In This Section</span></span>

  - [<span data-ttu-id="af88f-149">Сводка по сертификатам: SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af88f-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="af88f-150">Сводка по портам: SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af88f-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="af88f-151">Сводка по DNS — SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af88f-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af88f-152">См. также</span><span class="sxs-lookup"><span data-stu-id="af88f-152">See Also</span></span>


[<span data-ttu-id="af88f-153">Настройка политик для управления доступом федеративных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af88f-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="af88f-154">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af88f-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="af88f-155">Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af88f-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="af88f-156">Определение требований к DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af88f-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="af88f-157">Управление конфигурацией пограничного сервера доступа для Организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af88f-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="af88f-158">Управление федеративными доменами SIP для Организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af88f-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="af88f-159">Управление федеративными поставщиками SIP для Организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af88f-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

