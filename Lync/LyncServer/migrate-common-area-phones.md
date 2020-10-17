---
title: Миграция телефонов общего пользования
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af08e6de9b832289e898fd27003b896dd40fa81c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503576"
---
# <a name="migrate-common-area-phones"></a>Миграция телефонов общего пользования

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-29_

Телефоны общего пользования — это IP-телефоны, находящиеся обычно в общих рабочих помещениях или местах общего пользования, таких как вестибюли, кухни или заводские цеха. Для предоставления функций UC для Lync Server не требуется подключение к компьютеру телефонов. После переноса развертывания Lync Server 2010 на Lync Server 2013 необходимо также перенести объекты Contact, связанные с устаревшим стандартным телефоном. С помощью командной консоли Lync Server вы сначала получите все объекты Contacts, связанные с телефонами Lync Server 2010 с общими областями, а затем переместите эти объекты в пул Lync Server 2013.

**Миграция телефонов общего пользования**

1.  На сервере переднего плана Lync Server 2013 откройте консоль управления Lync Server.

2.  В командной строке введите следующую команду:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Чтобы убедиться, что все объекты Contact были перемещены в пул Lync Server 2013, в командной консоли Lync Server введите следующую команду:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Убедитесь, что все объекты Contact теперь связаны с пулом Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

