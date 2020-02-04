---
title: 'Lync Server 2013: поддерживаемое выровненное размещение серверов для пограничных компонентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc12e442be98ba1fd962634460200ce749aca3d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a>Поддерживаемое выровненное размещение серверов для пограничных компонентов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-08_

Служба пограничного доступа, служба Edge для веб-конференций, служба EDGE и служба КСМПП proxy размещаются на пограничных серверах. Следующие серверы предоставляют функции, необходимые для доступа внешних пользователей, и должны развертываться как выделенные серверы:

  - Пограничный сервер

  - Режиссер (необязательно)

  - Сертификат обратного прокси-сервера

<div>


> [!IMPORTANT]  
> Обратный прокси-сервер не требуется специально для обслуживания только сервера Lync Server 2013. Например, вы можете предоставить услуги для публикации веб-служб Lync Server и одновременно предоставить опубликованный веб-сайт для другого веб-сайта, на котором не установлено Lync Server. Если у вас уже есть обратный прокси-сервер в демилитаризованной зоне для поддержки других служб, вы можете использовать его для Lync Server 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

