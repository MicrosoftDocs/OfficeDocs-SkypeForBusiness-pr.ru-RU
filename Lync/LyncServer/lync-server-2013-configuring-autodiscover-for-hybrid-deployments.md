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
ms.openlocfilehash: d6015603d2c8c151cbe9d9b76410e51708f3ba9e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>Настройка службы автообнаружения в Lync Server 2013 для гибридных развертываний

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-12-12_

Гибридные развертывания — это конфигурации, в которых используются как облачная служба Microsoft Lync Online, так и локальное развертывание. В такой конфигурации служба автообнаружения должна иметь возможность определять действительное расположение пользователя. Это означает, что служба автообнаружения помогает найти учетную запись пользователя и сервера, на котором размещается учетная запись пользователя, независимо от того, находится ли он в локальном развертывании или в развертывании Lync Online.

Например, если учетная запись пользователя размещена на сервере в Lync Online, попытка обнаружения пользователя будет выполняться следующим образом, в процессе, известном как *обнаруживаемость*.

  - Пользователь предпринимает попытку подключения к локальному развертыванию **contoso.com**.

  - Сведения о такой попытке отправляются на lyncdiscover.contoso.com — DNS-имя, сопоставленное со службой автообнаружения.

  - Служба автообнаружения относится к предполагаемому пулу регистратора в contoso.com локальное развертывание и получает информацию о фактическом основном сервере пользователя, размещенном в Lync Online. После этого служба автообнаружения отправляет пользователю ссылку на Интернет-службу автообнаружения **lync.com**.

  - Пользователь предпринимает попытку подключения к Интернет-службе автообнаружения lync.com и может обнаружить учетную запись и почтовый сервер пользователя.

Чтобы разрешить клиентам обнаруживать развертывание, в котором находится домашний сервер пользователей, необходимо настроить службу автообнаружения с помощью нового URL-адреса. Выполните следующие действия для настройки службы автообнаружения.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Настройка службы автообнаружения для гибридного развертывания

1.  В разделе, [требования к службе автообнаружения для Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), вы можете использовать Get – CsHostingProvider для получения значения атрибута ProxyFQDN.

2.  В командной консоли Lync Server введите
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    Где \[Identity\] заменяется доменным именем общего адресного пространства SIP.

</div>

<div>

## <a name="see-also"></a>См. также


[Get — CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Set — CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

