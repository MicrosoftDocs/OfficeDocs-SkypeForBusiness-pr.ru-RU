---
title: 'Lync Server 2013: изменения, внесенные пользователем Grant-Ксаупермиссион'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="5705d-102">Изменения, внесенные функцией Grant-Ксаупермиссион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5705d-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5705d-103">_**Тема последнего изменения:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="5705d-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="5705d-104">Чтобы делегировать администрирование Lync Server 2013, вы можете добавить разрешения для указанных организационных подразделений, чтобы участники универсальных групп RTC, созданные с помощью подготовки леса, могли получать доступ к подразделениям без участия в группе Администраторы домена.</span><span class="sxs-lookup"><span data-stu-id="5705d-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="5705d-105">Командлет **Grant-ксаупермиссион** предоставляет разрешения на доступ к объектам в указанном подразделении, как указано в приведенных ниже таблицах.</span><span class="sxs-lookup"><span data-stu-id="5705d-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="5705d-106">Предоставление разрешений для объектов пользователей</span><span class="sxs-lookup"><span data-stu-id="5705d-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="5705d-107">Когда вы запускаете командлет **Grant-ксаупермиссион** для объектов пользователей в подразделении, группам предоставляются разрешения, как показано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="5705d-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="5705d-108">Разрешения, предоставленные для объектов пользователя</span><span class="sxs-lookup"><span data-stu-id="5705d-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5705d-109">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="5705d-109">Group</span></span></th>
<th><span data-ttu-id="5705d-110">PermissionSet</span><span class="sxs-lookup"><span data-stu-id="5705d-110">Permission</span></span></th>
<th><span data-ttu-id="5705d-111">Применимо к</span><span class="sxs-lookup"><span data-stu-id="5705d-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5705d-112">Ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="5705d-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="5705d-113">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="5705d-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="5705d-114">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5705d-115">Рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-116">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="5705d-116">List contents</span></span></p>
<p><span data-ttu-id="5705d-117">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="5705d-117">Read all properties</span></span></p>
<p><span data-ttu-id="5705d-118">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="5705d-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="5705d-119">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5705d-120">Рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-121">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="5705d-121">List contents</span></span></p>
<p><span data-ttu-id="5705d-122">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="5705d-122">Read all properties</span></span></p>
<p><span data-ttu-id="5705d-123">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="5705d-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="5705d-124">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5705d-125">Рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-126">Прочитать Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="5705d-127">Прочитать Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="5705d-128">Прочитать Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="5705d-129">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="5705d-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="5705d-130">Чтение общих данных</span><span class="sxs-lookup"><span data-stu-id="5705d-130">Read General-Information</span></span></p>
<p><span data-ttu-id="5705d-131">Чтение ограничений для учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="5705d-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="5705d-132">Дочерние объекты пользователей</span><span class="sxs-lookup"><span data-stu-id="5705d-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5705d-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="5705d-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="5705d-134">Напишите Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="5705d-135">Напишите Мсексчуквоицемаилсеттингс</span><span class="sxs-lookup"><span data-stu-id="5705d-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="5705d-136">Напишите Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="5705d-137">Напишите Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="5705d-138">Напишите proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5705d-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="5705d-139">Дочерние объекты пользователей</span><span class="sxs-lookup"><span data-stu-id="5705d-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="5705d-140">Предоставление разрешений на доступ к объектам компьютера</span><span class="sxs-lookup"><span data-stu-id="5705d-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="5705d-141">Когда вы запускаете командлет **Grant-ксаупермиссион** для объектов компьютеров в подразделении, группам предоставляются разрешения, как показано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="5705d-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="5705d-142">Разрешения, предоставленные для объектов компьютера</span><span class="sxs-lookup"><span data-stu-id="5705d-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5705d-143">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="5705d-143">Group</span></span></th>
<th><span data-ttu-id="5705d-144">PermissionSet</span><span class="sxs-lookup"><span data-stu-id="5705d-144">Permission</span></span></th>
<th><span data-ttu-id="5705d-145">Применимо к</span><span class="sxs-lookup"><span data-stu-id="5705d-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5705d-146">Ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="5705d-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="5705d-147">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="5705d-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="5705d-148">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5705d-149">Рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-150">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="5705d-150">List contents</span></span></p>
<p><span data-ttu-id="5705d-151">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="5705d-151">Read all properties</span></span></p>
<p><span data-ttu-id="5705d-152">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="5705d-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="5705d-153">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5705d-154">Рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-155">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="5705d-155">List contents</span></span></p>
<p><span data-ttu-id="5705d-156">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="5705d-156">Read all properties</span></span></p>
<p><span data-ttu-id="5705d-157">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="5705d-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="5705d-158">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5705d-159">Рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-160">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="5705d-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="5705d-161">Проверка на прочтении DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="5705d-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="5705d-162">Дочерние объекты компьютера</span><span class="sxs-lookup"><span data-stu-id="5705d-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5705d-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="5705d-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="5705d-164">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="5705d-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="5705d-165">Проверка на прочтении DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="5705d-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="5705d-166">Дочерние объекты компьютера</span><span class="sxs-lookup"><span data-stu-id="5705d-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="5705d-167">Предоставление разрешений на доступ к объектам контакта или Аппконтакт</span><span class="sxs-lookup"><span data-stu-id="5705d-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="5705d-168">При запуске командлета **Grant-ксаупермиссион** для объектов контакта или объектов аппконтакт в подразделении группам предоставляются разрешения, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="5705d-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="5705d-169">Разрешения, предоставленные для контактных и Аппконтактных объектов</span><span class="sxs-lookup"><span data-stu-id="5705d-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5705d-170">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="5705d-170">Group</span></span></th>
<th><span data-ttu-id="5705d-171">PermissionSet</span><span class="sxs-lookup"><span data-stu-id="5705d-171">Permission</span></span></th>
<th><span data-ttu-id="5705d-172">Применимо к</span><span class="sxs-lookup"><span data-stu-id="5705d-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5705d-173">Ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="5705d-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="5705d-174">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="5705d-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="5705d-175">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5705d-176">Рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-177">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="5705d-177">List contents</span></span></p>
<p><span data-ttu-id="5705d-178">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="5705d-178">Read all properties</span></span></p>
<p><span data-ttu-id="5705d-179">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="5705d-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="5705d-180">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5705d-181">Рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-182">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="5705d-182">List contents</span></span></p>
<p><span data-ttu-id="5705d-183">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="5705d-183">Read all properties</span></span></p>
<p><span data-ttu-id="5705d-184">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="5705d-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="5705d-185">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5705d-186">Рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-187">Прочитать Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="5705d-188">Прочитать Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="5705d-189">Прочитать Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="5705d-190">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="5705d-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="5705d-191">Чтение общих данных</span><span class="sxs-lookup"><span data-stu-id="5705d-191">Read General-Information</span></span></p>
<p><span data-ttu-id="5705d-192">Чтение персональных данных</span><span class="sxs-lookup"><span data-stu-id="5705d-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="5705d-193">Чтение ограничений для учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="5705d-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="5705d-194">Дочерние объекты контактов</span><span class="sxs-lookup"><span data-stu-id="5705d-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5705d-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="5705d-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="5705d-196">Напишите Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="5705d-197">Напишите Осерипфоне</span><span class="sxs-lookup"><span data-stu-id="5705d-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="5705d-198">Запись отображаемого текста</span><span class="sxs-lookup"><span data-stu-id="5705d-198">Write displayName</span></span></p>
<p><span data-ttu-id="5705d-199">Описание записи</span><span class="sxs-lookup"><span data-stu-id="5705d-199">Write description</span></span></p>
<p><span data-ttu-id="5705d-200">Напишите telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="5705d-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="5705d-201">Напишите Мсексчуквоицемаилсеттингс</span><span class="sxs-lookup"><span data-stu-id="5705d-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="5705d-202">Напишите Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="5705d-203">Напишите Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="5705d-204">Напишите proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5705d-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="5705d-205">Дочерние объекты контактов</span><span class="sxs-lookup"><span data-stu-id="5705d-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="5705d-206">Предоставление разрешения на доступ к объектам устройства</span><span class="sxs-lookup"><span data-stu-id="5705d-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="5705d-207">Когда вы запускаете командлет **Grant-ксаупермиссион** для объектов устройств в подразделении, группам предоставляются разрешения, как показано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="5705d-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="5705d-208">Разрешения, предоставленные для объектов устройства</span><span class="sxs-lookup"><span data-stu-id="5705d-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5705d-209">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="5705d-209">Group</span></span></th>
<th><span data-ttu-id="5705d-210">PermissionSet</span><span class="sxs-lookup"><span data-stu-id="5705d-210">Permission</span></span></th>
<th><span data-ttu-id="5705d-211">Применимо к</span><span class="sxs-lookup"><span data-stu-id="5705d-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5705d-212">Ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="5705d-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="5705d-213">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="5705d-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="5705d-214">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5705d-215">Рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-216">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="5705d-216">List contents</span></span></p>
<p><span data-ttu-id="5705d-217">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="5705d-217">Read all properties</span></span></p>
<p><span data-ttu-id="5705d-218">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="5705d-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="5705d-219">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5705d-220">Рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-221">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="5705d-221">List contents</span></span></p>
<p><span data-ttu-id="5705d-222">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="5705d-222">Read all properties</span></span></p>
<p><span data-ttu-id="5705d-223">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="5705d-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="5705d-224">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5705d-225">Рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-226">Прочитать Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="5705d-227">Прочитать Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="5705d-228">Прочитать Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="5705d-229">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="5705d-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="5705d-230">Чтение персональных данных</span><span class="sxs-lookup"><span data-stu-id="5705d-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="5705d-231">Чтение общих данных</span><span class="sxs-lookup"><span data-stu-id="5705d-231">Read General-Information</span></span></p>
<p><span data-ttu-id="5705d-232">Чтение ограничений для учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="5705d-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="5705d-233">Дочерние объекты контактов</span><span class="sxs-lookup"><span data-stu-id="5705d-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5705d-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="5705d-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="5705d-235">Создание дочернего элемента</span><span class="sxs-lookup"><span data-stu-id="5705d-235">Create child</span></span></p>
<p><span data-ttu-id="5705d-236">Удалить дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="5705d-236">Delete child</span></span></p>
<p><span data-ttu-id="5705d-237">Удалить дерево</span><span class="sxs-lookup"><span data-stu-id="5705d-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="5705d-238">Службу</span><span class="sxs-lookup"><span data-stu-id="5705d-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5705d-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="5705d-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="5705d-240">Запись отображаемого текста</span><span class="sxs-lookup"><span data-stu-id="5705d-240">Write displayName</span></span></p>
<p><span data-ttu-id="5705d-241">Описание записи</span><span class="sxs-lookup"><span data-stu-id="5705d-241">Write description</span></span></p>
<p><span data-ttu-id="5705d-242">Напишите telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="5705d-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="5705d-243">Дочерние объекты пользователей</span><span class="sxs-lookup"><span data-stu-id="5705d-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5705d-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="5705d-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="5705d-245">Напишите Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="5705d-246">Напишите Осерипфоне</span><span class="sxs-lookup"><span data-stu-id="5705d-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="5705d-247">Запись отображаемого текста</span><span class="sxs-lookup"><span data-stu-id="5705d-247">Write displayName</span></span></p>
<p><span data-ttu-id="5705d-248">Описание записи</span><span class="sxs-lookup"><span data-stu-id="5705d-248">Write description</span></span></p>
<p><span data-ttu-id="5705d-249">Напишите telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="5705d-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="5705d-250">Напишите Мсексчуквоицемаилсеттингс</span><span class="sxs-lookup"><span data-stu-id="5705d-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="5705d-251">Напишите Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="5705d-252">Напишите Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="5705d-253">Напишите proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5705d-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="5705d-254">Дочерние объекты контактов</span><span class="sxs-lookup"><span data-stu-id="5705d-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="5705d-255">Предоставление разрешения для объектов InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="5705d-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="5705d-256">При запуске командлета **Grant-ксаупермиссион** для объектов inetOrgPerson в подразделении группам предоставляются разрешения, описанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="5705d-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="5705d-257">Разрешения, предоставленные для объектов InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="5705d-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5705d-258">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="5705d-258">Group</span></span></th>
<th><span data-ttu-id="5705d-259">PermissionSet</span><span class="sxs-lookup"><span data-stu-id="5705d-259">Permission</span></span></th>
<th><span data-ttu-id="5705d-260">Применимо к</span><span class="sxs-lookup"><span data-stu-id="5705d-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5705d-261">Ртчсуниверсалсервицес</span><span class="sxs-lookup"><span data-stu-id="5705d-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="5705d-262">Репликация изменений каталога</span><span class="sxs-lookup"><span data-stu-id="5705d-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="5705d-263">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5705d-264">Рткуниверсалсерверреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-265">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="5705d-265">List contents</span></span></p>
<p><span data-ttu-id="5705d-266">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="5705d-266">Read all properties</span></span></p>
<p><span data-ttu-id="5705d-267">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="5705d-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="5705d-268">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5705d-269">Рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-270">Содержимое списка</span><span class="sxs-lookup"><span data-stu-id="5705d-270">List contents</span></span></p>
<p><span data-ttu-id="5705d-271">Чтение всех свойств</span><span class="sxs-lookup"><span data-stu-id="5705d-271">Read all properties</span></span></p>
<p><span data-ttu-id="5705d-272">Разрешения на чтение</span><span class="sxs-lookup"><span data-stu-id="5705d-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="5705d-273">Только этот объект</span><span class="sxs-lookup"><span data-stu-id="5705d-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5705d-274">Рткуниверсалусерреадонлиграуп</span><span class="sxs-lookup"><span data-stu-id="5705d-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5705d-275">Прочитать Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="5705d-276">Прочитать Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="5705d-277">Прочитать Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="5705d-278">Чтение персональных данных</span><span class="sxs-lookup"><span data-stu-id="5705d-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="5705d-279">Чтение общедоступной информации</span><span class="sxs-lookup"><span data-stu-id="5705d-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="5705d-280">Чтение общих данных</span><span class="sxs-lookup"><span data-stu-id="5705d-280">Read General-Information</span></span></p>
<p><span data-ttu-id="5705d-281">Чтение ограничений для учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="5705d-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="5705d-282">Дочерние объекты inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="5705d-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5705d-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="5705d-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="5705d-284">Напишите Рткусерсеарчпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="5705d-285">Напишите Рткусерпровисионингпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="5705d-286">Напишите Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="5705d-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="5705d-287">Напишите proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5705d-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="5705d-288">Дочерние объекты inetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="5705d-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

