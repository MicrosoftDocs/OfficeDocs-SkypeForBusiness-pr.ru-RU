---
title: Создание или изменение коллекции параметров конфигурации обновления устройств
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3f58e67a0d1fc8f6b01fecfbab7c7ff7dd8f31d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Создание или изменение коллекции параметров конфигурации обновления устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Параметры конфигурации обновления устройств можно создать (только на уровне сайта) с помощью Windows PowerShell и командлета **New-CsDeviceUpdateConfiguration** , а затем изменить с помощью командлета **Set-CsDeviceUpdateConfiguration** . Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]
> Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>статье Lync Server Windows PowerShell в блоге.



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>Создание параметров конфигурации обновления устройств, использующих значения по умолчанию

  - Эта команда создает новый набор параметров конфигурации обновления устройств для сайта Redmond:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    Так как в предыдущей команде не были указаны никакие параметры, кроме обязательного параметра Identity, Новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>Изменение значения отдельного свойства при создании параметров конфигурации обновления устройств

  - Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации обновления устройств, которые по умолчанию удаляют старые файлы журнала каждые 21 дня, используйте команду, подобную следующей:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>Изменение значений нескольких свойств при создании параметров конфигурации обновления устройств

  - Чтобы изменить несколько значений свойств, можно включить несколько параметров. Например, эта команда задает для интервала очистки журнала значение 21 дня, а в качестве значения интервала сброса журнала — 30 минут:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

Для получения дополнительных сведений об изменении параметров конфигурации устройств обратитесь к разделу "Справка" для командлета [Set – CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) . Для получения дополнительных сведений о создании коллекций параметров конфигурации обратитесь к разделу "Справка" для командлета [New – CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

