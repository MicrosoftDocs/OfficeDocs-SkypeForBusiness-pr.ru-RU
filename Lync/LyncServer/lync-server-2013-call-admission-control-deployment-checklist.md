---
title: 'Lync Server 2013: контрольный список развертывания управления допуском звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e768cdd11d92b3aab5ce849f91cc1a422f119407
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="b89db-102">Контрольный список развертывания управления допуском звонков для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b89db-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b89db-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b89db-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b89db-104">Используйте следующий контрольный список, чтобы убедиться, что вы выполнили все необходимые задачи по настройке для развертывания управления допуском вызовов (CAC).</span><span class="sxs-lookup"><span data-stu-id="b89db-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="b89db-105">Если один или несколько пограничных серверов развертываются, то каждый IP-адрес внешнего интерфейса должен быть добавлен в список подсетей в параметрах сетевой конфигурации с битовой маской 32.</span><span class="sxs-lookup"><span data-stu-id="b89db-105">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="b89db-106">Следует также связать эту подсеть (IP-адрес) с идентификатором сетевого сайта для географического расположения, где развернута пограничная служба A/V.</span><span class="sxs-lookup"><span data-stu-id="b89db-106">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b89db-107">Пограничные серверы не обязаны реализовывать CAC.</span><span class="sxs-lookup"><span data-stu-id="b89db-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="b89db-108">Убедитесь в том, что служба CAC включена либо с помощью панели управления Lync Server, либо путем запуска командлета, как указано в разделе [Включение функции управления допуском звонков в Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="b89db-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="b89db-109">Убедитесь в том, что контроль допуска звонков включен на всех центральных сайтах.</span><span class="sxs-lookup"><span data-stu-id="b89db-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="b89db-110">Это можно сделать с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="b89db-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="b89db-111">Если при публикации формируется предупреждение, *не* игнорируйте его.</span><span class="sxs-lookup"><span data-stu-id="b89db-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="b89db-112">Убедитесь в том, что параметры всех подсетей, управляемых в корпоративной сети, соответствуют конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="b89db-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="b89db-113">Кроме того, очень важно, чтобы каждая подсеть была связана с сетевым сайтом, как описано в разделах [Подключение подсети к сетевому сайту в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="b89db-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="b89db-114">Убедитесь, что подсеть или IP-адреса всех серверов переднего плана, устройств для обеспечения связи в филиалах, серверов аудио- и видеоконференций (если они размещаются в отдельном пуле) и серверов-посредников настроены в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="b89db-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

