---
title: Удаление существующей коллекции параметров конфигурации пограничного сервера аудио-и видеоданных
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
ms.openlocfilehash: 901562812e7847a6c205f042922dca6383ad6254
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Удаление существующей коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Пограничная служба аудио- и видеоконференций предоставляет способ для внутренних пользователей (пользователей, выполнивших вход в сеть организации) использовать звук и видео совместно с внешними пользователями (пользователями, не выполнившими вход в сеть организации). Пограничная служба аудио- и видеоконференций в основном управляется посредством использования параметров конфигурации пограничной аудио- и видеосвязи, настройка которой может быть выполнена на уровне сайта или службы (т. е. может быть настроена для дополнительного пограничного сервера аудио- и видеоданных).

При установке Lync Server создается глобальная коллекция параметров конфигурации пограничного сервера аудио-и видеоданных. Эта глобальная коллекция не может быть удалена. Тем не менее, вы можете использовать командлеты Windows PowerShell и Remove-CsAVEdgeConfiguration, чтобы сбросить глобальную коллекцию; Это означает, что все значения свойств в глобальной коллекции будут сброшены в значения по умолчанию. Например, если для свойства MaxTokenLifetime было задано значение 16 часов, для свойства будет возвращено значение по умолчанию, равное 8 часам.

Однако коллекции пользовательских параметров, созданных на уровне сайта или службы, могут быть удалены с помощью командлета Remove-CsAVEdgeConfiguration. Если удалить параметры сайта, пограничные серверы звука и видео в этом сайте будут  управляться глобальными параметрами. Если удалить параметры уровня службы, соответствующий сервер будет управляться параметрами своего сайта, если таковые существуют, или глобальными параметрами, если параметры сайта отсутствуют.

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>Сброс глобальной коллекции

  - Следующая команда сбрасывает глобальную коллекцию параметров конфигурации пограничного сервера звука и видео:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>Удаление коллекции из области сайта

  - Данная команда удаляет параметры конфигурации пограничного сервера аудио и видео для сайта Redmond:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>Удаление коллекции из области службы

  - Эта команда удаляет параметры, примененные к пограничному серверу звука и видео atl-edge-001.litwareinc.com:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>См. также


[Возврат сведений о конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Создание или изменение коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Пограничные серверы аудио/видео (A/V) в Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

