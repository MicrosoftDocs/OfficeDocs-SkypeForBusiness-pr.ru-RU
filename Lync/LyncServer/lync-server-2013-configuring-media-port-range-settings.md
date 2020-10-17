---
title: 'Lync Server 2013: Настройка параметров диапазона портов мультимедиа'
description: 'Lync Server 2013: Настройка параметров диапазона портов мультимедиа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a7670284c593197068c366f43bbb3faaaad8f63
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570745"
---
# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Настройка параметров диапазона портов мультимедиа в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-18_

Параметры диапазона портов медиаданных могут значительно влиять на производительность клиента и должны быть настроены. Эти параметры можно настроить с помощью консоли управления Lync Server.

### <a name="media-port-range-settings"></a>Параметры диапазона портов медиаданных

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр</th>
<th>Описание</th>
<th>Командлет командной консоли Lync Server</th>
<th>Параметры командлета</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>портранже\енаблед</p></td>
<td><p>Определяет, должен ли клиент использовать диапазоны портов, отправленные сервером, для обработки медиаданных и сигнализации. Используется в сочетании со значениями MinMediaPort и MaxMediaPort.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>Параметры clientmediaportrangeenabled</p></td>
</tr>
<tr class="even">
<td><p>портранже\минмедиапорт</p></td>
<td><p>Определяет начальный номер порта медиаданных. Вместе с параметром MaxMediaPort позволяет задать диапазон портов. Рекомендуемый минимальный диапазон составляет 40 портов.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (представляет собой начальный номер порта медиаданных клиента)</p></td>
</tr>
<tr class="odd">
<td><p>портранже\максмедиапорт</p></td>
<td><p>Определяет максимальный номер порта медиаданных. Вместе с параметром MinMediaPort позволяет задать диапазон портов. Рекомендуемый минимальный диапазон составляет 40 портов.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (определяет общее число портов, доступных для медиаданных клиента; по умолчанию: 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>Порядок настройки параметров диапазона портов медиаданных

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните следующий командлет:
    
        Get-CsConferencingConfiguration
    
    Этот командлет возвращает параметры конфигурации конференц-связи.

3.  Выполните следующий командлет с параметрами и значениями, которые требуется изменить (Дополнительные сведения о параметрах этого командлета см. в документации по командной консоли Lync Server).
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > Можно создавать дополнительные наборы параметров конфигурации конференц-связи для отдельных сайтов. Используйте командлет <STRONG>New- CsConferencingConfiguration</STRONG> с указанием идентификатора сайта. При создании новых параметров конфигурации конференц-связи для сайтов эти параметры сайтов имеют приоритет перед глобальными параметрами. Дополнительные сведения см. в документации Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

