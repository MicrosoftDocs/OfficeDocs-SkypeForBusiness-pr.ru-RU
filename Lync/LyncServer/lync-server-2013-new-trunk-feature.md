---
title: 'Lync Server 2013: новая функция магистрали'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18296a9d1da060c9faaf8d4c765c38403a9cb224
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="32a86-102">Новая функция магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32a86-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32a86-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="32a86-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="32a86-104">В Microsoft Lync Server 2013 можно определять несколько каналов связи между сервером-посредником и шлюзом.</span><span class="sxs-lookup"><span data-stu-id="32a86-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="32a86-105">Microsoft Lync Server 2010 разрешен только для одной магистрали между сервером-посредником и шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="32a86-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="32a86-106">Эта функция обеспечивает гибкие возможности для определения дополнительных каналов.</span><span class="sxs-lookup"><span data-stu-id="32a86-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="32a86-107">Магистраль — это логическая связь между полным доменным именем сервера-посредником и портом прослушивания и прослушиваемым портом шлюза PSTN.</span><span class="sxs-lookup"><span data-stu-id="32a86-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="32a86-108">Благодаря этой новой возможности вы можете легко определять устойчивость (в которой несколько серверов-источников можно использовать для направления звонков на один шлюз PSTN) для обеспечения взаимодействия УАТС, где можно использовать несколько каналов связи с различными связанными политиками. IP-УАТС и сервер-посредник, а также для конфигураций магистральных каналов SIP, где серверы исправлений на разных сайтах имеют магистральные магистрали SIP на перевозчике, на который ссылается то же полное доменное имя несущей частоты.</span><span class="sxs-lookup"><span data-stu-id="32a86-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="32a86-109">См. также</span><span class="sxs-lookup"><span data-stu-id="32a86-109">See Also</span></span>


[<span data-ttu-id="32a86-110">Новые возможности корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32a86-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

