---
title: 'Lync Server 2013: Удаление коллекции параметров конфигурации обновления устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 520247186289f4b02a136b3109ec86fa4fa1a6a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525746"
---
# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Удаление коллекции параметров конфигурации обновления устройств в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

Параметры конфигурации обновления устройств также можно удалить с помощью Windows PowerShell и командлета **Remove – CsdeviceUpdateConfiguration** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a>Удаление определенной коллекции параметров конфигурации обновления устройств

  - Эта команда удаляет параметры конфигурации обновления устройств, примененные к сайту Redmond:
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации обновления устройств, примененных к области сайта

  - Эта команда удаляет все параметры конфигурации обновления устройств, примененные к области сайта:
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a>Удаление параметров конфигурации обновления устройств на основе значения свойства Логклеанупинтервал

  - Следующая команда удаляет все параметры конфигурации обновления устройств, для которых интервал очистки журнала превышает 10 дней (10,00:00:00):
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

Дополнительные сведения см. в разделе справки для командлета [Remove – CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

