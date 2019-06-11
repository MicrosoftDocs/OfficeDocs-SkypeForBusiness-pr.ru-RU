---
title: 'Lync Server 2013: изменения, внесенные пользователем Grant-Кссетуппермиссион'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc63cf814f2bd901ab9753fe0f4501e7f44e2189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Изменения, внесенные функцией Grant-Кссетуппермиссион в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-20_

Для делегирования настройки вы можете предоставить разрешения на доступ к универсальной группе Рткуниверсалсерверадминс для определенного подразделения Active Directory (OU), включив в него членов группы Рткуниверсалсерверадминс для установки Lync Server 2013 в указанном домен, не являющийся членом группы администраторов домена.

Командлет **Grant-кссетуппермиссион** предоставляет разрешения на доступ к группе рткуниверсалсерверадминс на подразделение, как указано в приведенной ниже таблице.

### <a name="permissions-granted-to-objects-in-the-ou"></a>Разрешения, предоставленные объектам в подразделении

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Разрешения применяются к:</th>
<th>Предоставлены следующие разрешения:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Специальный доступ:</p>
<ul>
<li><p>Чтение передаваемые по себе</p></li>
<li><p>Вводный текст</p></li>
<li><p>Удалить дерево</p></li>
<li><p>Репликация изменений каталога</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Дочерние объекты serviceConnectionPoint</p></td>
<td><p>Специальный доступ:</p>
<ul>
<li><p>Разрешения на чтение</p></li>
<li><p>Разрешения на запись</p></li>
<li><p>Создание дочернего элемента</p></li>
<li><p>Удалить дочерний элемент</p></li>
<li><p>Содержимое списка</p></li>
<li><p>Запись свойства</p></li>
<li><p>Чтение свойства</p></li>
<li><p>Удалить дерево</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Дочерние объекты msRTCSIP-Server</p></td>
<td><p>Специальный доступ:</p>
<ul>
<li><p>Запись свойства</p></li>
<li><p>Чтение свойства</p></li>
<li><p>Удалить дерево</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Дочерние msRTCSIP — объекты-компоненты</p></td>
<td><p>Специальный доступ:</p>
<ul>
<li><p>Запись свойства</p></li>
<li><p>Чтение свойства</p></li>
<li><p>Удалить дерево</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Дочерние объекты msRTCSIP-MCU</p></td>
<td><p>Специальный доступ:</p>
<ul>
<li><p>Запись свойства</p></li>
<li><p>Чтение свойства</p></li>
<li><p>Удалить дерево</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Дочерние объекты msRTCSIP-Медиатионсервер</p></td>
<td><p>Специальный доступ:</p>
<ul>
<li><p>Запись свойства</p></li>
<li><p>Чтение свойства</p></li>
<li><p>Удалить дерево</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Дочерние объекты msRTCSIP-Аппликатионсервер</p></td>
<td><p>Специальный доступ:</p>
<ul>
<li><p>Запись свойства</p></li>
<li><p>Чтение свойства</p></li>
<li><p>Удалить дерево</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Дочерние объекты msRTCSIP-Коннектионпоинт</p></td>
<td><p>Специальный доступ:</p>
<ul>
<li><p>Запись свойства</p></li>
<li><p>Чтение свойства</p></li>
<li><p>Удалить дерево</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Дочерние объекты компьютера</p></td>
<td><p>Специальный доступ для serviceConnectionPoint:</p>
<ul>
<li><p>Создание дочерних объектов</p></li>
<li><p>Удаление дочерних объектов</p></li>
<li><p>Удалить дерево</p></li>
</ul>
<p>Специальный доступ к общедоступным сведениям:</p>
<ul>
<li><p>Чтение свойства</p></li>
</ul>
<p>Особый доступ для DNS-имени узла:</p>
<ul>
<li><p>Чтение свойства</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

