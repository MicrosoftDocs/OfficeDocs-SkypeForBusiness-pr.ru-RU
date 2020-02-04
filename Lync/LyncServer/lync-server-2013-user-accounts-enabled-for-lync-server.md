---
title: 'Lync Server 2013: учетные записи пользователей, включенные для Lync Server'
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
ms.openlocfilehash: 613d6350fcb405b1ae8beef78c3ee8c8a64a084c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>Учетные записи пользователей, включенные для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-04-18_

В этой статье приведены пошаговые инструкции по настройке параметров пользователей, которые можно выполнить с помощью панели управления Lync Server 2013.

<div>


> [!IMPORTANT]  
> Вы не можете использовать панель управления Lync Server для управления пользователями, которые являются членами группы администраторов домена Active Directory. Для пользователей, которые являются администраторами домена, можно использовать панель управления Lync Server только для выполнения операций поиска, предназначенных только для чтения. Для выполнения операций записи на пользователей администраторов домена (например, включить или отключить для панели управления Lync Server, изменить параметры пула или политики, настройки телефонной связи, адрес SIP) необходимо использовать командлеты Windows PowerShell, войдя в систему как пользователь с учетной записью администратора домена. Подробнее об использовании командлетов Windows PowerShell для управления пользователями можно узнать в разделе <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.



</div>

При выполнении любой административной задачи Lync Server 2013, которая включает в себя поиск пользователя или фильтрацию результатов поиска пользователей, в доменных службах Active Directory используются некоторые свойства пользователя, которые не реплицируются в глобальный каталог. пока не будет выполнено развертывание сервера Microsoft Exchange Server. Microsoft Exchange, а не Lync Server, помечает следующие атрибуты репликации в глобальный каталог после установки.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Сведения о пользователе</th>
<th>Адрес и номер телефона</th>
<th>Организация</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Инициалы</p></td>
<td><p>Почтовый адрес</p>
<p>Страна или регион</p>
<p>Оператора</p>
<p>Сообщений</p>
<p>Мобильный</p></td>
<td><p>Название</p>
<p>Между</p>
<p>Отдел</p>
<p>Office</p></td>
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

  - [Назначение политик для пользователей в Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

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

