---
title: 'Lync Server 2013: изменение параметров для файлов журнала обновления устройства'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37002e1043f990ae1e726301b9c720af35556201
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Изменение параметров для файлов журнала обновления устройства в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Вы можете изменить параметры, которые будут регистрироваться в вашей организации с помощью панели управления Lync Server или консоли управления Lync Server. В приведенной ниже таблице показано, какие параметры можно изменять, а также какие инструменты используются для изменения параметров.

Параметры журнала можно изменять и применять глобально или на уровне отдельных сайтов.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Для изменения</th>
<th>Применение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Максимальный размер файла журнала (в байтах)</p></td>
<td><p>Панель управления Lync Server</p>
<p>/</p>
<p>Командная консоль Lync Server</p></td>
</tr>
<tr class="even">
<td><p>Максимальный объем данных (в байтах), которые могут храниться в кэше</p></td>
<td><p>Панель управления Lync Server</p>
<p>/</p>
<p>Командная консоль Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Частота записи кэшированных данных в файл журнала (в минутах)</p></td>
<td><p>Панель управления Lync Server</p>
<p>/</p>
<p>Командная консоль Lync Server</p></td>
</tr>
<tr class="even">
<td><p>Продолжительность хранения файлов журнала (в днях)</p></td>
<td><p>Панель управления Lync Server</p>
<p>/</p>
<p>Командная консоль Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Время (в днях) для проверки просроченных файлов, которые нужно удалить</p></td>
<td><p>Командная консоль Lync Server</p></td>
</tr>
<tr class="even">
<td><p>Какие расширения файлов журналов разрешаются</p></td>
<td><p>Командная консоль Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Типы файлов журналов, которые нужно сохранить</p></td>
<td><p>Командная консоль Lync Server</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>Изменение параметров ведения журнала с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  На панели навигации слева выберите пункт **Клиенты**, а затем — **Конфигурация журнала устройств**.

3.  На странице **конфигурации журнала устройства** дважды щелкните конфигурацию, которую вы хотите изменить.

4.  В диалоговом окне **изменение параметров журнала** измените любые из указанных ниже параметров.
    
      - **Максимальный размер файла (в байтах)**   — максимальный размер, который может быть указан в файле журнала до его очистки. Значение по умолчанию — 1 024 000 байт (1 МБ).
    
      - **Максимальный размер кэша (в байтах)**   — максимальный объем данных (в байтах), которые могут храниться в кэше файлов журналов, прежде чем этот кэш должен быть очищен и данные записываются в файл журнала. Значение по умолчанию — 512 000 байт (0,5 МБ).
    
      - **Количество минут для кэша очистки (1-60)**   показывает, как часто данные, хранящиеся в кэше файлов журналов, записываются в файл журнала. После того как данные записываются в журнал, кэш очищается. По умолчанию используется значение 5 минут.
    
      - **Число дней для хранения файлов журнала (1-365)**   указывает количество дней, в течение которых хранятся файлы журнала, прежде чем они будут очищены. Значение по умолчанию — 10 дней.

5.  Нажмите **Исполнить**.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Изменение параметров ведения журнала с помощью командлетов Windows PowerShell

Параметры файла журнала обновления устройства можно изменить с помощью Windows PowerShell и командлета **Set-ксдевицеупдатеконфигуратион** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.



</div>

В следующих примерах показано несколько способов использования **Set-ксдевицеупдатеконфигуратион** для изменения параметров.

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>Изменение максимального размера файла журнала и интервала очистки журнала

  - Следующая команда изменяет параметры журнала обновления устройства, примененные к сайту Redmond. В этом примере для максимального размера файла журнала задано значение 204800 байт, а для интервала очистки журнала установлено значение 14 дней.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>Изменение времени очистки журнала за день

  - Эта команда задает время очистки журнала для сайта Redmond на 3:00 AM.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Set-ксдевицеупдатеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

