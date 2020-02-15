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

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Изменения, внесенные с помощью Grant – CsOUPermission в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-20_

Чтобы делегировать администрирование Lync Server 2013, можно добавить разрешения для указанных подразделений, чтобы участники универсальных групп RTC, созданные при подготовке леса, могли получать доступ к подразделениям, не открывая группу "Администраторы домена".

Командлет **Grant-CsOuPermission** предоставляет разрешения объектам в указанном подразделении, как указано в следующих таблицах.

<div>

## <a name="granting-permission-for-user-objects"></a>Предоставление разрешений для объектов-пользователей

При запуске командлета **Grant-CsOuPermission** для объектов-пользователей в подразделении группам предоставляются разрешения, как показано в следующей таблице.

### <a name="permissions-granted-for-user-objects"></a>Разрешения, предоставленные объектам-пользователям

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>Разрешение</th>
<th>Применимо к</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ртчсуниверсалсервицес</p></td>
<td><p>Репликация изменений каталога</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Чтение RTCUserSearchPropertySet</p>
<p>Чтение RTCUserProvisioningPropertySet</p>
<p>Чтение RTCPropertySet</p>
<p>Чтение Public-Information</p>
<p>Чтение General-Information</p>
<p>Чтение User-Account-Restrictions</p></td>
<td><p>К дочерним объектам-пользователям</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Запись RTCUserSearchPropertySet</p>
<p>Запись msExchUCVoiceMailSettings</p>
<p>Запись RTCUserProvisioningPropertySet</p>
<p>Запись RTCPropertySet</p>
<p>Запись proxyAddresses</p></td>
<td><p>К дочерним объектам-пользователям</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>Предоставление разрешений для объектов-компьютеров

При запуске командлета **Grant-CsOuPermission** для объектов-компьютеров в подразделении группам предоставляются разрешения, как показано в следующей таблице.

### <a name="permissions-granted-for-computer-objects"></a>Разрешения, предоставленные объектам-компьютерам

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>Разрешение</th>
<th>Применимо к</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ртчсуниверсалсервицес</p></td>
<td><p>Репликация изменений каталога</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Чтение Public-Information</p>
<p>Чтение Validated-DNS-Host-Name</p></td>
<td><p>К дочерним объектам-компьютерам</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Чтение Public-Information</p>
<p>Чтение Validated-DNS-Host-Name</p></td>
<td><p>К дочерним объектам-компьютерам</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Предоставление разрешений для контактных объектов  или объектов AppContact

При запуске командлета **Grant-CsOuPermission** для контактных объектов и объектов AppContact в подразделении группам предоставляются разрешения, как показано в следующей таблице.

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>Разрешения, предоставленные контактным объектам и объектам AppContact

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>Разрешение</th>
<th>Применимо к</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ртчсуниверсалсервицес</p></td>
<td><p>Репликация изменений каталога</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Чтение RTCUserSearchPropertySet</p>
<p>Чтение RTCUserProvisioningPropertySet</p>
<p>Чтение RTCPropertySet</p>
<p>Чтение Public-Information</p>
<p>Чтение General-Information</p>
<p>Чтение Personal-Information</p>
<p>Чтение User-Account-Restrictions</p></td>
<td><p>К дочерним контактным объектам</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Запись RTCUserSearchPropertySet</p>
<p>Запись otherIpPhone</p>
<p>Запись displayName</p>
<p>Запись description</p>
<p>Запись telephoneNumber</p>
<p>Запись msExchUCVoiceMailSettings</p>
<p>Запись RTCUserProvisioningPropertySet</p>
<p>Запись RTCPropertySet</p>
<p>Запись proxyAddresses</p></td>
<td><p>К дочерним контактным объектам</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>Предоставление разрешений для объектов-устройств

При запуске командлета **Grant-CsOuPermission** для объектов-устройств в подразделении группам предоставляются разрешения, как показано в следующей таблице.

### <a name="permissions-granted-for-device-objects"></a>Разрешения, предоставленные объектам-устройствам

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>Разрешение</th>
<th>Применимо к</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ртчсуниверсалсервицес</p></td>
<td><p>Репликация изменений каталога</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Чтение RTCUserSearchPropertySet</p>
<p>Чтение RTCUserProvisioningPropertySet</p>
<p>Чтение RTCPropertySet</p>
<p>Чтение Public-Information</p>
<p>Чтение Personal-Information</p>
<p>Чтение General-Information</p>
<p>Чтение User-Account-Restrictions</p></td>
<td><p>К дочерним контактным объектам</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Создание дочернего объекта</p>
<p>Удаление дочернего объекта</p>
<p>Удаление дерева</p></td>
<td><p>Контакт</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Запись displayName</p>
<p>Запись description</p>
<p>Запись telephoneNumber</p></td>
<td><p>К дочерним объектам-пользователям</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Запись RTCUserSearchPropertySet</p>
<p>Запись otherIpPhone</p>
<p>Запись displayName</p>
<p>Запись description</p>
<p>Запись telephoneNumber</p>
<p>Запись msExchUCVoiceMailSettings</p>
<p>Запись RTCUserProvisioningPropertySet</p>
<p>Запись RTCPropertySet</p>
<p>Запись proxyAddresses</p></td>
<td><p>К дочерним контактным объектам</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>Предоставление разрешений для объектов inetOrgPerson

При запуске командлета **Grant-CsOuPermission** для объектов inetOrgPerson в подразделении группам предоставляются разрешения, как показано в следующей таблице.

### <a name="permissions-granted-for-inetorgperson-objects"></a>Разрешения, предоставленные объектам inetOrgPerson

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>Разрешение</th>
<th>Применимо к</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ртчсуниверсалсервицес</p></td>
<td><p>Репликация изменений каталога</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Содержимое списка</p>
<p>Чтение всех свойств</p>
<p>Разрешения на чтение</p></td>
<td><p>Только к этому объекту</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Чтение RTCUserSearchPropertySet</p>
<p>Чтение RTCUserProvisioningPropertySet</p>
<p>Чтение RTCPropertySet</p>
<p>Чтение Personal-Information</p>
<p>Чтение Public-Information</p>
<p>Чтение General-Information</p>
<p>Чтение User-Account-Restrictions</p></td>
<td><p>К дочерним объектам inetOrgPerson</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Запись RTCUserSearchPropertySet</p>
<p>Запись RTCUserProvisioningPropertySet</p>
<p>Запись RTCPropertySet</p>
<p>Запись proxyAddresses</p></td>
<td><p>К дочерним объектам inetOrgPerson</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

