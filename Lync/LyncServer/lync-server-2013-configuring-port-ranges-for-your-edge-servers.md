---
title: 'Lync Server 2013: Настройка диапазонов портов для пограничных серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73827b9c16903a6b3cf06f0c56446c0409fb9cd4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Настройка диапазонов портов для пограничных серверов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2015-07-24_

В пограничных серверах вам не нужно настраивать отдельные диапазоны портов для обмена аудио, видео и приложений. Аналогичным образом диапазоны портов, используемые для пограничных серверов, не должны совпадать с диапазонами портов, используемыми для серверов конференций, приложений и исправлений. Перед тем как приступить к работе с нашим примером, важно перегрузить этот параметр, но мы не рекомендуем менять диапазоны портов, так как это может негативно сказаться на некоторых сценариях, если вы выйдете из диапазона портов 50000.

Например, предположим, что для использования следующих диапазонов портов настроены серверы конференций, приложений и исправлений:


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
<td><p>Голосовая связь</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Видеосвязь</p></td>
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


Как видите, диапазоны портов для обмена аудио, видео и приложениями начинаются с порта 40803 и включают в себя всего 24732 портов. При желании вы можете настроить этот граничный сервер для использования этих общих значений порта, выполнив следующую команду в командной консоли Lync Server.

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Вы также можете одновременно настроить все пограничные серверы в Организации с помощью следующей команды:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Вы можете проверить текущие параметры порта для пограничных серверов с помощью командной консоли Lync Server Management Shell:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Пока мы предоставляем эти параметры, мы настоятельно рекомендуем вам оставить все, что нужно для настройки порта.

</div>

<span> </span>

</div>

</div>

</div>

