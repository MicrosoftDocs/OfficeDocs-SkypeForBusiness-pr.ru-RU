---
title: 'Lync Server 2013: сетевые параметры для расширенных функций корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d6b01009aac5fdaf3d69e24b4137897e70051b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="9c44e-102">Сетевые параметры для расширенных функций корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c44e-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c44e-103">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="9c44e-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="9c44e-104">Lync Server включает три расширенные функции корпоративной голосовой связи: контроль допуска звонков (CAC), экстренные службы (E9-1-1) и обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="9c44e-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="9c44e-105">Эти функции совместно используют определенные требования к конфигурации для областей сети, сетевых сайтов и сопоставления каждой подсети в топологии Lync Server с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="9c44e-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="9c44e-106">Подробные сведения о планировании развертывания этих функций см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="9c44e-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="9c44e-107">Планирование контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c44e-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="9c44e-108">Планирование экстренных служб (E9-1-1) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c44e-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="9c44e-109">Планирование обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c44e-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="9c44e-110">Подробнее о развертывании каждой из этих функций можно узнать [в статье Deployment Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="9c44e-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="9c44e-111">В этом разделе представлены общие сведения о требованиях к конфигурации, которые являются общими для всех трех расширенных функций корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9c44e-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="9c44e-112">Области сети</span><span class="sxs-lookup"><span data-stu-id="9c44e-112">Network Regions</span></span>

<span data-ttu-id="9c44e-113">Область сети — это сетевой концентратор или сетевая магистраль, которая используется только в конфигурации контроля допуска звонков (CAC), служб экстренной помощи и обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="9c44e-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9c44e-114">Регионы сети отличаются от регионов конференц-связи с телефонным подключением Lync Server, которые необходимы для связи номеров доступа к конференц-связи с телефонным подключением с помощью одной или нескольких абонентских планов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c44e-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="9c44e-115">Дополнительные сведения о регионах конференц-связи с телефонным подключением приведены в статье Planninging ( <A href="lync-server-2013-dial-in-conferencing-requirements.md">требования к конференц-связи с телефонным подключением в Lync Server 2013</A> ).</span><span class="sxs-lookup"><span data-stu-id="9c44e-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="9c44e-116">Для управления CAC необходимо, чтобы у каждого региона сети был связанный центральный сайт Lync Server, который управляет трафиком мультимедиа в пределах региона (то есть принимает решения на основе настроенных политик, в зависимости от того, может ли работать аудио-или видеосеанс в режиме реального времени. устанавливаться).</span><span class="sxs-lookup"><span data-stu-id="9c44e-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="9c44e-117">Центральные сайты Lync Server не представляют географические расположения, а логически группы серверов, которые настроены в качестве пула или набора пулов.</span><span class="sxs-lookup"><span data-stu-id="9c44e-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="9c44e-118">Подробные сведения о центральных сайтах можно найти в статье [Справочник по топологии в Lync Server 2013](lync-server-2013-reference-topologies.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="9c44e-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="9c44e-119">В документации по поддержке также приведены [Поддерживаемые топологии в Lync Server 2013](lync-server-2013-supported-topologies.md) .</span><span class="sxs-lookup"><span data-stu-id="9c44e-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="9c44e-120">Чтобы настроить область сети, можно либо использовать вкладку **области** в разделе **Конфигурация сети** в панели управления Lync Server, либо выполнить командлеты **New — CsNetworkRegion** или **Set CsNetworkRegion** Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9c44e-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="9c44e-121">Инструкции приведены в статье [Создание или изменение области сети в Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) в документации по развертыванию или ссылка на документацию по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c44e-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="9c44e-122">Одни и те же определения области сети являются общими для всех трех расширенных функций корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9c44e-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="9c44e-123">Если области сети уже были созданы для одной функции, то для остальных функций не требуется создавать новые области сети.</span><span class="sxs-lookup"><span data-stu-id="9c44e-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="9c44e-124">Однако может потребоваться изменить существующее определение области сети, чтобы применить параметры для определенной функции.</span><span class="sxs-lookup"><span data-stu-id="9c44e-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="9c44e-125">Например, если созданы области сети для служб экстренной помощи (которым не требуется связанный центральный сайт), а затем разворачивается контроль допуска звонков, то необходимо изменить каждое определение областей сети, чтобы указать центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="9c44e-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="9c44e-126">Чтобы связать центральный сайт Lync Server с регионом сети, укажите имя центрального сайта: в разделе **Конфигурация сети** в панели управления Lync Server или с помощью командлетов **New-CsNetworkRegion** или **Set-CsNetworkRegion** Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9c44e-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="9c44e-127">Инструкции приведены в статье [Создание или изменение области сети в Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) в документации по развертыванию или ссылка на документацию по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c44e-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="9c44e-128">Узлы сети</span><span class="sxs-lookup"><span data-stu-id="9c44e-128">Network Sites</span></span>

<span data-ttu-id="9c44e-p107">Узел сети представляет географическое расположение, такое как филиал, региональное отделение или главный офис. Каждый узел сети должен быть связан с конкретной областью сети.</span><span class="sxs-lookup"><span data-stu-id="9c44e-p107">A network site represents a geographical location, such as a branch office, a regional office, or a main office. Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9c44e-131">Сетевые сайты используются только расширенными функциями корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9c44e-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="9c44e-132">Они не совпадают с сайтами филиалов, настроенными в вашей топологии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c44e-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="9c44e-133">Дополнительные сведения о сайтах филиалов приведены в статье Планирование <A href="lync-server-2013-reference-topologies.md">в статье Справочники по топологиям в Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="9c44e-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="9c44e-134">В документации по поддержке также приведены <A href="lync-server-2013-supported-topologies.md">Поддерживаемые топологии в Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="9c44e-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="9c44e-135">Чтобы настроить сетевой сайт и связать его с регионом сети, можно воспользоваться разделом **Конфигурация сети** в панели управления Lync Server или запустить командлеты командной консоли Lync Server **New-CsNetworkSite** или **Set-CsNetworkSite** .</span><span class="sxs-lookup"><span data-stu-id="9c44e-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="9c44e-136">Дополнительные сведения приведены в статье [Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) в документации по развертыванию или ссылка на документацию по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c44e-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="9c44e-137">Идентификация IP-подсетей</span><span class="sxs-lookup"><span data-stu-id="9c44e-137">Identify IP Subnets</span></span>

<span data-ttu-id="9c44e-p110">Для каждого узла сети потребуется совместно с администратором сети определить, какая IP-подсеть назначена этому узлу сети. Если ваш администратор сети уже организовал IP-подсети в области сети и в узлы сети, то ваша работа значительно облегчается.</span><span class="sxs-lookup"><span data-stu-id="9c44e-p110">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="9c44e-p111">В нашем примере узлу New York в области North America назначены следующие IP-подсети: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Когда Боб, который обычно работает в Детройте, приезжает в офис в Нью-Йорке для прохождения обучения, он включает свой компьютер и подключается к сети, его компьютер получает IP-адрес в одном из четырех диапазонов, выделенных для Нью-Йорка, например 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="9c44e-p111">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9c44e-142">IP-подсети, заданные во время конфигурации сети на сервере, должны соответствовать формату, предоставленному клиентскими компьютерами, чтобы они использовались соответствующим образом для обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="9c44e-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="9c44e-143">Клиент Lync принимает свой локальный IP-адрес и маскирует IP-адрес со связанной маской подсети.</span><span class="sxs-lookup"><span data-stu-id="9c44e-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="9c44e-144">При определении идентификатора обхода, связанного с каждым клиентом, регистратор будет сравнивать список IP-подсетей, связанных с каждым узлом сети, с подсетью, предоставленной клиентом, и искать точное совпадение.</span><span class="sxs-lookup"><span data-stu-id="9c44e-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="9c44e-145">По этой причине важно, чтобы подсети, указанные при конфигурации сети на сервере, были не виртуальными, а реальными подсетями.</span><span class="sxs-lookup"><span data-stu-id="9c44e-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="9c44e-146">(Если разворачивается контроль допуска звонков, но не обход сервера-посредника, то контроль допуска звонков будет работать должным образом даже при настройке виртуальных подсетей.)</span><span class="sxs-lookup"><span data-stu-id="9c44e-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="9c44e-147">Например, если клиент Lync выполняет вход на компьютер с IP-адресом 172.29.81.57 с маской IP-подсети 255.255.255.0, он запрашивает идентификатор обхода, связанный с подсетью 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="9c44e-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="9c44e-148">Если подсеть определена как 172.29.0.0/16, то хотя клиент принадлежит этой виртуальной подсети, регистратор не будет считать это соответствием, поскольку точно ищет подсеть 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="9c44e-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="9c44e-149">Поэтому важно, чтобы администратор ввел подсети в точном соответствии с предоставлением клиентов Lync (которые предоставляются подсетями во время настройки сети, как статическим, так и динамическим протоколом DHCP).</span><span class="sxs-lookup"><span data-stu-id="9c44e-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="9c44e-150">Сопоставление подсетей с узлами сети</span><span class="sxs-lookup"><span data-stu-id="9c44e-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="9c44e-151">Каждая подсеть в корпоративной сети должна быть связана с узлом сети (т.е. каждая подсеть должна быть связана с географическим расположением).</span><span class="sxs-lookup"><span data-stu-id="9c44e-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="9c44e-152">Такая связь подсетей позволяет расширенным функциям корпоративной голосовой связи искать конечные точки географически.</span><span class="sxs-lookup"><span data-stu-id="9c44e-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="9c44e-153">Например, обнаружение конечных точек позволяет контролю допуска звонков регулировать поток аудио- и видеоданных в режиме реального времени, приходящий в этот узел сети и выходящий из него.</span><span class="sxs-lookup"><span data-stu-id="9c44e-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="9c44e-154">Чтобы связать подсети с сетевыми сайтами, можно воспользоваться разделом **Конфигурация сети** в панели управления Lync Server или использовать командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c44e-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="9c44e-155">Инструкции приведены в статье [связывание подсети с сетевым сайтом в Lync server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) в документации по развертыванию или ссылки на документацию по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c44e-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c44e-156">См. также</span><span class="sxs-lookup"><span data-stu-id="9c44e-156">See Also</span></span>


[<span data-ttu-id="9c44e-157">Планирование контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c44e-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="9c44e-158">Планирование экстренных служб (E9-1-1) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c44e-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="9c44e-159">Планирование обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c44e-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

