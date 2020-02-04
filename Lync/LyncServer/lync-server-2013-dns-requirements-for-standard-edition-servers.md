---
title: 'Lync Server 2013: требования DNS для серверов стандартных выпусков'
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
ms.openlocfilehash: 3132ec1e18d27564f0077e83d411c5b3930c241b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a>Требования к DNS для серверов Standard Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-19_

В этом разделе описаны записи DNS, необходимые для развертывания стандартных серверов выпуска.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Записи DNS для серверов Standard Edition

В приведенной ниже таблице указаны требования к DNS для развертывания сервера Lync Server 2013 Standard Edition.

### <a name="dns-requirements-for-a-standard-edition-server"></a>Требования к DNS для сервера Standard Edition

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Сценарий развертывания</th>
<th>Требование DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition</p></td>
<td><p>Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.</p></td>
</tr>
<tr class="even">
<td><p>Автоматический вход в учетную запись клиента</p></td>
<td><p>Для каждого поддерживаемого домена SIP — запись SRV для _sipinternaltls. _tcp. &lt;домен&gt; , поступающий на порт 5061 и соответствующий доменному имени сервера Standard Edition, который проверяет подлинность и перенаправляет запросы клиентов на вход. Дополнительные сведения: <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">требования к DNS для автоматического входа на клиент в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Обнаружение веб-служб с помощью обновлений на устройствах с единым коммуникационным подключением (UC)</p></td>
<td><p>Внутренняя запись с именем укупдатес-R2. &lt;Домен&gt; SIP, который РАЗрешается в IP-адрес сервера Standard Edition, на котором размещена служба обновления устройств хостинга. В ситуации, когда устройство для установления связи включено, но пользователь не вошел в систему, запись A позволяет устройству найти веб-службу обновления устройства, на которой размещен сервер, и получить обновления. В противном случае устройство получает сведения о сервере посредством автоматической подготовки при первом входе пользователя.</p></td>
</tr>
<tr class="even">
<td><p>Обратный прокси-сервер, поддерживающий трафик HTTP</p></td>
<td><p>Внешняя запись A, разрешающая полное доменное имя внешней веб-фермы на внешний IP-адрес обратного прокси-сервера. Клиенты и устройства UC используют эту запись для подключения к обратному прокси-серверу. Подробности можно найти в разделе <a href="lync-server-2013-determine-dns-requirements.md">Определение требований DNS для Lync Server 2013</a> в документации по планированию.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

