---
title: Использование файлов журналов для устранения неполадок в Microsoft Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Узнайте о журналах отладки, мультимедиа и рабочего стола, которые были произведены Microsoft Teams, где их можно найти и как они могут помочь в мониторинге и устранении неполадок.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a18dbef0441055c1202c2b77ce4f8af87040e561
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689697"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="56ed1-103">Использование файлов журнала для отслеживания и устранения неполадок Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="56ed1-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="56ed1-104">Клиент автоматически получает файлы журналов трех типов, которые можно использовать для отслеживания и устранения неполадок Teams.</span><span class="sxs-lookup"><span data-stu-id="56ed1-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="56ed1-105">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="56ed1-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="56ed1-106">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="56ed1-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="56ed1-107">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="56ed1-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="56ed1-108">В этой статье описаны эти журналы и их использования.</span><span class="sxs-lookup"><span data-stu-id="56ed1-108">This article describes these logs and how they are used.</span></span> <span data-ttu-id="56ed1-109">Сведения об устранении конкретных проблем см. в Teams [устранении неполадок.](/MicrosoftTeams/troubleshoot/teams)</span><span class="sxs-lookup"><span data-stu-id="56ed1-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="56ed1-110">Сведения о том, как обратиться в службу поддержки, см. в [этой теме.](/microsoft-365/business-video/get-help-support)</span><span class="sxs-lookup"><span data-stu-id="56ed1-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span> <span data-ttu-id="56ed1-111">При обращении в службу поддержки нужно предоставить журналы отладки.</span><span class="sxs-lookup"><span data-stu-id="56ed1-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="56ed1-112">Наличие журнала отладки перед созданием запроса на поддержку позволит корпорации Майкрософт быстро приступить к устранению проблемы.</span><span class="sxs-lookup"><span data-stu-id="56ed1-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="56ed1-113">**Журналы** **мультимедиа и** рабочего стола требуются только при запросе корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="56ed1-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="56ed1-114">В этой статье под термином **Журналы отладки** относятся журналы, используемые для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="56ed1-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="56ed1-115">Однако в именах файлов, созданных для этих журналов, будут **содержаться** журналы диагностики терминов.</span><span class="sxs-lookup"><span data-stu-id="56ed1-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

## <a name="collect-and-enable-logging"></a><span data-ttu-id="56ed1-116">Сбор и включить ведение журнала</span><span class="sxs-lookup"><span data-stu-id="56ed1-116">Collect and enable logging</span></span>

<span data-ttu-id="56ed1-117">Важно собирать журналы сразу после возникновения проблемы.</span><span class="sxs-lookup"><span data-stu-id="56ed1-117">It’s important to collect logs as soon as an issue occurs.</span></span> <span data-ttu-id="56ed1-118">Журналы можно собрать всего несколькими щелчками мыши.</span><span class="sxs-lookup"><span data-stu-id="56ed1-118">The logs can be collected together with just a couple of clicks.</span></span>

<span data-ttu-id="56ed1-119">Windows: щелкните правой кнопкой мыши значок Teams в области задач и выберите **Сбор файлов поддержки**.</span><span class="sxs-lookup"><span data-stu-id="56ed1-119">Windows: Right-click on the Teams icon in the system tray and choose **Collect support files**.</span></span> 

<span data-ttu-id="56ed1-120">Mac: выберите меню Справка и выберите **Сбор файлов поддержки**.</span><span class="sxs-lookup"><span data-stu-id="56ed1-120">Mac: Select the Help menu and choose **Collect support files**.</span></span>

<span data-ttu-id="56ed1-121">Журналы от deug, Desktop и Media будут собраны в одной папке с именем MSTeams Diagnostics Log <local data and time> .</span><span class="sxs-lookup"><span data-stu-id="56ed1-121">Debug, Desktop, and Media logs will be collected in one folder with the name MSTeams Diagnostics Log <local data and time>.</span></span> <span data-ttu-id="56ed1-122">Эту папку можно сжать и использовать, когда вы открываете запрос в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="56ed1-122">This folder can be compressed and shared when you open a support request with Microsoft Support.</span></span> <span data-ttu-id="56ed1-123">Папка будет содержать папки "Рабочий стол", "Собрание (мультимедиа") и "Отложенный" (в Интернете).</span><span class="sxs-lookup"><span data-stu-id="56ed1-123">The folder will contain folders for Desktop, Meeting (Media), and Debug (web).</span></span> <span data-ttu-id="56ed1-124">Для сбора файлов можно использовать следующие сочетания клавиш:</span><span class="sxs-lookup"><span data-stu-id="56ed1-124">You can collect the files using the following keyboard shortcuts:</span></span>

<span data-ttu-id="56ed1-125">Windows: CRTL +ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="56ed1-125">Windows: Crtl + Alt + Shift + 1</span></span>

<span data-ttu-id="56ed1-126">Mac: OPTION+COMMAND+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="56ed1-126">Mac: Option + Command + Shift + 1</span></span>

<span data-ttu-id="56ed1-127">По умолчанию ведение журнала мультимедиа отключено.</span><span class="sxs-lookup"><span data-stu-id="56ed1-127">Media logging is turned off by default.</span></span> <span data-ttu-id="56ed1-128">Чтобы включить ведение журнала мультимедиа, пользователи должны включить этот параметр в Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="56ed1-128">To enable Media logging, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="56ed1-129">Перейдите **Параметры** общие и выберите Включить ведение журнала для диагностики собраний  >   **(требуется перезапуск Teams).**</span><span class="sxs-lookup"><span data-stu-id="56ed1-129">Go to **Settings** > **General**, and select **Enable logging for meeting diagnostics (requires restarting Teams)**.</span></span> <span data-ttu-id="56ed1-130">Чтобы Teams, необходимо перезапустить клиент.</span><span class="sxs-lookup"><span data-stu-id="56ed1-130">The Teams client must be restarted for logging to begin.</span></span>

> [!NOTE]
> <span data-ttu-id="56ed1-131">Если ведение журнала мультимедиа включено, в папку Собрание будут включены дополнительные файлы, необходимые для исследования проблем со звуком и видео.</span><span class="sxs-lookup"><span data-stu-id="56ed1-131">If Media logging is enabled, there will be additional files included in the Meeting folder which are necessary for investigating audio and video issues.</span></span> <span data-ttu-id="56ed1-132">Если ведение журнала мультимедиа не включено, будет доступно ограниченное количество журналов.</span><span class="sxs-lookup"><span data-stu-id="56ed1-132">If Media logging is not enabled, there will be a limited number of logs available.</span></span>

<span data-ttu-id="56ed1-133">В следующей таблице описаны различные клиенты и связанные с ними журналы.</span><span class="sxs-lookup"><span data-stu-id="56ed1-133">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="56ed1-134">Расположение файлов журналов зависит от клиента и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="56ed1-134">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="56ed1-135">Клиент</span><span class="sxs-lookup"><span data-stu-id="56ed1-135">Client</span></span> |<span data-ttu-id="56ed1-136">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="56ed1-136">Debug</span></span>|<span data-ttu-id="56ed1-137">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="56ed1-137">Desktop</span></span>|<span data-ttu-id="56ed1-138">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="56ed1-138">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="56ed1-139">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="56ed1-139">Web</span></span>    |<span data-ttu-id="56ed1-140">X</span><span class="sxs-lookup"><span data-stu-id="56ed1-140">X</span></span>         |-         |-         |
|<span data-ttu-id="56ed1-141">Windows</span><span class="sxs-lookup"><span data-stu-id="56ed1-141">Windows</span></span>     |<span data-ttu-id="56ed1-142">X</span><span class="sxs-lookup"><span data-stu-id="56ed1-142">X</span></span>         |<span data-ttu-id="56ed1-143">X</span><span class="sxs-lookup"><span data-stu-id="56ed1-143">X</span></span>         |<span data-ttu-id="56ed1-144">X</span><span class="sxs-lookup"><span data-stu-id="56ed1-144">X</span></span>         |
|<span data-ttu-id="56ed1-145">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="56ed1-145">Mac OSX</span></span>     |<span data-ttu-id="56ed1-146">X</span><span class="sxs-lookup"><span data-stu-id="56ed1-146">X</span></span>         |<span data-ttu-id="56ed1-147">X</span><span class="sxs-lookup"><span data-stu-id="56ed1-147">X</span></span>         |<span data-ttu-id="56ed1-148">X</span><span class="sxs-lookup"><span data-stu-id="56ed1-148">X</span></span>         |
|<span data-ttu-id="56ed1-149">Linux</span><span class="sxs-lookup"><span data-stu-id="56ed1-149">Linux</span></span>     |<span data-ttu-id="56ed1-150">X</span><span class="sxs-lookup"><span data-stu-id="56ed1-150">X</span></span>         |<span data-ttu-id="56ed1-151">X</span><span class="sxs-lookup"><span data-stu-id="56ed1-151">X</span></span>         |<span data-ttu-id="56ed1-152">X</span><span class="sxs-lookup"><span data-stu-id="56ed1-152">X</span></span>         |
|<span data-ttu-id="56ed1-153">iOS</span><span class="sxs-lookup"><span data-stu-id="56ed1-153">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="56ed1-154">Android</span><span class="sxs-lookup"><span data-stu-id="56ed1-154">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="56ed1-155">Полный список поддерживаемых операционных систем и браузеров см. в статье [Работа с клиентами для Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="56ed1-155">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="56ed1-156">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="56ed1-156">Debug logs</span></span>

<span data-ttu-id="56ed1-157">Инструкции _для Windows_ Mac см. в разделе Windows и включить ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="56ed1-157">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="56ed1-158">Журналы отлагки выпускаются классическими клиентами Windows и Mac, а также клиентами, основанными на браузерах.</span><span class="sxs-lookup"><span data-stu-id="56ed1-158">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="56ed1-159">Журналы основаны на тексте и читают их снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="56ed1-159">The logs are text-based and are read from the bottom-up.</span></span> <span data-ttu-id="56ed1-160">Их можно читать в любом текстовом редакторе, и при входе в клиент создаются новые журналы.</span><span class="sxs-lookup"><span data-stu-id="56ed1-160">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="56ed1-161">Журналы отладки показывают следующие потоки данных:</span><span class="sxs-lookup"><span data-stu-id="56ed1-161">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="56ed1-162">Вход</span><span class="sxs-lookup"><span data-stu-id="56ed1-162">Login</span></span>

-   <span data-ttu-id="56ed1-163">Запросы на подключение к службам среднего уровня</span><span class="sxs-lookup"><span data-stu-id="56ed1-163">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="56ed1-164">Звонок/беседа</span><span class="sxs-lookup"><span data-stu-id="56ed1-164">Call/conversation</span></span>

<span data-ttu-id="56ed1-165">Сбор журналов для Linux: сочетания клавиш CTRL+ALT+SHIFT+1 Файлы будут доступны в папке ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="56ed1-165">To collect logs for Linux: Keyboard shortcut: Ctrl + Alt + Shift + 1 The files will be available in ~/Downloads</span></span>

<span data-ttu-id="56ed1-166">Сбор журналов для браузера: сочетания клавиш: CRTL +ALT+SHIFT+1 Файлы будут доступны в папке %userprofile%\Downloads</span><span class="sxs-lookup"><span data-stu-id="56ed1-166">To collect logs for Browser: Keyboard shortcut: Crtl + Alt + Shift + 1 The files will be available in %userprofile%\Downloads</span></span>

## <a name="media-logs"></a><span data-ttu-id="56ed1-167">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="56ed1-167">Media logs</span></span>

<span data-ttu-id="56ed1-168">Инструкции _для Windows_ Mac см. в разделе Windows и включить ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="56ed1-168">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="56ed1-169">Журналы мультимедиа содержат диагностические данные о звуке, видео и совместном использовании экрана Teams собраниях.</span><span class="sxs-lookup"><span data-stu-id="56ed1-169">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="56ed1-170">Они необходимы для случаев поддержки, связанных с вопросами, связанными со звонками.</span><span class="sxs-lookup"><span data-stu-id="56ed1-170">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="56ed1-171">По умолчанию ведение журнала мультимедиа отключено.</span><span class="sxs-lookup"><span data-stu-id="56ed1-171">Media logging is turned off by default.</span></span> <span data-ttu-id="56ed1-172">Чтобы журнал диагностических данных Teams собраниях, пользователи должны включить параметр в Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="56ed1-172">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="56ed1-173">Перейдите **Параметры** общие , выберите включить ведение журнала для диагностики собраний  >   **(требуется** перезапуск Teams ), перезапустите Teams и воспроизводите проблему.</span><span class="sxs-lookup"><span data-stu-id="56ed1-173">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="56ed1-174">При отправке файлов журнала в службу поддержки Майкрософт проверьте временную рамку файлов журнала, чтобы журналы охватывают период времени, заданный при воспроизведении проблемы.</span><span class="sxs-lookup"><span data-stu-id="56ed1-174">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

<span data-ttu-id="56ed1-175">Сбор журналов для Linux. Файлы будут доступны в ~/.config/Microsoft/Microsoft Teams/media-stack/ .blog и *~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span><span class="sxs-lookup"><span data-stu-id="56ed1-175">To collect logs for Linux: The files will be available in ~/.config/Microsoft/Microsoft Teams/media-stack/*.blog and ~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span></span>

<span data-ttu-id="56ed1-176">Ниже данная информация содержит созданные файлы журналов и содержащиеся в них сведения.</span><span class="sxs-lookup"><span data-stu-id="56ed1-176">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="56ed1-177">Имя файла журнала</span><span class="sxs-lookup"><span data-stu-id="56ed1-177">Log file name</span></span>  |<span data-ttu-id="56ed1-178">Описание</span><span class="sxs-lookup"><span data-stu-id="56ed1-178">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="56ed1-179">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="56ed1-179">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="56ed1-180">Содержит сведения, относящиеся к стеку мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="56ed1-180">Contains information related to the media stack.</span></span> <span data-ttu-id="56ed1-181">К ним относятся состояние канала, например разрешение, используемая декодаторы и кодировки, а также количество отправленных и полученных кадров, а также состояние сеанса видео- и видеосвязи камеры и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="56ed1-181">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="56ed1-182">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="56ed1-182">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="56ed1-183">Записи сведений, связанных с действиями удаленного управления, таких как отметка времени при этом и указатель мыши.</span><span class="sxs-lookup"><span data-stu-id="56ed1-183">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="56ed1-184">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="56ed1-184">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="56ed1-185">Записи событий трассировки стека мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="56ed1-185">Records media stack trace events.</span></span>         |
|<span data-ttu-id="56ed1-186">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="56ed1-186">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="56ed1-187">Содержит сведения, связанные с агентом мультимедиа, включая качество отрисовки.</span><span class="sxs-lookup"><span data-stu-id="56ed1-187">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="56ed1-188">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="56ed1-188">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="56ed1-189">Записи событий в API ts-calling.</span><span class="sxs-lookup"><span data-stu-id="56ed1-189">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="56ed1-190">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="56ed1-190">Desktop logs</span></span>

<span data-ttu-id="56ed1-191">Инструкции _для Windows_ Mac см. в разделе Windows и включить ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="56ed1-191">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="56ed1-192">Журналы рабочего стола, также известные как журналы загрузок, содержат данные журнала, которые происходят между клиентом для настольных компьютеров и браузером.</span><span class="sxs-lookup"><span data-stu-id="56ed1-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="56ed1-193">Как и журналы мультимедиа, эти журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="56ed1-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="56ed1-194">Журналы основаны на тексте и могут быть прочитано в любом текстовом редакторе в формате сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="56ed1-194">The logs are text-based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="56ed1-195">Чтобы собрать журналы для Linux: щелкните значок Microsoft Teams в области задач и выберите **Получить журналы**.</span><span class="sxs-lookup"><span data-stu-id="56ed1-195">To collect logs for Linux: Click on the Microsoft Teams icon in your system tray, and select **Get Logs**.</span></span>
<span data-ttu-id="56ed1-196">Файлы будут доступны в папке ~/.config/Microsoft/Microsoft Teams/logs.txt.</span><span class="sxs-lookup"><span data-stu-id="56ed1-196">The files will be available in ~/.config/Microsoft/Microsoft Teams/logs.txt.</span></span>  


## <a name="browser-trace"></a><span data-ttu-id="56ed1-197">Трассировка браузера</span><span class="sxs-lookup"><span data-stu-id="56ed1-197">Browser trace</span></span>

<span data-ttu-id="56ed1-198">Для некоторых категорий ошибок служба поддержки Майкрософт может потребовать сбора трассировки браузера.</span><span class="sxs-lookup"><span data-stu-id="56ed1-198">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="56ed1-199">Эти сведения могут предоставлять важные сведения о состоянии клиента Teams в случае возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="56ed1-199">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="56ed1-200">Перед запуском трассировки браузера убедитесь, что вы уже Teams.</span><span class="sxs-lookup"><span data-stu-id="56ed1-200">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="56ed1-201">Это важно сделать перед началом трассировки, чтобы она не содержала конфиденциальных сведений о входе.</span><span class="sxs-lookup"><span data-stu-id="56ed1-201">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="56ed1-202">После того как вы выполните вставку, выберите одну из следующих ссылок( при необходимости для браузера) и выполните предоставленные действия.</span><span class="sxs-lookup"><span data-stu-id="56ed1-202">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="56ed1-203">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="56ed1-203">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="56ed1-204">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="56ed1-204">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="56ed1-205">Сафари</span><span class="sxs-lookup"><span data-stu-id="56ed1-205">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="56ed1-206">Firefox</span><span class="sxs-lookup"><span data-stu-id="56ed1-206">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="56ed1-207">В этом шаге замените все ссылки на портал Azure Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="56ed1-207">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="56ed1-208">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="56ed1-208">Related topics</span></span>

[<span data-ttu-id="56ed1-209">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="56ed1-209">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
