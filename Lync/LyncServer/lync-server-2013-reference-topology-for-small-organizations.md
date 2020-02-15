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
ms.openlocfilehash: 1f4c9d99e95dea0edd0b5990b0bb198dfe59dc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="5fb00-102">Эталонная топология для Lync Server 2013 в небольших организациях</span><span class="sxs-lookup"><span data-stu-id="5fb00-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fb00-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="5fb00-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="5fb00-104">Эталонная топология для малых организаций показывает, как можно развернуть надежное высокодоступное решение, развернув только три сервера, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fb00-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="5fb00-105">**Эталонная топология для небольших организаций**</span><span class="sxs-lookup"><span data-stu-id="5fb00-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="5fb00-106">![Эталонная топология, на которой разворачивается схема 3 серверов](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Эталонная топология, на которой разворачивается схема 3 серверов")</span><span class="sxs-lookup"><span data-stu-id="5fb00-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="5fb00-107">**Комбинация серверов Standard Edition, развернутых**     в этой Организации, на центральном сайте 4 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="5fb00-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="5fb00-108">Для обеспечения высокой доступности и аварийного восстановления Организация развернула два сервера Standard Edition и объединяет их вместе.</span><span class="sxs-lookup"><span data-stu-id="5fb00-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="5fb00-109">Каждый сервер 2 000 пользователей, но информация обо всех пользователях синхронизируется между двумя серверами.</span><span class="sxs-lookup"><span data-stu-id="5fb00-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="5fb00-110">В случае отказа одного сервера администратор может переключить соответствующих пользователей на обслуживание другим сервером, с минимальным влиянием на работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="5fb00-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="5fb00-111">Дополнительные сведения о функциях обеспечения высокого уровня доступности и аварийного восстановления в Lync Server 2013 приведены [в статье Планирование обеспечения высокой доступности и аварийного восстановления в Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="5fb00-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="5fb00-112">**Рекомендуется развертывание пограничного сервера.**    Несмотря на то, что развертывание пограничного сервера не является обязательным для внутреннего обмена мгновенными сообщениями, присутствия и конференций, рекомендуется использовать его даже для небольших развертываний.</span><span class="sxs-lookup"><span data-stu-id="5fb00-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="5fb00-113">Вы можете максимально увеличить инвестиции в Lync Server, развернув пограничный сервер, чтобы обеспечить обслуживание пользователей, находящихся за преработкой брандмауэров вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5fb00-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="5fb00-114">Ниже перечислены связанные с этим преимущества.</span><span class="sxs-lookup"><span data-stu-id="5fb00-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="5fb00-115">Пользователи вашей организации могут использовать функции Lync Server, если они работают дома или в дороге.</span><span class="sxs-lookup"><span data-stu-id="5fb00-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="5fb00-116">Ваши пользователи смогут приглашать внешних пользователей для участия в собраниях.</span><span class="sxs-lookup"><span data-stu-id="5fb00-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="5fb00-117">Если у вас есть партнер, поставщик или клиентская организация, которые также используют Lync Server, вы можете сформировать *федеративное отношение* с этой организацией.</span><span class="sxs-lookup"><span data-stu-id="5fb00-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="5fb00-118">Затем ваше развертывание Lync Server распознает пользователей из этой федеративной организации, что повышает эффективность совместной работы.</span><span class="sxs-lookup"><span data-stu-id="5fb00-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="5fb00-119">Пользователи могут обмениваться мгновенными сообщениями с пользователями общедоступных служб обмена мгновенными сообщениями, включая любые или все из следующих:\!Windows Live, AOL, Yahoo и Google говорите.</span><span class="sxs-lookup"><span data-stu-id="5fb00-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="5fb00-120">Для общедоступных служб обмена мгновенными сообщениями в этих службах может потребоваться отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="5fb00-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="5fb00-121">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="5fb00-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="5fb00-122">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5fb00-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="5fb00-123">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="5fb00-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="5fb00-124">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5fb00-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="5fb00-125">объявлено.</span><span class="sxs-lookup"><span data-stu-id="5fb00-125">has been announced.</span></span> <span data-ttu-id="5fb00-126">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5fb00-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="5fb00-127">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5fb00-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="5fb00-128">Messenger.</span><span class="sxs-lookup"><span data-stu-id="5fb00-128">Messenger.</span></span> <span data-ttu-id="5fb00-129">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="5fb00-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="5fb00-130">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="5fb00-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="5fb00-131">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="5fb00-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="5fb00-132">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="5fb00-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="5fb00-133">**Бесперебойность работы сайта филиала.**    В этой организации выполняется Пилотная программа корпоративной голосовой связи в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fb00-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="5fb00-134">Некоторые пользователи используют Lync Server в качестве единственного голосового решения.</span><span class="sxs-lookup"><span data-stu-id="5fb00-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="5fb00-135">Некоторые из этих пользователей пилотной версии находятся в филиале.</span><span class="sxs-lookup"><span data-stu-id="5fb00-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="5fb00-136">Сайт филиала не имеет надежной связи глобальной сети с центральным сайтом, поэтому в ней разворачивается устройство для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="5fb00-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="5fb00-137">При сбое связи с глобальной сетью пользователи филиала смогут принимать и осуществлять вызовы (звонки в организации и по ТСОП), использовать функции голосовой почты и общаться с помощью двухсторонних мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="5fb00-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="5fb00-138">В случае нарушения связи с глобальной сетью также будет доступна проверка подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="5fb00-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="5fb00-139">**Развертывание Exchange UM.**</span><span class="sxs-lookup"><span data-stu-id="5fb00-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="5fb00-140">Эта эталонная топология включает сервер единой системы обмена сообщениями Exchange (единой системы обмена сообщениями Exchange), на котором работает Microsoft Exchange Server, а не Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fb00-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="5fb00-141">Подробные сведения о единой системе обмена сообщениями Exchange приведены [в статье Планирование интеграции единой системы обмена сообщениями Exchange в Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) и [Интеграция единой системы обмена сообщениями Exchange в Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="5fb00-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="5fb00-142">**Сервер Office Web Apps.**</span><span class="sxs-lookup"><span data-stu-id="5fb00-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="5fb00-143">Рекомендуется развернуть сервер Office Web Apps Server или ферму серверов Office Web Apps Server в каждой организации, использующей веб-конференции.</span><span class="sxs-lookup"><span data-stu-id="5fb00-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="5fb00-144">Сервер Office Web Apps Server позволяет показывать слайды PowerPoint в веб-конференциях.</span><span class="sxs-lookup"><span data-stu-id="5fb00-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="5fb00-145">Дополнительную информацию можно узнать в статье [Настройка интеграции с сервером Office Web Apps и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="5fb00-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

