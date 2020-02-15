---
title: 'Lync Server 2013: таблица MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3496b8fe96e2bdfcbb49ec0155d66ad4eeb106fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a>Таблица MediaLine в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-21_

Каждая запись представляет одну линию мультимедиа. (Один звуковой сеанс обычно содержит одну линию звукового носителя). Один сеанс аудио-и видеоданных (A/V) обычно содержит одну линию аудио-и видеоконференций, хотя в этом сеансе могут содержаться две видеолинии, если используется устройство для конференц-связи или если используется представление галереи.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Column</strong></th>
<th><strong>Тип данных</strong></th>
<th><strong>Ключ или индекс</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>конференцедатетиме</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-session-table.md">таблицы Sessions в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>сессионсек</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Ссылка из <a href="lync-server-2013-session-table.md">таблицы Sessions в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>медиалинелабел</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>0 — это основной звук, 1 — основной видеоролик, а 2 — панорамное видео, 3 — общий доступ к приложениям и рабочим столам. Эта метка должна быть уникальной в пределах одного сеанса.</p></td>
</tr>
<tr class="even">
<td><p><strong>коннективитице</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Этот столбец присутствует, но не используется в Microsoft Lync Server 2013. Сведения о подключении, используемом для линии мультимедиа, записываются в столбцах Каллерконнективитице и Калликоннективитице.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллерицеварнингфлагс</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Сведения о процессе интерактивной установки подключения (ICE), описанные в разделе Флаги BITS. Дополнительные сведения можно найти в <em>спецификации протокола сервера мониторинга качества взаимодействия</em>, доступной для загрузки.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллиицеварнингфлагс</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>То же, что и Каллерицеварнингфлагс, но на стороне вызываемого абонента. Дополнительные сведения можно найти в <em>спецификации протокола сервера мониторинга качества взаимодействия</em>, доступной для загрузки.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Безопасность</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Используемый профиль безопасности. 0 – это NONE, 1 – SRTP, 2 – V1.</p></td>
</tr>
<tr class="even">
<td><p><strong>Transport</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 соответствует протоколу UDP, 1 – протоколу TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллерипаддр</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>IP-адрес вызывающего абонента. Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>каллерпорт</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Порт, используемый вызывающим абонентом.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллерсубнет</strong></p></td>
<td><p>int</p></td>
<td><p> Правительства</p></td>
<td><p>Подсеть вызывающего абонента. Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>каллеринсиде</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>1 означает, что вызывающий абонент находится внутри корпоративной сети, 0 означает, что вызывающий абонент находится за пределами сети.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллермакаддресс</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Mac-адрес вызывающего абонента, на который ссылается <a href="lync-server-2013-macaddress-table.md">Таблица MacAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллеррелайипаддр</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>IP-адрес пограничной службы Lync Server A/V, используемой вызывающим абонентом. Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллеррелайпорт</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Порт, используемый вызывающим абонентом для пограничной службы аудио-и видеоданных.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллеркаптуредев</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Устройство захвата, используемое вызывающим абонентом. Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллеррендердев</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Устройство отображения, используемое вызывающим абонентом. Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллеркаптуредевдривер</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Драйвер устройства захвата вызывающего абонента, на который ссылается <a href="lync-server-2013-devicedriver-table.md">таблица таблица devicedriver в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллеррендердевдривер</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Драйвер для устройства отрисовки вызывающего абонента, на который ссылается <a href="lync-server-2013-devicedriver-table.md">таблица таблица devicedriver в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллернетворкконнектионтипе</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Правительства</p></td>
<td><p>Показывает, как вызывающий абонент подключился к сети. Значения берутся из <a href="lync-server-2013-networkconnectiondetail-table.md">таблицы нетворкконнектиондетаил в Lync Server 2013</a>. Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллербссид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>BSSID для вызывающего абонента при использовании беспроводной связи. Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллервпн</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Ссылка вызывающего абонента. 1 – подключен к виртуальной частной сети, 0 – не подключен к виртуальной частной сети.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллерлинкспид</strong></p></td>
<td><p>десятичное число (18, 0)</p></td>
<td></td>
<td><p>Скорость сетевого соединения в бит/с для конечной точки вызывающего абонента.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллиипаддр</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>IP-адрес приемника вызовов. Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллипорт</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Порт, используемый приемником вызовов.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллисубнет</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Подсеть вызываемого абонента. Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллиинсиде</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>1 означает, что получатель вызова находится внутри корпоративной сети, 0 означает, что приемник вызовов находится за пределами сети.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллимакаддресс</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Mac-адрес вызываемого абонента. Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллирелайипаддр</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>IP-адрес пограничной службы аудио-и видеоданных, используемой приемником вызовов. Дополнительные сведения см. <a href="lync-server-2013-ipaddress-table.md">в таблице IPAddress в Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>каллирелайпорт</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Порт, используемый приемником вызовов для пограничной службы аудио-и видеоданных.</p></td>
</tr>
<tr class="odd">
<td><p><strong>калликаптуредев</strong></p></td>
<td><p>int</p></td>
<td><p>правительства</p></td>
<td><p>Устройство захвата, используемое приемником вызовов. Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллирендердев</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Устройство отображения, используемое приемником вызовов. Ссылка из <a href="lync-server-2013-device-table.md">таблицы устройств в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>калликаптуредевдривер</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Драйвер устройства захвата приемника вызовов. Ссылка из <a href="lync-server-2013-devicedriver-table.md">таблицы таблица devicedriver в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллирендердевдривер</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Правительства</p></td>
<td><p>Драйвер устройства обработки для приемника вызовов. Ссылка из <a href="lync-server-2013-devicedriver-table.md">таблицы таблица devicedriver в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллинетворкконнектионтипе</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Правительства</p></td>
<td><p>Показывает, как вызываемый абонент подключился к сети. Значения берутся из <a href="lync-server-2013-networkconnectiondetail-table.md">таблицы нетворкконнектиондетаил в Lync Server 2013</a>. Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллибссид</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>BSSID для вызываемого абонента, если используется беспроводной доступ. Ссылка из <a href="lync-server-2013-macaddress-table.md">таблицы MacAddress в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>калливпн</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>Ссылка приемника вызовов; 1 — это виртуальная частная сеть (VPN), 0 — не VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллилинкспид</strong></p></td>
<td><p>десятичное число (18, 0)</p></td>
<td><p> </p></td>
<td><p>Скорость сетевого соединения в бит/с для конечной точки приемника вызовов.</p></td>
</tr>
<tr class="odd">
<td><p><strong>конверсатионалмос</strong></p></td>
<td><p>десятичное число (3, 2)</p></td>
<td><p> </p></td>
<td><p>Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).</p></td>
</tr>
<tr class="even">
<td><p><strong>апплиедбандвидслимит</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Это фактическая пропускная способность, примененная к потоку отправки на стороне, в которой задаются различные параметры политики (TURN, API, SDP, сервер политики и т. д.). Ее не следует путать с эффективной пропускной способностью, потому что эффективная пропускная способность может быть меньше в зависимости от оценки пропускной способности. По сути это в основном максимальная пропускная способность потока отправителя с учетом ограничений, наложенных оценкой пропускной способности.</p></td>
</tr>
<tr class="odd">
<td><p><strong>апплиедбандвидссаурцекэй</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Источник применяемого ограничения пропускной способности. В нем описывается, откуда поступает предельный объем пропускной способности ("сервер политики", "превратить сервер", "модальность" и т. д.). Ссылка из <a href="lync-server-2013-appliedbandwidthsource-table.md">таблицы таблица appliedbandwidthsource в Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>Указывает, были ли получены метрики от вызывающего абонента; 1 — значение "Да", NULL — нет.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Вызываемого абонента</strong></p></td>
<td><p>Битовая</p></td>
<td><p> </p></td>
<td><p>Указывает, были ли получены метрики от приемника вызовов; 1 — значение "Да", NULL — нет.</p></td>
</tr>
<tr class="even">
<td><p><strong>мидкаллрепорт</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Указывает, относится ли отчет к части сеанса или к полному сеансу.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>классифиедпуркалл</strong></p></td>
<td><p>Битовая</p></td>
<td></td>
<td><p>Указывает, был ли вызов классифицирован как плохой вызов (значение 1) или как хороший вызов (0).</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллерконнективитице</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>калликоннективитице</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллеррефлексивелокалипаддр</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>IP-адрес пользователя, который поместил вызов. В организациях, использующих NAT (преобразование сетевых адресов), это IP-адрес прокси-сервера.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллервифидривердевицесдеск</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Описание устройства для драйвера Wi-Fi, используемого пользователем, который поместил звонок.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>каллервифидриверверсион</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Номер версии драйвера Wi-Fi, используемый пользователем, который поместил звонок.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>каллерефлексивелокалипаддр</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>IP-адрес пользователя, который получил вызов. В организациях, использующих NAT (преобразование сетевых адресов), это IP-адрес прокси-сервера.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>калливифидривердевицесдеск</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Описание устройства для драйвера Wi-Fi, используемого пользователем, который получил вызов.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>калливифидриверверсион</strong></p></td>
<td><p>int</p></td>
<td><p>Правительства</p></td>
<td><p>Номер версии драйвера Wi-Fi, используемый пользователем, получившим звонок.</p>
<p>Этот столбец появился в Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

