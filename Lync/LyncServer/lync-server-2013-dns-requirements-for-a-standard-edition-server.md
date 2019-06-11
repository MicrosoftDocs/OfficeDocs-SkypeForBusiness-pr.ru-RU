---
title: 'Lync Server 2013: Требования DNS для сервера Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7508fea0fa6640546bda4f1ecb559821d468803d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>Требования DNS для сервера Standard Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-22_

В этом разделе описаны записи DNS, необходимые для развертывания стандартных серверов выпуска.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Записи DNS для серверов Standard Edition

В приведенной ниже таблице указаны требования к DNS для развертывания сервера Lync Server 2013 Standard Edition.


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
<td><p>Для каждого поддерживаемого домена SIP — запись SRV для _сипинтерналтлс. _tcp. &lt;домен&gt; , поступающий на порт 5061 и соответствующий доменному имени сервера Standard Edition, который проверяет подлинность и перенаправляет запросы клиентов на вход. Дополнительные сведения: <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">требования к DNS для автоматического входа на клиент в Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Обнаружение веб-служб с помощью обновлений на устройствах с единым коммуникационным подключением (UC)</p></td>
<td><p>Внутренняя запись с именем укупдатес-R2. &lt;Домен&gt; SIP, который РАЗрешается в IP-адрес сервера Standard Edition, на котором размещена служба обновления устройств хостинга. В ситуации, когда устройство для установления связи включено, но пользователь не вошел в систему, запись A позволяет устройству найти веб-службу обновления устройства, на которой размещен сервер, и получить обновления. В противном случае устройство получает сведения о сервере посредством автоматической подготовки при первом входе пользователя. Подробные сведения об этом можно найти <a href="lync-server-2013-device-update-web-service.md">в разделе веб-служба обновления устройств в Lync Server 2013</a> в документации по эксплуатации.</p></td>
</tr>
<tr class="even">
<td><p>Обратный прокси-сервер, поддерживающий трафик HTTP</p></td>
<td><p>Внешняя запись A, разрешающая полное доменное имя внешней веб-фермы на внешний IP-адрес обратного прокси-сервера. Клиенты и устройства UC используют эту запись для подключения к обратному прокси-серверу. Подробности можно найти в разделе <a href="lync-server-2013-determine-dns-requirements.md">Определение требований DNS для Lync Server 2013</a> в документации по планированию.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Требования DNS для автоматического входа клиента в Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Веб-служба обновления устройств в Lync Server 2013](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

