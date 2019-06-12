---
title: 'Lync Server 2013: Проверка правил нормализации для приостановки звонка'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114c7e035d96217f8cf41e88a87ccfd490fe5754
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Проверка правил нормализации для парковки звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-11_

Орбиты для приостановки звонка не должны быть нормализованы. Check your dial plans to be sure that your orbit numbers are not normalized. Если необходимо создать дополнительное правило нормализации, чтобы не допустить нормализации, выполните действия, описанные в разделе [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md) , чтобы определить новое правило нормализации, чтобы **шаблон соответствовал** диапазону на орбите. и **шаблоном перевода** является **$1**. Например, если диапазон на повороте на поворот по орбите равен 7000 – 7999, **шаблон соответствует** **^ (7\\d{3}) $** , а **шаблон перевода** — **$1**.

<div>


> [!IMPORTANT]  
> Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d*)</STRONG>. В противном случае правило нормализации для приостановки вызова никогда не будет выполняться.



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

