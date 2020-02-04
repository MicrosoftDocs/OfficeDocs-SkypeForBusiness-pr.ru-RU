---
title: 'Lync Server 2013: требования DNS для пулов переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 252bacd9818676155dcab0f84e3e1c5fcdb31b5d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Требования DNS для пулов переднего плана в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-07_

Для успешного выполнения этой процедуры необходимо войти в систему на сервере или в домене в группу администраторов домена или в группу пользователей Днсадминс.

Прежде чем публиковать топологию в построителе топологии, необходимо настроить нужные записи DNS (Domain Name System). Кроме того, некоторые полные доменные имена, используемые в конфигурации Lync Server 2013, являются логическими, а не физическими (FQDN), поэтому перед публикацией требуется дополнительная настройка DNS.

<div>


> [!WARNING]  
> Lync Server 2013 не поддерживает домены, помеченные как единые. Например, лес с корневым доменом с именем <STRONG>contoso. local</STRONG> поддерживается, но корневой домен с именем <STRONG>Local</STRONG> не поддерживается. Подробные сведения о том, как настроить Windows для доменов с DNS-именами, сопоставленными с одной меткой, можно найти в статье 300684 (at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; кбид = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> Указанное имя должно быть идентично имени компьютера, настроенному на сервере. По умолчанию имя компьютера, не подключенного к домену, является коротким именем, а не FQDN. Построитель топологии использует полные доменные имена, а не короткие имена. При назначении полных доменных имен серверам Lync Server, пограничным серверам и пулам <STRONG>Используйте только стандартные символы</STRONG> (включая A-z, a-z, 0 – 9 и дефисы). Не используйте символы Unicode или подчеркивания. Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS-и общедоступными центрами сертификации (ЦС) (когда полное доменное имя должно быть назначено для SN в сертификате).



</div>

Перед тем как приступать к работе с топологией после ее развертывания, убедитесь в том, что созданы указанные ниже записи Active Directory и DNS (в зависимости от того, что требуется для определенных функций):

  - Все роли сервера, которые будут существовать в топологии, публикуются как объект Active Directory (это можно сделать с помощью присоединения компьютера к домену).

  - Для каждого сервера существует запись DNS A.

  - DNS SRV-запись для каждого домена SIP используется в том случае, если вы планируете использовать автоматический вход в систему \_для\_клиентов в форме сипинтерналтлс TCP. \<Домен\>SIP. Если вы будете использовать ручную настройку для клиентов, эта запись не требуется.

  - Запись DNS A для каждого настроенного простого URL-адреса, который обычно состоит из четырех: "Встреча", "Входящие", "лва" и "Планировщик". Кроме того, существует простой URL-адрес администратора, который является специальным URL-адресом для доступа к панели управления Lync Server 2013.

  - Сервер, на котором работает SQL Server, должен быть присоединен к домену и доступен на компьютере, с которого построитель топологии выполняет публикацию.

В таблице ниже приведены справочные архитектуры, представленные в разделе Планирование. Дополнительные сведения можно найти [в разделе сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) в документации по планированию.

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>DNS-записи, необходимые для пула переднего плана

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Расположение</th>
<th>Тип</th>
<th>Полное доменное имя</th>
<th>Карты и примечания</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>А</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (Балансировка нагрузки DNS). Требуется запись DNS A для IP-адреса каждого сервера переднего плана в пуле, сопоставленная с полным доменным именем пула.</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS</p></td>
<td><p>А</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (виртуальный IP-адрес (VIP) балансировщика аппаратной балансировки нагрузки).</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>А</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Сервер Pool01 переднего плана (узел 1).</p>
<p>Сервер Pool01 переднего плана (узел 2).</p>
<p>Сервер Pool01 переднего плана (узел 3).</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS</p></td>
<td><p>А</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Сервер Pool01 переднего плана (узел 2).</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>А</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>Pool01 (VIP) для веб-трафика между клиентом и сервером.</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS</p></td>
<td><p>А</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Сервер Pool01 Server, на котором запущен SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>А</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Требуется для Lync Phone Edition или для автоматического входа в систему клиентов без DNS SRV-записей и для строгого сопоставления доменов. Не является обязательным для всех случаев.</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS</p></td>
<td><p>А</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Предполагается наличие второго домена SIP. Требуется для Lync Phone Edition, автоматического входа в систему клиентов без DNS SRV-записей и для строгого сопоставления доменов. Не является обязательным для всех случаев.</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>А</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Простой URL-адрес для конференц-связи с телефонным подключением, опубликованный внутренне — сервер переднего плана (или режиссер, если он установлен) отвечает на простые URL-запросы.</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS</p></td>
<td><p>А</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Простой URL-адрес для конференций, опубликованный внутренне — сервер переднего плана (или режиссер, если он установлен) отвечает на простые URL-запросы.</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>А</p></td>
<td><p>admin.contoso.com</p>
<p>RAS</p></td>
<td><p>Необязательная запись, простой URL-адрес для панели управления Lync Server 2013, опубликованный внутренним образом сервер переднего плана (или режиссер, если он установлен) отвечает на простые URL-запросы. Рекомендуется только имя узла (имя домена не поддерживается).</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = виртуальный IP-адрес для подсистемы балансировки нагрузки для оборудования



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>Записи DNS SRV для пула переднего плана


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Расположение</th>
<th>Тип</th>
<th>Полное доменное имя</th>
<th>Целевое полное доменное имя</th>
<th>Порт</th>
<th>Карты и примечания</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. contoso. com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Требуется для автоматической настройки клиентов Lync 2013 для внутреннего использования.</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _tcp. fabrikam. com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Требуется для автоматической настройки клиентов Lync 2013 для внутреннего использования.</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>SRV</p></td>
<td><p>_ntp. _udp. contoso. com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Для устройств с Lync Phone Edition требуется источник сетевого времени (NTP). На внутреннем уровне это значение должно указывать на контроллер домена. Если контроллер домена не определен, он попытается использовать сервер NTP time.windows.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

