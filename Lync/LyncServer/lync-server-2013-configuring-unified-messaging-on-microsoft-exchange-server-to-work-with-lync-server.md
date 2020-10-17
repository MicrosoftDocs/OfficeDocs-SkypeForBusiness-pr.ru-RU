---
title: 'Lync Server 2013: Настройка единой системы обмена сообщениями на сервере Microsoft Exchange Server для работы с Lync Server'
description: 'Lync Server 2013: Настройка единой системы обмена сообщениями на сервере Microsoft Exchange для работы с Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53c303f0ae659536aafcbdfcd829ed236e35a0ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548245"
---
# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="7f180-103">Настройка единой системы обмена сообщениями на сервере Microsoft Exchange Server для работы с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f180-103">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f180-104">_**Последнее изменение темы:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="7f180-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7f180-105">Если вы хотите использовать единую систему обмена сообщениями Exchange для предоставления автоответчика, голосового доступа к Outlook или служб автосекретаря для пользователей корпоративной голосовой связи, ознакомьтесь с разделом <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Планирование интеграции единой системы обмена сообщениями Exchange в Lync Server 2013</A> в документации по планированию, а затем следуйте инструкциям, приведенным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7f180-105">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="7f180-106">Чтобы настроить единую систему обмена сообщениями Exchange для работы с корпоративной голосовой связью, необходимо выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="7f180-106">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="7f180-107">Настройка сертификатов на сервере, на котором запущены службы единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="7f180-107">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f180-108">Добавить все серверы клиентского доступа и почтовых ящиков во все абонентские группы URI для SIP единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7f180-108">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="7f180-109">В противном случае маршрутизация исходящих вызовов не сможет работать ожидаемым образом.</span><span class="sxs-lookup"><span data-stu-id="7f180-109">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="7f180-110">Создайте одну или несколько абонентских групп URI SIP с единой системой обмена сообщениями, а также номера телефонов абонентского доступа, если необходимо, а затем создайте соответствующие абонентские группы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7f180-110">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="7f180-111">С помощью сценария **exchucutil.ps1**:</span><span class="sxs-lookup"><span data-stu-id="7f180-111">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="7f180-112">создать IP-шлюзы единой системы обмена сообщениями;</span><span class="sxs-lookup"><span data-stu-id="7f180-112">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="7f180-113">создать сервисные группы единой системы обмена сообщениями;</span><span class="sxs-lookup"><span data-stu-id="7f180-113">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="7f180-114">Предоставьте Lync Server 2013 разрешение на чтение объектов доменных служб Active Directory единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7f180-114">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="7f180-115">создать объект автосекретаря единой системы обмена сообщениями;</span><span class="sxs-lookup"><span data-stu-id="7f180-115">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="7f180-116">создать объект абонентского доступа;</span><span class="sxs-lookup"><span data-stu-id="7f180-116">Create a subscriber access object.</span></span>

  - <span data-ttu-id="7f180-117">создать URI для SIP для каждого пользователя и связать пользователей с абонентской группой SIP единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7f180-117">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="7f180-118">Требования и рекомендации</span><span class="sxs-lookup"><span data-stu-id="7f180-118">Requirements and Recommendations</span></span>

<span data-ttu-id="7f180-119">Прежде чем приступать к работе, в документации в этом разделе предполагается, что вы развернули следующие роли Exchange 2013: клиентский доступ и почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="7f180-119">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="7f180-120">В Microsoft Exchange Server 2013 служба единой системы обмена сообщениями Exchange работает как служба на этих серверах.</span><span class="sxs-lookup"><span data-stu-id="7f180-120">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="7f180-121">Подробнее о развертывании Exchange 2013 можно узнать в библиотеке Exchange 2013 TechNet по адресу [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="7f180-121">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="7f180-122">Также обратите внимание на следующее.</span><span class="sxs-lookup"><span data-stu-id="7f180-122">Also note the following:</span></span>

  - <span data-ttu-id="7f180-123">Если единая система обмена сообщениями установлена в нескольких лесах, для каждого леса единой системы обмена сообщениями необходимо выполнить интеграцию с Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="7f180-123">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="7f180-124">Кроме того, каждый лес единой системы обмена сообщениями должен быть настроен для доверия лесу, в котором развернут Lync Server 2013, и лес, в котором развернут Lync Server 2013, должен быть настроен для доверия каждого леса единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7f180-124">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="7f180-125">Этапы интеграции выполняются как в ролях сервера Exchange, где выполняются службы единой системы обмена сообщениями, так и на сервере, на котором работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f180-125">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="7f180-126">Перед выполнением интеграции Lync Server 2013 необходимо выполнить действия по интеграции единой системы обмена сообщениями Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="7f180-126">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f180-127">Чтобы узнать, какие действия по интеграции выполняются на серверах и ролях администраторов, ознакомьтесь со статьей <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7f180-127">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="7f180-128">На каждом сервере, на котором запущена служба единой системы обмена сообщениями Exchange, должны быть доступны следующие средства:</span><span class="sxs-lookup"><span data-stu-id="7f180-128">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="7f180-129">командная консоль Exchange;</span><span class="sxs-lookup"><span data-stu-id="7f180-129">Exchange Management Shell</span></span>

  - <span data-ttu-id="7f180-130">сценарий **exchucutil.ps1**, выполняющий следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="7f180-130">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="7f180-131">Создает шлюз IP единой системы обмена сообщениями для каждого сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f180-131">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="7f180-132">Создает сервисную группу для каждого шлюза.</span><span class="sxs-lookup"><span data-stu-id="7f180-132">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="7f180-133">Пилотный идентификатор каждой сервисной группы указывает абонентскую группу универсального кода ресурса (URI) SIP единой системы обмена сообщениями, которую использует интерфейсный пул или сервер Standard Edition, связанный с шлюзом.</span><span class="sxs-lookup"><span data-stu-id="7f180-133">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="7f180-134">Предоставляет Lync Server 2013 разрешение на чтение объектов единой системы обмена сообщениями Exchange в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7f180-134">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f180-135">Содержание</span><span class="sxs-lookup"><span data-stu-id="7f180-135">In This Section</span></span>

  - [<span data-ttu-id="7f180-136">Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7f180-136">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="7f180-137">Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f180-137">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

