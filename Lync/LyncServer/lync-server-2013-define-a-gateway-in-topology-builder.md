---
title: 'Lync Server 2013: определение шлюза в построителе топологий'
description: 'Lync Server 2013: определение шлюза в построителе топологий.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f8bf09f06f54d8988c8c9a9e385ef251a960bd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567805"
---
# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="a08bd-103">Определение шлюза в построителе топологий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a08bd-103">Define a gateway in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a08bd-104">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="a08bd-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="a08bd-105">Выполните следующие действия, чтобы использовать построитель топологий, чтобы определить *узел* , с которым можно связать сервер-посредник, чтобы обеспечить подключение к телефонной сети общего пользования (PSTN) для пользователей, для которых включена поддержка корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a08bd-105">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="a08bd-106">Одноранговый сервер-посредник может быть шлюзом PSTN, IP-УАТС или пограничным контроллером сеансов (SBC) для поставщика услуг Интернет-телефонии (ITSP), к которому можно подключиться с помощью настройки магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="a08bd-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a08bd-107">В этом разделе предполагается, что вы настроили по крайней мере один внутренний интерфейсный пул или сервер Standard Edition по крайней мере на одном центральном сайте с размещенным или автономным сервером-посредником, как описано в статье <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Определение и Настройка пула переднего плана или сервера Standard Edition в Lync server 2013</A> и <A href="lync-server-2013-publish-the-topology.md">Публикация топологии в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a08bd-107">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="a08bd-108">В этом разделе также предполагается, что ваша инфраструктура соответствует требованиям, описанным в разделе <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">требования к программному обеспечению для корпоративной голосовой связи в Lync server 2013</A> , а <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">также необходимые условия для обеспечения безопасности и настройки корпоративной голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a08bd-108">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="a08bd-109">Определение однорангового узла для сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="a08bd-109">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="a08bd-110">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a08bd-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a08bd-111">В разделе Lync Server 2013, имя сайта, общие компоненты щелкните правой кнопкой мыши узел **шлюзы PSTN** и выберите команду **создать шлюз PSTN**.</span><span class="sxs-lookup"><span data-stu-id="a08bd-111">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="a08bd-112">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="a08bd-112">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="a08bd-113">В диалоговом окне **Определение нового шлюза IP/ТСОП** введите полное доменное имя или IP-адрес узла и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a08bd-113">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="a08bd-114">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="a08bd-114">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a08bd-115">Если в качестве типа транспорта указан протокол TLS, необходимо указать полное доменное имя, а не IP-адрес однорангового узла сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a08bd-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="a08bd-116">Определите режим прослушивания (IPv6 или IPv4) IP-адреса нового шлюза ТСОП и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a08bd-116">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="a08bd-117">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="a08bd-117">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="a08bd-118">Определите *корневую магистраль* для шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a08bd-118">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="a08bd-119">Магистраль — это логическое соединение между сервером-посредником и шлюзом, который однозначно идентифицируется кортежем.</span><span class="sxs-lookup"><span data-stu-id="a08bd-119">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="a08bd-120">{Полное доменное имя сервера-посредника, прослушивающий прослушивающий сервер (TLS или TCP): IP-адрес шлюза и полное доменное имя, прослушивающий порт шлюза}</span><span class="sxs-lookup"><span data-stu-id="a08bd-120">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="a08bd-121">При определении шлюза PSTN в построителе топологий необходимо определить корневую магистраль, чтобы успешно добавить шлюз PSTN в топологию.</span><span class="sxs-lookup"><span data-stu-id="a08bd-121">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="a08bd-122">Корневая магистраль не может быть удалена, пока не будет удален шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a08bd-122">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="a08bd-123">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="a08bd-123">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="a08bd-124">В разделе **прослушивающий порт для шлюза IP/PSTN**введите прослушивающий порт, который шлюз, УАТС или SBC будет использовать для SIP-сообщений от сервера-посредника, который будет связан с корневой магистралью шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="a08bd-124">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="a08bd-125">(По умолчанию для протокола TCP и протокола TLS на шлюзе PSTN, УАТС или SBC используются порты 5066 для протокола управления передачей (TCP) и 5067.</span><span class="sxs-lookup"><span data-stu-id="a08bd-125">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="a08bd-126">В устройстве для обеспечения связи в филиалах на сайте филиала по умолчанию используются порты 5081 для TCP и 5082 для TLS.</span><span class="sxs-lookup"><span data-stu-id="a08bd-126">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="a08bd-127">В разделе **Транспортный протокол SIP** выберите тип транспорта, используемый одноранговым узлом, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a08bd-127">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a08bd-128">В целях безопасности настоятельно рекомендуется развернуть одноранговый сервер-посредник, который может использовать TLS.</span><span class="sxs-lookup"><span data-stu-id="a08bd-128">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="a08bd-129">В разделе **связанный сервер-посредник**выберите пул серверов-посредников, который необходимо связать с корневой магистралью этого шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="a08bd-129">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="a08bd-130">В разделе **связанный порт сервера-посредника**введите прослушивающий порт, который сервер-посредник будет использовать для SIP-сообщений от шлюза.</span><span class="sxs-lookup"><span data-stu-id="a08bd-130">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a08bd-131">С поддержкой нескольких магистральных каналов в Lync Server 2013 можно определить несколько портов сигналов SIP на сервере-посреднике, который будет использоваться для связи с несколькими шлюзами PSTN.</span><span class="sxs-lookup"><span data-stu-id="a08bd-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="a08bd-132">При определении магистрали <STRONG>связанный с ним порт сервера-посредника</STRONG> должен находиться в пределах диапазона прослушивающих портов для соответствующего протокола, разрешенного сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="a08bd-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="a08bd-133">Этот диапазон портов определен в разделе Lync Server 2013 и пулы-посредники.</span><span class="sxs-lookup"><span data-stu-id="a08bd-133">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="a08bd-134">Щелкните правой кнопкой мыши интересующий пул сервера-посредника и выберите команду <STRONG>изменить свойства</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a08bd-134">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="a08bd-135">Укажите диапазон портов в поле <STRONG>Прослушивающие порты</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a08bd-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="a08bd-136">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a08bd-136">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a08bd-137">Прежде чем завершить этот шаг, убедитесь, что определенный вами одноранговый узел работает и использует заданное полное доменное имя или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="a08bd-137">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="a08bd-138">Затем, чтобы добавить одноранговый узел к топологии, выполните процедуры, описанные в статье [Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md) , в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a08bd-138">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="a08bd-139">Топологию необходимо опубликовать каждый раз, когда вы используете построитель топологий для создания или изменения топологии, чтобы эти данные можно было использовать для установки файлов для серверов, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a08bd-139">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a08bd-140">См. также</span><span class="sxs-lookup"><span data-stu-id="a08bd-140">See Also</span></span>


[<span data-ttu-id="a08bd-141">Изменение магистрали в построителе топологий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a08bd-141">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

