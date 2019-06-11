---
title: 'Lync Server 2013: Настройка SNMP для приложения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a15a911abc614ff30c4130fb2a35886458fcb1dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Настройка приложения SNMP в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-03_

Lync Server 2013 включает стандартный интерфейс веб-службы, который можно использовать для подключения службы сведений о расположении к приложениям протокола SNMP, которые соответствуют MAC-адресам с портом и переключаются.

Если установлено приложение SNMP и служба "сведения о местоположении" не может найти соответствие в базе данных расположения, Служба сведений о расположении автоматически запрашивает это приложение, используя MAC-адрес, предоставленный клиентом. Затем служба сведения о местоположении использует данные порта и коммутатора, возвращенные приложением SNMP, для повторного запроса к базе данных о расположении.

Подробности можно найти в разделе [Set-ксвебсервицеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).

<div>


> [!NOTE]  
> MAC-адреса недоступны на компьютерах под управлением Windows 8.



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>Настройка URL-адреса приложения SNMP

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Запустите следующий командлет для настройки URL-адреса приложения SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

