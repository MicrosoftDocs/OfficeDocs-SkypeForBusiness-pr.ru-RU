---
title: 'Lync Server 2013: Настройка пропускной способности видео'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed1dfd2e8879776733e6ca6fbd8d6024533ef622
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="85a8c-102">Настройка пропускной способности видео в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85a8c-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85a8c-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="85a8c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="85a8c-104">Lync Server 2013 содержит несколько параметров для управления видеороликом для двусторонних звонков и многосторонних конференций.</span><span class="sxs-lookup"><span data-stu-id="85a8c-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="85a8c-105">При развертывании Lync Server 2013 необходимо оценить, подходят ли параметры по умолчанию для вашей организации, и при необходимости изменить их.</span><span class="sxs-lookup"><span data-stu-id="85a8c-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="85a8c-p102">Параметры, описанные в этом разделе, применимы к двухсторонним звонкам и многопользовательским конференциям. Эти параметры можно просмотреть или изменить с помощью одного из следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="85a8c-p102">The parameters described in this section apply to both two-party calls and multiparty conferencing. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="85a8c-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="85a8c-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="85a8c-109">**Set — CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="85a8c-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="85a8c-110">**New — CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="85a8c-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="85a8c-111">Проверьте следующие параметры в политике конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="85a8c-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="85a8c-112">**Видеобитратекб**   этот параметр определяет максимальную скорость видеопотока в килобитах в секунду (кбит/с), используемую для видео, отправляемых пользователем.</span><span class="sxs-lookup"><span data-stu-id="85a8c-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="85a8c-113">Значение по умолчанию — 50000 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="85a8c-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="85a8c-114">Допустимые значения: от 0 до 50000.</span><span class="sxs-lookup"><span data-stu-id="85a8c-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="85a8c-115">Этот параметр применяется отдельно к основному и панорамному видео.</span><span class="sxs-lookup"><span data-stu-id="85a8c-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="85a8c-116">Пример: Если вы укажете 2000 кбит/с, то Lync Server может отправить 2000 кбит/с для основного видеопотока и 2000 кбит/с для видеопотока панорамного видео.</span><span class="sxs-lookup"><span data-stu-id="85a8c-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85a8c-117">Максимальная пропускная способность видеосети для конечной точки Lync 2013 составляет 8000 кбит/с для основного видео и 2500 кбит/с для панорамного видео.</span><span class="sxs-lookup"><span data-stu-id="85a8c-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="85a8c-118">Эти максимальные значения достигаются только в том случае, если одновременно получаются или передаются несколько видеопотоков.</span><span class="sxs-lookup"><span data-stu-id="85a8c-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="85a8c-119">Для получения дополнительных сведений см раздел "использование сети трафика мультимедиа" <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">требования к пропускной способности сети для трафика мультимедиа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="85a8c-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="85a8c-120">В этом разделе приводятся максимальная и обычная пропускная способность для передачи видеопотока во всех поддерживаемых разрешениях.</span><span class="sxs-lookup"><span data-stu-id="85a8c-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="85a8c-121">**Параметра totalreceivevideobitratekb задано**   этот параметр, который впервые появился в Lync Server 2013, указывает максимально допустимую скорость (в килобитах в секунду) для всех потоков видеоданных, полученных клиентом.</span><span class="sxs-lookup"><span data-stu-id="85a8c-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="85a8c-122">он определяет общую скорость всех видеопотоков, кроме панорамных видеопотоков, которую может принимать клиент.</span><span class="sxs-lookup"><span data-stu-id="85a8c-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="85a8c-123">Например, если указать скорость 1500 кбит/с, то клиент может получить до 1500 кбит/с видео, что может включать множество видеопотоков или один видеопоток.</span><span class="sxs-lookup"><span data-stu-id="85a8c-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="85a8c-124">Этот параметр применяется только к клиентам Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85a8c-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="85a8c-p106">Значение по умолчанию для **TotalReceiveVideoBitRateKb** — 50000 кбит/с. Если для параметра **EnableMultiviewJoin** представления коллекции установлено значение True, значение **TotalReceiveVideoBitRateKb** не должно быть ниже 420 кбит/с. Если значение параметра **EnableMultiviewJoin** представления коллекции равно False, значение **TotalReceiveVideoBitRateKb** не должно быть ниже 100 кбит/с. Если значение **EnableMultiviewJoin** равно True и не превышает 420 кбит/с, по умолчанию будут использоваться пороговое значение. Оно применяется, чтобы предотвратить случайные ошибки конфигурации, которые могут привести к снижению эффективности работы пользователей.</span><span class="sxs-lookup"><span data-stu-id="85a8c-p106">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps. If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value. This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85a8c-130">Подробные сведения о параметре <STRONG>для параметра enablemultiviewjoin</STRONG> приведены <A href="lync-server-2013-configuring-gallery-view.md">в разделе Настройка галереи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="85a8c-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="85a8c-131">**МаксвидеоконференЦингресолутион**   этот параметр больше не используется для клиентов Lync Server 2013 в конференциях Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85a8c-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="85a8c-132">Конференции Lync Server 2013 используют элементы управления скоростью передачи, описанные ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="85a8c-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="85a8c-133">Этот параметр все еще используется для устаревших клиентов, присоединяющихся к конференции Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85a8c-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="85a8c-134">Этот параметр определяет максимально допустимое разрешение для устаревших клиентов в конференциях, организованных пользователями, размещенными в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85a8c-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="85a8c-135">То есть устаревшие клиенты считаются такими же, как и в предыдущих версиях Lync Server или Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="85a8c-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="85a8c-p108">Помимо параметры политики конференций, которые применяются к пользователям, оцените параметры конфигурации мультимедиа. Эти параметры можно просмотреть или изменить с помощью одного из следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="85a8c-p108">In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="85a8c-138">**Get — CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="85a8c-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="85a8c-139">**Set — CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="85a8c-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="85a8c-140">**New — CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="85a8c-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="85a8c-141">Проверьте следующий параметр:</span><span class="sxs-lookup"><span data-stu-id="85a8c-141">Verify the following setting:</span></span>

  - <span data-ttu-id="85a8c-142">**Максвидеоратеалловед**   этот параметр для каждого пула определяет максимальную скорость передачи видеосигналов в конечных точках клиента.</span><span class="sxs-lookup"><span data-stu-id="85a8c-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="85a8c-143">Он применяется только к предыдущим версиям клиентов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85a8c-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85a8c-144">Lync Server 2013 клиенты игнорируют этот параметр и используют параметр параметра totalreceivevideobitratekb задано в политике конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="85a8c-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="85a8c-p110">Значение по умолчанию — HD720P. Допустимые значения: HD720p15M, VGA600K и CIF250K.</span><span class="sxs-lookup"><span data-stu-id="85a8c-p110">The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="85a8c-147">Пример: если указать 1500 кбит/с, то все устаревшие клиенты в пуле смогут получать до 1500 кбит/с видео в двухсторонних или многосторонних конференциях.</span><span class="sxs-lookup"><span data-stu-id="85a8c-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="85a8c-148">В следующих процедурах приведены примеры использования командной консоли Lync Server для изменения параметров, описанных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="85a8c-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="85a8c-149">Изменение параметров политики для видео конференций</span><span class="sxs-lookup"><span data-stu-id="85a8c-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="85a8c-150">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="85a8c-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="85a8c-151">В командной строке выполните следующий командлет, чтобы изменить политику конференций:</span><span class="sxs-lookup"><span data-stu-id="85a8c-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="85a8c-152">Изменение конфигурации мультимедиа для устаревших клиентов</span><span class="sxs-lookup"><span data-stu-id="85a8c-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="85a8c-153">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="85a8c-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="85a8c-154">В командной строке выполните следующий командлет, чтобы изменить конфигурацию мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="85a8c-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

