---
title: Создание или изменение коллекции параметров конфигурации пограничного сервера аудио-и видеоданных
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
ms.openlocfilehash: 3ec601a9c51e1b8d5785e91bae1f1f82c13bf245
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514776"
---
# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Создание или изменение коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Пограничная служба аудио- и видеоконференций предоставляет способ для внутренних пользователей (пользователей, выполнивших вход в сеть организации) использовать звук и видео совместно с внешними пользователями (пользователями, не выполнившими вход в сеть организации). Пограничная служба аудио- и видеоконференций в основном управляется посредством использования параметров конфигурации пограничной аудио- и видеосвязи, настройка которой может быть выполнена на уровне сайта или службы (т. е. может быть настроена для дополнительного пограничного сервера аудио- и видеоданных).

При установке Lync Server создается глобальная коллекция параметров конфигурации пограничного сервера аудио-и видеоданных. Кроме того, вы можете использовать командлеты Windows PowerShell и New-CsAVEdgeConfiguration для создания новых параметров на уровне сайта или на уровне службы (то есть для отдельного пограничного сервера аудио-и видеоданных). При создании новых параметров следует помнить о следующем.

  - Параметры, настроенные на уровне службы (то есть на каждом отдельном сервере), имеют самый высокий приоритет.

  - Параметры, настроенные на уровне сайта, имеют приоритет над параметрами, настроенными на глобальном уровне. Однако они переопределяются параметрами на уровне службы.

  - Параметры глобального уровня будут использоваться, только если отсутствуют параметры служб, настроенные на отдельном сервере, а также отсутствуют параметры сайта, в котором расположен тот или иной сервер.

Любой из параметров может быть изменен с помощью командлета Set-CsAVEdgeConfiguration. Для получения дополнительных сведений обратитесь к разделам справки для командлетов [New – CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) и [Set – CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>Создание новых параметров конфигурации пограничного сервера аудио-и видеоданных на уровне сайта

  - Следующая команда создает коллекцию параметров конфигурации пограничного сервера аудио- и видеоданных для сайта Redmond.
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>Создание настраиваемых параметров конфигурации пограничного сервера аудио-и видеоданных на уровне сайта

  - Так как дополнительных параметров не было включено, эти новые параметры будут использовать значения по умолчанию для пограничной службы звука и видео. Кроме того, можно добавить дополнительные параметры и значения параметров для создания пользовательской коллекции. Например, следующая команда задает для свойства MaxTokenLifetime значение 4 часа (04 ч : 00 мин. : 00 сек.):
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>Создание настраиваемых параметров конфигурации пограничного сервера аудио-и видеоданных на уровне службы

  - Эта команда создает аналогичную коллекцию, примененную к пограничному серверу звука и видео atl-edge-001.litwareinc.com:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>Изменение существующих параметров конфигурации пограничного сервера аудио-и видеоданных

  - В этом примере командлет Set-CsAVEdgeConfiguration используется для изменения максимального срока жизни маркера для сайта Redmond на 12 часов:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>См. также


[Возврат сведений о конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Удаление существующей коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Пограничные серверы аудио/видео (A/V) в Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))  
[Set — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

