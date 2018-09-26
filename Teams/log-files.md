---
title: Использование файлов журналов для устранения неполадок в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Сведения о журналах отладки, мультимедиа и рабочих журналах, создаваемых Microsoft Teams, их расположении и роли при устранении неполадок.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95d28bac036476c417ccbe7929a23ab9fb37f3a8
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "25018902"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="48b1f-103">Использование файлов журналов для устранения неполадок в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="48b1f-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="48b1f-104">Существует три типа журналов, создаваемых клиентом автоматически, которые облегчают устранение неполадок в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="48b1f-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="48b1f-105">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="48b1f-105">Debug logs</span></span>

-   <span data-ttu-id="48b1f-106">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="48b1f-106">Media logs</span></span>

-   <span data-ttu-id="48b1f-107">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="48b1f-107">Desktop logs</span></span>

<span data-ttu-id="48b1f-108">При обращении в службу поддержки нужно предоставить журналы отладки.</span><span class="sxs-lookup"><span data-stu-id="48b1f-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="48b1f-109">Это позволит Майкрософт быстро начать работу по устранению данной проблемы.</span><span class="sxs-lookup"><span data-stu-id="48b1f-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="48b1f-110">Журналы мультимедиа и рабочие журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="48b1f-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="48b1f-111">Следующая таблица описывает различные клиенты и соответствующие журналы.</span><span class="sxs-lookup"><span data-stu-id="48b1f-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="48b1f-112">Расположение файлов журналов зависит от клиента и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="48b1f-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="48b1f-113">Клиент</span><span class="sxs-lookup"><span data-stu-id="48b1f-113">Client</span></span> |<span data-ttu-id="48b1f-114">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="48b1f-114">Debug</span></span>|<span data-ttu-id="48b1f-115">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="48b1f-115">Desktop</span></span>|<span data-ttu-id="48b1f-116">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="48b1f-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="48b1f-117">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="48b1f-117">Web</span></span>    |<span data-ttu-id="48b1f-118">X</span><span class="sxs-lookup"><span data-stu-id="48b1f-118">X</span></span>         |-         |-         |
|<span data-ttu-id="48b1f-119">Windows</span><span class="sxs-lookup"><span data-stu-id="48b1f-119">Windows</span></span>     |<span data-ttu-id="48b1f-120">X</span><span class="sxs-lookup"><span data-stu-id="48b1f-120">X</span></span>         |<span data-ttu-id="48b1f-121">X</span><span class="sxs-lookup"><span data-stu-id="48b1f-121">X</span></span>         |<span data-ttu-id="48b1f-122">X</span><span class="sxs-lookup"><span data-stu-id="48b1f-122">X</span></span>         |
|<span data-ttu-id="48b1f-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="48b1f-123">Mac OSX</span></span>     |<span data-ttu-id="48b1f-124">X</span><span class="sxs-lookup"><span data-stu-id="48b1f-124">X</span></span>         |<span data-ttu-id="48b1f-125">X</span><span class="sxs-lookup"><span data-stu-id="48b1f-125">X</span></span>         |<span data-ttu-id="48b1f-126">X</span><span class="sxs-lookup"><span data-stu-id="48b1f-126">X</span></span>         |
|<span data-ttu-id="48b1f-127">iOS</span><span class="sxs-lookup"><span data-stu-id="48b1f-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="48b1f-128">Android</span><span class="sxs-lookup"><span data-stu-id="48b1f-128">Android</span></span>     |-         |-         |-         |
|<span data-ttu-id="48b1f-129">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="48b1f-129">Windows Phone</span></span>     |-         |-         |-         |

<span data-ttu-id="48b1f-130">Полный список поддерживаемых операционных систем и браузеров см. в статье [Работа с клиентами для Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="48b1f-130">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="48b1f-131">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="48b1f-131">Debug logs</span></span>
---------------------------

<span data-ttu-id="48b1f-132">Это наиболее распространенные журналы, которые требуются при любом обращении в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="48b1f-132">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="48b1f-133">Отладка производимые журналы Windows и Mac настольных клиентов, а также клиенты на основе браузера.</span><span class="sxs-lookup"><span data-stu-id="48b1f-133">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="48b1f-134">Эти журналы имеют текстовый формат, а читать их следует снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="48b1f-134">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="48b1f-135">Открыть их можно в любом текстовом редакторе. Новые журналы создаются при входе в клиент.</span><span class="sxs-lookup"><span data-stu-id="48b1f-135">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="48b1f-136">Журналы отладки показывают следующие потоки данных:</span><span class="sxs-lookup"><span data-stu-id="48b1f-136">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="48b1f-137">Вход</span><span class="sxs-lookup"><span data-stu-id="48b1f-137">Login</span></span>

-   <span data-ttu-id="48b1f-138">Запросы на подключение к службам среднего уровня</span><span class="sxs-lookup"><span data-stu-id="48b1f-138">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="48b1f-139">Звонок/беседа</span><span class="sxs-lookup"><span data-stu-id="48b1f-139">Call/conversation</span></span>

<span data-ttu-id="48b1f-140">Процедура создания этих журналов зависит от используемой операционной системы:</span><span class="sxs-lookup"><span data-stu-id="48b1f-140">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="48b1f-141">Windows:</span><span class="sxs-lookup"><span data-stu-id="48b1f-141">Windows:</span></span>

    1.  <span data-ttu-id="48b1f-142">щелкните правой кнопкой мыши **значок Microsoft Teams в** области приложений и выберите **Получить журналы**</span><span class="sxs-lookup"><span data-stu-id="48b1f-142">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="48b1f-143">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="48b1f-143">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="48b1f-144">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="48b1f-144">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="48b1f-145">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="48b1f-145">Mac OSX:</span></span>

    1.  <span data-ttu-id="48b1f-146">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="48b1f-146">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="48b1f-147">Сочетание клавиш: OPTION+COMMAND+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="48b1f-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="48b1f-148">Журналы отладки автоматически скачиваются в указанные ниже папки.</span><span class="sxs-lookup"><span data-stu-id="48b1f-148">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="48b1f-149">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="48b1f-149">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="48b1f-150">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="48b1f-150">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="48b1f-151">Браузер: вам будет предложено сохранить журнал отладки в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="48b1f-151">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="48b1f-152">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="48b1f-152">Media Logs</span></span>
---------------------------

<span data-ttu-id="48b1f-153">Журналы мультимедиа содержат диагностические данные о звуке, видео и демонстрации экрана.</span><span class="sxs-lookup"><span data-stu-id="48b1f-153">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="48b1f-154">При обращении в службу поддержки они предоставляются по отдельному запросу и анализируются только сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="48b1f-154">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="48b1f-155">Расположение журналов указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="48b1f-155">The following table outlines the log location.</span></span>


|<span data-ttu-id="48b1f-156">Клиент</span><span class="sxs-lookup"><span data-stu-id="48b1f-156">Client</span></span> |<span data-ttu-id="48b1f-157">Расположение</span><span class="sxs-lookup"><span data-stu-id="48b1f-157">Location</span></span> |
|---------|---------|
|<span data-ttu-id="48b1f-158">Windows</span><span class="sxs-lookup"><span data-stu-id="48b1f-158">Windows</span></span>     |<span data-ttu-id="48b1f-159">%AppData%\Microsoft\Teams\media-Stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="48b1f-159">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="48b1f-160">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="48b1f-160">Mac OSX</span></span>     |<span data-ttu-id="48b1f-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="48b1f-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="48b1f-162">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="48b1f-162">Desktop logs</span></span>
---------------------

<span data-ttu-id="48b1f-163">Рабочие журналы, также называемые журналами начального загрузчика, регистрируют данные, передаваемые между классическим клиентом и браузером.</span><span class="sxs-lookup"><span data-stu-id="48b1f-163">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="48b1f-164">Как и журналы мультимедиа, эти журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="48b1f-164">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="48b1f-165">Журналы имеют текстовый формат, открываются в любом текстовом редакторе и читаются сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="48b1f-165">The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="48b1f-166">Клиент</span><span class="sxs-lookup"><span data-stu-id="48b1f-166">Client</span></span> |<span data-ttu-id="48b1f-167">Расположение</span><span class="sxs-lookup"><span data-stu-id="48b1f-167">Location</span></span> |
|---------|---------|
|<span data-ttu-id="48b1f-168">Windows</span><span class="sxs-lookup"><span data-stu-id="48b1f-168">Windows</span></span>     |<span data-ttu-id="48b1f-169">%AppData%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="48b1f-169">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="48b1f-170">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="48b1f-170">Mac OSX</span></span>     |<span data-ttu-id="48b1f-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="48b1f-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
