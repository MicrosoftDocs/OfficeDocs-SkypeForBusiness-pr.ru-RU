---
title: 'Lync Server 2013: компоненты и топологии для локальной единой системы обмена сообщениями'
description: 'Lync Server 2013: компоненты и топологии для локальной единой системы обмена сообщениями.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fe2ca16ec9fbd39e9245fd366e1f7046dd16d42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576825"
---
# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="ac6a4-103">Компоненты и топологии для локальной единой системы обмена сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac6a4-103">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac6a4-104">_**Последнее изменение темы:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="ac6a4-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="ac6a4-105">В этом разделе описываются компоненты Microsoft Exchange Server 2013, необходимые для обеспечения возможности единой системы обмена сообщениями Exchange в развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-105">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="ac6a4-106">Здесь также описываются поддерживаемые топологии для локальной интеграции единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-106">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="ac6a4-107">Компоненты Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ac6a4-107">Exchange Server Components</span></span>

<span data-ttu-id="ac6a4-108">Для предоставления функций и служб единой системы обмена сообщениями Exchange, описанных в статье [функции интегрированной единой системы обмена сообщениями и Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) , пользователям корпоративной голосовой связи в Организации необходимо развернуть сервер почтовых ящиков и сервер клиентского доступа Microsoft Exchange, на котором размещаются почтовые ящики пользователей, а также одно место хранения для электронной почты и голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-108">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="ac6a4-109">Единая система обмена сообщениями Exchange работает как служба на серверах почтовых ящиков Exchange и серверах клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-109">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="ac6a4-110">Дополнительные сведения о компонентах единой системы обмена сообщениями Exchange в Microsoft Exchange Server 2007 и Microsoft Exchange Server 2010 приведены в статье [развертывание локальной единой системы обмена сообщениями Exchange для предоставления пользователю Lync Server 2013 голосовой почты](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-110">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="ac6a4-111">Поддерживаемые топологии</span><span class="sxs-lookup"><span data-stu-id="ac6a4-111">Supported Topologies</span></span>

<span data-ttu-id="ac6a4-112">Вы можете развернуть Lync Server 2013 и единую систему обмена сообщениями Exchange (UM) в одном лесу или нескольких лесах.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-112">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="ac6a4-113">Если развертывание охватывает несколько лесов, необходимо выполнить действия по интеграции Exchange для каждого леса единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-113">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="ac6a4-114">Кроме того, необходимо настроить каждый лес Microsoft Exchange так, чтобы он доверял лесу Lync Server 2013 и лесу Lync Server 2013 доверять каждому лесу единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-114">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="ac6a4-115">В дополнение к этому доверию лесов параметры Exchange единой системы обмена сообщениями для всех пользователей должны быть установлены для объектов User в лесу Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-115">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="ac6a4-116">Lync Server 2013 поддерживает следующие топологии интеграции с единой системой обмена сообщениями Exchange:</span><span class="sxs-lookup"><span data-stu-id="ac6a4-116">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="ac6a4-117">один лес;</span><span class="sxs-lookup"><span data-stu-id="ac6a4-117">Single forest</span></span>

  - <span data-ttu-id="ac6a4-118">Один домен (то есть один лес с одним доменом).</span><span class="sxs-lookup"><span data-stu-id="ac6a4-118">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="ac6a4-119">Lync Server 2013, Microsoft Exchange и пользователи находятся в одном домене.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-119">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="ac6a4-120">Несколько доменов (корневой домен с одним или несколькими дочерними доменами).</span><span class="sxs-lookup"><span data-stu-id="ac6a4-120">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="ac6a4-121">Lync Server 2013 и Microsoft Exchange Server развернуты в разных доменах из домена, в котором создаются пользователи.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-121">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="ac6a4-122">Серверы единой системы обмена сообщениями Exchange можно развертывать в разных доменах из пула Lync Server 2013, который они поддерживают.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-122">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="ac6a4-123">Несколько лесов (то есть лес ресурсов).</span><span class="sxs-lookup"><span data-stu-id="ac6a4-123">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="ac6a4-124">Lync Server 2013 развернут в отдельном лесу, а затем пользователи распределены по нескольким лесам.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-124">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="ac6a4-125">Атрибуты единой системы обмена сообщениями пользователей Exchange необходимо реплицировать в лес Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-125">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac6a4-126">Exchange можно развертывать в нескольких лесах.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-126">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="ac6a4-127">Каждая организация Exchange может предоставлять пользователям единую систему обмена сообщениями Exchange, а единая система обмена сообщениями Exchange может быть развернута в том же лесу, что и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac6a4-127">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

