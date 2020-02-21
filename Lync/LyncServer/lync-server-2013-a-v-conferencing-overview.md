---
title: Обзор Lync Server 2013 аудио-и видеоконференций
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2499b7cae2a6833612c34b877ca872f1a504fac9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="c33a8-102">Обзор аудио-и видеоконференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c33a8-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c33a8-103">_**Последнее изменение темы:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="c33a8-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="c33a8-p101">Аудио- и видеоконференции поддерживают аудио- и видеосвязь между пользователями в реальном времени. При развертывании конференц-связи можно включить и использовать веб-конференции и аудио- и видеоконференции или только веб-конференции.</span><span class="sxs-lookup"><span data-stu-id="c33a8-p101">A/V conferencing enables real-time audio and video communications between your users. When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="c33a8-p102">При планировании аудио- и видеоконференций следует учитывать пропускную способность сети, необходимую для типа медиаданных конференций, требуемых для организации. К этим медиаданным может относиться аудио, видео и панорамное видео.</span><span class="sxs-lookup"><span data-stu-id="c33a8-p102">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires. This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="c33a8-108">Перед тем как включить для пользователей аудио- и видеоконференции убедитесь, что сеть сможет обрабатывать результирующую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="c33a8-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="c33a8-109">Без достаточной пропускной способности сети взаимодействие пользователей может значительно ухудшиться.</span><span class="sxs-lookup"><span data-stu-id="c33a8-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="c33a8-110">Для управления пропускной способностью сети, используемой для аудио- и видеоконференций, можно использовать контроль допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="c33a8-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="c33a8-111">Это особенно важно для сетей служебного пользования, таких как каналы с ограниченной пропускной способностью между центральным сайтом и сайтами филиалов.</span><span class="sxs-lookup"><span data-stu-id="c33a8-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="c33a8-112">Дополнительные сведения см. [в разделе Обзор контроля допуска звонков в Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="c33a8-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="c33a8-113">Дополнительные сведения о требованиях к пропускной способности [сети для трафика мультимедиа в Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span><span class="sxs-lookup"><span data-stu-id="c33a8-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="c33a8-114">Если в сети развертываются аудиоконференции, пользователям понадобятся аудиоустройства, например гарнитуры, для участия в аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="c33a8-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="c33a8-115">Если развертываются видеоконференции, пользователям понадобятся видеоустройства, например веб-камеры.</span><span class="sxs-lookup"><span data-stu-id="c33a8-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="c33a8-116">Мы рекомендуем использовать устройства Объединенных коммуникаций, сертифицированные корпорацией Майкрософт для всех типов устройств, чтобы обеспечить оптимальное взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="c33a8-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="c33a8-117">Сведения об устройствах с поддержкой UC можно найти в [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861)разделе "телефоны и устройства для Lync".</span><span class="sxs-lookup"><span data-stu-id="c33a8-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="c33a8-118">Выбор аудио- и видеоустройств, развертывание устройств и обучение пользователей являются важными этапами планирования.</span><span class="sxs-lookup"><span data-stu-id="c33a8-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="c33a8-119">В следующих разделах описываются параметры аудио- и видеоконференций, включая сведения об управлении пропускной способностью и выборе подходящих клиентов.</span><span class="sxs-lookup"><span data-stu-id="c33a8-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="c33a8-120">Параметры аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="c33a8-120">Audio Conferencing Features</span></span>

<span data-ttu-id="c33a8-121">Lync Server 2013 предоставляет несколько функций, которые можно использовать для настройки взаимодействия голосовой связи для пользователя, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="c33a8-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="c33a8-122">**Отключение выключения**   аудитории докладчик может использовать этот параметр, чтобы отключить все звуковые участники в Конференции и перевести конференцию в состояние, в котором сторонние микрофоны не могут быть отключены.</span><span class="sxs-lookup"><span data-stu-id="c33a8-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="c33a8-123">**Объявления входа/выхода конференций**   если вы включили Конференц-связь с телефонным подключением, докладчики могут использовать этот параметр, чтобы включить или отключить объявления входа и выхода, чтобы свести к минимуму число отвлекающих сообщений во время проведения Конференции.</span><span class="sxs-lookup"><span data-stu-id="c33a8-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="c33a8-124">**Добавление пользователя с помощью абонентов**   , использующих докладчиков, и участников, которым предоставлено разрешение, может добавить к конференциям номера PSTN и исходящие номера для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="c33a8-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="c33a8-125">Параметры видеоконференций</span><span class="sxs-lookup"><span data-stu-id="c33a8-125">Video Conferencing Features</span></span>

<span data-ttu-id="c33a8-126">Lync Server 2013 предоставляет несколько функций, которые можно использовать для настройки взаимодействия видеоконференций для пользователя, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="c33a8-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="c33a8-127">**Представление коллекции в**   видеоконференциях, содержащих более двух пользователей, пользователи автоматически видят всех участников Конференции.</span><span class="sxs-lookup"><span data-stu-id="c33a8-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="c33a8-128">Если в конференции участвует больше пяти пользователей, видео самых активных участников отображается в верхнем ряду, а для остальных участников отображается только фото.</span><span class="sxs-lookup"><span data-stu-id="c33a8-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="c33a8-129">Многостороннее видео включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c33a8-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="c33a8-130">Дополнительные сведения о настройке или выключении многосторонних видеороликов можно узнать [в статье Настройка полосы пропускания видео в Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="c33a8-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="c33a8-131">**Панорамное видео**   если устройство видеоконференций Roundtable установлено в комнате конференц-связи, эта функция предоставляет полное представление конференц-зала 360.</span><span class="sxs-lookup"><span data-stu-id="c33a8-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="c33a8-132">Полоса панорамного видео доступна только при использовании устройств RoundTable.</span><span class="sxs-lookup"><span data-stu-id="c33a8-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="c33a8-133">**Только**   докладчик докладчики могут настраивать собрание таким образом, чтобы отображалось только видео из докладчика.</span><span class="sxs-lookup"><span data-stu-id="c33a8-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="c33a8-134">Это ограничивает отвлекающие моменты на больших собраниях, когда доступно несколько видеопотоков, которые захватываются из разных источников.</span><span class="sxs-lookup"><span data-stu-id="c33a8-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="c33a8-135">Этот режим также применяется к видео, которое захватывается и передается устройствами RoundTable.</span><span class="sxs-lookup"><span data-stu-id="c33a8-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="c33a8-136">**Видео**   в формате HD пользователи могут работать с разрешениями до HD 1080p в двусторонних вызовах и многосторонних конференциях.</span><span class="sxs-lookup"><span data-stu-id="c33a8-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="c33a8-137">**Видео Spotlight**   докладчики могут настроить собрание таким образом, чтобы другие участники Конференции видели только видео из выбранного участника, который является источником видеоролика.</span><span class="sxs-lookup"><span data-stu-id="c33a8-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="c33a8-138">Этот режим также применяется к видео, которое захватывается и передается устройствами панорамного видео RoundTable.</span><span class="sxs-lookup"><span data-stu-id="c33a8-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

