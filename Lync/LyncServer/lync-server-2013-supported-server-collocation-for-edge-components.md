---
title: 'Lync Server 2013: поддерживаемое выровненное размещение серверов для пограничных компонентов'
description: 'Lync Server 2013: поддерживаемое выровненное размещение серверов для пограничных компонентов.'
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
ms.openlocfilehash: 7bf253e5210e077ca62b3d00f7f130d54d8392a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556365"
---
# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="94bf5-103">Поддерживаемое выровненное размещение серверов для пограничных компонентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94bf5-103">Supported server collocation for edge components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94bf5-104">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="94bf5-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="94bf5-105">Пограничная служба доступа, пограничная служба веб-конференций, пограничная служба аудио-и видеоданных и прокси-служба XMPP размещены на пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="94bf5-105">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="94bf5-106">Следующие серверы предоставляют функции, необходимые для доступа внешних пользователей, и их следует развернуть как выделенные серверы:</span><span class="sxs-lookup"><span data-stu-id="94bf5-106">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="94bf5-107">пограничный сервер;</span><span class="sxs-lookup"><span data-stu-id="94bf5-107">Edge Server</span></span>

  - <span data-ttu-id="94bf5-108">Директор (необязательно);</span><span class="sxs-lookup"><span data-stu-id="94bf5-108">Director (Optional)</span></span>

  - <span data-ttu-id="94bf5-109">обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="94bf5-109">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="94bf5-110">Обратный прокси-сервер не обязательно должен быть выделен для обслуживания только Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94bf5-110">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="94bf5-111">Например, вы можете предоставить службы для публикации веб-служб Lync Server и одновременно предоставить опубликованный веб-сайт для другого веб-сайта, на котором не влияет Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94bf5-111">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="94bf5-112">Если у вас уже есть обратный прокси-сервер в сети периметра для поддержки других служб, его можно использовать для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94bf5-112">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

