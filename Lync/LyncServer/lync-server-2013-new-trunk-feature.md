---
title: 'Lync Server 2013: новая функция магистрали'
description: 'Lync Server 2013: новая функция магистрали.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8f923ceada899608cc350bd1343345c12d0996b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541945"
---
# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="17b34-103">Новая функция магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17b34-103">New trunk feature in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17b34-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="17b34-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="17b34-105">В Microsoft Lync Server 2013 можно определить несколько магистральных каналов между сервером-посредником и шлюзом.</span><span class="sxs-lookup"><span data-stu-id="17b34-105">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="17b34-106">Microsoft Lync Server 2010 разрешен только для одного канала связи между сервером-посредником и шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="17b34-106">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="17b34-107">Эта возможность увеличивает гибкость за счет определения дополнительных магистралей.</span><span class="sxs-lookup"><span data-stu-id="17b34-107">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="17b34-108">Магистраль — это логическая связь между полным доменным именем сервера-посредника и слушающим портом и полным доменным именем шлюза PSTN и слушающим портом.</span><span class="sxs-lookup"><span data-stu-id="17b34-108">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="17b34-109">Эта новая возможность позволяет легко задать устойчивость для устойчивости (где несколько серверов-посредников можно использовать для маршрутизации вызовов на один шлюз PSTN). для взаимодействия УАТС, где несколько магистральных линий с разными связанными политиками могут использоваться между IP-УАТС и сервером-посредником, а также для конфигураций магистральной сети SIP, в которых серверы-посредники на разных сайтах имеют магистральные магистрали SIP на перевозчике, на который ссылается такое же полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="17b34-109">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="17b34-110">См. также</span><span class="sxs-lookup"><span data-stu-id="17b34-110">See Also</span></span>


[<span data-ttu-id="17b34-111">Новые функции корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17b34-111">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

