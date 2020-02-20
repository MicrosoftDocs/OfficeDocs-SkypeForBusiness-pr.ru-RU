---
title: 'Lync Server 2013: определение требований к серверам переднего плана, обмену мгновенными сообщениями и присутствию'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 703ca1ab069101a7266c779aa21ff3f587b93f92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="ff1a5-102">Определение требований для серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff1a5-102">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff1a5-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="ff1a5-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="ff1a5-104">Основная задача при планировании системы обмена мгновенными сообщениями и сведений о присутствии состоит в обеспечении достаточного количества серверов переднего плана для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-104">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="ff1a5-105">Обеспечение взаимодействия с внешними пользователями</span><span class="sxs-lookup"><span data-stu-id="ff1a5-105">Enabling Communication with External Users</span></span>

<span data-ttu-id="ff1a5-106">Вы можете значительно увеличить преимущества инвестиций в Lync Server, разрешая пользователям связываться с внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-106">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="ff1a5-107">К внешним пользователям относятся:</span><span class="sxs-lookup"><span data-stu-id="ff1a5-107">External users can include:</span></span>

  - <span data-ttu-id="ff1a5-108">**Удаленные пользователи**   вашей организации, когда они работают за преработкой сетевых брандмауэров и используют их ноутбуки или другие устройства Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-108">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="ff1a5-109">**Пользователи федеративных пользователей**   из компаний, которые также работают с пользователями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-109">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="ff1a5-110">Чтобы ваши пользователи могли легко общаться с такими пользователями, с этими компаниями создаются отношения федерации.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-110">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="ff1a5-111">**Общедоступные пользователи**   общедоступных служб обмена мгновенными сообщениями, такие как службы обмена мгновенными сообщениями,\!предоставляемые сетью Windows Live, Yahoo и AOL, а также пользователей поставщиков и серверов, использующих протоколы XMPP, такие как Google говорите.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-111">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff1a5-112">Обратите внимание, что для организации связи с общедоступными службами Windows Live, AOL и Yahoo! может потребоваться отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-112">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="ff1a5-113">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="ff1a5-114">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ff1a5-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="ff1a5-115">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="ff1a5-116">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ff1a5-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="ff1a5-117">объявлено.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-117">has been announced.</span></span> <span data-ttu-id="ff1a5-118">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="ff1a5-119">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ff1a5-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="ff1a5-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-120">Messenger.</span></span> <span data-ttu-id="ff1a5-121">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="ff1a5-122">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="ff1a5-123">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="ff1a5-124">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="ff1a5-125">Чтобы включить все или все эти сценарии, необходимо развернуть пограничный сервер, чтобы обеспечить безопасное взаимодействие между развертыванием Lync Server и внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-125">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="ff1a5-126">Удаленные пользователи вашей организации и пользователи в федеративных организациях смогут видеть сведения о присутствии друг друга и общаться с помощью мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-126">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="ff1a5-127">Для получения дополнительных сведений о том, как обеспечить взаимодействие с внешними пользователями, ознакомьтесь со статьей [Планирование доступа внешних пользователей в Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-127">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="ff1a5-128">Архивирование мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="ff1a5-128">Archiving IM Content</span></span>

<span data-ttu-id="ff1a5-129">Lync Server предоставляет функции, которые можно использовать, если ваша организация должна следовать нормативным требованиям.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-129">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="ff1a5-130">С помощью архивации можно архивировать контент мгновенных сообщений для всех пользователей в организации или только для некоторых указанных пользователей.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-130">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="ff1a5-131">Дополнительные сведения приведены в статье [Планирование архивации в Lync Server 2013](lync-server-2013-planning-for-archiving.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-131">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="ff1a5-132">Если вы также развернули Microsoft Exchange Server 2013, вы можете интегрировать архивирование данных Exchange с архивированием данных Lync Server и использовать одно средство для поиска обоих типов архивных данных.</span><span class="sxs-lookup"><span data-stu-id="ff1a5-132">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="ff1a5-133">Дополнительные сведения см. [в статье Настройка Microsoft Lync server 2013 для использования архивации Microsoft Exchange server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="ff1a5-133">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

