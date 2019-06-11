---
title: 'Lync Server 2013: изменение пограничного пула, связанного с пулом переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>Изменение пограничного пула, связанного с пулом переднего плана в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Если пул пограничного пула отключается, но пул переднего плана на этом же сайте по-прежнему работает, вы должны настроить интерфейс пула на использование пограничного пула на другом сайте, пока не произойдет восстановление пула Edge.

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>Изменение пула EDGE, связанного с пулом переднего плана

1.  В построителе топологии найдите имя пула переднего плана, который нужно изменить.

2.  Щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.

3.  В разделе **связи** в группе **сопоставление краевого пула (для компонентов мультимедиа)** выберите в раскрывающемся списке пул краев, который вы хотите связать с этим пулом переднего плана.

4.  Нажмите кнопку **ОК**.

</div>

<div>

## <a name="see-also"></a>См. также


[Аварийное восстановление пограничного сервера в Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

