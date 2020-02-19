---
title: 'Lync Server 2013: требования к DNS для серверов Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7007c06835f0b942411d5200a20ef24c393e600
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a>Требования DNS для серверов Standard Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-19_

В данном разделе описываются записи службы доменных имен (DNS), необходимые для развертывания серверов Standard Edition.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>DNS-записи для серверов Standard Edition

В следующей таблице указаны требования к DNS для развертывания сервера Lync Server 2013 Standard Edition.

### <a name="dns-requirements-for-a-standard-edition-server"></a>Требования к DNS для сервера Standard Edition

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Сценарий развертывания</th>
<th>Требование к DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Сервер Standard Edition</p></td>
<td><p>Внутренняя запись A, которая разрешает полное доменное имя сервера в его IP-адрес.</p></td>
</tr>
<tr class="even">
<td><p>Автоматический вход клиентов</p></td>
<td><p>Для каждого поддерживаемого домена SIP запись SRV для _sipinternaltls. _tcp. &lt;домен&gt; через порт 5061, который соответствует полному доменному имени сервера Standard Edition, который выполняет проверку подлинности и перенаправляет запросы клиентов на вход. Дополнительные сведения см. <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">в статье требования к DNS для автоматического входа клиентов в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Обнаружение веб-службы обновления устройств устройствами объединенных коммуникаций</p></td>
<td><p>Внутренняя запись A с именем ucupdates – R2. &lt;Домен&gt; SIP, который разрешается в IP-адрес сервера Standard Edition, на котором размещается веб-служба обновления устройств. В ситуации, когда устройство объединенных коммуникаций включено, но пользователь еще никогда не выполнял вход на него, запись A позволяет устройству обнаруживать сервер с веб-службой обновления устройств и получать обновления. В противном случае устройство получает сведения о сервере посредством автоматической подготовки при первом входе пользователя.</p></td>
</tr>
<tr class="even">
<td><p>Обратный прокси-сервер для поддержки HTTP-трафика</p></td>
<td><p>Внешняя запись A, которая разрешает полное доменное имя внешней веб-фермы во внешний IP-адрес обратного прокси-сервера. Клиенты и устройства объединенных коммуникаций используют эту запись для подключения к обратному прокси-серверу. Дополнительные сведения: <a href="lync-server-2013-determine-dns-requirements.md">Определение требований к DNS для Lync Server 2013</a> в документации по планированию.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

