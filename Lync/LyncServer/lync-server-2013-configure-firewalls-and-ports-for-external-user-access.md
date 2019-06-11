---
title: 'Lync Server 2013: настройка брандмауэров и портов для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 142488d35c3d5afa988be11baa688849065df066
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="cbc1d-102">Настройка брандмауэров и портов для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbc1d-102">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbc1d-103">_**Тема последнего изменения:** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="cbc1d-103">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="cbc1d-104">Чтобы настроить брандмауэры и порты, необходимо настроить их для пограничных серверов, обратного прокси-сервера и подсистемы балансировки нагрузки для оборудования (для масштабируемого развертывания без использования балансировки нагрузки DNS).</span><span class="sxs-lookup"><span data-stu-id="cbc1d-104">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="cbc1d-105">В этом разделе приводятся сведения о требованиях к брандмауэру и порту для всех компонентов пограничного сервера и конфигурации портов брандмауэра для пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="cbc1d-105">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="cbc1d-106">Дополнительные сведения о настройке портов для обратного прокси-сервера приведены в разделе [Настройка обратного прокси-сервера для Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span><span class="sxs-lookup"><span data-stu-id="cbc1d-106">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="cbc1d-107">Если вы разворачиваете топологию с масштабированием и используете аппаратную балансировку нагрузки вместо балансировки нагрузки DNS, ознакомьтесь [с масштабируемым консолидированным краем с аппаратным балансировщикм нагрузки на Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) в документации по планированию, чтобы получить подробные сведения о настройке. порты для подсистем аппаратной балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="cbc1d-107">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="cbc1d-108">См. также</span><span class="sxs-lookup"><span data-stu-id="cbc1d-108">See Also</span></span>


[<span data-ttu-id="cbc1d-109">Определение требований к внешнему брандмауэру аудио- и видеосвязи и портам для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbc1d-109">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

