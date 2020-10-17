---
title: 'Lync Server 2013: изменения, внесенные Grant-CsOUPermission'
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
ms.openlocfilehash: 0ff916c0b4e284f9c6ce4d5dbaf9c2e196ed4bc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529436"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="4580e-102">Изменения, внесенные Grant-CsOUPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4580e-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4580e-103">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="4580e-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="4580e-104">Чтобы делегировать администрирование Lync Server 2013, можно добавить разрешения для указанных подразделений, чтобы участники универсальных групп RTC, созданные при подготовке леса, могли получать доступ к подразделениям, не открывая группу "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="4580e-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="4580e-105">Командлет **Grant-CsOuPermission** предоставляет разрешения объектам в указанном подразделении, как указано в следующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="4580e-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="4580e-106">Предоставление разрешений для объектов-пользователей</span><span class="sxs-lookup"><span data-stu-id="4580e-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="4580e-107">При запуске командлета **Grant-CsOuPermission** для объектов-пользователей в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4580e-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="4580e-108">Разрешения, предоставленные объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="4580e-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4580e-109">Группа</span><span class="sxs-lookup"><span data-stu-id="4580e-109">Group</span></span></th>
<th><span data-ttu-id="4580e-110">Разрешение</span><span class="sxs-lookup"><span data-stu-id="4580e-110">Permission</span></span></th>
<th><span data-ttu-id="4580e-111">Применимо к</span><span class="sxs-lookup"><span data-stu-id="4580e-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4580e-112">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="4580e-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="4580e-113">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="4580e-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="4580e-114">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4580e-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-116">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="4580e-116">List contents</span></span></p>
<p><span data-ttu-id="4580e-117">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="4580e-117">Read all properties</span></span></p>
<p><span data-ttu-id="4580e-118">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="4580e-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="4580e-119">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4580e-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-121">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="4580e-121">List contents</span></span></p>
<p><span data-ttu-id="4580e-122">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="4580e-122">Read all properties</span></span></p>
<p><span data-ttu-id="4580e-123">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="4580e-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="4580e-124">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4580e-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-126">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="4580e-127">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="4580e-128">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="4580e-129">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="4580e-130">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-130">Read General-Information</span></span></p>
<p><span data-ttu-id="4580e-131">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="4580e-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="4580e-132">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="4580e-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4580e-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="4580e-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="4580e-134">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="4580e-135">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="4580e-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="4580e-136">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="4580e-137">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="4580e-138">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="4580e-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="4580e-139">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="4580e-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="4580e-140">Предоставление разрешений для объектов-компьютеров</span><span class="sxs-lookup"><span data-stu-id="4580e-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="4580e-141">При запуске командлета **Grant-CsOuPermission** для объектов-компьютеров в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4580e-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="4580e-142">Разрешения, предоставленные объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="4580e-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4580e-143">Группа</span><span class="sxs-lookup"><span data-stu-id="4580e-143">Group</span></span></th>
<th><span data-ttu-id="4580e-144">Разрешение</span><span class="sxs-lookup"><span data-stu-id="4580e-144">Permission</span></span></th>
<th><span data-ttu-id="4580e-145">Применимо к</span><span class="sxs-lookup"><span data-stu-id="4580e-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4580e-146">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="4580e-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="4580e-147">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="4580e-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="4580e-148">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4580e-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-150">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="4580e-150">List contents</span></span></p>
<p><span data-ttu-id="4580e-151">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="4580e-151">Read all properties</span></span></p>
<p><span data-ttu-id="4580e-152">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="4580e-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="4580e-153">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4580e-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-155">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="4580e-155">List contents</span></span></p>
<p><span data-ttu-id="4580e-156">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="4580e-156">Read all properties</span></span></p>
<p><span data-ttu-id="4580e-157">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="4580e-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="4580e-158">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4580e-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-160">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="4580e-161">Чтение Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="4580e-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="4580e-162">К дочерним объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="4580e-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4580e-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="4580e-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="4580e-164">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="4580e-165">Чтение Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="4580e-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="4580e-166">К дочерним объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="4580e-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="4580e-167">Предоставление разрешений для контактных объектов  или объектов AppContact</span><span class="sxs-lookup"><span data-stu-id="4580e-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="4580e-168">При запуске командлета **Grant-CsOuPermission** для контактных объектов и объектов AppContact в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4580e-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="4580e-169">Разрешения, предоставленные контактным объектам и объектам AppContact</span><span class="sxs-lookup"><span data-stu-id="4580e-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4580e-170">Группа</span><span class="sxs-lookup"><span data-stu-id="4580e-170">Group</span></span></th>
<th><span data-ttu-id="4580e-171">Разрешение</span><span class="sxs-lookup"><span data-stu-id="4580e-171">Permission</span></span></th>
<th><span data-ttu-id="4580e-172">Применимо к</span><span class="sxs-lookup"><span data-stu-id="4580e-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4580e-173">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="4580e-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="4580e-174">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="4580e-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="4580e-175">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4580e-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-177">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="4580e-177">List contents</span></span></p>
<p><span data-ttu-id="4580e-178">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="4580e-178">Read all properties</span></span></p>
<p><span data-ttu-id="4580e-179">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="4580e-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="4580e-180">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4580e-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-182">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="4580e-182">List contents</span></span></p>
<p><span data-ttu-id="4580e-183">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="4580e-183">Read all properties</span></span></p>
<p><span data-ttu-id="4580e-184">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="4580e-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="4580e-185">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4580e-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-187">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="4580e-188">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="4580e-189">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="4580e-190">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="4580e-191">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-191">Read General-Information</span></span></p>
<p><span data-ttu-id="4580e-192">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="4580e-193">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="4580e-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="4580e-194">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="4580e-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4580e-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="4580e-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="4580e-196">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="4580e-197">Запись otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="4580e-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="4580e-198">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="4580e-198">Write displayName</span></span></p>
<p><span data-ttu-id="4580e-199">Запись description</span><span class="sxs-lookup"><span data-stu-id="4580e-199">Write description</span></span></p>
<p><span data-ttu-id="4580e-200">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="4580e-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="4580e-201">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="4580e-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="4580e-202">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="4580e-203">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="4580e-204">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="4580e-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="4580e-205">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="4580e-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="4580e-206">Предоставление разрешений для объектов-устройств</span><span class="sxs-lookup"><span data-stu-id="4580e-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="4580e-207">При запуске командлета **Grant-CsOuPermission** для объектов-устройств в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4580e-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="4580e-208">Разрешения, предоставленные объектам-устройствам</span><span class="sxs-lookup"><span data-stu-id="4580e-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4580e-209">Группа</span><span class="sxs-lookup"><span data-stu-id="4580e-209">Group</span></span></th>
<th><span data-ttu-id="4580e-210">Разрешение</span><span class="sxs-lookup"><span data-stu-id="4580e-210">Permission</span></span></th>
<th><span data-ttu-id="4580e-211">Применимо к</span><span class="sxs-lookup"><span data-stu-id="4580e-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4580e-212">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="4580e-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="4580e-213">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="4580e-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="4580e-214">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4580e-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-216">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="4580e-216">List contents</span></span></p>
<p><span data-ttu-id="4580e-217">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="4580e-217">Read all properties</span></span></p>
<p><span data-ttu-id="4580e-218">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="4580e-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="4580e-219">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4580e-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-221">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="4580e-221">List contents</span></span></p>
<p><span data-ttu-id="4580e-222">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="4580e-222">Read all properties</span></span></p>
<p><span data-ttu-id="4580e-223">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="4580e-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="4580e-224">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4580e-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-226">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="4580e-227">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="4580e-228">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="4580e-229">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="4580e-230">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="4580e-231">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-231">Read General-Information</span></span></p>
<p><span data-ttu-id="4580e-232">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="4580e-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="4580e-233">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="4580e-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4580e-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="4580e-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="4580e-235">Создание дочернего объекта</span><span class="sxs-lookup"><span data-stu-id="4580e-235">Create child</span></span></p>
<p><span data-ttu-id="4580e-236">Удаление дочернего объекта</span><span class="sxs-lookup"><span data-stu-id="4580e-236">Delete child</span></span></p>
<p><span data-ttu-id="4580e-237">Удаление дерева</span><span class="sxs-lookup"><span data-stu-id="4580e-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="4580e-238">Контакт</span><span class="sxs-lookup"><span data-stu-id="4580e-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4580e-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="4580e-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="4580e-240">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="4580e-240">Write displayName</span></span></p>
<p><span data-ttu-id="4580e-241">Запись description</span><span class="sxs-lookup"><span data-stu-id="4580e-241">Write description</span></span></p>
<p><span data-ttu-id="4580e-242">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="4580e-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="4580e-243">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="4580e-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4580e-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="4580e-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="4580e-245">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="4580e-246">Запись otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="4580e-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="4580e-247">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="4580e-247">Write displayName</span></span></p>
<p><span data-ttu-id="4580e-248">Запись description</span><span class="sxs-lookup"><span data-stu-id="4580e-248">Write description</span></span></p>
<p><span data-ttu-id="4580e-249">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="4580e-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="4580e-250">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="4580e-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="4580e-251">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="4580e-252">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="4580e-253">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="4580e-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="4580e-254">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="4580e-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="4580e-255">Предоставление разрешений для объектов inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="4580e-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="4580e-256">При запуске командлета **Grant-CsOuPermission** для объектов inetOrgPerson в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4580e-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="4580e-257">Разрешения, предоставленные объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="4580e-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4580e-258">Группа</span><span class="sxs-lookup"><span data-stu-id="4580e-258">Group</span></span></th>
<th><span data-ttu-id="4580e-259">Разрешение</span><span class="sxs-lookup"><span data-stu-id="4580e-259">Permission</span></span></th>
<th><span data-ttu-id="4580e-260">Применимо к</span><span class="sxs-lookup"><span data-stu-id="4580e-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4580e-261">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="4580e-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="4580e-262">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="4580e-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="4580e-263">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4580e-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-265">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="4580e-265">List contents</span></span></p>
<p><span data-ttu-id="4580e-266">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="4580e-266">Read all properties</span></span></p>
<p><span data-ttu-id="4580e-267">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="4580e-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="4580e-268">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4580e-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-270">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="4580e-270">List contents</span></span></p>
<p><span data-ttu-id="4580e-271">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="4580e-271">Read all properties</span></span></p>
<p><span data-ttu-id="4580e-272">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="4580e-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="4580e-273">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="4580e-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4580e-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="4580e-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="4580e-275">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="4580e-276">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="4580e-277">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="4580e-278">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="4580e-279">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="4580e-280">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="4580e-280">Read General-Information</span></span></p>
<p><span data-ttu-id="4580e-281">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="4580e-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="4580e-282">К дочерним объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="4580e-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4580e-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="4580e-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="4580e-284">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="4580e-285">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="4580e-286">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="4580e-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="4580e-287">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="4580e-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="4580e-288">К дочерним объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="4580e-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

