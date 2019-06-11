---
title: 'Lync Server 2013: Настройка пропускной способности видео'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ee374be85bc9427135ff89f3eb75acefd1cf5a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="9e6f5-102">Настройка пропускной способности видео в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e6f5-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e6f5-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9e6f5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9e6f5-104">Lync Server 2013 содержит несколько параметров для управления видеосвязью с участием двух сторон и многосторонних конференций.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="9e6f5-105">При развертывании Lync Server 2013 необходимо оценить, подходят ли для вашей организации параметры по умолчанию, и при необходимости изменить их.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="9e6f5-106">Параметры, описанные в этом разделе, относятся к обоим звонкам и конференц-связи с несколькими участниками.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-106">The parameters described in this section apply to both two-party calls and multiparty conferencing.</span></span> <span data-ttu-id="9e6f5-107">Чтобы просмотреть или изменить эти параметры, воспользуйтесь одним из следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="9e6f5-107">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="9e6f5-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="9e6f5-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="9e6f5-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="9e6f5-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="9e6f5-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="9e6f5-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="9e6f5-111">Убедитесь в том, что в политике конференц-связи указаны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="9e6f5-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="9e6f5-112">**Видеобитратекб**   этот параметр определяет максимальную скорость видеосвязи в килобитах в секунду (кбит/с), используемую для видео, отправленных пользователем.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="9e6f5-113">Значение по умолчанию — 50000 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="9e6f5-114">Допустимые значения: от 0 до 50000.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="9e6f5-115">Этот параметр действует отдельно для основного видео и панорамного видео.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="9e6f5-116">Пример: Если вы укажете 2000 кбит/с, то сервер Lync Server сможет отправлять 2000 кбит/с для основного видеопотока и 2000 кбит/с для видеопотока панорамного видео.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e6f5-117">Максимальная пропускная способность сетевого видео для конечной точки Lync 2013 составляет 8000 кбит/с для основного видео и 2500 кбит/с для панорамного видео.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="9e6f5-118">Эти максимальные значения достигаются только при получении или отправке нескольких видеороликов.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="9e6f5-119">Дополнительные сведения можно найти в разделе "использование сетевого трафика мультимедиа" в <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">требованиях к пропускной способности сети для мультимедийного трафика в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="9e6f5-120">В этом разделе приведена максимальная и Типичная пропускная способность потока видео для всех поддерживаемых разрешений.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="9e6f5-121">**Тоталрецеивевидеобитратекб**   этот параметр, который является новым в Lync Server 2013, указывает максимально допустимую скорость (в килобитах в секунду) для всех потоков видео, полученных клиентом.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="9e6f5-122">Это означает, что он указывает совокупный итог для всех видеопотоков, за исключением потоковых видеороликов, которые может получать клиент.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="9e6f5-123">Например, если вы укажете 1500 кбит/с, клиент может получить до 1500 кбит/с для видео, которое может состоять из нескольких видеопотоков или одного видеопотока.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="9e6f5-124">Этот параметр применяется только к клиентам Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="9e6f5-125">Значением по умолчанию для **тоталрецеивевидеобитратекб** является 50000 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-125">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps.</span></span> <span data-ttu-id="9e6f5-126">Если для параметра **енаблемултивиевжоин** в представлении коллекции задано значение "истина", **тоталрецеивевидеобитратекб** не должно быть задано ниже 420 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-126">If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps.</span></span> <span data-ttu-id="9e6f5-127">Если для параметра **енаблемултивиевжоин** в представлении коллекции задано значение "ложь", **тоталрецеивевидеобитратекб** не должно быть задано ниже 100 Кбит/с.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-127">If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps.</span></span> <span data-ttu-id="9e6f5-128">Если для **енаблемултивиевжоин** задано значение "true", а для значения ниже 420 кбит/с, то по умолчанию будет использоваться пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-128">If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value.</span></span> <span data-ttu-id="9e6f5-129">Это пороговое значение помогает избежать случайной неправильной конфигурации, которая может привести к плохому взаимодействию с пользователем.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-129">This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e6f5-130">Дополнительные сведения о параметре <STRONG>енаблемултивиевжоин</STRONG> : <A href="lync-server-2013-configuring-gallery-view.md">Настройка представления галереи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="9e6f5-131">**МаксвидеоконференЦингресолутион**   этот параметр больше не используется для клиентов Lync Server 2013 в конференциях Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="9e6f5-132">Конференции Lync Server 2013 используют элементы управления скоростью потока, описанные ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="9e6f5-133">Этот параметр по-прежнему используется для устаревших клиентов, присоединяющихся к конференции Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="9e6f5-134">Этот параметр определяет максимально допустимое разрешение для устаревших клиентов в конференциях, организованных пользователями, которые размещены на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="9e6f5-135">Это значит, что устаревшие клиенты обрабатываются так же, как в предыдущих версиях Lync Server или Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="9e6f5-136">Помимо параметров политики конференций, применяемых к пользователям, оцените параметры конфигурации мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-136">In addition to conferencing policy settings that apply to users, evaluate media configuration settings.</span></span> <span data-ttu-id="9e6f5-137">Чтобы просмотреть или изменить эти параметры, воспользуйтесь одним из следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="9e6f5-137">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="9e6f5-138">**Get-Ксмедиаконфигуратион**</span><span class="sxs-lookup"><span data-stu-id="9e6f5-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="9e6f5-139">**Set-Ксмедиаконфигуратион**</span><span class="sxs-lookup"><span data-stu-id="9e6f5-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="9e6f5-140">**New-Ксмедиаконфигуратион**</span><span class="sxs-lookup"><span data-stu-id="9e6f5-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="9e6f5-141">Проверьте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-141">Verify the following setting:</span></span>

  - <span data-ttu-id="9e6f5-142">**Максвидеоратеалловед**   этот параметр для каждого пула определяет максимальную скорость передачи видеосигналов на конечных точках клиента.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="9e6f5-143">Она применяется только к предыдущим версиям клиентов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e6f5-144">Пользователи Lync Server 2013 не пропускают этот параметр и используют параметр Тоталрецеивевидеобитратекб в разделе "политика конференц-связи".</span><span class="sxs-lookup"><span data-stu-id="9e6f5-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="9e6f5-145">Значением по умолчанию является HD720P.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-145">The default value is HD720P.</span></span> <span data-ttu-id="9e6f5-146">Допустимые значения: HD720p15M, VGA600K и CIF250K.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-146">Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="9e6f5-147">Пример: Если вы укажете 1500 кбит/с, то все устаревшие клиенты в пуле смогут получать до 1500 кбит/с для видео в двух или многосторонних конференциях.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="9e6f5-148">Ниже описаны действия, которые можно использовать для изменения параметров, описанных в этом разделе, в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="9e6f5-149">Изменение политики конференции для настройки видео</span><span class="sxs-lookup"><span data-stu-id="9e6f5-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="9e6f5-150">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9e6f5-151">Чтобы изменить политику конференц-связи, в командной строке выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="9e6f5-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="9e6f5-152">Изменение конфигурации мультимедиа для устаревших клиентов</span><span class="sxs-lookup"><span data-stu-id="9e6f5-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="9e6f5-153">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9e6f5-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9e6f5-154">Чтобы изменить конфигурацию мультимедиа, в командной строке выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="9e6f5-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

