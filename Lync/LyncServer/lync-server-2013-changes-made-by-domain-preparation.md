---
title: 'Lync Server 2013: изменения, внесенные с помощью подготовки домена'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Изменения, внесенные в ходе подготовки домена в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2010-10-18_

В следующей таблице перечислены записи управления доступом (ACE), которые подготовка домена создает в корне домена. Все ACE наследуются, если не указано иное.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>ACE, добавленные в корень домена

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>РЕЗУЛЬТИРУЮЩ</th>
<th>Рткуниверсал — Усерреадонли-Group</th>
<th>Рткуниверсал — Серверреадонли-Group</th>
<th>Рткуниверсал-Усерадминс</th>
<th>Ртчсуниверсал — службы</th>
<th>Прошедшие проверку — пользователи</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Прочитать контейнер (не наследуется)</p></td>
<td><p><strong>Кнопки</strong></p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Чтение пользовательских свойств в пользовательском интерфейсе — ограничения для учетных записей</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Чтение личных сведений о пользовательском свойстве</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Чтение общих сведений о пользовательском свойстве</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Чтение общедоступной информации о пользовательском свойстве</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Чтение Рткусерсеарчпроперти-Set для пользовательского свойства</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
</tr>
<tr class="odd">
<td><p>Чтение Рткпропертисет свойств пользователя</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Написание прокси-сервера свойств пользователя — адреса</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Запись пользовательского свойства Рткусерсеарчпроперти-Set</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p>Написание пользовательского свойства Рткпропертисет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p>Чтение набора свойств DS-репликация — получение изменений для всех объектов Active Directory</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p><strong>Да</strong></p></td>
<td><p>Нет</p></td>
</tr>
</tbody>
</table>


В следующей таблице перечислены записи ACE, которые подготовка домена создает в трех встроенных контейнерах: пользователи, компьютеры и контроллеры домена. Все ACE наследуются, если не указано иное.

### <a name="aces-added-to-built-in-containers"></a>ACE, добавленные в встроенные контейнеры

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>РЕЗУЛЬТИРУЮЩ</th>
<th>Рткуниверсал — Усерреадонли-Group</th>
<th>Рткуниверсал — Серверреадонли-Group</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Прочитать контейнер (не наследуется)</p></td>
<td><p><strong>Кнопки</strong></p></td>
<td><p><strong>Да</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

