---
title: 'Lync Server 2013: учетные записи пользователей, включенные для Lync Server'
description: 'Lync Server 2013: учетные записи пользователей, включенные для Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf87177c378ffe61715d5332d2fd23b1d8e6fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569875"
---
# <a name="user-accounts-enabled-for-lync-server-2013"></a>Учетные записи пользователей, включенные для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-04-18_

В подразделах этого раздела приводятся пошаговые процедуры для настройки пользовательских параметров, которые можно выполнить с помощью панели управления Lync Server 2013.

<div>


> [!IMPORTANT]  
> Вы не можете использовать панель управления Lync Server для управления пользователями, которые являются участниками группы администраторов домена Active Directory. Для пользователей домена Администраторы могут использовать панель управления Lync Server только для выполнения операций поиска, доступных только для чтения. Для выполнения операций записи для пользователей "Администраторы домена" (например, включить или отключить для панели управления Lync Server, изменить параметры пула или политики, параметры телефонии, SIP-адрес), необходимо использовать командлеты Windows PowerShell, войдя в систему как пользователь "Администраторы домена". Для получения дополнительных сведений об использовании командлетов Windows PowerShell для управления пользователями обратитесь к статье <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.



</div>

При выполнении любой административной задачи Lync Server 2013, которая включает поиск пользователя или фильтрацию результатов поиска пользователей, существуют некоторые свойства пользователя, которые существуют в качестве атрибутов в доменных службах Active Directory, но не реплицируются в глобальный каталог до развертывания Microsoft Exchange Server. Microsoft Exchange, а не Lync Server, помечает следующие атрибуты репликации в глобальном каталоге при его установке:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Сведения о пользователе</th>
<th>Адрес и телефон</th>
<th>Организация</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Initials</p></td>
<td><p>Адрес (улица, дом)</p>
<p>Страна или регион</p>
<p>Пейджер</p>
<p>Fax</p>
<p>Mobile</p></td>
<td><p>Название</p>
<p>Company</p>
<p>Отдел</p>
<p>Кабинет</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Содержание

  - [Просмотр сведений об учетных записях пользователей, включенных для Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Включение и отключение пользователей для Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Управление корпоративной голосовой связью для пользователей в Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Изменение свойств учетной записи пользователя в Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)

  - [Управление политикой внешнего доступа в Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Назначение политик для отдельных пользователей в Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Командлеты управления пользователями в Lync Server 2013](lync-server-2013-user-management-cmdlets.md)  


[Управление пользователями в Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

