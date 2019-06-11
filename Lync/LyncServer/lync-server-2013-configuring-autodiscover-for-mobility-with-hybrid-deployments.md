---
title: Настройка службы автообнаружения для мобильной работы с гибридными развертываниями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1865cab188bace472996db6207de62ce8498976
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>Настройка службы автообнаружения в Lync Server 2013 для мобильной работы с гибридными развертываниями

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-06-18_

Гибридное развертывание — это конфигурация, использующая как облачную службу Microsoft Lync Online, так и локальное развертывание. В этом типе конфигурации Служба автообнаружения должна находить место, где пользователь фактически находится. Это означает, что средства автообнаружения помогают найти учетную запись пользователя и сервер, на котором размещена учетная запись пользователя, независимо от того, есть ли в локальном развертывании или в развертывании Lync Online.

Например, если учетная запись пользователя размещена на сервере в Lync Online, попытка найти пользователя будет выполняться следующим образом в процессе, известном как *обнаруживаемость*.

  - Пользователь инициирует попытку подключения к локальному развертыванию **contoso.com**.

  - Предпринята попытка отправки в lyncdiscover.contoso.com, DNS-имя, связанное со службой автообнаружения.

  - Автообнаружения — это предполагаемый пул регистраторов в локальной среде развертывания contoso.com и получает сведения на основном сервере, размещенном на Lync Online. Затем служба автообнаружения отправляет пользователю ссылку на службу автообнаружения **Lync.com** Online.

  - Пользователь инициирует попытку подключения к службе автообнаружения lync.com Online и может найти учетную запись пользователя и домашний сервер пользователя.

Чтобы разрешить мобильным клиентам найти развертывание, в котором находится домашний сервер пользователей, необходимо настроить службу автообнаружения с помощью нового URL-адреса. Чтобы настроить службу автообнаружения, выполните указанные ниже действия.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Настройка автообнаружения для гибридных развертываний

1.  Функция Get-Кшостингпровидер используется для получения значения атрибута Проксифкдн.

2.  В командной консоли Lync Server введите
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    Где \[идентификатор\] заменяется доменным именем общего адресного пространства SIP.

</div>

<div>

## <a name="see-also"></a>См. также


[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

