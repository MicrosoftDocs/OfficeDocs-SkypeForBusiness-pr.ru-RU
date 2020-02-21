---
title: 'Lync Server 2013: удаление файлов журнала обновления устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 685b3e34c0f2bd5392f71899564d0738e814b616
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Удаление файлов журнала обновления устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Веб-служба обновления устройств хранит обширный набор файлов журналов. Эта коллекция включает оба журнала аудита, выполненных самой службой, а также файлами журналов, отправленных с клиентских устройств. Чтобы не допустить переполнения сервера с помощью журналов веб-службы обновления устройств, вы, вероятно, захотите очистить файл журнала, который выполнялся в течение определенного числа дней. Установите это количество дней в соответствии с действиями по обновлению и числом клиентских устройств в Организации, а также с помощью панели управления Lync Server или командной консоли Lync Server.

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>Очистка журнала обновлений устройств с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации последовательно выберите пункты **Клиенты** и **Конфигурация журналов устройств**.

3.  На странице **Конфигурация журналов устройств** дважды щелкните конфигурацию, которую требуется изменить.

4.  В диалоговом окне **изменение параметров журнала** в поле **число дней хранения файлов журнала (1-365)** укажите количество дней.

5.  Щелкните **Исполнить**. Все файлы, находились на сервере дольше указанного числа дней, удаляются. Этот параметр применяется к этой конфигурации, пока не будет изменен.

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Очистка журнала обновлений устройств с помощью командлетов Windows PowerShell

Вы можете очистить журналы обновления устройств с помощью Windows PowerShell и командлета **clear – ксдевицеупдателог** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>статье Lync Server Windows PowerShell в блоге.



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>Очистка журналов обновления устройств на одном сервере

  - Следующая команда очищает журнал обновлений устройств на веб-сервере atl-cs-001.litwareinc.com. Все записи журнала старше 10 дней (значение, указанное параметром Дайсбакк), будет удалено из журнала.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>Очистка всех журналов обновлений устройств

  - Эта команда удаляет устаревшие записи (в данном примере записи старше 10 дней) из всех журналов обновления устройств, используемых в настоящее время в Организации.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

Дополнительные сведения см. в разделе справки для командлета [clear – ксдевицеупдателог](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

