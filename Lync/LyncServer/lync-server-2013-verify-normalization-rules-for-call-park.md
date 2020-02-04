---
title: 'Lync Server 2013: Проверка правил нормализации для приостановки звонка'
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
ms.openlocfilehash: 2041b807ad16f1e91a83da39739d0ea058a5fba5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765580"
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

Орбиты для приостановки звонка не должны быть нормализованы. Check your dial plans to be sure that your orbit numbers are not normalized. Если необходимо создать дополнительное правило нормализации, чтобы не допустить нормализации, выполните действия, описанные в разделе [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md) , чтобы определить новое правило нормализации, чтобы **шаблон соответствовал** диапазону орбиты, а **шаблон перевода** — **$1**. Например, если диапазон на повороте на поворот по орбите равен 7000 – 7999, **шаблон соответствует** **^ (7\\d{3}) $** , а **шаблон перевода** — **$1**.

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

