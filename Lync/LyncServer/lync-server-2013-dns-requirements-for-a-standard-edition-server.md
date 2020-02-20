---
title: 'Lync Server 2013: требования к DNS для сервера Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cdd7a32519fe510819f82619c9086b22b820a52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>Требования DNS для сервера Standard Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-22_

В данном разделе описываются записи службы доменных имен (DNS), необходимые для развертывания серверов Standard Edition.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>DNS-записи для серверов Standard Edition

В следующей таблице указаны требования к DNS для развертывания сервера Lync Server 2013 Standard Edition.


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
<td><p>Внутренняя запись A с именем ucupdates – R2. &lt;Домен&gt; SIP, который разрешается в IP-адрес сервера Standard Edition, на котором размещается веб-служба обновления устройств. В ситуации, когда устройство объединенных коммуникаций включено, но пользователь еще никогда не выполнял вход на него, запись A позволяет устройству обнаруживать сервер с веб-службой обновления устройств и получать обновления. В противном случае устройство получает сведения о сервере посредством автоматической подготовки при первом входе пользователя. Сведения о <a href="lync-server-2013-device-update-web-service.md">веб-службе обновления устройств в Lync Server 2013</a> можно найти в документации по операциям.</p></td>
</tr>
<tr class="even">
<td><p>Обратный прокси-сервер для поддержки трафика HTTP</p></td>
<td><p>Внешняя запись A, которая разрешает полное доменное имя внешней веб-фермы во внешний IP-адрес обратного прокси-сервера. Клиенты и устройства объединенных коммуникаций используют эту запись для подключения к обратному прокси-серверу. Дополнительные сведения: <a href="lync-server-2013-determine-dns-requirements.md">Определение требований к DNS для Lync Server 2013</a> в документации по планированию.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Требования DNS для автоматического входа клиентов в Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Определение требований к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Веб-служба обновления устройств в Lync Server 2013](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

