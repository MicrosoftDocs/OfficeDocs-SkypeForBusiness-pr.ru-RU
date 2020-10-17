---
title: 'Lync Server 2013: Включение маршрутизации Location-Based'
description: 'Lync Server 2013: Включение маршрутизации Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7844af5792468cd5645b6b42c857c63b943c2df1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557625"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="3b20a-103">Включение маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b20a-103">Enabling Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b20a-104">_**Последнее изменение темы:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="3b20a-104">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="3b20a-105">После развертывания корпоративной голосовой связи и определенных областей сети, сайтов и подсетей можно включить маршрутизацию Location-Based.</span><span class="sxs-lookup"><span data-stu-id="3b20a-105">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="3b20a-106">Маршрутизация Location-Based должна быть включена для следующих элементов корпоративной голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="3b20a-106">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="3b20a-107">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="3b20a-107">Network sites</span></span>

  - <span data-ttu-id="3b20a-108">Конфигурации магистрали</span><span class="sxs-lookup"><span data-stu-id="3b20a-108">Trunk configurations</span></span>

  - <span data-ttu-id="3b20a-109">Политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3b20a-109">Voice policies</span></span>

  - <span data-ttu-id="3b20a-110">Конфигурация маршрутизации</span><span class="sxs-lookup"><span data-stu-id="3b20a-110">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="3b20a-111">Включение маршрутизации Location-Based для сетевых сайтов</span><span class="sxs-lookup"><span data-stu-id="3b20a-111">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="3b20a-112">После развертывания корпоративной голосовой связи и настроенных сетевых сайтов можно приступать к настройке маршрутизации Location-Based.</span><span class="sxs-lookup"><span data-stu-id="3b20a-112">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="3b20a-113">Сначала необходимо создать политику маршрутизации голосовой связи, чтобы связать сетевой сайт с подходящими использованиями PSTN.</span><span class="sxs-lookup"><span data-stu-id="3b20a-113">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="3b20a-114">При назначении использования PSTN для политики маршрутизации голосовых вызовов обязательно используйте только использование PSTN, связанное с маршрутами голосовой связи, которые используют локальный шлюз PSTN для сайта, или шлюз PSTN, расположенный в регионе, где не требуются ограничения маршрутизации Location-Based. Создайте политики маршрутизации голосовой связи с помощью команды Lync Server Windows PowerShell, панели управления New — CsVoiceRoutingPolicy или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b20a-114">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="3b20a-115">Дополнительные сведения см. в статье [New – CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="3b20a-115">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="3b20a-116">В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют две политики маршрутизации голосовых вызовов и связанные с ними использование PSTN, определенные в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="3b20a-116">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="3b20a-117">Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="3b20a-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="3b20a-118">Политика маршрутизации голосовых вызовов 1</span><span class="sxs-lookup"><span data-stu-id="3b20a-118">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="3b20a-119">Политика маршрутизации голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="3b20a-119">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b20a-120">Идентификатор политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3b20a-120">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="3b20a-121">Политика маршрутизации голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="3b20a-121">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3b20a-122">Политика маршрутизации голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="3b20a-122">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b20a-123">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="3b20a-123">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3b20a-124">Использование Нью Дели, использование УАТС Del, использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="3b20a-124">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="3b20a-125">Использование Хидерабад, использование Хид УАТС, использование УАТС del</span><span class="sxs-lookup"><span data-stu-id="3b20a-125">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="3b20a-126">Затем настройте маршрутизацию Location-Based для соответствующих сетевых сайтов и свяжите с ними политики маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="3b20a-126">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="3b20a-127">Используйте команду Lync Server Windows PowerShell New-CsNetworkSite, чтобы включить маршрутизацию Location-Based и связать политики маршрутизации голосовых вызовов с сетевыми сайтами, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3b20a-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="3b20a-128">В приведенном ниже примере показана Location-Based маршрутизация для двух различных сетевых сайтов, Нью Дели и Хидерабад, определенных в этом сценарии с помощью Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b20a-128">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="3b20a-129">Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="3b20a-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="3b20a-130">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="3b20a-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="3b20a-131">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="3b20a-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b20a-132">Имя сайта</span><span class="sxs-lookup"><span data-stu-id="3b20a-132">Site Name</span></span></p></td>
<td><p><span data-ttu-id="3b20a-133">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="3b20a-133">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="3b20a-134">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="3b20a-134">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b20a-135">енаблелокатионбаседраутинг</span><span class="sxs-lookup"><span data-stu-id="3b20a-135">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="3b20a-136">Да</span><span class="sxs-lookup"><span data-stu-id="3b20a-136">True</span></span></p></td>
<td><p><span data-ttu-id="3b20a-137">Да</span><span class="sxs-lookup"><span data-stu-id="3b20a-137">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b20a-138">Политика маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3b20a-138">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3b20a-139">Политика маршрутизации голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="3b20a-139">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3b20a-140">Политика маршрутизации голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="3b20a-140">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b20a-141">Подсети</span><span class="sxs-lookup"><span data-stu-id="3b20a-141">Subnets</span></span></p></td>
<td><p><span data-ttu-id="3b20a-142">Подсеть 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="3b20a-142">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="3b20a-143">Подсеть 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="3b20a-143">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="3b20a-144">Включение маршрутизации Location-Based в магистрали</span><span class="sxs-lookup"><span data-stu-id="3b20a-144">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="3b20a-145">Прежде чем можно будет включить конфигурацию магистрали для маршрутизации Location-Based, необходимо создать конфигурацию магистрали для каждой магистрали или каждого сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="3b20a-145">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="3b20a-146">Чтобы создать конфигурацию магистрали, используйте команду Windows PowerShell Lync Server с параметром New – CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3b20a-146">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="3b20a-147">Если несколько магистральных линий связаны с определенной системой (например, Gateway или УАТС), необходимо изменить каждую конфигурацию магистрали, чтобы включить Location-Based ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3b20a-147">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="3b20a-148">Дополнительные сведения см. в статье [New – CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="3b20a-148">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="3b20a-149">В этом примере приведенные ниже команды Windows PowerShell иллюстрируют создание одной конфигурации магистрали для каждой магистрали в развертывании, определенном в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="3b20a-149">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="3b20a-150">После настройки магистрали для каждой магистрали можно использовать командную консоль Windows PowerShell Lync Server, Set-CsTrunkConfiguration, чтобы включить Location-Based маршрутизацию в магистральные сети, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3b20a-150">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="3b20a-151">Включите маршрутизацию Location-Based в магистрали, которые направляют вызовы на шлюзы PSTN, которые направляют вызовы в PSTN, и связывают сетевой сайт, на котором расположен шлюз.</span><span class="sxs-lookup"><span data-stu-id="3b20a-151">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="3b20a-152">Дополнительные сведения см. в статье [New – CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="3b20a-152">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="3b20a-153">В этом примере Location-Based маршрутизация включена для каждой магистрали, связанной с шлюзами PSTN в Нью Дели и Хидерабад:</span><span class="sxs-lookup"><span data-stu-id="3b20a-153">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="3b20a-154">Не включайте Location-Based маршрутизацию для магистральных каналов, которые не направляют звонки в PSTN; Тем не менее, по-прежнему необходимо связать магистраль с сетевым сайтом, на котором размещается система, в качестве Location-Based ограничения маршрутизации, которые должны быть применены для вызовов PSTN, которые подключаются с помощью этой магистрали.</span><span class="sxs-lookup"><span data-stu-id="3b20a-154">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="3b20a-155">В этом примере Location-Based маршрутизация не включена для каждой магистрали, связанной с системами УАТС в Нью Дели и Хидерабад:</span><span class="sxs-lookup"><span data-stu-id="3b20a-155">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="3b20a-156">Конечные точки, которые подключены к системам, которые не направляют вызовы в PSTN (например, УАТС), будут иметь аналогичные ограничения в качестве конечных точек Lync для пользователей, для которых включена маршрутизация Location-Based.</span><span class="sxs-lookup"><span data-stu-id="3b20a-156">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="3b20a-157">Это означает, что эти пользователи смогут размещать и принимать звонки пользователю Lync независимо от расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="3b20a-157">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="3b20a-158">Кроме того, они могут выполнять прием вызовов в другие системы, которые не направляют вызовы в сеть PSTN (то есть конечная точка, подключенная к другой УАТС) независимо от того, к какому сетевому сайту относится система.</span><span class="sxs-lookup"><span data-stu-id="3b20a-158">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="3b20a-159">Все входящие звонки, исходящие звонки, передачи звонков и переадресация вызовов, связанные с конечными точками PSTN, будут подвергаться Location-Based принудительной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3b20a-159">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="3b20a-160">Такие вызовы должны использовать только шлюзы PSTN, которые определены как локальные для таких систем.</span><span class="sxs-lookup"><span data-stu-id="3b20a-160">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="3b20a-161">В следующей таблице показана конфигурация магистрали четырех магистральных линий на двух различных сетевых сайтах: два подключения к шлюзам PSTN и два подключения к системам УАТС.</span><span class="sxs-lookup"><span data-stu-id="3b20a-161">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b20a-162">Имя</span><span class="sxs-lookup"><span data-stu-id="3b20a-162">Name</span></span></th>
<th><span data-ttu-id="3b20a-163">енаблелокатионрестриктион</span><span class="sxs-lookup"><span data-stu-id="3b20a-163">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="3b20a-164">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="3b20a-164">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b20a-165">PstnGateway: магистраль 1 DEL — GW</span><span class="sxs-lookup"><span data-stu-id="3b20a-165">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="3b20a-166">Верно</span><span class="sxs-lookup"><span data-stu-id="3b20a-166">True</span></span></p></td>
<td><p><span data-ttu-id="3b20a-167">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="3b20a-167">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b20a-168">PstnGateway: магистраль 2 ХИД — GW</span><span class="sxs-lookup"><span data-stu-id="3b20a-168">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="3b20a-169">Верно</span><span class="sxs-lookup"><span data-stu-id="3b20a-169">True</span></span></p></td>
<td><p><span data-ttu-id="3b20a-170">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="3b20a-170">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b20a-171">PstnGateway: магистраль 3 DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="3b20a-171">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="3b20a-172">False</span><span class="sxs-lookup"><span data-stu-id="3b20a-172">False</span></span></p></td>
<td><p><span data-ttu-id="3b20a-173">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="3b20a-173">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b20a-174">PstnGateway: магистраль 4 ХИД — УАТС</span><span class="sxs-lookup"><span data-stu-id="3b20a-174">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="3b20a-175">False</span><span class="sxs-lookup"><span data-stu-id="3b20a-175">False</span></span></p></td>
<td><p><span data-ttu-id="3b20a-176">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="3b20a-176">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="3b20a-177">Включение маршрутизации Location-Based политик голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3b20a-177">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="3b20a-178">Чтобы обеспечить Location-Based маршрутизацию для определенных пользователей, настройте политику голосовой связи для этих пользователей, чтобы предотвратить обход платных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="3b20a-178">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="3b20a-179">Используйте командную консоль Lync Server Windows PowerShell New — CsVoicePolicy, чтобы создать новую политику голосовой связи или Set — CsVoicePolicy, если используется существующая политика, чтобы включить Location-Based маршрутизацию, запретив обход бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="3b20a-179">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="3b20a-180">Дополнительные сведения см. в статье [New – CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="3b20a-180">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="3b20a-181">В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют включение защиты от бесплатных бесплатных политик Нью Дели и Хидерабад голосовой связи, определенных в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="3b20a-181">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="3b20a-182">Только те параметры, которые относятся к Location-Based маршрутизации, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="3b20a-182">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="3b20a-183">Политика голосовой связи 1</span><span class="sxs-lookup"><span data-stu-id="3b20a-183">Voice policy 1</span></span></th>
<th><span data-ttu-id="3b20a-184">Политика голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="3b20a-184">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b20a-185">Идентификатор политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="3b20a-185">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="3b20a-186">Политика голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="3b20a-186">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="3b20a-187">Политика голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="3b20a-187">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b20a-188">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="3b20a-188">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3b20a-189">Использование Нью Дели, использование УАТС Del, использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="3b20a-189">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="3b20a-190">Использование Хидерабад, использование Хид УАТС, использование УАТС del</span><span class="sxs-lookup"><span data-stu-id="3b20a-190">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b20a-191">превентпстнтоллбипасс</span><span class="sxs-lookup"><span data-stu-id="3b20a-191">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="3b20a-192">Да</span><span class="sxs-lookup"><span data-stu-id="3b20a-192">True</span></span></p></td>
<td><p><span data-ttu-id="3b20a-193">Да</span><span class="sxs-lookup"><span data-stu-id="3b20a-193">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="3b20a-194">Включение маршрутизации Location-Based в конфигурации маршрутизации</span><span class="sxs-lookup"><span data-stu-id="3b20a-194">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="3b20a-195">Наконец, глобально разрешите Location-Based маршрутизацию в конфигурацию маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3b20a-195">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="3b20a-196">Чтобы включить маршрутизацию Location-Based, используйте команду Windows PowerShell Lync Server с параметром New – Ксраутингконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="3b20a-196">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="3b20a-197">Дополнительные сведения см. в статье [Set – ксраутингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="3b20a-197">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b20a-198">Несмотря на то, что необходимо включить Location-Based маршрутизацию через глобальную конфигурацию, набор применяемых правил будет применяться только к сайтам, пользователям и магистральным линиям, для которых она настроена, как указано в этой документации.</span><span class="sxs-lookup"><span data-stu-id="3b20a-198">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b20a-199">См. также</span><span class="sxs-lookup"><span data-stu-id="3b20a-199">See Also</span></span>


[<span data-ttu-id="3b20a-200">Настройка маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b20a-200">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

