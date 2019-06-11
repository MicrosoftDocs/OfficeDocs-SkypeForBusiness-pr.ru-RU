---
title: 'Lync Server 2013: изменения, внесенные пользователем Grant-Кссетуппермиссион'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc63cf814f2bd901ab9753fe0f4501e7f44e2189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="a829e-102">Изменения, внесенные функцией Grant-Кссетуппермиссион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a829e-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a829e-103">_**Тема последнего изменения:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="a829e-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="a829e-104">Для делегирования настройки вы можете предоставить разрешения на доступ к универсальной группе Рткуниверсалсерверадминс для определенного подразделения Active Directory (OU), включив в него членов группы Рткуниверсалсерверадминс для установки Lync Server 2013 в указанном домен, не являющийся членом группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="a829e-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="a829e-105">Командлет **Grant-кссетуппермиссион** предоставляет разрешения на доступ к группе рткуниверсалсерверадминс на подразделение, как указано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="a829e-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="a829e-106">Разрешения, предоставленные объектам в подразделении</span><span class="sxs-lookup"><span data-stu-id="a829e-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a829e-107">Разрешения применяются к:</span><span class="sxs-lookup"><span data-stu-id="a829e-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="a829e-108">Предоставлены следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="a829e-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a829e-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a829e-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a829e-110">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="a829e-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a829e-111">Чтение передаваемые по себе</span><span class="sxs-lookup"><span data-stu-id="a829e-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="a829e-112">Вводный текст</span><span class="sxs-lookup"><span data-stu-id="a829e-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="a829e-113">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="a829e-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="a829e-114">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="a829e-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a829e-115">Дочерние объекты serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="a829e-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="a829e-116">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="a829e-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a829e-117">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="a829e-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="a829e-118">Разрешения на запись</span><span class="sxs-lookup"><span data-stu-id="a829e-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="a829e-119">Создание дочернего элемента</span><span class="sxs-lookup"><span data-stu-id="a829e-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="a829e-120">Удалить дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="a829e-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="a829e-121">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="a829e-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="a829e-122">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="a829e-123">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="a829e-124">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="a829e-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a829e-125">Дочерние объекты msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="a829e-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="a829e-126">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="a829e-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a829e-127">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="a829e-128">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="a829e-129">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="a829e-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a829e-130">Дочерние msRTCSIP — объекты-компоненты</span><span class="sxs-lookup"><span data-stu-id="a829e-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="a829e-131">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="a829e-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a829e-132">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="a829e-133">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="a829e-134">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="a829e-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a829e-135">Дочерние объекты msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="a829e-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="a829e-136">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="a829e-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a829e-137">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="a829e-138">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="a829e-139">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="a829e-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a829e-140">Дочерние объекты msRTCSIP-Медиатионсервер</span><span class="sxs-lookup"><span data-stu-id="a829e-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="a829e-141">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="a829e-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a829e-142">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="a829e-143">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="a829e-144">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="a829e-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a829e-145">Дочерние объекты msRTCSIP-Аппликатионсервер</span><span class="sxs-lookup"><span data-stu-id="a829e-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="a829e-146">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="a829e-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a829e-147">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="a829e-148">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="a829e-149">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="a829e-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a829e-150">Дочерние объекты msRTCSIP-Коннектионпоинт</span><span class="sxs-lookup"><span data-stu-id="a829e-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="a829e-151">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="a829e-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="a829e-152">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="a829e-153">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="a829e-154">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="a829e-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a829e-155">Дочерние объекты компьютера</span><span class="sxs-lookup"><span data-stu-id="a829e-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="a829e-156">Специальный доступ для serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="a829e-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="a829e-157">Создание дочерних объектов</span><span class="sxs-lookup"><span data-stu-id="a829e-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="a829e-158">Удаление дочерних объектов</span><span class="sxs-lookup"><span data-stu-id="a829e-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="a829e-159">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="a829e-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="a829e-160">Специальный доступ к общедоступным сведениям:</span><span class="sxs-lookup"><span data-stu-id="a829e-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="a829e-161">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="a829e-162">Особый доступ для DNS-имени узла:</span><span class="sxs-lookup"><span data-stu-id="a829e-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="a829e-163">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="a829e-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

