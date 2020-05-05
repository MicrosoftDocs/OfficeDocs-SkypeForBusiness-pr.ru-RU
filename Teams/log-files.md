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
ms.openlocfilehash: 2c8da7e60e785d765e77e17935b60382e864a83b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833379"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="810fe-103">Использование файлов журналов для устранения неполадок в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="810fe-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="810fe-104">Существует три типа журналов, создаваемых клиентом автоматически, которые облегчают устранение неполадок в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="810fe-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="810fe-105">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="810fe-105">Debug logs</span></span>

-   <span data-ttu-id="810fe-106">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="810fe-106">Media logs</span></span>

-   <span data-ttu-id="810fe-107">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="810fe-107">Desktop logs</span></span>

<span data-ttu-id="810fe-108">При обращении в службу поддержки нужно предоставить журналы отладки.</span><span class="sxs-lookup"><span data-stu-id="810fe-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="810fe-109">Это позволит Майкрософт быстро начать работу по устранению данной проблемы.</span><span class="sxs-lookup"><span data-stu-id="810fe-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="810fe-110">Журналы мультимедиа и рабочие журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="810fe-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="810fe-111">Следующая таблица описывает различные клиенты и соответствующие журналы.</span><span class="sxs-lookup"><span data-stu-id="810fe-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="810fe-112">Расположение файлов журналов зависит от клиента и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="810fe-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="810fe-113">Клиент</span><span class="sxs-lookup"><span data-stu-id="810fe-113">Client</span></span> |<span data-ttu-id="810fe-114">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="810fe-114">Debug</span></span>|<span data-ttu-id="810fe-115">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="810fe-115">Desktop</span></span>|<span data-ttu-id="810fe-116">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="810fe-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="810fe-117">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="810fe-117">Web</span></span>    |<span data-ttu-id="810fe-118">X</span><span class="sxs-lookup"><span data-stu-id="810fe-118">X</span></span>         |-         |-         |
|<span data-ttu-id="810fe-119">Windows</span><span class="sxs-lookup"><span data-stu-id="810fe-119">Windows</span></span>     |<span data-ttu-id="810fe-120">X</span><span class="sxs-lookup"><span data-stu-id="810fe-120">X</span></span>         |<span data-ttu-id="810fe-121">X</span><span class="sxs-lookup"><span data-stu-id="810fe-121">X</span></span>         |<span data-ttu-id="810fe-122">X</span><span class="sxs-lookup"><span data-stu-id="810fe-122">X</span></span>         |
|<span data-ttu-id="810fe-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="810fe-123">Mac OSX</span></span>     |<span data-ttu-id="810fe-124">X</span><span class="sxs-lookup"><span data-stu-id="810fe-124">X</span></span>         |<span data-ttu-id="810fe-125">X</span><span class="sxs-lookup"><span data-stu-id="810fe-125">X</span></span>         |<span data-ttu-id="810fe-126">X</span><span class="sxs-lookup"><span data-stu-id="810fe-126">X</span></span>         |
|<span data-ttu-id="810fe-127">iOS</span><span class="sxs-lookup"><span data-stu-id="810fe-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="810fe-128">Android</span><span class="sxs-lookup"><span data-stu-id="810fe-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="810fe-129">Полный список поддерживаемых операционных систем и браузеров см. в статье [Работа с клиентами для Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="810fe-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="810fe-130">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="810fe-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="810fe-131">Это наиболее распространенные журналы, которые требуются при любом обращении в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="810fe-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="810fe-132">Журналы отладки создаются клиентами для настольных систем Windows и Mac, а также клиентами на базе браузера.</span><span class="sxs-lookup"><span data-stu-id="810fe-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="810fe-133">Эти журналы имеют текстовый формат, а читать их следует снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="810fe-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="810fe-134">Открыть их можно в любом текстовом редакторе. Новые журналы создаются при входе в клиент.</span><span class="sxs-lookup"><span data-stu-id="810fe-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="810fe-135">Журналы отладки показывают следующие потоки данных:</span><span class="sxs-lookup"><span data-stu-id="810fe-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="810fe-136">Вход</span><span class="sxs-lookup"><span data-stu-id="810fe-136">Login</span></span>

-   <span data-ttu-id="810fe-137">Запросы на подключение к службам среднего уровня</span><span class="sxs-lookup"><span data-stu-id="810fe-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="810fe-138">Звонок/беседа</span><span class="sxs-lookup"><span data-stu-id="810fe-138">Call/conversation</span></span>

<span data-ttu-id="810fe-139">Процедура создания этих журналов зависит от используемой операционной системы:</span><span class="sxs-lookup"><span data-stu-id="810fe-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="810fe-140">Windows:</span><span class="sxs-lookup"><span data-stu-id="810fe-140">Windows:</span></span>

      <span data-ttu-id="810fe-141">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="810fe-141">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="810fe-142">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="810fe-142">Mac OSX:</span></span>

      <span data-ttu-id="810fe-143">Сочетание клавиш: OPTION+COMMAND+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="810fe-143">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="810fe-144">Журналы отладки автоматически скачиваются в указанные ниже папки.</span><span class="sxs-lookup"><span data-stu-id="810fe-144">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="810fe-145">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="810fe-145">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="810fe-146">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="810fe-146">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="810fe-147">Браузер: вам будет предложено сохранить журнал отладки в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="810fe-147">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="810fe-148">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="810fe-148">Media Logs</span></span>
---------------------------

<span data-ttu-id="810fe-149">Журналы мультимедиа содержат диагностические данные о звуке, видео и демонстрации экрана.</span><span class="sxs-lookup"><span data-stu-id="810fe-149">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="810fe-150">При обращении в службу поддержки они предоставляются по отдельному запросу и анализируются только сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="810fe-150">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="810fe-151">Расположение журналов указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="810fe-151">The following table outlines the log location.</span></span>


|<span data-ttu-id="810fe-152">Клиент</span><span class="sxs-lookup"><span data-stu-id="810fe-152">Client</span></span> |<span data-ttu-id="810fe-153">Расположение</span><span class="sxs-lookup"><span data-stu-id="810fe-153">Location</span></span> |
|---------|---------|
|<span data-ttu-id="810fe-154">Windows</span><span class="sxs-lookup"><span data-stu-id="810fe-154">Windows</span></span>     |<span data-ttu-id="810fe-155">%appdata%\Microsoft\Teams\media-stack\\*. blog</span><span class="sxs-lookup"><span data-stu-id="810fe-155">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="810fe-156">%appdata%\Microsoft\Teams\skylib\\*. blog</span><span class="sxs-lookup"><span data-stu-id="810fe-156">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="810fe-157">%appdata%\Microsoft\Teams\media-stack\\*. ETL</span><span class="sxs-lookup"><span data-stu-id="810fe-157">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="810fe-158">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="810fe-158">Mac OSX</span></span>     |<span data-ttu-id="810fe-159">~/Library/Application Support support/Microsoft/Teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="810fe-159">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="810fe-160">~/Library/Application Support support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="810fe-160">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="810fe-161">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="810fe-161">Desktop logs</span></span>
---------------------

<span data-ttu-id="810fe-162">Рабочие журналы, также называемые журналами начального загрузчика, регистрируют данные, передаваемые между классическим клиентом и браузером.</span><span class="sxs-lookup"><span data-stu-id="810fe-162">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="810fe-163">Как и журналы мультимедиа, эти журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="810fe-163">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="810fe-164">Журналы имеют текстовый формат, открываются в любом текстовом редакторе и читаются сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="810fe-164">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="810fe-165">Windows:</span><span class="sxs-lookup"><span data-stu-id="810fe-165">Windows:</span></span>

1.  <span data-ttu-id="810fe-166">щелкните правой кнопкой мыши **значок Microsoft Teams в** области приложений и выберите **Получить журналы**</span><span class="sxs-lookup"><span data-stu-id="810fe-166">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

<span data-ttu-id="810fe-167">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="810fe-167">Mac OsX:</span></span>

1.  <span data-ttu-id="810fe-168">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="810fe-168">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

|<span data-ttu-id="810fe-169">Клиент</span><span class="sxs-lookup"><span data-stu-id="810fe-169">Client</span></span> |<span data-ttu-id="810fe-170">Расположение</span><span class="sxs-lookup"><span data-stu-id="810fe-170">Location</span></span> |
|---------|---------|
|<span data-ttu-id="810fe-171">Windows</span><span class="sxs-lookup"><span data-stu-id="810fe-171">Windows</span></span>     |<span data-ttu-id="810fe-172">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="810fe-172">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="810fe-173">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="810fe-173">Mac OSX</span></span>     |<span data-ttu-id="810fe-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="810fe-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
