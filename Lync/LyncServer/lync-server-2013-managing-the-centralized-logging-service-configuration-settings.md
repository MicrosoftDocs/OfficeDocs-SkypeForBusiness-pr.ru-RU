---
title: Управление параметрами конфигурации централизованной службы ведения журналов
description: Управление параметрами конфигурации централизованной службы ведения журналов.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e25294e096b8368aa06a11e4ad851fe5d1a84c0f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572605"
---
# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="88018-103">Управление параметрами конфигурации централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88018-103">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88018-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="88018-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="88018-105">Централизованная служба ведения журналов контролируется и настраивается параметрами и параметрами, которые создаются и используются централизованным контроллером службы ведения журналов (CLSController) для отправки команд в агент службы централизованного ведения журналов (CLSAgent) отдельного компьютера.</span><span class="sxs-lookup"><span data-stu-id="88018-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="88018-106">Этот агент обрабатывает отправляемые ему команды и (в случае получения команды Start) использует конфигурацию сценариев, поставщики, размер журнала, длительность трассировки и флаги для начала сбора данных для журналов трассировки в соответствии с предоставленной информации о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="88018-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="88018-107">Не все командлеты Windows PowerShell, перечисленные для централизованной службы ведения журналов, предназначены для использования с локальными развертываниями Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88018-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="88018-108">Несмотря на то, что они могут показаться работоспособными, следующие командлеты не предназначены для работы с локальными развертываниями Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88018-108">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="88018-109"><STRONG>Командлеты CsClsRegion:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A> и <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span><span class="sxs-lookup"><span data-stu-id="88018-109"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="88018-110"><STRONG>Командлеты CsClsSearchTerm:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> и <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span><span class="sxs-lookup"><span data-stu-id="88018-110"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="88018-111"><STRONG>Командлеты CsClsSecurityGroup:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A> и <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span><span class="sxs-lookup"><span data-stu-id="88018-111"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="88018-112">Параметры, определенные в этих командлетах, не мешают или не вызывают каких – либо неблагоприятных поведений, но они предназначены для использования в Microsoft 365 и не будут давать ожидаемые результаты в локальных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="88018-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="88018-113">Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.</span><span class="sxs-lookup"><span data-stu-id="88018-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="88018-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="88018-114">In This Section</span></span>

<span data-ttu-id="88018-115">В подразделах этого раздела определяются параметры конфигурации, параметры и параметры централизованной службы ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="88018-115">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="88018-116">Сведения о настройке централизованной службы ведения журналов, способах получения параметров конфигурации, создании сценариев, управлении группами безопасности для централизованной службы ведения журналов, поиска и многого другого, содержатся в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="88018-116">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="88018-117">Управление конфигурацией компьютера, сайта и глобальной централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88018-117">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="88018-118">Настройка поставщиков для централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88018-118">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="88018-119">Настройка сценариев для централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88018-119">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88018-120">См. также</span><span class="sxs-lookup"><span data-stu-id="88018-120">See Also</span></span>


[<span data-ttu-id="88018-121">Обзор централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88018-121">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="88018-122">Командлеты централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88018-122">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

