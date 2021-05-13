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
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337746"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="e19bf-103">Использование файлов журнала для отслеживания и устранения неполадок Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e19bf-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="e19bf-104">Клиент автоматически получает файлы журналов трех типов, которые можно использовать для отслеживания и устранения неполадок Teams.</span><span class="sxs-lookup"><span data-stu-id="e19bf-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="e19bf-105">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="e19bf-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="e19bf-106">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e19bf-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="e19bf-107">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="e19bf-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="e19bf-108">В этой статье описаны три журнала и их использования.</span><span class="sxs-lookup"><span data-stu-id="e19bf-108">This article describes the three logs and how they are used.</span></span> 

<span data-ttu-id="e19bf-109">Сведения об устранении конкретных проблем см. в Teams [устранении неполадок.](/MicrosoftTeams/troubleshoot/teams)</span><span class="sxs-lookup"><span data-stu-id="e19bf-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="e19bf-110">Сведения о том, как обратиться в службу поддержки, см. в [этой теме.](/microsoft-365/business-video/get-help-support)</span><span class="sxs-lookup"><span data-stu-id="e19bf-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span>

<span data-ttu-id="e19bf-111">При обращении в службу поддержки нужно предоставить журналы отладки.</span><span class="sxs-lookup"><span data-stu-id="e19bf-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="e19bf-112">Наличие журнала отладки перед созданием запроса на поддержку позволит корпорации Майкрософт быстро приступить к устранению проблемы.</span><span class="sxs-lookup"><span data-stu-id="e19bf-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="e19bf-113">**Журналы** **мультимедиа и** рабочего стола требуются только при запросе корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e19bf-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="e19bf-114">В этой статье под термином **Журналы отладки** относятся журналы, используемые для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="e19bf-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="e19bf-115">Однако в именах файлов, созданных для этих журналов, будут **содержаться** журналы диагностики терминов.</span><span class="sxs-lookup"><span data-stu-id="e19bf-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="e19bf-116">В следующей таблице описаны различные клиенты и связанные с ними журналы.</span><span class="sxs-lookup"><span data-stu-id="e19bf-116">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="e19bf-117">Расположение файлов журналов зависит от клиента и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e19bf-117">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="e19bf-118">Клиент</span><span class="sxs-lookup"><span data-stu-id="e19bf-118">Client</span></span> |<span data-ttu-id="e19bf-119">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="e19bf-119">Debug</span></span>|<span data-ttu-id="e19bf-120">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="e19bf-120">Desktop</span></span>|<span data-ttu-id="e19bf-121">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e19bf-121">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="e19bf-122">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="e19bf-122">Web</span></span>    |<span data-ttu-id="e19bf-123">X</span><span class="sxs-lookup"><span data-stu-id="e19bf-123">X</span></span>         |-         |-         |
|<span data-ttu-id="e19bf-124">Windows</span><span class="sxs-lookup"><span data-stu-id="e19bf-124">Windows</span></span>     |<span data-ttu-id="e19bf-125">X</span><span class="sxs-lookup"><span data-stu-id="e19bf-125">X</span></span>         |<span data-ttu-id="e19bf-126">X</span><span class="sxs-lookup"><span data-stu-id="e19bf-126">X</span></span>         |<span data-ttu-id="e19bf-127">X</span><span class="sxs-lookup"><span data-stu-id="e19bf-127">X</span></span>         |
|<span data-ttu-id="e19bf-128">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e19bf-128">Mac OSX</span></span>     |<span data-ttu-id="e19bf-129">X</span><span class="sxs-lookup"><span data-stu-id="e19bf-129">X</span></span>         |<span data-ttu-id="e19bf-130">X</span><span class="sxs-lookup"><span data-stu-id="e19bf-130">X</span></span>         |<span data-ttu-id="e19bf-131">X</span><span class="sxs-lookup"><span data-stu-id="e19bf-131">X</span></span>         |
|<span data-ttu-id="e19bf-132">Linux</span><span class="sxs-lookup"><span data-stu-id="e19bf-132">Linux</span></span>     |<span data-ttu-id="e19bf-133">X</span><span class="sxs-lookup"><span data-stu-id="e19bf-133">X</span></span>         |<span data-ttu-id="e19bf-134">X</span><span class="sxs-lookup"><span data-stu-id="e19bf-134">X</span></span>         |<span data-ttu-id="e19bf-135">X</span><span class="sxs-lookup"><span data-stu-id="e19bf-135">X</span></span>         |
|<span data-ttu-id="e19bf-136">iOS</span><span class="sxs-lookup"><span data-stu-id="e19bf-136">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="e19bf-137">Android</span><span class="sxs-lookup"><span data-stu-id="e19bf-137">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="e19bf-138">Полный список поддерживаемых операционных систем и браузеров см. в статье [Работа с клиентами для Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e19bf-138">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="e19bf-139">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="e19bf-139">Debug logs</span></span>

<span data-ttu-id="e19bf-140">Это наиболее распространенные журналы, которые требуются при любом обращении в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e19bf-140">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="e19bf-141">Журналы отлагки выпускаются классическими клиентами Windows и Mac, а также клиентами, основанными на браузерах.</span><span class="sxs-lookup"><span data-stu-id="e19bf-141">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="e19bf-142">Журналы основаны на тексте и читают их снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="e19bf-142">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="e19bf-143">Их можно читать в любом текстовом редакторе, и при входе в клиент создаются новые журналы.</span><span class="sxs-lookup"><span data-stu-id="e19bf-143">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="e19bf-144">Журналы отладки показывают следующие потоки данных:</span><span class="sxs-lookup"><span data-stu-id="e19bf-144">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="e19bf-145">Вход</span><span class="sxs-lookup"><span data-stu-id="e19bf-145">Login</span></span>

-   <span data-ttu-id="e19bf-146">Запросы на подключение к службам среднего уровня</span><span class="sxs-lookup"><span data-stu-id="e19bf-146">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="e19bf-147">Звонок/беседа</span><span class="sxs-lookup"><span data-stu-id="e19bf-147">Call/conversation</span></span>

<span data-ttu-id="e19bf-148">Журналы от debug используются следующими способами:</span><span class="sxs-lookup"><span data-stu-id="e19bf-148">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="e19bf-149">Windows:</span><span class="sxs-lookup"><span data-stu-id="e19bf-149">Windows:</span></span>

      <span data-ttu-id="e19bf-150">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="e19bf-150">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="e19bf-151">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="e19bf-151">Mac OSX:</span></span>

      <span data-ttu-id="e19bf-152">Сочетание клавиш: OPTION+COMMAND+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="e19bf-152">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="e19bf-153">Linux:</span><span class="sxs-lookup"><span data-stu-id="e19bf-153">Linux:</span></span>

      <span data-ttu-id="e19bf-154">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="e19bf-154">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="e19bf-155">Журналы отключки автоматически загружаются в следующие папки:</span><span class="sxs-lookup"><span data-stu-id="e19bf-155">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="e19bf-156">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="e19bf-156">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="e19bf-157">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="e19bf-157">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="e19bf-158">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="e19bf-158">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="e19bf-159">Браузер: вам будет предложено сохранить журнал отладки в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e19bf-159">Browser: You will be prompted to save the debug log to default save location</span></span>

## <a name="media-logs"></a><span data-ttu-id="e19bf-160">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e19bf-160">Media logs</span></span>

<span data-ttu-id="e19bf-161">Журналы мультимедиа содержат диагностические данные о звуке, видео и совместном использовании экрана Teams собраниях.</span><span class="sxs-lookup"><span data-stu-id="e19bf-161">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="e19bf-162">Они необходимы для случаев поддержки, связанных с вопросами, связанными со звонками.</span><span class="sxs-lookup"><span data-stu-id="e19bf-162">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="e19bf-163">По умолчанию ведение журнала мультимедиа отключено.</span><span class="sxs-lookup"><span data-stu-id="e19bf-163">Media logging is turned off by default.</span></span> <span data-ttu-id="e19bf-164">Чтобы журнал диагностических данных Teams собраниях, пользователи должны включить параметр в Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="e19bf-164">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="e19bf-165">Перейдите **Параметры** общие , выберите включить ведение журнала для диагностики собраний  >   **(требуется** перезапуск Teams ), перезапустите Teams и воспроизводите проблему.</span><span class="sxs-lookup"><span data-stu-id="e19bf-165">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="e19bf-166">В таблице ниже описаны расположения журналов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e19bf-166">The following table outlines the media log locations.</span></span> <span data-ttu-id="e19bf-167">При отправке файлов журнала в службу поддержки Майкрософт проверьте временную рамку файлов журнала, чтобы журналы охватывают период времени, заданный при воспроизведении проблемы.</span><span class="sxs-lookup"><span data-stu-id="e19bf-167">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="e19bf-168">Клиент</span><span class="sxs-lookup"><span data-stu-id="e19bf-168">Client</span></span> |<span data-ttu-id="e19bf-169">Расположение</span><span class="sxs-lookup"><span data-stu-id="e19bf-169">Location</span></span> |
|---------|---------|
|<span data-ttu-id="e19bf-170">Windows</span><span class="sxs-lookup"><span data-stu-id="e19bf-170">Windows</span></span>     |<span data-ttu-id="e19bf-171">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="e19bf-171">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="e19bf-172">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="e19bf-172">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="e19bf-173">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="e19bf-173">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="e19bf-174">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e19bf-174">Mac OSX</span></span>     |<span data-ttu-id="e19bf-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e19bf-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="e19bf-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e19bf-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="e19bf-177">Linux</span><span class="sxs-lookup"><span data-stu-id="e19bf-177">Linux</span></span>       |<span data-ttu-id="e19bf-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e19bf-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="e19bf-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e19bf-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="e19bf-180">Ниже данная информация содержит созданные файлы журналов и содержащиеся в них сведения.</span><span class="sxs-lookup"><span data-stu-id="e19bf-180">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="e19bf-181">Имя файла журнала</span><span class="sxs-lookup"><span data-stu-id="e19bf-181">Log file name</span></span>  |<span data-ttu-id="e19bf-182">Описание</span><span class="sxs-lookup"><span data-stu-id="e19bf-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="e19bf-183">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="e19bf-183">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="e19bf-184">Содержит сведения, относящиеся к стеку мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e19bf-184">Contains information related to the media stack.</span></span> <span data-ttu-id="e19bf-185">К ним относятся состояние канала, например разрешение, используемая декодаторы и кодировки, а также количество отправленных и полученных кадров, а также состояние сеанса видео- и видеосвязи камеры и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="e19bf-185">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="e19bf-186">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="e19bf-186">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="e19bf-187">Записи сведений, связанных с действиями удаленного управления, таких как отметка времени при этом и указатель мыши.</span><span class="sxs-lookup"><span data-stu-id="e19bf-187">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="e19bf-188">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="e19bf-188">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="e19bf-189">Записи событий трассировки стека мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e19bf-189">Records media stack trace events.</span></span>         |
|<span data-ttu-id="e19bf-190">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="e19bf-190">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="e19bf-191">Содержит сведения, связанные с агентом мультимедиа, включая качество отрисовки.</span><span class="sxs-lookup"><span data-stu-id="e19bf-191">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="e19bf-192">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="e19bf-192">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="e19bf-193">Записи событий в API ts-calling.</span><span class="sxs-lookup"><span data-stu-id="e19bf-193">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="e19bf-194">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="e19bf-194">Desktop logs</span></span>

<span data-ttu-id="e19bf-195">Журналы рабочего стола, также известные как журналы загрузок, содержат данные журнала, которые происходят между клиентом для настольных компьютеров и браузером.</span><span class="sxs-lookup"><span data-stu-id="e19bf-195">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="e19bf-196">Как и журналы мультимедиа, эти журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e19bf-196">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="e19bf-197">Журналы основаны на тексте и могут быть прочитано в любом текстовом редакторе в формате сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="e19bf-197">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="e19bf-198">Windows:</span><span class="sxs-lookup"><span data-stu-id="e19bf-198">Windows:</span></span>

 - <span data-ttu-id="e19bf-199">Щелкните правой кнопкой мыши **значок** Microsoft Teams области задач и выберите **получить журналы.**</span><span class="sxs-lookup"><span data-stu-id="e19bf-199">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="e19bf-200">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="e19bf-200">Mac OsX:</span></span>

 - <span data-ttu-id="e19bf-201">В **меню Справка** **выберите** пункт Получить журналы.</span><span class="sxs-lookup"><span data-stu-id="e19bf-201">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="e19bf-202">Linux:</span><span class="sxs-lookup"><span data-stu-id="e19bf-202">Linux:</span></span>

 - <span data-ttu-id="e19bf-203">Щелкните **значок Microsoft Teams** области задач и выберите **Получить журналы**.</span><span class="sxs-lookup"><span data-stu-id="e19bf-203">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="e19bf-204">Клиент</span><span class="sxs-lookup"><span data-stu-id="e19bf-204">Client</span></span> |<span data-ttu-id="e19bf-205">Расположение</span><span class="sxs-lookup"><span data-stu-id="e19bf-205">Location</span></span> |
|---------|---------|
|<span data-ttu-id="e19bf-206">Windows</span><span class="sxs-lookup"><span data-stu-id="e19bf-206">Windows</span></span>     |<span data-ttu-id="e19bf-207">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="e19bf-207">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="e19bf-208">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e19bf-208">Mac OSX</span></span>     |<span data-ttu-id="e19bf-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="e19bf-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="e19bf-210">Linux</span><span class="sxs-lookup"><span data-stu-id="e19bf-210">Linux</span></span>       |<span data-ttu-id="e19bf-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="e19bf-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="browser-trace"></a><span data-ttu-id="e19bf-212">Трассировка браузера</span><span class="sxs-lookup"><span data-stu-id="e19bf-212">Browser trace</span></span>

<span data-ttu-id="e19bf-213">Для некоторых категорий ошибок служба поддержки Майкрософт может потребовать сбора трассировки браузера.</span><span class="sxs-lookup"><span data-stu-id="e19bf-213">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="e19bf-214">Эти сведения могут предоставлять важные сведения о состоянии клиента Teams в случае возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="e19bf-214">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="e19bf-215">Перед запуском трассировки браузера убедитесь, что вы уже Teams.</span><span class="sxs-lookup"><span data-stu-id="e19bf-215">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="e19bf-216">Это важно сделать перед началом трассировки, чтобы она не содержала конфиденциальных сведений о входе.</span><span class="sxs-lookup"><span data-stu-id="e19bf-216">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="e19bf-217">После того как вы выполните вставку, выберите одну из следующих ссылок( при необходимости для браузера) и выполните предоставленные действия.</span><span class="sxs-lookup"><span data-stu-id="e19bf-217">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="e19bf-218">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="e19bf-218">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="e19bf-219">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="e19bf-219">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="e19bf-220">Сафари</span><span class="sxs-lookup"><span data-stu-id="e19bf-220">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="e19bf-221">Firefox</span><span class="sxs-lookup"><span data-stu-id="e19bf-221">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="e19bf-222">В этом шаге замените все ссылки на портал Azure Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="e19bf-222">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="e19bf-223">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e19bf-223">Related topics</span></span>

[<span data-ttu-id="e19bf-224">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="e19bf-224">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
