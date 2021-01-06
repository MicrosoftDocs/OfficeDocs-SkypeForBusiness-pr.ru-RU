---
title: Использование файлов журналов для устранения неполадок в Microsoft Teams
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Сведения о журналах отладки, мультимедиа и рабочих журналах, создаваемых Microsoft Teams, их расположении и роли при устранении неполадок.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761097"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="60dda-103">Использование файлов журналов для устранения неполадок в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60dda-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="60dda-104">Существует три типа файлов журнала, автоматически отготовимых клиентом, которые можно использовать для устранения неполадок Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="60dda-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="60dda-105">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="60dda-105">Debug logs</span></span>

-   <span data-ttu-id="60dda-106">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="60dda-106">Media logs</span></span>

-   <span data-ttu-id="60dda-107">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="60dda-107">Desktop logs</span></span>

<span data-ttu-id="60dda-108">При обращении в службу поддержки нужно предоставить журналы отладки.</span><span class="sxs-lookup"><span data-stu-id="60dda-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="60dda-109">Наличие в службе отладки перед созданием запроса на поддержку позволит корпорации Майкрософт быстро приступить к устранению проблемы.</span><span class="sxs-lookup"><span data-stu-id="60dda-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="60dda-110">**Журналы** **мультимедиа и** рабочего стола требуются только при запросе корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="60dda-110">**Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="60dda-111">В этой статье термин **"журналы** отладки" относится к журналам, которые используются для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="60dda-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="60dda-112">Однако файлы, созданные для этих журналов, будут содержать **журналы** диагностики терминов в своих именах.</span><span class="sxs-lookup"><span data-stu-id="60dda-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="60dda-113">В таблице ниже описаны различные клиенты и связанные с ними журналы.</span><span class="sxs-lookup"><span data-stu-id="60dda-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="60dda-114">Расположение файлов журналов зависит от клиента и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="60dda-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="60dda-115">Клиент</span><span class="sxs-lookup"><span data-stu-id="60dda-115">Client</span></span> |<span data-ttu-id="60dda-116">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="60dda-116">Debug</span></span>|<span data-ttu-id="60dda-117">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="60dda-117">Desktop</span></span>|<span data-ttu-id="60dda-118">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="60dda-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="60dda-119">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="60dda-119">Web</span></span>    |<span data-ttu-id="60dda-120">X</span><span class="sxs-lookup"><span data-stu-id="60dda-120">X</span></span>         |-         |-         |
|<span data-ttu-id="60dda-121">Windows</span><span class="sxs-lookup"><span data-stu-id="60dda-121">Windows</span></span>     |<span data-ttu-id="60dda-122">X</span><span class="sxs-lookup"><span data-stu-id="60dda-122">X</span></span>         |<span data-ttu-id="60dda-123">X</span><span class="sxs-lookup"><span data-stu-id="60dda-123">X</span></span>         |<span data-ttu-id="60dda-124">X</span><span class="sxs-lookup"><span data-stu-id="60dda-124">X</span></span>         |
|<span data-ttu-id="60dda-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="60dda-125">Mac OSX</span></span>     |<span data-ttu-id="60dda-126">X</span><span class="sxs-lookup"><span data-stu-id="60dda-126">X</span></span>         |<span data-ttu-id="60dda-127">X</span><span class="sxs-lookup"><span data-stu-id="60dda-127">X</span></span>         |<span data-ttu-id="60dda-128">X</span><span class="sxs-lookup"><span data-stu-id="60dda-128">X</span></span>         |
|<span data-ttu-id="60dda-129">Linux</span><span class="sxs-lookup"><span data-stu-id="60dda-129">Linux</span></span>     |<span data-ttu-id="60dda-130">X</span><span class="sxs-lookup"><span data-stu-id="60dda-130">X</span></span>         |<span data-ttu-id="60dda-131">X</span><span class="sxs-lookup"><span data-stu-id="60dda-131">X</span></span>         |<span data-ttu-id="60dda-132">X</span><span class="sxs-lookup"><span data-stu-id="60dda-132">X</span></span>         |
|<span data-ttu-id="60dda-133">iOS</span><span class="sxs-lookup"><span data-stu-id="60dda-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="60dda-134">Android</span><span class="sxs-lookup"><span data-stu-id="60dda-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="60dda-135">Полный список поддерживаемых операционных систем и браузеров см. в статье [Работа с клиентами для Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="60dda-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="60dda-136">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="60dda-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="60dda-137">Это наиболее распространенные журналы, которые требуются при любом обращении в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="60dda-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="60dda-138">Журналы отлагки произведены классическими клиентами Windows и Mac, а также клиентами, основанными на браузерах.</span><span class="sxs-lookup"><span data-stu-id="60dda-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="60dda-139">Журналы основаны на тексте и читают их снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="60dda-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="60dda-140">Их можно читать в любом текстовом редакторе, и при входе в клиент создаются новые журналы.</span><span class="sxs-lookup"><span data-stu-id="60dda-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="60dda-141">Журналы отладки показывают следующие потоки данных:</span><span class="sxs-lookup"><span data-stu-id="60dda-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="60dda-142">Вход</span><span class="sxs-lookup"><span data-stu-id="60dda-142">Login</span></span>

-   <span data-ttu-id="60dda-143">Запросы на подключение к службам среднего уровня</span><span class="sxs-lookup"><span data-stu-id="60dda-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="60dda-144">Звонок/беседа</span><span class="sxs-lookup"><span data-stu-id="60dda-144">Call/conversation</span></span>

<span data-ttu-id="60dda-145">Журналы отлагки произведены следующими способами:</span><span class="sxs-lookup"><span data-stu-id="60dda-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="60dda-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="60dda-146">Windows:</span></span>

      <span data-ttu-id="60dda-147">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="60dda-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="60dda-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="60dda-148">Mac OSX:</span></span>

      <span data-ttu-id="60dda-149">Сочетание клавиш: OPTION+COMMAND+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="60dda-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="60dda-150">Linux:</span><span class="sxs-lookup"><span data-stu-id="60dda-150">Linux:</span></span>

      <span data-ttu-id="60dda-151">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="60dda-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="60dda-152">Журналы отключки автоматически загружаются в следующие папки:</span><span class="sxs-lookup"><span data-stu-id="60dda-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="60dda-153">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="60dda-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="60dda-154">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="60dda-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="60dda-155">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="60dda-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="60dda-156">Браузер: вам будет предложено сохранить журнал отладки в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="60dda-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="60dda-157">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="60dda-157">Media logs</span></span>
---------------------------

<span data-ttu-id="60dda-158">Журналы мультимедиа содержат диагностические данные о звуке, видео и совместном доступе к экрану в собраниях Teams.</span><span class="sxs-lookup"><span data-stu-id="60dda-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="60dda-159">Они необходимы для случаев поддержки, связанных с вопросами, связанными со звонками.</span><span class="sxs-lookup"><span data-stu-id="60dda-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="60dda-160">По умолчанию ведение журнала мультимедиа отключено.</span><span class="sxs-lookup"><span data-stu-id="60dda-160">Media logging is turned off by default.</span></span> <span data-ttu-id="60dda-161">Чтобы журнал диагностических данных для собраний Teams, пользователи должны включить этот параметр в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="60dda-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="60dda-162">Перейдите **в "Общие** параметры", выберите параметр "Включить ведение журнала для диагностики собраний" (требуется перезапуск  >   **Teams),** перезапустите Teams и воспроизводите проблему.</span><span class="sxs-lookup"><span data-stu-id="60dda-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="60dda-163">В таблице ниже описаны расположения журналов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="60dda-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="60dda-164">При отправке файлов журнала в службу поддержки Майкрософт проверьте временную по времени их записи, чтобы журналы охватить период времени, заданный при воспроизведении проблемы.</span><span class="sxs-lookup"><span data-stu-id="60dda-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="60dda-165">Клиент</span><span class="sxs-lookup"><span data-stu-id="60dda-165">Client</span></span> |<span data-ttu-id="60dda-166">Расположение</span><span class="sxs-lookup"><span data-stu-id="60dda-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="60dda-167">Windows</span><span class="sxs-lookup"><span data-stu-id="60dda-167">Windows</span></span>     |<span data-ttu-id="60dda-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="60dda-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="60dda-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="60dda-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="60dda-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="60dda-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="60dda-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="60dda-171">Mac OSX</span></span>     |<span data-ttu-id="60dda-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="60dda-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="60dda-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="60dda-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="60dda-174">Linux</span><span class="sxs-lookup"><span data-stu-id="60dda-174">Linux</span></span>       |<span data-ttu-id="60dda-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="60dda-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="60dda-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="60dda-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="60dda-177">Ниже данная информация содержит созданные файлы журнала и содержащиеся в них сведения.</span><span class="sxs-lookup"><span data-stu-id="60dda-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="60dda-178">Имя файла журнала</span><span class="sxs-lookup"><span data-stu-id="60dda-178">Log file name</span></span>  |<span data-ttu-id="60dda-179">Описание</span><span class="sxs-lookup"><span data-stu-id="60dda-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="60dda-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="60dda-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="60dda-181">Содержит сведения, относящиеся к стеку мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="60dda-181">Contains information related to the media stack.</span></span> <span data-ttu-id="60dda-182">К ним относятся состояние канала, такое как разрешение, используемые декодеры и кодировки, а также количество отправленных и полученных кадров, а также состояние сеанса видео- и видеосвязи (VBSS).</span><span class="sxs-lookup"><span data-stu-id="60dda-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="60dda-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="60dda-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="60dda-184">Записи сведений, связанных с действиями удаленного управления, таких как отметка времени, когда предоставляется управление, и сведения о указателе мыши.</span><span class="sxs-lookup"><span data-stu-id="60dda-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="60dda-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="60dda-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="60dda-186">Записи событий трассировки стека мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="60dda-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="60dda-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="60dda-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="60dda-188">Содержит сведения, связанные с агентом мультимедиа, включая качество отрисовки.</span><span class="sxs-lookup"><span data-stu-id="60dda-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="60dda-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="60dda-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="60dda-190">Записи событий в API ts-calling.</span><span class="sxs-lookup"><span data-stu-id="60dda-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="60dda-191">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="60dda-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="60dda-192">Журналы рабочего стола, также известные как журналы загрузок, содержат данные журнала, которые находятся между клиентом для настольных компьютеров и браузером.</span><span class="sxs-lookup"><span data-stu-id="60dda-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="60dda-193">Как и журналы мультимедиа, эти журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="60dda-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="60dda-194">Журналы основаны на тексте и могут быть прочитано в любом текстовом редакторе в формате сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="60dda-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="60dda-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="60dda-195">Windows:</span></span>

 - <span data-ttu-id="60dda-196">Щелкните правой кнопкой **мыши значок Microsoft Teams** в области задач и выберите "Получить **журналы".**</span><span class="sxs-lookup"><span data-stu-id="60dda-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="60dda-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="60dda-197">Mac OsX:</span></span>

 - <span data-ttu-id="60dda-198">В **меню "Справка"** **выберите** пункт "Получить журналы".</span><span class="sxs-lookup"><span data-stu-id="60dda-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="60dda-199">Linux:</span><span class="sxs-lookup"><span data-stu-id="60dda-199">Linux:</span></span>

 - <span data-ttu-id="60dda-200">Щелкните **значок Microsoft Teams** в области задач и выберите **"Получить журналы".**</span><span class="sxs-lookup"><span data-stu-id="60dda-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="60dda-201">Клиент</span><span class="sxs-lookup"><span data-stu-id="60dda-201">Client</span></span> |<span data-ttu-id="60dda-202">Расположение</span><span class="sxs-lookup"><span data-stu-id="60dda-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="60dda-203">Windows</span><span class="sxs-lookup"><span data-stu-id="60dda-203">Windows</span></span>     |<span data-ttu-id="60dda-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="60dda-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="60dda-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="60dda-205">Mac OSX</span></span>     |<span data-ttu-id="60dda-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="60dda-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="60dda-207">Linux</span><span class="sxs-lookup"><span data-stu-id="60dda-207">Linux</span></span>       |<span data-ttu-id="60dda-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="60dda-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="60dda-209">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="60dda-209">Related topics</span></span>

[<span data-ttu-id="60dda-210">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="60dda-210">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
