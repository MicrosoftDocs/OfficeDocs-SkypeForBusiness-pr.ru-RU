---
title: 'Lync Server 2013: Настройка брандмауэров и портов для доступа внешних пользователей'
description: 'Lync Server 2013: Настройка брандмауэров и портов для доступа внешних пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68ccb382c3b3632b113b2b0a36846500700c1b9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553275"
---
# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="ee5d3-103">Настройка брандмауэров и портов для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee5d3-103">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee5d3-104">_**Последнее изменение темы:** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="ee5d3-104">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="ee5d3-105">Для настройки брандмауэров или портов необходимо настроить их для пограничных серверов, обратных прокси-серверов и аппаратных средств балансировки нагрузки (для масштабированного развертывания, не использующего балансировку нагрузки DNS).</span><span class="sxs-lookup"><span data-stu-id="ee5d3-105">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="ee5d3-106">В этом разделе представлены сведения о требвоаниях к брандмауэру и портам для всех компонентов пограничных серверов и конфигурации портов брандмауэра для пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-106">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="ee5d3-107">Дополнительные сведения о настройке портов для обратных прокси-серверов приведены в статье [Настройка обратных прокси-серверов для Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span><span class="sxs-lookup"><span data-stu-id="ee5d3-107">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="ee5d3-108">При развертывании масштабируемой пограничной топологии, а также при использовании аппаратной балансировки нагрузки вместо балансировки нагрузки DNS, ознакомьтесь [с масштабируемым консолидированным краем с аппаратными подсистемами балансировки нагрузки в Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) в документации по планированию для получения сведений о настройке портов для аппаратных подсистем балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="ee5d3-108">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ee5d3-109">См. также</span><span class="sxs-lookup"><span data-stu-id="ee5d3-109">See Also</span></span>


[<span data-ttu-id="ee5d3-110">Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee5d3-110">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

