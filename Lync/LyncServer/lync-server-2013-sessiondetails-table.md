---
title: 'Lync Server 2013: таблица SessionDetails'
description: 'Lync Server 2013: таблица SessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569935"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a>Таблица SessionDetails в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Каждая запись представляет одноранговый сеанс, которым может быть телефонный звонок VoIP-VoIP, двухсторонний сеанс обмена мгновенными сообщениями или друг тип сеанса. Вы можете выполнить присоединение таблицы к [таблице Media в Lync Server 2013](lync-server-2013-media-table.md) , чтобы найти подробные сведения о каждом из них, участвующих в этом сеансе.

Обратите внимание на то, что поля IsUser1IntegratedWithDeskPhone и IsUser2IntegratedWithDeskPhone удалены из таблицы SessionDetails, используемой в Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ или индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>сессионидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Время запроса сеанса. В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Основной, внешний</p></td>
<td><p>Идентификатор для идентификации сеанса. Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации сеанса. * Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ИД</strong></p></td>
<td><p>идентификатора</p></td>
<td></td>
<td><p>GUID для корреляции нескольких сеансов.</p></td>
</tr>
<tr class="even">
<td><p><strong>реплацедиалогидтиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификационный номер для определения диалога, замененного текущим сеансом. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>реплацедиалогидсек</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор для идентификации сеанса. Используется в сочетании с <strong>ReplacesDialogIdTime</strong> для уникальной идентификации сеанса. Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1Id</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор одного пользователя в сеансе. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор другого пользователя в сеансе. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>Идентификатора</p></td>
<td></td>
<td><p>GUID, идентифицирующий конечную точку, применяемую первым пользователем в сеансе.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>Идентификатора</p></td>
<td></td>
<td><p>GUID, идентифицирующий конечную точку, применяемую вторым пользователем в сеансе.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>URI-адрес исходного вызываемого пользователя в SIP-запросе. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>сессионстартедбид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор пользователя, инициировавшего сеанс. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>онбехалфофид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Определяет идентификатор пользователя, которого представляет вызывающий абонент. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>реферредбид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор пользователя, который ссылается на вызов. Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор сервера переднего плана, используемого для этого сеанса. Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>пулид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Идентификатор пула, в котором был записан сеанс. Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Тип контента, используемый в сеансе. Для получения дополнительных сведений см <a href="lync-server-2013-contenttypes-table.md">таблицу ContentTypes в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Версия клиента, применяемая пользователем User1. Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Версия клиента, применяемая пользователем User2. Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Пограничный сервер, применяемый пользователем User1. Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Пограничный сервер, применяемый пользователем User2. Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Вошел ли пользователь User1 из внутренней сети или нет.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Вошел ли пользователь User2 из внутренней сети или нет.</p></td>
</tr>
<tr class="odd">
<td><p><strong>инвитетиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время первого запроса INVITE. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO). Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>респонсетиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время ответа на первое сообщение INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>диагностиЦид</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Идентификатор диагностики из заголовка SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллприорити</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Приоритет звонка. Дополнительные сведения см. <a href="lync-server-2013-callpriorities-table.md">в таблице таблица callpriorities в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Число сообщений, отправленных пользователем User1 в сеансе.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Число сообщений, отправленных пользователем User2 в сеансе.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионендтиме</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Время окончания сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Бит, указывающий тип носителя этого сеанса. Дале перечислены определения типов:</p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>"IM" (Обмен мгновенными сообщениями);</p></td>
<td><p>1,1</p></td>
</tr>
<tr class="even">
<td><p>FILE_TRANSFER</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>REMOTE_ASSISTANCE</p></td>
<td><p>4 </p></td>
</tr>
<tr class="even">
<td><p>APP_SHARING</p></td>
<td><p>8 </p></td>
</tr>
<tr class="odd">
<td><p>ПРОИЗВЕДЕН</p></td>
<td><p>16 </p></td>
</tr>
<tr class="even">
<td><p>ВИДЕОМАТЕРИАЛ</p></td>
<td><p>32</p></td>
</tr>
<tr class="odd">
<td><p>APP_INVITE</p></td>
<td><p>64</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>User1Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Бит, обозначающий атрибуты пользователя User1. Далее перечислены определения атрибутов:</p>
<ul>
<li><p>0x01 — интегрировано со стационарным телефоном</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Бит, обозначающий атрибуты пользователя User2. Далее перечислены определения атрибутов:</p>
<ul>
<li><p>0x01 — интегрировано со стационарным телефоном</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>каллфлаг</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Бит, обозначающий атрибуты пользователя User2. Далее перечислены определения атрибутов:</p>
<ul>
<li><p>0x01 — повторенный сеанс</p></li>
<li><p>0x02 — вызов, выполненный агентом от имени группы ответа</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Обработать</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Для внутреннего использования службой мониторинга.</p>
<p>Это поле было введено в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\* Для большинства сеансов Сессионидсек будет иметь значение 1. Если несколько сеансов начинаются в одно и то же время, для одного из них SessionIdSeq будет иметь значение 1, для другого — 2 и т. д.

</div>

<span> </span>

</div>

</div>

</div>

