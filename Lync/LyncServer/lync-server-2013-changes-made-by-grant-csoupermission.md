---
title: 'Lync Server 2013: изменения, внесенные с помощью Grant — CsOUPermission'
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
ms.openlocfilehash: dfad0cf4b8b863cd19d4d4113241477de1a50aaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="491b4-102">Изменения, внесенные с помощью Grant – CsOUPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="491b4-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="491b4-103">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="491b4-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="491b4-104">Чтобы делегировать администрирование Lync Server 2013, можно добавить разрешения для указанных подразделений, чтобы участники универсальных групп RTC, созданные при подготовке леса, могли получать доступ к подразделениям, не открывая группу "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="491b4-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="491b4-105">Командлет **Grant-CsOuPermission** предоставляет разрешения объектам в указанном подразделении, как указано в следующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="491b4-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="491b4-106">Предоставление разрешений для объектов-пользователей</span><span class="sxs-lookup"><span data-stu-id="491b4-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="491b4-107">При запуске командлета **Grant-CsOuPermission** для объектов-пользователей в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="491b4-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="491b4-108">Разрешения, предоставленные объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="491b4-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="491b4-109">Group</span><span class="sxs-lookup"><span data-stu-id="491b4-109">Group</span></span></th>
<th><span data-ttu-id="491b4-110">Разрешение</span><span class="sxs-lookup"><span data-stu-id="491b4-110">Permission</span></span></th>
<th><span data-ttu-id="491b4-111">Применимо к</span><span class="sxs-lookup"><span data-stu-id="491b4-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="491b4-112">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="491b4-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="491b4-113">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="491b4-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="491b4-114">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491b4-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-116">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="491b4-116">List contents</span></span></p>
<p><span data-ttu-id="491b4-117">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="491b4-117">Read all properties</span></span></p>
<p><span data-ttu-id="491b4-118">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="491b4-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="491b4-119">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491b4-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-121">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="491b4-121">List contents</span></span></p>
<p><span data-ttu-id="491b4-122">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="491b4-122">Read all properties</span></span></p>
<p><span data-ttu-id="491b4-123">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="491b4-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="491b4-124">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491b4-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-126">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="491b4-127">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="491b4-128">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="491b4-129">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="491b4-130">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-130">Read General-Information</span></span></p>
<p><span data-ttu-id="491b4-131">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="491b4-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="491b4-132">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="491b4-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491b4-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="491b4-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="491b4-134">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="491b4-135">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="491b4-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="491b4-136">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="491b4-137">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="491b4-138">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="491b4-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="491b4-139">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="491b4-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="491b4-140">Предоставление разрешений для объектов-компьютеров</span><span class="sxs-lookup"><span data-stu-id="491b4-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="491b4-141">При запуске командлета **Grant-CsOuPermission** для объектов-компьютеров в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="491b4-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="491b4-142">Разрешения, предоставленные объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="491b4-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="491b4-143">Group</span><span class="sxs-lookup"><span data-stu-id="491b4-143">Group</span></span></th>
<th><span data-ttu-id="491b4-144">Разрешение</span><span class="sxs-lookup"><span data-stu-id="491b4-144">Permission</span></span></th>
<th><span data-ttu-id="491b4-145">Применимо к</span><span class="sxs-lookup"><span data-stu-id="491b4-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="491b4-146">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="491b4-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="491b4-147">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="491b4-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="491b4-148">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491b4-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-150">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="491b4-150">List contents</span></span></p>
<p><span data-ttu-id="491b4-151">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="491b4-151">Read all properties</span></span></p>
<p><span data-ttu-id="491b4-152">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="491b4-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="491b4-153">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491b4-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-155">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="491b4-155">List contents</span></span></p>
<p><span data-ttu-id="491b4-156">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="491b4-156">Read all properties</span></span></p>
<p><span data-ttu-id="491b4-157">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="491b4-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="491b4-158">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491b4-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-160">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="491b4-161">Чтение Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="491b4-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="491b4-162">К дочерним объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="491b4-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491b4-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="491b4-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="491b4-164">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="491b4-165">Чтение Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="491b4-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="491b4-166">К дочерним объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="491b4-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="491b4-167">Предоставление разрешений для контактных объектов  или объектов AppContact</span><span class="sxs-lookup"><span data-stu-id="491b4-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="491b4-168">При запуске командлета **Grant-CsOuPermission** для контактных объектов и объектов AppContact в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="491b4-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="491b4-169">Разрешения, предоставленные контактным объектам и объектам AppContact</span><span class="sxs-lookup"><span data-stu-id="491b4-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="491b4-170">Group</span><span class="sxs-lookup"><span data-stu-id="491b4-170">Group</span></span></th>
<th><span data-ttu-id="491b4-171">Разрешение</span><span class="sxs-lookup"><span data-stu-id="491b4-171">Permission</span></span></th>
<th><span data-ttu-id="491b4-172">Применимо к</span><span class="sxs-lookup"><span data-stu-id="491b4-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="491b4-173">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="491b4-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="491b4-174">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="491b4-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="491b4-175">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491b4-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-177">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="491b4-177">List contents</span></span></p>
<p><span data-ttu-id="491b4-178">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="491b4-178">Read all properties</span></span></p>
<p><span data-ttu-id="491b4-179">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="491b4-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="491b4-180">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491b4-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-182">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="491b4-182">List contents</span></span></p>
<p><span data-ttu-id="491b4-183">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="491b4-183">Read all properties</span></span></p>
<p><span data-ttu-id="491b4-184">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="491b4-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="491b4-185">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491b4-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-187">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="491b4-188">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="491b4-189">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="491b4-190">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="491b4-191">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-191">Read General-Information</span></span></p>
<p><span data-ttu-id="491b4-192">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="491b4-193">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="491b4-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="491b4-194">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="491b4-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491b4-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="491b4-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="491b4-196">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="491b4-197">Запись otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="491b4-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="491b4-198">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="491b4-198">Write displayName</span></span></p>
<p><span data-ttu-id="491b4-199">Запись description</span><span class="sxs-lookup"><span data-stu-id="491b4-199">Write description</span></span></p>
<p><span data-ttu-id="491b4-200">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="491b4-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="491b4-201">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="491b4-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="491b4-202">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="491b4-203">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="491b4-204">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="491b4-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="491b4-205">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="491b4-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="491b4-206">Предоставление разрешений для объектов-устройств</span><span class="sxs-lookup"><span data-stu-id="491b4-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="491b4-207">При запуске командлета **Grant-CsOuPermission** для объектов-устройств в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="491b4-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="491b4-208">Разрешения, предоставленные объектам-устройствам</span><span class="sxs-lookup"><span data-stu-id="491b4-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="491b4-209">Group</span><span class="sxs-lookup"><span data-stu-id="491b4-209">Group</span></span></th>
<th><span data-ttu-id="491b4-210">Разрешение</span><span class="sxs-lookup"><span data-stu-id="491b4-210">Permission</span></span></th>
<th><span data-ttu-id="491b4-211">Применимо к</span><span class="sxs-lookup"><span data-stu-id="491b4-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="491b4-212">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="491b4-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="491b4-213">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="491b4-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="491b4-214">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491b4-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-216">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="491b4-216">List contents</span></span></p>
<p><span data-ttu-id="491b4-217">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="491b4-217">Read all properties</span></span></p>
<p><span data-ttu-id="491b4-218">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="491b4-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="491b4-219">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491b4-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-221">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="491b4-221">List contents</span></span></p>
<p><span data-ttu-id="491b4-222">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="491b4-222">Read all properties</span></span></p>
<p><span data-ttu-id="491b4-223">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="491b4-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="491b4-224">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491b4-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-226">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="491b4-227">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="491b4-228">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="491b4-229">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="491b4-230">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="491b4-231">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-231">Read General-Information</span></span></p>
<p><span data-ttu-id="491b4-232">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="491b4-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="491b4-233">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="491b4-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491b4-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="491b4-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="491b4-235">Создание дочернего объекта</span><span class="sxs-lookup"><span data-stu-id="491b4-235">Create child</span></span></p>
<p><span data-ttu-id="491b4-236">Удаление дочернего объекта</span><span class="sxs-lookup"><span data-stu-id="491b4-236">Delete child</span></span></p>
<p><span data-ttu-id="491b4-237">Удаление дерева</span><span class="sxs-lookup"><span data-stu-id="491b4-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="491b4-238">Контакт</span><span class="sxs-lookup"><span data-stu-id="491b4-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491b4-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="491b4-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="491b4-240">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="491b4-240">Write displayName</span></span></p>
<p><span data-ttu-id="491b4-241">Запись description</span><span class="sxs-lookup"><span data-stu-id="491b4-241">Write description</span></span></p>
<p><span data-ttu-id="491b4-242">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="491b4-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="491b4-243">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="491b4-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491b4-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="491b4-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="491b4-245">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="491b4-246">Запись otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="491b4-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="491b4-247">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="491b4-247">Write displayName</span></span></p>
<p><span data-ttu-id="491b4-248">Запись description</span><span class="sxs-lookup"><span data-stu-id="491b4-248">Write description</span></span></p>
<p><span data-ttu-id="491b4-249">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="491b4-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="491b4-250">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="491b4-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="491b4-251">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="491b4-252">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="491b4-253">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="491b4-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="491b4-254">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="491b4-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="491b4-255">Предоставление разрешений для объектов inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="491b4-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="491b4-256">При запуске командлета **Grant-CsOuPermission** для объектов inetOrgPerson в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="491b4-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="491b4-257">Разрешения, предоставленные объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="491b4-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="491b4-258">Group</span><span class="sxs-lookup"><span data-stu-id="491b4-258">Group</span></span></th>
<th><span data-ttu-id="491b4-259">Разрешение</span><span class="sxs-lookup"><span data-stu-id="491b4-259">Permission</span></span></th>
<th><span data-ttu-id="491b4-260">Применимо к</span><span class="sxs-lookup"><span data-stu-id="491b4-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="491b4-261">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="491b4-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="491b4-262">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="491b4-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="491b4-263">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491b4-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-265">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="491b4-265">List contents</span></span></p>
<p><span data-ttu-id="491b4-266">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="491b4-266">Read all properties</span></span></p>
<p><span data-ttu-id="491b4-267">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="491b4-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="491b4-268">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491b4-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-270">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="491b4-270">List contents</span></span></p>
<p><span data-ttu-id="491b4-271">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="491b4-271">Read all properties</span></span></p>
<p><span data-ttu-id="491b4-272">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="491b4-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="491b4-273">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="491b4-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491b4-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="491b4-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="491b4-275">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="491b4-276">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="491b4-277">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="491b4-278">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="491b4-279">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="491b4-280">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="491b4-280">Read General-Information</span></span></p>
<p><span data-ttu-id="491b4-281">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="491b4-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="491b4-282">К дочерним объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="491b4-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491b4-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="491b4-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="491b4-284">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="491b4-285">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="491b4-286">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="491b4-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="491b4-287">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="491b4-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="491b4-288">К дочерним объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="491b4-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

