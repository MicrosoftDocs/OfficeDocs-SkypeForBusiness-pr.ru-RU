---
title: Настройка службы автообнаружения для мобильной работы с гибридными развертываниями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3b0617094c9dcab6b6eee0cf634440fea63cf16
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502166"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>Настройка службы автообнаружения в Lync Server 2013 для мобильной работы с гибридными развертываниями

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-06-18_

Гибридные развертывания — это конфигурации, в которых используются как облачная служба Microsoft Lync Online, так и локальное развертывание. В такой конфигурации служба автообнаружения должна иметь возможность определять действительное расположение пользователя. Это означает, что служба автообнаружения помогает найти учетную запись пользователя и сервера, на котором размещается учетная запись пользователя, независимо от того, находится ли он в локальном развертывании или в развертывании Lync Online.

Например, если учетная запись пользователя размещена на сервере в Lync Online, попытка обнаружения пользователя будет выполняться следующим образом, в процессе, известном как *обнаруживаемость*.

  - Пользователь предпринимает попытку подключения к локальному развертыванию **contoso.com**.

  - Сведения о такой попытке отправляются на lyncdiscover.contoso.com — DNS-имя, сопоставленное со службой автообнаружения.

  - Служба автообнаружения относится к предполагаемому пулу регистратора в contoso.com локальное развертывание и получает информацию о фактическом основном сервере пользователя, размещенном в Lync Online. После этого служба автообнаружения отправляет пользователю ссылку на Интернет-службу автообнаружения **lync.com**.

  - Пользователь предпринимает попытку подключения к Интернет-службе автообнаружения lync.com и может обнаружить учетную запись и почтовый сервер пользователя.

Чтобы предоставить мобильным клиентам возможность обнаружения развертывания, в котором размещен домашний сервер пользователя, необходимо настроить службу автообнаружения с новым унифицированным указателем ресурсов (URL-адресом). Выполните следующие действия для настройки службы автообнаружения.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Настройка службы автообнаружения для гибридного развертывания

1.  Для получения значения атрибута ProxyFQDN используется Get-CsHostingProvider.

2.  В командной консоли Lync Server введите
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    Где \[ Identity \] заменяется доменным именем общего адресного пространства SIP.

</div>

<div>

## <a name="see-also"></a>См. также


[Get — CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))  
[Set — CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

