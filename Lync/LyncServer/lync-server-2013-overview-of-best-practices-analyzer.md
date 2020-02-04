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
ms.openlocfilehash: 53e63bf6063803364a679a3cc0724ec1cbeae1a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="e5ecb-102">Обзор анализатора соответствия рекомендациям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5ecb-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5ecb-103">_**Тема последнего изменения:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="e5ecb-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="e5ecb-104">Вы можете использовать Lync Server 2013, анализатор соответствия рекомендациям для выявления и устранения проблем, возникающих при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="e5ecb-105">Lync Server 2013, анализатор соответствия рекомендациям собирает сведения о конфигурации из компонентов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="e5ecb-106">При правильном доступе к сети анализатор соответствия рекомендациям может проверять серверы, на которых работают доменные службы Active Directory, единая система обмена сообщениями Exchange Server (UM) и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="e5ecb-107">Анализатор соответствия рекомендациям можно использовать для выполнения указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="e5ecb-108">Упреждающее выполнение проверок, проверка того, что конфигурация задана в соответствии с рекомендованными рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="e5ecb-109">Автоматическое определение необходимых обновлений для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="e5ecb-110">Создание списка проблем, таких как Неоптимальные параметры конфигурации, неподдерживаемые параметры, отсутствующие обновления или рекомендации, которые мы не рекомендуем использовать.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="e5ecb-111">Помощь в устранении неполадок и устранение определенных проблем.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="e5ecb-112">Анализатор соответствия рекомендациям предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="e5ecb-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="e5ecb-113">Минимальные требования для установки.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="e5ecb-114">Интерактивная документация по обнаруженным проблемам, в том числе советы по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="e5ecb-115">Сведения о конфигурации, которые можно сохранить для последующего рецензирования.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="e5ecb-116">Штатный анализ системы.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="e5ecb-117">Анализатор соответствия рекомендациям использует набор XML-файлов конфигурации, чтобы определить, какие данные нужно собирать из среды Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="e5ecb-118">Помимо проверки доменных служб Active Directory, она проверяет источники, такие как реестр операционной системы Windows Server и параметры в инструментарии управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="e5ecb-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="e5ecb-119">Анализатор соответствия рекомендациям сравнивает собираемые данные с набором предопределенных правил для параметров и конфигураций развертываний Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="e5ecb-120">После того как вы сравните собранные данные с предопределенными правилами, средство сообщит о проблемах.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="e5ecb-121">В анализаторе соответствия рекомендациям содержатся сведения о том, что было обнаружено в отсканированной среде Lync Server 2013 и рекомендуемая конфигурация для каждой ошибки.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="e5ecb-122">Анализатор соответствия рекомендациям также содержит ссылки на более подробные сведения о конкретных проблемах.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5ecb-123">Lync Server 2013, анализатор соответствия рекомендациям собирает сведения о конфигурации только из компонентов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="e5ecb-124">Вы можете использовать предыдущие версии средства для поиска предыдущих сред.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="e5ecb-125">Дополнительные сведения можно найти <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">в разделе Требования для анализатора соответствия рекомендациям в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e5ecb-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

