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
ms.openlocfilehash: 118ed297998072edf721d0f6a254f2b66120d343
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a>Поддерживаемое выровненное размещение серверов для пограничных компонентов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-08_

Пограничная служба доступа, пограничная служба веб-конференций, пограничная служба аудио-и видеоданных и прокси-служба XMPP размещены на пограничных серверах. Следующие серверы предоставляют функции, необходимые для доступа внешних пользователей, и их следует развернуть как выделенные серверы:

  - пограничный сервер;

  - Директор (необязательно);

  - обратный прокси-сервер.

<div>


> [!IMPORTANT]  
> Обратный прокси-сервер не обязательно должен быть выделен для обслуживания только Lync Server 2013. Например, вы можете предоставить службы для публикации веб-служб Lync Server и одновременно предоставить опубликованный веб-сайт для другого веб-сайта, на котором не влияет Lync Server. Если у вас уже есть обратный прокси-сервер в сети периметра для поддержки других служб, его можно использовать для Lync Server 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

