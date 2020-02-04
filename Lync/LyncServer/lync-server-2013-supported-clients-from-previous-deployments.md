---
title: 'Lync Server 2013: поддерживаемые клиенты из предыдущих развертываний'
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
ms.openlocfilehash: 38d4fe00b834778f1ad87f021656ed08488c1ba2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Поддерживаемые клиенты из предыдущих развертываний в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-12-14_

В сценарии сосуществования Пользователи Lync Server 2013 могут взаимодействовать с клиентами из более ранних версий Lync Server и Office Communications Server. В отличие от предыдущих выпусков, Lync Server 2010 поддерживает новые клиенты Lync 2013. Это позволяет организациям, работающим с Lync Server 2010, развертывать новые клиенты независимо от того, как Lync Server выполняет обновление.

<div>

## <a name="supported-server-and-client-combinations"></a>Поддерживаемые комбинации сервера и клиента

В следующей таблице показаны поддерживаемые комбинации версий клиентов и сервера. Lync Server 2013 поддерживает две предыдущие версии клиента, а Lync Server 2010 поддерживает новый клиент Lync 2013.


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
<td><p>Lync 2010</p></td>
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
<td><p>Участник Lync 2010</p></td>
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
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
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


1In Microsoft Lync Server 2010, функция группового чата была доступна для сервера группового чата, стороннего доверенного приложения для Lync Server 2010. Клиенты Lync 2013 несовместимы с Lync Server 2010, групповой чат.

2Lync веб-приложение 2013 теперь обеспечивает полное участие в собрании, в том числе звуковое сопровождение и видео компьютера, и считается заменой для участника Lync 2010.

3The функции присутствия и обмена мгновенными сообщениями в Office Communicator 2007 R2 совместимы с Lync Server 2013, но возможности конференции не поддерживаются. При переходе с Office Communications Server 2007 R2 подходящими для обеспечения взаимодействия и обмена мгновенными сообщениями является Office Communicator 2007 R2, но пользователи должны использовать Lync Web App 2013, чтобы присоединиться к собраниям Lync Server 2013.

<div>


> [!NOTE]  
> Подробные сведения о том, как можно сосуществование клиентов Lync Server 2013 и взаимодействовать с клиентами из более ранних версий Lync Server и Office Communications Server, вы можете найти в разделе взаимодействие с клиентами <A href="lync-server-2013-client-interoperability-in-lync-2013.md">в lync 2013</A> в документации по планированию.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

