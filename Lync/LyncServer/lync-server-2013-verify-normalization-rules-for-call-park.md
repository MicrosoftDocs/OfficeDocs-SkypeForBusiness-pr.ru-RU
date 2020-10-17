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
# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Проверка правил нормализации для парковки вызовов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-11_

Орбиты парковки вызовов не должны быть нормализованы. Проверьте абонентские группы и убедитесь, что значения орбит не нормализованы. Если необходимо создать дополнительное правило нормализации, чтобы не допустить нормализации орбит, выполните процедуру в разделе [Create a абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md) , чтобы определить новое правило нормализации, чтобы **в соответствии с шаблоном** определялся диапазон орбиты, а **шаблон перевода** — **$1**. Например, если диапазон орбиты парковки вызовов равен 7000 – 7999, то **шаблону, который необходимо найти** , является **^ (7 \\ d {3} ) $** и **шаблоном перевода** является **$1**.

<div>


> [!IMPORTANT]  
> Убедитесь, что правило нормализации по умолчанию в абонентских группах не содержит <STRONG>^(\d*)</STRONG>. В противном случае правило нормализации приостановки вызовов никогда не будет выполняться.



</div>

<div>

## <a name="see-also"></a>См. также


[Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

