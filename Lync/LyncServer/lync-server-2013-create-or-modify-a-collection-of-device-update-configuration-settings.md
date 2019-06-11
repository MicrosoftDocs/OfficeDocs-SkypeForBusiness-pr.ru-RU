---
title: Создание или изменение коллекции параметров конфигурации центра обновления устройства
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d5b53ff6e876a2c5226b6728e0ebde95d55e7ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Создание или изменение коллекции параметров конфигурации обновления устройства в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Параметры конфигурации обновления устройства можно создать (только на уровне сайта) с помощью Windows PowerShell и командлета **New-ксдевицеупдатеконфигуратион** , а затем изменить с помощью командлета **Set-ксдевицеупдатеконфигуратион** . Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]
> Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>Создание параметров конфигурации обновления устройства, использующих значения по умолчанию

  - Эта команда создает новый набор параметров конфигурации обновления устройства для сайта Redmond.
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    Поскольку в предыдущей команде не указаны никакие параметры, кроме обязательных параметров, Новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех его свойств.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>Изменение значения отдельного свойства при создании параметров конфигурации обновления устройства

  - Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации обновления для устройств, которые по умолчанию удаляют старые файлы журнала каждые 21 дня, используйте команду, подобную следующей:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>Изменение нескольких значений свойства при создании параметров конфигурации обновления устройства

  - Чтобы изменить несколько значений свойств, можно включить несколько параметров. Например, эта команда задает для интервала очистки журнала значение 21 дня, а интервал сброса журнала — 30 минут.
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

Подробнее об изменении существующих параметров конфигурации устройств можно узнать в разделе справки по командлету [Set-ксдевицеупдатеконфигуратион](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) . Дополнительные сведения о создании коллекций параметров конфигурации можно найти в разделе справки для командлета [New-ксдевицеупдатеконфигуратион](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

