---
title: 'Lync Server 2013: Настройка службы Mobility Service для высокой производительности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29eaea1e45c5d3b745debbc2f97370a76e6d16db
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Настройка службы Mobility Service для высокой производительности в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-17_

<div>


> [!IMPORTANT]  
> Этот раздел относится только к службе мобильной связи Lync Server 2013 (МККС) и не применяется к веб-API единой системы обмена сообщениями (УКВА), как в накопительных обновлениях для Lync Server 2013: Февраль 2013.



</div>

При установке службы Mobility Service (МККС) в службах IIS 7,5 программа установки службы Mobility Service настраивает некоторые параметры быстродействия на сервере переднего плана. We recommend that you use IIS 7.5 for mobility. The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.

Далее представлены параметры производительности:

<div>

## <a name="settings-for-mcx-on-iis-75"></a>Параметры для Mcx в службе IIS 7.5

1.  **maxConcurrentThreadsPerCPU** имеет значение нуля (0).

2.  **maxConcurrentRequestsPerCPU** имеет значение нуля (0).

3.  Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).

4.  Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).

</div>

</div>

<span> </span>

</div>

</div>

</div>

