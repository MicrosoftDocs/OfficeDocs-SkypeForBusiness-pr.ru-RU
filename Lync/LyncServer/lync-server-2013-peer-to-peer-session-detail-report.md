---
title: 'Lync Server 2013: отчет об одноранговом сеансе'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca709ea2478d5ed2bdff2a80fbdc9c238d6e92cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a>Отчет по деталям однорангового сеанса в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-06_

Отчет по деталям однорангового сеанса (Peer-to-Peer Session Detail Report) предоставляет подробные сведения об одноранговом сеансе. Например, если выбрать сеанс обмена мгновенными сообщениями, то отчет предоставит сведения о количестве сообщений, отправленных в этом сеансе каждым из двух пользователей.

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Доступ к отчету по деталям однорангового сеанса

Отчет по деталям однорангового сеанса можно вызвать в любом из следующих отчетов (все они доступны на домашней странице отчетов мониторинга).

  - Отчет по запасам IP-телефонов (Phone Inventory Report)

  - Отчет по действиям пользователей (User Activity Report)

  - Отчет по контролю допуска звонков (Call Admission Control Report)

  - Отчет по списку сбоев (Failure List Report)

В отчете по деталям однорангового сеанса можно получить доступ к [диагностическим отчетам в Lync Server 2013](lync-server-2013-diagnostic-report.md) , щелкнув метрику диагностического отчета (Details) (сведения). Можно также вызвать отчет по основным сбоям (Top Failures Report), щелкнув одну из следующих метрик:

  - Отклик

  - Код диагностики

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Оптимальное использование отчета по деталям однорангового сеанса

В отчете по деталям однорангового сеанса имеется большое количество метрик, многие из которых могут быть незнакомы системным администраторам. Однако во многих случаях при наведении указателя мыши на метку метрики отображаются всплывающие подсказки, дающие краткое описание этой метрики.

Следует отметить, что фактические метрики, которые отображаются в конкретном отчете, будут зависеть от типа выбранного однорангового сеанса. Для сеанса аудио- или видеосвязи и для сеанса обмена мгновенными сообщениями будут отображаться разные наборы метрик.

Кроме того, поместив указатель мыши на метрику Response code (Код ответа) или Diagnostic ID (ИД диагностики), можно получить описание следующих значений.

</div>

<div>

## <a name="filters"></a>Фильтры

Фильтры отсутствуют. Фильтрация отчета по деталям однорангового сеанса не предусмотрена.

</div>

<div>

## <a name="session-information-metrics"></a>Метрики сведений о сеансе

В следующей таблице приведены сведения, которые предоставляются отчетом по деталям однорангового сеанса для каждого сеанса.

### <a name="session-information-metrics"></a>Метрики сведений о сеансе

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Pool FQDN (Полное доменное имя пула)</strong></p></td>
<td><p>Полное доменное имя пула регистратора или пограничного сервера, участвующего в сеансе.</p></td>
</tr>
<tr class="even">
<td><p><strong>Invite time (Время приглашения)</strong></p></td>
<td><p>Дата и время, когда было отправлено приглашение принять участие в сеансе.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Response time (Время ответа)</strong></p></td>
<td><p>Дата и время, когда было получено принятие приглашения.</p></td>
</tr>
<tr class="even">
<td><p><strong>From user (Пользователь-инициатор)</strong></p></td>
<td><p>SIP-адрес пользователя, начавшего сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>From user agent (Агент пользователя-инициатора)</strong></p></td>
<td><p>Программное обеспечение, использовавшееся конечной точкой пользователя, начавшего сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>Is From user internal (Пользователь-инициатор внутренний?)</strong></p></td>
<td><p>Указывает, вошел ли пользователь, начавший сеанс, во внутреннюю сеть.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Is From user integrated with desk phone (Пользователь-инициатор интегрирован со стационарным телефоном?)</strong></p></td>
<td><p>Указывает, интегрирована ли конечная точка пользователя, начавшего сеанс, с его стационарным телефоном.</p></td>
</tr>
<tr class="even">
<td><p><strong>Session Priority (Приоритет сеанса)</strong></p></td>
<td><p>Приоритет, назначенный сеансу. Возможные приоритеты: Unknown (Неизвестно); Non-Urgent (Несрочный); Normal (Обычный); Urgent (Срочный) и Emergency (Экстренный).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Response code (Код ответа)</strong></p></td>
<td><p>SIP-код ответа, отправленный при сбое сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Front end (Сервер переднего плана)</strong></p></td>
<td><p>Имя сервера переднего плана, использовавшегося в конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Capture time (Время регистрации)</strong></p></td>
<td><p>Дата и время регистрации сведений о сеансе.</p></td>
</tr>
<tr class="even">
<td><p><strong>End time (Время окончания)</strong></p></td>
<td><p>Дата и время окончания сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>To user (Пользователь-получатель)</strong></p></td>
<td><p>SIP-адрес пользователя, приглашенного принять участие в сеансе.</p></td>
</tr>
<tr class="even">
<td><p><strong>To user agent (Агент пользователя-получателя)</strong></p></td>
<td><p>Программное обеспечение, использовавшееся конечной точкой пользователя, приглашенного принять участие в сеансе.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Is To user internal (Пользователь-получатель внутренний?)</strong></p></td>
<td><p>Указывает, вошел ли пользователь, приглашенный принять участие в сеансе, во внутреннюю сеть.</p></td>
</tr>
<tr class="even">
<td><p><strong>Is To user integrated with desk phone (Пользователь-получатель интегрирован со стационарным телефоном?)</strong></p></td>
<td><p>Указывает, интегрирована ли конечная точка пользователя, приглашенного принять участие в сеансе, с его стационарным телефоном.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Is retried session (Повторный сеанс?)</strong></p></td>
<td><p>Указывает, являлся ли этот сеанс попыткой повтора сеанса, который завершился неудачно.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnostic ID</strong> (ИД диагностики)</p></td>
<td><p>Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки. Поместите указатель мыши на этот идентификатор, чтобы увидеть дополнительные сведения о нем.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a>Метрики для модальностей

В следующей таблице приведены сведения, которые предоставляются отчетом по деталям однорангового сеанса для всех модальностей сеанса.

### <a name="metrics-for-modalities"></a>Метрики для модальностей

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Возможность сортировки по этому показателю</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Модальности</strong></p></td>
<td><p>Нет</p></td>
<td><p>Модальности, использованные в сеансе, например, обмен мгновенными сообщениями или передача файла.</p></td>
</tr>
<tr class="even">
<td><p><strong>From user messages (Сообщения пользователя-инициатора)</strong></p></td>
<td><p>Нет</p></td>
<td><p>Количество сообщений, отправленных пользователем, начавшим сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>To user messages (Сообщения пользователя-получателя)</strong></p></td>
<td><p>Нет</p></td>
<td><p>Количество сообщений, отправленных пользователем, приглашенным принять участие в сеансе.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a>Метрики для диагностических отчетов

В следующей таблице приведены сведения, которые отчет по деталям однорангового сеанса предоставляет для каждого диагностического отчета.

### <a name="metrics-for-diagnostic-reports"></a>Метрики для диагностических отчетов

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Возможность сортировки по этому показателю</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Detail</strong></p></td>
<td><p>Нет</p></td>
<td><p>При нажатии этой метрики отображается диагностический отчет для данного сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>Report time (Время отчета)</strong></p></td>
<td><p>Нет</p></td>
<td><p>Дата и время создания отчета.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Запрос</strong></p></td>
<td><p>Нет</p></td>
<td><p>SIP-тип запроса. Например, INVITE или BYE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnostic ID (ИД диагностики)</strong></p></td>
<td><p>Нет</p></td>
<td><p>Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Content type</strong> (Тип содержимого)</p></td>
<td><p>Нет</p></td>
<td><p>Тип контента мультимедиа, использовавшегося в конференции. Например, распространенным типом контента является Application/sdp. Протокол SDP — это стандартный Интернет-протокол, используемый для объявления о сеансе, приглашения принять участие в сеансе и других форм инициации сеанса мультимедиа.</p></td>
</tr>
<tr class="even">
<td><p><strong>Reported by (Сообщил)</strong></p></td>
<td><p>Нет</p></td>
<td><p>Компьютер (клиент или сервер), который сообщил о проблеме.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

