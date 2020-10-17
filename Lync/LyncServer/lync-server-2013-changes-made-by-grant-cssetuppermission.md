---
title: 'Lync Server 2013: изменения, внесенные Grant-CsSetupPermission'
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
ms.openlocfilehash: 8ec13a23daf0f3dae47ae0ce0dc630e64c596e7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529416"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="ab662-102">Изменения, внесенные Grant-CsSetupPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab662-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab662-103">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="ab662-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="ab662-104">Чтобы делегировать установку, можно предоставить разрешения универсальной группе RTCUniversalServerAdmins для определенного подразделения Active Directory (OU), разрешив членам группы RTCUniversalServerAdmins в этом подразделении установить Lync Server 2013 в указанном домене без участия в группе администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="ab662-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="ab662-105">Командлет **Grant-CsSetupPermission** предоставляет группе RTCUniversalServerAdmins разрешения на подразделение, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="ab662-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="ab662-106">Разрешения. предоставляемые на объекты в подразделении</span><span class="sxs-lookup"><span data-stu-id="ab662-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab662-107">Разрешения применяются к</span><span class="sxs-lookup"><span data-stu-id="ab662-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="ab662-108">Предоставляемые разрешения</span><span class="sxs-lookup"><span data-stu-id="ab662-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab662-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ab662-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ab662-110">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="ab662-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab662-111">чтение в servicePrincipalName;</span><span class="sxs-lookup"><span data-stu-id="ab662-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="ab662-112">запись в servicePrincipalName;</span><span class="sxs-lookup"><span data-stu-id="ab662-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="ab662-113">удаление дерева;</span><span class="sxs-lookup"><span data-stu-id="ab662-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="ab662-114">репликацию изменений каталога.</span><span class="sxs-lookup"><span data-stu-id="ab662-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab662-115">Объектам-потомкам serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="ab662-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="ab662-116">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="ab662-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab662-117">чтение;</span><span class="sxs-lookup"><span data-stu-id="ab662-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="ab662-118">запись;</span><span class="sxs-lookup"><span data-stu-id="ab662-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="ab662-119">создание дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="ab662-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="ab662-120">удаление дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="ab662-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="ab662-121">перечень содержимого;</span><span class="sxs-lookup"><span data-stu-id="ab662-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="ab662-122">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="ab662-123">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="ab662-124">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="ab662-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab662-125">Объектам-потомкам msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="ab662-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="ab662-126">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="ab662-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab662-127">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="ab662-128">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="ab662-129">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="ab662-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab662-130">Объектам-потомкам msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="ab662-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="ab662-131">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="ab662-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab662-132">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="ab662-133">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="ab662-134">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="ab662-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab662-135">Объектам-потомкам msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="ab662-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="ab662-136">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="ab662-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab662-137">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="ab662-138">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="ab662-139">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="ab662-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab662-140">Объектам-потомкам msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="ab662-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="ab662-141">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="ab662-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab662-142">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="ab662-143">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="ab662-144">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="ab662-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab662-145">Объектам-потомкам msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="ab662-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="ab662-146">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="ab662-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab662-147">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="ab662-148">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="ab662-149">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="ab662-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab662-150">Объектам-потомкам msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="ab662-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="ab662-151">Особый доступ на:</span><span class="sxs-lookup"><span data-stu-id="ab662-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab662-152">запись свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="ab662-153">чтение свойства;</span><span class="sxs-lookup"><span data-stu-id="ab662-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="ab662-154">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="ab662-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab662-155">Объектам-потомкам Computer</span><span class="sxs-lookup"><span data-stu-id="ab662-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="ab662-156">Особый доступ для serviceConnectionPoint на:</span><span class="sxs-lookup"><span data-stu-id="ab662-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab662-157">создание дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="ab662-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="ab662-158">удаление дочерних объектов;</span><span class="sxs-lookup"><span data-stu-id="ab662-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="ab662-159">удаление дерева.</span><span class="sxs-lookup"><span data-stu-id="ab662-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="ab662-160">Специальный доступ для общедоступных сведений на:</span><span class="sxs-lookup"><span data-stu-id="ab662-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab662-161">чтение свойства.</span><span class="sxs-lookup"><span data-stu-id="ab662-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="ab662-162">Специальный доступ для имени узла DNS на:</span><span class="sxs-lookup"><span data-stu-id="ab662-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab662-163">чтение свойства.</span><span class="sxs-lookup"><span data-stu-id="ab662-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

