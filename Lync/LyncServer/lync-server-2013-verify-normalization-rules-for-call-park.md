---
title: 'Lync Server 2013: Проверка правил нормализации для парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 627832870de3a8306912d07134bb92caeee3076e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518626"
---
# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="9c543-102">Проверка правил нормализации для парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c543-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c543-103">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="9c543-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="9c543-104">Орбиты парковки вызовов не должны быть нормализованы.</span><span class="sxs-lookup"><span data-stu-id="9c543-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="9c543-105">Проверьте абонентские группы и убедитесь, что значения орбит не нормализованы.</span><span class="sxs-lookup"><span data-stu-id="9c543-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="9c543-106">Если необходимо создать дополнительное правило нормализации, чтобы не допустить нормализации орбит, выполните процедуру в разделе [Create a абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md) , чтобы определить новое правило нормализации, чтобы **в соответствии с шаблоном** определялся диапазон орбиты, а **шаблон перевода** — **$1**.</span><span class="sxs-lookup"><span data-stu-id="9c543-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="9c543-107">Например, если диапазон орбиты парковки вызовов равен 7000 – 7999, то **шаблону, который необходимо найти** , является **^ (7 \\ d {3} ) $** и **шаблоном перевода** является **$1**.</span><span class="sxs-lookup"><span data-stu-id="9c543-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9c543-108">Убедитесь, что правило нормализации по умолчанию в абонентских группах не содержит <STRONG>^(\d\*)</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9c543-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="9c543-109">В противном случае правило нормализации приостановки вызовов никогда не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="9c543-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c543-110">См. также</span><span class="sxs-lookup"><span data-stu-id="9c543-110">See Also</span></span>


[<span data-ttu-id="9c543-111">Создание абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c543-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

