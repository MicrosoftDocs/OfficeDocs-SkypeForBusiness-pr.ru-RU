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
ms.openlocfilehash: f938ccc4e4a040307a7cf86a8084353c480cfdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="61c99-102">Новые возможности для клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61c99-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61c99-103">_**Тема последнего изменения:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="61c99-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="61c99-104">В Microsoft Lync 2013 имеется переработанный пользовательский интерфейс и важные новые возможности.</span><span class="sxs-lookup"><span data-stu-id="61c99-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="61c99-105">Для администраторов теперь клиент входит в состав программы установки Office, что обеспечивает более простой подход к развертыванию Office и настройке клиентов в Организации.</span><span class="sxs-lookup"><span data-stu-id="61c99-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61c99-106">Наглядное представление об обновлениях пользовательского интерфейса Lync 2013 можно найти в <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>разделе "что нового в Lync 2013".</span><span class="sxs-lookup"><span data-stu-id="61c99-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="61c99-107">Интеграция с программой установки Office</span><span class="sxs-lookup"><span data-stu-id="61c99-107">Integration with Office Setup</span></span>

<span data-ttu-id="61c99-108">Клиент Lync 2013 и надстройка "собрание по сети" для Lync 2013, поддерживающие управление собраниями в клиенте Outlook для обмена сообщениями и совместной работы, теперь включены вместе с программой установки Office 2013.</span><span class="sxs-lookup"><span data-stu-id="61c99-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="61c99-109">В предыдущих версиях Lync и Office Communicator вы можете настраивать и управлять установкой Office с помощью свойств установщика Windows.</span><span class="sxs-lookup"><span data-stu-id="61c99-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="61c99-110">Поскольку Lync 2013 интегрируется с программой установки Office, вы можете использовать следующие методы для настройки настройки Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="61c99-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="61c99-111">Использование центра развертывания Office (OCT)</span><span class="sxs-lookup"><span data-stu-id="61c99-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="61c99-112">Выполнение задач установки с помощью файла config. XML</span><span class="sxs-lookup"><span data-stu-id="61c99-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="61c99-113">Использование параметров командной строки для настройки</span><span class="sxs-lookup"><span data-stu-id="61c99-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61c99-114">Программа установки Lync 2013 не удаляет предыдущие версии Lync и Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="61c99-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="61c99-115">Клиент Lync 2013 устанавливается параллельно с другими клиентами Lync или Office Communicator</span><span class="sxs-lookup"><span data-stu-id="61c99-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="61c99-116">Подробные сведения можно найти [в разделе Развертывание клиентов Lync в Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="61c99-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="61c99-117">Развертывание групповой политики</span><span class="sxs-lookup"><span data-stu-id="61c99-117">Group Policy Deployment</span></span>

<span data-ttu-id="61c99-118">Поскольку Lync 2013 теперь включен в программу установки Office, изменился метод развертывания параметров групповой политики Lync.</span><span class="sxs-lookup"><span data-stu-id="61c99-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="61c99-119">В предыдущих версиях Lync и Office Communicator вы можете использовать Communicator. adm для определения параметров групповой политики, в то время как в Lync 2013 теперь можно использовать административные шаблоны Lync ADMX и ADML, предоставленные вместе с групповой политикой Office. Административные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="61c99-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="61c99-120">Подробные сведения можно найти в разделе [Параметры групповой политики для Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="61c99-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="61c99-121">Обновления надстройки в Outlook "планирование"</span><span class="sxs-lookup"><span data-stu-id="61c99-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="61c99-122">Надстройка "собрание по сети" для Lync 2013 включает настройку приглашения на собрание и новые параметры собрания.</span><span class="sxs-lookup"><span data-stu-id="61c99-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="61c99-123">Администраторы могут настроить приглашения на собрание Организации, добавив собственный логотип, URL-адрес службы поддержки, URL-адрес юридического отказа или настраиваемый текст нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="61c99-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="61c99-124">Подробности можно найти в разделе [Настройка надстройки онлайн-собраний в Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="61c99-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="61c99-125">Новые элементы управления звуком участника позволяют организаторов по умолчанию планировать конференции, в которых в качестве звукового и видеоролика отключено звуковое сопровождение.</span><span class="sxs-lookup"><span data-stu-id="61c99-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="61c99-126">Надстройка инфраструктуры виртуальных рабочих столов</span><span class="sxs-lookup"><span data-stu-id="61c99-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="61c99-127">Клиент Lync 2013 теперь поддерживает звук и видео в среде инфраструктуры виртуальных рабочих столов (VDI).</span><span class="sxs-lookup"><span data-stu-id="61c99-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="61c99-128">Пользователь может подключить звуковое или видеоустройство (например, гарнитуру или камеру) к локальному компьютеру (например, на компьютере с тонким клиентом или переназначенным компьютером).</span><span class="sxs-lookup"><span data-stu-id="61c99-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="61c99-129">Пользователь может подключиться к виртуальной машине, войти в клиент Lync 2013, который запущен на виртуальной машине, и принять участие в голосовой и видеосвязи в режиме реального времени, как будто клиент запущен на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="61c99-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="61c99-130">В среде виртуальных рабочих столов поддерживаются следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="61c99-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="61c99-131">Интеграция устройств для звуковых и видеофайлов, включая указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="61c99-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="61c99-132">Звонки на элементы управления с устройства</span><span class="sxs-lookup"><span data-stu-id="61c99-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="61c99-133">Интеграция присутствия на устройстве</span><span class="sxs-lookup"><span data-stu-id="61c99-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="61c99-134">Поддержка нескольких HID (устройств с видеоинтерфейсом)</span><span class="sxs-lookup"><span data-stu-id="61c99-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="61c99-135">Поддержка местоположения и экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="61c99-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="61c99-136">Поддержка всех модальностей Lync, включая обмен мгновенными сообщениями, аудио, видео, общий доступ к приложениям, общий доступ к рабочему столу, общий доступ к PowerPoint, доску и передачу файлов.</span><span class="sxs-lookup"><span data-stu-id="61c99-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="61c99-137">Поддержка аудио-и видеосвязи в видеозвонках и звонках между пользователями и конференциями.</span><span class="sxs-lookup"><span data-stu-id="61c99-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="61c99-138">Сведения о том, как развертывать плагины VDI, приведены [в разделе Развертывание плагина LYNC VDI в Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="61c99-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="61c99-139">Улучшенные возможности видео</span><span class="sxs-lookup"><span data-stu-id="61c99-139">Video Enhancements</span></span>

<span data-ttu-id="61c99-140">Несколько новых функций значительно улучшают качество видео для участников Конференции.</span><span class="sxs-lookup"><span data-stu-id="61c99-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="61c99-141">Видео Улучшено с обнаружением и интеллектуальным формированием, чтобы видеоролики находились по центру в кадре.</span><span class="sxs-lookup"><span data-stu-id="61c99-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="61c99-142">Видео с высокой степенью четкости теперь поддерживается при звонках с двух сторон и на многосторонние конференции.</span><span class="sxs-lookup"><span data-stu-id="61c99-142">High-definition video is now supported in two-party calls and multiparty conferences.</span></span> <span data-ttu-id="61c99-143">Пользователи могут столкнуться с разрешениями до HD 1080P.</span><span class="sxs-lookup"><span data-stu-id="61c99-143">Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="61c99-144">Участники могут выбирать из разных макетов собрания: в представлении коллекции отображаются изображения и видео всех участников; В режиме докладчика отображается содержимое собрания, а также видео или изображение текущего динамика. В представлении "Презентация" отображается только содержимое собрания; Компактный вид: только элементы управления собранием.</span><span class="sxs-lookup"><span data-stu-id="61c99-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="61c99-145">С помощью новой функции коллекции участники могут одновременно просматривать несколько видеоканалов.</span><span class="sxs-lookup"><span data-stu-id="61c99-145">With the new Gallery feature, participants can see multiple video feeds at the same time.</span></span> <span data-ttu-id="61c99-146">Если на Конференции установлено более пяти участников собрания, в верхней строке появляются видеоканалы только самых активных участников, а для других участников — рисунки.</span><span class="sxs-lookup"><span data-stu-id="61c99-146">If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="61c99-147">Участники могут использовать закрепление видео, чтобы выбрать один или несколько доступных видеоканалов, чтобы они были видны всегда.</span><span class="sxs-lookup"><span data-stu-id="61c99-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="61c99-148">Выступающие могут использовать функцию "видео в центре внимания" для выбора видеоканала одного пользователя, чтобы каждый участник собрания мог видеть только этот участник.</span><span class="sxs-lookup"><span data-stu-id="61c99-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="61c99-149">Интеграция с комнатой чата</span><span class="sxs-lookup"><span data-stu-id="61c99-149">Chat Room Integration</span></span>

<span data-ttu-id="61c99-150">В Lync 2013 теперь интегрируются функции, ранее предоставленные приложением Lync 2010 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="61c99-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="61c99-151">Отдельный клиент группового чата больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="61c99-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="61c99-152">В Lync 2013 пользователи могут выполнять поиск комнат чатов, добавлять комнаты чата в их контакты, отслеживать действия в комнате чата, а также читать и публиковать сообщения.</span><span class="sxs-lookup"><span data-stu-id="61c99-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="61c99-153">Пользователи могут создавать тематические веб-каналы таким образом, чтобы они могли получать уведомления, если пользователь в одной из комнат чатов добавляет запись с определенными ключевыми словами.</span><span class="sxs-lookup"><span data-stu-id="61c99-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="61c99-154">С помощью новой страницы параметров **сохраняемого чата** пользователи могут настраивать уведомления и звуки, которые применяются при размещении сообщений в комнатах чатов.</span><span class="sxs-lookup"><span data-stu-id="61c99-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="61c99-155">Обновления Lync Web App</span><span class="sxs-lookup"><span data-stu-id="61c99-155">Lync Web App Updates</span></span>

<span data-ttu-id="61c99-156">Lync Web App — это веб-клиент конференции для Lync Server 2013 для собраний.</span><span class="sxs-lookup"><span data-stu-id="61c99-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="61c99-157">В этом выпуске Добавление звуковых и видеофайлов в Lync Web App обеспечивает полную работу в собрании для всех пользователей, которые не установили на локальном компьютере клиента Lync.</span><span class="sxs-lookup"><span data-stu-id="61c99-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="61c99-158">Участники собраний имеют доступ ко всем функциональным возможностям совместной работы и общего доступа, а выступающие — к элементам управления собранием.</span><span class="sxs-lookup"><span data-stu-id="61c99-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="61c99-159">Если пользователь попытается присоединиться к собранию, но у него нет установленного на компьютере клиента, откроется приложение Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="61c99-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="61c99-160">Если вы хотите разрешить другим параметрам присоединиться к собранию, вы можете настроить страницу присоединения к собранию; Ознакомьтесь со статьей [Настройка присоединения к собранию в Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="61c99-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="61c99-161">Из-за улучшений в Lync Web App обновленная версия участника недоступна для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61c99-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="61c99-162">Lync Web App — это клиент выбора для участников за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="61c99-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="61c99-163">Установка локального клиента не требуется, несмотря на то, что для настройки звука, видео и общего пользования требуется установка плагина при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="61c99-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="61c99-164">Обновления Lync 2013 для мобильных клиентов</span><span class="sxs-lookup"><span data-stu-id="61c99-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="61c99-165">Помимо улучшенных возможностей присутствия, контактов и обмена мгновенными сообщениями, мобильные клиенты Lync 2013 теперь предоставляют возможность голосовой и видеосвязи через Интернет и подключения к сотовым каналам данных.</span><span class="sxs-lookup"><span data-stu-id="61c99-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="61c99-166">Выбрав ссылку на собрание в элементе календаря, мобильные пользователи смогут присоединиться к голосовым и видеособраниям Lync.</span><span class="sxs-lookup"><span data-stu-id="61c99-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="61c99-167">Дополнительные сведения о мобильных клиентах Lync 2013 можно найти [в разделе Планирование мобильных клиентов в Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="61c99-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="61c99-168">Обновления пользовательского интерфейса Lync 2013</span><span class="sxs-lookup"><span data-stu-id="61c99-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="61c99-169">Обновления специальных возможностей</span><span class="sxs-lookup"><span data-stu-id="61c99-169">Accessibility Updates</span></span>

<span data-ttu-id="61c99-170">Lync 2013 включает несколько новых функций специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="61c99-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="61c99-171">Lync 2013 поддерживает высокое разрешение DPI, позволяя пользователям масштабировать текст и рисунки в 125% и 150% точек на дюйм.</span><span class="sxs-lookup"><span data-stu-id="61c99-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="61c99-172">Lync обеспечивает поддержку высокой контрастности, чтобы пользовательский интерфейс оставался полнофункциональным при использовании с темами высокой контрастности в Windows.</span><span class="sxs-lookup"><span data-stu-id="61c99-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="61c99-173">Lync поддерживает более 100 сочетаний клавиш, чтобы пользователи могли получать доступ к важным функциям без мыши.</span><span class="sxs-lookup"><span data-stu-id="61c99-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="61c99-174">Например, пользователь может нажать клавиши ALT + C, чтобы выполнить звонок, или ALT + I, чтобы проигнорировать его без необходимости табуляции или установки фокуса.</span><span class="sxs-lookup"><span data-stu-id="61c99-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="61c99-175">Нажатие (Alt + Q) завершает звонок, (Ctrl + N) запускает OneNote, а (Alt + т) открывает меню Сервис.</span><span class="sxs-lookup"><span data-stu-id="61c99-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="61c99-176">Расширенная поддержка средства чтения с экрана в Lync 2013 обеспечивает чтение вслух всех уведомлений, входящих запросов и мгновенных сообщений при включенном средстве чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="61c99-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="61c99-177">Присутствие при совместном доступе</span><span class="sxs-lookup"><span data-stu-id="61c99-177">Presence While Sharing</span></span>

<span data-ttu-id="61c99-178">Если Lync обнаруживает, что пользователь предоставляет общий доступ, Lync автоматически назначает пользователю представление о присутствии.</span><span class="sxs-lookup"><span data-stu-id="61c99-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="61c99-179">Это состояние блокирует все входящие сообщения, если отправителю не назначены параметры конфиденциальности Рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="61c99-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="61c99-180">Если пользователь полностью использует функцию общего доступа на дополнительном мониторе, Lync не назначает состояние присутствия для представления.</span><span class="sxs-lookup"><span data-stu-id="61c99-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="61c99-181">Обновления окна беседы</span><span class="sxs-lookup"><span data-stu-id="61c99-181">Conversation Window Updates</span></span>

<span data-ttu-id="61c99-182">Переработанное окно беседы обеспечивает более быстрый доступ к важным функциям.</span><span class="sxs-lookup"><span data-stu-id="61c99-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="61c99-183">С помощью новой функции бесед с вкладками пользователи смогут сохранять все свои комнаты общения и чата в одном окне беседы.</span><span class="sxs-lookup"><span data-stu-id="61c99-183">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window.</span></span> <span data-ttu-id="61c99-184">Вкладки в левой части окна беседы позволяют пользователям быстро переходить между всеми активными беседами.</span><span class="sxs-lookup"><span data-stu-id="61c99-184">The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="61c99-185">Пользователи могут открывать отдельные беседы в отдельном окне, а затем изменять размер окна.</span><span class="sxs-lookup"><span data-stu-id="61c99-185">Users can pop out an individual conversation into a separate window, and then resize the window.</span></span> <span data-ttu-id="61c99-186">Они также могут вернуть окно в главное окно беседы.</span><span class="sxs-lookup"><span data-stu-id="61c99-186">They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="61c99-187">Lync 2013 повторно открывает беседы пользователя, когда пользователь выходит из приложения, а затем снова входит в Lync.</span><span class="sxs-lookup"><span data-stu-id="61c99-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="61c99-188">Пользователи могут быстро добавлять мгновенные сообщения, видео, программы общего доступа к рабочему столу и средства веб-конференций (доска, заметки к собранию, общие записные книжки и вложения) в любую беседу.</span><span class="sxs-lookup"><span data-stu-id="61c99-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="61c99-189">В собрании, где размещается видео или контент, пользователи могут открыть видео собрания или общее содержимое, а затем изменить размер окна.</span><span class="sxs-lookup"><span data-stu-id="61c99-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="61c99-190">Обновления главного окна Lync</span><span class="sxs-lookup"><span data-stu-id="61c99-190">Lync Main Window Updates</span></span>

<span data-ttu-id="61c99-191">Новый упрощенный вид содержит знакомые функции, такие как " **что происходит сегодня?** ", "Выбор состояния" и "Настройка выбора **местоположения** ".</span><span class="sxs-lookup"><span data-stu-id="61c99-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="61c99-192">Если включены комнаты чата, пользователи видят новый значок " **комнаты чата** " на главной странице Lync.</span><span class="sxs-lookup"><span data-stu-id="61c99-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="61c99-193">С помощью значка **комнаты чата** пользователи могут быстро получить доступ к своим комнатам и фильтрам чатов.</span><span class="sxs-lookup"><span data-stu-id="61c99-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="61c99-194">Пользователи могут щелкнуть значок представления, чтобы перейти к представлению " **Контакты** ", " **комнаты чата** ", " **беседы** " или " **Телефон** ".</span><span class="sxs-lookup"><span data-stu-id="61c99-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="61c99-195">Если пользователи были перенесены в Exchange 2013, они могут отправить фотографию с высоким разрешением.</span><span class="sxs-lookup"><span data-stu-id="61c99-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="61c99-196">Сведения о представлениях "Контакты" и "карточка контакта"</span><span class="sxs-lookup"><span data-stu-id="61c99-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="61c99-197">Lync 2013 предоставляет пользователям различные способы просмотра контактов и групп в представлении " **Контакты** ".</span><span class="sxs-lookup"><span data-stu-id="61c99-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="61c99-198">Благодаря новому единому хранилищу контактов после того как контакты Lync пользователей будут перенесены в Exchange 2013, пользователи смогут получать доступ к своим контактам и управлять ими из Lync 2013, Outlook или Outlook Web App, а их избранные элементы остаются синхронизированными.</span><span class="sxs-lookup"><span data-stu-id="61c99-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="61c99-199">Например, если пользователь добавляет контакт в список "Избранное" в Outlook, этот контакт появится в группе "Избранное" в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="61c99-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="61c99-200">Если вы добавили и настроили прокси-сервер КСМПП и шлюз КСМПП, пользователи смогут добавлять контакты из партнеров на основе КСМПП для обмена мгновенными сообщениями и их присутствия.</span><span class="sxs-lookup"><span data-stu-id="61c99-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="61c99-201">Новый **контакт, который не является членом моей организации,** дает пользователям простой способ добавить пользователей, которые являются внешними по отношению к Организации.</span><span class="sxs-lookup"><span data-stu-id="61c99-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="61c99-202">Новая группа **"Избранное"** позволяет пользователям создавать список пользователей, которым часто обращаются чаще всего для быстрого доступа.</span><span class="sxs-lookup"><span data-stu-id="61c99-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="61c99-203">Пользователи могут выбрать способ сортировки и отображения контактов с помощью новых параметров **списка контактов** .</span><span class="sxs-lookup"><span data-stu-id="61c99-203">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts.</span></span> <span data-ttu-id="61c99-204">Пользователи могут выбрать развернутое представление с двумя строками, в котором отображаются рисунки контактов или сжатое однострочное представление.</span><span class="sxs-lookup"><span data-stu-id="61c99-204">Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view.</span></span> <span data-ttu-id="61c99-205">Пользователи также могут сортировать контакты в алфавитном порядке или по доступности.</span><span class="sxs-lookup"><span data-stu-id="61c99-205">Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="61c99-206">Обновления конференций</span><span class="sxs-lookup"><span data-stu-id="61c99-206">Conferencing Updates</span></span>

<span data-ttu-id="61c99-207">В Lync 2013 есть несколько улучшений функций для проведения конференций.</span><span class="sxs-lookup"><span data-stu-id="61c99-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="61c99-208">В зависимости от типа собрания пользователи могут теперь отключиться от аудитории и разрешить или заблокировать доступ к видео при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="61c99-208">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting.</span></span> <span data-ttu-id="61c99-209">Эти параметры доступны на странице **параметры собрания** и рекомендуются для крупных собраний с более чем 20 собеседниками.</span><span class="sxs-lookup"><span data-stu-id="61c99-209">These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="61c99-210">Простое использование элементов управления звуком в комнате для собраний позволяет пользователю управлять параметрами звука, например включить или отключить звук, изменить устройство и т. д.</span><span class="sxs-lookup"><span data-stu-id="61c99-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="61c99-211">При совместном доступе к программам пользователи могут выбрать несколько программ для совместного использования, если требуется работать с несколькими программами.</span><span class="sxs-lookup"><span data-stu-id="61c99-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="61c99-212">Теперь пользователи могут отправлять презентации, содержащие видеоклипы, отправив файл PowerPoint и наведя указатель мыши на слайд, чтобы отобразить элементы управления видео, такие как воспроизведение, пауза и звуковые элементы управления.</span><span class="sxs-lookup"><span data-stu-id="61c99-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="61c99-213">В ходе собрания пользователи могут объединять другую открытую беседу в собрании с помощью команды **объединить этот звонок** в меню **дополнительных параметров** (**...**).</span><span class="sxs-lookup"><span data-stu-id="61c99-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="61c99-214">Чтобы просмотреть имена участников, пользователи могут навести указатель мыши на кнопку **просмотреть участников** или выбрать команду **Показать список участников** , чтобы закрепить панель на собрании.</span><span class="sxs-lookup"><span data-stu-id="61c99-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="61c99-215">В зависимости от типа собрания пользователи могут выбирать из нескольких разных представлений контента и участников.</span><span class="sxs-lookup"><span data-stu-id="61c99-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="61c99-216">Записи собраний автоматически сохраняются в формате, воспроизводимом в проигрывателе Windows Media (MP4).</span><span class="sxs-lookup"><span data-stu-id="61c99-216">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4).</span></span> <span data-ttu-id="61c99-217">Пользователи могут легко предоставить общий доступ к файлу любому пользователю или воспользоваться функцией **публикации** в диспетчере записи, чтобы опубликовать запись в общем расположении.</span><span class="sxs-lookup"><span data-stu-id="61c99-217">Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="61c99-218">OneNote обеспечивает новые способы совместной работы на собрании.</span><span class="sxs-lookup"><span data-stu-id="61c99-218">OneNote enables new ways to collaborate in a meeting.</span></span> <span data-ttu-id="61c99-219">Во время собрания пользователи могут делать заметки в OneNote для личного использования после собрания, а также использовать общие записные книжки и совместное редактирование с участниками собрания в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="61c99-219">During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time.</span></span> <span data-ttu-id="61c99-220">Все участники группы могут получить доступ к общим заметкам для получения информации, идей мозгового штурма или использования страниц записной книжки в качестве виртуальной доски.</span><span class="sxs-lookup"><span data-stu-id="61c99-220">All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard.</span></span> <span data-ttu-id="61c99-221">Люди и контент, к которым предоставлен общий доступ в собрании, автоматически добавляются к заметкам.</span><span class="sxs-lookup"><span data-stu-id="61c99-221">People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="61c99-222">Пользователи могут переключаться между типами контента с помощью функции " **общий доступ к контенту и ведущим собраниям** " в нижней части комнаты для собраний.</span><span class="sxs-lookup"><span data-stu-id="61c99-222">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room.</span></span> <span data-ttu-id="61c99-223">Пользователи также могут использовать меню " **Управление содержимым для показа** ", чтобы выбрать содержимое, к которому нужно предоставить общий доступ.</span><span class="sxs-lookup"><span data-stu-id="61c99-223">Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="61c99-224">См. также</span><span class="sxs-lookup"><span data-stu-id="61c99-224">See Also</span></span>


[<span data-ttu-id="61c99-225">Планирование для клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61c99-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

