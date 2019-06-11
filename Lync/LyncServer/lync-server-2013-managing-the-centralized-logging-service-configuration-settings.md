---
title: Управление централизованными параметрами конфигурации службы ведения журналов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce13f34a5a48c80c1f825e225a20c96ebfa2db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Управление централизованными параметрами конфигурации службы ведения журналов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Централизованная служба ведения журнала контролируется и настраивается с помощью параметров и параметров, создаваемых и используемых централизованным контроллером службы ведения журналов (Клсконтроллер), для отправки команд агенту службы ведения журнала для отдельного компьютера ( Клсажент). Агент обрабатывает отправляемые им команды и (в случае команды запуска) использует конфигурацию сценариев, поставщиков, размера журнала, длительности трассировки и флагов для начала сбора журналов трассировки в соответствии с предоставленными сведениями о конфигурации.

<div>


> [!IMPORTANT]
> Не все командлеты Windows PowerShell, указанные для централизованной службы ведения журналов, предназначены для использования с локальными развертываниями Lync Server 2013. Несмотря на то, что они работают, следующие командлеты не предназначены для работы с локальными развертываниями Lync Server 2013. 
> <UL>
> <LI>
> <P><STRONG>Командлеты ксклсрегион:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-ксклсрегион</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-ксклсрегион</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-Ксклсрегион</A>и Remove <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">-ксклсрегион</A>.</P>
> <LI>
> <P><STRONG>Командлеты ксклссеарчтерм:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-ксклссеарчтерм</A> и <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-ксклссеарчтерм</A>.</P>
> <LI>
> <P><STRONG>Командлеты ксклссекуритиграуп:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-ксклссекуритиграуп</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-ксклссекуритиграуп</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-Ксклссекуритиграуп</A>и Remove <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">-ксклссекуритиграуп</A>.</P></LI></UL>Параметры, определенные в этих командлетах, не мешают или не вызывают какое-либо неотрицательное поведение, но они предназначены для работы с Microsoft Office 365 и не будут давать ожидаемые результаты в локальных развертываниях. Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.



</div>

<div>

## <a name="in-this-section"></a>Содержание

В темах этого раздела определяются параметры конфигурации, параметры и параметры для централизованной службы ведения журналов. Сведения о настройке централизованной службы ведения журналов, о том, как извлекать параметры конфигурации, создавать сценарии, управлять группами безопасности для централизованной службы ведения журнала, поиска и других сведений, которые содержатся в указанных ниже разделах.

  - [Управление конфигурацией службы ведения журналов на компьютере, сайте и глобальном централизованном хранилище в Lync Server 2013](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Настройка поставщиков для централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Настройка сценариев для централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Общие сведения об централизованной службе ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Командлеты централизованного ведения журналов в Lync Server 2013](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

