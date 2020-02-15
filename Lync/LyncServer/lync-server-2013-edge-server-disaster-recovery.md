---
title: 'Lync Server 2013: аварийное восстановление пограничного сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cd85a769d021aae6873a50a719a6043ef72f770
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="d4070-102">Аварийное восстановление пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4070-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4070-103">_**Последнее изменение темы:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="d4070-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="d4070-p101">Как и в случае других ролей, лучший способ обеспечить высокую доступность используемых пограничных серверов — развернуть на каждой площадке несколько пограничных серверов. При отказе одного пограничного сервера остальные серверы пула продолжат предоставлять соответствующие службы.</span><span class="sxs-lookup"><span data-stu-id="d4070-p101">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site. If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="d4070-p102">Чтобы сделать возможными процедуры аварийного восстановления, необходимо развернуть на отдельных площадках независимые пулы пограничных серверов. В отличие от пулов переднего плана, явное связывание пулов пограничных серверов не требуется — использование нескольких пулов пограничных серверов само по себе обеспечивает возможность продолжения работы в случае отказа одного пула пограничных серверов. В следующих разделах подробно описывается аварийное восстановления для различных функций пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="d4070-p102">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites. You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down. The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="d4070-109">Удаленный доступ</span><span class="sxs-lookup"><span data-stu-id="d4070-109">Remote Access</span></span>

<span data-ttu-id="d4070-110">Если у вас есть несколько сайтов, каждый из которых имеет пул пограничных серверов, и один весь пограничный пул завершается с ошибкой, службы удаленного доступа продолжат работать без вмешательства администратора.</span><span class="sxs-lookup"><span data-stu-id="d4070-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="d4070-111">При создании пулов пограничных серверов на разных сайтах нельзя использовать одно полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="d4070-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="d4070-112">Каждый пограничный пул должен иметь уникальные полные доменные имена (внутренние и внешние).</span><span class="sxs-lookup"><span data-stu-id="d4070-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="d4070-113">Пограничные пулы не используют правила публикации обратного прокси-сервера для общения с серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="d4070-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="d4070-114">Автоматическая отработка отказа происходит, когда клиент повторно запрашивает записи службы DNS удаленного доступа, а удаленные пользователи перенаправляются на пограничные серверы на другом сайте.</span><span class="sxs-lookup"><span data-stu-id="d4070-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="d4070-115">Клиент пытается попытаться все внешнее полное доменное имя сервера в соответствии с приоритетом записей SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="d4070-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4070-116">Чтобы отработка отказа работала без проблем, убедитесь, что брандмауэр разрешает внешним серверам всех пулов взаимодействовать со всеми пограничными серверами.</span><span class="sxs-lookup"><span data-stu-id="d4070-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="d4070-117">Федерация</span><span class="sxs-lookup"><span data-stu-id="d4070-117">Federation</span></span>

<span data-ttu-id="d4070-118">Для связей Федерации с другими организациями, работающими под управлением Lync Server, входящие запросы Федерации продолжат работать при наличии таких решений, как Geo-DNS ВЫХОДУ.</span><span class="sxs-lookup"><span data-stu-id="d4070-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="d4070-119">Важно понимать, что отработка отказа Федерации не обеспечивает отработку отказа с приоритетом в записях SRV.</span><span class="sxs-lookup"><span data-stu-id="d4070-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="d4070-120">Приведенное выше решение поможет обеспечить возможности аварийного восстановления для входящей Федерации.</span><span class="sxs-lookup"><span data-stu-id="d4070-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="d4070-121">Внешняя федерация всегда настраивается с помощью одного опубликованного пограничного сервера или пула пограничных серверов в организации.</span><span class="sxs-lookup"><span data-stu-id="d4070-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="d4070-122">В случае отказа этого пула пограничных серверов необходимо использовать построитель топологий, чтобы изменить маршрут внешней федерации так, чтобы использовать все еще работающий пул пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="d4070-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="d4070-123">Дополнительные сведения см. [при отработки отказа пограничного пула, используемого для Федерации Lync Server в Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="d4070-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="d4070-124">Федерация XMPP</span><span class="sxs-lookup"><span data-stu-id="d4070-124">XMPP Federation</span></span>

<span data-ttu-id="d4070-125">В случае федерации XMPP при отказе пула пограничных серверов, назначенного в качестве шлюза федерации XMPP, происходит сбой доставки как исходящего, так и входящего трафика.</span><span class="sxs-lookup"><span data-stu-id="d4070-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="d4070-126">Для восстановления работы федерации XMPP необходимо переключить федерацию XMPP на использование другого пула пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="d4070-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="d4070-127">Подробнее: [отработка отказа пограничного пула, используемого для Федерации XMPP в Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="d4070-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="d4070-128">Отказ пула пограничных серверов при сохранении работоспособности пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="d4070-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="d4070-129">Если на площадке происходит отказ пула пограничных серверов, но пул переднего плана серверов продолжает работать, понадобится переключить пул переднего плана на использование другого пула пограничных серверов на время неработоспособности первого пула.</span><span class="sxs-lookup"><span data-stu-id="d4070-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="d4070-130">Дополнительную информацию можно узнать [в статье изменение пограничного пула, связанного с пулом переднего плана в Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d4070-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

