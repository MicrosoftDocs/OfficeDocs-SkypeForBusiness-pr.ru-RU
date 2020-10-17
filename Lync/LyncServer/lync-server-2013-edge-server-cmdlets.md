---
title: 'Lync Server 2013: командлеты пограничного сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server cmdlets
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415635(v=OCS.15)
ms:contentKeyID: 48183534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8af979b36564fef40a4839e31f2597d82117741
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533386"
---
# <a name="edge-server-cmdlets-in-lync-server-2013"></a>Командлеты пограничного сервера в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-10-07_

Пограничные серверы предоставляют способ расширения возможностей Microsoft Lync Server 2013 для пользователей, которые не вошли во внутреннюю сеть. Например, если у вас есть удаленные пользователи с проверкой подлинности с проверкой подлинности, которые входят в Lync Server 2013 через Интернет, а не через внутреннюю сеть, вам потребуется настроить пограничный сервер, на котором работает пограничная служба доступа Lync Server. Кроме того, пограничные серверы необходимы, если вы хотите установить Федерацию с другой организацией или вы хотите предоставить пользователям право на взаимодействие с пользователями, у которых есть учетные записи с общедоступными службами обмена мгновенными сообщениями, такими как Yahoo \! , AOL или MSN.

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров. Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo! Messenger до даты завершения работы службы. Дата окончания срока жизни 2014 для AOL и Yahoo! объявлено. Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</P>
> <LI>
> <P>УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo! Messenger. Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</P>
> <LI>
> <P>Lync — это мощное средство для связи между организациями и пользователями мира. Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL. В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a>Командлеты пограничных серверов

Ниже приведен список командлетов, которые относятся непосредственно к управлению пограничными серверами:

**Пограничный сервер**

  - <span></span>  
    [Get — CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))

  - <span></span>  
    [Set — CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))

  - <span></span>  
    [New — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))

  - <span></span>  
    [Remove — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))

  - <span></span>  
    [Set — CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set — Кседжесервер](https://technet.microsoft.com/library/Gg398859(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>См. также


[Блог Lync Server PowerShell](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

