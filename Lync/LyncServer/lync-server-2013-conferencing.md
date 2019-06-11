---
title: 'Lync Server 2013: конференц-связь'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00f368a375a73eddc78b858c0d85a1bc21a1bd04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="58d78-102">Конференц-связь в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58d78-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58d78-103">_**Тема последнего изменения:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="58d78-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="58d78-104">С помощью единой Конференции в Lync Server 2013 пользователи могут совместно работать, обмениваться информацией и координировать работу в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="58d78-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="58d78-105">Все пользователи могут использовать полную область совместной работы, запланированных собраний и средств для собраний.</span><span class="sxs-lookup"><span data-stu-id="58d78-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="58d78-106">Возможности голосовой связи и видеоконференции можно использовать в любом месте с подключением к Интернету, а пользователи за пределами компьютера могут принимать участие в телеконференциях с помощью коммутируемой телефонной сети с коммутируемой телефонной связью.</span><span class="sxs-lookup"><span data-stu-id="58d78-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="58d78-107">Встроенные в Outlook средства для собраний организаторов, чтобы запланировать собрание или начать конференцию незапланированное одним щелчком, а также сделать так, чтобы участники были легко присоединены.</span><span class="sxs-lookup"><span data-stu-id="58d78-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="58d78-108">Веб-клиент расширяет возможности многофункциональной конференции для участников, которые не работают в классической версии Lync.</span><span class="sxs-lookup"><span data-stu-id="58d78-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="58d78-109">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="58d78-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="58d78-110">Lync Server предоставляет пользователю возможности, знакомые пользователям традиционных служб, в том числе к службам телефонного моста с помощью команд управления звонками.</span><span class="sxs-lookup"><span data-stu-id="58d78-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="58d78-111">В то же время она включает в себя широкие возможности планирования, присоединения и управления, доступные только со встроенной платформой единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="58d78-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="58d78-112">С помощью одного щелчка пользователи могут запланировать собрание в Outlook.</span><span class="sxs-lookup"><span data-stu-id="58d78-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="58d78-113">Сведения, такие как время собрания, расположение и участники, следуют знакомому шаблону Outlook.</span><span class="sxs-lookup"><span data-stu-id="58d78-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="58d78-114">Кроме того, сведения, относящиеся к Конференции, такие как номера телефонного подключения, идентификаторы собраний и личные ПИН-коды, заполняются автоматически.</span><span class="sxs-lookup"><span data-stu-id="58d78-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="58d78-115">Чтобы убедиться в том, что в звонке участвуют только авторизованные люди, Lync Server предлагает несколько уровней проверки подлинности для участников.</span><span class="sxs-lookup"><span data-stu-id="58d78-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="58d78-116">Пользователи, присоединяющиеся с помощью Lync, уже прошли проверку подлинности доменных служб Active Directory и не нуждаются в вводе PIN-кода, идентификатора передачи или ИД собрания.</span><span class="sxs-lookup"><span data-stu-id="58d78-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="58d78-117">Lync упрощает пользовательский интерфейс видеоконференций, добавляя в него видео в единую систему, чтобы можно было легко и быстро распланировать собрание с видео или восприятие видео.</span><span class="sxs-lookup"><span data-stu-id="58d78-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="58d78-118">Lync Server упрощает добавление видео в стандартный телефонный звонок одним щелчком мыши.</span><span class="sxs-lookup"><span data-stu-id="58d78-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="58d78-119">Если в видеозвонке или Конференции есть несколько участников, каждый из них может видеть видео одновременно не более чем пяти пользователей, или выступающее может выбрать только один источник видео, который будет смотреться исключительно всеми.</span><span class="sxs-lookup"><span data-stu-id="58d78-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="58d78-120">Видео высокой четкости (разрешение 1270 x 720; пропорции 16:9) и видео VGA (разрешение 640 x 480; пропорции 4:3) поддерживаются для одноранговых вызовов между пользователями Lync на компьютерах с большим объемом.</span><span class="sxs-lookup"><span data-stu-id="58d78-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="58d78-121">Разрешение, отображаемое каждым участником одной беседы, может различаться в зависимости от того, какие видеоролики есть на оборудовании каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="58d78-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="58d78-122">ИТ-администраторы могут настроить политики для ограничения или отключения высококачественных и видеороликов на клиентах, в зависимости от возможности компьютера, пропускной способности сети и присутствия камеры, позволяющей добиться требуемого разрешения.</span><span class="sxs-lookup"><span data-stu-id="58d78-122">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution.</span></span> <span data-ttu-id="58d78-123">Эти политики принудительно применяются при подготовке по каналу.</span><span class="sxs-lookup"><span data-stu-id="58d78-123">These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="58d78-124">веб-конференции</span><span class="sxs-lookup"><span data-stu-id="58d78-124">Web conferencing</span></span>

<span data-ttu-id="58d78-125">Lync Server интегрирует в упрощенное приложение Lync функции совместного использования конференций, такие как настольные компьютеры, приложения, вложения, доски, опрос и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="58d78-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="58d78-126">В сочетании с аудио-и видеоконференцией результат — это очень впечатляющий и совместный сеанс, который легко легко облегчить.</span><span class="sxs-lookup"><span data-stu-id="58d78-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="58d78-127">Чтобы улучшить общее взаимодействие пользователей с презентацией PowerPoint, Lync Server 2013 использует Office Web Apps для обработки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="58d78-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="58d78-128">Пользователи могут предоставить доступ к рисунку или скопировать и вставить текст с помощью доски на собрании Lync.</span><span class="sxs-lookup"><span data-stu-id="58d78-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="58d78-129">Выступающие могут проводить опросы на собрании Lync, чтобы запрашивать отзывы от участников.</span><span class="sxs-lookup"><span data-stu-id="58d78-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="58d78-130">Функция совместного доступа к рабочему столу позволяет выступающим широковещательно рассылать любые визуальные элементы, приложения, веб-страницы, документы, программное обеспечение или часть настольных компьютеров другим участникам в режиме реального времени, прямо из Lync.</span><span class="sxs-lookup"><span data-stu-id="58d78-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="58d78-131">Участники аудитории могут следовать за движением мыши и вводом с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="58d78-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="58d78-132">Выступающие могут предоставить общий доступ ко всему экрану или только к части.</span><span class="sxs-lookup"><span data-stu-id="58d78-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="58d78-133">Выполнив демонстрацию своих настольных компьютеров, выступающие смогут привлекаться к своим аудиториям в интерактивных и программных демонстрационных программах из любого места.</span><span class="sxs-lookup"><span data-stu-id="58d78-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="58d78-134">Функция общего доступа к приложениям позволяет выступающим совместно управлять программным обеспечением на своих компьютерах, не теряя обратной связи между участниками и вопросами на тексте.</span><span class="sxs-lookup"><span data-stu-id="58d78-134">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions.</span></span> <span data-ttu-id="58d78-135">Выступающие также могут делегировать управление приложением участникам собрания.</span><span class="sxs-lookup"><span data-stu-id="58d78-135">Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="58d78-136">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="58d78-136">Dial-in Conferencing</span></span>

<span data-ttu-id="58d78-137">Для пользователей, не использующих персональный компьютер, вы можете присоединиться к конференции Lync Server несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="58d78-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="58d78-138">Пользователь PSTN может набрать номер доступа, получить доступ к мосту собраний, а затем ввести код собрания.</span><span class="sxs-lookup"><span data-stu-id="58d78-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="58d78-139">Для более безопасной собраний пользователю также может потребоваться ввести PIN-код для проверки подлинности в службе каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="58d78-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="58d78-140">Lync Server также поддерживает устройства Lync Phone Edition, которые являются самостоятельными устройствами IP-телефонии, предоставляемыми партнерами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="58d78-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

