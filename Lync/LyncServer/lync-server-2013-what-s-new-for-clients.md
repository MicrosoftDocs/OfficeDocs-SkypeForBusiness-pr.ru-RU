---
title: 'Lync Server 2013: новые возможности для клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210218ec3250e31356564731286735df48836ad6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="03620-102">Новые возможности для клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03620-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03620-103">_**Последнее изменение темы:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="03620-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="03620-104">Microsoft Lync 2013 имеет переработанный пользовательский интерфейс и важные новые функции.</span><span class="sxs-lookup"><span data-stu-id="03620-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="03620-105">Для администраторов клиент теперь включен в программу установки Office, что упрощает развертывание Office и настройку клиентов в Организации.</span><span class="sxs-lookup"><span data-stu-id="03620-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03620-106">Иллюстрированное представление обновлений пользовательского интерфейса Lync 2013: "что нового в Lync 2013" <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span><span class="sxs-lookup"><span data-stu-id="03620-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="03620-107">Интеграция с установкой Office</span><span class="sxs-lookup"><span data-stu-id="03620-107">Integration with Office Setup</span></span>

<span data-ttu-id="03620-108">Клиент Lync 2013 и надстройка "собрание по сети" для Lync 2013, поддерживающие управление собраниями в клиенте обмена сообщениями и совместной работы Outlook, теперь включены в программу установки Office 2013.</span><span class="sxs-lookup"><span data-stu-id="03620-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="03620-109">В предыдущих версиях Lync и Office Communicator можно было использовать свойства установщика Windows для настройки и управления установкой Office.</span><span class="sxs-lookup"><span data-stu-id="03620-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="03620-110">Так как Lync 2013 интегрируется с программой установки Office, можно использовать следующие методы для настройки установки Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="03620-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="03620-111">Использование центра развертывания Office (OCT)</span><span class="sxs-lookup"><span data-stu-id="03620-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="03620-112">Использование Config.xml для выполнения задач, связанных с установкой</span><span class="sxs-lookup"><span data-stu-id="03620-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="03620-113">Использование параметров командной строки установки</span><span class="sxs-lookup"><span data-stu-id="03620-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03620-114">Программа установки Lync 2013 не удаляет предыдущие версии Lync или Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="03620-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="03620-115">Клиент Lync 2013 устанавливается параллельно с другими клиентами Lync или Office Communicator</span><span class="sxs-lookup"><span data-stu-id="03620-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="03620-116">Дополнительные сведения см. [в статье Deploy Lync Clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="03620-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="03620-117">Развертывание с использованием групповой политики</span><span class="sxs-lookup"><span data-stu-id="03620-117">Group Policy Deployment</span></span>

<span data-ttu-id="03620-118">Так как Lync 2013 теперь включен в программу установки Office, метод развертывания параметров групповой политики Lync изменился.</span><span class="sxs-lookup"><span data-stu-id="03620-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="03620-119">В предыдущих версиях Lync и Office Communicator можно было использовать Communicator. adm для определения параметров групповой политики, в то время как в Lync 2013 вы можете использовать административные шаблоны Lync ADMX и ADML, предоставляемые вместе с групповой политикой Office. Административные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="03620-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="03620-120">Дополнительные сведения см. в разделе [Параметры групповой политики для Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="03620-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="03620-121">Обновления надстройки расписаний Outlook</span><span class="sxs-lookup"><span data-stu-id="03620-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="03620-122">Надстройка "собрание по сети" для Lync 2013 включает настройку приглашения на собрание и новые варианты собрания.</span><span class="sxs-lookup"><span data-stu-id="03620-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="03620-123">Администраторы могут настраивать приглашения на собрания в организации, добавляя логотипы, URL-адрес поддержки, URL-адрес юридического уведомления или пользовательский текст нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="03620-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="03620-124">Дополнительную информацию можно узнать в статье [Настройка надстройки "собрание по сети" в Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="03620-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="03620-125">Новые средства отключения звука участников позволяют организаторам собраний планировать конференции, в которых видео и аудио участников выключены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="03620-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="03620-126">Надстройка инфраструктуры виртуальных рабочих столов</span><span class="sxs-lookup"><span data-stu-id="03620-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="03620-127">Клиент Lync 2013 теперь поддерживает аудио и видео в среде инфраструктуры виртуальных рабочих столов (VDI).</span><span class="sxs-lookup"><span data-stu-id="03620-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="03620-128">Пользователь может подключить аудио- или видеоустройство (например, гарнитуру или камеру) к локальному компьютеру (например, к тонкому клиенту или используемому в качестве такового старому компьютеру).</span><span class="sxs-lookup"><span data-stu-id="03620-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="03620-129">Пользователь может подключиться к виртуальной машине, войти в клиент Lync 2013, запущенный на виртуальной машине, и участвовать в аудио-и видеобеседе в режиме реального времени, как будто клиент запущен на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="03620-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="03620-130">В среде виртуальных рабочих столов поддерживаются следующие функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="03620-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="03620-131">Интеграция устройств для аудио и видео, включая следующее.</span><span class="sxs-lookup"><span data-stu-id="03620-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="03620-132">Управление вызовами с устройства</span><span class="sxs-lookup"><span data-stu-id="03620-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="03620-133">Интеграция присутствия на устройстве</span><span class="sxs-lookup"><span data-stu-id="03620-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="03620-134">Поддержка нескольких устройств HID</span><span class="sxs-lookup"><span data-stu-id="03620-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="03620-135">Поддержка служб размещения и экстренного вызова</span><span class="sxs-lookup"><span data-stu-id="03620-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="03620-136">Поддержка всех модальности Lync, включая обмен мгновенными сообщениями, аудио, видео, общий доступ к приложениям, общий доступ к рабочему столу, общий доступ к PowerPoint, доску и передачу файлов.</span><span class="sxs-lookup"><span data-stu-id="03620-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="03620-137">Поддержка аудио и видео при индивидуальном общении и в конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="03620-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="03620-138">Сведения о развертывании подключаемого модуля VDI можно найти в статье [Развертывание подключаемого модуля VDI для Lync в Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="03620-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="03620-139">Улучшения видео</span><span class="sxs-lookup"><span data-stu-id="03620-139">Video Enhancements</span></span>

<span data-ttu-id="03620-140">Несколько новых функциональных возможностей значительно улучшают видеосвязь при конференциях.</span><span class="sxs-lookup"><span data-stu-id="03620-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="03620-141">Работа с видео улучшена благодаря новым функциям, таким как определение лиц и интеллектуальное формирование кадров, так что видео участника перемещается, позволяя ему все время оставаться в центре кадра.</span><span class="sxs-lookup"><span data-stu-id="03620-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="03620-p107">Теперь поддерживается видео высокой четкости при двусторонних вызовах и многосторонних конференциях. Пользователи могут использовать разрешения вплоть до HD 1080P.</span><span class="sxs-lookup"><span data-stu-id="03620-p107">High-definition video is now supported in two-party calls and multiparty conferences. Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="03620-144">Участники могут выбрать различные макеты собраний: в представлении галереи приведены все изображения или видео участников; представление докладчика отображает содержание собрание и видео или изображение докладчика; представление презентации отображает только содержание собрание; компактное представление показывает исключительно элементы управления собранием.</span><span class="sxs-lookup"><span data-stu-id="03620-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="03620-p108">Благодаря новой функциональной возможности галереи участники могут одновременно просматривать несколько видеотрансляций. Если в конференции принимает участие более пяти участников, в верхней строке отображаются видеотрансляции самых активных участников, другие участники представлены изображениями.</span><span class="sxs-lookup"><span data-stu-id="03620-p108">With the new Gallery feature, participants can see multiple video feeds at the same time. If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="03620-147">Участники могут использовать закрепление видео, чтобы постоянно отображать одну или несколько видеотрансляций.</span><span class="sxs-lookup"><span data-stu-id="03620-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="03620-148">Докладчики могут использовать функциональную возможность центра внимания видео для выбора видеотрансляции одного участника, чтобы все остальные участники видели исключительно ее.</span><span class="sxs-lookup"><span data-stu-id="03620-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="03620-149">Интеграция с комнатами чата</span><span class="sxs-lookup"><span data-stu-id="03620-149">Chat Room Integration</span></span>

<span data-ttu-id="03620-150">Lync 2013 теперь интегрирует функции, ранее предоставляемые Lync 2010 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="03620-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="03620-151">Отдельного клиента группового чата больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="03620-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="03620-152">В Lync 2013 пользователи могут искать комнаты чата, добавлять комнаты чата в контакты, отслеживать действия комнаты чата, а также читать и отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="03620-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="03620-153">Пользователи могут создавать тематические каналы, чтобы получать уведомления, когда пользователь в одной из комнат чата добавит сообщение, содержащее определенные ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="03620-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="03620-154">Благодаря новой странице параметров **Сохраняемый част** пользователи могут настраивать уведомления и звуковые оповещения, которые будут срабатывать при публикации другими пользователями сообщений в комнатах чата.</span><span class="sxs-lookup"><span data-stu-id="03620-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="03620-155">Обновления Lync Web App</span><span class="sxs-lookup"><span data-stu-id="03620-155">Lync Web App Updates</span></span>

<span data-ttu-id="03620-156">Lync Web App — это клиент конференций на основе веб-сайта для Lync Server 2013 Meetings.</span><span class="sxs-lookup"><span data-stu-id="03620-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="03620-157">В этом выпуске Добавление аудио-и видеофайлов в Lync Web App обеспечивает полный интерфейс для собраний для всех пользователей, у которых не установлен клиент Lync.</span><span class="sxs-lookup"><span data-stu-id="03620-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="03620-158">Участники собраний имеют доступ ко всем функциональным возможностям совместной работы и общего доступа, а докладчики — к элементам управления собранием.</span><span class="sxs-lookup"><span data-stu-id="03620-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="03620-159">Если пользователь попытается присоединиться к собранию, но на нем нет установленного на локальном компьютере клиента, откроется Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="03620-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="03620-160">Если вы хотите разрешить присоединение к собранию, вы можете настроить страницу присоединения к собранию; в документации по развертыванию вы найдете [страницу Настройка страницы присоединения к собранию в Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) .</span><span class="sxs-lookup"><span data-stu-id="03620-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="03620-161">Из-за улучшений в Lync Web App обновленная версия участника недоступна для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03620-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="03620-162">Lync Web App — это клиент, который подходит для участников за пререшениями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="03620-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="03620-163">Локальной установки клиента не требуется, хотя для работы функциональных возможностей аудио, видео и совместного доступа требуется установка надстройки при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="03620-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="03620-164">Обновления для мобильных клиентов Lync 2013</span><span class="sxs-lookup"><span data-stu-id="03620-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="03620-165">Кроме расширенных возможностей присутствия, контактов и обмена мгновенными сообщениями, мобильные клиенты Lync 2013 теперь обеспечивают голосовые и видеозвонки через Интернет и подключения к сотовым каналам данных.</span><span class="sxs-lookup"><span data-stu-id="03620-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="03620-166">С помощью одного касания ссылки на собрание в элементе календаря мобильные пользователи могут присоединяться к собраниям и голосовым собраниям Lync.</span><span class="sxs-lookup"><span data-stu-id="03620-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="03620-167">Дополнительные сведения о клиентах для мобильных устройств Lync 2013 вы найдете [в статье Планирование для мобильных клиентов в Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="03620-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="03620-168">Обновления пользовательского интерфейса Lync 2013</span><span class="sxs-lookup"><span data-stu-id="03620-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="03620-169">Обновления специальных возможностей</span><span class="sxs-lookup"><span data-stu-id="03620-169">Accessibility Updates</span></span>

<span data-ttu-id="03620-170">Lync 2013 включает несколько новых функций специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="03620-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="03620-171">Lync 2013 поддерживает разрешение высокого разрешения, позволяя пользователям масштабировать текст и графику для 125% и 150% точек на дюйм.</span><span class="sxs-lookup"><span data-stu-id="03620-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="03620-172">Lync обеспечивает поддержку высокой контрастности, поэтому пользовательский интерфейс остается полностью функциональным при использовании с высококонтрастными темами в Windows.</span><span class="sxs-lookup"><span data-stu-id="03620-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="03620-173">Lync предлагает более 100 сочетаний клавиш, чтобы пользователи могли получать доступ к важным функциям без мыши.</span><span class="sxs-lookup"><span data-stu-id="03620-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="03620-174">Например, пользователи могут нажать клавиши Alt+C, чтобы принять вызов, или клавиши Alt + I, чтобы игнорировать его, без необходимости перемещения фокуса в нужное окно.</span><span class="sxs-lookup"><span data-stu-id="03620-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="03620-175">Нажатие Alt+Q завершает вызов, Ctrl+N — запускает OneNote, а Alt+T служит для открытия меню "Сервис".</span><span class="sxs-lookup"><span data-stu-id="03620-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="03620-176">Широкая поддержка средства чтения с экрана в Lync 2013 гарантирует, что все уведомления, входящие запросы и мгновенные сообщения считываются вслух, когда включено средство чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="03620-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="03620-177">Состояние присутствия во время общего доступа</span><span class="sxs-lookup"><span data-stu-id="03620-177">Presence While Sharing</span></span>

<span data-ttu-id="03620-178">Когда Lync обнаружит, что пользователь предоставляет общий доступ, Lync автоматически назначает пользователю представление о присутствии.</span><span class="sxs-lookup"><span data-stu-id="03620-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="03620-179">Это состояние приводит к блокированию всей входящей связи, если отправитель не имеет частных отношений рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="03620-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="03620-180">Если пользователь полностью использует функцию общего доступа на дополнительном мониторе, Lync не назначает представление о присутствии.</span><span class="sxs-lookup"><span data-stu-id="03620-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="03620-181">Обновления окна беседы</span><span class="sxs-lookup"><span data-stu-id="03620-181">Conversation Window Updates</span></span>

<span data-ttu-id="03620-182">Измененное окно беседы обеспечивает более быстрый доступ к важным функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="03620-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="03620-p116">Благодаря новой функциональной возможности размещения бесед на вкладках пользователи могут использовать одно окно для ведения всех своих бесед в чатах и с помощью мгновенного обмена сообщениями. Вкладки по левой стороне окна беседы позволяют пользователям без труда переключаться между активными беседами.</span><span class="sxs-lookup"><span data-stu-id="03620-p116">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window. The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="03620-p117">Пользователи могут перенести беседу в отдельное окно, а затем изменить его размеры. Кроме того, можно также вернуть это окно обратно в окне бесед.</span><span class="sxs-lookup"><span data-stu-id="03620-p117">Users can pop out an individual conversation into a separate window, and then resize the window. They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="03620-187">Lync 2013 повторно открывает диалоги пользователя, когда пользователь выйдет из приложения и войдет обратно в Lync.</span><span class="sxs-lookup"><span data-stu-id="03620-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="03620-188">Пользователи могут быстро добавлять мгновенные сообщения, видео, общий доступ к программам, общий доступ к рабочему столу или средства веб-конференции (доска, заметки, общие записные книжки и вложения) в любые беседы.</span><span class="sxs-lookup"><span data-stu-id="03620-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="03620-189">При проведении собрания с использованием общего доступа к видео или другому содержимому пользователи могут перенести в отдельное окно видео собрания или совместно используемые материалы, а затем изменить размеры этого окна.</span><span class="sxs-lookup"><span data-stu-id="03620-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="03620-190">Обновления основного окна Lync</span><span class="sxs-lookup"><span data-stu-id="03620-190">Lync Main Window Updates</span></span>

<span data-ttu-id="03620-191">Новый упрощенный вид сохраняет знакомые особенности, такие как поле заметки **Что сегодня произошло?**, возможность выбора состояния и возможность выбора **Задать местоположение**.</span><span class="sxs-lookup"><span data-stu-id="03620-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="03620-192">Когда комнаты чата включены, пользователи видят новый значок **чатов** на основной странице Lync.</span><span class="sxs-lookup"><span data-stu-id="03620-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="03620-193">С помощью значка **Комнаты чата** пользователи могут быстро получить доступ к своим комнатам чата и фильтрам.</span><span class="sxs-lookup"><span data-stu-id="03620-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="03620-194">Пользователи могут щелкать значки представления для переключения в представление **Контакты**, **Комнаты чата**, **Беседы** или **Телефон**.</span><span class="sxs-lookup"><span data-stu-id="03620-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="03620-195">Если пользователи были перенесены в Exchange 2013, они могут отправить изображение с высоким разрешением.</span><span class="sxs-lookup"><span data-stu-id="03620-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="03620-196">Обновления представления "Контакты" и карточки контакта</span><span class="sxs-lookup"><span data-stu-id="03620-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="03620-197">Lync 2013 предоставляет пользователям различные способы просмотра контактов и групп в их представлениях **контактов** .</span><span class="sxs-lookup"><span data-stu-id="03620-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="03620-198">Благодаря новому единому хранилищу контактов после переноса контактов Lync для пользователей в Exchange 2013 пользователи могут получать доступ к своим контактам и управлять ими из Lync 2013, Outlook или Outlook Web App, а их Избранное остается синхронизированным.</span><span class="sxs-lookup"><span data-stu-id="03620-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="03620-199">Например, если пользователь добавляет контакт в папку "Избранное" в Outlook, он отображается в группе "Избранное" в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="03620-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="03620-200">При добавлении и настройке прокси-сервера XMPP и шлюза XMPP пользователи могут добавлять контакты партнеров XMPP для обмена мгновенными сообщениями и просмотра состояния присутствия.</span><span class="sxs-lookup"><span data-stu-id="03620-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="03620-201">Новая функциональная возможность **добавления контакта, не состоящего в моей организации** предоставляет пользователям простой способ добавлять пользователей, которые являются внешними по отношению к организации.</span><span class="sxs-lookup"><span data-stu-id="03620-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="03620-202">Новая группа **Избранное** позволяет пользователям создать списки людей, с которыми пользователями связываются чаще всего, для упрощения доступа.</span><span class="sxs-lookup"><span data-stu-id="03620-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="03620-p120">Пользователи могут использовать новую страницу параметров **Список контактов** для определения сортировки и отображения контактов. Пользователи могут выбрать расширенное, двухстрочное представление с отображением фотографии контакта или сжатое представление в одну строку. Пользователи могут также упорядочивать контакты в алфавитном порядке или в соответствии с доступностью.</span><span class="sxs-lookup"><span data-stu-id="03620-p120">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts. Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view. Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="03620-206">Обновления конференц-связи</span><span class="sxs-lookup"><span data-stu-id="03620-206">Conferencing Updates</span></span>

<span data-ttu-id="03620-207">Lync 2013 предлагает несколько улучшений функций конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="03620-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="03620-p121">В зависимости от типа собрания пользователи могут выключать звук участников или блокировать видеопоказ на этапе планирования собрания. Эти параметры доступны на странице **Параметры собрания** и рекомендованы к использованию для больших собраний с числом участников более 20.</span><span class="sxs-lookup"><span data-stu-id="03620-p121">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting. These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="03620-210">Простые в использовании элементы управления аудио в комнате собрания позволяют управлять такими параметрами аудио, как отключение и включение звука, изменение устройства и т. д.</span><span class="sxs-lookup"><span data-stu-id="03620-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="03620-211">При предоставлении общего доступа к программам пользователи могут выбрать несколько программ для общего доступа, если необходимо работать с несколькими программами.</span><span class="sxs-lookup"><span data-stu-id="03620-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="03620-212">Теперь пользователи могут загружать презентации, содержащие видеоклипы, путем передачи файлов PowerPoint, а также наводить указатель мыши на слайд для отображения элементов управления видео, таких как воспроизведение, пауза и элементы управления звуком.</span><span class="sxs-lookup"><span data-stu-id="03620-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="03620-213">Во время собрания пользователи могут объединить с собранием другую открытую беседу с помощью команды **Объединить беседу в** в меню **Дополнительные параметры** (**…**).</span><span class="sxs-lookup"><span data-stu-id="03620-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="03620-214">Чтобы просмотреть имена участников, можно навести указатель мыши на кнопку **Просмотреть участников** или щелкнуть **Показать список участников** для стыковки панели в собрании.</span><span class="sxs-lookup"><span data-stu-id="03620-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="03620-215">В зависимости от типа собрания пользователи могут выбрать различные представления содержимого и участников.</span><span class="sxs-lookup"><span data-stu-id="03620-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="03620-p122">Записи собраний автоматически сохраняются в формате, который воспроизводится в Windows Media Player (MP4). Пользователи могут без труда предоставлять файл записи другим пользователям или использовать возможность **публикации** в диспетчере записей для публикации записи в общедоступном месте.</span><span class="sxs-lookup"><span data-stu-id="03620-p122">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4). Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="03620-p123">Приложение OneNote предоставляет новые способы совместной работы в собрании. Во время собрания пользователи могут делать заметки с помощью OneNote для их последующего личного использования. Также можно использовать общие записные книжки, совместно редактируя в них записи в режиме реального времени. Все участники группы имеют доступ к общим запискам и могут предоставлять сведения, делиться идеями или использовать страницы блокнота в качестве виртуальной доски. Общее содержимое собрания автоматически добавляется в заметки.</span><span class="sxs-lookup"><span data-stu-id="03620-p123">OneNote enables new ways to collaborate in a meeting. During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time. All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard. People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="03620-p124">Пользователи могут переключаться между типами содержимого с помощью параметра **Совместный доступ к содержимому и действиям ведущего** в нижней части комнаты собрания. Кроме того, пользователи могут использовать меню **Управление демонстрируемым содержимым** для выбора содержимого, совместный доступ к которому необходимо предоставить.</span><span class="sxs-lookup"><span data-stu-id="03620-p124">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room. Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03620-224">См. также</span><span class="sxs-lookup"><span data-stu-id="03620-224">See Also</span></span>


[<span data-ttu-id="03620-225">Планирование для клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03620-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

