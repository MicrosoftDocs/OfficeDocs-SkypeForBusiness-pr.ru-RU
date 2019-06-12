---
title: 'Lync Server 2013: запуск Lync из другого приложения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e2d28a8083a7e7f1e693ddf55c5cfe3e758e96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>Запуск Lync из другого приложения

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

Вы можете использовать параметры командной строки для быстрого запуска Lync 2013. Например, если пользователь щелкает номер телефона в другом приложении, приложение может запустить экземпляр Lync 2013 и инициировать Звонок на этот номер.

Lync 2013 также может распознать список имен контактов, разделенных точкой с запятой, для односторонних конференций.

Если Lync 2013 настроен на автоматический вход при запуске, то при запуске Lync 2013 с параметрами командной строки откроется главное окно Lync. Если Lync не настроен для автоматического входа при запуске, откроется окно входа.

В приведенной ниже таблице показаны доступные параметры.

### <a name="lync-2013-command-line-parameters"></a>Параметры командной строки Lync 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Добавоч</th>
<th>Формат данных</th>
<th>Действие</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel</p></td>
<td><p>универсальный код ресурса (URI) Tel</p></td>
<td><p>Открытие окна беседы для голосовой связи, но не набирает указанный номер.</p></td>
</tr>
<tr class="even">
<td><p>тегом "callto</p></td>
<td><p>URI TEL:, SIP: или Type Tel</p></td>
<td><p>Открытие окна беседы для голосовой связи, но не набирает указанный номер.</p></td>
</tr>
<tr class="odd">
<td><p>Установка</p></td>
<td><p>Универсальный код ресурса SIP</p></td>
<td><p>Открытие окна беседы с указанным универсальным кодом ресурса (URI) SIP в списке участников.</p></td>
</tr>
<tr class="even">
<td><p>Протоколов</p></td>
<td><p>Универсальный код ресурса SIP</p></td>
<td><p>Если Lync 2013 настроен на использование протокола TLS, функция работает точно так же, как SIP:. Если TLS не используется, откроется диалоговое окно с уведомлением о том, что требуется более высокий уровень безопасности.</p></td>
</tr>
<tr class="odd">
<td><p>CONF</p></td>
<td><p>Универсальный код ресурса (URI) для присоединения к Конференции</p></td>
<td><p>Если URI является самосозданием, он создает фокус и выводит представление только для списка. В противном случае выводится представление списка, но приглашение не отправляется.</p></td>
</tr>
<tr class="even">
<td><p>бесед</p></td>
<td><p>Универсальный код ресурса SIP</p></td>
<td><p>Отображается окно беседы с помощью URI SIP (только для обмена мгновенными сообщениями). Принимает несколько URI SIP, указанных в угловых&lt;&gt;скобках () без разделителя.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


В таблице ниже приведены примеры этих параметров командной строки.

### <a name="command-line-parameter-examples"></a>Примеры параметров командной строки

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Примеру</th>
<th>Поиска</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel: + 14255550101</p></td>
<td><p>Открытие представления "только для телефона" с + 14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Тегом "callto: Tel: + 14255550101</p></td>
<td><p>Открытие представления "только для телефона" с + 14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Открытие представления "только для телефона" с kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Открытие окна беседы с помощью kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf: SIP:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Открытие окна беседы и отображение параметров присоединения к звуковому каналу собрания.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

