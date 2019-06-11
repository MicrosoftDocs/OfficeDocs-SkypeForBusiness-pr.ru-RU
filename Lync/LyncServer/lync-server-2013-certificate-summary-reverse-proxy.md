---
title: 'Lync Server 2013: сводка по сертификатам — обратный прокси-сервер'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a10259ac4a0beb6d79897b26bf446b109801a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Сводка по сертификатам — обратный прокси-сервер в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-14_

Требования к сертификатам для обратного прокси-сервера значительно проще, чем для пограничных серверов. В предоставленных блок-схемах представлены необходимые требования. Сопутствующая таблица представляет собой типичное имя субъекта сертификата и альтернативные имена субъектов в отношении сценариев, которые мы проверили в обсуждениях пограничного сервера. Более подробную информацию о сценариях пограничного сервера можно найти [в разделе сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Блок-схема "сертификаты" для обратного прокси**

![Блокическая схема сертификатов для пограничного сервера] (images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Блокическая схема сертификатов для пограничного сервера")

### <a name="reverse-proxy-external-interface"></a>Обратный прокси: внешний интерфейс

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Компонент</th>
<th>Имя субъекта</th>
<th>Замещающий имя субъекта (SAN)/Order</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Обратный прокси-сервер</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Необязательно):*. contoso.com</p></td>
<td><p>Сертификат должен быть выдан общедоступным центром сертификации и в серверном EKU. Службы включают в себя службу адресной книги, развертывание групп рассылки Office Web Apps для конференций и правила публикации для IP-устройств Lync. Ниже указаны дополнительные имена субъектов.</p>
<ul>
<li><p>Полное доменное имя внешней веб-службы для пула серверов переднего плана или внешнего интерфейса</p></li>
<li><p>Полное доменное имя внешней веб-службы для режиссера или режиссера</p></li>
<li><p>Конференц-связь с телефонным подключением</p></li>
<li><p>Правило публикации для собрания по сети</p></li>
<li><p>Office Web Apps для конференций</p></li>
<li><p>Lyncdiscover (автообнаружение)</p></li>
</ul>
<p>Необязательный подстановочный знак заменяет и соответствие требованиям к сети SAN</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

