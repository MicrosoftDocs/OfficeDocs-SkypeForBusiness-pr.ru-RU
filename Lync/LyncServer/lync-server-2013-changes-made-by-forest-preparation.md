---
title: 'Lync Server 2013: изменения, внесенные при подготовке леса'
description: 'Lync Server 2013: изменения, внесенные при подготовке леса.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c9bc40539c285e03610b2fc97166842473997fb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543655"
---
# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Изменения, внесенные при подготовке леса в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-30_

В данном разделе описываются глобальные параметры и объекты, а также универсальные группы служб и административные группы, создаваемые на этапе подготовки леса.

<div>

## <a name="active-directory-global-settings-and-objects"></a>Глобальные параметры и объекты Active Directory

Если глобальные параметры хранятся в контейнере конфигурации (как в случае со всеми новыми развертываниями Lync Server 2013), подготовка леса использует существующий контейнер служб и добавляет объект **службы RTC** в \\ объект Configuration Services. В объект RTC Service процедура подготовки лета добавляет объект **Global Settings** типа msRTCSIP-GlobalContainer. В глобальном объекте Settings хранятся все параметры, применимые к развертыванию Lync Server. Если глобальные параметры хранятся в контейнере System, то при подготовке леса используется контейнер Microsoft Container в контейнере System корневого домена и объект службы RTC в системном \\ объекте Майкрософт.

Процедура подготовки леса также добавляет новый объект **msRTCSIP-Domain** для корневого домена, в котором выполняется процедура.

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Универсальные группы служб и административные группы Active Directory

Процедура подготовки леса создает универсальные группы на основании указанного вами домена и добавляет для этих групп элементы управления доступом (ACE). На данном этапе универсальные группы создаются в контейнерах User указанного вами домена.

Универсальные группы позволяют администраторам осуществлять доступ к глобальным параметрам и службам и управлять ими. Процедура подготовки леса добавляет следующие типы универсальных групп:

  - **Административные группы**     Эти группы определяют роли администратора для сети Lync Server.

  - **Группы инфраструктуры**     Эти группы предоставляют разрешение на доступ к определенным областям инфраструктуры Lync Server. Они выступают в качестве компонентов административных групп. Вам не следует изменять эти группы или добавлять пользователей непосредственно в них.

  - **Группы служб**     Эти группы являются учетными записями служб, необходимыми для доступа к различным службам Lync Server.

В следующей таблице описываются административные группы.

### <a name="administrative-groups-created-during-forest-preparation"></a>Административные группы, созданные во время подготовки леса

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Административная группа</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Позволяет членам управлять параметрами серверов и пулов, включая все роли сервера, глобальные параметры и пользователей.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Позволяет членам управлять параметрами пользователей и перемещать пользователей из одного сервера или пула в другой.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Позволяет членам считывать параметры серверов, пулов и пользователей.</p></td>
</tr>
</tbody>
</table>


В следующей таблице описываются группы инфраструктуры.

### <a name="infrastructure-groups-created-during-forest-preparation"></a>Группы инфраструктуры, созданные во время подготовки леса

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Группа инфраструктуры</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>рткуниверсалглобалвритеграуп</p></td>
<td><p>Предоставляет доступ на запись к глобальным объектам параметров для Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Предоставляет доступ только для чтения к глобальным объектам Setting для Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Предоставляет доступ только для чтения к параметрам пользователя Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Предоставляет доступ только для чтения к параметрам Lync Server. Данная группа не имеет доступа к параметрам уровня пулов, ей доступны только параметры для отдельного сервера.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Предоставляет доступ только для чтения к конфигурации Lync Server и помещаются в группу локальных администраторов устройств для обеспечения связи в филиалах во время установки.</p></td>
</tr>
</tbody>
</table>


В следующей таблице описываются группы служб.

### <a name="service-groups-created-during-forest-preparation"></a>Группы служб, созданные во время подготовки леса

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Группа служб</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ртчсуниверсалсервицес</p></td>
<td><p>Включает учетные записи служб, используемые для запуска серверов переднего плана и серверов Standard Edition. Эта группа разрешает серверам доступ для чтения и записи к глобальным параметрам Lync Server и объектам пользователя Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Включает служебные учетные записи, используемые для выполнения серверов аудио-и видеоконференций, веб-служб, сервера-посредника, сервера архивации и сервера мониторинга.</p></td>
</tr>
<tr class="odd">
<td><p>рткпроксюниверсалсервицес</p></td>
<td><p>Включает учетные записи служб, используемые для запуска пограничных серверов Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>рткуниверсалконфигрепликатор</p></td>
<td><p>Включает серверы, которые могут участвовать в репликации центрального хранилища управления Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>ртксбауниверсалсервицес</p></td>
<td><p>Предоставляет доступ только для чтения к параметрам Lync Server, но позволяет настраивать установку сервера для обеспечения связи в филиалах и развертывания устройства в филиалах.</p></td>
</tr>
</tbody>
</table>


После этого процедура подготовки леса добавляет группы служб и административные группы в соответствующие группы инфраструктуры следующим образом:

  - RTCUniversalServerAdmins добавляется в RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

  - RTCUniversalUserAdmins добавляется в качестве члена групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

  - RTCHSUniversalServices, RTCComponentUniversalServices и RTCUniversalReadOnlyAdmins добавляются в качестве членов групп RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup и RTCUniversalUserReadOnlyGroup.

Процедура подготовки леса также создает следующие группы управления доступом на основе ролей:

  - CSAdministrator

  - Роли csarchivingadministrator

  - CSHelpDesk

  - кслокатионадминистратор

  - ксреспонсеграупадминистратор

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - ксперсистентчатадминистатор

  - CsResponseGroupManager

Подробные сведения о ролях RBAC и задачах, разрешенных для каждого из них, приведены в статье [Планирование управления доступом на основе ролей в Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) в документации по планированию.

Процедура подготовки леса создает как частные, так и общие элементы управления доступом. Он создает частные записи управления доступом в контейнере глобальных параметров, используемом Lync Server. Этот контейнер используется только Lync Server и находится в контейнере конфигурации или в контейнере System в корневом домене в зависимости от того, где хранятся глобальные параметры. В следующей таблице приведены общие элементы управления доступом, создаваемые процедурой подготовки леса.

### <a name="public-aces-created-by-forest-preparation"></a>Общие элементы управления доступом, создаваемые процедурой подготовки леса

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Чтение контейнера System корневого домена (не наследуется)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Чтение контейнера DisplaySpecifiers конфигурации (не наследуется)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>Элементы управления доступом, которые не являются унаследованными, не предоставляют доступ к дочерним объектам в этих контейнерах. Наследуемые элементы управления доступом предоставляют доступ к дочерним объектам в таких контейнерах.



</div>

В контейнере Configuration в контексте именования Configuration процедура подготовки леса выполняет следующие задачи:

  - Добавляет запись **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** для страницы **RTC property** в атрибутах adminContextMenu и adminPropertyPages описателя отображения языка для пользователей, контактов и InetOrgPersons (например, CN=user-Display,CN=409,CN=DisplaySpecifiers).

  - Добавляет объект **RTCPropertySet** типа **controlAccessRight** в **Extended-Rights**, применяемый к классам User и Contact.

  - Добавляет объект **RTCUserSearchPropertySet** типа **controlAccessRight** в **Extended-Rights**, применяемый к классам User, Contact, OU и DomainDNS.

  - Добавляет **msRTCSIP-PrimaryUserAddress** в атрибут **extraColumns** каждого описателя отображения языкового подразделения (например, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) и копирует значения атрибута **extraColumns** отображения по умолчанию (например, CN=default-Display, CN=409,CN=DisplaySpecifiers).

  - Добавляет атрибуты фильтрации **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** и **msRTCSIP-UserEnabled** в атрибут **attributeDisplayNames** каждого описателя отображения языка для объектов Users, Contacts и InetOrgPerson (например, для английского: CN=user-Display,CN=409,CN=DisplaySpecifiers).

</div>

</div>

<span> </span>

</div>

</div>

</div>

