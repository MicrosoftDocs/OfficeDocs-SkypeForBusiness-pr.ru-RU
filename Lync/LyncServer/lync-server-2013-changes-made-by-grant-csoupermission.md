---
title: 'Lync Server 2013: изменения, внесенные Grant-CsOUPermission'
description: 'Lync Server 2013: изменения, внесенные с помощью Grant – CsOUPermission.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543615"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="45ec5-103">Изменения, внесенные Grant-CsOUPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45ec5-103">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45ec5-104">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="45ec5-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="45ec5-105">Чтобы делегировать администрирование Lync Server 2013, можно добавить разрешения для указанных подразделений, чтобы участники универсальных групп RTC, созданные при подготовке леса, могли получать доступ к подразделениям, не открывая группу "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="45ec5-105">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="45ec5-106">Командлет **Grant-CsOuPermission** предоставляет разрешения объектам в указанном подразделении, как указано в следующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="45ec5-106">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="45ec5-107">Предоставление разрешений для объектов-пользователей</span><span class="sxs-lookup"><span data-stu-id="45ec5-107">Granting Permission for User Objects</span></span>

<span data-ttu-id="45ec5-108">При запуске командлета **Grant-CsOuPermission** для объектов-пользователей в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="45ec5-108">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="45ec5-109">Разрешения, предоставленные объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="45ec5-109">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45ec5-110">Группа</span><span class="sxs-lookup"><span data-stu-id="45ec5-110">Group</span></span></th>
<th><span data-ttu-id="45ec5-111">Разрешение</span><span class="sxs-lookup"><span data-stu-id="45ec5-111">Permission</span></span></th>
<th><span data-ttu-id="45ec5-112">Применимо к</span><span class="sxs-lookup"><span data-stu-id="45ec5-112">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-113">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="45ec5-113">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="45ec5-114">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="45ec5-114">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="45ec5-115">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-115">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ec5-116">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-116">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-117">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45ec5-117">List contents</span></span></p>
<p><span data-ttu-id="45ec5-118">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45ec5-118">Read all properties</span></span></p>
<p><span data-ttu-id="45ec5-119">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45ec5-119">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-120">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-120">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-121">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-121">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-122">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45ec5-122">List contents</span></span></p>
<p><span data-ttu-id="45ec5-123">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45ec5-123">Read all properties</span></span></p>
<p><span data-ttu-id="45ec5-124">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45ec5-124">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-125">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-125">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ec5-126">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-126">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-127">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-127">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-128">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-128">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-129">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-129">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-130">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-130">Read Public-Information</span></span></p>
<p><span data-ttu-id="45ec5-131">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-131">Read General-Information</span></span></p>
<p><span data-ttu-id="45ec5-132">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="45ec5-132">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-133">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="45ec5-133">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45ec5-134">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45ec5-135">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-135">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-136">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="45ec5-136">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="45ec5-137">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-137">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-138">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-138">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-139">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="45ec5-139">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="45ec5-140">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="45ec5-140">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="45ec5-141">Предоставление разрешений для объектов-компьютеров</span><span class="sxs-lookup"><span data-stu-id="45ec5-141">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="45ec5-142">При запуске командлета **Grant-CsOuPermission** для объектов-компьютеров в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="45ec5-142">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="45ec5-143">Разрешения, предоставленные объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="45ec5-143">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45ec5-144">Группа</span><span class="sxs-lookup"><span data-stu-id="45ec5-144">Group</span></span></th>
<th><span data-ttu-id="45ec5-145">Разрешение</span><span class="sxs-lookup"><span data-stu-id="45ec5-145">Permission</span></span></th>
<th><span data-ttu-id="45ec5-146">Применимо к</span><span class="sxs-lookup"><span data-stu-id="45ec5-146">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-147">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="45ec5-147">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="45ec5-148">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="45ec5-148">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="45ec5-149">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-149">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ec5-150">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-150">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-151">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45ec5-151">List contents</span></span></p>
<p><span data-ttu-id="45ec5-152">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45ec5-152">Read all properties</span></span></p>
<p><span data-ttu-id="45ec5-153">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45ec5-153">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-154">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-154">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-155">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-155">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-156">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45ec5-156">List contents</span></span></p>
<p><span data-ttu-id="45ec5-157">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45ec5-157">Read all properties</span></span></p>
<p><span data-ttu-id="45ec5-158">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45ec5-158">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-159">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-159">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ec5-160">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-160">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-161">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-161">Read Public-Information</span></span></p>
<p><span data-ttu-id="45ec5-162">Чтение Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="45ec5-162">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="45ec5-163">К дочерним объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="45ec5-163">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-164">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45ec5-164">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45ec5-165">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-165">Read Public-Information</span></span></p>
<p><span data-ttu-id="45ec5-166">Чтение Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="45ec5-166">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="45ec5-167">К дочерним объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="45ec5-167">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="45ec5-168">Предоставление разрешений для контактных объектов  или объектов AppContact</span><span class="sxs-lookup"><span data-stu-id="45ec5-168">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="45ec5-169">При запуске командлета **Grant-CsOuPermission** для контактных объектов и объектов AppContact в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="45ec5-169">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="45ec5-170">Разрешения, предоставленные контактным объектам и объектам AppContact</span><span class="sxs-lookup"><span data-stu-id="45ec5-170">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45ec5-171">Группа</span><span class="sxs-lookup"><span data-stu-id="45ec5-171">Group</span></span></th>
<th><span data-ttu-id="45ec5-172">Разрешение</span><span class="sxs-lookup"><span data-stu-id="45ec5-172">Permission</span></span></th>
<th><span data-ttu-id="45ec5-173">Применимо к</span><span class="sxs-lookup"><span data-stu-id="45ec5-173">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-174">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="45ec5-174">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="45ec5-175">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="45ec5-175">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="45ec5-176">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-176">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ec5-177">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-177">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-178">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45ec5-178">List contents</span></span></p>
<p><span data-ttu-id="45ec5-179">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45ec5-179">Read all properties</span></span></p>
<p><span data-ttu-id="45ec5-180">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45ec5-180">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-181">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-181">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-182">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-182">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-183">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45ec5-183">List contents</span></span></p>
<p><span data-ttu-id="45ec5-184">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45ec5-184">Read all properties</span></span></p>
<p><span data-ttu-id="45ec5-185">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45ec5-185">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-186">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-186">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ec5-187">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-187">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-188">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-188">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-189">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-189">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-190">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-190">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-191">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-191">Read Public-Information</span></span></p>
<p><span data-ttu-id="45ec5-192">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-192">Read General-Information</span></span></p>
<p><span data-ttu-id="45ec5-193">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-193">Read Personal-Information</span></span></p>
<p><span data-ttu-id="45ec5-194">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="45ec5-194">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-195">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="45ec5-195">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-196">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45ec5-196">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45ec5-197">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-197">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-198">Запись otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="45ec5-198">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="45ec5-199">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="45ec5-199">Write displayName</span></span></p>
<p><span data-ttu-id="45ec5-200">Запись description</span><span class="sxs-lookup"><span data-stu-id="45ec5-200">Write description</span></span></p>
<p><span data-ttu-id="45ec5-201">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="45ec5-201">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="45ec5-202">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="45ec5-202">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="45ec5-203">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-203">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-204">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-204">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-205">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="45ec5-205">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="45ec5-206">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="45ec5-206">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="45ec5-207">Предоставление разрешений для объектов-устройств</span><span class="sxs-lookup"><span data-stu-id="45ec5-207">Granting Permission for Device Objects</span></span>

<span data-ttu-id="45ec5-208">При запуске командлета **Grant-CsOuPermission** для объектов-устройств в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="45ec5-208">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="45ec5-209">Разрешения, предоставленные объектам-устройствам</span><span class="sxs-lookup"><span data-stu-id="45ec5-209">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45ec5-210">Группа</span><span class="sxs-lookup"><span data-stu-id="45ec5-210">Group</span></span></th>
<th><span data-ttu-id="45ec5-211">Разрешение</span><span class="sxs-lookup"><span data-stu-id="45ec5-211">Permission</span></span></th>
<th><span data-ttu-id="45ec5-212">Применимо к</span><span class="sxs-lookup"><span data-stu-id="45ec5-212">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-213">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="45ec5-213">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="45ec5-214">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="45ec5-214">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="45ec5-215">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-215">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ec5-216">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-216">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-217">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45ec5-217">List contents</span></span></p>
<p><span data-ttu-id="45ec5-218">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45ec5-218">Read all properties</span></span></p>
<p><span data-ttu-id="45ec5-219">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45ec5-219">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-220">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-220">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-221">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-221">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-222">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45ec5-222">List contents</span></span></p>
<p><span data-ttu-id="45ec5-223">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45ec5-223">Read all properties</span></span></p>
<p><span data-ttu-id="45ec5-224">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45ec5-224">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-225">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-225">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ec5-226">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-226">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-227">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-227">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-228">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-228">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-229">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-229">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-230">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-230">Read Public-Information</span></span></p>
<p><span data-ttu-id="45ec5-231">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-231">Read Personal-Information</span></span></p>
<p><span data-ttu-id="45ec5-232">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-232">Read General-Information</span></span></p>
<p><span data-ttu-id="45ec5-233">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="45ec5-233">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-234">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="45ec5-234">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-235">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45ec5-235">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45ec5-236">Создание дочернего объекта</span><span class="sxs-lookup"><span data-stu-id="45ec5-236">Create child</span></span></p>
<p><span data-ttu-id="45ec5-237">Удаление дочернего объекта</span><span class="sxs-lookup"><span data-stu-id="45ec5-237">Delete child</span></span></p>
<p><span data-ttu-id="45ec5-238">Удаление дерева</span><span class="sxs-lookup"><span data-stu-id="45ec5-238">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="45ec5-239">Контакт</span><span class="sxs-lookup"><span data-stu-id="45ec5-239">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ec5-240">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45ec5-240">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45ec5-241">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="45ec5-241">Write displayName</span></span></p>
<p><span data-ttu-id="45ec5-242">Запись description</span><span class="sxs-lookup"><span data-stu-id="45ec5-242">Write description</span></span></p>
<p><span data-ttu-id="45ec5-243">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="45ec5-243">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="45ec5-244">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="45ec5-244">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-245">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45ec5-245">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45ec5-246">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-246">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-247">Запись otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="45ec5-247">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="45ec5-248">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="45ec5-248">Write displayName</span></span></p>
<p><span data-ttu-id="45ec5-249">Запись description</span><span class="sxs-lookup"><span data-stu-id="45ec5-249">Write description</span></span></p>
<p><span data-ttu-id="45ec5-250">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="45ec5-250">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="45ec5-251">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="45ec5-251">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="45ec5-252">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-252">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-253">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-253">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-254">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="45ec5-254">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="45ec5-255">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="45ec5-255">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="45ec5-256">Предоставление разрешений для объектов inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="45ec5-256">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="45ec5-257">При запуске командлета **Grant-CsOuPermission** для объектов inetOrgPerson в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="45ec5-257">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="45ec5-258">Разрешения, предоставленные объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="45ec5-258">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45ec5-259">Группа</span><span class="sxs-lookup"><span data-stu-id="45ec5-259">Group</span></span></th>
<th><span data-ttu-id="45ec5-260">Разрешение</span><span class="sxs-lookup"><span data-stu-id="45ec5-260">Permission</span></span></th>
<th><span data-ttu-id="45ec5-261">Применимо к</span><span class="sxs-lookup"><span data-stu-id="45ec5-261">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-262">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="45ec5-262">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="45ec5-263">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="45ec5-263">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="45ec5-264">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-264">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ec5-265">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-265">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-266">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45ec5-266">List contents</span></span></p>
<p><span data-ttu-id="45ec5-267">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45ec5-267">Read all properties</span></span></p>
<p><span data-ttu-id="45ec5-268">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45ec5-268">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-269">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-269">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-270">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-270">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-271">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45ec5-271">List contents</span></span></p>
<p><span data-ttu-id="45ec5-272">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45ec5-272">Read all properties</span></span></p>
<p><span data-ttu-id="45ec5-273">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45ec5-273">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-274">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45ec5-274">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ec5-275">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45ec5-275">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45ec5-276">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-276">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-277">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-277">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-278">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-278">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-279">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-279">Read Personal-Information</span></span></p>
<p><span data-ttu-id="45ec5-280">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-280">Read Public-Information</span></span></p>
<p><span data-ttu-id="45ec5-281">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="45ec5-281">Read General-Information</span></span></p>
<p><span data-ttu-id="45ec5-282">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="45ec5-282">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="45ec5-283">К дочерним объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="45ec5-283">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ec5-284">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45ec5-284">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45ec5-285">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-285">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-286">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-286">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-287">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45ec5-287">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="45ec5-288">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="45ec5-288">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="45ec5-289">К дочерним объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="45ec5-289">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

