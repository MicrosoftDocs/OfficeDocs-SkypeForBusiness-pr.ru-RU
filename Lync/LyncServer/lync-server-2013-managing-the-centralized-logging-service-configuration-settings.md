---
title: Управление централизованными параметрами конфигурации службы ведения журналов
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
ms.openlocfilehash: 4cb3b16210b3fac64c0c5bd7886849da7dd0d065
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="81644-102">Управление централизованными параметрами конфигурации службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81644-102">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81644-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="81644-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="81644-104">Централизованная служба ведения журнала контролируется и настраивается с помощью параметров и параметров, создаваемых и используемых централизованным контроллером службы ведения журналов (Клсконтроллер), для отправки команд агенту службы ведения журнала для отдельного компьютера ( Клсажент).</span><span class="sxs-lookup"><span data-stu-id="81644-104">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="81644-105">Агент обрабатывает отправляемые им команды и (в случае команды запуска) использует конфигурацию сценариев, поставщиков, размера журнала, длительности трассировки и флагов для начала сбора журналов трассировки в соответствии с предоставленными сведениями о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="81644-105">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="81644-106">Не все командлеты Windows PowerShell, указанные для централизованной службы ведения журналов, предназначены для использования с локальными развертываниями Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81644-106">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="81644-107">Несмотря на то, что они работают, следующие командлеты не предназначены для работы с локальными развертываниями Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81644-107">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="81644-108"><STRONG>Командлеты ксклсрегион:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-ксклсрегион</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-ксклсрегион</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-ксклсрегион</A>и <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-ксклсрегион</A>.</span><span class="sxs-lookup"><span data-stu-id="81644-108"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="81644-109"><STRONG>Командлеты ксклссеарчтерм:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-ксклссеарчтерм</A> и <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-ксклссеарчтерм</A>.</span><span class="sxs-lookup"><span data-stu-id="81644-109"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="81644-110"><STRONG>Командлеты ксклссекуритиграуп:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-ксклссекуритиграуп</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-ксклссекуритиграуп</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-ксклссекуритиграуп</A>и <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-ксклссекуритиграуп</A>.</span><span class="sxs-lookup"><span data-stu-id="81644-110"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="81644-111">Параметры, определенные в этих командлетах, не мешают или не вызывают какое-либо неотрицательное поведение, но они предназначены для работы с Microsoft Office 365 и не будут давать ожидаемые результаты в локальных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="81644-111">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="81644-112">Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.</span><span class="sxs-lookup"><span data-stu-id="81644-112">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="81644-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="81644-113">In This Section</span></span>

<span data-ttu-id="81644-114">В темах этого раздела определяются параметры конфигурации, параметры и параметры для централизованной службы ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="81644-114">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="81644-115">Сведения о настройке централизованной службы ведения журналов, о том, как извлекать параметры конфигурации, создавать сценарии, управлять группами безопасности для централизованной службы ведения журнала, поиска и других сведений, которые содержатся в указанных ниже разделах.</span><span class="sxs-lookup"><span data-stu-id="81644-115">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="81644-116">Управление конфигурацией службы ведения журналов на компьютере, сайте и глобальном централизованном хранилище в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81644-116">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="81644-117">Настройка поставщиков для централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81644-117">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="81644-118">Настройка сценариев для централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81644-118">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81644-119">См. также</span><span class="sxs-lookup"><span data-stu-id="81644-119">See Also</span></span>


[<span data-ttu-id="81644-120">Общие сведения об централизованной службе ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81644-120">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="81644-121">Командлеты централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81644-121">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

