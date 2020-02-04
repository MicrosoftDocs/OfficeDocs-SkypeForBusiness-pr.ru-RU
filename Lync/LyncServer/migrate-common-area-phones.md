---
title: Миграция телефонов общего пользования
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba32f8aa95b870190280aebd94d51bdbeec0f2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>Миграция телефонов общего пользования

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-29_

Обычные телефоны — это IP-телефоны, которые чаще всего находятся в общей рабочей области или в общей области, например в зале ожидания, кухни или фабрики. Для обеспечения функций UC для Lync Server не нужно подключаться к компьютеру с помощью обычных телефонов. После миграции развертывания Lync Server 2010 на Lync Server 2013 необходимо также перенести объекты контактов, связанные с устаревшим стандартным телефоном. С помощью командной консоли Lync Server вы сначала получите все объекты контактов, связанные с Lync Server 2010 Common Area Phone, а затем переместите эти объекты в пул Lync Server 2013.

**Миграция телефонов общего пользования**

1.  На сервере переднего плана Lync Server 2013 откройте консоль управления Lync Server.

2.  В командной строке введите следующую команду:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Чтобы убедиться в том, что все объекты контакта были перемещены в пул Lync Server 2013, в командной консоли Lync Server Management Shell введите следующую команду:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Убедитесь, что все объекты контакта теперь связаны с пулом Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

