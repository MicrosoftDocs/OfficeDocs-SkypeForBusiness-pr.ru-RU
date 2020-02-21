---
title: 'Lync Server 2013: новые функции для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 526daf4359cec022b71476dc4abaa67c52e8409a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="a09b9-102">Новые функции для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a09b9-102">New features for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a09b9-103">_**Последнее изменение темы:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="a09b9-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="a09b9-104">Lync Server 2013 содержит новые функции, расширяющие возможности и методы связи для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a09b9-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="a09b9-105">Кроме того, Lync Server 2013 вводит изменения в существующие службы для улучшения интеграции и расширения служб, доступных в Организации.</span><span class="sxs-lookup"><span data-stu-id="a09b9-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="a09b9-106">Ниже приведена сводка изменений, которые могут повлиять на планирование и развертывание служб пограничного сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a09b9-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="a09b9-107">**Поддержка IPv6-адресов**   Lync Server 2013 поддерживает IPv6-адресацию для всех служб пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="a09b9-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="a09b9-108">Если вы предоставили IPv6-адреса для интерфейсов с помощью конфигурации в Windows Server, вы можете использовать IPv6-адреса в конфигурации пограничного сервера через конфигурацию IP-адресов в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="a09b9-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a09b9-109">Использование IPv6-адресов в Lync Server 2013 зависит от поддержки IPv6 в маршрутизаторах и брандмауэрах, которые разворачиваются в Организации, а также в поддержке через поставщика услуг Интернета.</span><span class="sxs-lookup"><span data-stu-id="a09b9-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="a09b9-110">**XMPP (Extensible Messaging and Presence Protocol)**   , Lync Server 2013 содержит полностью интегрированный прокси-сервер XMPP (развернутый на пограничных серверах) и шлюз XMPP, развернутый на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a09b9-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="a09b9-111">Вы можете развернуть федерацию XMPP как дополнительный компонент.</span><span class="sxs-lookup"><span data-stu-id="a09b9-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="a09b9-112">Добавление и настройка прокси-сервера XMPP и шлюза XMPP позволит пользователям Microsoft Lync 2013 добавлять контакты из партнеров на основе XMPP для обмена мгновенными сообщениями и сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="a09b9-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a09b9-113">В настоящее время службы XMPP в Lync Server 2013 обеспечивают обмен мгновенными сообщениями и сведения о присутствии между клиентами Lync и контактами на XMPP.</span><span class="sxs-lookup"><span data-stu-id="a09b9-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="a09b9-114">**Службы Mobility Services для мобильных клиентов**   , добавленные в клиентском обновлении для Lync Server 2010, службы Mobility Services в Lync Server 2013 позволяют клиентам Microsoft Lync Mobile на мобильных телефонах и планшетных устройствах, использующих поддерживаемые мобильные устройства Apple iOS, Android, Windows Phone или Nokia, для выполнения таких действий, как отправка и получение мгновенных сообщений, просмотр контактов и Просмотр сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="a09b9-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="a09b9-115">Кроме того, мобильные устройства поддерживают некоторые функции корпоративной голосовой связи, такие как присоединение к собранию одним щелчком, "Позвонить с рабочего", звонок с одного номера, голосовая почта и уведомление о пропущенных вызовах.</span><span class="sxs-lookup"><span data-stu-id="a09b9-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a09b9-116">Службы Mobility Services используются обратный прокси-сервер и опубликованные службы, развернутые на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a09b9-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="a09b9-117">Вносить изменения в пограничные серверы не требуется.</span><span class="sxs-lookup"><span data-stu-id="a09b9-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="a09b9-118">**Директора — это необязательная роль**   . роль сервера Director в топологии Lync Server 2013 не изменилась.</span><span class="sxs-lookup"><span data-stu-id="a09b9-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="a09b9-119">Она все так же размещает веб-службы, выполняет предварительную проверку подлинности входящих пользовательских запросов и направляет внешних пользователей в домашний пул.</span><span class="sxs-lookup"><span data-stu-id="a09b9-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="a09b9-120">Изменение директора с помощью рекомендованной роли на необязательную роль не уменьшает значение директора, но подчеркивает количество серверов и другие требования к оборудованию (например, аппаратные подсистемы балансировки нагрузки для директоров) без Безопасность компонентов и функций.</span><span class="sxs-lookup"><span data-stu-id="a09b9-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="a09b9-121">Так как серверы переднего плана могут выполнять те же задачи, что и директор, не влияя на предоставляемые службы, при необходимости вы можете развернуть режиссеров.</span><span class="sxs-lookup"><span data-stu-id="a09b9-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="a09b9-122">Вы можете безопасно исключить директора, чтобы серверы переднего плана предоставляли одни и те же службы на своем месте.</span><span class="sxs-lookup"><span data-stu-id="a09b9-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a09b9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a09b9-123">See Also</span></span>


[<span data-ttu-id="a09b9-124">Планирование и настройка IPv6 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a09b9-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="a09b9-125">Планирование доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a09b9-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="a09b9-126">Планирование Федерации XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a09b9-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

