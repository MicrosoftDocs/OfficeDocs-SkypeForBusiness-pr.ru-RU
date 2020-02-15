---
title: 'Lync Server 2013: рекомендации по контролю допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c00dbaa2f47d34f06424c9013a5b691caab56499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="d4e91-102">Рекомендации по контролю допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4e91-102">Best practices for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4e91-103">_**Последнее изменение темы:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="d4e91-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="d4e91-104">Чтобы улучшить производительность и упростить развертывание, руководствуйтесь следующими рекомендациями при развертывании контроля допуска звонков:</span><span class="sxs-lookup"><span data-stu-id="d4e91-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="d4e91-105">Убедитесь, что глобальные сети соответствующим образом подготовлены для текущего и прогнозируемого трафика мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d4e91-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4e91-p101">Мы рекомендуем учесть в ограничениях пропускной способности буфер. Существуют сценарии, такие как состояние гонки, которые затрагивают общую пропускную способность и могут привести к превышению предела пропускной способности. Например, при попытке запуска двух звонков в условиях приближения к пределу пропускной способности один из них может быть отклонен, так как другому удалось запуститься первым.</span><span class="sxs-lookup"><span data-stu-id="d4e91-p101">We recommend that you factor in a buffer to your bandwidth limits. There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded. For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="d4e91-109">Отслеживайте использование сети и записи регистрации вызовов, чтобы вы могли выбрать оптимальные параметры управления допуском звонков и обновлять их по мере изменения использования сети.</span><span class="sxs-lookup"><span data-stu-id="d4e91-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="d4e91-110">Используйте политики пропускной способности управления допуском звонков для настройки параметров качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="d4e91-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="d4e91-111">Если требуется перенаправлять заблокированные звонки в ТСОП, убедитесь в работоспособности и достаточной емкости этой телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="d4e91-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="d4e91-112">Дополнительные сведения см. [в статье Планирование маршрутизации исходящих голосовых вызовов в Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="d4e91-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4e91-113">Под емкостью понимается количество портов, которые требуется открыть для обеспечения поддержки потенциального объема перенаправлений в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="d4e91-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

