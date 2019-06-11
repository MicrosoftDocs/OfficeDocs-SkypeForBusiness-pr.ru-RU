---
title: 'Lync Server 2013: новые функции для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d365c4e32c5eaebbd0368cd85b41be7886a59df
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="b763f-102">Новые функции для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b763f-102">New features for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b763f-103">_**Тема последнего изменения:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="b763f-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="b763f-104">В Lync Server 2013 появились новые функции, расширяющие возможности и способы связи для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b763f-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="b763f-105">Кроме того, Lync Server 2013 предлагает изменения в существующих службах для лучшей интеграции и продления служб, доступных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b763f-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="b763f-106">Ниже приведена сводка изменений, которые могут повлиять на планирование и развертывание служб сервера Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="b763f-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="b763f-107">**Поддержка IPv6-адресов**   Lync Server 2013 поддерживает адресацию IPv6 для всех служб пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="b763f-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="b763f-108">Если вы указали IPv6-адреса для интерфейсов с помощью конфигурации в Windows Server, вы можете использовать IPv6-адреса в конфигурации пограничного сервера с помощью конфигурации IP Address Builder в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="b763f-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b763f-109">Использование IPv6-адресов в Lync Server 2013 зависит от поддержки IPv6 в маршрутизаторах и брандмауэрах, а также о поддержке через поставщика услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="b763f-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="b763f-110">**Расширенный протокол передачи сообщений и доступности (КСМПП)**   Lync Server 2013 представляет полностью интегрированный прокси-сервер КСМПП (развернутый на пограничном сервере) и шлюз КСМПП, развернутый на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b763f-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="b763f-111">Вы можете развернуть КСМПП Федерацию как дополнительный компонент.</span><span class="sxs-lookup"><span data-stu-id="b763f-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="b763f-112">Добавление и Настройка шлюза КСМПП proxy и КСМПП позволит пользователям Microsoft Lync 2013 добавлять контакты из партнеров на основе КСМПП для обмена мгновенными сообщениями и их присутствия.</span><span class="sxs-lookup"><span data-stu-id="b763f-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b763f-113">В настоящее время службы КСМПП в Lync Server 2013 предоставляют мгновенные сообщения и сведения о присутствии между клиентами Lync и контактами на КСМПП.</span><span class="sxs-lookup"><span data-stu-id="b763f-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="b763f-114">**Службы Mobility Service для мобильных клиентов**   , введенные в клиенте для Lync Server 2010, службы Mobility Service в Lync Server 2013 разрешают использование мобильных клиентов Microsoft Lync на мобильных телефонах и планшетных устройствах с поддержкой Apple iOS, Android, Windows Телефоны и мобильные устройства Nokia для выполнения таких операций, как отправка и получение мгновенных сообщений, просмотр контактов и Просмотр сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="b763f-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="b763f-115">Кроме того, мобильные устройства поддерживают некоторые корпоративные функции голосовой связи, например, для присоединения к Конференции, звонков по каналам связи с одним числом, а также голосовую почту и уведомление о пропущенных звонках.</span><span class="sxs-lookup"><span data-stu-id="b763f-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b763f-116">В службах Mobility Service используются обратные прокси-серверы и опубликованные службы, развернутые на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b763f-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="b763f-117">Пограничные серверы не требуют изменений.</span><span class="sxs-lookup"><span data-stu-id="b763f-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="b763f-118">**Режиссеры —**   это необязательная роль, которую роль сервера Director в топологии Lync Server 2013 не изменилась.</span><span class="sxs-lookup"><span data-stu-id="b763f-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="b763f-119">Он по-прежнему содержит веб-службы, предварительную проверку подлинности входящих запросов пользователя и направляет внешних пользователей в свой личный пул.</span><span class="sxs-lookup"><span data-stu-id="b763f-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="b763f-120">Изменение режиссера с помощью рекомендованной роли на дополнительную роль не снижает ценность режиссера, но уменьшает число серверов и другие требования к оборудованию (например, подсистема балансировки нагрузки для этого директора) без ослабление функциональных возможностей и функций.</span><span class="sxs-lookup"><span data-stu-id="b763f-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="b763f-121">Поскольку сервер переднего плана может выполнять те же задачи, что и режиссер, но не влияет на предоставленные услуги, вы можете при желании развернуть их.</span><span class="sxs-lookup"><span data-stu-id="b763f-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="b763f-122">Вы можете безопасно исключить режиссера, чтобы серверный интерфейс предоставил вам те же услуги на своем своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="b763f-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b763f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b763f-123">See Also</span></span>


[<span data-ttu-id="b763f-124">Планирование и настройка IPv6 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b763f-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="b763f-125">Планирование доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b763f-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="b763f-126">Планирование Федерации протоколов обмена сообщениями и присутствия в КСМПП в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b763f-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

