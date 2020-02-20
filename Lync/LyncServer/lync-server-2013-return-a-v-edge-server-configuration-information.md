---
title: 'Lync Server 2013: возврат сведений о конфигурации пограничного сервера аудио-и видеоданных'
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
ms.openlocfilehash: 920c45abf98678c3e866650e094b9e4a52a418a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Возврат сведений о конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Пограничная служба аудио- и видеоконференций предоставляет способ для внутренних пользователей (пользователей, выполнивших вход в сеть организации) использовать звук и видео совместно с внешними пользователями (пользователями, не выполнившими вход в сеть организации). Пограничная служба аудио- и видеоконференций в основном управляется посредством использования параметров конфигурации пограничной аудио- и видеосвязи, настройка которой может быть выполнена на уровне сайта или службы (т. е. может быть настроена для дополнительного пограничного сервера аудио- и видеоданных).

Чтобы получить сведения о параметрах конфигурации пограничного сервера аудио-и видеосвязи, используемых в Организации, необходимо использовать Windows PowerShell и командлет Get-CsAVEdgeConfiguration. Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Get – CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .

Сведения, возвращаемые командлетом Get-CsAVEdgeConfiguration, выглядят следующим образом.

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>Возврат сведений о всех параметрах конфигурации пограничного сервера аудио-и видеоданных

  - Следующая команда возвращает сведения о всех параметрах конфигурации пограничной службы обработки аудио- и видеоданных, используемых в организации.
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>Возврат сведений о параметрах конфигурации пограничного сервера аудио-и видеоданных на уровне сайта

  - Чтобы получить сведения об определенном наборе параметров конфигурации для пограничной службы обработки аудио- и видеоданных, укажите идентификатор этого набора при выполнении командлета Get-CsAVEdgeConfiguration. Например, следующая команда возвращает сведения только о тех параметрах, которые применяются к сайту Redmond.
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>Возврат сведений о параметрах конфигурации пограничного сервера аудио-и видеоданных на уровне службы

  - Эта команда возвращает сведения только о тех параметрах, которые применяются к определенному пограничному серверу аудио- и видеоданных.
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Удаление существующей коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Пограничные серверы аудио/видео (A/V) в Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

