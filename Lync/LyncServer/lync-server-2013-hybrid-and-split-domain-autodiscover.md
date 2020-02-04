---
title: 'Lync Server 2013: гибридный и разделяемый домен — автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce38bba4717e3340e7eacf33ce67fc357d208b83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Гибридная и Разделяемая доменные возможности автообнаружения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-14_

Общее адресное пространство SIP, также называемое развертыванием с *разделением доменов* или *гибридным* развертыванием, — это конфигурация, в которой пользователи развертываются в рамках локального развертывания и из Интернета. Желаемый результат состоит в том, что пользователь вне зависимости от того, где расположен домашний сервер (локально или в сети), подключается к развертыванию и перенаправляется на место своего домашнего сервера. Для этого функция автообнаружения в Lync Server 2013 используется для перенаправления пользователя Online в сетевую топологию. Это можно сделать, настроив указатель URL-адреса автообнаружения с помощью командной консоли Lync Server Management Shell, командлета **Get-кшостингпровидер** и командлета **Set-кшостингпровидер** .

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Мобильность для раздельного развертывания доменов

Вам потребуется собрать и записать следующие развернутые атрибуты:

  - В командной консоли Lync Server введите
    
        Get-CsHostingProvider

  - В результатах найдите Интернет-провайдер с атрибутом **проксифкдн**. Например, sipfed.online.lync.com.

  - Запишите значение параметра Проксифкдн.

  - Включите Федерацию в локальной панели управления Lync Server и разрешите Федерацию с помощью веб-поставщика.

  - Включите Федерацию для поставщика услуг Интернета. По умолчанию все пользователи в сети включены в доменную Федерацию и могут взаимодействовать со всеми доменами.

  - Если вы определяете блокируемые и разрешенные домены, определите домены, которые будут явно разрешены или явным образом заблокированы.

  - Для службы интеграции с Интернетом необходимо планировать исключения брандмауэра, сертификаты и узел DNS (A или AAAA, если используется IPv6). Кроме того, необходимо настроить политики Федерации. Подробные сведения можно найти в разделе [планирование для Lync server 2013 и Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

