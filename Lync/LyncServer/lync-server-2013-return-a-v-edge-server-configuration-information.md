---
title: 'Lync Server 2013: возврат сведений о конфигурации пограничного сервера/V'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea7d7ed1ef74c092dac60ecfb2f009219564455
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Возврат сведений о конфигурации пограничного сервера в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Служба "A/V Edge" обеспечивает способ предоставления внутренних пользователей (пользователей, вошедших в вашу организационную сеть) для совместного использования звуковых и видеофайлов с внешними пользователями (пользователям, которые не вошли в свою организационную сеть). Служба EDGE (A/V) главным образом управляется с помощью параметров конфигурации краев/V, параметров, которые можно настроить в области сайта или в области службы (то есть можно настроить для отдельного пограничного сервера A/V).

Чтобы получить сведения о параметрах конфигурации краев, используемых в вашей организации, необходимо использовать Windows PowerShell и командлет Get-Ксаведжеконфигуратион. Дополнительные сведения можно найти в разделе справки по командлету [Get-ксаведжеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .

Данные, возвращаемые командлетом Get-Ксаведжеконфигуратион, будут выглядеть примерно так:

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>Получение сведений о всех параметрах конфигурации Edge

  - Следующая команда возвращает сведения обо всех параметрах, которые используются в вашей организации в качестве параметров конфигурации Edge для/V.
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>Возврат сведений о параметрах конфигурации сайта в качестве границы области

  - Чтобы получить сведения о конкретной коллекции параметров конфигурации краев/V, укажите удостоверение этой коллекции при запуске командлета Get-Ксаведжеконфигуратион. Например, эта команда возвращает сведения только о параметрах, примененных к сайту Redmond.
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>Возврат сведений о параметрах конфигурации краев, заданных в пределах службы

  - Эта команда возвращает данные только для параметров, примененных к конкретному пограничному серверу/V.
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>См. также


[Создание и изменение коллекции параметров конфигурации пограничного сервера в Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Удаление существующей коллекции параметров конфигурации пограничного сервера в Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Пограничные серверы для аудио-и видеоустройств (A/V) в Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

