---
title: 'Lync Server 2013: Мониторинг файлов журнала трассировки запросов IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1257e350dd7695bf132959d6b4cde4843192e41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>Мониторинг файлов журнала трассировки запросов IIS в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

При включении трассировки запросов служб IIS для службы Lync Server Mobility Service (МККС) создаваемые файлы журнала могут занимать до 3 ГБ дискового пространства за день. IIS trace logging is enabled by default. Убедитесь, что на серверах переднего плана не осталось свободного места.

По умолчанию службы IIS хранят файлы журнала на странице журнала%\\systemdrive\\%\\инетпуб.

Чтобы отключить трассировку запросов служб IIS для всего сервера, выполните в командной строке следующую команду:

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Подробные сведения о команде **хттплоггинг** можно найти [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927)в статьях.

</div>

<span> </span>

</div>

</div>

</div>

