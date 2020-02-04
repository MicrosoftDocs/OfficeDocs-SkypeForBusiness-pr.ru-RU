---
title: 'Lync Server 2013: Включение QoS для устройств, которые не основаны на Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7574169c5a8c9cb660a81b384711a4937056b37
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Включение QoS в Lync Server 2013 для устройств, которые не основаны на Windows

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

При установке Microsoft Lync Server 2013, качество обслуживания (QoS) не будет разрешено для устройств, используемых в вашей организации, которые используют операционную систему, отличную от Windows. Это можно проверить, запустив в командной консоли Lync Server 2013 следующую команду:

    Get-CsMediaConfiguration

Если вы не внесли никаких изменений в параметры конфигурации мультимедиа, вы должны получить информацию примерно так:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Если для свойства Енаблекос задано значение false (как в предыдущем выводе), это означает, что качество обслуживания не разрешено для компьютеров и устройств, использующих операционную систему, отличную от Windows. Служба QoS включена по умолчанию для устройств Lync Phone Edition; Однако можно отключить качество обслуживания для Lync Phone Edition.

Чтобы включить качество обслуживания в глобальной области, выполните в командной консоли Lync Server следующую команду:

    Set-CsMediaConfiguration -EnableQoS $True

Предыдущая команда включает QoS в глобальной области; Однако важно отметить, что параметры конфигурации мультимедиа также можно применить к области сайта. Если необходимо включить качество обслуживания для сайта, необходимо включить удостоверение параметров конфигурации при вызове Set-Ксмедиаконфигуратион. Например, эта команда включает QoS для сайта Redmond.

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> Нужно ли включить качество обслуживания в области сайта? Смотря как. Параметры, назначенные области сайта, имеют приоритет над параметрами, назначенными глобальной области. Предположим, что в глобальной области включена служба QoS, но она отключена в области сайта (для сайта Redmond). В этом случае качество обслуживания для сайта Redmond будет отключено. Это связано с тем, что параметры сайта имеют приоритет. Чтобы включить QoS для сайта Redmond, вам понадобится использовать параметры конфигурации мультимедиа, примененные к этому сайту.



</div>

Если вы хотите одновременно включить QoS для всех параметров конфигурации мультимедиа (независимо от области), выполните эту команду в командной консоли Lync Server Management Shell.

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Вы можете отключить QoS для устройств, использующих операционную систему, отличную от Windows, установив для свойства Енаблекос значение false. Например:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Это позволяет реализовать качество обслуживания для некоторых частей сети (например, на сайте Redmond), не отключая качество обслуживания для других частей сети.

Вы можете включить и отключить QoS только с помощью Windows PowerShell. Эти параметры недоступны на панели управления Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

