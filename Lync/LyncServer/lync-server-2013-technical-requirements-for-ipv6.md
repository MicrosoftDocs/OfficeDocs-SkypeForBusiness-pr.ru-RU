---
title: 'Lync Server 2013: технические требования к IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0688319a1b37dbd609a2f2051b3b8c6dfc6a2d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Технические требования к IPv6 в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-30_

Если вы планируете настроить Lync Server 2013 для IPv6, учитывайте указанные ниже требования.

  - Чтобы использовать IPv6-адреса в Lync Server, вам нужно создать записи DNS для записей, которые должны быть обнаружены и разрешены в IPv6-адресе. Служба DNS для IPv6 использует записи узла AAAA (quad-A). Если в развертывании используются IPv4 и IPv6, лучше всего настроить и поддерживать записи A узла для IPv4 и записи AAAA для IPv6. Даже если полностью переводите развертывание на IPv6, вам по-прежнему могут потребоваться записи DNS для IPv4 для внешних пользователей, которые все еще применяют IPv4.
    
    Можно развернуть записи узла DNS для IPv6 перед началом использования IPv6. Если клиент или сервер не используют IPv6, запись не будет указываться. Технологии туннелирования будут принимать решение относительно того, какую запись следует использовать, в зависимости от конфигурации технологии туннелирования и политик.

  - Каждый адрес IPv6 обладает определенной областью. Три области, которые можно использовать для адресации IPv6, — это глобальные адреса IPv6 (такие как общедоступные IPv4-адреса), уникальные локальные адреса IPv6 (аналогичные диапазонам частных IPv4-адресов) и локальные адреса IPv6 (аналогично автоматическим частным Windows Server для IPv4). Всем серверам в пуле должны быть назначены адреса IPv6, относящиеся к одной и той же области.

<div>


> [!IMPORTANT]  
> Протокол IPv6 — это сложная тема, требующая тщательного планирования с помощью сетевой команды и поставщика услуг Интернета, чтобы убедиться в том, что адреса, назначенные на уровне Windows Server и на уровне Lync Server 2013, работают должным образом. Для получения доступа к дополнительным ресурсам, содержащим информацию о планировании и адресации IPv6, воспользуйтесь ссылками, приведенными в конце этого раздела.



</div>

<div>

## <a name="see-also"></a>См. также


[Архитектура адресации протокола IP версии 6](http://tools.ietf.org/html/rfc4291)  
[Формат адреса глобального одноадресной рассылки IPv6](http://tools.ietf.org/html/rfc3587)  
[Уникальные локальные адреса одноадресной рассылки IPv6](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

