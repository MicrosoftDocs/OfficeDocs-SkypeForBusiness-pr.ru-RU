---
title: Lync Server 2013 — поддержка интеграции размещенной единой системы обмена сообщениями Exchange
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
ms.openlocfilehash: 3ebc49336712e96bca428132f3ccad631817208d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524176"
---
# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="76acd-102">Поддержка интеграции размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76acd-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76acd-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="76acd-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="76acd-104">Приложение Lync Server 2013 ExUM Routing поддерживает интеграцию с единой системой обмена сообщениями Exchange в локальной среде, где Lync Server 2013 и Exchange единой системы обмена сообщениями устанавливаются локально на предприятии, или с единой системой обмена сообщениями Exchange, размещенной у поставщика услуг, как показано на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="76acd-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="76acd-105">![Развертывание локальной единой системы обмена сообщениями Lync Server Exchange](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Развертывание локальной единой системы обмена сообщениями Lync Server Exchange")</span><span class="sxs-lookup"><span data-stu-id="76acd-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="76acd-106">Поддерживаются следующие режимы:</span><span class="sxs-lookup"><span data-stu-id="76acd-106">The following modes are supported:</span></span>

  - <span data-ttu-id="76acd-107">**Локальный режим**     Lync Server 2013 и служба единой системы обмена сообщениями Exchange развернуты на локальных серверах предприятия.</span><span class="sxs-lookup"><span data-stu-id="76acd-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="76acd-108">**Перекрестный режим**     Lync Server 2013 развернут на локальных серверах в Организации, а единая система обмена сообщениями Exchange размещается в средстве поставщика веб-служб, например в центре обработки данных Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="76acd-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="76acd-109">**Смешанный режим**     В развертывании Lync Server 2013 есть некоторые почтовые ящики пользователей, размещенные на локальных серверах Microsoft Exchange Server на предприятии, а некоторые почтовые ящики расположены в размещенном центре обработки данных службы Exchange.</span><span class="sxs-lookup"><span data-stu-id="76acd-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="76acd-110">Смешанный режим можно использовать в качестве переходного решения при оценке и поэтапной миграции пользователей в размещенную единую систему обмена сообщениями Exchange, а также в виде постоянного решения, если вы хотите, чтобы некоторые пользователи сохраняли локальные службы единой системы обмена сообщениями после миграции других пользователей.</span><span class="sxs-lookup"><span data-stu-id="76acd-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="76acd-111">Чтобы интегрировать Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange, необходимо настроить *Общее адресное пространство SIP* (также называемое *разделенным доменом*).</span><span class="sxs-lookup"><span data-stu-id="76acd-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="76acd-112">В этой конфигурации как Lync Server 2013, так и сторонний поставщик услуг единой системы обмена сообщениями Exchange могут получать доступ к тому же адресному пространству домена SIP.</span><span class="sxs-lookup"><span data-stu-id="76acd-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="76acd-113">Для получения дополнительных сведений ознакомьтесь с [разархитектурой Интеграция размещенной единой системы обмена сообщениями Exchange в Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="76acd-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

