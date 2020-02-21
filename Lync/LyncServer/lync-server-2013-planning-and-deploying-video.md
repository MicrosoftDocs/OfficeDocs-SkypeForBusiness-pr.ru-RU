---
title: 'Lync Server 2013: планирование и развертывание видео'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6cc926ecdf990c9d82c4a088a77611ad0fd5806
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="e3659-102">Планирование и развертывание видео в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3659-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3659-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e3659-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e3659-104">Lync Server 2013 содержит следующие новые функции видео:</span><span class="sxs-lookup"><span data-stu-id="e3659-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="e3659-105">**Видео**   в формате HD пользователи могут работать с разрешениями до полного High Definition (1920 x 1080) в двусторонних вызовах и многосторонних конференциях.</span><span class="sxs-lookup"><span data-stu-id="e3659-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="e3659-106">**Представление галереи в**   видеоконференциях, содержащих более двух пользователей, пользователи могут просматривать видео участников Конференции.</span><span class="sxs-lookup"><span data-stu-id="e3659-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="e3659-107">Если в конференции используется более пяти участников, в верхней строке отображается только видео о наиболее активных участниках, и отображается фотография для остальных участников.</span><span class="sxs-lookup"><span data-stu-id="e3659-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="e3659-108">**H. 264 видео**   видеокодек H. 264 теперь используется по умолчанию для кодирования видео на клиентах Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e3659-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="e3659-109">Видео H.264 поддерживает более широкий диапазон разрешений и частоты кадров, а также улучшает масштабируемость видео.</span><span class="sxs-lookup"><span data-stu-id="e3659-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e3659-110">Lync Server 2013 по-прежнему поддерживает кодек VC1 для взаимодействия с предыдущими версиями Lync.</span><span class="sxs-lookup"><span data-stu-id="e3659-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="e3659-111">Сведения и общие сведения о новом видеокоде можно найти в статье Джефф Счертз в блоге, "взаимодействие с видео в Lync 2013" по адресу <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span><span class="sxs-lookup"><span data-stu-id="e3659-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="e3659-112">В этом разделе описывается управление пропускной способностью для видео в Lync Server 2013 и Настройка функций видео.</span><span class="sxs-lookup"><span data-stu-id="e3659-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e3659-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="e3659-113">In This Section</span></span>

  - [<span data-ttu-id="e3659-114">Настройка пропускной способности видео в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3659-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="e3659-115">Настройка представления галереи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3659-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="e3659-116">Настройка примеров видеороликов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3659-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="e3659-117">Вопросы взаимодействия с видеоконференциями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3659-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

