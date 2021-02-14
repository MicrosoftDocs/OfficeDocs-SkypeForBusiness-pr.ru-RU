---
title: Использование памяти в Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Узнайте об использовании системной памяти в Microsoft Teams и о том, почему использование памяти одинаково между классическим приложением и веб-приложением.
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
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="f95f6-103">Использование памяти в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f95f6-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="f95f6-104">У некоторых пользователей Microsoft Teams есть вопросы о том, как Teams использует память.</span><span class="sxs-lookup"><span data-stu-id="f95f6-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="f95f6-105">В этой статье описано, как используется память в Teams и почему настольное приложение (приложение) Teams и веб-приложение Teams не мешают другим приложениям и рабочим нагрузкам на том же компьютере иметь достаточно памяти для оптимальной работы.</span><span class="sxs-lookup"><span data-stu-id="f95f6-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="f95f6-106">Teams предназначена для использования современных веб-технологий.</span><span class="sxs-lookup"><span data-stu-id="f95f6-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="f95f6-107">Для этого был разработан клиент Teams для настольных систем на платформе Electron, в котором для отрисовки используется Chromium.</span><span class="sxs-lookup"><span data-stu-id="f95f6-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="f95f6-108">Это один и тот же обдвижка отрисовки, который отстает от многих популярных браузеров, включая Microsoft Edge и Chrome.</span><span class="sxs-lookup"><span data-stu-id="f95f6-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="f95f6-109">Как работает Teams</span><span class="sxs-lookup"><span data-stu-id="f95f6-109">How Teams works</span></span>

<span data-ttu-id="f95f6-110">Teams, разработанные на основе Electron, обеспечивает более быструю разработку и обеспечивает парность версий Teams в различных операционных системах (Windows, Mac и Linux).</span><span class="sxs-lookup"><span data-stu-id="f95f6-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="f95f6-111">Это возможно, так как в электронах и на основе Chromium коды во всех версиях аналогичны.</span><span class="sxs-lookup"><span data-stu-id="f95f6-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="f95f6-112">Еще одним преимуществом такой архитектуры является аналогичный профиль использования памяти между веб-приложением Teams и настольной версией.</span><span class="sxs-lookup"><span data-stu-id="f95f6-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="f95f6-113">Как веб-приложение, так и классические версии используют память так же, как и браузер.</span><span class="sxs-lookup"><span data-stu-id="f95f6-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="f95f6-114">Дополнительные сведения о Компании Electron можно найти на [их веб-сайте.](https://electronjs.org/)</span><span class="sxs-lookup"><span data-stu-id="f95f6-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="f95f6-115">Дополнительные [сведения см. в функциях использования памяти Chromium](https://www.chromium.org/developers/memory-usage-backgrounder) и ключевых понятиях [в памяти Chrome.](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)</span><span class="sxs-lookup"><span data-stu-id="f95f6-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="f95f6-116">На следующем рисунке показано, как работает память в настольном приложении Teams для Windows и в веб-приложении Teams (в данном примере — в Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="f95f6-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Использование памяти Teams для настольного приложения и веб-приложения](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="f95f6-118">Использование памяти в Teams</span><span class="sxs-lookup"><span data-stu-id="f95f6-118">Memory usage in Teams</span></span>

<span data-ttu-id="f95f6-119">Важно понимать, как  ожидается поведение Teams, когда речь идет о системной памяти, и симптомы проблем с памятью по-настоящему.</span><span class="sxs-lookup"><span data-stu-id="f95f6-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="f95f6-120">Ожидаемое использование памяти в Teams</span><span class="sxs-lookup"><span data-stu-id="f95f6-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="f95f6-121">Независимо от того, используете ли вы настольное приложение Teams или веб-приложение Teams, Chromium определяет объем доступной системной памяти и использует ее для оптимизации работы.</span><span class="sxs-lookup"><span data-stu-id="f95f6-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="f95f6-122">Если другим приложениям или службам требуется системная память, Chromium передает эти процессы памяти.</span><span class="sxs-lookup"><span data-stu-id="f95f6-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="f95f6-123">Использование памяти Chromium в Teams постоянно, чтобы оптимизировать производительность Teams, не влияя на другие текущие показатели.</span><span class="sxs-lookup"><span data-stu-id="f95f6-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="f95f6-124">Таким образом, похожие рабочие нагрузки на Chromium могут использовать различные объемы памяти в зависимости от объема доступной системной памяти.</span><span class="sxs-lookup"><span data-stu-id="f95f6-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="f95f6-125">На приведенном ниже рисунке по изображено использование памяти Teams в четырех отдельных системах с разным объемом доступной памяти.</span><span class="sxs-lookup"><span data-stu-id="f95f6-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="f95f6-126">В каждой системе одинаковые рабочие нагрузки (открыты и запущены одинаковые приложения).</span><span class="sxs-lookup"><span data-stu-id="f95f6-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Использование памяти Teams в разных системах](media/teams-memory-usage.png)

<span data-ttu-id="f95f6-128">Когда компьютеры имеют больше памяти, Teams будет использовать эту память.</span><span class="sxs-lookup"><span data-stu-id="f95f6-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="f95f6-129">В системах, в которых память засюмеяется, Teams будет использовать меньше.</span><span class="sxs-lookup"><span data-stu-id="f95f6-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="f95f6-130">Признаки проблем с системной памятью</span><span class="sxs-lookup"><span data-stu-id="f95f6-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="f95f6-131">Если на компьютере есть один или несколько из следующих признаков, это может привести к серьезной проблеме с памятью в системе:</span><span class="sxs-lookup"><span data-stu-id="f95f6-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="f95f6-132">Высокая память используется, если одновременно запущено несколько больших приложений.</span><span class="sxs-lookup"><span data-stu-id="f95f6-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="f95f6-133">Низкая производительность системы или зависающие приложения.</span><span class="sxs-lookup"><span data-stu-id="f95f6-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="f95f6-134">Стабильное общее использование системной памяти на 90 % или более во всех приложениях.</span><span class="sxs-lookup"><span data-stu-id="f95f6-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="f95f6-135">Благодаря такому объему использования памяти Teams будет возвращать память другим приложениям и рабочим нагрузкам.</span><span class="sxs-lookup"><span data-stu-id="f95f6-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="f95f6-136">Стабильное использование памяти на 90 % может означать, что Teams не передает память системе, что указывает на проблему.</span><span class="sxs-lookup"><span data-stu-id="f95f6-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="f95f6-137">На следующих рисунках покажите примеры представлений в диспетчере задач, если в системе не полностью расходуется память.</span><span class="sxs-lookup"><span data-stu-id="f95f6-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Представление использования памяти Teams в диспетчере задач](media/teams-memory-high-mem-process-list.png)

![График использования памяти Teams в диспетчере задач](media/teams-memory-high-mem-process-list2.png)
