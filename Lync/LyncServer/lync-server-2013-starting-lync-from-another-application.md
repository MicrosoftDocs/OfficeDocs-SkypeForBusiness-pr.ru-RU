---
title: 'Lync Server 2013: запуск Lync из другого приложения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40e049b2a8a88514b9236ee0172474a5252bfdb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>Запуск Lync из другого приложения

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

Вы можете использовать параметры командной строки для быстрого запуска Lync 2013. Например, если пользователь щелкает номер телефона в другом приложении, приложение может запустить экземпляр Lync 2013 и инициировать вызов этого номера.

Lync 2013 также может распознать список имен контактов, разделенных точкой с запятой, для конференц-связи с многоадресной связью.

Если Lync 2013 настроен на автоматический вход при запуске, то при запуске Lync 2013 с параметрами командной строки будет открыто главное окно Lync. Если Lync не настроен на автоматический вход при запуске, откроется окно входа.

В следующей таблице приведены доступные параметры.

### <a name="lync-2013-command-line-parameters"></a>Параметры командной строки Lync 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Расширение</th>
<th>Формат данных</th>
<th>Action</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel</p></td>
<td><p>универсальный код ресурса (URI) Tel</p></td>
<td><p>Открывает окно беседы для голосовой связи, но не набирает указанный номер.</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>Tel:, SIP: или типизированный URI TEL</p></td>
<td><p>Открывает окно беседы для голосовой связи, но не набирает указанный номер.</p></td>
</tr>
<tr class="odd">
<td><p>панели</p></td>
<td><p>Универсальный код ресурса (URI) SIP</p></td>
<td><p>Открывает окно беседы с указанным универсальным кодом ресурса (URI) SIP в списке участников.</p></td>
</tr>
<tr class="even">
<td><p>Sips</p></td>
<td><p>Универсальный код ресурса (URI) SIP</p></td>
<td><p>Если Lync 2013 настроен для использования протокола TLS, функционирует аналогично SIP:. Если протокол TLS не используется, отображается диалоговое окно, которое информирует пользователя о том, что необходим более высокий уровень безопасности.</p></td>
</tr>
<tr class="odd">
<td><p>дает</p></td>
<td><p>Универсальный код ресурса (URI) SIP конференции для присоединения</p></td>
<td><p>Если URI является самостоятельным, он создает фокус и выводит представление только для списка. В противном случае отображает представление списка, но не отправляет приглашение.</p></td>
</tr>
<tr class="even">
<td><p>обмена мгновенными сообщениями</p></td>
<td><p>Универсальный код ресурса (URI) SIP</p></td>
<td><p>Отображает окно беседы с URI SIP только для обмена мгновенными сообщениями. Принимает несколько URI SIP, указанных внутри угловых&lt;&gt;скобок () без разделителя.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


В следующей таблице приведены примеры этих параметров командной строки.

### <a name="command-line-parameter-examples"></a>Примеры параметров командной строки

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Экземпляр</th>
<th>Результаты</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel: + 14255550101</p></td>
<td><p>Открывает представление "только телефон" с + 14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Callto: Tel: + 14255550101</p></td>
<td><p>Открывает представление "только телефон" с + 14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Открывает только телефонное представление с kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Открывает окно беседы с kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf: SIP:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Открывает окно беседы и отображает варианты присоединения к собранию.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

