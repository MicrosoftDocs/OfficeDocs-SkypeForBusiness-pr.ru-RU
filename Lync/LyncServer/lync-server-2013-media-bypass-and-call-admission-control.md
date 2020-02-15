---
title: 'Lync Server 2013: обход сервера мультимедиа и контроль допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0a2df9eee6ee9cf0ca387c9098623d574292a27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="2d596-102">Обход сервера мультимедиа и контроль допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d596-102">Media bypass and call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d596-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="2d596-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="2d596-p101">Обход сервера-посредника и контроль допуска звонков (CAC) взаимодействуют для управления полосой пропускания для мультимедиа данных звонков. Обход сервера-посредника обеспечивает поток мультимедиа по каналам с хорошей связью; CAC управляет трафиком на каналах с ограниченной пропускной полосой. Так как обход сервера-посредника и CAC являются взаимоисключающими, необходимо быть осторожным при планировании использования этих компонентов. Поддерживаются следующие комбинации.</span><span class="sxs-lookup"><span data-stu-id="2d596-p101">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media. Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints. Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other. The following combinations are supported:</span></span>

  - <span data-ttu-id="2d596-p102">CAC и обход сервера-посредника включены. Для обхода сервера-посредника должно быть задано значение **Использовать сведения об узлах и областях**. Эти сведения совпадают с данными, которые используются для CAC.</span><span class="sxs-lookup"><span data-stu-id="2d596-p102">CAC and Media Bypass are both enabled. Media Bypass must be set to **Use Site and Region Information**. This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="2d596-p103">Если включить CAC, вы не сможете выбрать параметр **Всегда обходить**, и наоборот, так как эти две конфигурации являются взаимоисключающими. Т. е. только одна из них будет применима к любому звонку через ТСОП. Во-первых, выполняется проверка, чтобы определить, применяется ли обход сервера-посредника к вызову. Если это так, CAC не используется. Это имеет смысл, так как если вызов имеет право на обход, он по определению использует подключение, где CAC не требуется. Если обход не может применяться к вызову (т. е. идентификаторы обхода клиента и шлюза не совпадают), к звонку применяется CAC.</span><span class="sxs-lookup"><span data-stu-id="2d596-p103">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive. That is, only one of the two will apply to any given PSTN call. First, a check is made to determine if media bypass applies to the call. If it does, then CAC is not used. This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed. If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="2d596-117">CAC не включен и для обхода сервера-посредника задано значение **Всегда обходить**.</span><span class="sxs-lookup"><span data-stu-id="2d596-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="2d596-118">В этой конфигурации как к клиентские так и магистральные подсети сопоставляются с одним-единственным идентификатором обхода, который вычисляется системой.</span><span class="sxs-lookup"><span data-stu-id="2d596-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="2d596-119">CAC не включен и для обхода сервера-посредника задано значение **Использовать сведения об узлах и областях**.</span><span class="sxs-lookup"><span data-stu-id="2d596-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="2d596-p104">Если указан параметр **Использовать сведения об узлах и областях**, определение необходимости обхода работает, в принципе, так же независимо от того, включен или нет CAC. Т. е. для любого звонка через ТСОП подсети клиента сопоставляются с определенным узлом, при этом извлекается идентификатор обхода для этой подсети. Аналогично подсеть шлюза сопоставляется с определенным узлом, при этом извлекается идентификатор обхода для этой подсети. Только если два идентификатора обхода идентичны, для этого звонка будет применяться обход. Если они не совпадают, обход не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="2d596-p104">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not. That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Only if the two bypass IDs are identical will bypass happen for the call. If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="2d596-p105">Даже если CAC отключен глобально, необходимо задать политику полосы пропускания для каждого узла и каждой связи, если вы хотите использовать конфигурацию узла и области для управления применением обхода. Фактическое значение ограничения пропускной полосу или ее модальность не имеет значения. Конечная цель состоит в том, чтобы система автоматически вычисляла разные идентификаторы обхода для связи с различными региональными стандартами с плохой связью. Определение ограничения полосы пропускания по определению означает, что связь не очень хорошая.</span><span class="sxs-lookup"><span data-stu-id="2d596-p105">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision. The actual value of the bandwidth constraint or its modality doesn’t matter. The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected. Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="2d596-129">CAC включен, а обход сервера-посредника не включен.</span><span class="sxs-lookup"><span data-stu-id="2d596-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="2d596-130">Эта конфигурация применима, только если все шлюзы и IP-УАТС подключены по нестабильным каналам или не соответствуют другим требованиям для обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="2d596-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="2d596-131">Дополнительные сведения о требованиях к обходу сервера мультимедиа можно найти [в статье технические требования для обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="2d596-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2d596-132">См. также</span><span class="sxs-lookup"><span data-stu-id="2d596-132">See Also</span></span>


[<span data-ttu-id="2d596-133">Обзор обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d596-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="2d596-134">Режимы обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d596-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="2d596-135">Технические требования для обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d596-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

