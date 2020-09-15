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
ms.openlocfilehash: 468f0f67743f7cd0e11ff28e4484f70a71af3b64
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766763"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="b5c96-103">Использование файлов журналов для устранения неполадок в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5c96-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="b5c96-104">Существует три типа журналов, создаваемых клиентом автоматически, которые облегчают устранение неполадок в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b5c96-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="b5c96-105">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="b5c96-105">Debug logs</span></span>

-   <span data-ttu-id="b5c96-106">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="b5c96-106">Media logs</span></span>

-   <span data-ttu-id="b5c96-107">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="b5c96-107">Desktop logs</span></span>

<span data-ttu-id="b5c96-108">При обращении в службу поддержки нужно предоставить журналы отладки.</span><span class="sxs-lookup"><span data-stu-id="b5c96-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="b5c96-109">Это позволит Майкрософт быстро начать работу по устранению данной проблемы.</span><span class="sxs-lookup"><span data-stu-id="b5c96-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="b5c96-110">Журналы мультимедиа и рабочие журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b5c96-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="b5c96-111">Следующая таблица описывает различные клиенты и соответствующие журналы.</span><span class="sxs-lookup"><span data-stu-id="b5c96-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="b5c96-112">Расположение файлов журналов зависит от клиента и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b5c96-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="b5c96-113">Клиент</span><span class="sxs-lookup"><span data-stu-id="b5c96-113">Client</span></span> |<span data-ttu-id="b5c96-114">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="b5c96-114">Debug</span></span>|<span data-ttu-id="b5c96-115">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="b5c96-115">Desktop</span></span>|<span data-ttu-id="b5c96-116">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="b5c96-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="b5c96-117">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="b5c96-117">Web</span></span>    |<span data-ttu-id="b5c96-118">X</span><span class="sxs-lookup"><span data-stu-id="b5c96-118">X</span></span>         |-         |-         |
|<span data-ttu-id="b5c96-119">Windows</span><span class="sxs-lookup"><span data-stu-id="b5c96-119">Windows</span></span>     |<span data-ttu-id="b5c96-120">X</span><span class="sxs-lookup"><span data-stu-id="b5c96-120">X</span></span>         |<span data-ttu-id="b5c96-121">X</span><span class="sxs-lookup"><span data-stu-id="b5c96-121">X</span></span>         |<span data-ttu-id="b5c96-122">X</span><span class="sxs-lookup"><span data-stu-id="b5c96-122">X</span></span>         |
|<span data-ttu-id="b5c96-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b5c96-123">Mac OSX</span></span>     |<span data-ttu-id="b5c96-124">X</span><span class="sxs-lookup"><span data-stu-id="b5c96-124">X</span></span>         |<span data-ttu-id="b5c96-125">X</span><span class="sxs-lookup"><span data-stu-id="b5c96-125">X</span></span>         |<span data-ttu-id="b5c96-126">X</span><span class="sxs-lookup"><span data-stu-id="b5c96-126">X</span></span>         |
|<span data-ttu-id="b5c96-127">Linux</span><span class="sxs-lookup"><span data-stu-id="b5c96-127">Linux</span></span>     |<span data-ttu-id="b5c96-128">X</span><span class="sxs-lookup"><span data-stu-id="b5c96-128">X</span></span>         |<span data-ttu-id="b5c96-129">X</span><span class="sxs-lookup"><span data-stu-id="b5c96-129">X</span></span>         |<span data-ttu-id="b5c96-130">X</span><span class="sxs-lookup"><span data-stu-id="b5c96-130">X</span></span>         |
|<span data-ttu-id="b5c96-131">iOS</span><span class="sxs-lookup"><span data-stu-id="b5c96-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="b5c96-132">Android</span><span class="sxs-lookup"><span data-stu-id="b5c96-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="b5c96-133">Полный список поддерживаемых операционных систем и браузеров см. в статье [Работа с клиентами для Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="b5c96-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="b5c96-134">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="b5c96-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="b5c96-135">Это наиболее распространенные журналы, которые требуются при любом обращении в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b5c96-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="b5c96-136">Журналы отладки создаются клиентами для настольных систем Windows и Mac, а также клиентами на базе браузера.</span><span class="sxs-lookup"><span data-stu-id="b5c96-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="b5c96-137">Эти журналы имеют текстовый формат, а читать их следует снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="b5c96-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="b5c96-138">Открыть их можно в любом текстовом редакторе. Новые журналы создаются при входе в клиент.</span><span class="sxs-lookup"><span data-stu-id="b5c96-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="b5c96-139">Журналы отладки показывают следующие потоки данных:</span><span class="sxs-lookup"><span data-stu-id="b5c96-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="b5c96-140">Вход</span><span class="sxs-lookup"><span data-stu-id="b5c96-140">Login</span></span>

-   <span data-ttu-id="b5c96-141">Запросы на подключение к службам среднего уровня</span><span class="sxs-lookup"><span data-stu-id="b5c96-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="b5c96-142">Звонок/беседа</span><span class="sxs-lookup"><span data-stu-id="b5c96-142">Call/conversation</span></span>

<span data-ttu-id="b5c96-143">Процедура создания этих журналов зависит от используемой операционной системы:</span><span class="sxs-lookup"><span data-stu-id="b5c96-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="b5c96-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="b5c96-144">Windows:</span></span>

      <span data-ttu-id="b5c96-145">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="b5c96-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="b5c96-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="b5c96-146">Mac OSX:</span></span>

      <span data-ttu-id="b5c96-147">Сочетание клавиш: OPTION+COMMAND+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="b5c96-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="b5c96-148">Linux</span><span class="sxs-lookup"><span data-stu-id="b5c96-148">Linux:</span></span>

      <span data-ttu-id="b5c96-149">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="b5c96-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="b5c96-150">Журналы отладки автоматически скачиваются в указанные ниже папки.</span><span class="sxs-lookup"><span data-stu-id="b5c96-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="b5c96-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="b5c96-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="b5c96-152">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="b5c96-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="b5c96-153">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="b5c96-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="b5c96-154">Браузер: вам будет предложено сохранить журнал отладки в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5c96-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="b5c96-155">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="b5c96-155">Media logs</span></span>
---------------------------

<span data-ttu-id="b5c96-156">Журналы мультимедиа содержат диагностические данные о звуке, видео и демонстрации экрана в собраниях Teams.</span><span class="sxs-lookup"><span data-stu-id="b5c96-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="b5c96-157">При обращении в службу поддержки они предоставляются по отдельному запросу и анализируются только сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b5c96-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> 

<span data-ttu-id="b5c96-158">Ведение журнала мультимедиа по умолчанию отключено.</span><span class="sxs-lookup"><span data-stu-id="b5c96-158">Media logging is turned off by default.</span></span> <span data-ttu-id="b5c96-159">Чтобы вести журнал диагностических данных для собраний Teams, пользователи должны включить параметр в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="b5c96-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="b5c96-160">Перейдите в раздел **Параметры**  >  **General**, установите флажок **включить ведение журнала для диагностики собраний (требуется перезапуск Teams**), а затем перезапустите Teams.</span><span class="sxs-lookup"><span data-stu-id="b5c96-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams.</span></span>

<span data-ttu-id="b5c96-161">В таблице ниже описаны места, в которых находятся журналы.</span><span class="sxs-lookup"><span data-stu-id="b5c96-161">The following table outlines the log locations.</span></span>

|<span data-ttu-id="b5c96-162">Клиент</span><span class="sxs-lookup"><span data-stu-id="b5c96-162">Client</span></span> |<span data-ttu-id="b5c96-163">Расположение</span><span class="sxs-lookup"><span data-stu-id="b5c96-163">Location</span></span> |
|---------|---------|
|<span data-ttu-id="b5c96-164">Windows</span><span class="sxs-lookup"><span data-stu-id="b5c96-164">Windows</span></span>     |<span data-ttu-id="b5c96-165">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="b5c96-165">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="b5c96-166">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="b5c96-166">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="b5c96-167">%appdata%\Microsoft\Teams\media-stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="b5c96-167">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="b5c96-168">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b5c96-168">Mac OSX</span></span>     |<span data-ttu-id="b5c96-169">~/Library/Application Support support/Microsoft/Teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b5c96-169">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="b5c96-170">~/Library/Application Support support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b5c96-170">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="b5c96-171">Linux</span><span class="sxs-lookup"><span data-stu-id="b5c96-171">Linux</span></span>       |<span data-ttu-id="b5c96-172">~/.config/Microsoft/Microsoft Teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b5c96-172">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="b5c96-173">~/.config/Microsoft/Microsoft Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b5c96-173">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="b5c96-174">Ниже приведен список созданных файлов журнала и сведений, которые они содержат.</span><span class="sxs-lookup"><span data-stu-id="b5c96-174">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="b5c96-175">Имя файла журнала</span><span class="sxs-lookup"><span data-stu-id="b5c96-175">Log file name</span></span>  |<span data-ttu-id="b5c96-176">Описание</span><span class="sxs-lookup"><span data-stu-id="b5c96-176">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b5c96-177">Teams. MSRTC-0-s1039525249. blog</span><span class="sxs-lookup"><span data-stu-id="b5c96-177">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="b5c96-178">Информация, относящаяся к комплекту носителей.</span><span class="sxs-lookup"><span data-stu-id="b5c96-178">Contains information related to the media stack.</span></span> <span data-ttu-id="b5c96-179">Сюда входит состояние канала, например разрешение, декодеры и используемые кодировщики, количество отправленных и полученных кадров, а также состояние сеанса демонстрации экрана (VBSS) на камере и видео.</span><span class="sxs-lookup"><span data-stu-id="b5c96-179">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="b5c96-180">rtmcontrol. MSRTC-0-2415069487. blog</span><span class="sxs-lookup"><span data-stu-id="b5c96-180">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="b5c96-181">Записываются сведения о действиях, связанных с удаленным управлением, например отметка времени для элемента управления, и указатель мыши.</span><span class="sxs-lookup"><span data-stu-id="b5c96-181">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="b5c96-182">Teams_MediaStackETW -2-U-xr-U. ETL</span><span class="sxs-lookup"><span data-stu-id="b5c96-182">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="b5c96-183">Записывает события трассировки стека мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="b5c96-183">Records media stack trace events.</span></span>         |
|<span data-ttu-id="b5c96-184">Отладка-0-s2790420889. blog</span><span class="sxs-lookup"><span data-stu-id="b5c96-184">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="b5c96-185">Содержит сведения, связанные с агентом мультимедиа, в том числе качество рендеринга.</span><span class="sxs-lookup"><span data-stu-id="b5c96-185">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="b5c96-186">tscalling-0-2061129496. blog</span><span class="sxs-lookup"><span data-stu-id="b5c96-186">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="b5c96-187">Записывает события в API-интерфейс, вызывающий TS.</span><span class="sxs-lookup"><span data-stu-id="b5c96-187">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="b5c96-188">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="b5c96-188">Desktop logs</span></span>
---------------------

<span data-ttu-id="b5c96-189">Рабочие журналы, также называемые журналами начального загрузчика, регистрируют данные, передаваемые между классическим клиентом и браузером.</span><span class="sxs-lookup"><span data-stu-id="b5c96-189">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="b5c96-190">Как и журналы мультимедиа, эти журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b5c96-190">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="b5c96-191">Журналы имеют текстовый формат, открываются в любом текстовом редакторе и читаются сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="b5c96-191">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="b5c96-192">Windows:</span><span class="sxs-lookup"><span data-stu-id="b5c96-192">Windows:</span></span>

1.  <span data-ttu-id="b5c96-193">Щелкните правой кнопкой мыши значок **Microsoft Teams** в области уведомлений и выберите пункт **получить журналы** .</span><span class="sxs-lookup"><span data-stu-id="b5c96-193">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="b5c96-194">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="b5c96-194">Mac OsX:</span></span>

1.  <span data-ttu-id="b5c96-195">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="b5c96-195">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="b5c96-196">Linux</span><span class="sxs-lookup"><span data-stu-id="b5c96-196">Linux:</span></span>

1.  <span data-ttu-id="b5c96-197">На панели задач нажмите значок **Microsoft Teams** , а затем выберите команду **получить журналы** .</span><span class="sxs-lookup"><span data-stu-id="b5c96-197">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="b5c96-198">Клиент</span><span class="sxs-lookup"><span data-stu-id="b5c96-198">Client</span></span> |<span data-ttu-id="b5c96-199">Расположение</span><span class="sxs-lookup"><span data-stu-id="b5c96-199">Location</span></span> |
|---------|---------|
|<span data-ttu-id="b5c96-200">Windows</span><span class="sxs-lookup"><span data-stu-id="b5c96-200">Windows</span></span>     |<span data-ttu-id="b5c96-201">% AppData% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="b5c96-201">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="b5c96-202">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b5c96-202">Mac OSX</span></span>     |<span data-ttu-id="b5c96-203">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="b5c96-203">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="b5c96-204">Linux</span><span class="sxs-lookup"><span data-stu-id="b5c96-204">Linux</span></span>       |<span data-ttu-id="b5c96-205">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="b5c96-205">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="b5c96-206">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b5c96-206">Related topics</span></span>

[<span data-ttu-id="b5c96-207">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="b5c96-207">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

