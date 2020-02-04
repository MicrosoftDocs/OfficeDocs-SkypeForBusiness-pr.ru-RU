---
title: 'Lync Server 2013: изменения, внесенные пользователем Grant-Кссетуппермиссион'
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
ms.openlocfilehash: 9d82b896f1d6d1da1184bfa61d7352c9b4803a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="9adfe-102">Изменения, внесенные функцией Grant-Кссетуппермиссион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9adfe-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9adfe-103">_**Тема последнего изменения:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="9adfe-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="9adfe-104">Для делегирования настройки вы можете предоставить разрешения на доступ к универсальной группе Рткуниверсалсерверадминс для определенного подразделения Active Directory (OU), включив в него членов группы Рткуниверсалсерверадминс для установки Lync Server 2013 в указанном домен, не являющийся членом группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="9adfe-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="9adfe-105">Командлет **Grant-кссетуппермиссион** предоставляет разрешения на доступ к группе рткуниверсалсерверадминс на подразделение, как указано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="9adfe-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="9adfe-106">Разрешения, предоставленные объектам в подразделении</span><span class="sxs-lookup"><span data-stu-id="9adfe-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9adfe-107">Разрешения применяются к:</span><span class="sxs-lookup"><span data-stu-id="9adfe-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="9adfe-108">Предоставлены следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="9adfe-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9adfe-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9adfe-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="9adfe-110">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="9adfe-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adfe-111">Чтение передаваемые по себе</span><span class="sxs-lookup"><span data-stu-id="9adfe-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="9adfe-112">Вводный текст</span><span class="sxs-lookup"><span data-stu-id="9adfe-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="9adfe-113">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="9adfe-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="9adfe-114">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="9adfe-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9adfe-115">Дочерние объекты serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="9adfe-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="9adfe-116">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="9adfe-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adfe-117">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="9adfe-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="9adfe-118">Разрешения на запись</span><span class="sxs-lookup"><span data-stu-id="9adfe-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="9adfe-119">Создание дочернего элемента</span><span class="sxs-lookup"><span data-stu-id="9adfe-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="9adfe-120">Удалить дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="9adfe-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="9adfe-121">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="9adfe-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="9adfe-122">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-123">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-124">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="9adfe-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9adfe-125">Дочерние объекты msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="9adfe-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="9adfe-126">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="9adfe-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adfe-127">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-128">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-129">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="9adfe-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9adfe-130">Дочерние msRTCSIP — объекты-компоненты</span><span class="sxs-lookup"><span data-stu-id="9adfe-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="9adfe-131">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="9adfe-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adfe-132">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-133">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-134">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="9adfe-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9adfe-135">Дочерние объекты msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="9adfe-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="9adfe-136">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="9adfe-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adfe-137">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-138">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-139">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="9adfe-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9adfe-140">Дочерние объекты msRTCSIP-Медиатионсервер</span><span class="sxs-lookup"><span data-stu-id="9adfe-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="9adfe-141">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="9adfe-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adfe-142">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-143">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-144">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="9adfe-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9adfe-145">Дочерние объекты msRTCSIP-Аппликатионсервер</span><span class="sxs-lookup"><span data-stu-id="9adfe-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="9adfe-146">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="9adfe-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adfe-147">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-148">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-149">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="9adfe-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9adfe-150">Дочерние объекты msRTCSIP-Коннектионпоинт</span><span class="sxs-lookup"><span data-stu-id="9adfe-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="9adfe-151">Специальный доступ:</span><span class="sxs-lookup"><span data-stu-id="9adfe-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adfe-152">Запись свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-153">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="9adfe-154">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="9adfe-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9adfe-155">Дочерние объекты компьютера</span><span class="sxs-lookup"><span data-stu-id="9adfe-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="9adfe-156">Специальный доступ для serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="9adfe-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adfe-157">Создание дочерних объектов</span><span class="sxs-lookup"><span data-stu-id="9adfe-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="9adfe-158">Удаление дочерних объектов</span><span class="sxs-lookup"><span data-stu-id="9adfe-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="9adfe-159">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="9adfe-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="9adfe-160">Специальный доступ к общедоступным сведениям:</span><span class="sxs-lookup"><span data-stu-id="9adfe-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adfe-161">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="9adfe-162">Особый доступ для DNS-имени узла:</span><span class="sxs-lookup"><span data-stu-id="9adfe-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adfe-163">Чтение свойства</span><span class="sxs-lookup"><span data-stu-id="9adfe-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

