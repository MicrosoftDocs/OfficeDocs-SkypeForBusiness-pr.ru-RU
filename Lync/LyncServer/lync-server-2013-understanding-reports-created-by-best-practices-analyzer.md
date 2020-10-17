---
title: 'Lync Server 2013: Общие сведения об отчетах, созданных анализатором соответствия рекомендациям'
description: 'Lync Server 2013: Общие сведения об отчетах, созданных анализатором соответствия рекомендациям.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fbb84cdffe6e6e6f079c2d72aba4799f5538776
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542375"
---
# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="5fc8f-103">Общие сведения об отчетах, созданных анализатором соответствия рекомендациям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fc8f-103">Understanding reports created by Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fc8f-104">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="5fc8f-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="5fc8f-p101">Анализатором соответствия рекомендациям предоставляются отчеты нескольких типов, создаваемые для облегчения анализа и устранения проблем. Анализатором соответствия рекомендациям определяются проблемы, такие как ошибки, предупреждения, а также информация иного рода.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-p101">Best Practices Analyzer provides multiple types of reports that are organized to facilitate the analysis and resolution of issues. Best Practices Analyzer identifies issues such as errors, warnings, and other information.</span></span>

<div>

## <a name="reports"></a><span data-ttu-id="5fc8f-107">Отчеты</span><span class="sxs-lookup"><span data-stu-id="5fc8f-107">Reports</span></span>

<span data-ttu-id="5fc8f-108">Результаты сканирования можно просмотреть в следующих отчетах:</span><span class="sxs-lookup"><span data-stu-id="5fc8f-108">You can access the results of a scan by viewing each of the following reports:</span></span>

  - <span data-ttu-id="5fc8f-109">**Перечисление отчетов**     Список отчетов организован по определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-109">**List reports**   List reports are organized by specific criteria.</span></span> <span data-ttu-id="5fc8f-110">Можно упорядочить результаты по классам, уровню строгости или по проблемам.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-110">You can arrange the results by class, severity, or issue.</span></span> <span data-ttu-id="5fc8f-111">Например, если упорядочить результаты по классам, проблемы связанные с директорами, включаются в отчете в раздел директоров.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-111">For example, if you organize results by class, issues related to Directors are included under the Directors section of the report.</span></span> <span data-ttu-id="5fc8f-112">Имеется возможность просмотра всех проблем или только информационных элементов.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-112">You can view all of the issues, or just the informational items.</span></span> <span data-ttu-id="5fc8f-113">Можно выполнить поиск в списочном отчете конкретных элементов, например памяти.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-113">You can search a list report for specific items, such as memory.</span></span> <span data-ttu-id="5fc8f-114">Можно также распечатать или экспортировать отчет.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-114">You can also print the report or export it.</span></span>

  - <span data-ttu-id="5fc8f-115">Отчеты по дереву **Tree reports**     Отчеты по дереву упорядочиваются по правилам, которые используются для запуска сканирования и других параметров, указанных при запуске сканирования.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-115">**Tree reports**   Tree reports are organized by the rules that are used to run the scan and other options that you specified at the time the scan was run.</span></span> <span data-ttu-id="5fc8f-116">Например, проблемы, связанные с правилами тестовой топологии включаются в отчете в раздел тестовой топологии.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-116">For example, issues related to the Test Topology rules are included under the Test Topology section of the report.</span></span> <span data-ttu-id="5fc8f-117">Имеется возможность просмотра сведений о всех проблемах или только сводки проблем.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-117">You can view the details of all the issues, or just a summary of the issues.</span></span> <span data-ttu-id="5fc8f-118">В древовидном отчете можно выполнить поиск определенных элементов, например памяти.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-118">You can search a tree report for specific items, such as memory.</span></span> <span data-ttu-id="5fc8f-119">Можно также распечатать или экспортировать отчет.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-119">You can also print the report or export it.</span></span>

  - <span data-ttu-id="5fc8f-120">**Другие отчеты**     Элементы в других отчетах включают в себя журнал времени выполнения задач, включенных в сканирование.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-120">**Other reports**   Items in other reports include the run-time log of tasks that were included in the scan.</span></span> <span data-ttu-id="5fc8f-121">В других отчетах может выполняться поиск определенных элементов, например памяти.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-121">You can search the items in other reports for specific items, such as memory.</span></span> <span data-ttu-id="5fc8f-122">Можно также распечатать или экспортировать отчет.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-122">You can also print the report or export it.</span></span>

</div>

<div>

## <a name="issues"></a><span data-ttu-id="5fc8f-123">Проблемы</span><span class="sxs-lookup"><span data-stu-id="5fc8f-123">Issues</span></span>

<span data-ttu-id="5fc8f-124">В отчетах, создаваемых анализатором соответствия рекомендациям, указываются конкретные проблемы, которые идентифицированы во время сканирования рабочей среды, включая следующие типы проблем:</span><span class="sxs-lookup"><span data-stu-id="5fc8f-124">The reports generated by Best Practices Analyzer indicate specific issues that are identified during the scan of your environment, including following types of issues:</span></span>

  - <span data-ttu-id="5fc8f-125">**Ошибки**     Критические проблемы, требующие внесения изменений в среду.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-125">**Errors**   Critical issues that require you to make a change in your environment.</span></span> <span data-ttu-id="5fc8f-126">Например, если основные компоненты Lync Server 2013 не установлены, в журнал записывается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-126">For example, if Lync Server 2013 Core Components are not installed, an error is logged.</span></span>

    <span data-ttu-id="5fc8f-p106">Проблемы, которые классифицируются как ошибки, идентифицируются в отчете по красному символу X. Ошибки отображаются на вкладке **Все проблемы** в представлении **Списочные отчеты**, а также на вкладках **Таблица** и **Сводка** представления**Древовидные отчеты**. Если не хотите видеть какую-либо конкретную ошибку в отчете, можно указать, чтобы ошибка не показывалась для одного экземпляра или для всех экземпляров этой ошибки в отчете. Тогда ошибка отображается только на вкладке **Скрытые элементы** представления **Другие отчеты**, если не изменен параметр и не указано, что ошибка должна отображаться в отчете.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-p106">Issues that are classified as errors are identified in the report by a red X symbol. Errors are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The error is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the error be displayed in the report.</span></span>

  - <span data-ttu-id="5fc8f-131">**Предупреждения**     Проблемы, которые не соответствуют реализации рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-131">**Warnings**   Issues that are not consistent with the implementation of a best practice.</span></span> <span data-ttu-id="5fc8f-132">Это может указывать или не указывать на необходимость изменений в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-132">This may or may not indicate the need for a change in your environment.</span></span> <span data-ttu-id="5fc8f-133">Проблема может быть известной проблемой с конкретным параметром, который не нуждается в изменении.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-133">The issue could be a known issue with a specific setting that you do not need to change.</span></span> <span data-ttu-id="5fc8f-134">Например, службы, которые не запускаются на сервере, регистрируются как предупреждения.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-134">For example, services that are not started on a server are logged as warnings.</span></span>

    <span data-ttu-id="5fc8f-p108">Проблемы, которые классифицируются как предупреждения, идентифицируются в отчете по треугольному желтому символу предупреждения. Предупреждения отображаются на вкладке **Все проблемы** представления **Списочные отчеты**, а также на вкладках **Таблица** и **Сводка** представления **Древовидные отчеты**. Если не хотите, чтобы какая-нибудь конкретная ошибка отображалась в отчете, можно указать, чтобы эта ошибка не показывалась для одного экземпляра или для всех экземпляров этой ошибки в отчете. Тогда предупреждение отображается только на вкладке **Скрытые элементы** представления **Другие отчеты**, если не изменить параметр и не указать, что это предупреждение должно отображаться в отчете.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-p108">Issues that are classified as warnings are identified in the report by a triangular yellow warning symbol. Warnings are displayed on the **All Issues** tab of the **List Reports** view, as well as on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The warning is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the warning be displayed in the report.</span></span>

  - <span data-ttu-id="5fc8f-139">**Сведения**     Включает все проблемы, которые не классифицируются как ошибки или предупреждения.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-139">**Information**   Includes all issues that are not classified as errors or warnings.</span></span> <span data-ttu-id="5fc8f-140">Например, количество объектов сервера Standard Edition Lync Server 2013 в доменных службах Active Directory классифицируется как информационный вопрос.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-140">For example, the number of Lync Server 2013 Standard Edition server objects in Active Directory Domain Services is classified as an information issue.</span></span>

    <span data-ttu-id="5fc8f-141">Информационные проблемы отображаются на вкладке **Все проблемы** представления **Списочные отчеты** и на вкладке **Таблица** представления **Древовидные отчеты**.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-141">Information issues are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab of the **Tree Reports** view.</span></span>

<span data-ttu-id="5fc8f-142">Lync Server 2013, анализатор соответствия рекомендациям не вносит изменения в среду для устранения проблем.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-142">The Lync Server 2013, Best Practices Analyzer does not make changes to your environment to resolve issues.</span></span> <span data-ttu-id="5fc8f-143">В результате сканирования лишь детектируются потенциальные проблемы и предоставляются отчеты, содержащие информацию о том, как решить каждую проблему.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-143">The scan only detects potential issues and provides reports that contain information about how to resolve each issue.</span></span>

<span data-ttu-id="5fc8f-p111">Если щелкнуть проблему, отображаются объяснение и некоторые возможности для конкретных проблем. Далее можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="5fc8f-p111">If you click an issue, an explanation and some options are displayed for specific issues. Then, you can do any of the following:</span></span>

  - <span data-ttu-id="5fc8f-146">Найти более подробные сведения о проблеме и способе ее решения.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-146">Find more detailed information about the issue, and how to resolve it.</span></span>

  - <span data-ttu-id="5fc8f-147">Остановить отображение проблем в отчете:</span><span class="sxs-lookup"><span data-stu-id="5fc8f-147">Stop showing issues in reports:</span></span>

      - <span data-ttu-id="5fc8f-148">Остановить отображение проблем для выбранного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-148">Stop showing issues for the selected instance.</span></span>

      - <span data-ttu-id="5fc8f-149">Остановить отображение проблем для все экземпляров данной проблемы.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-149">Stop showing issues for all instances of that issue.</span></span>

    <span data-ttu-id="5fc8f-p112">Чтобы просмотреть проблемы, отображение которых в отчетах остановлено, перейдите на вкладку **Скрытые элементы** представления **Другие отчеты**. Находясь на этой вкладке, можно указать, чтобы проблемы снова отображались в отчетах.</span><span class="sxs-lookup"><span data-stu-id="5fc8f-p112">To see the issues you have stopped showing in reports, go to the **Hidden Items** tab of the **Other Reports** view. From there, you can specify to start showing issues in reports again.</span></span>

<span data-ttu-id="5fc8f-152">Сведения об устранении определенных проблем приведены [в статье анализ и устранение проблем, выявленных анализатором соответствия рекомендациям в Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="5fc8f-152">For details about resolving specific issues, see [Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
