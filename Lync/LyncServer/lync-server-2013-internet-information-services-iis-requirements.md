---
title: 'Lync Server 2013: требования к службам IIS'
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
ms.openlocfilehash: 9a086713c4c4c1ea5752c7e1b46ce46e48a0ea42
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Требования к службам IIS в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-19_

Для некоторых компонентов Lync Server 2013 требуются информационные службы Интернета (IIS). В этом разделе описываются конкретные компоненты IIS, необходимые для поддержки Lync Server. В подразделах данного раздела рассматриваются требования отдельных компонентов к службам IIS.

Когда на Windows Server 2008 включена роль «Веб-сервер (IIS)», по умолчанию устанавливаются различные службы роли. В следующей таблице описываются дополнительные службы роли, которые следует установить при включении роли «Веб-сервер (IIS)» в Windows Server 2008.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Служба роли</th>
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
<td><p>Средства ведения журнала</p></td>
</tr>
<tr class="odd">
<td><p>Проверка работоспособности и диагностика</p></td>
<td><p>Образца</p></td>
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
<td><p>Сценарии и средства управления IIS</p></td>
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
<th><img src="images/Gg398321.security(OCS.15).gif" title="защиты" alt="security" />Примечание о безопасности:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если вы используете IIS 7,0 в операционной системе Windows Server 2008, программа установки Lync Server отключает проверку подлинности в режиме ядра в службах IIS.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Требования к службам IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

