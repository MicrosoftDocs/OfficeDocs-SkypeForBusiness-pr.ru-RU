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
ms.openlocfilehash: c64c11ba999763a44105a68502e53fc4889af305
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="8c5be-102">Изменения, внесенные с помощью Grant – CsOUPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c5be-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c5be-103">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="8c5be-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="8c5be-104">Чтобы делегировать администрирование Lync Server 2013, можно добавить разрешения для указанных подразделений, чтобы участники универсальных групп RTC, созданные при подготовке леса, могли получать доступ к подразделениям, не открывая группу "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="8c5be-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="8c5be-105">Командлет **Grant-CsOuPermission** предоставляет разрешения объектам в указанном подразделении, как указано в следующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="8c5be-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="8c5be-106">Предоставление разрешений для объектов-пользователей</span><span class="sxs-lookup"><span data-stu-id="8c5be-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="8c5be-107">При запуске командлета **Grant-CsOuPermission** для объектов-пользователей в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8c5be-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="8c5be-108">Разрешения, предоставленные объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="8c5be-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c5be-109">Group</span><span class="sxs-lookup"><span data-stu-id="8c5be-109">Group</span></span></th>
<th><span data-ttu-id="8c5be-110">Разрешение</span><span class="sxs-lookup"><span data-stu-id="8c5be-110">Permission</span></span></th>
<th><span data-ttu-id="8c5be-111">Применимо к</span><span class="sxs-lookup"><span data-stu-id="8c5be-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-112">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="8c5be-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8c5be-113">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="8c5be-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8c5be-114">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5be-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-116">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="8c5be-116">List contents</span></span></p>
<p><span data-ttu-id="8c5be-117">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="8c5be-117">Read all properties</span></span></p>
<p><span data-ttu-id="8c5be-118">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="8c5be-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-119">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-121">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="8c5be-121">List contents</span></span></p>
<p><span data-ttu-id="8c5be-122">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="8c5be-122">Read all properties</span></span></p>
<p><span data-ttu-id="8c5be-123">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="8c5be-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-124">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5be-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-126">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-127">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-128">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-129">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c5be-130">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-130">Read General-Information</span></span></p>
<p><span data-ttu-id="8c5be-131">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="8c5be-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-132">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="8c5be-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c5be-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c5be-134">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-135">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="8c5be-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="8c5be-136">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-137">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-138">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8c5be-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8c5be-139">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="8c5be-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="8c5be-140">Предоставление разрешений для объектов-компьютеров</span><span class="sxs-lookup"><span data-stu-id="8c5be-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="8c5be-141">При запуске командлета **Grant-CsOuPermission** для объектов-компьютеров в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8c5be-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="8c5be-142">Разрешения, предоставленные объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="8c5be-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c5be-143">Group</span><span class="sxs-lookup"><span data-stu-id="8c5be-143">Group</span></span></th>
<th><span data-ttu-id="8c5be-144">Разрешение</span><span class="sxs-lookup"><span data-stu-id="8c5be-144">Permission</span></span></th>
<th><span data-ttu-id="8c5be-145">Применимо к</span><span class="sxs-lookup"><span data-stu-id="8c5be-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-146">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="8c5be-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8c5be-147">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="8c5be-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8c5be-148">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5be-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-150">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="8c5be-150">List contents</span></span></p>
<p><span data-ttu-id="8c5be-151">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="8c5be-151">Read all properties</span></span></p>
<p><span data-ttu-id="8c5be-152">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="8c5be-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-153">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-155">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="8c5be-155">List contents</span></span></p>
<p><span data-ttu-id="8c5be-156">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="8c5be-156">Read all properties</span></span></p>
<p><span data-ttu-id="8c5be-157">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="8c5be-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-158">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5be-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-160">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c5be-161">Чтение Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="8c5be-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="8c5be-162">К дочерним объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="8c5be-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c5be-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c5be-164">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c5be-165">Чтение Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="8c5be-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="8c5be-166">К дочерним объектам-компьютерам</span><span class="sxs-lookup"><span data-stu-id="8c5be-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="8c5be-167">Предоставление разрешений для контактных объектов  или объектов AppContact</span><span class="sxs-lookup"><span data-stu-id="8c5be-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="8c5be-168">При запуске командлета **Grant-CsOuPermission** для контактных объектов и объектов AppContact в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8c5be-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="8c5be-169">Разрешения, предоставленные контактным объектам и объектам AppContact</span><span class="sxs-lookup"><span data-stu-id="8c5be-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c5be-170">Group</span><span class="sxs-lookup"><span data-stu-id="8c5be-170">Group</span></span></th>
<th><span data-ttu-id="8c5be-171">Разрешение</span><span class="sxs-lookup"><span data-stu-id="8c5be-171">Permission</span></span></th>
<th><span data-ttu-id="8c5be-172">Применимо к</span><span class="sxs-lookup"><span data-stu-id="8c5be-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-173">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="8c5be-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8c5be-174">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="8c5be-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8c5be-175">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5be-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-177">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="8c5be-177">List contents</span></span></p>
<p><span data-ttu-id="8c5be-178">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="8c5be-178">Read all properties</span></span></p>
<p><span data-ttu-id="8c5be-179">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="8c5be-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-180">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-182">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="8c5be-182">List contents</span></span></p>
<p><span data-ttu-id="8c5be-183">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="8c5be-183">Read all properties</span></span></p>
<p><span data-ttu-id="8c5be-184">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="8c5be-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-185">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5be-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-187">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-188">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-189">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-190">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c5be-191">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-191">Read General-Information</span></span></p>
<p><span data-ttu-id="8c5be-192">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="8c5be-193">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="8c5be-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-194">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="8c5be-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c5be-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c5be-196">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-197">Запись otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="8c5be-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="8c5be-198">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="8c5be-198">Write displayName</span></span></p>
<p><span data-ttu-id="8c5be-199">Запись description</span><span class="sxs-lookup"><span data-stu-id="8c5be-199">Write description</span></span></p>
<p><span data-ttu-id="8c5be-200">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="8c5be-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="8c5be-201">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="8c5be-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="8c5be-202">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-203">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-204">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8c5be-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8c5be-205">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="8c5be-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="8c5be-206">Предоставление разрешений для объектов-устройств</span><span class="sxs-lookup"><span data-stu-id="8c5be-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="8c5be-207">При запуске командлета **Grant-CsOuPermission** для объектов-устройств в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8c5be-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="8c5be-208">Разрешения, предоставленные объектам-устройствам</span><span class="sxs-lookup"><span data-stu-id="8c5be-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c5be-209">Group</span><span class="sxs-lookup"><span data-stu-id="8c5be-209">Group</span></span></th>
<th><span data-ttu-id="8c5be-210">Разрешение</span><span class="sxs-lookup"><span data-stu-id="8c5be-210">Permission</span></span></th>
<th><span data-ttu-id="8c5be-211">Применимо к</span><span class="sxs-lookup"><span data-stu-id="8c5be-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-212">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="8c5be-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8c5be-213">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="8c5be-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8c5be-214">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5be-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-216">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="8c5be-216">List contents</span></span></p>
<p><span data-ttu-id="8c5be-217">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="8c5be-217">Read all properties</span></span></p>
<p><span data-ttu-id="8c5be-218">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="8c5be-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-219">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-221">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="8c5be-221">List contents</span></span></p>
<p><span data-ttu-id="8c5be-222">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="8c5be-222">Read all properties</span></span></p>
<p><span data-ttu-id="8c5be-223">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="8c5be-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-224">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5be-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-226">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-227">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-228">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-229">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c5be-230">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="8c5be-231">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-231">Read General-Information</span></span></p>
<p><span data-ttu-id="8c5be-232">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="8c5be-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-233">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="8c5be-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c5be-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c5be-235">Создание дочернего объекта</span><span class="sxs-lookup"><span data-stu-id="8c5be-235">Create child</span></span></p>
<p><span data-ttu-id="8c5be-236">Удаление дочернего объекта</span><span class="sxs-lookup"><span data-stu-id="8c5be-236">Delete child</span></span></p>
<p><span data-ttu-id="8c5be-237">Удаление дерева</span><span class="sxs-lookup"><span data-stu-id="8c5be-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="8c5be-238">Контакт</span><span class="sxs-lookup"><span data-stu-id="8c5be-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5be-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c5be-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c5be-240">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="8c5be-240">Write displayName</span></span></p>
<p><span data-ttu-id="8c5be-241">Запись description</span><span class="sxs-lookup"><span data-stu-id="8c5be-241">Write description</span></span></p>
<p><span data-ttu-id="8c5be-242">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="8c5be-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="8c5be-243">К дочерним объектам-пользователям</span><span class="sxs-lookup"><span data-stu-id="8c5be-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c5be-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c5be-245">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-246">Запись otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="8c5be-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="8c5be-247">Запись displayName</span><span class="sxs-lookup"><span data-stu-id="8c5be-247">Write displayName</span></span></p>
<p><span data-ttu-id="8c5be-248">Запись description</span><span class="sxs-lookup"><span data-stu-id="8c5be-248">Write description</span></span></p>
<p><span data-ttu-id="8c5be-249">Запись telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="8c5be-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="8c5be-250">Запись msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="8c5be-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="8c5be-251">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-252">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-253">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8c5be-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8c5be-254">К дочерним контактным объектам</span><span class="sxs-lookup"><span data-stu-id="8c5be-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="8c5be-255">Предоставление разрешений для объектов inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="8c5be-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="8c5be-256">При запуске командлета **Grant-CsOuPermission** для объектов inetOrgPerson в подразделении группам предоставляются разрешения, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8c5be-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="8c5be-257">Разрешения, предоставленные объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="8c5be-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c5be-258">Group</span><span class="sxs-lookup"><span data-stu-id="8c5be-258">Group</span></span></th>
<th><span data-ttu-id="8c5be-259">Разрешение</span><span class="sxs-lookup"><span data-stu-id="8c5be-259">Permission</span></span></th>
<th><span data-ttu-id="8c5be-260">Применимо к</span><span class="sxs-lookup"><span data-stu-id="8c5be-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-261">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="8c5be-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8c5be-262">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="8c5be-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8c5be-263">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5be-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-265">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="8c5be-265">List contents</span></span></p>
<p><span data-ttu-id="8c5be-266">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="8c5be-266">Read all properties</span></span></p>
<p><span data-ttu-id="8c5be-267">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="8c5be-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-268">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-270">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="8c5be-270">List contents</span></span></p>
<p><span data-ttu-id="8c5be-271">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="8c5be-271">Read all properties</span></span></p>
<p><span data-ttu-id="8c5be-272">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="8c5be-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-273">Только к этому объекту</span><span class="sxs-lookup"><span data-stu-id="8c5be-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c5be-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c5be-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c5be-275">Чтение RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-276">Чтение RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-277">Чтение RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-278">Чтение Personal-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="8c5be-279">Чтение Public-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c5be-280">Чтение General-Information</span><span class="sxs-lookup"><span data-stu-id="8c5be-280">Read General-Information</span></span></p>
<p><span data-ttu-id="8c5be-281">Чтение User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="8c5be-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8c5be-282">К дочерним объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="8c5be-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c5be-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c5be-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c5be-284">Запись RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-285">Запись RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-286">Запись RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="8c5be-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c5be-287">Запись proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8c5be-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8c5be-288">К дочерним объектам inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="8c5be-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

