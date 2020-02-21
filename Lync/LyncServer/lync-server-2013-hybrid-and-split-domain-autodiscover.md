---
title: 'Lync Server 2013: гибридное и разделенное доменное обнаружение'
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
ms.openlocfilehash: 3fca0097f6ad0264755dd9d0a80a296e9ebf60b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Гибридное и комбинированное доменное обнаружение в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-14_

Общее адресное пространство SIP, которое также называется развертыванием с *разделенным доменом* или *гибридным* развертыванием, представляет собой конфигурацию, в которой пользователи развертываются в локальном развертывании и в интерактивной среде. Желаемый результат состоит в том, что пользователь независимо от того, где находится домашний сервер (локальный или в сети), подключается к развертыванию и перенаправляется на расположение домашнего сервера. Для этого используется функция автообнаружения Lync Server 2013 для перенаправления интерактивного пользователя в сетевую топологию. Это можно сделать, настроив URL-адрес автообнаружения с помощью командной консоли Lync Server, командлета **Get-CsHostingProvider** и командлета **Set-CsHostingProvider** .

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Мобильность для развертывания разделенного домена

Вам потребуется собрать и записать следующие развернутые атрибуты:

  - В командной консоли Lync Server введите
    
        Get-CsHostingProvider

  - В результатах найдите сетевого поставщика с атрибутом **ProxyFQDN**. Например, sipfed.online.lync.com.

  - Запишите значение параметра ProxyFQDN.

  - Включите Федерацию на локальной панели управления Lync Server, разрешив Федерацию с поставщиком в Интернете.

  - Включите федерацию для этого сетевого поставщика. По умолчанию для всех интерактивных пользователей включена Федерация домена и могут связываться со всеми доменами.

  - Если вы определите заблокированные и разрешенные домены, определите домены, которые вы явно разрешите или явным образом заблокируйте.

  - Для Интернет-Федерации необходимо спланировать исключения брандмауэра, сертификаты и узел DNS (A или AAAA, если используется IPv6). Кроме того, следует настроить политики федерации. Дополнительные сведения см. в статье [планирование для интеграции Lync server 2013 и Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

