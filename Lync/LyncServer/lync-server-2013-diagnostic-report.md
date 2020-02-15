---
title: 'Lync Server 2013: диагностический отчет'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a906e131329df1b59c4ac6067a4696871f0bebfc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a>Диагностический отчет в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-07_

Диагностический отчет предоставляет сведения о сеансах, которые завершились с ошибкой. Эти сведения включают ИД диагностики и диагностический заголовок, переданные при сбое сеанса. ИД диагностики — это уникальный идентификатор (в виде заголовка ms-diagnostics), который возвращает добавленное сообщение SIP, а диагностический заголовок содержит дополнительное описание ИД диагностики. Отчет также может содержать дополнительные сведения об устранении неполадок, предоставляемые компонентом создания отчетов. Пример:

  - Код причины, предоставляемый шлюзом PSTN, которая привела к возникновению ошибки. Если происходит сбой в PSTN при обработке исходящего звонка, автоматически создается код причины ISUP. Например, шлюз PSTN может прислать код причины 34, говорящий о том, что для выполнения вызова нет доступного канала или цепи.

  - Полное доменное имя узла, порт и WinSock для ошибок подключения.

  - Запрашиваемые имена для ошибок разрешения DNS-имен. Разрешение DNS-имен выполняется при каждом обращении клиента к серверу имен и запросе IP-адреса, соответствующему указанному имени устройства.

<div>

## <a name="accessing-the-diagnostic-report"></a>Доступ к диагностическому отчету

Чтобы получить доступ к диагностическим отчетам, щелкните метрику диагностического отчета (Detail) в [отчете по деталям однорангового сеанса в Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) или подробный отчет по Конференции.

</div>

<div>

## <a name="filters"></a>Фильтры

Нет. В диагностическом отчете нельзя использовать фильтр.

</div>

<div>

## <a name="metrics"></a>Метрик

В следующей таблице перечислены сведения, содержащиеся в диагностическом отчете.

### <a name="diagnostic-report-metrics"></a>Показатели отчета Diagnostic Report (Диагностический отчет)

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
<td><p><strong>Reported time</strong> (Время создания отчета)</p></td>
<td><p>Нет</p></td>
<td><p>Дата и время создания отчета.</p></td>
</tr>
<tr class="even">
<td><p><strong>Response code</strong> (Код ответа)</p></td>
<td><p>Нет</p></td>
<td><p>Код ответа SIP, отправленный при сбое сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Request type</strong> (Тип запроса)</p></td>
<td><p>Нет</p></td>
<td><p>Тип запроса SIP, завершившегося с ошибкой. Например, INVITE, BYE или SERVICE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>Нет</p></td>
<td><p>Источник ошибки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>From user URI</strong> (URI пользователя, инициатора сеанса)</p></td>
<td><p>Нет</p></td>
<td><p>SIP-адрес пользователя, инициировавшего сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>From user agent</strong> (Агент пользователя, инициатора сеанса)</p></td>
<td><p>Нет</p></td>
<td><p>Программное обеспечение, используемое конечной точкой пользователя, инициировавшего сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnostic ID</strong> (ИД диагностики)</p></td>
<td><p>Нет</p></td>
<td><p>Уникальный идентификатор (в форме заголовка ms-diagnostics), присоединенный к сообщению SIP, который часто содержит сведения, помогающий устранять ошибки.</p></td>
</tr>
<tr class="even">
<td><p><strong>Content type</strong> (Тип содержимого)</p></td>
<td><p>Нет</p></td>
<td><p>Тип содержимого мультимедиа, которое привело к ошибке. Например, общий тип содержимого Application/sdp. Протокол SDP — это стандартный протокол Интернета, который используется для оповещений сеансов, приглашений сеансов и других видов инициирования сеансов мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application</strong></p></td>
<td><p>Нет</p></td>
<td><p>Приложение, используемое при возникновении ошибки.</p></td>
</tr>
<tr class="even">
<td><p><strong>To user URI</strong> (URI пользователя, получившего приглашение к сеансу)</p></td>
<td><p>Нет</p></td>
<td><p>SIP-адрес пользователя, получившего приглашение к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p>Время присоединения к конференции (мс)</p></td>
<td><p>Нет</p></td>
<td><p>Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnostic header</strong> (Заголовок диагностики)</p></td>
<td><p>Нет</p></td>
<td><p>Описание ИД диагностики.</p></td>
</tr>
</tbody>
</table>


Список ошибок диагностики можно найти на [странице заголовков MS-Diagnostics](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

