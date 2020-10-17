---
title: 'Lync Server 2013: включение качества обслуживания для устройств, не основанных на Windows'
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
ms.openlocfilehash: e9fe6364e92fc6416a78ec49001e94193ae9731e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500936"
---
# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Включение качества обслуживания в Lync Server 2013 для устройств, не основанных на Windows

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

При установке Microsoft Lync Server 2013, качество обслуживания (QoS) не будет включено для устройств, используемых в Организации, использующих операционную систему, отличную от Windows. Это можно проверить, выполнив следующую команду в командной консоли Lync Server 2013:

    Get-CsMediaConfiguration

Если вы не вносили изменений в параметры настройки сервера-посредника, должна быть возвращена следующая информация:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Если для свойства Енаблекос задано значение false (как в предыдущем выводе), то это означает, что качество службы не включено для компьютеров и устройств, использующих операционную систему, отличную от Windows. По умолчанию качество обслуживания включено для устройств Lync Phone Edition; Тем не менее, можно отключить качество обслуживания для Lync Phone Edition.

Чтобы включить качество службы в глобальной области, выполните следующую команду в командной консоли Lync Server:

    Set-CsMediaConfiguration -EnableQoS $True

Предыдущая команда включает качество обслуживания на глобальном уровне. Однако важно заметить, что параметры конфигурации сервера-посредника также можно применить на уровне узла. Если нужно включить качество обслуживания для узла, укажите идентификатор параметров конфигурации при вызове командлета Set-CsMediaConfiguration. Например, следующая команда включает качество обслуживания для узла Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> Необходимость в использовании качества обслуживания на уровне узла зависит от обстоятельств. Параметры, назначенные на уровне узла, имеют приоритет перед заданными на глобальном уровне. Предположим, что вы включили качество обслуживания на глобальном уровне, но отключили на уровне узла (для узла Redmond). В этом случае качество обслуживания будет отключено для узла Redmond, так как параметры узла имеют приоритет. Чтобы включить качество обслуживания для узла Redmond, вам потребуется воспользоваться параметрами конфигурации сервера-посредника, применяемыми к этому узлу.



</div>

Если вы хотите одновременно включить QoS для всех параметров конфигурации мультимедиа (независимо от области), выполните следующую команду в командной консоли Lync Server:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Можно отключить службу QoS для устройств, использующих операционную систему, отличную от Windows, задав для свойства Енаблекос значение false. Пример:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Таким образом вы можете включить качество обслуживания для отдельных частей сети (например, узла Redmond), не включая его для других частей.

Службу QoS можно включать и отключать только с помощью Windows PowerShell. Эти параметры недоступны в панели управления Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

