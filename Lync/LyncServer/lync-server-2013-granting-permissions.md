---
title: 'Lync Server 2013: предоставление разрешений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccfdf804fc9052ac69b383d0f8cd3321222e79a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Предоставление разрешений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-15_

Для настройки можно предоставить разрешения на доступ к универсальной группе Рткуниверсалсерверадминс для определенного подразделения Active Directory (OU), включив в него членов группы Рткуниверсалсерверадминс для установки Lync Server 2013 в указанном домене. При предоставлении разрешений на доступ к подразделению предоставляются следующие разрешения:

  - Читаются

  - Пишу

  - реадспн

  - вритеспн

Для администрирования вы можете добавить разрешения для указанных подразделений, чтобы участники универсальных групп RTC, созданные с помощью подготовки леса, могли получать доступ к подразделениям без необходимости входить в группу администраторов домена. Разрешения, добавленные в указанный ОРГАНИЗАЦИОНный элемент, совпадают с разрешениями, которые командлет **Enable-ксаддомаин** добавляет к контейнерам OU Computers и Users.

<div>

## <a name="in-this-section"></a>Содержание

  - [Предоставление разрешений на установку в Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Предоставление разрешений организационного подразделения в Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

