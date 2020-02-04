---
title: Удаление существующей коллекции параметров конфигурации пограничного сервера/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cc085cd6ac39c4712647795c5baf06eaa68f77a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Удаление существующей коллекции параметров конфигурации пограничного сервера в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Служба "A/V Edge" обеспечивает способ предоставления внутренних пользователей (пользователей, вошедших в вашу организационную сеть) для совместного использования звуковых и видеофайлов с внешними пользователями (пользователям, которые не вошли в свою организационную сеть). Служба EDGE (A/V) главным образом управляется с помощью параметров конфигурации краев/V, параметров, которые можно настроить в области сайта или в области службы (то есть можно настроить для отдельного пограничного сервера A/V).

При установке сервера Lync Server для вас создается глобальная коллекция параметров конфигурации Edge-V. Эту глобальную коллекцию нельзя удалить. Тем не менее, вы можете использовать командлеты Windows PowerShell и Remove-Ксаведжеконфигуратион для "сброса" глобальной коллекции; Это означает, что все значения свойств в глобальной коллекции будут сбрасываться к значениям по умолчанию. Например, если для свойства Макстокенлифетиме задано значение 16 часов, для этого свойства по умолчанию будет назначено 8 часов.

Тем не менее, пользовательские коллекции параметров, созданные на уровне сайта или в области службы, можно удалить с помощью командлета Remove-Ксаведжеконфигуратион. Если вы удалите параметры сайта, то на них будут управлять серверы пограничного сервера/V с помощью глобальных параметров. Если вы удалили параметры области службы, то этот сервер будет управляться с помощью параметров сайта, если они существуют, или с помощью глобальных параметров, если параметры сайта недоступны.

Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксаведжеконфигуратион](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>Сброс глобальной коллекции

  - Следующая команда сбрасывает глобальную коллекцию для параметров конфигурации Edge/V.
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>Удаление коллекции из области сайта

  - Эта команда удаляет параметры конфигурации Edge/V, примененные к сайту Redmond.
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>Удаление коллекции из области служб

  - Эта команда удаляет параметры, примененные к серверу пограничного сервера/V atl-edge-001.litwareinc.com:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>См. также


[Возврат сведений о конфигурации пограничного сервера в Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Создание и изменение коллекции параметров конфигурации пограничного сервера в Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Пограничные серверы для аудио-и видеоустройств (A/V) в Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

