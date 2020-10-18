---
title: 'Lync Server 2013: Поддерживаемые клиенты из предыдущих развертываний'
description: 'Lync Server 2013: Поддерживаемые клиенты из предыдущих развертываний.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f83723a571bb63cb012d6ef8a8b502af2717213
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575325"
---
# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Поддерживаемые клиенты из предыдущих развертываний в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-12-14_

В сценарии сосуществования клиенты Lync Server 2013 могут взаимодействовать с клиентами из более ранних версий Lync Server и Office Communications Server. В отличие от предыдущих выпусков, Lync Server 2010 поддерживает новые клиенты Lync 2013. Это позволяет организациям, которые обновляются с Lync Server 2010, развертывать новые клиенты независимо от обновлений Lync Server.

<div>

## <a name="supported-server-and-client-combinations"></a>Поддерживаемые сочетания сервера и клиента

В следующей таблице показаны поддерживаемые сочетания версий клиентов и серверов. Lync Server 2013 поддерживает две предыдущие версии клиентов, а Lync Server 2010 поддерживает новый клиент Lync 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Клиент</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Group Chat</p></td>
<td><p>Неприменимо</p></td>
<td><p>Supported1</p></td>
<td><p>Неприменимо</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Не Supported2</p></td>
<td><p>Поддерживается</p></td>
<td><p>Не поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Помощник Microsoft Office Communications Server 2007 R2</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Поддерживается</p></td>
<td><p>Поддерживается</p></td>
</tr>
</tbody>
</table>


1In Microsoft Lync Server 2010, функция группового чата была доступна с сервером группового чата, доверенным сторонним приложением для Lync Server 2010. Клиенты Lync 2013 несовместимы с Lync Server 2010, группового чата.

2Lync Web App 2013 теперь предоставляет полный интерфейс для собраний, включая аудио-и видеоданные, и считается заменой участнику Lync 2010.

3The присутствия и функции обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но функции конференц-связи не поддерживаются. Во время миграции с Office Communications Server 2007 R2 приложение Office Communicator 2007 R2 подходит для взаимодействия с присутствием и обменом мгновенными сообщениями, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.

<div>


> [!NOTE]  
> Сведения о возможности совместного использования клиентов Lync Server 2013 и взаимодействия с клиентами из более ранних версий Lync Server и Office Communications Server представлены в разделе <A href="lync-server-2013-client-interoperability-in-lync-2013.md">взаимодействие клиентов в lync 2013</A> в документации по планированию.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

