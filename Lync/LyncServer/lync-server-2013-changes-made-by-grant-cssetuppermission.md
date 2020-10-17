---
title: 'Lync Server 2013: изменения, внесенные Grant-CsSetupPermission'
description: 'Lync Server 2013: изменения, внесенные с помощью GRANT – CsSetupPermission.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543605"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="1733c-103">Изменения, внесенные Grant-CsSetupPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1733c-103">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1733c-104">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="1733c-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="1733c-105">Чтобы делегировать установку, можно предоставить разрешения универсальной группе RTCUniversalServerAdmins для определенного подразделения Active Directory (OU), разрешив членам группы RTCUniversalServerAdmins в этом подразделении установить Lync Server 2013 в указанном домене без участия в группе администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="1733c-105">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="1733c-106">Командлет **Grant-CsSetupPermission** предоставляет группе RTCUniversalServerAdmins разрешения на подразделение, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1733c-106">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="1733c-107">Разрешения. предоставляемые на объекты в подразделении</span><span class="sxs-lookup"><span data-stu-id="1733c-107">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1733c-108">Разрешения применяются к</span><span class="sxs-lookup"><span data-stu-id="1733c-108">Permissions apply to:</span></span></th>
<th><span data-ttu-id="1733c-109">Предоставляемые разрешения</span><span class="sxs-lookup"><span data-stu-id="1733c-109">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1733c-110">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1733c-110">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="1733c-111">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1733c-111">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1733c-112">чтение в servicePrincipalName;</span><span class="sxs-lookup"><span data-stu-id="1733c-112">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="1733c-113">запись в servicePrincipalName;</span><span class="sxs-lookup"><span data-stu-id="1733c-113">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="1733c-114">удаление дерева;</span><span class="sxs-lookup"><span data-stu-id="1733c-114">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="1733c-115">репликацию изменений каталога.</span><span class="sxs-lookup"><span data-stu-id="1733c-115">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1733c-116">Объектам-потомкам serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="1733c-116">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="1733c-117">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1733c-117">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1733c-118">чтение;</span><span class="sxs-lookup"><span data-stu-id="1733c-118">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="1733c-119">запись;</span><span class="sxs-lookup"><span data-stu-id="1733c-119">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="1733c-120">создание дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="1733c-120">Create child</span></span></p></li>
<li><p><span data-ttu-id="1733c-121">удаление дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="1733c-121">Delete child</span></span></p></li>
<li><p><span data-ttu-id="1733c-122">перечень содержимого;</span><span class="sxs-lookup"><span data-stu-id="1733c-122">List contents</span></span></p></li>
<li><p><span data-ttu-id="1733c-123">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-123">Write property</span></span></p></li>
<li><p><span data-ttu-id="1733c-124">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-124">Read property</span></span></p></li>
<li><p><span data-ttu-id="1733c-125">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1733c-125">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1733c-126">Объектам-потомкам msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="1733c-126">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="1733c-127">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1733c-127">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1733c-128">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-128">Write property</span></span></p></li>
<li><p><span data-ttu-id="1733c-129">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-129">Read property</span></span></p></li>
<li><p><span data-ttu-id="1733c-130">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1733c-130">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1733c-131">Объектам-потомкам msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="1733c-131">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="1733c-132">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1733c-132">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1733c-133">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-133">Write property</span></span></p></li>
<li><p><span data-ttu-id="1733c-134">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-134">Read property</span></span></p></li>
<li><p><span data-ttu-id="1733c-135">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1733c-135">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1733c-136">Объектам-потомкам msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="1733c-136">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="1733c-137">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1733c-137">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1733c-138">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-138">Write property</span></span></p></li>
<li><p><span data-ttu-id="1733c-139">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-139">Read property</span></span></p></li>
<li><p><span data-ttu-id="1733c-140">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1733c-140">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1733c-141">Объектам-потомкам msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="1733c-141">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="1733c-142">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1733c-142">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1733c-143">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-143">Write property</span></span></p></li>
<li><p><span data-ttu-id="1733c-144">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-144">Read property</span></span></p></li>
<li><p><span data-ttu-id="1733c-145">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1733c-145">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1733c-146">Объектам-потомкам msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="1733c-146">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="1733c-147">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1733c-147">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1733c-148">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-148">Write property</span></span></p></li>
<li><p><span data-ttu-id="1733c-149">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-149">Read property</span></span></p></li>
<li><p><span data-ttu-id="1733c-150">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1733c-150">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1733c-151">Объектам-потомкам msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="1733c-151">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="1733c-152">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1733c-152">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1733c-153">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-153">Write property</span></span></p></li>
<li><p><span data-ttu-id="1733c-154">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1733c-154">Read property</span></span></p></li>
<li><p><span data-ttu-id="1733c-155">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1733c-155">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1733c-156">Объектам-потомкам Computer</span><span class="sxs-lookup"><span data-stu-id="1733c-156">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="1733c-157">Особый доступ для serviceConnectionPoint на:</span><span class="sxs-lookup"><span data-stu-id="1733c-157">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="1733c-158">создание дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="1733c-158">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="1733c-159">удаление дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="1733c-159">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="1733c-160">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1733c-160">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="1733c-161">Специальный доступ для общедоступных сведений на:</span><span class="sxs-lookup"><span data-stu-id="1733c-161">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="1733c-162">чтение свойства.</span><span class="sxs-lookup"><span data-stu-id="1733c-162">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="1733c-163">Специальный доступ для имени узла DNS на:</span><span class="sxs-lookup"><span data-stu-id="1733c-163">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="1733c-164">чтение свойства.</span><span class="sxs-lookup"><span data-stu-id="1733c-164">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

