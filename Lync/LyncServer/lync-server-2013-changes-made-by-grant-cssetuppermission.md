---
title: 'Lync Server 2013: изменения, внесенные с помощью GRANT — CsSetupPermission'
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
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="1d250-102">Изменения, внесенные с помощью GRANT – CsSetupPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d250-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d250-103">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="1d250-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="1d250-104">Чтобы делегировать установку, можно предоставить разрешения универсальной группе RTCUniversalServerAdmins для определенного подразделения Active Directory (OU), разрешив членам группы RTCUniversalServerAdmins в этом подразделении установить Lync Server 2013 в заданном домен, не являющийся членом группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="1d250-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="1d250-105">Командлет **Grant-CsSetupPermission** предоставляет группе RTCUniversalServerAdmins разрешения на подразделение, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1d250-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="1d250-106">Разрешения. предоставляемые на объекты в подразделении</span><span class="sxs-lookup"><span data-stu-id="1d250-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d250-107">Разрешения применяются к</span><span class="sxs-lookup"><span data-stu-id="1d250-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="1d250-108">Предоставляемые разрешения</span><span class="sxs-lookup"><span data-stu-id="1d250-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d250-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1d250-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="1d250-110">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1d250-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d250-111">чтение в servicePrincipalName;</span><span class="sxs-lookup"><span data-stu-id="1d250-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="1d250-112">запись в servicePrincipalName;</span><span class="sxs-lookup"><span data-stu-id="1d250-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="1d250-113">удаление дерева;</span><span class="sxs-lookup"><span data-stu-id="1d250-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="1d250-114">репликацию изменений каталога.</span><span class="sxs-lookup"><span data-stu-id="1d250-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d250-115">Объектам-потомкам serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="1d250-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="1d250-116">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1d250-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d250-117">чтение;</span><span class="sxs-lookup"><span data-stu-id="1d250-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="1d250-118">запись;</span><span class="sxs-lookup"><span data-stu-id="1d250-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="1d250-119">создание дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="1d250-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="1d250-120">удаление дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="1d250-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="1d250-121">перечень содержимого;</span><span class="sxs-lookup"><span data-stu-id="1d250-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="1d250-122">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="1d250-123">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="1d250-124">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1d250-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d250-125">Объектам-потомкам msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="1d250-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="1d250-126">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1d250-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d250-127">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="1d250-128">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="1d250-129">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1d250-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d250-130">Объектам-потомкам msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="1d250-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="1d250-131">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1d250-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d250-132">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="1d250-133">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="1d250-134">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1d250-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d250-135">Объектам-потомкам msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="1d250-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="1d250-136">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1d250-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d250-137">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="1d250-138">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="1d250-139">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1d250-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d250-140">Объектам-потомкам msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="1d250-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="1d250-141">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1d250-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d250-142">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="1d250-143">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="1d250-144">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1d250-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d250-145">Объектам-потомкам msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="1d250-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="1d250-146">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1d250-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d250-147">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="1d250-148">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="1d250-149">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1d250-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d250-150">Объектам-потомкам msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="1d250-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="1d250-151">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="1d250-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d250-152">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="1d250-153">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="1d250-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="1d250-154">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1d250-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d250-155">Объектам-потомкам Computer</span><span class="sxs-lookup"><span data-stu-id="1d250-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="1d250-156">Особый доступ для serviceConnectionPoint на:</span><span class="sxs-lookup"><span data-stu-id="1d250-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d250-157">создание дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="1d250-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="1d250-158">удаление дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="1d250-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="1d250-159">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="1d250-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="1d250-160">Специальный доступ для общедоступных сведений на:</span><span class="sxs-lookup"><span data-stu-id="1d250-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d250-161">чтение свойства.</span><span class="sxs-lookup"><span data-stu-id="1d250-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="1d250-162">Специальный доступ для имени узла DNS на:</span><span class="sxs-lookup"><span data-stu-id="1d250-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d250-163">чтение свойства.</span><span class="sxs-lookup"><span data-stu-id="1d250-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

