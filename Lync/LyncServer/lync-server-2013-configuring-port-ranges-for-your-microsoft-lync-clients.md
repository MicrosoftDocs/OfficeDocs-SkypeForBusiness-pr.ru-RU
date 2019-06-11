---
title: 'Lync Server 2013: Настройка диапазонов портов для клиентов Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03cd4c109760756dd265526bd9d5285fdc9fed30
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Настройка диапазонов портов для клиентов Microsoft Lync в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-04-22_

По умолчанию клиентские приложения Lync могут использовать любой порт между портами 1024 и 65535 при включении в сеанс связи. Это происходит из-за того, что определенные диапазоны портов не включены автоматически для клиентов. Тем не менее, чтобы использовать качество обслуживания, вам потребуется переназначить различные типы трафика (звук, видео, мультимедиа, общий доступ к приложениям и передачу файлов) на ряд уникальных диапазонов портов. Это можно сделать с помощью командлета Set-КсконференЦингконфигуратион.

<div>


> [!NOTE]  
> Конечные пользователи не могут вносить эти изменения. Изменение портов может выполняться только администраторами с помощью командлета Set-КсконференЦингконфигуратион.



</div>

Вы можете определить, какие диапазоны портов используются в сеансах связи, выполнив следующую команду в командной консоли Microsoft Lync Server 2013:

    Get-CsConferencingConfiguration

Если вы не внесли никаких изменений в параметры конференц-связи после установки Lync Server 2013, вы должны получить информацию, которая включает следующие значения свойств.

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Если вы ближе просмотрит предыдущий результат, вы увидите два важных элемента. Сначала свойство Клиентмедиапортранжеенаблед имеет значение false.

    ClientMediaPortRangeEnabled : False

Это важно, так как, если для этого свойства задано значение false, клиенты Lync будут использовать любой доступный порт между портами 1024 и 65535 при включении в сеанс связи. Это справедливо независимо от других параметров порта (например, Клиентмедиапорт или Клиентвидеопорт). Если вы хотите ограничить использование заданным набором портов (и это нужно сделать, если вы планируете реализовать качество обслуживания), необходимо сначала включить диапазоны портов клиента мультимедиа. Это можно сделать с помощью следующей команды Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

Предыдущая команда включает диапазоны порта клиента мультимедиа для глобальной коллекции параметров конфигурации конференций. Однако эти параметры также можно применять к области действия сайта и (или) области службы (только для службы сервера конференц-связи). Чтобы включить диапазон портов клиента мультимедиа для определенного сайта или сервера, укажите удостоверение этого сайта или сервера при вызове Set-КсконференЦингконфигуратион:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Кроме того, вы можете использовать эту команду для одновременного включения диапазонов портов для всех параметров настройки конференц-связи.

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

Во втором случае важно заметить, что в примере вывода показано, что по умолчанию диапазоны портов мультимедиа, заданные для каждого типа сетевого трафика, идентичны:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Для реализации QoS каждый из этих диапазонов должен быть уникальным. Например, вы можете настроить диапазоны портов следующим образом:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип трафика клиента</th>
<th>Начало порта</th>
<th>Диапазон портов</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Голосовая связь</p></td>
<td><p>50020</p></td>
<td><p>средняя</p></td>
</tr>
<tr class="even">
<td><p>Видеосвязь</p></td>
<td><p>58000</p></td>
<td><p>средняя</p></td>
</tr>
<tr class="odd">
<td><p>Общий доступ к приложениям</p></td>
<td><p>42000</p></td>
<td><p>средняя</p></td>
</tr>
<tr class="even">
<td><p>Передача файлов</p></td>
<td><p>42020</p></td>
<td><p>средняя</p></td>
</tr>
</tbody>
</table>


В приведенной выше таблице диапазоны портов клиента представляют собой подмножество диапазонов портов, настроенных для серверов. Например, на серверах общий доступ к приложениям настроен на использование портов 40803 – 49151; на клиентских компьютерах общий доступ к приложениям настроен на использование портов 42000 – 42019. Это также необходимо сделать, чтобы упростить администрирование QoS: портам клиента не нужно представлять подмножество портов, используемых на сервере. (Например, на клиентских компьютерах вы можете настроить общий доступ к приложениям, например, с помощью портов 10000 – 10019.) Тем не менее рекомендуется сделать порт клиента подмножеством диапазонов портов сервера.

Кроме того, вы могли заметить, что порты 8348 были настроены для совместного использования приложений на серверах, но для совместного использования приложений на клиентских компьютерах задано только 20 портов. Это, как правило, рекомендуется, но не является жесткой и быстрой. Как правило, вы можете использовать каждый доступный порт для представления одного сеанса связи: Если в диапазоне портов есть доступные порты 100, то в любой момент времени компьютер может принимать участие в сеансах связи 100. Поскольку серверы, скорее чем, будут работать в большинстве сеансов, чем клиенты, имеет смысл открыть на серверах больше портов, чем на клиентах. Настройка 20 портов для совместного использования приложений на клиенте означает, что пользователь может принимать участие в 20 сеансах общего разделения приложений на указанном устройстве и одновременно. Это должно быть достаточно для самых разнообразных пользователей.

Чтобы назначить предыдущие диапазоны портов для глобальной коллекции параметров настройки конференц-связи, вы можете использовать следующую команду оболочки Lync Server Management Shell:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Кроме того, можно использовать эту команду для назначения одинаковых диапазонов портов для всех параметров настройки конференц-связи.

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Чтобы изменения вступили в силу, пользователи должны выйти из Lync, а затем снова войти в систему.

<div>


> [!NOTE]  
> Вы также можете включить диапазоны портов клиента мультимедиа, а затем назначить эти диапазоны портов с помощью одной команды. Например:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

