---
title: 'Lync Server 2013: изменение пограничного пула, связанного с пулом переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7ad6ee6e40edb76d4ef5d7d53524f89e44a2aee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>Изменение пограничного пула, связанного с пулом переднего плана в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Если пограничный пул отключается, однако интерфейсный пул все еще работает, необходимо указать для интерфейсного пула использование пограничного пула в другом сайте, пока не будет восстановлена работоспособность сбойного пограничного пула.

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>Изменение пограничного пула, связанного с интерфейсным пулом

1.  В построителе топологий перейдите к имени интерфейсного пула, который необходимо изменить.

2.  Щелкните правой кнопкой мыши соответствующий пул, а затем выберите **Изменить свойства**.

3.  В разделе **Связи** под надписью **Сопоставить пограничный пул (для компонентов мультимедиа)** используйте раскрывающееся поле для выбора пограничного пула, с которым следует сопоставить интерфейсный пул.

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

