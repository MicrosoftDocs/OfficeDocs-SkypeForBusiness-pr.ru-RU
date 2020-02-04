---
title: Создание или изменение коллекции параметров конфигурации пограничного сервера
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c4b45b34b5c52d0eb138fbc16c37e5aaee7262b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Создание и изменение коллекции параметров конфигурации пограничного сервера в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Служба "A/V Edge" обеспечивает способ предоставления внутренних пользователей (пользователей, вошедших в вашу организационную сеть) для совместного использования звуковых и видеофайлов с внешними пользователями (пользователям, которые не вошли в свою организационную сеть). Служба EDGE (A/V) главным образом управляется с помощью параметров конфигурации краев/V, параметров, которые можно настроить в области сайта или в области службы (то есть можно настроить для отдельного пограничного сервера A/V).

При установке сервера Lync Server для вас создается глобальная коллекция параметров конфигурации Edge-V. Кроме того, вы можете использовать командлеты Windows PowerShell и New-Ксаведжеконфигуратион для создания новых параметров в области сайта или области службы (то есть для конкретного пограничного сервера A/V). Если вы создаете новые параметры, имейте в виду, что:

  - Параметры, настроенные для области службы (то есть на отдельном сервере), имеют приоритет над всеми.

  - Параметры, настроенные в области сайта, имеют приоритет над параметрами, настроенными в глобальной области. Однако параметры области служб также будут заменять параметры области сайта.

  - Параметры в глобальной области будут использоваться только в том случае, если на отдельном сервере не настроены параметры службы и для сайта, на котором находится этот сервер, отсутствуют параметры сайта.

Любой из параметров можно изменить с помощью командлета Set-Ксаведжеконфигуратион. Дополнительные сведения можно найти в разделах справки, посвященных командлетам [New-ксаведжеконфигуратион](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) и [Set-ксаведжеконфигуратион](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>Создание новых параметров конфигурации EDGE на странице "область сайта"

  - Следующая команда создает новую коллекцию параметров конфигурации Edge для сайта Redmond.
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>Создание настраиваемых параметров конфигурации краев/V в области сайта

  - Так как дополнительные параметры не были включены, эти новые параметры будут использовать значения по умолчанию для службы EDGE (A/V). Кроме того, вы можете добавить дополнительные параметры и значения параметров для создания настраиваемой коллекции. Например, эта команда задает для свойства Макстокенлифетиме значение 4 часа (04 часа: 00 мин: 00 с):
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>Создание настраиваемых параметров конфигурации краев/V на уровне службы

  - Эта команда создает сходную коллекцию, примененную к пограничного сервера atl-edge-001.litwareinc.com:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>Изменение существующих параметров конфигурации краев/V

  - В этом примере командлет Set-Ксаведжеконфигуратион используется для изменения максимального срока жизни токенов для сайта Redmond до 12 часов.
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>См. также


[Возврат сведений о конфигурации пограничного сервера в Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Удаление существующей коллекции параметров конфигурации пограничного сервера в Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Пограничные серверы для аудио-и видеоустройств (A/V) в Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

