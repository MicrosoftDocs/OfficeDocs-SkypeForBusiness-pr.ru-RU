---
title: Конференц-связь Lync Server 2013
description: Конференц-связь Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d4a5f1ca1edc6246aace56c8a4bfa5b5215c4bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555955"
---
# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="67e4e-103">Конференц-связь в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67e4e-103">Conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67e4e-104">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="67e4e-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="67e4e-105">С помощью единой конференц-связи в Lync Server 2013 пользователи могут совместно работать, обмениваться информацией и координировать свои усилия в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="67e4e-105">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="67e4e-106">Все пользователи могут использовать весь спектр средств для недостаточной совместной работы, запланированных собраний и средств для собраний.</span><span class="sxs-lookup"><span data-stu-id="67e4e-106">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="67e4e-107">Возможности голосовой связи и видеоконференций можно использовать в любом расположении с подключением к Интернету, а пользователи, отходящие от компьютера, могут участвовать в конференциях с помощью телефонного подключения с помощью телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="67e4e-107">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="67e4e-108">Средства собраний, интегрированные в Outlook, позволяют организаторов запланировать собрание или начать конференцию случайные одним щелчком, а также сделать так же простым присоединением участников.</span><span class="sxs-lookup"><span data-stu-id="67e4e-108">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="67e4e-109">Веб-клиент расширяет функциональные возможности конференций для участников, на которых не установлена настольная версия Lync.</span><span class="sxs-lookup"><span data-stu-id="67e4e-109">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="67e4e-110">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="67e4e-110">Audio and Video Conferencing</span></span>

<span data-ttu-id="67e4e-111">Lync Server предоставляет пользователю возможности, знакомые пользователям традиционных служб аудио-моста, в том числе службы с телефонным подключением PSTN с помощью команд управления звонками.</span><span class="sxs-lookup"><span data-stu-id="67e4e-111">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="67e4e-112">В то же время он включает мощные функции планирования, присоединения и управления, доступные только при использовании интегрированной платформы Объединенных коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="67e4e-112">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="67e4e-113">С помощью одного щелчка пользователи могут запланировать собрание в Outlook.</span><span class="sxs-lookup"><span data-stu-id="67e4e-113">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="67e4e-114">Сведения, такие как время собрания, расположение и участники, следуют привычному шаблону Outlook.</span><span class="sxs-lookup"><span data-stu-id="67e4e-114">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="67e4e-115">Кроме того, сведения, относящиеся непосредственно к конференц-вызову, такие как набираемый номер, идентификаторы собраний и напоминания о личном идентификационном номере (ПИН), заполняются автоматически.</span><span class="sxs-lookup"><span data-stu-id="67e4e-115">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="67e4e-116">Чтобы убедиться, что только авторизованные сотрудники участвуют в вызове, Lync Server предоставляет несколько уровней проверки подлинности для участников.</span><span class="sxs-lookup"><span data-stu-id="67e4e-116">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="67e4e-117">Пользователи, присоединяющиеся с помощью Lync, уже прошли проверку подлинности доменными службами Active Directory и не нуждаются в вводе ПИН-кода, кода передачи или идентификатора собрания.</span><span class="sxs-lookup"><span data-stu-id="67e4e-117">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="67e4e-118">Lync упрощает взаимодействие с видеоконференциями, включая видео в едином клиенте, чтобы распланировать собрание с видео или переключаться на видео в неудобством и легком.</span><span class="sxs-lookup"><span data-stu-id="67e4e-118">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="67e4e-119">Lync Server упрощает добавление видео в стандартный телефонный звонок только одним щелчком мыши.</span><span class="sxs-lookup"><span data-stu-id="67e4e-119">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="67e4e-120">При наличии в видеовызове или конференции нескольких участников makes каждый пользователь может смотреть видео пяти различных пользователей одновременно, а докладчик может выбрать один источник видео, который будет виден каждому участнику.</span><span class="sxs-lookup"><span data-stu-id="67e4e-120">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="67e4e-121">Видео высокой четкости (разрешение 1270 x 720; пропорции 16:9) и видео VGA (разрешение 640 x 480; пропорции 4:3) поддерживаются для одноранговых вызовов между пользователями Lync на высокодоступных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="67e4e-121">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="67e4e-122">Разрешение, видимое каждым участником в рамках отдельной беседы, может отличаться в зависимости от возможностей используемого оборудования.</span><span class="sxs-lookup"><span data-stu-id="67e4e-122">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="67e4e-p108">ИТ-администраторы могут задавать политики для ограничения или отключения видео высокой четкости или VGA в зависимости от возможностей компьютеров, пропускной способности сети и наличия камеры соответствующего разрешения. Эти политики применяются при автоматической подготовке.</span><span class="sxs-lookup"><span data-stu-id="67e4e-p108">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution. These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="67e4e-125">Веб-конференции</span><span class="sxs-lookup"><span data-stu-id="67e4e-125">Web conferencing</span></span>

<span data-ttu-id="67e4e-126">Lync Server интегрирует функции общего доступа к конференц-связи, такие как настольные приложения, приложения, вложения, доски, опрос и PowerPoint, в упрощенный Lync.</span><span class="sxs-lookup"><span data-stu-id="67e4e-126">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="67e4e-127">Вместе с возможностями аудио- и видеоконференций это позволяет задействовать высокоэффективный сеанс удобной совместной работы пользователей.</span><span class="sxs-lookup"><span data-stu-id="67e4e-127">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="67e4e-128">Чтобы упростить общий доступ пользователей к презентациям PowerPoint, Lync Server 2013 использует Office Web Apps для обработки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="67e4e-128">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="67e4e-129">Пользователи могут обмениваться изображениями, а также копировать и вставлять текст с помощью доски в собрании Lync.</span><span class="sxs-lookup"><span data-stu-id="67e4e-129">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="67e4e-130">Выступающие могут проводить опросы на собрании Lync, чтобы запрашивать отзывы от участников.</span><span class="sxs-lookup"><span data-stu-id="67e4e-130">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="67e4e-131">Общий доступ к рабочему столу позволяет докладчикам широковещательно транслировать любые визуальные элементы, приложения, веб-страницы, документы, программное обеспечение или часть настольных компьютеров на удаленные участники в режиме реального времени, прямо из Lync.</span><span class="sxs-lookup"><span data-stu-id="67e4e-131">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="67e4e-132">Аудитория может следить за движениями мыши и вводом с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="67e4e-132">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="67e4e-133">Участники могут открыть доступ ко всему экрану или только к его части.</span><span class="sxs-lookup"><span data-stu-id="67e4e-133">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="67e4e-134">Предоставляя доступ к своим рабочим столам, докладчики могут взаимодействовать со своими слушателями в интерактивном продукте или демонстрационном ПО, находясь в любом месте.</span><span class="sxs-lookup"><span data-stu-id="67e4e-134">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="67e4e-p112">Совместный доступ к приложениям позволяет докладчикам совместно управлять программным обеспечением на своих рабочих станциях, одновременно контролируя отзывы или текстовые вопросы участников. Докладчики могут делегировать управление приложением участникам собрания.</span><span class="sxs-lookup"><span data-stu-id="67e4e-p112">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions. Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="67e4e-137">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="67e4e-137">Dial-in Conferencing</span></span>

<span data-ttu-id="67e4e-138">Для пользователей, не использующих персональный компьютер, существует несколько способов присоединения к конференц-связи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67e4e-138">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="67e4e-139">Пользователь ТФОП может набрать номер доступа, выполнить вход в аудиомост и ввести идентификатор собрания.</span><span class="sxs-lookup"><span data-stu-id="67e4e-139">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="67e4e-140">Если необходима более высокая степень безопасности, пользователь может ввести свой ПИН-код для прохождения проверки подлинности в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="67e4e-140">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="67e4e-141">Lync Server также поддерживает устройства Lync Phone Edition, которые являются самостоятельными устройствами IP-телефонии, предоставляемыми партнерами корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="67e4e-141">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

