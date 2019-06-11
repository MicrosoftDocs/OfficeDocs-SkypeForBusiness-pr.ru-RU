---
title: Перенос аналоговых устройств
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66866ee7cb6dafecb2c30b53d04a50f849f09c94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>Перенос аналоговых устройств

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-16_

Lync Server обеспечивает поддержку аналоговых устройств. В частности, поддерживаются аналоговые устройства аналогового и аналогового факсимильного аппарата. Вы можете настроить полные шлюзы для поддержки использования аналоговых устройств в среде Lync Server. После перехода с Lync Server 2010 на Lync Server 2013 необходимо также перенести объекты контактов, связанные с аналоговыми устройствами. Используйте командную консоль Lync Server Management Shell, чтобы сначала получить все объекты контактов, связанные с аналоговыми устройствами Lync Server 2010, а затем переместить эти объекты в пул Lync Server 2013.

<div>

## <a name="to-migrate-analog-devices"></a>Миграция аналоговых устройств

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  В командной строке выполните следующую команду:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  Убедитесь, что все объекты контакта были перемещены в пул Lync Server 2013. В командной строке выполните следующую команду:
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  Убедитесь, что все объекты контакта теперь связаны с пулом Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

