---
title: 'Lync Server 2013: сводка по сертификатам — обратный прокси-сервер'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25e83fb5857988396c3d13d2b07078c654972c92
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515746"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Сводка по сертификатам — обратный прокси-сервер в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-14_

Требования к сертификатам для обратного прокси-сервера значительно проще, чем для пограничных серверов. В приведенной блок-схеме представлены обязательные требования. Сопроводительная таблица представляет Типичное имя субъекта сертификата и альтернативные имена субъектов в отношении сценариев, которые мы рассматривали в дискуссиях пограничных серверов. Более подробную информацию о сценариях пограничных серверов можно найти [в статье сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Блок-схема сертификатов для обратного прокси-сервера**

![Сертификаты для пограничного сервера (блок-схема)](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Сертификаты для пограничного сервера (блок-схема)")

### <a name="reverse-proxy-external-interface"></a>Обратный прокси-сервер: внешний интерфейс

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
<th>Альтернативное имя субъекта (SAN)/заказ</th>
<th>Comments</th>
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
<td><p>Сертификат должен быть выпущен открытым центром сертификации и содержать ключ EKU сервера. Службы включают в себя службу адресной книги, расширения группы рассылки Office Web Apps для конференций и правила публикации для IP-устройств Lync. Альтернативное имя субъекта включает следующее:</p>
<ul>
<li><p>Полное доменное имя внешних веб-служб для сервера переднего плана или интерфейсного пула</p></li>
<li><p>Полное доменное имя внешних веб-служб для директора или пула директоров</p></li>
<li><p>Конференц-связь с телефонным подключением</p></li>
<li><p>Правила публикации интернет-собраний</p></li>
<li><p>Office Web Apps для конференц-связи</p></li>
<li><p>Lyncdiscover (автообнаружение)</p></li>
</ul>
<p>Дополнительный подстановочный знак заменяет имя SAN собраний и телефонных подключений</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

