---
title: 'Lync Server 2013: Настройка диапазонов портов для пограничных серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ce17300c6504989d132cb27301128bfbc568870
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Настройка диапазонов портов для пограничных серверов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2015-07-24_

При наличии пограничных серверов нет необходимости настраивать отдельные диапазоны портов для аудио, видео и общего доступа к приложениям; кроме того, диапазоны портов, используемые для пограничных серверов, не требуется сопоставлять с номерами портов, используемыми с серверами конференций, приложений и с серверами-посредниками. Прежде чем приступить к работе с нашим примером, важно нагрузить этот параметр, но мы не рекомендуем изменять диапазоны портов, так как это может отрицательно сказаться на некоторых сценариях, если вы перейдете из диапазона портов 50000.

Например, предположим, что серверы конференций, приложений и сервер-посредник настроены для использования следующих портов.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип пакета</th>
<th>Начальный порт</th>
<th>Количество зарезервированных портов</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Общий доступ к приложениям</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>"Audio" (Аудио);</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Видео</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>Итоги</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Как видите, диапазоны портов для передачи звука, видео и общего доступа к приложениям начинаются с порта 40803 и охватывают всего 24732 портов. При желании можно настроить конкретный пограничный сервер для использования этих значений портов, выполнив в командной консоли Lync Server команду, аналогичную следующей:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Можно также одновременно настроить все пограничные серверы в организации с помощью следующей команды:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Вы можете проверить текущие параметры портов для пограничных серверов с помощью командной консоли Lync Server Management Shell:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Опять же, пока мы предоставляем эти параметры, мы настоятельно рекомендуем оставить их в соответствии с конфигурацией порта.

</div>

<span> </span>

</div>

</div>

</div>

