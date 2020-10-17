---
title: 'Lync Server 2013: Настройка приложения SNMP'
description: 'Lync Server 2013: Настройка приложения SNMP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7374b61ad85d7ddcb40ef1db535e17f86dea58f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546705"
---
# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Настройка приложения SNMP в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-03_

Lync Server 2013 включает стандартный интерфейс веб-службы, который можно использовать для подключения службы сведений о местоположении к приложениям SNMP, которые совпадают с MAC-адресами и сведениями о порте и коммутаторе.

Если приложение SNMP установлено и служба сведений о местоположении не может найти соответствующее значение в базе данных расположений, Служба сведений о местоположении автоматически запрашивает приложение, используя MAC-адрес, предоставленный клиентом. Затем служба "сведения о местоположении" использует сведения о порте и коммутаторе, возвращенные приложением SNMP, для повторного запроса к базе данных расположений.

Дополнительные сведения см. в статье [Set – CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).

<div>


> [!NOTE]  
> MAC-адреса недоступны на компьютерах под управлением Windows 8.



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>Настройка URL-адреса приложения SNMP

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Запустите следующий командлет для настройки URL-адреса приложения SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

