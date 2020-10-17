---
title: 'Lync Server 2013: вопросы взаимодействия для видеоконференций'
description: 'Lync Server 2013: рекомендации по обеспечению взаимодействия для видеоконференций.'
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
ms.openlocfilehash: 89675954ea4c4f188f50aab8fb2cb49494bcc247
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543935"
---
# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="fe84a-103">Вопросы взаимодействия с видеоконференциями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe84a-103">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe84a-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fe84a-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fe84a-105">В этом разделе описывается взаимодействие с пользователем во время фазы сосуществования миграции при взаимодействии между устаревшими клиентами и пулом Lync Server 2013 или Lync Server 2013 и устаревшим пулом.</span><span class="sxs-lookup"><span data-stu-id="fe84a-105">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="fe84a-106">Пулы Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe84a-106">Lync Server 2013 Pools</span></span>

<span data-ttu-id="fe84a-107">Если устаревший клиент используется в пуле Lync Server 2013, пользователи сталкиваются со следующим поведением:</span><span class="sxs-lookup"><span data-stu-id="fe84a-107">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="fe84a-108">Для двусторонних звонков разрешение видео будет тем же, что и в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="fe84a-108">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="fe84a-p101">В случае с многопользовательскими конференциями разрешение видео и доступные функции видеоконференций будут теми же, что и в устаревшем пуле. Развернутый вид и высокое разрешение недоступны.</span><span class="sxs-lookup"><span data-stu-id="fe84a-p101">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool. Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="fe84a-111">Устаревшие пулы</span><span class="sxs-lookup"><span data-stu-id="fe84a-111">Legacy Pools</span></span>

<span data-ttu-id="fe84a-112">При использовании клиента Lync Server 2013 в устаревшем пуле пользователи будут испытывать следующее поведение:</span><span class="sxs-lookup"><span data-stu-id="fe84a-112">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="fe84a-113">Для двусторонних вызовов в Lync Server 2013 клиенты могут использовать новые функции следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fe84a-113">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="fe84a-114">H. 264 доступен, если оба участника используют клиенты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe84a-114">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="fe84a-115">Клиент Lync Server 2013 использует значение по умолчанию для параметра totalreceivevideobitratekb задано, так как устаревший сервер не отправляет эту информацию при подготовке по каналу.</span><span class="sxs-lookup"><span data-stu-id="fe84a-115">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="fe84a-116">В случае с многопользовательскими конференциями разрешение видео и доступные функции видеоконференций будут теми же, что и при использовании устаревшего клиента в устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="fe84a-116">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe84a-117">Если на устаревшем сервере размещается клиент Lync Server 2013, можно настроить пропускную способность видеоконференций так, чтобы все пользователи в пуле получали только видео с небольшим разрешением, но отправляли видео с высоким разрешением.</span><span class="sxs-lookup"><span data-stu-id="fe84a-117">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="fe84a-118">Например, можно присвоить параметру MaxVideoRateAllowed в конфигурации сервера-посредника значение CIF-250K, а параметру VideoBitRateKb в политике конференц-связи — значение 2000 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="fe84a-118">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="fe84a-119">В результате пользователи в пуле не смогут получать видео в высоком разрешении.</span><span class="sxs-lookup"><span data-stu-id="fe84a-119">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="fe84a-120">Так как Максвидеоратеалловед больше не используется для клиентов Lync Server 2013, он не может запретить клиентам Lync Server 2013 запрашивать видео с высоким разрешением.</span><span class="sxs-lookup"><span data-stu-id="fe84a-120">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="fe84a-121">Вместо этого задайте для параметра VideoBitRateKb в политике конференц-связи для всех пользователей в пуле то же значение, что и для параметра MaxVideoRateAllowed (то есть CIF для скорости 250 кбит/с, VGA для скорости 600 кбит/с или HD для скорости 1500 кбит/с).</span><span class="sxs-lookup"><span data-stu-id="fe84a-121">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

