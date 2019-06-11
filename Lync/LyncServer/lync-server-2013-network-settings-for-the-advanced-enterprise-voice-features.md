---
title: 'Lync Server 2013: сетевые параметры для расширенных корпоративных функций голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d633d111e9df09cde57b91f32f4592b7f80c9f26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="e53b4-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e53b4-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e53b4-103">_**Тема последнего изменения:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="e53b4-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="e53b4-104">На сервере Lync Server есть три опытных услуги голосовой связи: управление допуском звонков (CAC), службы экстренной помощи (E9-1) и обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e53b4-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="e53b4-105">Эти функции используются для предоставления определенных требований к конфигурации для сетевых регионов, сетевых сайтов и связей каждой подсети в топологии сервера Lync с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="e53b4-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="e53b4-106">Подробные сведения о планировании развертывания этих функций можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="e53b4-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="e53b4-107">Планирование контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e53b4-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="e53b4-108">Планирование чрезвычайных служб (E9-1-1) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e53b4-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="e53b4-109">Планирование обхода серверов-посредников в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e53b4-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="e53b4-110">Подробнее о том, как развертывать каждую из этих функций, можно найти [в разделе Развертывание дополнительных функций голосовой связи в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e53b4-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e53b4-111">В этом разделе приводятся общие сведения о требованиях к конфигурации, которые являются общими для всех трех улучшенных корпоративных голосовых функций.</span><span class="sxs-lookup"><span data-stu-id="e53b4-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="e53b4-112">Сетевые регионы</span><span class="sxs-lookup"><span data-stu-id="e53b4-112">Network Regions</span></span>

<span data-ttu-id="e53b4-113">Сетевой регион — это сетевой концентратор или сетевая магистраль, которые используются только в конфигурации контроля допуска звонков (CAC), служб экстренной помощи и обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="e53b4-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e53b4-114">Регионы сети не совпадают с областями конференц-связи с телефонным подключением Lync Server, которые необходимы для сопоставления номеров доступа для конференц-связи с телефонным подключением с помощью одной или нескольких абонентов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e53b4-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="e53b4-115">Подробнее об областях конференц-связи с телефонным подключением можно найти в разделе Требования к конференциям с <A href="lync-server-2013-dial-in-conferencing-requirements.md">телефонным подключением в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e53b4-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="e53b4-116">Для использования CAC требуется, чтобы у каждого сетевого региона был связанный центральный сайт Lync Server, который управляет трафиком мультимедиа в регионе (то есть принимают решения на основе настроенных политик, в зависимости от того, может ли этот сеанс аудио-или видеосвязи в реальном времени быть установлен).</span><span class="sxs-lookup"><span data-stu-id="e53b4-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="e53b4-117">Центральные сайты Lync Server не представляют географические расположения, а логические группы серверов, которые настроены как пул или набор пулов.</span><span class="sxs-lookup"><span data-stu-id="e53b4-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="e53b4-118">Подробнее об основных сайтах можно найти [в разделе топологии ссылок в Lync Server 2013](lync-server-2013-reference-topologies.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e53b4-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="e53b4-119">[Поддерживаемые топологии в Lync Server 2013](lync-server-2013-supported-topologies.md) можно найти в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="e53b4-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="e53b4-120">Чтобы настроить сетевой регион, вы можете воспользоваться вкладкой **регионы** в разделе **Сетевая конфигурация** на панели управления Lync Server или выполнить команду **New-кснетворкрегион** или **Set-кснетворкрегион** Lync Server Management Shell. Командлеты.</span><span class="sxs-lookup"><span data-stu-id="e53b4-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="e53b4-121">Инструкции читайте в статье [Создание или изменение сетевого региона в Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) в документации по развертыванию или ссылка на документацию по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e53b4-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="e53b4-122">Одни и те же определения сетевого региона совместно используются всеми тремя расширенными корпоративными голосовыми функциями.</span><span class="sxs-lookup"><span data-stu-id="e53b4-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="e53b4-123">Если сетевые регионы уже были созданы для одной функции, то для остальных функций не требуется создание новых сетевых регионов.</span><span class="sxs-lookup"><span data-stu-id="e53b4-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="e53b4-124">Но может потребоваться изменить существующее определение сетевых регионов, чтобы применить параметры для определенной функции.</span><span class="sxs-lookup"><span data-stu-id="e53b4-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="e53b4-125">Например, если созданы сетевые регионы для служб экстренной помощи (E9-1-1) (которым не требуется связанный центральный сайт), а затем разворачивается контроль допуска звонков, то необходимо изменить каждое определение сетевого региона, чтобы указать центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="e53b4-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="e53b4-126">Чтобы связать центральный сайт Lync Server с сетевым регионом, укажите его имя с помощью раздела " **Настройка сети** " на панели управления Lync Server или с помощью команды **New-кснетворкрегион** или \*\*Set-кснетворкрегион \*\*Командлеты оболочки Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e53b4-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="e53b4-127">Инструкции читайте в статье [Создание или изменение сетевого региона в Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) в документации по развертыванию или ссылка на документацию по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e53b4-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="e53b4-128">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="e53b4-128">Network Sites</span></span>

<span data-ttu-id="e53b4-p107">Сетевой сайт представляет географическое расположение, такое как филиал, региональное отделение или главный офис. Каждый сетевой сайт должен быть связан с конкретным сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="e53b4-p107">A network site represents a geographical location, such as a branch office, a regional office, or a main office. Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e53b4-131">Сетевые сайты используются только расширенными корпоративными голосовыми функциями.</span><span class="sxs-lookup"><span data-stu-id="e53b4-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="e53b4-132">Они не совпадают с сайтами филиалов, которые настроены в топологии сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="e53b4-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="e53b4-133">Дополнительные сведения о сайтах филиалов можно найти <A href="lync-server-2013-reference-topologies.md">в разделе топологии ссылок в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e53b4-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="e53b4-134"><A href="lync-server-2013-supported-topologies.md">Поддерживаемые топологии в Lync Server 2013</A> можно найти в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="e53b4-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="e53b4-135">Чтобы настроить сайт сети и связать его с сетевым регионом, вы можете либо использовать раздел " **Настройка сети** " на панели управления Lync Server, либо запустить командную консоль Lync Server Management **New-кснетворксите** или **Set-кснетворксите** Командлеты.</span><span class="sxs-lookup"><span data-stu-id="e53b4-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="e53b4-136">Подробнее читайте в статье [Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) в документации по развертыванию или ссылка на документацию по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e53b4-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="e53b4-137">Определение IP-подсетей</span><span class="sxs-lookup"><span data-stu-id="e53b4-137">Identify IP Subnets</span></span>

<span data-ttu-id="e53b4-p110">Для каждого сетевого сайта потребуется совместно с администратором сети определить, какая IP-подсеть назначена этому сетевому сайту. Если ваш администратор сети уже организовал IP-подсети в сетевые регионы и сетевые сайты, ваша работа значительно облегчается.</span><span class="sxs-lookup"><span data-stu-id="e53b4-p110">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="e53b4-p111">В нашем примере сайту "Нью-Йорк" в регионе "Северная Америка" назначены следующие IP-подсети: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Когда Боб, который обычно работает в Детройте, приезжает в офис в Нью-Йорке для прохождения обучения, он включает свой компьютер и подключается к сети, его компьютер получает IP-адрес в одном из четырех диапазонов, выделенных для Нью-Йорка, например 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="e53b4-p111">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e53b4-142">IP-подсети, заданные во время конфигурации сети на сервере, должны соответствовать формату, предоставленному клиентскими компьютерами, чтобы они использовались соответствующим образом для обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="e53b4-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="e53b4-143">Клиент Lync принимает свой локальный IP-адрес и маскирует IP-адрес с помощью соответствующей маски подсети.</span><span class="sxs-lookup"><span data-stu-id="e53b4-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="e53b4-144">При определении идентификатора обхода, связанного с каждым клиентом, регистратор будет сравнивать список IP-подсетей, связанных с каждым сетевым сайтом, с подсетью, предоставленной клиентом, и искать точное совпадение.</span><span class="sxs-lookup"><span data-stu-id="e53b4-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="e53b4-145">По этой причине важно, чтобы подсети, указанные при конфигурации сети на сервере, были не виртуальными, а реальными подсетями.</span><span class="sxs-lookup"><span data-stu-id="e53b4-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="e53b4-146">(Если разворачивается контроль допуска звонков, а не обход сервера-посредника, то контроль допуска звонков будет работать должным образом даже при настройке виртуальных подсетей.)</span><span class="sxs-lookup"><span data-stu-id="e53b4-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="e53b4-147">Например, если клиент Lync выполняет вход на компьютере с IP-адресом 172.29.81.57 с маской подсети IP 255.255.255.0, он запрашивает идентификатор обхода, связанный с подсетью 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="e53b4-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="e53b4-148">Если подсеть определена как 172.29.0.0/16, то хотя клиент принадлежит к этой виртуальной подсети, регистратор не будет считать это соответствием, поскольку точно ищет подсеть 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="e53b4-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="e53b4-149">Таким образом, важно, чтобы администратор ввел подсети точно так же, как и в клиентах Lync (которые доставляются с подсетями в процессе настройки сети, статически или по протоколу DHCP).</span><span class="sxs-lookup"><span data-stu-id="e53b4-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="e53b4-150">Сопоставление подсетей с сетевыми сайтами</span><span class="sxs-lookup"><span data-stu-id="e53b4-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="e53b4-151">Каждая подсеть в корпоративной сети должна быть связана с сетевым сайтом (т.е. каждая подсеть должна быть связана с географическим расположением).</span><span class="sxs-lookup"><span data-stu-id="e53b4-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="e53b4-152">Такая ассоциация подсетей позволяет дополнительно находить конечные точки в графических элементах предприятия.</span><span class="sxs-lookup"><span data-stu-id="e53b4-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="e53b4-153">Например, обнаружение конечных точек позволяет функции контроля допуска звонков регулировать поток аудио- и видео данных в режиме реального времени, приходящий на этот сетевой сайт и исходящий из него.</span><span class="sxs-lookup"><span data-stu-id="e53b4-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="e53b4-154">Чтобы связать подсети с сетевыми сайтами, вы можете использовать раздел " **Настройка сети** " на панели управления Lync Server или консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e53b4-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="e53b4-155">Инструкции можно найти в разделе [Сопоставление подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) в документации по развертыванию или ознакомьтесь с документацией по командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e53b4-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e53b4-156">См. также</span><span class="sxs-lookup"><span data-stu-id="e53b4-156">See Also</span></span>


[<span data-ttu-id="e53b4-157">Планирование контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e53b4-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="e53b4-158">Планирование чрезвычайных служб (E9-1-1) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e53b4-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="e53b4-159">Планирование обхода серверов-посредников в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e53b4-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

