---
title: Перенос аналоговых устройств
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daa85bae73df45fe8252973a3bf4d4e0690ec4a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>Перенос аналоговых устройств

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-16_

Lync Server обеспечивает поддержку аналоговых устройств. В частности, к поддерживаемым аналоговым устройствам относятся аналоговые телефоны и факсимильные аппараты. Можно настроить квалифицированные шлюзы для поддержки использования аналоговых устройств в среде Lync Server. После перехода с Lync Server 2010 на Lync Server 2013 необходимо также перенести объекты Contact, связанные с аналоговыми устройствами. Используйте командную консоль Lync Server, чтобы сначала получить все объекты Contacts, связанные с аналоговыми устройствами Lync Server 2010, а затем переместить эти объекты в пул Lync Server 2013.

<div>

## <a name="to-migrate-analog-devices"></a>Перенос аналоговых устройств

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  В командной строке введите следующую команду.
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  Убедитесь, что все объекты Contacts были перемещены в пул Lync Server 2013. В командной строке введите следующую команду.
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  Убедитесь, что все объекты Contact теперь связаны с пулом Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

