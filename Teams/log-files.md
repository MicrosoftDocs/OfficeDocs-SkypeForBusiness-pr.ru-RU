---
title: Использование файлов журналов для устранения неполадок в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Сведения о журналах отладки, мультимедиа и рабочих журналах, создаваемых Microsoft Teams, их расположении и роли при устранении неполадок.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2325532126c11e397b7aec5a6ed040b71aa659b0
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849941"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="fe90e-103">Использование файлов журналов для устранения неполадок в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe90e-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="fe90e-104">Существует три типа журналов, создаваемых клиентом автоматически, которые облегчают устранение неполадок в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fe90e-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="fe90e-105">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="fe90e-105">Debug logs</span></span>

-   <span data-ttu-id="fe90e-106">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="fe90e-106">Media logs</span></span>

-   <span data-ttu-id="fe90e-107">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="fe90e-107">Desktop logs</span></span>

<span data-ttu-id="fe90e-108">При обращении в службу поддержки нужно предоставить журналы отладки.</span><span class="sxs-lookup"><span data-stu-id="fe90e-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="fe90e-109">Это позволит Майкрософт быстро начать работу по устранению данной проблемы.</span><span class="sxs-lookup"><span data-stu-id="fe90e-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="fe90e-110">Журналы мультимедиа и рабочие журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fe90e-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="fe90e-111">Следующая таблица описывает различные клиенты и соответствующие журналы.</span><span class="sxs-lookup"><span data-stu-id="fe90e-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="fe90e-112">Расположение файлов журналов зависит от клиента и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="fe90e-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="fe90e-113">Клиент</span><span class="sxs-lookup"><span data-stu-id="fe90e-113">Client</span></span> |<span data-ttu-id="fe90e-114">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="fe90e-114">Debug</span></span>|<span data-ttu-id="fe90e-115">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="fe90e-115">Desktop</span></span>|<span data-ttu-id="fe90e-116">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="fe90e-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="fe90e-117">Веб-клиент</span><span class="sxs-lookup"><span data-stu-id="fe90e-117">Web</span></span>    |<span data-ttu-id="fe90e-118">X</span><span class="sxs-lookup"><span data-stu-id="fe90e-118">X</span></span>         |-         |-         |
|<span data-ttu-id="fe90e-119">Windows</span><span class="sxs-lookup"><span data-stu-id="fe90e-119">Windows</span></span>     |<span data-ttu-id="fe90e-120">X</span><span class="sxs-lookup"><span data-stu-id="fe90e-120">X</span></span>         |<span data-ttu-id="fe90e-121">X</span><span class="sxs-lookup"><span data-stu-id="fe90e-121">X</span></span>         |<span data-ttu-id="fe90e-122">X</span><span class="sxs-lookup"><span data-stu-id="fe90e-122">X</span></span>         |
|<span data-ttu-id="fe90e-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fe90e-123">Mac OSX</span></span>     |<span data-ttu-id="fe90e-124">X</span><span class="sxs-lookup"><span data-stu-id="fe90e-124">X</span></span>         |<span data-ttu-id="fe90e-125">X</span><span class="sxs-lookup"><span data-stu-id="fe90e-125">X</span></span>         |<span data-ttu-id="fe90e-126">X</span><span class="sxs-lookup"><span data-stu-id="fe90e-126">X</span></span>         |
|<span data-ttu-id="fe90e-127">iOS</span><span class="sxs-lookup"><span data-stu-id="fe90e-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="fe90e-128">Android</span><span class="sxs-lookup"><span data-stu-id="fe90e-128">Android</span></span>     |-         |-         |-         |
|<span data-ttu-id="fe90e-129">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="fe90e-129">Windows Phone</span></span>     |-         |-         |-         |

<span data-ttu-id="fe90e-130">Полный список поддерживаемых операционных систем и браузеров см. в статье [Работа с клиентами для Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="fe90e-130">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="fe90e-131">Журналы отладки</span><span class="sxs-lookup"><span data-stu-id="fe90e-131">Debug logs</span></span>
---------------------------

<span data-ttu-id="fe90e-132">Это наиболее распространенные журналы, которые требуются при любом обращении в службу поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fe90e-132">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="fe90e-133">Они создаются классическими клиентами Windows и Mac, а также клиентами на основе браузеров.</span><span class="sxs-lookup"><span data-stu-id="fe90e-133">Debug logs are produced by the Window and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="fe90e-134">Эти журналы имеют текстовый формат, а читать их следует снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="fe90e-134">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="fe90e-135">Открыть их можно в любом текстовом редакторе. Новые журналы создаются при входе в клиент.</span><span class="sxs-lookup"><span data-stu-id="fe90e-135">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="fe90e-136">Журналы отладки показывают следующие потоки данных:</span><span class="sxs-lookup"><span data-stu-id="fe90e-136">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="fe90e-137">Вход</span><span class="sxs-lookup"><span data-stu-id="fe90e-137">Login</span></span>

-   <span data-ttu-id="fe90e-138">Запросы на подключение к службам среднего уровня</span><span class="sxs-lookup"><span data-stu-id="fe90e-138">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="fe90e-139">Звонок/беседа</span><span class="sxs-lookup"><span data-stu-id="fe90e-139">Call/conversation</span></span>

<span data-ttu-id="fe90e-140">Процедура создания этих журналов зависит от используемой операционной системы:</span><span class="sxs-lookup"><span data-stu-id="fe90e-140">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="fe90e-141">Windows:</span><span class="sxs-lookup"><span data-stu-id="fe90e-141">Windows:</span></span>

    1.  <span data-ttu-id="fe90e-142">щелкните правой кнопкой мыши **значок Microsoft Teams в** области приложений и выберите **Получить журналы**</span><span class="sxs-lookup"><span data-stu-id="fe90e-142">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="fe90e-143">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="fe90e-143">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="fe90e-144">Сочетание клавиш: CTRL+ALT+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="fe90e-144">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="fe90e-145">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="fe90e-145">Mac OSX:</span></span>

    1.  <span data-ttu-id="fe90e-146">Выбор пункта **Получить журналы** в раскрывающемся меню **Справка**</span><span class="sxs-lookup"><span data-stu-id="fe90e-146">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="fe90e-147">Сочетание клавиш: OPTION+COMMAND+SHIFT+1</span><span class="sxs-lookup"><span data-stu-id="fe90e-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="fe90e-148">Журналы отладки автоматически скачиваются в указанные ниже папки.</span><span class="sxs-lookup"><span data-stu-id="fe90e-148">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="fe90e-149">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="fe90e-149">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="fe90e-150">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="fe90e-150">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="fe90e-151">Браузер: вам будет предложено сохранить журнал отладки в расположении по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe90e-151">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="fe90e-152">Журналы мультимедиа</span><span class="sxs-lookup"><span data-stu-id="fe90e-152">Media Logs</span></span>
---------------------------

<span data-ttu-id="fe90e-153">Журналы мультимедиа содержат диагностические данные о звуке, видео и демонстрации экрана.</span><span class="sxs-lookup"><span data-stu-id="fe90e-153">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="fe90e-154">При обращении в службу поддержки они предоставляются по отдельному запросу и анализируются только сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fe90e-154">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="fe90e-155">Расположение журналов указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="fe90e-155">The following table outlines the log location.</span></span>


|<span data-ttu-id="fe90e-156">Клиент</span><span class="sxs-lookup"><span data-stu-id="fe90e-156">Client</span></span> |<span data-ttu-id="fe90e-157">Расположение</span><span class="sxs-lookup"><span data-stu-id="fe90e-157">Location</span></span> |
|---------|---------|
|<span data-ttu-id="fe90e-158">Windows</span><span class="sxs-lookup"><span data-stu-id="fe90e-158">Windows</span></span>     |<span data-ttu-id="fe90e-159">%AppData%\Microsoft\Teams\media-Stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="fe90e-159">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="fe90e-160">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fe90e-160">Mac OSX</span></span>     |<span data-ttu-id="fe90e-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="fe90e-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="fe90e-162">Рабочие журналы</span><span class="sxs-lookup"><span data-stu-id="fe90e-162">Desktop logs</span></span>
---------------------

<span data-ttu-id="fe90e-163">Рабочие журналы, также называемые журналами начального загрузчика, регистрируют данные, передаваемые между классическим клиентом и браузером.</span><span class="sxs-lookup"><span data-stu-id="fe90e-163">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="fe90e-164">Как и журналы мультимедиа, эти журналы следует предоставлять только по отдельному запросу Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fe90e-164">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="fe90e-165">Журналы имеют текстовый формат, открываются в любом текстовом редакторе и читаются сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="fe90e-165">The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="fe90e-166">Клиент</span><span class="sxs-lookup"><span data-stu-id="fe90e-166">Client</span></span> |<span data-ttu-id="fe90e-167">Расположение</span><span class="sxs-lookup"><span data-stu-id="fe90e-167">Location</span></span> |
|---------|---------|
|<span data-ttu-id="fe90e-168">Windows</span><span class="sxs-lookup"><span data-stu-id="fe90e-168">Windows</span></span>     |<span data-ttu-id="fe90e-169">%AppData%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="fe90e-169">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="fe90e-170">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fe90e-170">Mac OSX</span></span>     |<span data-ttu-id="fe90e-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="fe90e-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
