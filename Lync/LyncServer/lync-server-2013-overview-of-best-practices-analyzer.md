---
title: 'Lync Server 2013: Обзор анализатора соответствия рекомендациям'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85bee37f748f0356458770c742f26e704132ad6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="c9553-102">Обзор анализатора соответствия рекомендациям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9553-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9553-103">_**Последнее изменение темы:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="c9553-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="c9553-104">Вы можете использовать Lync Server 2013, анализатор соответствия рекомендациям для обнаружения и устранения проблем при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9553-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="c9553-105">Lync Server 2013, анализатор соответствия рекомендациям собирает сведения о конфигурации из компонентов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9553-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="c9553-106">При правильном доступе к сети анализатор соответствия рекомендациям может проверить серверы, на которых работают доменные службы Active Directory, единая система обмена сообщениями Exchange Server (UM) и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9553-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="c9553-107">Анализатор соответствия рекомендациям можно использовать для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="c9553-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="c9553-108">превентивного выполнения проверок для выяснения соответствия установленной конфигурации рекомендациям;</span><span class="sxs-lookup"><span data-stu-id="c9553-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="c9553-109">Автоматическое определение необходимых обновлений для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9553-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="c9553-110">создания списка проблем, таких как неоптимальные параметры конфигурации, неподдерживаемые параметры, пропущенные обновления и не рекомендуемые методы;</span><span class="sxs-lookup"><span data-stu-id="c9553-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="c9553-111">помощи в диагностике и устранении конкретных проблем.</span><span class="sxs-lookup"><span data-stu-id="c9553-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="c9553-112">Анализатор соответствия рекомендациям предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="c9553-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="c9553-113">минимальные обязательные требования для установки;</span><span class="sxs-lookup"><span data-stu-id="c9553-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="c9553-114">электронное документирование обнаруженных проблем, включая советы по диагностике;</span><span class="sxs-lookup"><span data-stu-id="c9553-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="c9553-115">сведения о конфигурации, которые можно сохранять для последующего просмотра;</span><span class="sxs-lookup"><span data-stu-id="c9553-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="c9553-116">современный анализ системы.</span><span class="sxs-lookup"><span data-stu-id="c9553-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="c9553-117">Анализатор соответствия рекомендациям использует набор XML-файлов конфигурации для определения сведений, которые необходимо собрать из среды Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9553-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="c9553-118">Помимо проверки доменных служб Active Directory, он проверяет такие источники, как системный реестр операционной системы Windows Server и параметры в инструментарии управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="c9553-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="c9553-119">Анализатор соответствия рекомендациям сравнивает собираемые данные с набором предопределенных правил для настроек и конфигураций развертываний Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9553-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="c9553-120">После сравнения собранных данных с предопределенными правилами этот инструмент сообщает о проблемах.</span><span class="sxs-lookup"><span data-stu-id="c9553-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="c9553-121">Для каждой выданной в отчете ошибки анализатор соответствия рекомендациям содержит сведения о том, что было обнаружено в просканированной среде Lync Server 2013 и рекомендуемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c9553-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="c9553-122">Анализатор соответствия рекомендациям также предоставляет ссылки на дополнительные сведения по конкретным проблемам.</span><span class="sxs-lookup"><span data-stu-id="c9553-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9553-123">Lync Server 2013, анализатор соответствия рекомендациям собирает сведения о конфигурации только из компонентов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9553-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="c9553-124">Для анализа предыдущих сред можно использовать предыдущие версии этого инструмента.</span><span class="sxs-lookup"><span data-stu-id="c9553-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="c9553-125">Дополнительные сведения см. <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">в статье требования для запуска анализатора соответствия рекомендациям в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c9553-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

