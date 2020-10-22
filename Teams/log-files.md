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
ms.openlocfilehash: 2ff24ddb8aaf63b539959119138aebf2f5d4e81f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650832"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="d3728-103">Использование файлов журналов для устранения неполадок в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3728-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="d3728-104">Существует три типа журналов, создаваемых клиентом автоматически, которые облегчают устранение неполадок в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d3728-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="d3728-105">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="d3728-105">Debug logs</span></span>

-   <span data-ttu-id="d3728-106">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d3728-106">Media logs</span></span>

-   <span data-ttu-id="d3728-107">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="d3728-107">Desktop logs</span></span>

<span data-ttu-id="d3728-108">При обращении в службу поддержки нужно предоставить журналы отладки.</span><span class="sxs-lookup"><span data-stu-id="d3728-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="d3728-109">Это позволит Майкрософт быстро начать работу по устранению данной проблемы.</span><span class="sxs-lookup"><span data-stu-id="d3728-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="d3728-110">Журналы мультимедиа и рабочие журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d3728-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="d3728-111">Следующая таблица описывает различные клиенты и соответствующие журналы.</span><span class="sxs-lookup"><span data-stu-id="d3728-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="d3728-112">Расположение файлов журналов зависит от клиента и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="d3728-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="d3728-113">Клиент</span><span class="sxs-lookup"><span data-stu-id="d3728-113">Client</span></span> |<span data-ttu-id="d3728-114">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="d3728-114">Debug</span></span>|<span data-ttu-id="d3728-115">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="d3728-115">Desktop</span></span>|<span data-ttu-id="d3728-116">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d3728-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="d3728-117">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="d3728-117">Web</span></span>    |<span data-ttu-id="d3728-118">X</span><span class="sxs-lookup"><span data-stu-id="d3728-118">X</span></span>         |-         |-         |
|<span data-ttu-id="d3728-119">Windows</span><span class="sxs-lookup"><span data-stu-id="d3728-119">Windows</span></span>     |<span data-ttu-id="d3728-120">X</span><span class="sxs-lookup"><span data-stu-id="d3728-120">X</span></span>         |<span data-ttu-id="d3728-121">X</span><span class="sxs-lookup"><span data-stu-id="d3728-121">X</span></span>         |<span data-ttu-id="d3728-122">X</span><span class="sxs-lookup"><span data-stu-id="d3728-122">X</span></span>         |
|<span data-ttu-id="d3728-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="d3728-123">Mac OSX</span></span>     |<span data-ttu-id="d3728-124">X</span><span class="sxs-lookup"><span data-stu-id="d3728-124">X</span></span>         |<span data-ttu-id="d3728-125">X</span><span class="sxs-lookup"><span data-stu-id="d3728-125">X</span></span>         |<span data-ttu-id="d3728-126">X</span><span class="sxs-lookup"><span data-stu-id="d3728-126">X</span></span>         |
|<span data-ttu-id="d3728-127">Linux</span><span class="sxs-lookup"><span data-stu-id="d3728-127">Linux</span></span>     |<span data-ttu-id="d3728-128">X</span><span class="sxs-lookup"><span data-stu-id="d3728-128">X</span></span>         |<span data-ttu-id="d3728-129">X</span><span class="sxs-lookup"><span data-stu-id="d3728-129">X</span></span>         |<span data-ttu-id="d3728-130">X</span><span class="sxs-lookup"><span data-stu-id="d3728-130">X</span></span>         |
|<span data-ttu-id="d3728-131">iOS</span><span class="sxs-lookup"><span data-stu-id="d3728-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="d3728-132">Android</span><span class="sxs-lookup"><span data-stu-id="d3728-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="d3728-133">Полный список поддерживаемых операционных систем и браузеров см. в статье [Работа с клиентами для Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="d3728-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="d3728-134">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="d3728-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="d3728-135">Это наиболее распространенные журналы, которые требуются при любом обращении в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d3728-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="d3728-136">Журналы отладки создаются клиентами для настольных систем Windows и Mac, а также клиентами на базе браузера.</span><span class="sxs-lookup"><span data-stu-id="d3728-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="d3728-137">Эти журналы имеют текстовый формат, а читать их следует снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="d3728-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="d3728-138">Открыть их можно в любом текстовом редакторе. Новые журналы создаются при входе в клиент.</span><span class="sxs-lookup"><span data-stu-id="d3728-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="d3728-139">Журналы отладки показывают следующие потоки данных:</span><span class="sxs-lookup"><span data-stu-id="d3728-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="d3728-140">Вход</span><span class="sxs-lookup"><span data-stu-id="d3728-140">Login</span></span>

-   <span data-ttu-id="d3728-141">Запросы на подключение к службам среднего уровня</span><span class="sxs-lookup"><span data-stu-id="d3728-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="d3728-142">Звонок/беседа</span><span class="sxs-lookup"><span data-stu-id="d3728-142">Call/conversation</span></span>

<span data-ttu-id="d3728-143">Процедура создания этих журналов зависит от используемой операционной системы:</span><span class="sxs-lookup"><span data-stu-id="d3728-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="d3728-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="d3728-144">Windows:</span></span>

      <span data-ttu-id="d3728-145">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="d3728-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="d3728-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="d3728-146">Mac OSX:</span></span>

      <span data-ttu-id="d3728-147">Сочетание клавиш: OPTION+COMMAND+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="d3728-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="d3728-148">Linux</span><span class="sxs-lookup"><span data-stu-id="d3728-148">Linux:</span></span>

      <span data-ttu-id="d3728-149">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="d3728-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="d3728-150">Журналы отладки автоматически скачиваются в указанные ниже папки.</span><span class="sxs-lookup"><span data-stu-id="d3728-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="d3728-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="d3728-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="d3728-152">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="d3728-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="d3728-153">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="d3728-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="d3728-154">Браузер: вам будет предложено сохранить журнал отладки в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3728-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="d3728-155">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d3728-155">Media logs</span></span>
---------------------------

<span data-ttu-id="d3728-156">Журналы мультимедиа содержат диагностические данные о звуке, видео и демонстрации экрана в собраниях Teams.</span><span class="sxs-lookup"><span data-stu-id="d3728-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="d3728-157">Они необходимы для обращений в службу поддержки, которые связаны с вопросами, связанными с вызовами.</span><span class="sxs-lookup"><span data-stu-id="d3728-157">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="d3728-158">Ведение журнала мультимедиа по умолчанию отключено.</span><span class="sxs-lookup"><span data-stu-id="d3728-158">Media logging is turned off by default.</span></span> <span data-ttu-id="d3728-159">Чтобы вести журнал диагностических данных для собраний Teams, пользователи должны включить параметр в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="d3728-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="d3728-160">Перейдите в раздел **Параметры**  >  **General**, установите флажок **включить ведение журнала для диагностики собраний (требуется перезапуск Teams**), а затем перезапустите Teams и воспроизведите ошибку.</span><span class="sxs-lookup"><span data-stu-id="d3728-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams and reproduce the issue.</span></span> 

<span data-ttu-id="d3728-161">В приведенной ниже таблице указаны расположения в журнале мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d3728-161">The following table outlines the media log locations.</span></span> <span data-ttu-id="d3728-162">При отправке файлов журнала в службу поддержки Майкрософт Проверьте отметки времени для файлов журнала, чтобы убедиться в том, что при воспроизведении ошибки журналы закрывают временный кадр.</span><span class="sxs-lookup"><span data-stu-id="d3728-162">When you send the log files to Microsoft support, please verify the timestamp of the log files to make sure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="d3728-163">Клиент</span><span class="sxs-lookup"><span data-stu-id="d3728-163">Client</span></span> |<span data-ttu-id="d3728-164">Расположение</span><span class="sxs-lookup"><span data-stu-id="d3728-164">Location</span></span> |
|---------|---------|
|<span data-ttu-id="d3728-165">Windows</span><span class="sxs-lookup"><span data-stu-id="d3728-165">Windows</span></span>     |<span data-ttu-id="d3728-166">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="d3728-166">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="d3728-167">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="d3728-167">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="d3728-168">%appdata%\Microsoft\Teams\media-stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="d3728-168">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="d3728-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="d3728-169">Mac OSX</span></span>     |<span data-ttu-id="d3728-170">~/Library/Application Support support/Microsoft/Teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="d3728-170">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="d3728-171">~/Library/Application Support support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="d3728-171">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="d3728-172">Linux</span><span class="sxs-lookup"><span data-stu-id="d3728-172">Linux</span></span>       |<span data-ttu-id="d3728-173">~/.config/Microsoft/Microsoft Teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="d3728-173">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="d3728-174">~/.config/Microsoft/Microsoft Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="d3728-174">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="d3728-175">Ниже приведен список созданных файлов журнала и сведений, которые они содержат.</span><span class="sxs-lookup"><span data-stu-id="d3728-175">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="d3728-176">Имя файла журнала</span><span class="sxs-lookup"><span data-stu-id="d3728-176">Log file name</span></span>  |<span data-ttu-id="d3728-177">Описание</span><span class="sxs-lookup"><span data-stu-id="d3728-177">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d3728-178">Teams. MSRTC-0-s1039525249. blog</span><span class="sxs-lookup"><span data-stu-id="d3728-178">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="d3728-179">Информация, относящаяся к комплекту носителей.</span><span class="sxs-lookup"><span data-stu-id="d3728-179">Contains information related to the media stack.</span></span> <span data-ttu-id="d3728-180">Сюда входит состояние канала, например разрешение, декодеры и используемые кодировщики, количество отправленных и полученных кадров, а также состояние сеанса демонстрации экрана (VBSS) на камере и видео.</span><span class="sxs-lookup"><span data-stu-id="d3728-180">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="d3728-181">rtmcontrol. MSRTC-0-2415069487. blog</span><span class="sxs-lookup"><span data-stu-id="d3728-181">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="d3728-182">Записываются сведения о действиях, связанных с удаленным управлением, например отметка времени для элемента управления, и указатель мыши.</span><span class="sxs-lookup"><span data-stu-id="d3728-182">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="d3728-183">Teams_MediaStackETW -2-U-xr-U. ETL</span><span class="sxs-lookup"><span data-stu-id="d3728-183">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="d3728-184">Записывает события трассировки стека мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d3728-184">Records media stack trace events.</span></span>         |
|<span data-ttu-id="d3728-185">Отладка-0-s2790420889. blog</span><span class="sxs-lookup"><span data-stu-id="d3728-185">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="d3728-186">Содержит сведения, связанные с агентом мультимедиа, в том числе качество рендеринга.</span><span class="sxs-lookup"><span data-stu-id="d3728-186">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="d3728-187">tscalling-0-2061129496. blog</span><span class="sxs-lookup"><span data-stu-id="d3728-187">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="d3728-188">Записывает события в API-интерфейс, вызывающий TS.</span><span class="sxs-lookup"><span data-stu-id="d3728-188">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="d3728-189">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="d3728-189">Desktop logs</span></span>
---------------------

<span data-ttu-id="d3728-190">Рабочие журналы, также называемые журналами начального загрузчика, регистрируют данные, передаваемые между классическим клиентом и браузером.</span><span class="sxs-lookup"><span data-stu-id="d3728-190">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="d3728-191">Как и журналы мультимедиа, эти журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d3728-191">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="d3728-192">Журналы имеют текстовый формат, открываются в любом текстовом редакторе и читаются сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="d3728-192">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="d3728-193">Windows:</span><span class="sxs-lookup"><span data-stu-id="d3728-193">Windows:</span></span>

1.  <span data-ttu-id="d3728-194">Щелкните правой кнопкой мыши значок **Microsoft Teams** в области уведомлений и выберите пункт **получить журналы** .</span><span class="sxs-lookup"><span data-stu-id="d3728-194">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="d3728-195">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="d3728-195">Mac OsX:</span></span>

1.  <span data-ttu-id="d3728-196">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="d3728-196">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="d3728-197">Linux</span><span class="sxs-lookup"><span data-stu-id="d3728-197">Linux:</span></span>

1.  <span data-ttu-id="d3728-198">На панели задач нажмите значок **Microsoft Teams** , а затем выберите команду **получить журналы** .</span><span class="sxs-lookup"><span data-stu-id="d3728-198">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="d3728-199">Клиент</span><span class="sxs-lookup"><span data-stu-id="d3728-199">Client</span></span> |<span data-ttu-id="d3728-200">Расположение</span><span class="sxs-lookup"><span data-stu-id="d3728-200">Location</span></span> |
|---------|---------|
|<span data-ttu-id="d3728-201">Windows</span><span class="sxs-lookup"><span data-stu-id="d3728-201">Windows</span></span>     |<span data-ttu-id="d3728-202">% AppData% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="d3728-202">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="d3728-203">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="d3728-203">Mac OSX</span></span>     |<span data-ttu-id="d3728-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="d3728-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="d3728-205">Linux</span><span class="sxs-lookup"><span data-stu-id="d3728-205">Linux</span></span>       |<span data-ttu-id="d3728-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="d3728-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="d3728-207">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d3728-207">Related topics</span></span>

[<span data-ttu-id="d3728-208">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="d3728-208">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
