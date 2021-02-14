---
title: 'Поддержка виртуализации для Skype для бизнеса Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Сведения о поддержке виртуализации в Skype для бизнеса Server 2019.
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509036"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="b3769-103">Поддержка виртуализации для Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="b3769-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="b3769-104">Skype для бизнеса Server 2019 поддерживается для виртуализации.</span><span class="sxs-lookup"><span data-stu-id="b3769-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="b3769-105">Хотя виртуализация поддерживается, следует помнить о некоторых ключевых моментах:</span><span class="sxs-lookup"><span data-stu-id="b3769-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="b3769-106">Поддержив соотношение виртуальных ЦП к физическому ЦП 1:1.</span><span class="sxs-lookup"><span data-stu-id="b3769-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="b3769-107">Не перемещайте гостевой сервер во время его работы.</span><span class="sxs-lookup"><span data-stu-id="b3769-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="b3769-108">Перенос живой системы и переносимость виртуальной машины не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b3769-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="b3769-109">Отключать hyper-threading на всех ведущих.</span><span class="sxs-lookup"><span data-stu-id="b3769-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="b3769-110">Не настраивайте динамическую память на серверах хост-серверов.</span><span class="sxs-lookup"><span data-stu-id="b3769-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="b3769-111">Используйте фиксированные или сквозные диски, а не динамические диски.</span><span class="sxs-lookup"><span data-stu-id="b3769-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="b3769-112">Допускается 6–10 процентов накладных расходов для гипервизоров, которые не требуются виртуальному гостю.</span><span class="sxs-lookup"><span data-stu-id="b3769-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="b3769-113">Поддерживаемые гипервизоры</span><span class="sxs-lookup"><span data-stu-id="b3769-113">Supported hypervisors</span></span>

<span data-ttu-id="b3769-114">SfB Server 2019 поддерживается в Windows Server 2016 и Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b3769-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="b3769-115">Для сторонних гипервизоров требуется гипервизор, который прошел тестирование программы проверки виртуализации серверов (SVVP) для соответствующей ОС.</span><span class="sxs-lookup"><span data-stu-id="b3769-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="b3769-116">См. [версии Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) в списке SVVP.</span><span class="sxs-lookup"><span data-stu-id="b3769-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="b3769-117">См. [версии Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) в списке SVVP.</span><span class="sxs-lookup"><span data-stu-id="b3769-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="b3769-118">Средство для работы с нагрузкой и производительностью</span><span class="sxs-lookup"><span data-stu-id="b3769-118">Stress and performance tool</span></span>

<span data-ttu-id="b3769-119">Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b3769-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="b3769-120">Skype для бизнеса Server 2019 Stress and Performance Tool поможет вам:</span><span class="sxs-lookup"><span data-stu-id="b3769-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="b3769-121">Упрощение планирования оборудования для Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="b3769-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="b3769-122">Предоставление дополнительных знаний и лучших методик настройки производительности</span><span class="sxs-lookup"><span data-stu-id="b3769-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="b3769-123">Измерение производительности предполагаемых развертывание Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="b3769-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="b3769-124">Вы можете скачать средство [здесь.](https://www.microsoft.com/download/details.aspx?id=101447)</span><span class="sxs-lookup"><span data-stu-id="b3769-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
