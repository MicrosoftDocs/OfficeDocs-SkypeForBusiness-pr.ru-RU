---
title: 'Lync Server 2013: Проверка параметров конфигурации магистрали SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97257add21595770716b3310aed6c59a018ad1b6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519186"
---
# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a>Проверка параметров конфигурации магистрали SIP в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:

  - Следует ли включить обход медиаданных на линиях связи.

  - Условия, при которых передаются пакеты по протоколу RTCP.

  - Требуется ли шифрование по протоколу SRTP на каждой магистрали.

При установке Microsoft Lync Server 2013 создается глобальная коллекция параметров конфигурации магистрали SIP. Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП). Кроме того, администраторы могут использовать командлет Test-CsTrunkConfiguration, чтобы убедиться, что магистраль может преобразовать номер, набранный пользователем, на номер, который может обрабатываться шлюзом.

Параметры конфигурации магистрали можно тестировать только с помощью Windows PowerShell и командлета [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a>Тестирование параметров конфигурации магистрали SIP

  - Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набранный номер 4255551212.
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

