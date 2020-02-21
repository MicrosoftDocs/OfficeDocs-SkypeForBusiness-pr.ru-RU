---
title: 'Lync Server 2013: Включение маршрутизации на основе расположения'
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
ms.openlocfilehash: 5a66ced9530510ade4d91e8d76032a4260870530
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="7554d-102">Включение маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7554d-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7554d-103">_**Последнее изменение темы:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="7554d-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="7554d-104">После развертывания корпоративной голосовой связи и определенных областей сети, сайтов и подсетей можно включить маршрутизацию на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="7554d-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="7554d-105">Маршрутизация на основе расположения должна быть включена для следующих элементов корпоративной голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="7554d-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="7554d-106">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="7554d-106">Network sites</span></span>

  - <span data-ttu-id="7554d-107">Конфигурации магистрали</span><span class="sxs-lookup"><span data-stu-id="7554d-107">Trunk configurations</span></span>

  - <span data-ttu-id="7554d-108">Политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="7554d-108">Voice policies</span></span>

  - <span data-ttu-id="7554d-109">Конфигурация маршрутизации</span><span class="sxs-lookup"><span data-stu-id="7554d-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="7554d-110">Включение маршрутизации на основе расположения на сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="7554d-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="7554d-111">После развертывания корпоративной голосовой связи и настроенных сетевых сайтов можно приступать к настройке маршрутизации на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="7554d-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="7554d-112">Сначала необходимо создать политику маршрутизации голосовой связи, чтобы связать сетевой сайт с подходящими использованиями PSTN.</span><span class="sxs-lookup"><span data-stu-id="7554d-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="7554d-113">При назначении использования PSTN для политики маршрутизации голосовых вызовов обязательно используйте только использование PSTN, связанное с маршрутами голосовой связи, которые используют локальную сеть шлюза PSTN для сайта или шлюза PSTN, расположенного в регионе, в котором не требуются ограничения маршрутизации на основе расположения. Создайте политики маршрутизации голосовой связи с помощью команды Lync Server Windows PowerShell, панели управления New — CsVoiceRoutingPolicy или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7554d-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="7554d-114">Дополнительные сведения см. в статье [New – CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="7554d-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="7554d-115">В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют две политики маршрутизации голосовых вызовов и связанные с ними использование PSTN, определенные в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="7554d-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="7554d-116">Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="7554d-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="7554d-117">Политика маршрутизации голосовых вызовов 1</span><span class="sxs-lookup"><span data-stu-id="7554d-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="7554d-118">Политика маршрутизации голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="7554d-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7554d-119">Идентификатор политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="7554d-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="7554d-120">Политика маршрутизации голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="7554d-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="7554d-121">Политика маршрутизации голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="7554d-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7554d-122">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="7554d-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="7554d-123">Использование Нью Дели, использование УАТС Del, использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="7554d-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="7554d-124">Использование Хидерабад, использование Хид УАТС, использование УАТС del</span><span class="sxs-lookup"><span data-stu-id="7554d-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="7554d-125">Затем настройте маршрутизацию на основе расположения для соответствующих сетевых сайтов и свяжите с ними политики маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="7554d-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="7554d-126">Используйте команду Lync Server Windows PowerShell New-CsNetworkSite, чтобы включить маршрутизацию на основе расположения и связать политики маршрутизации голосовой связи с сетевыми сайтами, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="7554d-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="7554d-127">В этом примере в следующей таблице показана маршрутизация на основе расположения для двух различных сетевых сайтов, Нью Дели и Хидерабад, определенных в этом сценарии с помощью Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7554d-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="7554d-128">Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="7554d-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="7554d-129">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="7554d-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="7554d-130">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="7554d-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7554d-131">Имя сайта</span><span class="sxs-lookup"><span data-stu-id="7554d-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="7554d-132">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="7554d-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="7554d-133">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="7554d-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7554d-134">енаблелокатионбаседраутинг</span><span class="sxs-lookup"><span data-stu-id="7554d-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="7554d-135">Да</span><span class="sxs-lookup"><span data-stu-id="7554d-135">True</span></span></p></td>
<td><p><span data-ttu-id="7554d-136">Да</span><span class="sxs-lookup"><span data-stu-id="7554d-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7554d-137">Политика маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="7554d-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="7554d-138">Политика маршрутизации голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="7554d-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="7554d-139">Политика маршрутизации голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="7554d-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7554d-140">Подсети</span><span class="sxs-lookup"><span data-stu-id="7554d-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="7554d-141">Подсеть 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="7554d-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="7554d-142">Подсеть 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="7554d-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="7554d-143">Включение маршрутизации на основе расположения в магистрали</span><span class="sxs-lookup"><span data-stu-id="7554d-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="7554d-144">Прежде чем можно будет включить конфигурацию магистрали для маршрутизации на основе расположения, необходимо создать конфигурацию магистрали для каждой магистрали или каждого сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="7554d-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="7554d-145">Чтобы создать конфигурацию магистрали, используйте команду Windows PowerShell Lync Server с параметром New – CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7554d-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="7554d-146">Если несколько магистральных линий связаны с заданной системой (то есть шлюз или УАТС), необходимо изменить каждую конфигурацию магистрали, чтобы включить ограничения маршрутизации на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="7554d-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="7554d-147">Дополнительные сведения см. в статье [New – CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="7554d-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="7554d-148">В этом примере приведенные ниже команды Windows PowerShell иллюстрируют создание одной конфигурации магистрали для каждой магистрали в развертывании, определенном в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="7554d-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="7554d-149">После настройки магистрали для каждой магистрали можно использовать командную консоль Windows PowerShell Lync Server, Set-CsTrunkConfiguration, чтобы включить маршрутизацию на основе расположения для каналов, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="7554d-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="7554d-150">Включите маршрутизацию на основе расположения в магистрали, которые направляют вызовы на шлюзы PSTN, которые направляют вызовы в PSTN, и связывают сетевой сайт, на котором расположен шлюз.</span><span class="sxs-lookup"><span data-stu-id="7554d-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="7554d-151">Дополнительные сведения см. в статье [New – CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="7554d-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="7554d-152">В этом примере маршрутизация на основе расположения включена для каждой магистрали, связанной с шлюзами PSTN в Нью Дели и Хидерабад:</span><span class="sxs-lookup"><span data-stu-id="7554d-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="7554d-153">Не включайте маршрутизацию на основе расположения для магистральных каналов, которые не направляют звонки в PSTN; Тем не менее, по-прежнему необходимо связать магистраль с сетевым сайтом, на котором система расположена в качестве ограничений маршрутизации на основе расположения, для звонков по протоколу PSTN, подключенных к конечным точкам, подключенным через эту магистраль.</span><span class="sxs-lookup"><span data-stu-id="7554d-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="7554d-154">В этом примере маршрутизация на основе расположения не включена для каждой магистрали, связанной с системами УАТС в Нью Дели и Хидерабад:</span><span class="sxs-lookup"><span data-stu-id="7554d-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="7554d-155">Конечные точки, которые подключены к системам, которые не направляют звонки на PSTN (например, УАТС), будут иметь аналогичные ограничения, как конечные точки Lync для пользователей, для которых включена маршрутизация на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="7554d-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="7554d-156">Это означает, что эти пользователи смогут размещать и принимать звонки пользователю Lync независимо от расположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="7554d-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="7554d-157">Кроме того, они могут выполнять прием вызовов в другие системы, которые не направляют вызовы в сеть PSTN (то есть конечная точка, подключенная к другой УАТС) независимо от того, к какому сетевому сайту относится система.</span><span class="sxs-lookup"><span data-stu-id="7554d-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="7554d-158">Все входящие звонки, исходящие звонки, передачи звонков и переадресация звонков, связанные с конечными точками PSTN, будут применяться к принудительной маршрутизации на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="7554d-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="7554d-159">Такие вызовы должны использовать только шлюзы PSTN, которые определены как локальные для таких систем.</span><span class="sxs-lookup"><span data-stu-id="7554d-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="7554d-160">В следующей таблице показана конфигурация магистрали четырех магистральных линий на двух различных сетевых сайтах: два подключения к шлюзам PSTN и два подключения к системам УАТС.</span><span class="sxs-lookup"><span data-stu-id="7554d-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7554d-161">Имя</span><span class="sxs-lookup"><span data-stu-id="7554d-161">Name</span></span></th>
<th><span data-ttu-id="7554d-162">енаблелокатионрестриктион</span><span class="sxs-lookup"><span data-stu-id="7554d-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="7554d-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="7554d-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7554d-164">PstnGateway: магистраль 1 DEL — GW</span><span class="sxs-lookup"><span data-stu-id="7554d-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="7554d-165">Верно</span><span class="sxs-lookup"><span data-stu-id="7554d-165">True</span></span></p></td>
<td><p><span data-ttu-id="7554d-166">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="7554d-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7554d-167">PstnGateway: магистраль 2 ХИД — GW</span><span class="sxs-lookup"><span data-stu-id="7554d-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="7554d-168">Верно</span><span class="sxs-lookup"><span data-stu-id="7554d-168">True</span></span></p></td>
<td><p><span data-ttu-id="7554d-169">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="7554d-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7554d-170">PstnGateway: магистраль 3 DEL — УАТС</span><span class="sxs-lookup"><span data-stu-id="7554d-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="7554d-171">False</span><span class="sxs-lookup"><span data-stu-id="7554d-171">False</span></span></p></td>
<td><p><span data-ttu-id="7554d-172">Сайт 1 (Нью Дели)</span><span class="sxs-lookup"><span data-stu-id="7554d-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7554d-173">PstnGateway: магистраль 4 ХИД — УАТС</span><span class="sxs-lookup"><span data-stu-id="7554d-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="7554d-174">False</span><span class="sxs-lookup"><span data-stu-id="7554d-174">False</span></span></p></td>
<td><p><span data-ttu-id="7554d-175">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="7554d-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="7554d-176">Включение маршрутизации на основе расположения в политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="7554d-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="7554d-177">Чтобы принудительно применить маршрутизацию на основе расположения для определенных пользователей, настройте политику голосовой связи для этих пользователей, чтобы предотвратить обход бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="7554d-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="7554d-178">Используйте командную консоль Lync Server Windows PowerShell New — CsVoicePolicy, чтобы создать новую политику голосовой связи или Set — CsVoicePolicy, если используется существующая политика, чтобы включить маршрутизацию на основе расположения, предотвращая обход бесплатных звонков по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="7554d-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="7554d-179">Дополнительные сведения см. в статье [New – CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="7554d-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="7554d-180">В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют включение защиты от бесплатных бесплатных политик Нью Дели и Хидерабад голосовой связи, определенных в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="7554d-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="7554d-181">Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="7554d-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="7554d-182">Политика голосовой связи 1</span><span class="sxs-lookup"><span data-stu-id="7554d-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="7554d-183">Политика голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="7554d-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7554d-184">Идентификатор политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="7554d-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="7554d-185">Политика голосовой связи Нью Дели</span><span class="sxs-lookup"><span data-stu-id="7554d-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="7554d-186">Политика голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="7554d-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7554d-187">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="7554d-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="7554d-188">Использование Нью Дели, использование УАТС Del, использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="7554d-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="7554d-189">Использование Хидерабад, использование Хид УАТС, использование УАТС del</span><span class="sxs-lookup"><span data-stu-id="7554d-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7554d-190">превентпстнтоллбипасс</span><span class="sxs-lookup"><span data-stu-id="7554d-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="7554d-191">Да</span><span class="sxs-lookup"><span data-stu-id="7554d-191">True</span></span></p></td>
<td><p><span data-ttu-id="7554d-192">Да</span><span class="sxs-lookup"><span data-stu-id="7554d-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="7554d-193">Включение маршрутизации на основе расположения в конфигурации маршрутизации</span><span class="sxs-lookup"><span data-stu-id="7554d-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="7554d-194">Наконец, глобально включите маршрутизацию на основе расположения в конфигурацию маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="7554d-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="7554d-195">Используйте команду Lync Server Windows PowerShell New – Ксраутингконфигуратион, чтобы включить маршрутизацию на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="7554d-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="7554d-196">Дополнительные сведения см. в статье [Set – ксраутингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="7554d-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7554d-197">Если маршрутизация на основе расположения должна быть включена через глобальную конфигурацию, набор применяемых правил будет применяться только к сайтам, пользователям и магистральным линиям, для которых она настроена, как указано в этой документации.</span><span class="sxs-lookup"><span data-stu-id="7554d-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7554d-198">См. также</span><span class="sxs-lookup"><span data-stu-id="7554d-198">See Also</span></span>


[<span data-ttu-id="7554d-199">Настройка маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7554d-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

