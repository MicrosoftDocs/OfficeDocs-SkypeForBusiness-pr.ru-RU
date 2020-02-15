---
title: Планирование SIP, Федерации XMPP и общедоступных мгновенных сообщений
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2070d9e977a730b7c667a2c49a7e896d1309eef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="54fa2-102">Планирование SIP, Федерации XMPP и общедоступных мгновенных сообщений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54fa2-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54fa2-103">_**Последнее изменение темы:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="54fa2-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="54fa2-104">Пограничные серверы можно настроить так, чтобы разрешить внутренним и внешним пользователям получать доступ к контактам в партнерских организациях или службах.</span><span class="sxs-lookup"><span data-stu-id="54fa2-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="54fa2-105">Федерации — так называются эти партнерские соглашения — могут предоставить любые из перечисленных ниже возможностей контактам в вашей организации по федерации партнера или контакты в федерации партнера вашим контактам:</span><span class="sxs-lookup"><span data-stu-id="54fa2-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="54fa2-106">Обмен мгновенными сообщениями и сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="54fa2-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="54fa2-107">Совместная работа и конференц-связь, например веб-конференции</span><span class="sxs-lookup"><span data-stu-id="54fa2-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="54fa2-108">Аудиоконференции и/или видеоконференции</span><span class="sxs-lookup"><span data-stu-id="54fa2-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="54fa2-109">В некоторых случаях обмен данными, например обмен мгновенными сообщениями и сведения о присутствии между Microsoft Lync Server 2013 и контактом XMPP (Extensible Messaging and Presence Protocol), является одноранговой только для вас и контакта в Федерации. партнерство.</span><span class="sxs-lookup"><span data-stu-id="54fa2-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="54fa2-110">В других случаях, таких как Lync Server, Lync Server 2010 to Lync Server 2013 Федерация, можно пригласить нескольких участников в беседу.</span><span class="sxs-lookup"><span data-stu-id="54fa2-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="54fa2-111">Федерация Lync Server и Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="54fa2-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="54fa2-112">Федерация между Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server поддерживает одноранговые и многосторонние подключения.</span><span class="sxs-lookup"><span data-stu-id="54fa2-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="54fa2-113">Одноранговые беседы можно преобразовать в беседы с несколькими участниками, создавая импровизированные собрания по сети.</span><span class="sxs-lookup"><span data-stu-id="54fa2-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="54fa2-114">Собрания — это веб-конференции или аудио- и видеоконференции, которые можно планировать для включения в них контактов, находящихся как в вашей организации, так и в организациях партнеров, с которыми настроена федерация.</span><span class="sxs-lookup"><span data-stu-id="54fa2-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="54fa2-115">Федерация впервые появилась в Microsoft Office Live Communications Server 2005 и поддерживала один вид Федерации, прямая Федерация.</span><span class="sxs-lookup"><span data-stu-id="54fa2-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="54fa2-116">Непосредственная Федерация требовалось знать домен SIP и полное доменное имя (FQDN) пограничного сервера партнера (SIP).</span><span class="sxs-lookup"><span data-stu-id="54fa2-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="54fa2-117">Live Communications Server 2005 с пакетом обновления 1 (SP1) предоставила дополнительные типы Федерации, все необходимые записи SRV DNS, которые должны быть опубликованы федеративным партнером для обнаружения их пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="54fa2-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="54fa2-118">Терминология для этого выпуска:</span><span class="sxs-lookup"><span data-stu-id="54fa2-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="54fa2-119">*Откройте расширенную Федерацию*: примите любое имя домена SIP и используйте DNS SRV, чтобы определить расположение пограничного сервера партнера</span><span class="sxs-lookup"><span data-stu-id="54fa2-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="54fa2-120">*Расширенная Федерация*: Настройте имя домена SIP партнера в качестве партнера Федерации для вашей организации и используйте DNS SRV для поиска пограничного сервера партнера</span><span class="sxs-lookup"><span data-stu-id="54fa2-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="54fa2-121">*Прямая Федерация*: Настройте имя домена SIP и полное доменное имя партнера на пограничный сервер партнера.</span><span class="sxs-lookup"><span data-stu-id="54fa2-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="54fa2-122">*Список разрешенных серверов*: Примите любой домен, используйте DNS SRV, чтобы найти пограничный сервер поставщика услуг хостинга или поставщика услуг подключения к общедоступному мгновенным сообщениям (IM).</span><span class="sxs-lookup"><span data-stu-id="54fa2-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="54fa2-123">Microsoft Office Communications Server 2007 представил обновленное именование для типов Федерации, чтобы лучше определить, что именно делает каждый тип Федерации:</span><span class="sxs-lookup"><span data-stu-id="54fa2-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="54fa2-124">Открытая Расширенная Федерация стала известна как *обнаруженный домен партнера*</span><span class="sxs-lookup"><span data-stu-id="54fa2-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="54fa2-125">Расширенная Федерация стала известна как *разрешенный домен партнера*</span><span class="sxs-lookup"><span data-stu-id="54fa2-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="54fa2-126">Прямая Федерация стала известна как *разрешенный сервер-партнер*</span><span class="sxs-lookup"><span data-stu-id="54fa2-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="54fa2-127">Список разрешенных серверов стал известен как *поставщик услуг хостинга* и *общедоступный поставщик обмена мгновенными сообщениями*</span><span class="sxs-lookup"><span data-stu-id="54fa2-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="54fa2-128">Microsoft Lync Server 2010 предоставила более узкое определение поставщика услуг размещения в соответствии с Microsoft Lync Online 2010 и Microsoft Office 365, а также применяет к тому же списку разрешенных, который определяется разрешенным типом Федерации доменных партнеров.</span><span class="sxs-lookup"><span data-stu-id="54fa2-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="54fa2-129">Включение федерации между Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server использует пограничные серверы и обратные прокси-серверы для применения правил и разрешенных доменов-партнеров, которые вы определяете.</span><span class="sxs-lookup"><span data-stu-id="54fa2-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="54fa2-130">С точки зрения планирования, Федерации с другим сервером Lync Server, Office Communications Server необходимы следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="54fa2-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="54fa2-131">Включите Федерацию в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="54fa2-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="54fa2-132">Дополнительные сведения см. в разделе Deployment [: Настройка Федерации SIP, Федерации XMPP и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="54fa2-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="54fa2-133">Определите требования для обнаружения федеративного домена.</span><span class="sxs-lookup"><span data-stu-id="54fa2-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="54fa2-134">Для ручной настройки федерации необходимо иметь полное доменное имя (FQDN) пограничного сервера и доменного имени партнера или доменное имя домена, которое вводится в панели управления Lync Server, **Федерации и внешнего доступа**, **федеративных доменов SIP**.</span><span class="sxs-lookup"><span data-stu-id="54fa2-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="54fa2-135">Создайте **новую** политику или **измените** существующую, чтобы разрешить или заблокировать домены по полному доменному имени.</span><span class="sxs-lookup"><span data-stu-id="54fa2-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="54fa2-136">Ручная настройка пограничного сервера партнера Федерации может привести к сбою в случае, если партнер изменит IP-адрес пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="54fa2-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="54fa2-137">Для <STRONG>новых федеративных доменов SIP</STRONG>необходимо указать <STRONG>доменное имя (или полное доменное имя)</STRONG> для Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="54fa2-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="54fa2-138">Для Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server также необходимо предоставить <STRONG>службу пограничного доступа (полное доменное имя)</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="54fa2-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="54fa2-139">Для обнаруженной Федерации Федерации, где партнеры могут обнаруживать пограничный сервер, вы создаете запись SRV во внешней службе DNS \_-сипфедератионтлс. \_TCP.contoso.com —, который указывает на порт 5061 и запись узла (A) пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="54fa2-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="54fa2-140">Если вы поддерживаете клиентов Microsoft Lync Mobile на Windows Phone или Apple iPhone, iPad или других устройствах Apple, и используете службу push-уведомлений или службу push-уведомлений, необходимо запланировать _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="54fa2-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="54fa2-141">&lt;Записи SRV&gt; для доменов SIP для каждого домена SIP, в котором у вас есть клиенты Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="54fa2-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="54fa2-142">Android и Nokia Symbian Lync Mobile не используют push-уведомления и не подчиняются этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="54fa2-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="54fa2-143">Настройка политик доступа внешних пользователей для поддержки федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="54fa2-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="54fa2-144">Откройте порты брандмауэра для протокола SIP, веб-конференций и аудио-и видеосвязи, чтобы обеспечить поддержку Федерации или контактов.</span><span class="sxs-lookup"><span data-stu-id="54fa2-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="54fa2-145">Дополнительные сведения: [Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="54fa2-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="54fa2-146">Приведенные ниже сведения помогут вам определить требования к сертификатам, портам, протоколам и DNS для Федерации с Microsoft Lync Server 2013 и Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="54fa2-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="54fa2-147">Планирование сертификатов, брандмауэров, требований к портам и протоколам и требованиям DNS обычно является прямым пересылкой, если вы планируете или развернули пограничные серверы Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54fa2-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="54fa2-148">Так как Федерация является дополнительным компонентом, использующим существующий пограничный сервер, требования к планированию обычно выполняются при планировании и развертывании пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="54fa2-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="54fa2-149">Используйте приведенные ниже таблицы, чтобы определить, выполнены ли требования, и внесите изменения в порт/протокол и DNS соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="54fa2-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="54fa2-150">Если у вас есть пул пограничных серверов, которые включаются в Федерацию с участниками Lync Server 2013 или Lync Server 2010, вы можете использовать балансировку нагрузки на DNS или аппаратные подсистемы балансировки нагрузки на внутренних и внешних сторонах пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="54fa2-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="54fa2-151">Если вы представляете Федерацию с Office Communications Server 2007 или Office Communications Server 2007 R2, аппаратная балансировка нагрузки обеспечит поддержку отработки отказа в случае пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="54fa2-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="54fa2-152">Office Communications Server 2007 и Office Communications Server 2007 R2 не поддерживают балансировку нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="54fa2-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="54fa2-153">Пограничные серверы партнеров будут устанавливать связь с первым пограничным сервером в пуле, который отвечает.</span><span class="sxs-lookup"><span data-stu-id="54fa2-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="54fa2-154">Если этот пограничный сервер завершается с ошибкой, соединение не отменяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="54fa2-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="54fa2-155">Требования к сертификатам обычно выполняются при планировании сертификатов для выбранного пограничного сервера или плана пограничного сервера пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="54fa2-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="54fa2-156">Общедоступная служба обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="54fa2-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="54fa2-157">Общедоступная служба обмена мгновенными сообщениями — это класс Федерации, который позволяет внутренним и внешним пользователям Lync Server 2013 добавлять контакты из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="54fa2-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="54fa2-158">Контакты Messenger</span><span class="sxs-lookup"><span data-stu-id="54fa2-158">Messenger contacts</span></span>

  - <span data-ttu-id="54fa2-159">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="54fa2-159">Yahoo\!</span></span> <span data-ttu-id="54fa2-160">contacts</span><span class="sxs-lookup"><span data-stu-id="54fa2-160">contacts</span></span>

  - <span data-ttu-id="54fa2-161">Контакты America Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="54fa2-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="54fa2-162">С 1 сентября 2012 г. Лицензия на подписку общедоступных служб обмена мгновенными сообщениями Microsoft Lync (PIC усл) больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="54fa2-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="54fa2-163">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="54fa2-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="54fa2-164">Messenger до даты завершения работы службы (Точная дата все еще не может быть определена, но не раньше июня 2013).</span><span class="sxs-lookup"><span data-stu-id="54fa2-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="54fa2-165">УСЛ PIC — это лицензия на помесячную подписку на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с Yahoo!</span><span class="sxs-lookup"><span data-stu-id="54fa2-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="54fa2-166">Messenger.</span><span class="sxs-lookup"><span data-stu-id="54fa2-166">Messenger.</span></span> <span data-ttu-id="54fa2-167">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого обновление не выполняется.</span><span class="sxs-lookup"><span data-stu-id="54fa2-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="54fa2-168">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="54fa2-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="54fa2-169">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="54fa2-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="54fa2-170">В этот список будет добавлена Федерация Skype, которая позволяет пользователям Lync достигать сотни миллионов людей с помощью обмена мгновенными сообщениями и голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="54fa2-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="54fa2-171">При планировании для этого класса федерации необходимо учитывать следующее:</span><span class="sxs-lookup"><span data-stu-id="54fa2-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="54fa2-172">В дополнение к обмену мгновенными сообщениями пользователи Windows Live Messenger могут иметь возможность однорангового аудио-и визуального взаимодействия с пользователями Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54fa2-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="54fa2-173">Пограничные серверы должны отвечать определенным требованиям к портам и протоколам.</span><span class="sxs-lookup"><span data-stu-id="54fa2-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="54fa2-174">Подробнее: [Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54fa2-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="54fa2-175">Для обмена мгновенными сообщениями Yahoo не предъявляются уникальные требования, кроме тех, которые обычно используются при планировании и развертывании типичного пограничного сервера, обеспечивающего Федерацию.</span><span class="sxs-lookup"><span data-stu-id="54fa2-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="54fa2-176">Для работы в Америке Online необходимо, чтобы сертификат пограничного сервера, назначенный пограничной службе доступа, использовал расширенное использование ключа (EKU) клиента.</span><span class="sxs-lookup"><span data-stu-id="54fa2-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="54fa2-177">Федерация Extensible Messaging and Presence Protocol (XMPP)</span><span class="sxs-lookup"><span data-stu-id="54fa2-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="54fa2-178">Предыдущие версии Lync Server и Office Communications Server предоставили шлюз XMPP (Extensible Messaging and Presence Protocol), который может быть развернут как отдельная роль сервера, чтобы разрешить федерацию с развертываниями XMPP.</span><span class="sxs-lookup"><span data-stu-id="54fa2-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="54fa2-179">В Microsoft Lync Server 2013 функция XMPP может быть развернута в качестве компонента.</span><span class="sxs-lookup"><span data-stu-id="54fa2-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="54fa2-180">Функции XMPP устанавливаются в двух частях: прокси-сервер XMPP, выполняющийся на пограничном сервере, и шлюз XMPP, работающий на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="54fa2-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="54fa2-181">Развертывание и Настройка XMPP рассматривается в разделе [развертывание доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) вы планируете поддерживать XMPP в Организации, определяя правила портов и протоколов в брандмауэре, настройку сертификатов и добавление записей DNS.</span><span class="sxs-lookup"><span data-stu-id="54fa2-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="54fa2-182">В следующих подразделах этого раздела приводится сводка сведений, необходимых для успешного планирования Федерации XMPP для развертывания.</span><span class="sxs-lookup"><span data-stu-id="54fa2-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="54fa2-183">Функция XMPP Lync Server 2013 тестируется и поддерживается корпорацией Майкрософт для федерации обмена мгновенными сообщениями с Google говорите.</span><span class="sxs-lookup"><span data-stu-id="54fa2-183">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="54fa2-184">Для любой другой системы XMPP обратитесь к сторонним поставщикам, чтобы убедиться, что они поддерживают Федерацию с Lync Server 2013, а также рекомендации по развертыванию и устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="54fa2-184">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="54fa2-185">Федерация XMPP не поддерживается для пользователей, которые размещены на устройствах для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="54fa2-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="54fa2-186">Это относится как к просмотру сведений о присутствии, так и при обмене МГНОВЕНными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="54fa2-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="54fa2-187">В следующих разделах содержатся указания по определению сертификатов, портов брандмауэра и записей DNS для типов поддерживаемых сценариев Федерации.</span><span class="sxs-lookup"><span data-stu-id="54fa2-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="54fa2-188">Сводка по сертификатам: SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54fa2-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="54fa2-189">Сводка по портам: SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54fa2-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="54fa2-190">Сводка по DNS — SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54fa2-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54fa2-191">См. также</span><span class="sxs-lookup"><span data-stu-id="54fa2-191">See Also</span></span>


[<span data-ttu-id="54fa2-192">Настройка политик для управления доступом федеративных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54fa2-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="54fa2-193">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54fa2-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="54fa2-194">Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54fa2-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="54fa2-195">Определение требований к DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54fa2-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="54fa2-196">Управление конфигурацией пограничного сервера доступа для Организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54fa2-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="54fa2-197">Управление федеративными доменами SIP для Организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54fa2-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="54fa2-198">Управление федеративными поставщиками SIP для Организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54fa2-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

