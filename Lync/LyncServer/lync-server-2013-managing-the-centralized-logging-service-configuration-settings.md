---
title: Управление параметрами конфигурации централизованной службы ведения журналов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b89923932b06e07ed01049895e34c960938cc88
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Управление параметрами конфигурации централизованной службы ведения журналов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Централизованная служба ведения журналов контролируется и настраивается параметрами и параметрами, которые создаются и используются централизованным контроллером службы ведения журналов (CLSController) для отправки команд агенту службы ведения журнала в отдельном компьютере ( CLSAgent). Этот агент обрабатывает отправляемые ему команды и (в случае получения команды Start) использует конфигурацию сценариев, поставщики, размер журнала, длительность трассировки и флаги для начала сбора данных для журналов трассировки в соответствии с предоставленной информации о конфигурации.

<div>


> [!IMPORTANT]
> Не все командлеты Windows PowerShell, перечисленные для централизованной службы ведения журналов, предназначены для использования с локальными развертываниями Lync Server 2013. Несмотря на то, что они могут показаться работоспособными, следующие командлеты не предназначены для работы с локальными развертываниями Lync Server 2013. 
> <UL>
> <LI>
> <P><STRONG>Командлеты CsClsRegion:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A> и <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</P>
> <LI>
> <P><STRONG>Командлеты CsClsSearchTerm:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> и <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</P>
> <LI>
> <P><STRONG>Командлеты CsClsSecurityGroup:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A> и <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</P></LI></UL>Параметры, определенные в этих командлетах, не мешают или не вызывают каких – либо неблагоприятных поведений, но они предназначены для использования с Microsoft Office 365 и не будут давать ожидаемые результаты в локальных развертываниях. Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.



</div>

<div>

## <a name="in-this-section"></a>Содержание

В подразделах этого раздела определяются параметры конфигурации, параметры и параметры централизованной службы ведения журналов. Сведения о настройке централизованной службы ведения журналов, способах получения параметров конфигурации, создании сценариев, управлении группами безопасности для централизованной службы ведения журналов, поиска и многого другого, содержатся в следующих разделах.

  - [Управление конфигурацией компьютера, сайта и глобальной централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Настройка поставщиков для централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Настройка сценариев для централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Обзор централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Командлеты централизованного ведения журналов в Lync Server 2013](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

