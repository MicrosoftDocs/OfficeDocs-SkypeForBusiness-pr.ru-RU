---
title: 'Lync Server 2013: удаление файлов журнала обновления устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99fb9e6109c6f27e2985de18c2fcdf804dd184c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Удаление файлов журнала обновления устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Веб-служба обновления устройства хранит обширный набор файлов журнала. Эта коллекция включает оба журнала аудита, выполненных самой службой, и файлы журналов, загруженные с клиентских устройств. Чтобы не допустить, чтобы сервер запускался с журналами веб-службы обновления устройств, вы, возможно, захотите очистить файлы журнала, которые использовались в течение определенного числа дней. Задать это количество дней на основе действий по обновлению и количества клиентских устройств в вашей организации, а также с помощью панели управления Lync Server или командной консоли Lync Server Management.

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>Очистка журнала обновления устройства с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  На панели навигации слева выберите пункт **Клиенты**, а затем — **Конфигурация журнала устройств**.

3.  На странице **конфигурации журнала устройства** дважды щелкните конфигурацию, которую вы хотите изменить.

4.  В диалоговом окне **изменение параметров журнала** введите количество дней, в **течение которых нужно хранить файлы журнала (1-365)**.

5.  Нажмите **Исполнить**. Все файлы, которые были на сервере больше указанного количества дней, удаляются. Этот параметр будет применяться к этой конфигурации, пока вы не измените ее.

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Очистка журнала обновления устройства с помощью командлетов Windows PowerShell

Вы можете очистить журналы обновления устройства с помощью Windows PowerShell и командлета **clear-ксдевицеупдателог** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>Очистка журналов обновления устройства на одном сервере

  - Следующая команда очищает журнал обновления устройства на веб-сервере atl-cs-001.litwareinc.com. Все записи журнала более 10 дней устарели (значение, указанное в параметре Дайсбакк), будет удалено из журнала.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>Очистка всех журналов обновлений устройств

  - Эта команда используется для удаления устаревших записей (в данном примере — более 10 дней назад) из всех журналов обновлений для каждого обновления устройства, которые в настоящее время используются в вашей организации.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

Дополнительные сведения можно найти в разделе справки по командлету [clear-ксдевицеупдателог](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

