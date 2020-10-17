---
title: 'Lync Server 2013: вопросы взаимодействия для видеоконференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f71977dc1909fa6993bc21f7944e821276dd86d6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498396"
---
# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Вопросы взаимодействия с видеоконференциями в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

В этом разделе описывается взаимодействие с пользователем во время фазы сосуществования миграции при взаимодействии между устаревшими клиентами и пулом Lync Server 2013 или Lync Server 2013 и устаревшим пулом.

<div>

## <a name="lync-server-2013-pools"></a>Пулы Lync Server 2013

Если устаревший клиент используется в пуле Lync Server 2013, пользователи сталкиваются со следующим поведением:

  - Для двусторонних звонков разрешение видео будет тем же, что и в устаревшем пуле.

  - В случае с многопользовательскими конференциями разрешение видео и доступные функции видеоконференций будут теми же, что и в устаревшем пуле. Развернутый вид и высокое разрешение недоступны.

</div>

<div>

## <a name="legacy-pools"></a>Устаревшие пулы

При использовании клиента Lync Server 2013 в устаревшем пуле пользователи будут испытывать следующее поведение:

  - Для двусторонних вызовов в Lync Server 2013 клиенты могут использовать новые функции следующим образом:
    
      - H. 264 доступен, если оба участника используют клиенты Lync Server 2013.
    
      - Клиент Lync Server 2013 использует значение по умолчанию для параметра totalreceivevideobitratekb задано, так как устаревший сервер не отправляет эту информацию при подготовке по каналу.

  - В случае с многопользовательскими конференциями разрешение видео и доступные функции видеоконференций будут теми же, что и при использовании устаревшего клиента в устаревшем пуле.

<div>


> [!NOTE]  
> Если на устаревшем сервере размещается клиент Lync Server 2013, можно настроить пропускную способность видеоконференций так, чтобы все пользователи в пуле получали только видео с небольшим разрешением, но отправляли видео с высоким разрешением. Например, можно присвоить параметру MaxVideoRateAllowed в конфигурации сервера-посредника значение CIF-250K, а параметру VideoBitRateKb в политике конференц-связи — значение 2000 кбит/с. В результате пользователи в пуле не смогут получать видео в высоком разрешении.<BR>Так как Максвидеоратеалловед больше не используется для клиентов Lync Server 2013, он не может запретить клиентам Lync Server 2013 запрашивать видео с высоким разрешением. Вместо этого задайте для параметра VideoBitRateKb в политике конференц-связи для всех пользователей в пуле то же значение, что и для параметра MaxVideoRateAllowed (то есть CIF для скорости 250 кбит/с, VGA для скорости 600 кбит/с или HD для скорости 1500 кбит/с).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

