---
title: 'Lync Server 2013: определение требований для экстренных вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d190d240db85016bd13bfd2480b42b088ca5f88
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504366"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>Определение требований для экстренных вызовов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-06_

Прежде чем приступить к развертыванию Microsoft Lync Server 2013 E9 – 1 – 1, сначала необходимо ответить на вопросы, описанные в следующих разделах. Необходимое планирование зависит от типа решения E9-1-1, которое планируется разворачивать — канал SIP для подключения к поставщику услуг E9-1-1  или шлюз ELIN. В следующей таблице приведены разделы данного руководства по планированию, которые необходимо изучить для каждого из этих решений.

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a>Этапы планирования типа решения E9-1-1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Поставщик услуг по каналу SIP</th>
<th>Шлюз ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Определение области развертывания E9 – 1 – 1 в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Определение области развертывания E9 – 1 – 1 в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Определение сетевых элементов, используемых для определения расположения в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Определение сетевых элементов, используемых для определения расположения в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Включение пользователей для E9 – 1 — 1 в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Включение пользователей для E9 – 1 — 1 в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Управление расположениями для поставщиков услуг магистрали SIP в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Управление расположениями для шлюзов ELIN в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Определение пользовательского интерфейса для ручного получения расположения в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Определение пользовательского интерфейса для ручного получения расположения в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Проектирование магистрали SIP для E9 – 1 – 1 в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Включая службу безопасности в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Включая службу безопасности в Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Определение политики расположения для Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Выбор поставщика услуг E9 – 1 – 1 для Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Назначение области действия политики расположения в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Определение политики расположения для Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Назначение области действия политики расположения в Lync Server 2013</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Содержание

  - [Определение области развертывания E9 – 1 – 1 в Lync Server 2013](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [Определение сетевых элементов, используемых для определения расположения в Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [Включение пользователей для E9 – 1 — 1 в Lync Server 2013](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [Управление расположениями для поставщиков услуг магистрали SIP в Lync Server 2013](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [Управление расположениями для шлюзов ELIN в Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [Определение пользовательского интерфейса для ручного получения расположения в Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [Проектирование магистрали SIP для E9 – 1 – 1 в Lync Server 2013](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Включая службу безопасности в Lync Server 2013](lync-server-2013-including-the-security-desk.md)

  - [Выбор поставщика услуг E9 – 1 – 1 для Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [Определение политики расположения для Lync Server 2013](lync-server-2013-defining-the-location-policy.md)

  - [Назначение области действия политики расположения в Lync Server 2013](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

