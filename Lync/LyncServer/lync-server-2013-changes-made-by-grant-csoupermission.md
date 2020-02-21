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
ms.openlocfilehash: 6143310797c7372a30665cd380d7fb07340ebaf9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="45e67-102">Изменения, внесенные с помощью Grant – CsOUPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45e67-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45e67-103">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="45e67-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="45e67-104">Чтобы делегировать администрирование Lync Server 2013, можно добавить разрешения для указанных подразделений, чтобы участники универсальных групп RTC, созданные при подготовке леса, могли получать доступ к подразделениям, не открывая группу "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="45e67-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="45e67-105">Командлет **Grant-CsOuPermission** предоставляет разрешения объектам в указанном подразделении, как указано в следующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="45e67-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="45e67-106">Предоставление разрешений для объектов-пользователей</span><span class="sxs-lookup"><span data-stu-id="45e67-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="45e67-107">При запуске командлета **Grant-CsOuPermission** для объектов-пользователей в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="45e67-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="45e67-108">Разрешения, предоставленные объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="45e67-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45e67-109">Group</span><span class="sxs-lookup"><span data-stu-id="45e67-109">Group</span></span></th>
<th><span data-ttu-id="45e67-110">Разрешение</span><span class="sxs-lookup"><span data-stu-id="45e67-110">Permission</span></span></th>
<th><span data-ttu-id="45e67-111">Применимо к</span><span class="sxs-lookup"><span data-stu-id="45e67-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45e67-112">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="45e67-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="45e67-113">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="45e67-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="45e67-114">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45e67-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-116">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45e67-116">List contents</span></span></p>
<p><span data-ttu-id="45e67-117">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45e67-117">Read all properties</span></span></p>
<p><span data-ttu-id="45e67-118">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45e67-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45e67-119">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45e67-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-121">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45e67-121">List contents</span></span></p>
<p><span data-ttu-id="45e67-122">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45e67-122">Read all properties</span></span></p>
<p><span data-ttu-id="45e67-123">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45e67-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45e67-124">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45e67-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-126">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45e67-127">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45e67-128">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="45e67-129">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="45e67-130">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-130">Read General-Information</span></span></p>
<p><span data-ttu-id="45e67-131">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="45e67-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="45e67-132">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="45e67-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45e67-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45e67-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45e67-134">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45e67-135">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="45e67-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="45e67-136">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45e67-137">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="45e67-138">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="45e67-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="45e67-139">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="45e67-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="45e67-140">Предоставление разрешений для объектов-компьютеров</span><span class="sxs-lookup"><span data-stu-id="45e67-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="45e67-141">При запуске командлета **Grant-CsOuPermission** для объектов-компьютеров в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="45e67-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="45e67-142">Разрешения, предоставленные объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="45e67-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45e67-143">Group</span><span class="sxs-lookup"><span data-stu-id="45e67-143">Group</span></span></th>
<th><span data-ttu-id="45e67-144">Разрешение</span><span class="sxs-lookup"><span data-stu-id="45e67-144">Permission</span></span></th>
<th><span data-ttu-id="45e67-145">Применимо к</span><span class="sxs-lookup"><span data-stu-id="45e67-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45e67-146">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="45e67-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="45e67-147">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="45e67-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="45e67-148">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45e67-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-150">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45e67-150">List contents</span></span></p>
<p><span data-ttu-id="45e67-151">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45e67-151">Read all properties</span></span></p>
<p><span data-ttu-id="45e67-152">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45e67-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45e67-153">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45e67-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-155">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45e67-155">List contents</span></span></p>
<p><span data-ttu-id="45e67-156">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45e67-156">Read all properties</span></span></p>
<p><span data-ttu-id="45e67-157">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45e67-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45e67-158">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45e67-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-160">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="45e67-161">Чтение Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="45e67-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="45e67-162">К дочерним объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="45e67-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45e67-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45e67-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45e67-164">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="45e67-165">Чтение Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="45e67-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="45e67-166">К дочерним объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="45e67-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="45e67-167">Предоставление разрешений для контактных объектов  или объектов AppContact</span><span class="sxs-lookup"><span data-stu-id="45e67-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="45e67-168">При запуске командлета **Grant-CsOuPermission** для контактных объектов и объектов AppContact в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="45e67-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="45e67-169">Разрешения, предоставленные контактным объектам и объектам AppContact</span><span class="sxs-lookup"><span data-stu-id="45e67-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45e67-170">Group</span><span class="sxs-lookup"><span data-stu-id="45e67-170">Group</span></span></th>
<th><span data-ttu-id="45e67-171">Разрешение</span><span class="sxs-lookup"><span data-stu-id="45e67-171">Permission</span></span></th>
<th><span data-ttu-id="45e67-172">Применимо к</span><span class="sxs-lookup"><span data-stu-id="45e67-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45e67-173">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="45e67-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="45e67-174">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="45e67-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="45e67-175">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45e67-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-177">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45e67-177">List contents</span></span></p>
<p><span data-ttu-id="45e67-178">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45e67-178">Read all properties</span></span></p>
<p><span data-ttu-id="45e67-179">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45e67-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45e67-180">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45e67-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-182">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45e67-182">List contents</span></span></p>
<p><span data-ttu-id="45e67-183">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45e67-183">Read all properties</span></span></p>
<p><span data-ttu-id="45e67-184">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45e67-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45e67-185">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45e67-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-187">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45e67-188">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45e67-189">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="45e67-190">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="45e67-191">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-191">Read General-Information</span></span></p>
<p><span data-ttu-id="45e67-192">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="45e67-193">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="45e67-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="45e67-194">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="45e67-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45e67-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45e67-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45e67-196">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45e67-197">Запись otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="45e67-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="45e67-198">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="45e67-198">Write displayName</span></span></p>
<p><span data-ttu-id="45e67-199">Запись description</span><span class="sxs-lookup"><span data-stu-id="45e67-199">Write description</span></span></p>
<p><span data-ttu-id="45e67-200">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="45e67-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="45e67-201">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="45e67-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="45e67-202">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45e67-203">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="45e67-204">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="45e67-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="45e67-205">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="45e67-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="45e67-206">Предоставление разрешений для объектов-устройств</span><span class="sxs-lookup"><span data-stu-id="45e67-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="45e67-207">При запуске командлета **Grant-CsOuPermission** для объектов-устройств в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="45e67-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="45e67-208">Разрешения, предоставленные объектам-устройствам</span><span class="sxs-lookup"><span data-stu-id="45e67-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45e67-209">Group</span><span class="sxs-lookup"><span data-stu-id="45e67-209">Group</span></span></th>
<th><span data-ttu-id="45e67-210">Разрешение</span><span class="sxs-lookup"><span data-stu-id="45e67-210">Permission</span></span></th>
<th><span data-ttu-id="45e67-211">Применимо к</span><span class="sxs-lookup"><span data-stu-id="45e67-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45e67-212">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="45e67-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="45e67-213">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="45e67-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="45e67-214">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45e67-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-216">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45e67-216">List contents</span></span></p>
<p><span data-ttu-id="45e67-217">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45e67-217">Read all properties</span></span></p>
<p><span data-ttu-id="45e67-218">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45e67-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45e67-219">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45e67-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-221">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45e67-221">List contents</span></span></p>
<p><span data-ttu-id="45e67-222">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45e67-222">Read all properties</span></span></p>
<p><span data-ttu-id="45e67-223">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45e67-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45e67-224">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45e67-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-226">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45e67-227">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45e67-228">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="45e67-229">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="45e67-230">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="45e67-231">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-231">Read General-Information</span></span></p>
<p><span data-ttu-id="45e67-232">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="45e67-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="45e67-233">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="45e67-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45e67-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45e67-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45e67-235">Создание дочернего объекта</span><span class="sxs-lookup"><span data-stu-id="45e67-235">Create child</span></span></p>
<p><span data-ttu-id="45e67-236">Удаление дочернего объекта</span><span class="sxs-lookup"><span data-stu-id="45e67-236">Delete child</span></span></p>
<p><span data-ttu-id="45e67-237">Удаление дерева</span><span class="sxs-lookup"><span data-stu-id="45e67-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="45e67-238">Контакт</span><span class="sxs-lookup"><span data-stu-id="45e67-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45e67-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45e67-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45e67-240">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="45e67-240">Write displayName</span></span></p>
<p><span data-ttu-id="45e67-241">Запись description</span><span class="sxs-lookup"><span data-stu-id="45e67-241">Write description</span></span></p>
<p><span data-ttu-id="45e67-242">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="45e67-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="45e67-243">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="45e67-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45e67-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45e67-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45e67-245">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45e67-246">Запись otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="45e67-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="45e67-247">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="45e67-247">Write displayName</span></span></p>
<p><span data-ttu-id="45e67-248">Запись description</span><span class="sxs-lookup"><span data-stu-id="45e67-248">Write description</span></span></p>
<p><span data-ttu-id="45e67-249">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="45e67-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="45e67-250">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="45e67-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="45e67-251">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45e67-252">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="45e67-253">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="45e67-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="45e67-254">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="45e67-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="45e67-255">Предоставление разрешений для объектов inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="45e67-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="45e67-256">При запуске командлета **Grant-CsOuPermission** для объектов inetOrgPerson в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="45e67-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="45e67-257">Разрешения, предоставленные объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="45e67-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45e67-258">Group</span><span class="sxs-lookup"><span data-stu-id="45e67-258">Group</span></span></th>
<th><span data-ttu-id="45e67-259">Разрешение</span><span class="sxs-lookup"><span data-stu-id="45e67-259">Permission</span></span></th>
<th><span data-ttu-id="45e67-260">Применимо к</span><span class="sxs-lookup"><span data-stu-id="45e67-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45e67-261">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="45e67-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="45e67-262">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="45e67-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="45e67-263">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45e67-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-265">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45e67-265">List contents</span></span></p>
<p><span data-ttu-id="45e67-266">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45e67-266">Read all properties</span></span></p>
<p><span data-ttu-id="45e67-267">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45e67-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45e67-268">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45e67-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-270">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="45e67-270">List contents</span></span></p>
<p><span data-ttu-id="45e67-271">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="45e67-271">Read all properties</span></span></p>
<p><span data-ttu-id="45e67-272">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="45e67-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="45e67-273">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="45e67-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45e67-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="45e67-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="45e67-275">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45e67-276">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45e67-277">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="45e67-278">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="45e67-279">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="45e67-280">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="45e67-280">Read General-Information</span></span></p>
<p><span data-ttu-id="45e67-281">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="45e67-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="45e67-282">К дочерним объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="45e67-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45e67-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="45e67-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="45e67-284">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="45e67-285">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="45e67-286">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="45e67-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="45e67-287">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="45e67-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="45e67-288">К дочерним объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="45e67-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

