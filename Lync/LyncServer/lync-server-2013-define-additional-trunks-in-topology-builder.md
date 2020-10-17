---
title: 'Lync Server 2013: определение дополнительных магистральных линий в построителе топологий'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e8e5650492cc51b024b03cc0c92f64ff46d818b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504646"
---
# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="85470-102">Определение дополнительных магистральных линий в построителе топологий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85470-102">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85470-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="85470-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="85470-104">Выполните следующие действия, чтобы использовать построитель топологий для определения дополнительной магистрали, с которой можно связать *одноранговый* сервер с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="85470-104">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="85470-105">Одноранговый узел предоставляет пользователям доступ к корпоративной голосовой связи с подключением к телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="85470-105">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="85470-106">Узлом может быть шлюз ТСОП, IP-УАТС или пограничный контроллер сеансов (SBC) для поставщика услуг Интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="85470-106">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="85470-107">Магистраль определяет соединение между сервером-посредником и одноранговым узлом.</span><span class="sxs-lookup"><span data-stu-id="85470-107">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="85470-108">Для каждого сервера-посредника может быть определено несколько магистральных линий связи.</span><span class="sxs-lookup"><span data-stu-id="85470-108">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="85470-109">Сервер-посредник может быть связан с несколькими одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="85470-109">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="85470-110">Магистраль — это логическое соединение между сервером-посредником и шлюзом, уникальным образом идентифицированным кортежем:</span><span class="sxs-lookup"><span data-stu-id="85470-110">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="85470-111">{Полное доменное имя сервера-посредника, прослушивающий прослушивающий сервер (TLS или TCP): IP-адрес шлюза и полное доменное имя, прослушивающий порт шлюза}</span><span class="sxs-lookup"><span data-stu-id="85470-111">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85470-112">В этом разделе предполагается, что вы настроили шлюз PSTN и корневую магистраль по крайней мере с одним совмещенным или автономным сервером-посредником, как описано в статье <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">определение шлюза в построителе топологий в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="85470-112">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="85470-113">В этом разделе предполагается, что вы настроили по крайней мере один интерфейсный пул или сервер Standard Edition по крайней мере на одном центральном сайте, как описано в статье <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Определение и Настройка пула переднего плана или сервера Standard Edition в Lync server 2013</A> и <A href="lync-server-2013-publish-the-topology.md">Публикация топологии в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="85470-113">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="85470-114">Определение дополнительной магистрали между сервером-посредником и одноранговым узлом шлюза</span><span class="sxs-lookup"><span data-stu-id="85470-114">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="85470-115">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="85470-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="85470-116">В разделе Lync Server 2013, имя сайта, **Общие компоненты**щелкните узел **магистрали** правой кнопкой мыши и выберите команду **создать магистраль**.</span><span class="sxs-lookup"><span data-stu-id="85470-116">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="85470-117">![Экран структуры файлов в построителе топологий Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Экран структуры файлов в построителе топологий Lync Server")</span><span class="sxs-lookup"><span data-stu-id="85470-117">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="85470-118">В окне **Определение новой магистрали** введите понятное имя для уникальной идентификации магистрали.</span><span class="sxs-lookup"><span data-stu-id="85470-118">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="85470-119">Не может быть двух магистралей с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="85470-119">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85470-120">Если в качестве типа транспорта указан протокол TLS, необходимо указать полное доменное имя, а не IP-адрес однорангового узла сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="85470-120">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="85470-121">В окне **Связанный шлюз ТСОП** выберите узел шлюза ТСОП, который следует связать с этой магистралью.</span><span class="sxs-lookup"><span data-stu-id="85470-121">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="85470-122">![Параметры свойств для однорангового шлюза PSTN для магистрали](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Параметры свойств для однорангового шлюза PSTN для магистрали")</span><span class="sxs-lookup"><span data-stu-id="85470-122">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="85470-123">В разделе **прослушивающий порт для шлюза PSTN**введите прослушивающий порт, который узел (шлюз PSTN, IP-УАТС или SBC) будет получать сообщения SIP от сервера-посредника, который должен быть связан с этой магистралью.</span><span class="sxs-lookup"><span data-stu-id="85470-123">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="85470-124">Порты по умолчанию — 5066 для протокола TCP и 5067 для TLS.</span><span class="sxs-lookup"><span data-stu-id="85470-124">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="85470-125">По умолчанию для устройства для обеспечения связи в филиалах используется порт 5081 для протокола TCP и 5082 для TLS.</span><span class="sxs-lookup"><span data-stu-id="85470-125">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="85470-126">В окне **Транспортный протокол SIP** щелкните тип транспорта, используемый узлом.</span><span class="sxs-lookup"><span data-stu-id="85470-126">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85470-127">В целях безопасности настоятельно рекомендуется развернуть одноранговый сервер-посредник, который может использовать TLS.</span><span class="sxs-lookup"><span data-stu-id="85470-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="85470-128">В разделе **связанный сервер-посредник**выберите пул серверов-посредников, который необходимо связать с корневой магистралью этого узла</span><span class="sxs-lookup"><span data-stu-id="85470-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="85470-129">В разделе **связанный порт сервера-посредника**введите прослушивающий порт, который сервер-посредник будет получать сообщения SIP от узла.</span><span class="sxs-lookup"><span data-stu-id="85470-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85470-130">При использовании нескольких магистральных каналов в Lync Server 2013 две магистральные линии связи с разными именами магистральных линий невозможно настроить с одним и тем же <STRONG>связанным портом сервера-посредником</STRONG> и <STRONG>слушающим портом для шлюза IP/PSTN</STRONG></span><span class="sxs-lookup"><span data-stu-id="85470-130">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85470-131">С поддержкой нескольких магистральных каналов в Lync Server 2013 можно определить несколько портов сигналов SIP на сервере-посреднике для связи с несколькими одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="85470-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="85470-132">При определении магистрали номер <STRONG>порта связанного сервера-посредника</STRONG> должен находиться в пределах диапазона прослушивающих портов для соответствующего протокола, разрешенного сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="85470-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="85470-133">Этот диапазон портов определен в группе Lync Server 2013 и пулы серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="85470-133">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="85470-134">Щелкните правой кнопкой мыши нужный пул серверов-посредников и выберите команду <STRONG>изменить свойства</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="85470-134">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="85470-135">Укажите диапазон портов в поле <STRONG>Прослушивающие порты</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="85470-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="85470-136">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="85470-136">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85470-137">См. также</span><span class="sxs-lookup"><span data-stu-id="85470-137">See Also</span></span>


[<span data-ttu-id="85470-138">Изменение магистрали в построителе топологий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85470-138">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

