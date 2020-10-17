---
title: 'Lync Server 2013: изменение параметров для файлов журнала обновления устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2118cac5e8380d27e8f273f5cb469efdbddfd9bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534336"
---
# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Изменение параметров для файлов журнала обновления устройств в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

С помощью панели управления Lync Server или командной консоли Lync Server можно изменить параметры регистрации сведений об обновлениях устройств в Организации. В следующей таблице приведены параметры, доступные для изменения, а также средства, используемые для изменения параметров.

Параметры журнала можно изменять и применять глобально или на уровне сайта.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Чтобы изменить</th>
<th>Использование</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Максимальный размер файла журнала (в байтах)</p></td>
<td><p>Панель управления сервера Lync</p>
<p>-или-</p>
<p>Командная консоль Lync Server</p></td>
</tr>
<tr class="even">
<td><p>Максимальный объем данных (в байтах), которые могут храниться в кэше</p></td>
<td><p>Панель управления сервера Lync</p>
<p>-или-</p>
<p>Командная консоль Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Частота записи кэшированных данных в файл журнала (в минутах)</p></td>
<td><p>Панель управления сервера Lync</p>
<p>-или-</p>
<p>Командная консоль Lync Server</p></td>
</tr>
<tr class="even">
<td><p>Срок хранения файлов журнала (в днях)</p></td>
<td><p>Панель управления сервера Lync</p>
<p>-или-</p>
<p>Командная консоль Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Время (в днях) проверки просроченных файлов, которые следует удалить</p></td>
<td><p>Командная консоль Lync Server</p></td>
</tr>
<tr class="even">
<td><p>Какие расширения файлов журналов разрешаются</p></td>
<td><p>Командная консоль Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Типы файлов журналов, которые необходимо сохранить</p></td>
<td><p>Командная консоль Lync Server</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>Изменение параметров ведения журнала с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации последовательно выберите пункты **Клиенты** и **Конфигурация журналов устройств**.

3.  На странице **Конфигурация журналов устройств** дважды щелкните конфигурацию, которую требуется изменить.

4.  В диалоговом окне **изменение параметров журнала** измените любой из следующих параметров:
    
      - **Максимальный размер файла (в байтах)**     Задает максимальный размер файла журнала до его очистки. Значение по умолчанию 1 024 000 байт (1 МБ).
    
      - **Максимальный размер кэша (в байтах)**     Задает максимальный объем данных (в байтах), которые могут храниться в кэше файлов журнала до очистки этого кэша и записи данных в файл журнала. Значение по умолчанию 512 000 байт (0,5 МБ).
    
      - **Количество минут до очистки кэша (1-60)**     Указывает, как часто данные, хранящиеся в кэше файлов журналов, записываются в фактический файл журнала. После того как данные заносятся в журнал, кэш очищается. Значение по умолчанию 5 минут.
    
      - **Число дней хранения файлов журнала (1-365)**     Указывает количество дней, в течение которых файлы журнала хранятся до очистки. Значение по умолчанию — 10 дней.

5.  Нажмите кнопку **Зафиксировать**.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Изменение параметров ведения журналов с помощью командлетов Windows PowerShell

Параметры файла журнала обновления устройств можно изменить с помощью Windows PowerShell и командлета **Set – CsDeviceUpdateConfiguration** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

В следующих примерах показаны несколько способов, которые можно использовать для изменения параметров **Set – CsDeviceUpdateConfiguration** .

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>Изменение максимального размера файла журнала и интервала очистки журнала

  - Следующая команда изменяет параметры журнала обновления устройств, применяемые к сайту Redmond. В этом примере для максимального размера файла журнала задано значение 204800 байт, а для интервала очистки журнала задано значение 14 дней.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>Изменение времени очистки журнала в день

  - Эта команда задает время очистки журнала для сайта Redmond равным 3:00 AM.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

Дополнительные сведения см. в разделе справки для командлета [Set – CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

