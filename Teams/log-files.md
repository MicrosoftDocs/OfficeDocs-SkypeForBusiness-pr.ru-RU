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
ms.openlocfilehash: 6a14d6db6c03b540a6495b9028a4f0342ff92636
ms.sourcegitcommit: 336a9c95602d58ff069e4990b340e376a2d0d809
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26716337"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="961c2-103">Использование файлов журналов для устранения неполадок в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="961c2-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="961c2-104">Существует три типа журналов, создаваемых клиентом автоматически, которые облегчают устранение неполадок в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="961c2-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="961c2-105">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="961c2-105">Debug logs</span></span>

-   <span data-ttu-id="961c2-106">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="961c2-106">Media logs</span></span>

-   <span data-ttu-id="961c2-107">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="961c2-107">Desktop logs</span></span>

<span data-ttu-id="961c2-108">При обращении в службу поддержки нужно предоставить журналы отладки.</span><span class="sxs-lookup"><span data-stu-id="961c2-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="961c2-109">Это позволит Майкрософт быстро начать работу по устранению данной проблемы.</span><span class="sxs-lookup"><span data-stu-id="961c2-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="961c2-110">Журналы мультимедиа и рабочие журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="961c2-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="961c2-111">Следующая таблица описывает различные клиенты и соответствующие журналы.</span><span class="sxs-lookup"><span data-stu-id="961c2-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="961c2-112">Расположение файлов журналов зависит от клиента и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="961c2-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="961c2-113">Клиент</span><span class="sxs-lookup"><span data-stu-id="961c2-113">Client</span></span> |<span data-ttu-id="961c2-114">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="961c2-114">Debug</span></span>|<span data-ttu-id="961c2-115">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="961c2-115">Desktop</span></span>|<span data-ttu-id="961c2-116">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="961c2-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="961c2-117">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="961c2-117">Web</span></span>    |<span data-ttu-id="961c2-118">X</span><span class="sxs-lookup"><span data-stu-id="961c2-118">X</span></span>         |-         |-         |
|<span data-ttu-id="961c2-119">Windows</span><span class="sxs-lookup"><span data-stu-id="961c2-119">Windows</span></span>     |<span data-ttu-id="961c2-120">X</span><span class="sxs-lookup"><span data-stu-id="961c2-120">X</span></span>         |<span data-ttu-id="961c2-121">X</span><span class="sxs-lookup"><span data-stu-id="961c2-121">X</span></span>         |<span data-ttu-id="961c2-122">X</span><span class="sxs-lookup"><span data-stu-id="961c2-122">X</span></span>         |
|<span data-ttu-id="961c2-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="961c2-123">Mac OSX</span></span>     |<span data-ttu-id="961c2-124">X</span><span class="sxs-lookup"><span data-stu-id="961c2-124">X</span></span>         |<span data-ttu-id="961c2-125">X</span><span class="sxs-lookup"><span data-stu-id="961c2-125">X</span></span>         |<span data-ttu-id="961c2-126">X</span><span class="sxs-lookup"><span data-stu-id="961c2-126">X</span></span>         |
|<span data-ttu-id="961c2-127">iOS</span><span class="sxs-lookup"><span data-stu-id="961c2-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="961c2-128">Android</span><span class="sxs-lookup"><span data-stu-id="961c2-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="961c2-129">Полный список поддерживаемых операционных систем и браузеров см. в статье [Работа с клиентами для Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="961c2-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="961c2-130">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="961c2-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="961c2-131">Это наиболее распространенные журналы, которые требуются при любом обращении в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="961c2-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="961c2-132">Отладка производимые журналы Windows и Mac настольных клиентов, а также клиенты на основе браузера.</span><span class="sxs-lookup"><span data-stu-id="961c2-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="961c2-133">Эти журналы имеют текстовый формат, а читать их следует снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="961c2-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="961c2-134">Открыть их можно в любом текстовом редакторе. Новые журналы создаются при входе в клиент.</span><span class="sxs-lookup"><span data-stu-id="961c2-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="961c2-135">Журналы отладки показывают следующие потоки данных:</span><span class="sxs-lookup"><span data-stu-id="961c2-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="961c2-136">Вход</span><span class="sxs-lookup"><span data-stu-id="961c2-136">Login</span></span>

-   <span data-ttu-id="961c2-137">Запросы на подключение к службам среднего уровня</span><span class="sxs-lookup"><span data-stu-id="961c2-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="961c2-138">Звонок/беседа</span><span class="sxs-lookup"><span data-stu-id="961c2-138">Call/conversation</span></span>

<span data-ttu-id="961c2-139">Процедура создания этих журналов зависит от используемой операционной системы:</span><span class="sxs-lookup"><span data-stu-id="961c2-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="961c2-140">Windows:</span><span class="sxs-lookup"><span data-stu-id="961c2-140">Windows:</span></span>

    1.  <span data-ttu-id="961c2-141">щелкните правой кнопкой мыши **значок Microsoft Teams в** области приложений и выберите **Получить журналы**</span><span class="sxs-lookup"><span data-stu-id="961c2-141">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="961c2-142">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="961c2-142">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="961c2-143">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="961c2-143">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="961c2-144">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="961c2-144">Mac OSX:</span></span>

    1.  <span data-ttu-id="961c2-145">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="961c2-145">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="961c2-146">Сочетание клавиш: OPTION+COMMAND+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="961c2-146">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="961c2-147">Журналы отладки автоматически скачиваются в указанные ниже папки.</span><span class="sxs-lookup"><span data-stu-id="961c2-147">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="961c2-148">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="961c2-148">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="961c2-149">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="961c2-149">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="961c2-150">Браузер: вам будет предложено сохранить журнал отладки в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="961c2-150">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="961c2-151">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="961c2-151">Media Logs</span></span>
---------------------------

<span data-ttu-id="961c2-152">Журналы мультимедиа содержат диагностические данные о звуке, видео и демонстрации экрана.</span><span class="sxs-lookup"><span data-stu-id="961c2-152">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="961c2-153">При обращении в службу поддержки они предоставляются по отдельному запросу и анализируются только сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="961c2-153">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="961c2-154">Расположение журналов указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="961c2-154">The following table outlines the log location.</span></span>


|<span data-ttu-id="961c2-155">Клиент</span><span class="sxs-lookup"><span data-stu-id="961c2-155">Client</span></span> |<span data-ttu-id="961c2-156">Расположение</span><span class="sxs-lookup"><span data-stu-id="961c2-156">Location</span></span> |
|---------|---------|
|<span data-ttu-id="961c2-157">Windows</span><span class="sxs-lookup"><span data-stu-id="961c2-157">Windows</span></span>     |<span data-ttu-id="961c2-158">%AppData%\Microsoft\Teams\media-Stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="961c2-158">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="961c2-159">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="961c2-159">Mac OSX</span></span>     |<span data-ttu-id="961c2-160">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="961c2-160">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="961c2-161">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="961c2-161">Desktop logs</span></span>
---------------------

<span data-ttu-id="961c2-162">Рабочие журналы, также называемые журналами начального загрузчика, регистрируют данные, передаваемые между классическим клиентом и браузером.</span><span class="sxs-lookup"><span data-stu-id="961c2-162">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="961c2-163">Как и журналы мультимедиа, эти журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="961c2-163">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="961c2-164">Журналы имеют текстовый формат, открываются в любом текстовом редакторе и читаются сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="961c2-164">The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="961c2-165">Клиент</span><span class="sxs-lookup"><span data-stu-id="961c2-165">Client</span></span> |<span data-ttu-id="961c2-166">Расположение</span><span class="sxs-lookup"><span data-stu-id="961c2-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="961c2-167">Windows</span><span class="sxs-lookup"><span data-stu-id="961c2-167">Windows</span></span>     |<span data-ttu-id="961c2-168">%AppData%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="961c2-168">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="961c2-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="961c2-169">Mac OSX</span></span>     |<span data-ttu-id="961c2-170">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="961c2-170">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
