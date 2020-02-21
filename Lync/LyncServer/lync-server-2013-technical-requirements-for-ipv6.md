---
title: Технические требования к Lync Server 2013 для IPv6
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
ms.openlocfilehash: 6a5565080f2b5fab0f47cc944f9569f55e8721c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Технические требования для IPv6 в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-30_

Если вы планируете настроить Lync Server 2013 для IPv6, учитывайте следующие требования:

  - Чтобы использовать IPv6-адреса с сервером Lync Server, необходимо создать записи DNS для записей, которые должны быть обнаружены и разрешены в IPv6-адресе. Служба DNS для IPv6 использует записи узла AAAA (quad-A). Если в развертывании используются IPv4 и IPv6, лучше всего настроить и поддерживать записи A узла для IPv4 и записи AAAA для IPv6. Даже если полностью переводите развертывание на IPv6, вам по-прежнему могут потребоваться записи DNS для IPv4 для внешних пользователей, которые все еще применяют IPv4.
    
    Можно развернуть записи узла DNS для IPv6 перед началом использования IPv6. Если клиент или сервер не используют IPv6, запись не будет указываться. Технологии туннелирования будут принимать решение относительно того, какую запись следует использовать, в зависимости от конфигурации технологии туннелирования и политик.

  - Каждый адрес IPv6 обладает определенной областью. Три области, которые можно использовать для адресации IPv6, это глобальные IPv6-адреса (аналогичные общедоступным IPv4-адресам), уникальные локальные адреса IPv6 (аналогично диапазонам частных IPv4-адресов) и IPv6-адресам локальной связи (аналогично автоматическим частным IP-адресам в Windows Server для IPv4). Всем серверам в пуле должны быть назначены адреса IPv6, относящиеся к одной и той же области.

<div>


> [!IMPORTANT]  
> IPv6 — это сложная тема, которая требует тщательного планирования с вашей командой сети и поставщиком услуг Интернета, чтобы убедиться в том, что адреса, назначенные на уровне Windows Server и на уровне сервера Lync Server 2013, работают должным образом. Для получения доступа к дополнительным ресурсам, содержащим информацию о планировании и адресации IPv6, воспользуйтесь ссылками, приведенными в конце этого раздела.



</div>

<div>

## <a name="see-also"></a>См. также


[Архитектура адресации протокола IP версии 6](https://tools.ietf.org/html/rfc4291)  
[Глобальный одноадресный формат IPv6](https://tools.ietf.org/html/rfc3587)  
[Уникальные локальные адреса одноадресной рассылки IPv6](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

