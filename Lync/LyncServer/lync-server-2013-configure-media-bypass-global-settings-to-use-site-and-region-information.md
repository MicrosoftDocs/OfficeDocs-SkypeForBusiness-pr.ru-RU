---
title: Настройка глобальных параметров обхода сервера-посредника для использования сведений о сайте и области
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac820c444f894aabf060c06d6f034f7d92b696c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="dbd56-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span><span class="sxs-lookup"><span data-stu-id="dbd56-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbd56-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="dbd56-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="dbd56-104">В этой статье предполагается, что вы уже настроили мультимедиа для всех каналов подключения с сервера-посредника на одноранговый шлюз (коммутируемая телефонная сеть (PSTN), IP-УАТС или одновременный контроллер границ (SBC) в службе телефонной связи через Интернет. Поставщик (ИТСП) для определенного сайта или службы, для которого требуется, чтобы мультимедиа обходило сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="dbd56-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="dbd56-105">В этом разделе предполагается, что вы определили все центральные сайты и сайты филиалов в построителе топологии так, чтобы они соответствовали сетевому региону, сетевому сайту и конфигурации подсети, которые были выполнены в соответствии с инструкциями по <A href="lync-server-2013-create-or-modify-a-network-region.md">созданию и изменению сетевого 2013 региона</A>в lync Server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013</A>, а также <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">для связывания подсети с сетевым сайтом в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dbd56-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="dbd56-106">Если это не так, обход мультимедиа не будет успешным.</span><span class="sxs-lookup"><span data-stu-id="dbd56-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="dbd56-107">Кроме включения функции обхода мультимедиа для отдельных магистральных подключений, связанных с одноранговым узлом, необходимо также настроить глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="dbd56-107">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings.</span></span> <span data-ttu-id="dbd56-108">Если вы используете действия, описанные в этом разделе, чтобы настроить общие параметры для обхода мультимедиа, предполагается, что в вашей конфигурации влияет одна или обе из указанных ниже ситуаций.</span><span class="sxs-lookup"><span data-stu-id="dbd56-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="dbd56-109">У *вас нет* хорошей связи между конечными точками Lync Server и любыми одноранговыми узлами, для которых вы настроили обходные носители на магистральном подключении.</span><span class="sxs-lookup"><span data-stu-id="dbd56-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="dbd56-110">Включено управление допуском звонков (CAC) для управления пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="dbd56-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="dbd56-111">Подробные сведения о том, как и об управлении допуском звонков, и на обход мультимедиа можно найти в разделе "Управление допуском звонков из бесконтактных подключений" на сервере обобщения <A href="lync-server-2013-media-bypass-and-mediation-server.md">и исправлений мультимедиа в Lync server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="dbd56-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="dbd56-p103">Информация об областях сети и сетевых узлах совместно используется компонентами расширенной корпоративной голосовой связи с обходом сервера посредника и контроля допуска звонков (когда оба этих компоненты включены). Таким образом, если контроль допуска звонков уже настроен, не нужно использовать следующую процедуру для изменения информации о сетевых узлах и областях сети специально для обхода сервера-посредника. Выполните описанные в этой процедуре действия, если области сети и сетевые узлы для контроля допуска звонков еще не настроены и нужно изменить параметры обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="dbd56-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="dbd56-115">Кроме того, если вы хотите использовать сведения о сайте и регионе для принятия решения по пропуску, выполните указанные ниже действия, но не задействуете разрешение на управление предоставлением звонков.</span><span class="sxs-lookup"><span data-stu-id="dbd56-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="dbd56-116">В таком случае ссылки с ограниченным доступом к пропускной способности по-прежнему должны быть представлены через политики межсетевого соединения, как описано в разделе [Создание политик межсетевого канала в Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dbd56-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="dbd56-117">Фактические ограничения пропускной способности не так важны, так как управление допуском звонков не включено.</span><span class="sxs-lookup"><span data-stu-id="dbd56-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="dbd56-118">Вместо этого эти ссылки используются для секционирования подсетей, чтобы указать, что они не имеют ограничений по пропускной способности и могут, следовательно, использовать мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="dbd56-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="dbd56-119">Обратите внимание, что это также верно, когда включена функция управления допуском звонков и обходится мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="dbd56-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="dbd56-120">Кроме того, чтобы обойтись без ошибок, необходимо наличие согласованности между сайтом, определенным в построителе топологии, и оно определено при настройке регионов сети и сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="dbd56-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="dbd56-121">Например, если у вас есть сайт филиала, определенный в построителе топологии так, чтобы он был развернут только с шлюзом PSTN, то на нем должна быть настроена Корпоративная политика голосовой связи, позволяющая пользователям сайтов филиалов маршрутизировать звонки через КТСОП. Gateway на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="dbd56-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="dbd56-122">Настройка сведений о сайте и области для обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="dbd56-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="dbd56-123">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dbd56-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dbd56-124">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dbd56-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="dbd56-125">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="dbd56-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="dbd56-126">Дважды щелкните конфигурацию **Глобальная** в таблице.</span><span class="sxs-lookup"><span data-stu-id="dbd56-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="dbd56-127">На странице **Изменение глобального параметра** установите флажок **Включить обход сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="dbd56-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="dbd56-128">Щелкните элемент **Использовать конфигурацию узлов и областей**.</span><span class="sxs-lookup"><span data-stu-id="dbd56-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="dbd56-129">При необходимости установите флажок **Включить обход сервера-посредника для несопоставленных сайтов**.</span><span class="sxs-lookup"><span data-stu-id="dbd56-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="dbd56-p107">Установите этот флажок только в том случае, если есть один или несколько крупных сайтов, сопоставленных с одной областью, для которых отсутствуют ограничения по пропускной способности (например, крупный центральный сайт), но также имеется несколько сайтов филиалов, сопоставленных с той же областью, для которых ограничения по пропускной способности присутствуют. Когда разрешается обход для несопоставленных сайтов, конфигурация упрощается, так как указываются только подсети, сопоставленные с сайтами филиалов, а указывать все подсети, сопоставленные со всеми сайтами, не требуется. Рекомендуется не устанавливать этот флажок, когда включен контроль допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="dbd56-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="dbd56-133">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="dbd56-133">Click **Commit**.</span></span>

<span data-ttu-id="dbd56-134">Затем добавьте к сетевому сайту подсети, как описано в разделе [связывание подсетей с сетевыми сайтами для обхода мультимедиа в Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="dbd56-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="dbd56-135">(Фактические процедуры для связывания подсетей с сетевыми сайтами описаны в разделе [связывание подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) После того как вы свяжете все подсети с сетевыми сайтами, развертывание мультимедиа завершается.</span><span class="sxs-lookup"><span data-stu-id="dbd56-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="dbd56-136">Если вы еще не создали области сети и сетевые узлы, вам необходимо создать их, прежде чем вы сможете приступить к развертыванию обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="dbd56-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="dbd56-137">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-create-or-modify-a-network-region.md">Создание или изменение сетевого региона в Lync server 2013</A> , а <A href="lync-server-2013-create-or-modify-a-network-site.md">также создание или изменение сетевого сайта в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dbd56-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dbd56-138">См. также</span><span class="sxs-lookup"><span data-stu-id="dbd56-138">See Also</span></span>


[<span data-ttu-id="dbd56-139">Связывание подсетей с сетевыми сайтами для обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbd56-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

