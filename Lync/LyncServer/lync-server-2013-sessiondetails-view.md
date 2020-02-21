---
title: 'Lync Server 2013: представление SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66d883b48d1269fff8a57594101f083c88f1fbd1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a>Представление SessionDetails в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

В представлении SessionDetails хранятся сведения об одноранговых сеансах, которые могут быть телефонным звонком VoIP, двусторонним сеансом обмена мгновенными сообщениями или другим типом сеансов. Это представление было представлено в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время запроса сеанса. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в таблице Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификационный номер для идентификации сеанса. Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>инвитетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время первого запроса INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO). Время первого запроса INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>фромури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, запустившего сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>таури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, который присоединился к сеансу.</p></td>
</tr>
<tr class="even">
<td><p><strong>фромуритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, запустившего сеанс. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>тауритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, который присоединился к сеансу. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>фромтенант</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Клиент пользователя, запустившего сеанс. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>тотенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, который присоединился к сеансу. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>фромендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор конечной точки пользователя, запустившего сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>тоендпоинтид</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>Уникальный идентификатор конечной точки пользователя, который присоединился к сеансу.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время окончания сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>фроммессажекаунт</strong></p></td>
<td><p>int</p></td>
<td><p>Число сообщений, отправленных пользователем, запустившим сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>томессажекаунт</strong></p></td>
<td><p>int</p></td>
<td><p>Число сообщений, отправленных пользователем, который присоединился к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>фромклиентверсион</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Версия клиента пользователя, запустившего сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>фромклиенттипе</strong></p></td>
<td><p>int</p></td>
<td><p>Версия клиента пользователя, который запустил сеанс. Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>фромклиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Имя категории клиента пользователя, запустившего сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>токлиентверсион</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Версия клиента пользователя, который присоединился к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>токлиенттипе</strong></p></td>
<td><p>int</p></td>
<td><p>Версия клиента пользователя, который присоединился к сеансу. Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>токлиенткатегори</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Имя категории клиента пользователя, который присоединился к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TargetUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI целевого пользователя сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>таржетуритипе</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Тип URI целевого пользователя сеанса. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>онбехалфофури</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, от имени которого был запущен сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>онннбехалфофуритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, от имени которого был запущен сеанс. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>онбехалфофтенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, от имени которого был запущен сеанс. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>реферредбюри</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI пользователя, который указал ссылку на сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>реферредбюритипе</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип URI пользователя, который указал ссылку на сеанс. Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>реферредбитенант</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Клиент пользователя, который указал ссылку на сеанс. Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>Код диалога SIP. Формат:</p>
<p>диалоговое окно; from — Tag; to – Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>ИД</strong></p></td>
<td><p>идентификатора</p></td>
<td><p>GUID, используемый для сопоставления нескольких сеансов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>реплацедиалогидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время диалога, который был заменен сеансом. Используется совместно с ReplaceDialogIdSeq для уникальной идентификации диалога, который был заменен сеансом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>реплацедиалогидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Идентификатор сеанса. Используется совместно с параметром ReplaceDialogIdTime для уникальной идентификации диалога, который был заменен сеансом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>реплацесдиалогид</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>Код диалога SIP, который заменяется сеансом. Формат:</p>
<p>диалоговое окно; from — Tag; to – Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>респонсетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Время ответа на первое сообщение INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>респонсекоде</strong></p></td>
<td><p>int</p></td>
<td><p>Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>диагностиЦид</strong></p></td>
<td><p>int</p></td>
<td><p>Код диагностики из заголовков SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Тип контента для этого сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Интерфейса</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя интерфейсного сервера, который получил данные этого сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ресурсов</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя пула, который получил данные этого сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>фромеджесервер</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя пограничного сервера, применяемого пользователем, запустившим сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>тоеджесервер</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Полное доменное имя пограничного сервера, применяемого пользователем, запустившим сеанс</p></td>
</tr>
<tr class="even">
<td><p><strong>исфроминтернал</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Указывает, вошел ли пользователь, запустивший сеанс, в систему из внутренней сети.</p></td>
</tr>
<tr class="odd">
<td><p><strong>истоинтернал</strong></p></td>
<td><p>Битовая</p></td>
<td><p>Указывает, вошел ли пользователь, который присоединился к сеансу, в систему из внутренней сети.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллприорити</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Приоритет вызова сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>фромусерфлаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Указывает атрибуты пользователя, начавшего сеанс. Допустимы следующие определения атрибутов:</p>
<p>0x01 — интегрировано со стационарным телефоном</p></td>
</tr>
<tr class="even">
<td><p><strong>таусерфлаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Указывает атрибуты пользователя, начавшего сеанс. Допустимы следующие определения атрибутов:</p>
<p>0x01 — интегрировано со стационарным телефоном</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллфлаг</strong></p></td>
<td><p>smallint</p></td>
<td><p>Указывает атрибуты вызова. Допустимы следующие определения атрибутов:</p>
<p>0x01 — повторенный сеанс</p>
<p>0x02 — вызов, выполненный агентом от имени группы ответа</p></td>
</tr>
<tr class="even">
<td><p><strong>Location</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Расположение экстренного звонка.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

