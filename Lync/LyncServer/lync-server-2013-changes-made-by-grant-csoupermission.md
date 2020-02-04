---
title: 'Lync Server 2013: изменения, внесенные пользователем Grant-Ксаупермиссион'
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
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="333a4-102">Изменения, внесенные функцией Grant-Ксаупермиссион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="333a4-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="333a4-103">_**Тема последнего изменения:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="333a4-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="333a4-104">Чтобы делегировать администрирование Lync Server 2013, вы можете добавить разрешения для указанных организационных подразделений, чтобы участники универсальных групп RTC, созданные с помощью подготовки леса, могли получать доступ к подразделениям без участия в группе Администраторы домена.</span><span class="sxs-lookup"><span data-stu-id="333a4-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="333a4-105">Командлет **Grant-ксаупермиссион** предоставляет разрешения на доступ к объектам в указанном подразделении, как указано в приведенных ниже таблицах.</span><span class="sxs-lookup"><span data-stu-id="333a4-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="333a4-106">Предоставление разрешений для объектов пользователей</span><span class="sxs-lookup"><span data-stu-id="333a4-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="333a4-107">Когда вы запускаете командлет **Grant-ксаупермиссион** для объектов пользователей в подразделении, группам предоставляются разрешения, как показано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="333a4-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="333a4-108">Разрешения, предоставленные для объектов пользователя</span><span class="sxs-lookup"><span data-stu-id="333a4-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="333a4-109">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="333a4-109">Group</span></span></th>
<th><span data-ttu-id="333a4-110">PermissionSet</span><span class="sxs-lookup"><span data-stu-id="333a4-110">Permission</span></span></th>
<th><span data-ttu-id="333a4-111">Применимо к</span><span class="sxs-lookup"><span data-stu-id="333a4-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="333a4-112">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="333a4-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="333a4-113">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="333a4-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="333a4-114">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333a4-115">рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-116">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="333a4-116">List contents</span></span></p>
<p><span data-ttu-id="333a4-117">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="333a4-117">Read all properties</span></span></p>
<p><span data-ttu-id="333a4-118">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="333a4-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="333a4-119">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333a4-120">рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-121">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="333a4-121">List contents</span></span></p>
<p><span data-ttu-id="333a4-122">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="333a4-122">Read all properties</span></span></p>
<p><span data-ttu-id="333a4-123">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="333a4-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="333a4-124">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333a4-125">рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-126">Прочитать Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="333a4-127">Прочитать Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="333a4-128">Прочитать Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="333a4-129">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="333a4-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="333a4-130">Чтение общих данных</span><span class="sxs-lookup"><span data-stu-id="333a4-130">Read General-Information</span></span></p>
<p><span data-ttu-id="333a4-131">Чтение ограничений для учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="333a4-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="333a4-132">Дочерние объекты пользователей</span><span class="sxs-lookup"><span data-stu-id="333a4-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333a4-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="333a4-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="333a4-134">Напишите Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="333a4-135">Напишите Мсексчуквоицемаилсеттингс</span><span class="sxs-lookup"><span data-stu-id="333a4-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="333a4-136">Напишите Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="333a4-137">Напишите Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="333a4-138">Напишите proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="333a4-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="333a4-139">Дочерние объекты пользователей</span><span class="sxs-lookup"><span data-stu-id="333a4-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="333a4-140">Предоставление разрешений на доступ к объектам компьютера</span><span class="sxs-lookup"><span data-stu-id="333a4-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="333a4-141">Когда вы запускаете командлет **Grant-ксаупермиссион** для объектов компьютеров в подразделении, группам предоставляются разрешения, как показано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="333a4-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="333a4-142">Разрешения, предоставленные для объектов компьютера</span><span class="sxs-lookup"><span data-stu-id="333a4-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="333a4-143">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="333a4-143">Group</span></span></th>
<th><span data-ttu-id="333a4-144">PermissionSet</span><span class="sxs-lookup"><span data-stu-id="333a4-144">Permission</span></span></th>
<th><span data-ttu-id="333a4-145">Применимо к</span><span class="sxs-lookup"><span data-stu-id="333a4-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="333a4-146">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="333a4-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="333a4-147">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="333a4-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="333a4-148">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333a4-149">рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-150">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="333a4-150">List contents</span></span></p>
<p><span data-ttu-id="333a4-151">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="333a4-151">Read all properties</span></span></p>
<p><span data-ttu-id="333a4-152">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="333a4-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="333a4-153">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333a4-154">рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-155">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="333a4-155">List contents</span></span></p>
<p><span data-ttu-id="333a4-156">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="333a4-156">Read all properties</span></span></p>
<p><span data-ttu-id="333a4-157">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="333a4-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="333a4-158">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333a4-159">рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-160">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="333a4-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="333a4-161">Проверка на прочтении DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="333a4-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="333a4-162">Дочерние объекты компьютера</span><span class="sxs-lookup"><span data-stu-id="333a4-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333a4-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="333a4-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="333a4-164">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="333a4-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="333a4-165">Проверка на прочтении DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="333a4-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="333a4-166">Дочерние объекты компьютера</span><span class="sxs-lookup"><span data-stu-id="333a4-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="333a4-167">Предоставление разрешений на доступ к объектам контакта или Аппконтакт</span><span class="sxs-lookup"><span data-stu-id="333a4-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="333a4-168">При запуске командлета **Grant-ксаупермиссион** для объектов контакта или объектов аппконтакт в подразделении группам предоставляются разрешения, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="333a4-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="333a4-169">Разрешения, предоставленные для контактных и Аппконтактных объектов</span><span class="sxs-lookup"><span data-stu-id="333a4-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="333a4-170">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="333a4-170">Group</span></span></th>
<th><span data-ttu-id="333a4-171">PermissionSet</span><span class="sxs-lookup"><span data-stu-id="333a4-171">Permission</span></span></th>
<th><span data-ttu-id="333a4-172">Применимо к</span><span class="sxs-lookup"><span data-stu-id="333a4-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="333a4-173">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="333a4-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="333a4-174">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="333a4-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="333a4-175">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333a4-176">рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-177">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="333a4-177">List contents</span></span></p>
<p><span data-ttu-id="333a4-178">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="333a4-178">Read all properties</span></span></p>
<p><span data-ttu-id="333a4-179">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="333a4-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="333a4-180">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333a4-181">рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-182">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="333a4-182">List contents</span></span></p>
<p><span data-ttu-id="333a4-183">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="333a4-183">Read all properties</span></span></p>
<p><span data-ttu-id="333a4-184">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="333a4-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="333a4-185">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333a4-186">рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-187">Прочитать Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="333a4-188">Прочитать Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="333a4-189">Прочитать Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="333a4-190">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="333a4-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="333a4-191">Чтение общих данных</span><span class="sxs-lookup"><span data-stu-id="333a4-191">Read General-Information</span></span></p>
<p><span data-ttu-id="333a4-192">Чтение персональных данных</span><span class="sxs-lookup"><span data-stu-id="333a4-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="333a4-193">Чтение ограничений для учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="333a4-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="333a4-194">Дочерние объекты контактов</span><span class="sxs-lookup"><span data-stu-id="333a4-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333a4-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="333a4-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="333a4-196">Напишите Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="333a4-197">Напишите Осерипфоне</span><span class="sxs-lookup"><span data-stu-id="333a4-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="333a4-198">Запись отображаемого текста</span><span class="sxs-lookup"><span data-stu-id="333a4-198">Write displayName</span></span></p>
<p><span data-ttu-id="333a4-199">Описание записи</span><span class="sxs-lookup"><span data-stu-id="333a4-199">Write description</span></span></p>
<p><span data-ttu-id="333a4-200">Напишите telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="333a4-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="333a4-201">Напишите Мсексчуквоицемаилсеттингс</span><span class="sxs-lookup"><span data-stu-id="333a4-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="333a4-202">Напишите Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="333a4-203">Напишите Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="333a4-204">Напишите proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="333a4-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="333a4-205">Дочерние объекты контактов</span><span class="sxs-lookup"><span data-stu-id="333a4-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="333a4-206">Предоставление разрешения на доступ к объектам устройства</span><span class="sxs-lookup"><span data-stu-id="333a4-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="333a4-207">Когда вы запускаете командлет **Grant-ксаупермиссион** для объектов устройств в подразделении, группам предоставляются разрешения, как показано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="333a4-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="333a4-208">Разрешения, предоставленные для объектов устройства</span><span class="sxs-lookup"><span data-stu-id="333a4-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="333a4-209">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="333a4-209">Group</span></span></th>
<th><span data-ttu-id="333a4-210">PermissionSet</span><span class="sxs-lookup"><span data-stu-id="333a4-210">Permission</span></span></th>
<th><span data-ttu-id="333a4-211">Применимо к</span><span class="sxs-lookup"><span data-stu-id="333a4-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="333a4-212">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="333a4-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="333a4-213">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="333a4-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="333a4-214">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333a4-215">рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-216">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="333a4-216">List contents</span></span></p>
<p><span data-ttu-id="333a4-217">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="333a4-217">Read all properties</span></span></p>
<p><span data-ttu-id="333a4-218">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="333a4-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="333a4-219">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333a4-220">рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-221">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="333a4-221">List contents</span></span></p>
<p><span data-ttu-id="333a4-222">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="333a4-222">Read all properties</span></span></p>
<p><span data-ttu-id="333a4-223">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="333a4-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="333a4-224">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333a4-225">рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-226">Прочитать Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="333a4-227">Прочитать Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="333a4-228">Прочитать Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="333a4-229">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="333a4-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="333a4-230">Чтение персональных данных</span><span class="sxs-lookup"><span data-stu-id="333a4-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="333a4-231">Чтение общих данных</span><span class="sxs-lookup"><span data-stu-id="333a4-231">Read General-Information</span></span></p>
<p><span data-ttu-id="333a4-232">Чтение ограничений для учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="333a4-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="333a4-233">Дочерние объекты контактов</span><span class="sxs-lookup"><span data-stu-id="333a4-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333a4-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="333a4-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="333a4-235">Создание дочернего элемента</span><span class="sxs-lookup"><span data-stu-id="333a4-235">Create child</span></span></p>
<p><span data-ttu-id="333a4-236">Удалить дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="333a4-236">Delete child</span></span></p>
<p><span data-ttu-id="333a4-237">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="333a4-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="333a4-238">Службу</span><span class="sxs-lookup"><span data-stu-id="333a4-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333a4-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="333a4-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="333a4-240">Запись отображаемого текста</span><span class="sxs-lookup"><span data-stu-id="333a4-240">Write displayName</span></span></p>
<p><span data-ttu-id="333a4-241">Описание записи</span><span class="sxs-lookup"><span data-stu-id="333a4-241">Write description</span></span></p>
<p><span data-ttu-id="333a4-242">Напишите telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="333a4-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="333a4-243">Дочерние объекты пользователей</span><span class="sxs-lookup"><span data-stu-id="333a4-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333a4-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="333a4-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="333a4-245">Напишите Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="333a4-246">Напишите Осерипфоне</span><span class="sxs-lookup"><span data-stu-id="333a4-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="333a4-247">Запись отображаемого текста</span><span class="sxs-lookup"><span data-stu-id="333a4-247">Write displayName</span></span></p>
<p><span data-ttu-id="333a4-248">Описание записи</span><span class="sxs-lookup"><span data-stu-id="333a4-248">Write description</span></span></p>
<p><span data-ttu-id="333a4-249">Напишите telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="333a4-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="333a4-250">Напишите Мсексчуквоицемаилсеттингс</span><span class="sxs-lookup"><span data-stu-id="333a4-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="333a4-251">Напишите Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="333a4-252">Напишите Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="333a4-253">Напишите proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="333a4-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="333a4-254">Дочерние объекты контактов</span><span class="sxs-lookup"><span data-stu-id="333a4-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="333a4-255">Предоставление разрешения для объектов InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="333a4-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="333a4-256">При запуске командлета **Grant-ксаупермиссион** для объектов inetOrgPerson в подразделении группам предоставляются разрешения, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="333a4-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="333a4-257">Разрешения, предоставленные для объектов InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="333a4-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="333a4-258">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="333a4-258">Group</span></span></th>
<th><span data-ttu-id="333a4-259">PermissionSet</span><span class="sxs-lookup"><span data-stu-id="333a4-259">Permission</span></span></th>
<th><span data-ttu-id="333a4-260">Применимо к</span><span class="sxs-lookup"><span data-stu-id="333a4-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="333a4-261">ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="333a4-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="333a4-262">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="333a4-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="333a4-263">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333a4-264">рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-265">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="333a4-265">List contents</span></span></p>
<p><span data-ttu-id="333a4-266">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="333a4-266">Read all properties</span></span></p>
<p><span data-ttu-id="333a4-267">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="333a4-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="333a4-268">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333a4-269">рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-270">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="333a4-270">List contents</span></span></p>
<p><span data-ttu-id="333a4-271">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="333a4-271">Read all properties</span></span></p>
<p><span data-ttu-id="333a4-272">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="333a4-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="333a4-273">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="333a4-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333a4-274">рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="333a4-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="333a4-275">Прочитать Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="333a4-276">Прочитать Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="333a4-277">Прочитать Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="333a4-278">Чтение персональных данных</span><span class="sxs-lookup"><span data-stu-id="333a4-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="333a4-279">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="333a4-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="333a4-280">Чтение общих данных</span><span class="sxs-lookup"><span data-stu-id="333a4-280">Read General-Information</span></span></p>
<p><span data-ttu-id="333a4-281">Чтение ограничений для учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="333a4-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="333a4-282">Дочерние объекты inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="333a4-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="333a4-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="333a4-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="333a4-284">Напишите Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="333a4-285">Напишите Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="333a4-286">Напишите Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="333a4-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="333a4-287">Напишите proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="333a4-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="333a4-288">Дочерние объекты inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="333a4-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

