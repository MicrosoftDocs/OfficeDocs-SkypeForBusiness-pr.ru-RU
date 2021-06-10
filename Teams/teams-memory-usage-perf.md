---
title: Использование памяти в Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Узнайте, Microsoft Teams использование системной памяти и почему использование памяти одинаково между классическим приложением и веб-приложением.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: d218c71a0e3ecdde40559d67e1ad3a408d65a5d9
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878723"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="c6314-103">Использование памяти в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6314-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="c6314-104">У Microsoft Teams есть вопросы о том, как Teams памяти.</span><span class="sxs-lookup"><span data-stu-id="c6314-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="c6314-105">В этой статье описано, как Teams используется память, и почему настольное приложение Teams (приложение) и веб-приложение Teams не предотвращают оптимальное работу других приложений и рабочих нагрузок на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="c6314-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="c6314-106">Teams предназначена для использования современных веб-технологий.</span><span class="sxs-lookup"><span data-stu-id="c6314-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="c6314-107">Для этого настольный клиент Teams был разработан на компьютере с иголкой, Chromium для отрисовки.</span><span class="sxs-lookup"><span data-stu-id="c6314-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="c6314-108">Этот же механизм отрисовки работает и в большинстве популярных браузеров, включая Microsoft Edge и Chrome.</span><span class="sxs-lookup"><span data-stu-id="c6314-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="c6314-109">Как Teams работает</span><span class="sxs-lookup"><span data-stu-id="c6314-109">How Teams works</span></span>

<span data-ttu-id="c6314-110">Teams предназначение для Работы схиву , обеспечивает более быструю разработку, а также обеспечивает парность между Teams версиями в разных операционных системах (Windows, Mac и Linux).</span><span class="sxs-lookup"><span data-stu-id="c6314-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="c6314-111">Такая четность возможна, так как в Chromium и в разных версиях поддерживается одинаковый код.</span><span class="sxs-lookup"><span data-stu-id="c6314-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="c6314-112">Еще одним преимуществом такой архитектуры является схожий профиль использования памяти между веб-приложением Teams и настольной версией.</span><span class="sxs-lookup"><span data-stu-id="c6314-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="c6314-113">Как веб-приложение, так и классические версии используют память так же, как и браузер.</span><span class="sxs-lookup"><span data-stu-id="c6314-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="c6314-114">Дополнительные сведения о службе "Электрон" можно найти [на их веб-сайте.](https://electronjs.org/)</span><span class="sxs-lookup"><span data-stu-id="c6314-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="c6314-115">Дополнительные [Chromium использования памяти](https://www.chromium.org/developers/memory-usage-backgrounder) и [основные понятия в памяти Chrome.](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)</span><span class="sxs-lookup"><span data-stu-id="c6314-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="c6314-116">На рисунке ниже показано использование памяти рядом с классическим приложением Teams для Windows и веб-приложением Teams (в данном примере — в Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="c6314-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Teams памяти для классических приложений и веб-приложений](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="c6314-118">Использование памяти в Teams</span><span class="sxs-lookup"><span data-stu-id="c6314-118">Memory usage in Teams</span></span>

<span data-ttu-id="c6314-119">Важно понимать ожидаемое  поведение системы Teams, когда речь идет о системной памяти, и о проблемах с действительно проблемной памятью системы.</span><span class="sxs-lookup"><span data-stu-id="c6314-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="c6314-120">Ожидаемое использование памяти Teams</span><span class="sxs-lookup"><span data-stu-id="c6314-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="c6314-121">Независимо от того, используете ли вы Teams или веб-приложение Teams, Chromium определяет объем доступной системной памяти и использует достаточно памяти для оптимизации работы с отрисовки.</span><span class="sxs-lookup"><span data-stu-id="c6314-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="c6314-122">Если другим приложениям или службам требуется системная память, Chromium памяти для этих процессов.</span><span class="sxs-lookup"><span data-stu-id="c6314-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="c6314-123">Chromium мелодий Teams постоянное использование памяти, чтобы оптимизировать производительность Teams не влияет ни на что другое в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="c6314-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="c6314-124">Таким образом, Chromium могут использовать разные объемы памяти в зависимости от объема доступной системной памяти.</span><span class="sxs-lookup"><span data-stu-id="c6314-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="c6314-125">На приведенном ниже рисунке по Teams в четырех отдельных системах с разным объемом доступной памяти.</span><span class="sxs-lookup"><span data-stu-id="c6314-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="c6314-126">Каждая из систем обрабатывает похожие рабочие нагрузки (открыты и запущены те же приложения).</span><span class="sxs-lookup"><span data-stu-id="c6314-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Teams использование памяти в разных системах](media/teams-memory-usage.png)

<span data-ttu-id="c6314-128">Если на компьютерах больше памяти, Teams будет использовать эту память.</span><span class="sxs-lookup"><span data-stu-id="c6314-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="c6314-129">В системах, где память засюмеется, Teams будут использовать меньше.</span><span class="sxs-lookup"><span data-stu-id="c6314-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="c6314-130">Проблемы с памятью системы</span><span class="sxs-lookup"><span data-stu-id="c6314-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="c6314-131">Если на компьютере есть один или несколько из следующих признаков, возможно, у вас серьезные проблемы с памятью системы:</span><span class="sxs-lookup"><span data-stu-id="c6314-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="c6314-132">Высокая память используется, если одновременно запущено несколько крупных приложений.</span><span class="sxs-lookup"><span data-stu-id="c6314-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="c6314-133">Низкая производительность системы или зависающие приложения.</span><span class="sxs-lookup"><span data-stu-id="c6314-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="c6314-134">Стабильное общее использование системной памяти на 90 % или более во всех приложениях.</span><span class="sxs-lookup"><span data-stu-id="c6314-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="c6314-135">При таком объеме использования памяти Teams необходимо вернуть память другим приложениям и рабочим нагрузкам.</span><span class="sxs-lookup"><span data-stu-id="c6314-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="c6314-136">Стабильное использование 90 % памяти может означать, Teams не возвращает память в систему, что указывает на проблему.</span><span class="sxs-lookup"><span data-stu-id="c6314-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="c6314-137">На рисунках ниже демонстрироваться примеры представлений в диспетчере задач, если объем памяти системы аномально высока.</span><span class="sxs-lookup"><span data-stu-id="c6314-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Teams представления использования памяти в диспетчере задач](media/teams-memory-high-mem-process-list.png)

![Teams использования памяти в диспетчере задач](media/teams-memory-high-mem-process-list2.png)
