---
title: "Использование файлов журналов для устранения неполадок в Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о журналах отладки, мультимедиа и рабочих журналах, создаваемых Microsoft Teams, их расположении и роли при устранении неполадок."
appliesto:
- Microsoft Teams
ms.openlocfilehash: bef400cd5838848a0eb25f709e930611fac9ed6d
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="57488-103">Использование файлов журналов для устранения неполадок в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57488-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="57488-104">Существует три типа журналов, создаваемых клиентом автоматически, которые облегчают устранение неполадок в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="57488-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="57488-105">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="57488-105">Debug logs</span></span>

-   <span data-ttu-id="57488-106">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="57488-106">Media logs</span></span>

-   <span data-ttu-id="57488-107">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="57488-107">Desktop logs</span></span>

<span data-ttu-id="57488-108">При обращении в службу поддержки нужно предоставить журналы отладки.</span><span class="sxs-lookup"><span data-stu-id="57488-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="57488-109">Это позволит Майкрософт быстро начать работу по устранению данной проблемы.</span><span class="sxs-lookup"><span data-stu-id="57488-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="57488-110">Журналы мультимедиа и рабочие журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57488-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="57488-111">Следующая таблица описывает различные клиенты и соответствующие журналы.</span><span class="sxs-lookup"><span data-stu-id="57488-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="57488-112">Расположение файлов журналов зависит от клиента и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="57488-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="57488-113">Клиент</span><span class="sxs-lookup"><span data-stu-id="57488-113">Client</span></span> |<span data-ttu-id="57488-114">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="57488-114">Debug</span></span>|<span data-ttu-id="57488-115">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="57488-115">Desktop</span></span>|<span data-ttu-id="57488-116">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="57488-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="57488-117">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="57488-117">Web</span></span>    |<span data-ttu-id="57488-118">X</span><span class="sxs-lookup"><span data-stu-id="57488-118">X</span></span>         |-         |-         |
|<span data-ttu-id="57488-119">Windows</span><span class="sxs-lookup"><span data-stu-id="57488-119">Windows</span></span>     |<span data-ttu-id="57488-120">X</span><span class="sxs-lookup"><span data-stu-id="57488-120">X</span></span>         |<span data-ttu-id="57488-121">X</span><span class="sxs-lookup"><span data-stu-id="57488-121">X</span></span>         |<span data-ttu-id="57488-122">X</span><span class="sxs-lookup"><span data-stu-id="57488-122">X</span></span>         |
|<span data-ttu-id="57488-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="57488-123">Mac OSX</span></span>     |<span data-ttu-id="57488-124">X</span><span class="sxs-lookup"><span data-stu-id="57488-124">X</span></span>         |<span data-ttu-id="57488-125">X</span><span class="sxs-lookup"><span data-stu-id="57488-125">X</span></span>         |<span data-ttu-id="57488-126">X</span><span class="sxs-lookup"><span data-stu-id="57488-126">X</span></span>         |
|<span data-ttu-id="57488-127">iOS</span><span class="sxs-lookup"><span data-stu-id="57488-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="57488-128">Android</span><span class="sxs-lookup"><span data-stu-id="57488-128">Android</span></span>     |-         |-         |-         |
|<span data-ttu-id="57488-129">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="57488-129">Windows Phone</span></span>     |-         |-         |-         |

<span data-ttu-id="57488-130">Полный список поддерживаемых операционных систем и браузеров см. в [вопросах и ответах по Microsoft Teams](https://support.office.com/en-US/article/Frequently-asked-questions-about-Microsoft-Teams-%E2%80%93-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc).</span><span class="sxs-lookup"><span data-stu-id="57488-130">For a complete list of supported operating systems and browsers, reference the following [Microsoft Teams FAQ](https://support.office.com/en-US/article/Frequently-asked-questions-about-Microsoft-Teams-%E2%80%93-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc).</span></span>

<a name="debug-logs"></a><span data-ttu-id="57488-131">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="57488-131">Debug logs</span></span>
---------------------------

<span data-ttu-id="57488-132">Это наиболее распространенные журналы, которые требуются при любом обращении в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57488-132">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="57488-133">Они создаются классическими клиентами Windows и Mac, а также клиентами на основе браузеров.</span><span class="sxs-lookup"><span data-stu-id="57488-133">Debug logs are produced by the Window and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="57488-134">Эти журналы имеют текстовый формат, а читать их следует снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="57488-134">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="57488-135">Открыть их можно в любом текстовом редакторе. Новые журналы создаются при входе в клиент.</span><span class="sxs-lookup"><span data-stu-id="57488-135">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="57488-136">Журналы отладки показывают следующие потоки данных:</span><span class="sxs-lookup"><span data-stu-id="57488-136">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="57488-137">Вход</span><span class="sxs-lookup"><span data-stu-id="57488-137">Login</span></span>

-   <span data-ttu-id="57488-138">Запросы на подключение к службам среднего уровня</span><span class="sxs-lookup"><span data-stu-id="57488-138">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="57488-139">Звонок/беседа</span><span class="sxs-lookup"><span data-stu-id="57488-139">Call/conversation</span></span>

<span data-ttu-id="57488-140">Процедура создания этих журналов зависит от используемой операционной системы:</span><span class="sxs-lookup"><span data-stu-id="57488-140">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="57488-141">Windows:</span><span class="sxs-lookup"><span data-stu-id="57488-141">Windows:</span></span>

    1.  <span data-ttu-id="57488-142">щелкните правой кнопкой мыши **значок Microsoft Teams в** области приложений и выберите **Получить журналы**</span><span class="sxs-lookup"><span data-stu-id="57488-142">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="57488-143">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="57488-143">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="57488-144">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="57488-144">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="57488-145">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="57488-145">Mac OSX:</span></span>

    1.  <span data-ttu-id="57488-146">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="57488-146">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="57488-147">Сочетание клавиш: OPTION+COMMAND+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="57488-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="57488-148">Журналы отладки автоматически скачиваются в указанные ниже папки.</span><span class="sxs-lookup"><span data-stu-id="57488-148">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="57488-149">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="57488-149">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="57488-150">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="57488-150">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="57488-151">Браузер: вам будет предложено сохранить журнал отладки в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="57488-151">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="57488-152">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="57488-152">Media Logs</span></span>
---------------------------

<span data-ttu-id="57488-153">Журналы мультимедиа содержат диагностические данные о звуке, видео и демонстрации экрана.</span><span class="sxs-lookup"><span data-stu-id="57488-153">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="57488-154">При обращении в службу поддержки они предоставляются по отдельному запросу и анализируются только сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57488-154">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="57488-155">Расположение журналов указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="57488-155">The following table outlines the log location.</span></span>


|<span data-ttu-id="57488-156">Клиент</span><span class="sxs-lookup"><span data-stu-id="57488-156">Client</span></span> |<span data-ttu-id="57488-157">Расположение</span><span class="sxs-lookup"><span data-stu-id="57488-157">Location</span></span> |
|---------|---------|
|<span data-ttu-id="57488-158">Windows</span><span class="sxs-lookup"><span data-stu-id="57488-158">Windows</span></span>     |<span data-ttu-id="57488-159">%appdata%\Roaming\Microsoft\Teams\media-stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="57488-159">%appdata%\Roaming\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="57488-160">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="57488-160">Mac OSX</span></span>     |<span data-ttu-id="57488-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="57488-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="57488-162">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="57488-162">Desktop logs</span></span>
---------------------

<span data-ttu-id="57488-163">Рабочие журналы, также называемые журналами начального загрузчика, регистрируют данные, передаваемые между классическим клиентом и браузером.</span><span class="sxs-lookup"><span data-stu-id="57488-163">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="57488-164">Как и журналы мультимедиа, эти журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57488-164">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="57488-165">Журналы имеют текстовый формат, открываются в любом текстовом редакторе и читаются сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="57488-165">The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="57488-166">Клиент</span><span class="sxs-lookup"><span data-stu-id="57488-166">Client</span></span> |<span data-ttu-id="57488-167">Расположение</span><span class="sxs-lookup"><span data-stu-id="57488-167">Location</span></span> |
|---------|---------|
|<span data-ttu-id="57488-168">Windows</span><span class="sxs-lookup"><span data-stu-id="57488-168">Windows</span></span>     |<span data-ttu-id="57488-169">%appdata%\Roaming\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="57488-169">%appdata%\Roaming\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="57488-170">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="57488-170">Mac OSX</span></span>     |<span data-ttu-id="57488-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="57488-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
