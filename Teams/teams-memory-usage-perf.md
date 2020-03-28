---
title: Использование памяти в Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Как в Microsoft Teams используется системная память, и почему использование памяти одинаково между классским приложением и веб-приложением.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59940eafcdb6f86961b3cd6805cb9c5bb40f9fb2
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033403"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="fdabb-103">Использование памяти в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fdabb-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="fdabb-104">У некоторых пользователей Microsoft Teams есть вопросы о том, как в Teams используется память.</span><span class="sxs-lookup"><span data-stu-id="fdabb-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="fdabb-105">В этой статье объясняется, как в Teams используется память, и почему классическое приложение Teams (приложение) и веб-приложение Teams не запрещает другим приложениям и рабочим нагрузкам на том же компьютере достаточное количество памяти для оптимальной работы.</span><span class="sxs-lookup"><span data-stu-id="fdabb-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="fdabb-106">Teams разработана для использования современных веб-технологий.</span><span class="sxs-lookup"><span data-stu-id="fdabb-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="fdabb-107">Для этого классическое приложение Teams разрабатывалось на электронном г., которое использует Chromium для отрисовки.</span><span class="sxs-lookup"><span data-stu-id="fdabb-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="fdabb-108">Это тот же механизм обработки, что и в большинстве современных популярных браузеров, включая ребры и хромы.</span><span class="sxs-lookup"><span data-stu-id="fdabb-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="fdabb-109">Принципы работы Teams</span><span class="sxs-lookup"><span data-stu-id="fdabb-109">How Teams works</span></span>

<span data-ttu-id="fdabb-110">Команды, разработанные в электронном виде, позволяют быстрее разрабатывать приложения, а также сохранять четность между версиями Teams в разных операционных системах (Windows, Mac и Linux).</span><span class="sxs-lookup"><span data-stu-id="fdabb-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="fdabb-111">Это может быть связано с тем, что электронную и Chromium поддерживать одинаковую базу кода во всех версиях.</span><span class="sxs-lookup"><span data-stu-id="fdabb-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="fdabb-112">Еще одно преимущество этой архитектуры — это использование аналогичного профиля использования памяти между Teams Web App и классической версией.</span><span class="sxs-lookup"><span data-stu-id="fdabb-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="fdabb-113">Как в веб-приложении, так и в классической версии память используется так же, как и в браузере.</span><span class="sxs-lookup"><span data-stu-id="fdabb-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="fdabb-114">Дополнительные сведения об электронном курсе можно найти на [веб-сайте](https://electronjs.org/).</span><span class="sxs-lookup"><span data-stu-id="fdabb-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="fdabb-115">Более подробную информацию смотрите в разделе [использование памяти Chromium](https://www.chromium.org/developers/memory-usage-backgrounder) и основные [понятия в памяти Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) .</span><span class="sxs-lookup"><span data-stu-id="fdabb-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="fdabb-116">На приведенном ниже рисунке показано использование оперативной памяти в классическом приложении Teams для Windows и в веб-приложении Teams (в этом примере выполняется в Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="fdabb-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Классическое приложение Teams и использование памяти веб-приложения](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="fdabb-118">Использование памяти в Teams</span><span class="sxs-lookup"><span data-stu-id="fdabb-118">Memory usage in Teams</span></span>

<span data-ttu-id="fdabb-119">Важно понимать *ожидаемое* поведение команд в Teams, когда дело доходит до системной памяти, и узнать, какие признаки действительно проблем с системной памятью.</span><span class="sxs-lookup"><span data-stu-id="fdabb-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="fdabb-120">Ожидаемое использование памяти в Teams</span><span class="sxs-lookup"><span data-stu-id="fdabb-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="fdabb-121">Независимо от того, используете ли вы классическое приложение Teams или Teams Web App, Chromium определяет, сколько системной памяти доступно и использует достаточно памяти для оптимизации процесса рендеринга.</span><span class="sxs-lookup"><span data-stu-id="fdabb-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="fdabb-122">Если в других приложениях или службах требуется Системная память, Chromium передает память этим процессам.</span><span class="sxs-lookup"><span data-stu-id="fdabb-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="fdabb-123">Chromium использует память в Teams для оптимизации производительности групп, не влияя на что-либо еще в данный момент.</span><span class="sxs-lookup"><span data-stu-id="fdabb-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="fdabb-124">Таким образом, аналогичные рабочие нагрузки Chromium могут использовать различные объемы памяти в зависимости от объема доступной системной памяти.</span><span class="sxs-lookup"><span data-stu-id="fdabb-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="fdabb-125">На следующем графике показано использование памяти группами в четырех отдельных системах, каждый из которых имеет различные объемы доступной памяти.</span><span class="sxs-lookup"><span data-stu-id="fdabb-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="fdabb-126">Каждая система обрабатывает похожие рабочие нагрузки (открытые и запущенные приложения).</span><span class="sxs-lookup"><span data-stu-id="fdabb-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Использование памяти в Teams для разных систем](media/teams-memory-usage.png)

<span data-ttu-id="fdabb-128">Если на компьютере установлено больше памяти, они будут использовать эту память в Teams.</span><span class="sxs-lookup"><span data-stu-id="fdabb-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="fdabb-129">В системах, где недостаточно памяти, группы будут использовать меньше.</span><span class="sxs-lookup"><span data-stu-id="fdabb-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="fdabb-130">Признаки проблем с системной памятью</span><span class="sxs-lookup"><span data-stu-id="fdabb-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="fdabb-131">Если на компьютере есть одна или несколько описанных ниже симптомов, возможно, возникла серьезная проблема с системной памятью.</span><span class="sxs-lookup"><span data-stu-id="fdabb-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="fdabb-132">Большое использование памяти при одновременном выполнении нескольких больших приложений.</span><span class="sxs-lookup"><span data-stu-id="fdabb-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="fdabb-133">Низкая производительность системы или приложения.</span><span class="sxs-lookup"><span data-stu-id="fdabb-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="fdabb-134">Общий объем оперативной памяти, поддерживаемой 90% или более, для всех приложений.</span><span class="sxs-lookup"><span data-stu-id="fdabb-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="fdabb-135">С помощью этого объема памяти команды должны предоставлять доступ к другим приложениям и рабочим нагрузкам.</span><span class="sxs-lookup"><span data-stu-id="fdabb-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="fdabb-136">Длительное использование памяти в 90% может означать, что команды не передают память системе, что означает проблему.</span><span class="sxs-lookup"><span data-stu-id="fdabb-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="fdabb-137">На следующих рисунках показаны примеры представлений в диспетчере задач при неправильном высоком уровне использования системной памяти.</span><span class="sxs-lookup"><span data-stu-id="fdabb-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Представление "использование памяти в Teams" в диспетчере задач](media/teams-memory-high-mem-process-list.png)

![Диаграмма использования памяти Teams в диспетчере задач](media/teams-memory-high-mem-process-list2.png)
