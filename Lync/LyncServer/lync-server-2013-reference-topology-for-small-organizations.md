---
title: Эталонная топология Lync Server 2013 для малых организаций
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="135f1-102">Топология ссылок для Lync Server 2013 в небольших организациях</span><span class="sxs-lookup"><span data-stu-id="135f1-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="135f1-103">_**Тема последнего изменения:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="135f1-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="135f1-104">Топология ссылок в малых организациях показывает, как развернуть надежное решение с высокой степенью доступности, развертывая только три сервера с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="135f1-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="135f1-105">**Эталонная топология для небольших организаций**</span><span class="sxs-lookup"><span data-stu-id="135f1-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="135f1-106">![Схема эталонной топологии с развертыванием трех серверов](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Схема эталонной топологии с развертыванием трех серверов")</span><span class="sxs-lookup"><span data-stu-id="135f1-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="135f1-107">**Для пары серверов стандартных выпусков, развернутых**     в этой Организации, у вас 4 000 пользователей на своем центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="135f1-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="135f1-108">Для обеспечения высокого уровня доступности и аварийного восстановления Организация развернула два сервера стандартных выпусков Standard и пару их вместе.</span><span class="sxs-lookup"><span data-stu-id="135f1-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="135f1-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span><span class="sxs-lookup"><span data-stu-id="135f1-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="135f1-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span><span class="sxs-lookup"><span data-stu-id="135f1-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="135f1-111">Дополнительные сведения о возможностях высокой доступности и аварийного восстановления в Lync Server 2013 можно найти [в разделе Планирование обеспечения высокой доступности и аварийного восстановления в Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="135f1-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="135f1-112">**Рекомендуется развертывание пограничного сервера.**    Несмотря на то, что развертывание пограничного сервера не требуется для внутренних мгновенных сообщений, присутствия и конференций, рекомендуется даже для небольших развертываний.</span><span class="sxs-lookup"><span data-stu-id="135f1-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="135f1-113">Вы можете максимально увеличить инвестиции на Lync Server, развертывая пограничный сервер, чтобы обеспечить обслуживание пользователей, находящихся за пределами брандмауэров вашей организации.</span><span class="sxs-lookup"><span data-stu-id="135f1-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="135f1-114">Вам будут доступны следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="135f1-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="135f1-115">Пользователи вашей организации могут использовать возможности Lync Server, если они работают дома или находятся в пути.</span><span class="sxs-lookup"><span data-stu-id="135f1-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="135f1-116">Ваши пользователи смогут приглашать внешних пользователей для участия в собраниях.</span><span class="sxs-lookup"><span data-stu-id="135f1-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="135f1-117">Если у вас есть партнер, поставщик или организация клиента, который также использует Lync Server, вы можете сформировать *федеративное отношение* с этой организацией.</span><span class="sxs-lookup"><span data-stu-id="135f1-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="135f1-118">После этого развертывание Lync Server сможет распознать пользователей из этой федеративной организации, что лучше для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="135f1-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="135f1-119">Пользователи могут обмениваться мгновенными сообщениями с пользователями общедоступных служб обмена мгновенными сообщениями, в том числе любые или все из\!указанных ниже вариантов: Windows Live, AOL, Yahoo и Google.</span><span class="sxs-lookup"><span data-stu-id="135f1-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="135f1-120">Для общедоступной службы обмена мгновенными сообщениями с этими службами может потребоваться отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="135f1-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="135f1-121">По состоянию на 1 сентября 2012, лицензия на подписку на общедоступные службы обмена мгновенными сообщениями в Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="135f1-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="135f1-122">Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="135f1-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="135f1-123">Messenger, пока служба не отключается.</span><span class="sxs-lookup"><span data-stu-id="135f1-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="135f1-124">Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня.</span><span class="sxs-lookup"><span data-stu-id="135f1-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="135f1-125">было объявлено.</span><span class="sxs-lookup"><span data-stu-id="135f1-125">has been announced.</span></span> <span data-ttu-id="135f1-126">Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="135f1-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="135f1-127">УСЛ PIC является лицензией на ежемесячную подписку для пользователей Lync Server или Office Communications Server, которая требуется для Федерации с помощью Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="135f1-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="135f1-128">Messenger.</span><span class="sxs-lookup"><span data-stu-id="135f1-128">Messenger.</span></span> <span data-ttu-id="135f1-129">Возможность предоставления этой услуги корпорацией Майкрософт зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="135f1-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="135f1-130">В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру.</span><span class="sxs-lookup"><span data-stu-id="135f1-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="135f1-131">Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств за пределами стандартной клиентской лицензии Lync.</span><span class="sxs-lookup"><span data-stu-id="135f1-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="135f1-132">В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут общаться с сотнями миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="135f1-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="135f1-133">**Бесперебойность сайтов филиалов.**    В этой организации запущен пилотный проект функции "Корпоративная голосовая связь" на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="135f1-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="135f1-134">Некоторые пользователи используют Lync Server в качестве единственного голосового решения.</span><span class="sxs-lookup"><span data-stu-id="135f1-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="135f1-135">Некоторые из этих пользователей пилотного проекта находятся на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="135f1-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="135f1-136">Сайт филиала не имеет надежной ссылки на глобальную сеть (WAN) на центральный сайт, поэтому там будет развернуто работающее устройство для филиалов.</span><span class="sxs-lookup"><span data-stu-id="135f1-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="135f1-137">При сбое связи по глобальной сети эта система позволяет пользователям на сайте филиала принимать и посылать вызовы (внутри организации и по ТСОП), пользоваться возможностями голосовой почты и обмениваться двусторонними мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="135f1-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="135f1-138">Кроме того, при нарушении связи по глобальной сети возможна проверка подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="135f1-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="135f1-139">**Развертывание единой системы обмена сообщениями Exchange.**</span><span class="sxs-lookup"><span data-stu-id="135f1-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="135f1-140">Эта топология ссылок включает сервер единой системы обмена сообщениями Exchange (UM), на котором запущен Microsoft Exchange Server, а не Lync Server.</span><span class="sxs-lookup"><span data-stu-id="135f1-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="135f1-141">Подробнее об обмене мгновенными сообщениями в Exchange можно узнать в разделе [Планирование интеграции единой системы обмена сообщениями Exchange в Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) и [интеграции единой системы обмена сообщениями Exchange в среде Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="135f1-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="135f1-142">**Сервер Office Web Apps.**</span><span class="sxs-lookup"><span data-stu-id="135f1-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="135f1-143">В каждой организации, где проводятся веб-конференции, рекомендуется развернуть сервер Office Web Apps или ферму таких серверов.</span><span class="sxs-lookup"><span data-stu-id="135f1-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="135f1-144">Сервер Office Web Apps обеспечивает возможность представления слайдов PowerPoint на веб-конференциях.</span><span class="sxs-lookup"><span data-stu-id="135f1-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="135f1-145">Дополнительные сведения можно найти [в разделе Настройка интеграции с Office Web Apps Server и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="135f1-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

