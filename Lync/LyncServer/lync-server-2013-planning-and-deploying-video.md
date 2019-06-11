---
title: 'Lync Server 2013: планирование и развертывание видео'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feac758dcc8547128c9b3684bc74dd6b69599d5f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="eb0c8-102">Планирование и развертывание видео в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb0c8-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb0c8-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="eb0c8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="eb0c8-104">В Lync Server 2013 появились следующие новые функции видео:</span><span class="sxs-lookup"><span data-stu-id="eb0c8-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="eb0c8-105">**Пользователи HD видео**   могут столкнуться с разрешениями до полного высокого разрешения (HD) (1920 x 1080) во входящих звонках и многосторонних конференциях.</span><span class="sxs-lookup"><span data-stu-id="eb0c8-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="eb0c8-106">**Представление коллекции в**   видеоконференциях, имеющих более двух пользователей, пользователи могут просматривать видео участников Конференции.</span><span class="sxs-lookup"><span data-stu-id="eb0c8-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="eb0c8-107">Если на Конференции установлено более пяти участников собрания, в верхней строке отображаются только самые активные участники, а для других участников — фотография.</span><span class="sxs-lookup"><span data-stu-id="eb0c8-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="eb0c8-108">**H. 264 видео**   видеокодек H. 264 теперь используется по умолчанию для кодирования видео на клиентах Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="eb0c8-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="eb0c8-109">Видео H. 264 поддерживает широкий спектр разрешений и частот кадров, а затем повышает масштабируемость видео.</span><span class="sxs-lookup"><span data-stu-id="eb0c8-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb0c8-110">Lync Server 2013 по-прежнему поддерживает кодек VC1 для взаимодействия с предыдущими версиями Lync.</span><span class="sxs-lookup"><span data-stu-id="eb0c8-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="eb0c8-111">Сведения и общие сведения о новом видеокоде можно найти в статье Счертз в блоге об использовании видео в Lync 2013 <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span><span class="sxs-lookup"><span data-stu-id="eb0c8-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="eb0c8-112">В этом разделе рассказывается, как управлять пропускной способностью видео в Lync Server 2013 и настраивать возможности видео.</span><span class="sxs-lookup"><span data-stu-id="eb0c8-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eb0c8-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="eb0c8-113">In This Section</span></span>

  - [<span data-ttu-id="eb0c8-114">Настройка пропускной способности видео в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb0c8-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="eb0c8-115">Настройка представления коллекции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb0c8-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="eb0c8-116">Настройка примеров видеороликов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb0c8-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="eb0c8-117">Рекомендации по взаимодействию при видеоконференциях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb0c8-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

