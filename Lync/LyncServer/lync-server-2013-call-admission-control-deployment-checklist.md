---
title: 'Lync Server 2013: контрольный список развертывания контроля допуска звонков'
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
ms.openlocfilehash: 1a8dc32eb017baf832128301b9639aefe23ae4ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="f5ae9-102">Контрольный список развертывания контроля допуска звонков для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5ae9-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5ae9-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f5ae9-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f5ae9-104">Используйте следующий контрольный список, чтобы убедиться в выполнении всех необходимых задач конфигурации для развертывания контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="f5ae9-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="f5ae9-p101">Если развернут один или несколько пограничных серверов, IP-адреса внешних интерфейсов необходимо добавить в список подсетей в параметрах конфигурации с битовой маской 32. Кроме того, необходимо связать эту подсеть (IP-адрес) с ИД сетевого узла для географического расположения, где развернута пограничная служба A/V.</span><span class="sxs-lookup"><span data-stu-id="f5ae9-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5ae9-107">Пограничные серверы не являются обязательным требованием для развертывания контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="f5ae9-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="f5ae9-108">Убедитесь, что служба контроля допуска звонков включена либо с помощью панели управления Lync Server, либо с помощью командлета, указанного в разделе [Включение контроля допуска звонков в Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="f5ae9-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="f5ae9-109">Убедитесь, что контроль допуска звонков включен на всех центральных сайтах.</span><span class="sxs-lookup"><span data-stu-id="f5ae9-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="f5ae9-110">Это можно сделать с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="f5ae9-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="f5ae9-111">Если при публикации создается предупреждение, *не* игнорируйте его.</span><span class="sxs-lookup"><span data-stu-id="f5ae9-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="f5ae9-112">Убедитесь, что все подсети, управляемые в корпоративной сети, настроены в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="f5ae9-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="f5ae9-113">Кроме того, важно, чтобы каждая подсеть была связана с сетевым сайтом, как описано в [привязку подсети к сетевому сайту в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="f5ae9-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="f5ae9-114">Убедитесь, что подсеть или IP-адреса всех серверов переднего плана, устройств для обеспечения связи в филиалах, серверов аудио- и видеоконференций (если они размещаются в отдельном пуле) и серверов-посредников настроены в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="f5ae9-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

