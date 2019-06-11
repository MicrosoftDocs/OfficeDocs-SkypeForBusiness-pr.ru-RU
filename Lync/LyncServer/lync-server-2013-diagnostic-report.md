---
title: 'Lync Server 2013: диагностический отчет'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b314bccb0c1df539598e17ffc8ca12b30287b8eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a>Диагностический отчет в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-07_

Диагностический отчет предоставляет сведения о сеансах, которые завершились с ошибкой. Эти сведения включают ИД диагностики и диагностический заголовок, переданные при сбое сеанса. ИД диагностики – это уникальный идентификатор (в виде заголовка ms-diagnostics), который возвращает добавленное сообщение SIP, а диагностический заголовок содержит дополнительное описание ИД диагностики. Отчет также может содержать дополнительные сведения об устранении неполадок, предоставляемые компонентом создания отчетов. Пример:

  - Код причины, предоставляемый шлюзом PSTN, которая привела к возникновению ошибки. Если происходит сбой в PSTN при обработке исходящего звонка, автоматически создается код причины ISUP. Например, шлюз PSTN может прислать код причины 34, говорящий о том, что для выполнения вызова нет доступного канала или цепи.

  - Полное доменное имя узла, порт и WinSock для ошибок подключения.

  - Запрашиваемые имена для ошибок разрешения DNS-имен. Разрешение DNS-имен выполняется при каждом обращении клиента к серверу имен и запросе IP-адреса, соответствующему указанному имени устройства.

<div>

## <a name="accessing-the-diagnostic-report"></a>Доступ к диагностическому отчету

Отчет о диагностике можно получить, щелкнув метрику диагностического отчета (подробности) в отчете о одноранговых [сеансах в Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) или в отчете "сведения о конференции".

</div>

<div>

## <a name="filters"></a>Фильтры

Нет. В диагностическом отчете нельзя использовать фильтр.

</div>

<div>

## <a name="metrics"></a>Показатели

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
<th>Поддержка сортировки</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Время создания отчета</strong></p></td>
<td><p>Нет</p></td>
<td><p>Дата и время создания отчета.</p></td>
</tr>
<tr class="even">
<td><p><strong>Код ответа</strong></p></td>
<td><p>Нет</p></td>
<td><p>Код ответа SIP, отправленный при сбое сеанса.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Тип запроса</strong></p></td>
<td><p>Нет</p></td>
<td><p>Тип запроса SIP, завершившегося с ошибкой. Например, INVITE, BYE или SERVICE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Источник</strong></p></td>
<td><p>Нет</p></td>
<td><p>Источник ошибки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI пользователя, инициатора сеанса</strong></p></td>
<td><p>Нет</p></td>
<td><p>SIP-адрес пользователя, инициировавшего сеанс.</p></td>
</tr>
<tr class="even">
<td><p><strong>Агент пользователя, инициатора сеанса</strong></p></td>
<td><p>Нет</p></td>
<td><p>Программное обеспечение, используемое конечной точкой пользователя, инициировавшего сеанс.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ИД диагностики</strong></p></td>
<td><p>Нет</p></td>
<td><p>Прикрепленный к SIP-сообщению уникальный идентификатор (в форме заголовка ms-diagnostics), который часто содержит информацию, полезную при поиске и устранении ошибок.</p></td>
</tr>
<tr class="even">
<td><p><strong>Тип содержимого</strong></p></td>
<td><p>Нет</p></td>
<td><p>Тип содержимого мультимедиа, которое привело к ошибке. Например, общий тип содержимого Application/sdp. Протокол SDP – это стандартный протокол Интернета, который используется для оповещений сеансов, приглашений сеансов и других видов инициирования сеансов мультимедиа.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Приложение</strong></p></td>
<td><p>Нет</p></td>
<td><p>Приложение, используемое при возникновении ошибки.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI пользователя, получившего приглашение к сеансу</strong></p></td>
<td><p>Нет</p></td>
<td><p>SIP-адрес пользователя, получившего приглашение к сеансу.</p></td>
</tr>
<tr class="odd">
<td><p>Время присоединения к конференции (мс)</p></td>
<td><p>Нет</p></td>
<td><p>Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Заголовок диагностики</strong></p></td>
<td><p>Нет</p></td>
<td><p>Описание ИД диагностики.</p></td>
</tr>
</tbody>
</table>


Список ошибок диагностики можно найти на странице заголовков [MS-Diagnostics](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

