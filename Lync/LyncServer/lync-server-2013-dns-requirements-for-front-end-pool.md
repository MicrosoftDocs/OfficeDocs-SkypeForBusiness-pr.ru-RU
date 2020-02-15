---
title: 'Lync Server 2013: требования к DNS для пула переднего плана'
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
ms.openlocfilehash: 078b8dc63e630487e13f1d187896bcf0617c0d15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Требования к DNS для пула переднего плана в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-07_

Чтобы успешно выполнить данную процедуру, вы должны войти на сервер или в домен хотя бы в качестве члена группы администраторов домена или группы DnsAdmins.

Перед публикацией топологии в построителе топологий необходимо настроить требуемые записи службы доменных имен (DNS). Кроме того, некоторые полные доменные имена, используемые в конфигурации развертывания Lync Server 2013, являются логическими и не являются полными доменными именами, поэтому перед публикацией требуется дополнительная настройка DNS.

<div>


> [!WARNING]  
> Lync Server 2013 не поддерживает домены с одной меткой. Например, лес с корневым доменом <STRONG>contoso.local</STRONG> будет поддерживаться, а с корневым доменом <STRONG>local</STRONG> — нет. Дополнительные сведения см. в статье 300684 базы знаний Майкрософт "сведения о настройке Windows для доменов с DNS-именем с одной меткой", "по <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> Указанное имя должно совпадать с именем компьютера, заданным на сервере. По умолчанию именем компьютера, не присоединенного к домена,является короткое, а не полное доменное имя. Построитель топологии использует полные доменные имена, а не короткие имена. <STRONG>Используйте только стандартные символы</STRONG> (включая a – z, a – z, 0 – 9 и дефисы) при назначении полных доменных имен серверов, на которых работает Lync Server, пограничные серверы и пулы. Не используйте символы Юникода и подчеркивания. Наличие нестандартных символов в полном доменном имени часто не поддерживается внешней DNS и общими центрами сертификации (когда полное доменное имя должно быть назначено имени субъекта в сертификате).



</div>

Прежде чем приступать к работе с топологией, убедитесь, что созданы следующие записи Active Directory и DNS (по мере необходимости для определенных функций):

  - Каждая роль сервера, которая будет существовать в топологии, публикуется как объект Active Directory (это достигается путем присоединения компьютера к домену).

  - Для каждого сервера существует DNS-запись A.

  - Запись DNS SRV для каждого домена SIP, если вы планируете использовать автоматический вход для клиентов в форме \_сипинтерналтлс\_TCP. \<Домен\>SIP. Если вы будете использовать ручную настройку для клиентов, эта запись не является обязательной.

  - DNS-запись A для каждого настроенного простого URL-адреса, которых обычно существует четыре: meet, dialin, lwa и scheduler. Кроме того, существует простой URL-адрес администратора, который является специальным URL-адресом для доступа к панели управления Lync Server 2013.

  - Сервер, на котором работает SQL Server, должен быть присоединен к домену и доступен компьютеру, с которого построитель топологий выполняет публикацию.

В таблице описаны эталонные архитектуры, представленные в разделе «Планирование». Дополнительные сведения: [сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) в документации по планированию.

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>Записи DNS, необходимые для пула переднего плана

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
<th>FQDN</th>
<th>Сопоставление/комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (балансировка нагрузки через DNS). Требуется запись A DNS для IP-адреса каждого сервера переднего плана в пуле, сопоставление с полным доменным именем пула.</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (виртуальный IP (VIP) оборудования подсистемы балансировки нагрузки).</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Сервер переднего плана Pool01 (узел 1).</p>
<p>Сервер переднего плана Pool01 (узел 2).</p>
<p>Сервер переднего плана Pool01 (узел 3).</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Сервер переднего плана Pool01 (узел 2).</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>Pool01 (VIP) для веб-трафика от клиента на сервер.</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Внутренний сервер Pool01, на котором работает SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Обязательный для Lync Phone Edition или автоматический вход в систему клиентов без DNS-записей SRV и для обязательного согласования доменов. Требуется не во всех случаях.</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Подразумевает второй домен SIP. Обязательный для Lync Phone Edition, автоматический вход клиентов без записей DNS SRV и для обязательного согласования доменов. Требуется не во всех случаях.</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Простой URL-адрес для конференц-связи с телефонным подключением, опубликованный внутренним образом — сервер переднего плана (или директор, если он установлен) отвечает на простые URL-запросы.</p></td>
</tr>
<tr class="even">
<td><p>Внутренняя DNS</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Простой URL-адрес для конференций, опубликованных внутренним образом — сервер переднего плана (или директор, если он установлен) отвечает на запросы простых URL-адресов.</p></td>
</tr>
<tr class="odd">
<td><p>Внутренняя DNS</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>группы</p></td>
<td><p>Необязательная запись, простой URL-адрес для панели управления Lync Server 2013, опубликованный внутренним сервером переднего плана (или режиссером, если он установлен), отвечает на запросы простых URL-адресов. Рекомендуется использовать только имя узла (без имени домена).</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP — виртуальный IP-адрес для аппаратного средства балансировки нагрузки



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
<th>FQDN</th>
<th>Целевое полное доменное имя</th>
<th>Порт</th>
<th>Сопоставление/комментарии</th>
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
<td><p>Источник сетевого времени (NTP), необходимый для устройств, на которых работает Lync Phone Edition. При внутреннем использовании она может указывать на контроллер домена. Если контроллер домена не задан, она пытается использовать сервер NTP time.windows.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

