---
title: 'Lync Server 2013: определение сетевых элементов, используемых для определения расположения'
description: 'Lync Server 2013: определение сетевых элементов, используемых для определения расположения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a77ad0a7d704bf2cc43118db45d9bcfb89daa327
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576285"
---
# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="24acd-103">Определение сетевых элементов, используемых для определения расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24acd-103">Defining the network elements used to determine location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24acd-104">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="24acd-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="24acd-105">Если вы настраиваете инфраструктуру Lync Server для поддержки автоматического обнаружения местонахождения клиентов, сначала необходимо решить, какие сетевые элементы будут использоваться для сопоставления абонентов с расположениями.</span><span class="sxs-lookup"><span data-stu-id="24acd-105">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="24acd-106">В Lync Server 2013 вы можете сопоставить следующие сетевые элементы уровня 2 и 3 с расположениями:</span><span class="sxs-lookup"><span data-stu-id="24acd-106">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="24acd-107">адреса BSSID точек беспроводного доступа (WAP) (уровень 2);</span><span class="sxs-lookup"><span data-stu-id="24acd-107">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="24acd-108">порт коммутатора LLDP (уровень 2);</span><span class="sxs-lookup"><span data-stu-id="24acd-108">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="24acd-109">идентификаторы шасси коммутаторов LLDP (уровень 2);</span><span class="sxs-lookup"><span data-stu-id="24acd-109">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="24acd-110">IP-подсети (уровень 3);</span><span class="sxs-lookup"><span data-stu-id="24acd-110">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="24acd-111">MAC-адреса клиентов (уровень 2).</span><span class="sxs-lookup"><span data-stu-id="24acd-111">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="24acd-112">Элементы сети перечислены в порядке приоритета.</span><span class="sxs-lookup"><span data-stu-id="24acd-112">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="24acd-113">Если клиент можно найти с помощью нескольких элементов сети, Lync Server использует порядок приоритетов для определения используемого механизма.</span><span class="sxs-lookup"><span data-stu-id="24acd-113">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="24acd-114">В следующих подразделах приводятся более подробные сведения об использовании каждого элемента сети.</span><span class="sxs-lookup"><span data-stu-id="24acd-114">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24acd-115">При использовании сетевых элементов для сопоставления вызывающих абонентов с расположением местоположениями важно, чтобы база данных службы сведений о расположениях была актуальной.</span><span class="sxs-lookup"><span data-stu-id="24acd-115">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="24acd-116">Так, если вы добавляете или изменяете элемент сети, например WAP, вам нужно удалить старую запись и добавить новую в базу данных местоположений.</span><span class="sxs-lookup"><span data-stu-id="24acd-116">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="24acd-117">Точка беспроводного доступа</span><span class="sxs-lookup"><span data-stu-id="24acd-117">Wireless Access Point</span></span>

<span data-ttu-id="24acd-118">Когда клиент подключается к сети беспроводным способом, запрос расположения использует адрес BSSID в WAP, чтобы определить его расположение.</span><span class="sxs-lookup"><span data-stu-id="24acd-118">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="24acd-119">Если клиент находится в роуминге, указанный WAP может не быть самым ближайшим, а также можно взять WAP, который находится на другом этаже здания.</span><span class="sxs-lookup"><span data-stu-id="24acd-119">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="24acd-120">Чтобы указать, что расположение приблизительно указано, можно присвоить параметру location значение NEAR или Close для дескриптора.</span><span class="sxs-lookup"><span data-stu-id="24acd-120">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="24acd-121">Этот метод определения местоположения предполагает, что адреса BSSID всех точек WAP являются статическими.</span><span class="sxs-lookup"><span data-stu-id="24acd-121">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="24acd-122">Однако если производитель WAP использует динамически назначаемые адреса BSSID, полученный адрес BSSID может измениться (вследствие изменения конфигурации WAP) и беспроводные клиенты могут не получить местоположение.</span><span class="sxs-lookup"><span data-stu-id="24acd-122">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="24acd-123">Чтобы предотвратить эту возможность, необходимо заполнить базу данных службы сведений о местоположении на Erl для всех возможных адресов BSSID, используемых каждым приложением WAP.</span><span class="sxs-lookup"><span data-stu-id="24acd-123">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="24acd-124">Порты и коммутаторы LLDP</span><span class="sxs-lookup"><span data-stu-id="24acd-124">LLDP Ports and Switches</span></span>

<span data-ttu-id="24acd-p106">Управляемые коммутаторы Ethernet, поддерживающие протокол LLDP-MED, могут сообщить свои идентификационные данные и сведения о портах клиентам, совместимым с LLDP-MED. Это позволяет затем выполнять запросы к базе данных местоположений для определения местоположения устройства. Вы можете связать сведения о местоположении для экстренных служб с идентификатором шасси коммутатора или сопоставить их также на более низком уровне — уровне портов.</span><span class="sxs-lookup"><span data-stu-id="24acd-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24acd-127">Lync Server 2013 поддерживает использование LLDP — MED для определения расположений только для устройств Lync Phone Edition и Lync 2013 под управлением Windows 8.</span><span class="sxs-lookup"><span data-stu-id="24acd-127">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="24acd-128">Если необходимо использовать данные уровня 2 уровня коммутатора, чтобы определить расположение других проводных клиентов Lync на основе компьютера, необходимо использовать метод клиентского MAC-адреса.</span><span class="sxs-lookup"><span data-stu-id="24acd-128">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="24acd-129">Подсеть</span><span class="sxs-lookup"><span data-stu-id="24acd-129">Subnet</span></span>

<span data-ttu-id="24acd-130">IP-подсети уровня 3 предоставляют механизм, поддерживаемый всеми клиентами Lync Server, которые можно использовать для автоматического обнаружения местоположения клиента.</span><span class="sxs-lookup"><span data-stu-id="24acd-130">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="24acd-131">Использование IP-подсетей является самым простым способом определения местоположения в плане настройки клиентов проводного доступа и управления ими.</span><span class="sxs-lookup"><span data-stu-id="24acd-131">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="24acd-132">Однако прежде чем выбрать его, ответьте на следующие вопросы, чтобы определить, будет ли он достаточно точным в вашей ситуации.</span><span class="sxs-lookup"><span data-stu-id="24acd-132">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="24acd-133">Охватывают ли какие-либо клиентские подсети несколько этажей?</span><span class="sxs-lookup"><span data-stu-id="24acd-133">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="24acd-134">Охватывают ли какие-либо подсети несколько зданий?</span><span class="sxs-lookup"><span data-stu-id="24acd-134">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="24acd-135">Какую площадь покрывает каждая клиентская подсеть?</span><span class="sxs-lookup"><span data-stu-id="24acd-135">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="24acd-p109">Если подсеть покрывает слишком большую площадь, может потребоваться использовать другой способ для определения местоположения клиентов. Однако, если это целесообразно, мы рекомендуем клиентам реорганизовать структуру IP-подсетей в соответствии с требованиями к точности определения местоположений ERL вместо того, чтобы реализовывать сторонние решения на основе SNMP, связанные с дополнительными затратами и повышением сложности.</span><span class="sxs-lookup"><span data-stu-id="24acd-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="24acd-138">MAC-адрес клиента</span><span class="sxs-lookup"><span data-stu-id="24acd-138">Client MAC Address</span></span>

<span data-ttu-id="24acd-139">Чтобы использовать MAC-адрес клиентского компьютера для поиска вызывающего абонента, необходимы управляемые коммутаторы Ethernet и решение SNMP стороннего производителя, которое может обнаружить MAC-адреса клиентов Lync, подключенных к (или) этим коммутаторам.</span><span class="sxs-lookup"><span data-stu-id="24acd-139">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="24acd-140">Решение SNMP постоянно опрашивает управляемые коммутаторы для получения текущих сопоставлений MAC-адресов конечной точки, подключенных к каждому порту, и получения соответствующих идентификаторов портов.</span><span class="sxs-lookup"><span data-stu-id="24acd-140">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="24acd-141">Во время запроса клиента Lync в службе сведений о расположении служба сведений о местоположении запрашивает приложение стороннего производителя, используя MAC-адрес клиента, а затем возвращает все подходящие IP-адреса коммутатора и идентификаторы портов.</span><span class="sxs-lookup"><span data-stu-id="24acd-141">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="24acd-142">Служба "сведения о местоположении" использует эти сведения для запроса к опубликованному уровню 2 карты географических соответствий для соответствующей записи и возвращает расположение клиенту.</span><span class="sxs-lookup"><span data-stu-id="24acd-142">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="24acd-143">Если вы используете этот параметр, убедитесь, что идентификаторы портов коммутатора согласованы между записями SNMP и опубликованными записями базы данных расположения.</span><span class="sxs-lookup"><span data-stu-id="24acd-143">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24acd-144">Некоторые сторонние решения SNMP могут поддерживать неуправляемые ключи доступа. Если коммутатор, который работает с клиентом Lync, неуправляемый, но имеет привязку к управляемому коммутатору распространения, управляемый коммутатор может отчитываться о нем в SNMP-адреса клиентов, подключенных к параметру доступа.</span><span class="sxs-lookup"><span data-stu-id="24acd-144">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="24acd-145">Эта информация позволяет службе сведений о местоположении определить расположение пользователя.</span><span class="sxs-lookup"><span data-stu-id="24acd-145">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="24acd-146">Тем не менее, можно назначить только один Пэр всем портам неуправляемого коммутатора, поэтому характер расположения доступен только на уровне корпуса коммутатора доступа, а не на уровне порта.</span><span class="sxs-lookup"><span data-stu-id="24acd-146">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

