---
title: Использование файлов журналов для устранения неполадок в Microsoft Teams
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 7ad44af297cdfe375f28485e1c4c4e223f616666
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012195"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="3225d-103">Использование файлов журналов для устранения неполадок в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3225d-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="3225d-104">Существует три типа журналов, создаваемых клиентом автоматически, которые облегчают устранение неполадок в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3225d-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="3225d-105">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="3225d-105">Debug logs</span></span>

-   <span data-ttu-id="3225d-106">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="3225d-106">Media logs</span></span>

-   <span data-ttu-id="3225d-107">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="3225d-107">Desktop logs</span></span>

<span data-ttu-id="3225d-108">При обращении в службу поддержки нужно предоставить журналы отладки.</span><span class="sxs-lookup"><span data-stu-id="3225d-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="3225d-109">Это позволит Майкрософт быстро начать работу по устранению данной проблемы.</span><span class="sxs-lookup"><span data-stu-id="3225d-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="3225d-110">Журналы мультимедиа и рабочие журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3225d-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="3225d-111">Следующая таблица описывает различные клиенты и соответствующие журналы.</span><span class="sxs-lookup"><span data-stu-id="3225d-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="3225d-112">Расположение файлов журналов зависит от клиента и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="3225d-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="3225d-113">Клиент</span><span class="sxs-lookup"><span data-stu-id="3225d-113">Client</span></span> |<span data-ttu-id="3225d-114">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="3225d-114">Debug</span></span>|<span data-ttu-id="3225d-115">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="3225d-115">Desktop</span></span>|<span data-ttu-id="3225d-116">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="3225d-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="3225d-117">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="3225d-117">Web</span></span>    |<span data-ttu-id="3225d-118">X</span><span class="sxs-lookup"><span data-stu-id="3225d-118">X</span></span>         |-         |-         |
|<span data-ttu-id="3225d-119">Windows</span><span class="sxs-lookup"><span data-stu-id="3225d-119">Windows</span></span>     |<span data-ttu-id="3225d-120">X</span><span class="sxs-lookup"><span data-stu-id="3225d-120">X</span></span>         |<span data-ttu-id="3225d-121">X</span><span class="sxs-lookup"><span data-stu-id="3225d-121">X</span></span>         |<span data-ttu-id="3225d-122">X</span><span class="sxs-lookup"><span data-stu-id="3225d-122">X</span></span>         |
|<span data-ttu-id="3225d-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="3225d-123">Mac OSX</span></span>     |<span data-ttu-id="3225d-124">X</span><span class="sxs-lookup"><span data-stu-id="3225d-124">X</span></span>         |<span data-ttu-id="3225d-125">X</span><span class="sxs-lookup"><span data-stu-id="3225d-125">X</span></span>         |<span data-ttu-id="3225d-126">X</span><span class="sxs-lookup"><span data-stu-id="3225d-126">X</span></span>         |
|<span data-ttu-id="3225d-127">Linux</span><span class="sxs-lookup"><span data-stu-id="3225d-127">Linux</span></span>     |<span data-ttu-id="3225d-128">X</span><span class="sxs-lookup"><span data-stu-id="3225d-128">X</span></span>         |<span data-ttu-id="3225d-129">X</span><span class="sxs-lookup"><span data-stu-id="3225d-129">X</span></span>         |<span data-ttu-id="3225d-130">X</span><span class="sxs-lookup"><span data-stu-id="3225d-130">X</span></span>         |
|<span data-ttu-id="3225d-131">iOS</span><span class="sxs-lookup"><span data-stu-id="3225d-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="3225d-132">Android</span><span class="sxs-lookup"><span data-stu-id="3225d-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="3225d-133">Полный список поддерживаемых операционных систем и браузеров см. в статье [Работа с клиентами для Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="3225d-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="3225d-134">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="3225d-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="3225d-135">Это наиболее распространенные журналы, которые требуются при любом обращении в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3225d-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="3225d-136">Журналы отладки создаются клиентами для настольных систем Windows и Mac, а также клиентами на базе браузера.</span><span class="sxs-lookup"><span data-stu-id="3225d-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="3225d-137">Эти журналы имеют текстовый формат, а читать их следует снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="3225d-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="3225d-138">Открыть их можно в любом текстовом редакторе. Новые журналы создаются при входе в клиент.</span><span class="sxs-lookup"><span data-stu-id="3225d-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="3225d-139">Журналы отладки показывают следующие потоки данных:</span><span class="sxs-lookup"><span data-stu-id="3225d-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="3225d-140">Вход</span><span class="sxs-lookup"><span data-stu-id="3225d-140">Login</span></span>

-   <span data-ttu-id="3225d-141">Запросы на подключение к службам среднего уровня</span><span class="sxs-lookup"><span data-stu-id="3225d-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="3225d-142">Звонок/беседа</span><span class="sxs-lookup"><span data-stu-id="3225d-142">Call/conversation</span></span>

<span data-ttu-id="3225d-143">Процедура создания этих журналов зависит от используемой операционной системы:</span><span class="sxs-lookup"><span data-stu-id="3225d-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="3225d-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="3225d-144">Windows:</span></span>

      <span data-ttu-id="3225d-145">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="3225d-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="3225d-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="3225d-146">Mac OSX:</span></span>

      <span data-ttu-id="3225d-147">Сочетание клавиш: OPTION+COMMAND+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="3225d-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="3225d-148">Linux</span><span class="sxs-lookup"><span data-stu-id="3225d-148">Linux:</span></span>

      <span data-ttu-id="3225d-149">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="3225d-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="3225d-150">Журналы отладки автоматически скачиваются в указанные ниже папки.</span><span class="sxs-lookup"><span data-stu-id="3225d-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="3225d-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="3225d-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="3225d-152">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="3225d-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="3225d-153">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="3225d-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="3225d-154">Браузер: вам будет предложено сохранить журнал отладки в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3225d-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="3225d-155">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="3225d-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="3225d-156">Журналы мультимедиа содержат диагностические данные о звуке, видео и демонстрации экрана.</span><span class="sxs-lookup"><span data-stu-id="3225d-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="3225d-157">При обращении в службу поддержки они предоставляются по отдельному запросу и анализируются только сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3225d-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="3225d-158">Расположение журналов указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="3225d-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="3225d-159">Клиент</span><span class="sxs-lookup"><span data-stu-id="3225d-159">Client</span></span> |<span data-ttu-id="3225d-160">Расположение</span><span class="sxs-lookup"><span data-stu-id="3225d-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="3225d-161">Windows</span><span class="sxs-lookup"><span data-stu-id="3225d-161">Windows</span></span>     |<span data-ttu-id="3225d-162">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="3225d-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="3225d-163">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="3225d-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="3225d-164">%appdata%\Microsoft\Teams\media-stack \\ \*. ETL</span><span class="sxs-lookup"><span data-stu-id="3225d-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="3225d-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="3225d-165">Mac OSX</span></span>     |<span data-ttu-id="3225d-166">~/Library/Application Support support/Microsoft/Teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="3225d-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="3225d-167">~/Library/Application Support support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="3225d-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="3225d-168">Linux</span><span class="sxs-lookup"><span data-stu-id="3225d-168">Linux</span></span>       |<span data-ttu-id="3225d-169">~/.config/Microsoft/Microsoft Teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="3225d-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="3225d-170">~/.config/Microsoft/Microsoft Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="3225d-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="3225d-171">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="3225d-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="3225d-172">Рабочие журналы, также называемые журналами начального загрузчика, регистрируют данные, передаваемые между классическим клиентом и браузером.</span><span class="sxs-lookup"><span data-stu-id="3225d-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="3225d-173">Как и журналы мультимедиа, эти журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3225d-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="3225d-174">Журналы имеют текстовый формат, открываются в любом текстовом редакторе и читаются сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="3225d-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="3225d-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="3225d-175">Windows:</span></span>

1.  <span data-ttu-id="3225d-176">Щелкните правой кнопкой мыши значок **Microsoft Teams** в области уведомлений и выберите пункт **получить журналы** .</span><span class="sxs-lookup"><span data-stu-id="3225d-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="3225d-177">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="3225d-177">Mac OsX:</span></span>

1.  <span data-ttu-id="3225d-178">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="3225d-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="3225d-179">Linux</span><span class="sxs-lookup"><span data-stu-id="3225d-179">Linux:</span></span>

1.  <span data-ttu-id="3225d-180">На панели задач нажмите значок **Microsoft Teams** , а затем выберите команду **получить журналы** .</span><span class="sxs-lookup"><span data-stu-id="3225d-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="3225d-181">Клиент</span><span class="sxs-lookup"><span data-stu-id="3225d-181">Client</span></span> |<span data-ttu-id="3225d-182">Расположение</span><span class="sxs-lookup"><span data-stu-id="3225d-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="3225d-183">Windows</span><span class="sxs-lookup"><span data-stu-id="3225d-183">Windows</span></span>     |<span data-ttu-id="3225d-184">% AppData% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="3225d-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="3225d-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="3225d-185">Mac OSX</span></span>     |<span data-ttu-id="3225d-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="3225d-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="3225d-187">Linux</span><span class="sxs-lookup"><span data-stu-id="3225d-187">Linux</span></span>       |<span data-ttu-id="3225d-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="3225d-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |
