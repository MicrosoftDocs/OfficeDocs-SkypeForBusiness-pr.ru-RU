---
title: 'Lync Server 2013: требования служб IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f4b51ac4996e2556ced3ad91e15a6cc58a1623c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Требования служб IIS в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-19_

Для некоторых компонентов Lync Server 2013 требуются информационные службы Интернета (IIS). В этой статье описаны особые возможности IIS, необходимые для поддержки сервера Lync Server. В подразделах этого раздела описаны требования конкретных компонентов IIS.

Если роль веб-сервера (IIS) включена в Windows Server 2008, по умолчанию устанавливаются различные службы ролей. В приведенной ниже таблице описаны дополнительные службы ролей, которые необходимо установить, если в Windows Server 2008 включена роль веб-сервера (IIS).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Служба ролей</th>
<th>Функция</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Основные возможности HTTP</p></td>
<td><p>Перенаправление HTTP</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Расширяемость .NET</p></td>
</tr>
<tr class="even">
<td><p>Разработка приложений</p></td>
<td><p>Расширения ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Разработка приложений</p></td>
<td><p>Фильтры ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Средства ведения журналов</p></td>
</tr>
<tr class="odd">
<td><p>Работоспособность и диагностика</p></td>
<td><p>Трассировка</p></td>
</tr>
<tr class="even">
<td><p>Безопасность</p></td>
<td><p>Обычная проверка подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Безопасность</p></td>
<td><p>Проверка подлинности Windows</p></td>
</tr>
<tr class="even">
<td><p>Средства управления</p></td>
<td><p>Сценарии и средства управления для служб IIS</p></td>
</tr>
<tr class="odd">
<td><p>Средства управления</p></td>
<td><p>Совместимость управления IIS 6</p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="разрешения" alt="security" />Примечание о безопасности:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если вы используете сервер IIS 7,0 в операционной системе Windows Server 2008, Настройка сервера Lync Server отключает проверку подлинности в режиме ядра в службах IIS.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Требования IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

