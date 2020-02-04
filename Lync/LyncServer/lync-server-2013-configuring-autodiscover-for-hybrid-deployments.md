---
title: 'Lync Server 2013: Настройка автообнаружения для гибридных развертываний'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8924194d89eafb75c06ff78ed3b765699e36b196
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>Настройка автообнаружения в Lync Server 2013 для гибридных развертываний

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-12-12_

Гибридное развертывание — это конфигурация, использующая как облачную службу Microsoft Lync Online, так и локальное развертывание. В этом типе конфигурации Служба автообнаружения должна находить место, где пользователь фактически находится. Это означает, что средства автообнаружения помогают найти учетную запись пользователя и сервер, на котором размещена учетная запись пользователя, независимо от того, есть ли в локальном развертывании или в развертывании Lync Online.

Например, если учетная запись пользователя размещена на сервере в Lync Online, попытка найти пользователя будет выполняться следующим образом в процессе, известном как *обнаруживаемость*.

  - Пользователь инициирует попытку подключения к локальному развертыванию **contoso.com**.

  - Предпринята попытка отправки в lyncdiscover.contoso.com, DNS-имя, связанное со службой автообнаружения.

  - Автообнаружения — это предполагаемый пул регистраторов в локальной среде развертывания contoso.com и получает сведения на основном сервере, размещенном на Lync Online. Затем служба автообнаружения отправляет пользователю ссылку на службу автообнаружения **Lync.com** Online.

  - Пользователь инициирует попытку подключения к службе автообнаружения lync.com Online и может найти учетную запись пользователя и домашний сервер пользователя.

Чтобы разрешить клиентам определять развертывание, в котором находится домашний сервер пользователей, необходимо настроить службу автообнаружения с помощью нового URL-адреса. Чтобы настроить службу автообнаружения, выполните указанные ниже действия.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Настройка автообнаружения для гибридных развертываний

1.  В теме, [требования к службе автообнаружения для Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), вы можете использовать Get-кшостингпровидер для получения значения атрибута проксифкдн.

2.  В командной консоли Lync Server введите
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    Где \[идентификатор\] заменяется доменным именем общего адресного пространства SIP.

</div>

<div>

## <a name="see-also"></a>См. также


[Get-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

