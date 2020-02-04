---
title: 'Lync Server 2013: Включение маршрутизации на основе местоположения'
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
ms.openlocfilehash: e21e1a285fa5b2129d4d0ed0b5d75e8dcee42f2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="04be6-102">Включение маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04be6-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04be6-103">_**Тема последнего изменения:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="04be6-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="04be6-104">После развернутой голосовой связи и определения регионов сети, сайтов и подсетей вы можете включить маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="04be6-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="04be6-105">Для следующих корпоративных элементов голосовой связи должна быть включена маршрутизация на основе местоположения:</span><span class="sxs-lookup"><span data-stu-id="04be6-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="04be6-106">Сетевые сайты</span><span class="sxs-lookup"><span data-stu-id="04be6-106">Network sites</span></span>

  - <span data-ttu-id="04be6-107">Конфигурации магистрали</span><span class="sxs-lookup"><span data-stu-id="04be6-107">Trunk configurations</span></span>

  - <span data-ttu-id="04be6-108">Политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="04be6-108">Voice policies</span></span>

  - <span data-ttu-id="04be6-109">Настройка маршрутизации</span><span class="sxs-lookup"><span data-stu-id="04be6-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="04be6-110">Включение маршрутизации на основе местоположения на сайты сети</span><span class="sxs-lookup"><span data-stu-id="04be6-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="04be6-111">После того как вы развернули корпоративную голосовую почту и настроили сетевые сайты, вы можете настроить маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="04be6-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="04be6-112">Сначала необходимо создать политику маршрутизации голосовой связи для связи сайта сети с соответствующими использованием PSTN.</span><span class="sxs-lookup"><span data-stu-id="04be6-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="04be6-113">Если вы назначаете использование PSTN для политики голосовой маршрутизации, убедитесь, что используются только использование PSTN, связанное с голосовыми маршрутами, которые используют локальные шлюзы PSTN для сайта, или шлюз PSTN, который находится в регионе, где не требуются ограничения на маршрутизацию на основе местоположения. С помощью команды Lync Server Windows PowerShell, панели управления New-Ксвоицераутингполици или Lync Server можно создавать политики голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="04be6-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="04be6-114">Дополнительные сведения см. в разделе [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="04be6-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="04be6-115">В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют две политики маршрутизации голосовой связи и использование PSTN, описанных в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="04be6-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="04be6-116">В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="04be6-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="04be6-117">Политика маршрутизации голосовой связи 1</span><span class="sxs-lookup"><span data-stu-id="04be6-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="04be6-118">Политика маршрутизации голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="04be6-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04be6-119">Идентификатор политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="04be6-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="04be6-120">Политика маршрутизации голосовой связи Делхи</span><span class="sxs-lookup"><span data-stu-id="04be6-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="04be6-121">Политика маршрутизации голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="04be6-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04be6-122">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="04be6-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="04be6-123">Использование Делхи, использование АТС DELETE, использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="04be6-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="04be6-124">Использование Хидерабад, Хид УАТС, использование АТС Delete</span><span class="sxs-lookup"><span data-stu-id="04be6-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="04be6-125">Затем настройте маршрутизацию на основе местоположения для соответствующих сайтов сети и свяжите с ними политики маршрутизации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="04be6-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="04be6-126">Используйте команду Lync Server Windows PowerShell New-Кснетворксите, чтобы включить маршрутизацию на основе местоположения и связать политики голосовой маршрутизации с сетевыми сайтами, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="04be6-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="04be6-127">В приведенной ниже таблице показана маршрутизация на основе местоположения для двух различных сайтов сети, Делхи и Хидерабад, определенных в этом сценарии, с помощью Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04be6-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="04be6-128">В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="04be6-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="04be6-129">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="04be6-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="04be6-130">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="04be6-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04be6-131">Имя сайта</span><span class="sxs-lookup"><span data-stu-id="04be6-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="04be6-132">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="04be6-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="04be6-133">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="04be6-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04be6-134">енаблелокатионбаседраутинг</span><span class="sxs-lookup"><span data-stu-id="04be6-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="04be6-135">Верно</span><span class="sxs-lookup"><span data-stu-id="04be6-135">True</span></span></p></td>
<td><p><span data-ttu-id="04be6-136">Верно</span><span class="sxs-lookup"><span data-stu-id="04be6-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04be6-137">Политика маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="04be6-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="04be6-138">Политика маршрутизации голосовой связи Делхи</span><span class="sxs-lookup"><span data-stu-id="04be6-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="04be6-139">Политика маршрутизации голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="04be6-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04be6-140">Подсети</span><span class="sxs-lookup"><span data-stu-id="04be6-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="04be6-141">Подсеть 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="04be6-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="04be6-142">Подсеть 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="04be6-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="04be6-143">Включение маршрутизации на основе местоположения в магистральные магистрали</span><span class="sxs-lookup"><span data-stu-id="04be6-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="04be6-144">Прежде чем можно будет включить конфигурацию магистральной конфигурации для маршрутизации на основе расположения, необходимо создать конфигурацию магистрали для каждой магистрали или каждого из сайтов сети.</span><span class="sxs-lookup"><span data-stu-id="04be6-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="04be6-145">Используйте команду Lync Server Windows PowerShell New-CsTrunkConfiguration для создания конфигурации канала магистрали.</span><span class="sxs-lookup"><span data-stu-id="04be6-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="04be6-146">Если несколько магистральных каналов связаны с определенной системой (например, Gateway или УАТС), каждую из них нужно изменить, чтобы включить ограничения маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="04be6-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="04be6-147">Дополнительные сведения можно найти в разделе [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="04be6-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="04be6-148">В этом примере следующие команды Windows PowerShell иллюстрируют создание одной конфигурации магистрали для каждой магистрали в развертывании, определенном в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="04be6-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="04be6-149">После настройки магистральной конфигурации для каждой магистрали вы можете использовать команду Lync Server Windows PowerShell Set-CsTrunkConfiguration, чтобы включить маршрутизацию на основе местоположения для каналов, которые должны применять ограничения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="04be6-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="04be6-150">Включите маршрутизацию с учетом местоположения на магистральы, которые направляют звонки на шлюзы PSTN, которые направляют звонки в КТСОП и связывают сетевой сайт, на котором расположен шлюз.</span><span class="sxs-lookup"><span data-stu-id="04be6-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="04be6-151">Дополнительные сведения можно найти в разделе [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="04be6-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="04be6-152">В этом примере для каждой магистрали, связанной с шлюзами PSTN в Делхи и Хидерабад, включена маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="04be6-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="04be6-153">Не включайте маршрутизацию на основе местоположения для каналов связи, которые не направляют звонки в КТСОП. Однако вы по-прежнему обязаны привязать магистраль к сетевому сайту, на котором система находится в качестве ограничений маршрутизации на основе местоположения, для звонков по КОММУТИРУЕМой линии, подсоединенной с помощью этой магистрали, должны быть принудительно использовать ограничения на расположение.</span><span class="sxs-lookup"><span data-stu-id="04be6-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="04be6-154">В этом примере маршрутизация на основе местоположения не включена для каждой магистрали, связанной с системами УАТС в Делхи и Хидерабад:</span><span class="sxs-lookup"><span data-stu-id="04be6-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="04be6-155">Конечные точки, которые подключены к системам, не накладываемым на протокол PSTN (например, УАТС), имеют аналогичные ограничения в качестве конечных точек Lync для пользователей, для которых включена маршрутизация на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="04be6-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="04be6-156">Это означает, что эти пользователи смогут размещать и принимать звонки на пользователей Lync, независимо от местонахождения пользователя.</span><span class="sxs-lookup"><span data-stu-id="04be6-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="04be6-157">Кроме того, они смогут принимать звонки в другие системы и из них, которые не направляют звонки в сеть PSTN (например, конечную точку, подключенную к другой УАТС) независимо от того, с какой сетевой страницы связана система.</span><span class="sxs-lookup"><span data-stu-id="04be6-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="04be6-158">Все входящие звонки, звонки и переадресация звонков, связанные с конечными точками PSTN, будут применяться для маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="04be6-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="04be6-159">Такие звонки должны использовать только шлюзы PSTN, определенные как локальные для таких систем.</span><span class="sxs-lookup"><span data-stu-id="04be6-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="04be6-160">В приведенной ниже таблице показана конфигурация магистрали с четырьмя магистральами на двух разных сетевых сайтах: два соединения с шлюзами PSTN и двумя подключенными к системам АТС.</span><span class="sxs-lookup"><span data-stu-id="04be6-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04be6-161">Имя</span><span class="sxs-lookup"><span data-stu-id="04be6-161">Name</span></span></th>
<th><span data-ttu-id="04be6-162">енаблелокатионрестриктион</span><span class="sxs-lookup"><span data-stu-id="04be6-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="04be6-163">нетворкситеид</span><span class="sxs-lookup"><span data-stu-id="04be6-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04be6-164">Пстнгатевай: магистраль 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="04be6-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="04be6-165">Верно</span><span class="sxs-lookup"><span data-stu-id="04be6-165">True</span></span></p></td>
<td><p><span data-ttu-id="04be6-166">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="04be6-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04be6-167">Пстнгатевай: магистраль 2 ХИД-GW</span><span class="sxs-lookup"><span data-stu-id="04be6-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="04be6-168">Верно</span><span class="sxs-lookup"><span data-stu-id="04be6-168">True</span></span></p></td>
<td><p><span data-ttu-id="04be6-169">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="04be6-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04be6-170">Пстнгатевай: магистраль 3 DEL-УАТС</span><span class="sxs-lookup"><span data-stu-id="04be6-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="04be6-171">False</span><span class="sxs-lookup"><span data-stu-id="04be6-171">False</span></span></p></td>
<td><p><span data-ttu-id="04be6-172">Сайт 1 (Делхи)</span><span class="sxs-lookup"><span data-stu-id="04be6-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04be6-173">Пстнгатевай: ХИД-УАТС (магистральная линия 4)</span><span class="sxs-lookup"><span data-stu-id="04be6-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="04be6-174">False</span><span class="sxs-lookup"><span data-stu-id="04be6-174">False</span></span></p></td>
<td><p><span data-ttu-id="04be6-175">Сайт 2 (Хидерабад)</span><span class="sxs-lookup"><span data-stu-id="04be6-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="04be6-176">Включение маршрутизации на основе местоположения в политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="04be6-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="04be6-177">Чтобы обеспечить возможность маршрутизации с учетом расположения определенным пользователям, настройте политику голосовой связи пользователей, чтобы отключить бесплатный звонок.</span><span class="sxs-lookup"><span data-stu-id="04be6-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="04be6-178">Используйте команду Lync Server Windows PowerShell New-Ксвоицеполици, чтобы создать новую политику голосовой связи или Set-Ксвоицеполици, при использовании существующей политики для включения маршрутизации на основе местоположения, запретив бесплатный звонок по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="04be6-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="04be6-179">Дополнительные сведения можно найти в разделе [New-ксвоицеполици](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="04be6-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="04be6-180">В этом примере приведенная ниже таблица и команды Windows PowerShell иллюстрируют использование политик голосовой связи по Делхи и Хидерабад, описанных в этом сценарии, в целях предотвращения бесплатной поддержки PSTN.</span><span class="sxs-lookup"><span data-stu-id="04be6-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="04be6-181">В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="04be6-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="04be6-182">Политика голосовой связи 1</span><span class="sxs-lookup"><span data-stu-id="04be6-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="04be6-183">Политика голосовой связи 2</span><span class="sxs-lookup"><span data-stu-id="04be6-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04be6-184">Идентификатор политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="04be6-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="04be6-185">Политика голосовой связи Делхи</span><span class="sxs-lookup"><span data-stu-id="04be6-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="04be6-186">Политика голосовой связи Хидерабад</span><span class="sxs-lookup"><span data-stu-id="04be6-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04be6-187">Использование PSTN</span><span class="sxs-lookup"><span data-stu-id="04be6-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="04be6-188">Использование Делхи, использование АТС DELETE, использование Хид УАТС</span><span class="sxs-lookup"><span data-stu-id="04be6-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="04be6-189">Использование Хидерабад, Хид УАТС, использование АТС Delete</span><span class="sxs-lookup"><span data-stu-id="04be6-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04be6-190">превентпстнтоллбипасс</span><span class="sxs-lookup"><span data-stu-id="04be6-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="04be6-191">Верно</span><span class="sxs-lookup"><span data-stu-id="04be6-191">True</span></span></p></td>
<td><p><span data-ttu-id="04be6-192">Верно</span><span class="sxs-lookup"><span data-stu-id="04be6-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="04be6-193">Включение маршрутизации на основе местоположения в конфигурации маршрутизации</span><span class="sxs-lookup"><span data-stu-id="04be6-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="04be6-194">Наконец, глобально включите маршрутизацию на основе местоположения в конфигурацию маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="04be6-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="04be6-195">Используйте команду Lync Server Windows PowerShell New-Ксраутингконфигуратион, чтобы включить маршрутизацию на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="04be6-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="04be6-196">Дополнительные сведения можно найти в разделе [Set-ксраутингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="04be6-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04be6-197">Если маршрутизация на основе расположения должна быть включена через глобальную конфигурацию, набор применяемых правил будет применяться только для сайтов, пользователей и магистральных каналов, для которых она настроена, как указано в этой документации.</span><span class="sxs-lookup"><span data-stu-id="04be6-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="04be6-198">См. также</span><span class="sxs-lookup"><span data-stu-id="04be6-198">See Also</span></span>


[<span data-ttu-id="04be6-199">Настройка маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04be6-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

