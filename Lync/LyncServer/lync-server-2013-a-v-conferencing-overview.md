---
title: Общие сведения о конференц-связи Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d477a8423e7e5ee57e54d0bde584edeb02db4608
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="4769a-102">Общие сведения о конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4769a-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4769a-103">_**Тема последнего изменения:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="4769a-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="4769a-104">Конференции и видеоконференции в режиме реального времени обеспечивают взаимодействие между пользователями.</span><span class="sxs-lookup"><span data-stu-id="4769a-104">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="4769a-105">При развертывании конференций вы можете включить и использовать веб-конференции, а также Конференции или только веб-конференции.</span><span class="sxs-lookup"><span data-stu-id="4769a-105">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="4769a-106">При планировании видео- и голосовой конференц-связи следует понимать, какие мультимедийные данные требуется передавать при конференц-связи в организации и какая полоса пропускания сети необходима для этого типа мультимедийных данных.</span><span class="sxs-lookup"><span data-stu-id="4769a-106">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="4769a-107">Возможные типы – звук, видеоизображение и панорамное видеоизображение.</span><span class="sxs-lookup"><span data-stu-id="4769a-107">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="4769a-108">Перед включением пользователей для конференций/V убедитесь, что сеть может обрабатывать полученную нагрузку.</span><span class="sxs-lookup"><span data-stu-id="4769a-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="4769a-109">Недостаточная полоса пропускания сети может существенно ухудшить взаимодействие в пользователями.</span><span class="sxs-lookup"><span data-stu-id="4769a-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="4769a-110">Вы можете использовать управление допуском звонков (CAC), чтобы управлять пропускной способностью сети, используемой в конференц-связи/V.</span><span class="sxs-lookup"><span data-stu-id="4769a-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="4769a-111">Это важно для сетей с ограниченным доступом, например, для ссылок с ограниченной пропускной способностью между центральным и филиалным сайтами.</span><span class="sxs-lookup"><span data-stu-id="4769a-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="4769a-112">Подробности можно найти [в статье Обзор управления допуском звонков в Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="4769a-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="4769a-113">Дополнительные сведения о требованиях к пропускной способности [сети в Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)см.</span><span class="sxs-lookup"><span data-stu-id="4769a-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="4769a-114">При развертывании звуковых конференций в сети пользователям понадобятся звуковые устройства, например гарнитуры, которые будут участвовать в голосовой конференции.</span><span class="sxs-lookup"><span data-stu-id="4769a-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="4769a-115">Если вы развертываете видеоконференции, вам нужно развернуть видеоустройства, например веб-камеру для пользователей.</span><span class="sxs-lookup"><span data-stu-id="4769a-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="4769a-116">Для обеспечения оптимального взаимодействия с пользователем мы рекомендуем использовать устройства унифицированной связи (UC), сертифицированные корпорацией Майкрософт для всех типов устройств.</span><span class="sxs-lookup"><span data-stu-id="4769a-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="4769a-117">Подробные сведения об устройствах, сертифицированных в UC, можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)разделе "телефоны и устройства для Lync".</span><span class="sxs-lookup"><span data-stu-id="4769a-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="4769a-118">Для использования аудио и видеоустройств, развертывания устройств и обучения пользователей необходимо учитывать и планировать.</span><span class="sxs-lookup"><span data-stu-id="4769a-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="4769a-119">В следующих разделах описаны возможности голосовой и видеоконференции, в том числе сведения об управлении пропускной способностью и выборе соответствующих клиентов.</span><span class="sxs-lookup"><span data-stu-id="4769a-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="4769a-120">Возможности голосовой конференции</span><span class="sxs-lookup"><span data-stu-id="4769a-120">Audio Conferencing Features</span></span>

<span data-ttu-id="4769a-121">Lync Server 2013 предоставляет несколько функций, которые можно использовать для настройки возможностей голосовой связи для пользователя, включая указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="4769a-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="4769a-122">**Отключить звук**   аудитории. Выступающие могут использовать этот параметр, чтобы отключить все участники звука на Конференции и перевести конференцию в состояние, в котором не выступающие могут отключить микрофон.</span><span class="sxs-lookup"><span data-stu-id="4769a-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="4769a-123">**Объявления записей и выхода**   в конференциях если вы включили Конференц-связь с телефонным подключением, выступающие могут использовать этот параметр, чтобы включить или отключить объявления входа и выхода, чтобы свести к минимуму количество отвлекающих событий во время проведения Конференции.</span><span class="sxs-lookup"><span data-stu-id="4769a-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="4769a-124">**Если вы добавляете пользователя с помощью абонентов**   , находящихся в списке, вы можете добавить в конференции номера PSTN и исходящие звонки на эти номера.</span><span class="sxs-lookup"><span data-stu-id="4769a-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="4769a-125">Возможности видеоконференций</span><span class="sxs-lookup"><span data-stu-id="4769a-125">Video Conferencing Features</span></span>

<span data-ttu-id="4769a-126">Lync Server 2013 предоставляет несколько функций, с помощью которых можно настроить видеоконференции для пользователя, в том числе указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="4769a-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="4769a-127">**Представление коллекции в**   видеоконференциях, в которых более двух пользователей, пользователи автоматически видят всех участников Конференции.</span><span class="sxs-lookup"><span data-stu-id="4769a-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="4769a-128">Если в конференции больше пяти участников, верхний ряд содержит видеоизображения самых активных участников; остальные участники представлены только фотографией.</span><span class="sxs-lookup"><span data-stu-id="4769a-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="4769a-129">По умолчанию многосторонняя видеосвязь включена.</span><span class="sxs-lookup"><span data-stu-id="4769a-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="4769a-130">Дополнительные сведения о настройке и отключении многокомпонентного видео можно найти [в разделе Настройка пропускной способности видео в Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="4769a-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="4769a-131">**Панорамное видео**   если в конференц-зале Roundtable установлено устройство для видеоконференций, эта функция обеспечивает полную версию 360 в конференц-зале.</span><span class="sxs-lookup"><span data-stu-id="4769a-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="4769a-132">Полоса панорамного видеоизображения доступна только при наличии устройств RoundTable.</span><span class="sxs-lookup"><span data-stu-id="4769a-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="4769a-133">\*\*\*\* Выступающий. Выступающие могут настроить собрание, чтобы отображалось только видео из выступающего.   </span><span class="sxs-lookup"><span data-stu-id="4769a-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="4769a-134">Это ограничивает отвлекающие факторы на больших собраниях при наличии нескольких потоков видеоданных, привязанных к разным источникам.</span><span class="sxs-lookup"><span data-stu-id="4769a-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="4769a-135">Этот режим применяется также к захвату и передаче видеосигнала на устройствах RoundTable.</span><span class="sxs-lookup"><span data-stu-id="4769a-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="4769a-136">**Пользователи HD видео**   могут столкнуться с разрешениями до HD 1080p с участием двух сторон и многофакторных конференций.</span><span class="sxs-lookup"><span data-stu-id="4769a-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="4769a-137">**Видеоролики в центре внимания**   могут настроить собрание таким образом, что участники Конференции будут видеть только видео из выбранного участника, который является источником видео.</span><span class="sxs-lookup"><span data-stu-id="4769a-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="4769a-138">Этот режим применяется также к захвату и передаче видеосигнала на устройствах RoundTable, обеспечивающих панорамное видеоизображение.</span><span class="sxs-lookup"><span data-stu-id="4769a-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

