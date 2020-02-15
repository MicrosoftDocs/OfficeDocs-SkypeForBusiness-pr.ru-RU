---
title: 'Lync Server 2013: Настройка диапазонов портов для клиентов Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0300b042dc124f0fb8bf523221e39128cbf57a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Настройка диапазонов портов для клиентов Microsoft Lync в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-04-22_

По умолчанию клиентские приложения Lync могут использовать любой порт между портами 1024 и 65535 при включении в сеанс связи; Это связано с тем, что для определенных диапазонов портов не включены автоматически клиенты. Однако для использования качества обслуживания необходимо переназначить различные типы трафика (аудио, видео, мультимедиа, общий доступ к приложениям и передачу файлов) для ряда уникальных диапазонов портов. Это можно сделать с помощью командлета Set – CsConferencingConfiguration.

<div>


> [!NOTE]  
> Конечные пользователи не могут вносить эти изменения самостоятельно. Изменения портов могут выполняться только администраторами с помощью командлета Set – CsConferencingConfiguration.



</div>

Вы можете определить, какие диапазоны портов используются в данный момент для сеансов связи, выполнив следующую команду в командной консоли управления Microsoft Lync Server 2013:

    Get-CsConferencingConfiguration

Если вы не внесли какие-либо изменения в параметры конференц-связи после установки Lync Server 2013, необходимо получить сведения, содержащие следующие значения свойств:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Если внимательно посмотреть на предыдущие данные, можно увидеть две важных вещи. Во-первых, для свойства ClientMediaPortRangeEnabled задано значение False:

    ClientMediaPortRangeEnabled : False

Это важно, так как если для этого свойства задано значение false, клиенты Lync будут использовать любой доступный порт между портами 1024 и 65535 при включении в сеанс связи; Это справедливо независимо от других параметров порта (например, ClientMediaPort или Клиентвидеопорт). Если вы хотите ограничить использование указанного набора портов (и это нужно сделать при планировании реализации качества обслуживания), необходимо сначала включить диапазоны портов клиента для передачи данных. Это можно сделать с помощью следующей команды Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

Приведенная выше команда активирует диапазоны портов мультимедиа клиентов для глобальной коллекции параметров конфигурации конференций. Однако данные настройки также могут применяться к области сайта или службы (только для службы сервера конференций). Чтобы включить диапазоны портов мультимедиа клиентов для определенного сайта или сервера, укажите идентификатор этого сайта или сервера при вызове команды Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Или же вы можете использовать следующую команду, чтобы одновременно включить диапазоны порты для всех параметров конфигурации конференций:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

Второй важный момент — в примере выходных данных показано, что по умолчанию набор диапазонов портов мультимедиа для каждого типа сетевого трафика идентичны:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Чтобы реализовать QoS, каждый из этих диапазонов портов должен быть уникальным. Например, вы можете настроить следующие диапазоны портов:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип клиентского трафика</th>
<th>Начальный порт</th>
<th>Диапазон портов</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>"Audio" (Аудио);</p></td>
<td><p>50020</p></td>
<td><p>двадцать</p></td>
</tr>
<tr class="even">
<td><p>Видео</p></td>
<td><p>58000</p></td>
<td><p>двадцать</p></td>
</tr>
<tr class="odd">
<td><p>Общий доступ к приложениям</p></td>
<td><p>42000</p></td>
<td><p>двадцать</p></td>
</tr>
<tr class="even">
<td><p>Передача файлов</p></td>
<td><p>42020</p></td>
<td><p>двадцать</p></td>
</tr>
</tbody>
</table>


В приведенной выше таблице диапазоны портов клиента представляют подмножество диапазонов портов, настроенных для ваших серверов. Например, на серверах для совместного использования приложений были настроены порты с 40803 по 49151. На клиентских компьютерах для совместного использования приложений были настроены порты с 42000 по 42019. Это, в основном, сделано для упрощения управления QoS: клиентские порты не должны представлять подмножество портов, используемых на сервере. (Например, на клиентских компьютерах можно настроить для совместного использования приложений, скажем, порты 10000-10019) Однако рекомендуется сделать диапазоны портов клиента подмножеством диапазонов портов сервера.

Кроме того, вы могли заметить, что 8348 портов было выделено для совместного использования приложений на серверах, но всего 20 портов было выделено для совместного использования приложений на клиентах. Это также рекомендуется, но не является строго обязательным. В общем, можно рассмотреть каждый доступный порт для представления отдельного сеанса связи: если у вас 100 портов в диапазоне, что означает, что компьютер может участвовать максимум в 100 сеансах связи в любой момент времени. Поскольку серверы, вероятно, будут участвовать в большем числе сеансов, чем клиенты, имеет смысл открыть намного больше портов на серверах, чем на клиентах. Выделение 20 портов для совместного использования приложений на клиентах означает, что пользователь одновременно может участвовать в 20 сеансах совместного применения приложений на указанном устройстве. Если должно быть достаточно для подавляющего большинства пользователей.

Чтобы назначить предыдущие диапазоны портов глобальной коллекции параметров конфигурации конференц-связи, можно использовать следующую команду в командной консоли Lync Server:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Или с помощью этой команды можно назначить эти же диапазоны портов всем параметрам конфигурации конференций:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Отдельные пользователи должны выйти из Lync, а затем снова войти в систему, чтобы изменения вступили в силу.

<div>


> [!NOTE]  
> Вы также можете включить диапазоны портов мультимедиа клиентов, а затем назначить эти диапазоны портов с помощью одной команды. Пример:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

