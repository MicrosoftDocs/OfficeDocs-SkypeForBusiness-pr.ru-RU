---
title: 'Lync Server 2013: определение шлюза в построителе топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c9e57ad4e3d8c1692731bcfd4a56dc5c3d05bda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="fc6bd-102">Определение шлюза в построителе топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc6bd-102">Define a gateway in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc6bd-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="fc6bd-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="fc6bd-104">Выполните эти действия, чтобы определить одноранговый элемент \*\* , с помощью которого можно связать сервер-посредник, чтобы обеспечить подключение к телефонной сети с открытым коммутируемым доступом (КТСОП) для пользователей, поддерживающих корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-104">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="fc6bd-105">Одноранговый сервер может быть шлюзом PSTN, IP-УАТС или контроллером границ сеанса (SBC) для поставщика услуг телефонной связи через Интернет (ИТСП), к которому вы подключаетесь, настраивая магистраль SIP.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-105">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fc6bd-106">В этой статье предполагается, что вы установили по крайней мере один внутренний пул внешних интерфейсов или сервер Standard Edition по крайней мере на одном центральном сайте с размещенным или изолированным сервером-посредником, как описано в статье <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Определение и Настройка внешнего пула и сервера Standard Edition в Lync Server 2013</A> и <A href="lync-server-2013-publish-the-topology.md">опубликуйте топологию в lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-106">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="fc6bd-107">Кроме того, в этой статье предполагается, что ваша инфраструктура отвечает требованиям, описанным в разделе Требования к <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">программному обеспечению для корпоративной голосовой связи в Lync Server 2013</A> и <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">требования к безопасности и конфигурации для корпоративной голосовой связи в Lync Сервер 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-107">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="fc6bd-108">Определение однорангового узла для сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="fc6bd-108">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="fc6bd-109">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="fc6bd-110">В разделе Lync Server 2013, имя сайта, общие компоненты щелкните правой кнопкой мыши узел **шлюзы PSTN** и выберите команду **создать шлюз PSTN**.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-110">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="fc6bd-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1] (images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="fc6bd-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="fc6bd-112">В диалоговом окне **Определение нового шлюза IP/ТСОП** введите полное доменное имя или IP-адрес узла и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-112">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="fc6bd-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8] (images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="fc6bd-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fc6bd-114">Если в качестве типа транспорта указан протокол TLS, необходимо указать полное доменное имя, а не IP-адрес однорангового сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-114">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="fc6bd-115">Определите режим прослушивания (IPv6 или IPv4) IP-адреса нового шлюза ТСОП и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-115">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="fc6bd-116">![c7fc0d12-adc8-45a7-ACA1-b376e1d2fcec] (images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-ACA1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="fc6bd-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="fc6bd-117">Определите *корневую магистраль* для шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-117">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="fc6bd-118">Магистраль — это логическая связь между сервером-посредником и шлюзом, уникальным образом идентифицированными кортежем.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-118">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="fc6bd-119">Полное доменное имя сервера-посредника, прослушивающий порт сервера (TLS или TCP): IP Gateway и FQDN, порт прослушивания шлюза}</span><span class="sxs-lookup"><span data-stu-id="fc6bd-119">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="fc6bd-120">При определении шлюза PSTN в построителе топологии необходимо определить корневой магистраль, чтобы успешно добавить шлюз PSTN в топологию.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-120">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="fc6bd-121">Корневая магистраль не может быть удалена, пока не будет удален шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-121">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="fc6bd-122">![3b030757-EB35-4616-bb6b-74ee67507e3d] (images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-EB35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="fc6bd-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="fc6bd-123">В разделе **прослушивающий порт для IP/КТСОП Gateway**введите прослушивающий порт, который шлюз, УАТС или SBC будет использовать для сообщений SIP от сервера-посредника, который будет связан с корневой магистральным шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-123">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="fc6bd-124">(По умолчанию используется порт 5066 для TCP и порт 5067 для TLS на шлюзе ТСОП, УАТС или SBC.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-124">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="fc6bd-125">Для бесперебойно работающего устройства филиалов на сайте филиала по умолчанию используются порты 5081 для TCP и 5082 для TLS.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-125">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="fc6bd-126">В разделе **Транспортный протокол SIP** выберите тип транспорта, используемый одноранговым узлом, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-126">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fc6bd-127">По соображениям безопасности настоятельно рекомендуется развернуть одноранговый элемент на сервере-посреднике, который может использовать TLS.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="fc6bd-128">В разделе сопоставленный **сервер исправлений**выберите пул серверов обисправлений, который нужно связать с корневой магистральной магистрали этого шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="fc6bd-129">В разделе **связанный порт сервера исправлений**введите прослушивающий порт, который сервер обправителя будет использовать для SIP messages с шлюза.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fc6bd-130">Поддержка нескольких коммуникационных каналов в Lync Server 2013 позволяет определить несколько сигнальных портов SIP на сервере, который будет использоваться для связи с несколькими шлюзами PSTN.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-130">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="fc6bd-131">При определении канала связи <STRONG>соответствующий порт сервера</STRONG> -посредника должен находиться в диапазоне портов прослушивания соответствующего протокола, разрешенного сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-131">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="fc6bd-132">Этот диапазон портов определен в группе Lync Server 2013 и пулы исправлений.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-132">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="fc6bd-133">Щелкните правой кнопкой мыши требуемый пул серверов-исправлений и выберите команду <STRONG>изменить свойства</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-133">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="fc6bd-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="fc6bd-135">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-135">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fc6bd-136">Перед завершением этого шага убедитесь, что определенный одноранговый элемент запущен, и использует указанное полное доменное имя или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-136">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="fc6bd-137">Затем, чтобы добавить одноранговый элемент в топологию, выполните действия, описанные в разделе [Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-137">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="fc6bd-138">Вы должны опубликовать свою топологию каждый раз, когда вы используете Topology Builder для создания или изменения топологии, чтобы эти данные можно было использовать для установки файлов на серверах с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fc6bd-138">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fc6bd-139">См. также</span><span class="sxs-lookup"><span data-stu-id="fc6bd-139">See Also</span></span>


[<span data-ttu-id="fc6bd-140">Изменение магистрали в построителе топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc6bd-140">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

