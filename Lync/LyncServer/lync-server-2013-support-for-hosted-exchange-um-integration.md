---
title: 'Lync Server 2013: поддержка интеграции размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24139ad5294bf908a85b797300397fa8b2ac9140
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="e5738-102">Поддержка интеграции размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5738-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5738-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e5738-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e5738-104">Приложение Lync Server 2013 Ексум поддерживает интеграцию с единой системой обмена сообщениями Exchange (UM) в локальной среде, где Lync Server 2013 и Exchange UM установлены локально внутри организации, или в единой системе обмена сообщениями Exchange, размещенной на поставщик услуг, как показано на приведенной ниже схеме.</span><span class="sxs-lookup"><span data-stu-id="e5738-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="e5738-105">![Развертывание локальной системы обмена сообщениями на сервере Lync Server](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Развертывание локальной системы обмена сообщениями на сервере Lync Server")</span><span class="sxs-lookup"><span data-stu-id="e5738-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="e5738-106">Поддерживаются перечисленные ниже режимы.</span><span class="sxs-lookup"><span data-stu-id="e5738-106">The following modes are supported:</span></span>

  - <span data-ttu-id="e5738-107">**Локальный режим**   Lync Server 2013 и Exchange разворачиваются на локальных серверах в пределах организации.</span><span class="sxs-lookup"><span data-stu-id="e5738-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="e5738-108">**Одноранговый режим**   Lync Server 2013 развернут на локальных серверах в рамках предприятия, а UM-среде Exchange — в средстве поставщика Интернет-услуг, например в центре обработки данных Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e5738-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="e5738-109">**Смешанный режим**   сервер Lync Server 2013 имеет некоторые почтовые ящики пользователей, расположенные на локальных серверах Microsoft Exchange Server, а некоторые почтовые ящики расположены в центре обработки данных служб Exchange.</span><span class="sxs-lookup"><span data-stu-id="e5738-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5738-110">Смешанный режим можно использовать в качестве переходного решения во время оценки и степвисе миграции пользователей на размещенную систему обмена СООБЩЕНИЯми Exchange или как постоянное решение, если вы не хотите, чтобы некоторые пользователи работали в локальной среде обмена СООБЩЕНИЯми после миграции других пользователей.</span><span class="sxs-lookup"><span data-stu-id="e5738-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="e5738-111">Чтобы интегрировать Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange, необходимо настроить *Общее адресное пространство SIP* (также называемое *разделенным доменом*).</span><span class="sxs-lookup"><span data-stu-id="e5738-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="e5738-112">В этой конфигурации как в Lync Server 2013, так и в поставщике служб UM стороннего поставщика могут получить доступ к тому же адресному пространству домена SIP.</span><span class="sxs-lookup"><span data-stu-id="e5738-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="e5738-113">Подробности можно найти [в разделе Архитектура интеграции единой системы обмена сообщениями Exchange в Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e5738-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

