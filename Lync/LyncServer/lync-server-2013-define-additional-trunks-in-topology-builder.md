---
title: 'Lync Server 2013: определение дополнительных каналов в построителе топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b18d12762566258051d5fe0e7c71921b9fff160c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="e25c2-102">Определение дополнительных каналов в построителе топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e25c2-102">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e25c2-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="e25c2-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="e25c2-104">Выполните эти действия, чтобы определить дополнительный магистраль, с которым можно связать одноранговый сервер с \*\* сервером-посредником, с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="e25c2-104">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="e25c2-105">Одноранговая сеть обеспечивает пользователей, подключенных к корпоративной голосовой связи, с подключением к телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="e25c2-105">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="e25c2-106">Одноранговый узел может быть шлюзом ТСОП, узлом IP-УАТС или пограничным контроллером сеансов (SBC) для поставщика услуг интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="e25c2-106">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="e25c2-107">Магистраль определяет соединение между сервером и одноранговым компьютером.</span><span class="sxs-lookup"><span data-stu-id="e25c2-107">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="e25c2-108">Для каждого сервера — может быть определено несколько магистральных каналов.</span><span class="sxs-lookup"><span data-stu-id="e25c2-108">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="e25c2-109">Сервер-посредник может быть связан с несколькими одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="e25c2-109">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="e25c2-110">Магистраль — это логическая связь между сервером-посредником и шлюзом, уникальным образом идентифицированными кортежем.</span><span class="sxs-lookup"><span data-stu-id="e25c2-110">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="e25c2-111">Полное доменное имя сервера-посредника, прослушивающий порт сервера (TLS или TCP): IP Gateway и FQDN, порт прослушивания шлюза}</span><span class="sxs-lookup"><span data-stu-id="e25c2-111">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e25c2-112">В этой статье предполагается, что вы намерены настроить шлюз PSTN и корневой магистрали по крайней мере на одном размещенном или отдельном сервере или в отдельном пуле, как описано в статье <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">определение шлюза в построителе топологии в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e25c2-112">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e25c2-113">В этой статье предполагается, что вы установили по крайней мере один пул переднего плана или сервер Standard Edition по крайней мере с одного центрального сайта, как описано в статье <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Определение и Настройка внешнего пула и сервера Standard Edition в Lync server 2013</A> и <A href="lync-server-2013-publish-the-topology.md">Публикация топологии в Lync Сервер 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e25c2-113">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="e25c2-114">Определение дополнительной магистрали между сервером-посредником и одноранговым узлом шлюза</span><span class="sxs-lookup"><span data-stu-id="e25c2-114">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="e25c2-115">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e25c2-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e25c2-116">В разделе Lync Server 2013, имя сайта, **Общие компоненты**щелкните правой кнопкой мыши узел \*\*\*\* "магистральные" и выберите команду **создать новую магистраль**.</span><span class="sxs-lookup"><span data-stu-id="e25c2-116">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="e25c2-117">![Экран "структура файла" в построителе топологии Lync Server] (images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Экран \"структура файла\" в построителе топологии Lync Server")</span><span class="sxs-lookup"><span data-stu-id="e25c2-117">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="e25c2-118">В поле **Определение новой линии связи** введите информативное имя, однозначно определяющее магистраль.</span><span class="sxs-lookup"><span data-stu-id="e25c2-118">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="e25c2-119">Повторяющиеся имена магистралей не допускаются.</span><span class="sxs-lookup"><span data-stu-id="e25c2-119">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e25c2-120">Если в качестве типа транспорта указан протокол TLS, необходимо указать полное доменное имя, а не IP-адрес однорангового сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="e25c2-120">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="e25c2-121">В разделе **Связанный шлюз ТСОП** выберите одноранговый узел шлюза ТСОП для связывания с данной магистралью.</span><span class="sxs-lookup"><span data-stu-id="e25c2-121">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="e25c2-122">![Параметры свойств для однорангового шлюза PSTN для магистрали] (images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Параметры свойств для однорангового шлюза PSTN для магистрали")</span><span class="sxs-lookup"><span data-stu-id="e25c2-122">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="e25c2-123">В разделе **прослушивающий порт для шлюза PSTN**введите прослушивающий порт, который узел (шлюз PSTN, IP-УАТС или SBC) будет получать сообщения SIP от сервера-посредника, который должен быть связан с этой магистральной магистрали.</span><span class="sxs-lookup"><span data-stu-id="e25c2-123">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="e25c2-124">По умолчанию для протокола TCP применяется одноранговый порт 5066, а для протокола TLS – одноранговый порт 5067.</span><span class="sxs-lookup"><span data-stu-id="e25c2-124">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="e25c2-125">Значения по умолчанию для бесперебойно применяемых портов устройства ветвления — 5081 для TCP и 5082 для TLS.</span><span class="sxs-lookup"><span data-stu-id="e25c2-125">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="e25c2-126">В разделе **Транспортный протокол SIP** щелкните тип транспортного протокола, применяемый на одноранговом узле.</span><span class="sxs-lookup"><span data-stu-id="e25c2-126">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e25c2-127">По соображениям безопасности настоятельно рекомендуется развернуть одноранговый элемент на сервере-посреднике, который может использовать TLS.</span><span class="sxs-lookup"><span data-stu-id="e25c2-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="e25c2-128">В разделе сопоставленный **сервер исправлений**выберите пул серверов обисправлений, который нужно связать с корневой магистралью этого узла.</span><span class="sxs-lookup"><span data-stu-id="e25c2-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="e25c2-129">В разделе **связанный порт сервера исправлений**введите прослушивающий порт, который сервер обновлений будет получать сообщения SIP от однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="e25c2-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e25c2-130">Поддержка нескольких магистральных каналов в Lync Server 2013 с помощью одного и того же <STRONG>порта сервера</STRONG> -канала и <STRONG>прослушивающего порта для шлюза IP/КТСОП</STRONG> не может быть настроен для двух каналов связи с разными именами.</span><span class="sxs-lookup"><span data-stu-id="e25c2-130">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e25c2-131">Поддержка нескольких коммуникационных каналов в Lync Server 2013 позволяет определять несколько сигнальных портов SIP на сервере, где они будут работать.</span><span class="sxs-lookup"><span data-stu-id="e25c2-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="e25c2-132">При определении магистрали номер <STRONG>порта соответствующего сервера</STRONG> -посредника должен находиться в диапазоне портов прослушивания для соответствующего протокола, разрешенного сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="e25c2-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="e25c2-133">Этот диапазон портов определяется в пулах серверов Lync Server 2013 и исправлений.</span><span class="sxs-lookup"><span data-stu-id="e25c2-133">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="e25c2-134">Щелкните правой кнопкой мыши требуемый пул серверов исправлений и выберите пункт <STRONG>изменить свойства</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e25c2-134">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="e25c2-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span><span class="sxs-lookup"><span data-stu-id="e25c2-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="e25c2-136">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e25c2-136">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e25c2-137">См. также</span><span class="sxs-lookup"><span data-stu-id="e25c2-137">See Also</span></span>


[<span data-ttu-id="e25c2-138">Изменение магистрали в построителе топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e25c2-138">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

