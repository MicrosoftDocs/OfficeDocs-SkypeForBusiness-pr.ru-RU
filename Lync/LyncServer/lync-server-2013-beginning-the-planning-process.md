---
title: 'Lync Server 2013: начало процесса планирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd0a83042415cd2cf919d0fd66fe5309a4cae9e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="802d6-102">Начало процесса планирования для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="802d6-102">Beginning the planning process for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="802d6-103">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="802d6-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="802d6-104">При планировании локального развертывания единой системы обмена сообщениями может показаться, что запугивать, Lync Server предоставляет два полезных средства, которые помогут вам:</span><span class="sxs-lookup"><span data-stu-id="802d6-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="802d6-105">**Средство планирования** — это мастер, который предоставляет ряд вопросов о вашей организации, функции Lync Server, которые необходимо включить, и требования к планированию мощности.</span><span class="sxs-lookup"><span data-stu-id="802d6-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="802d6-106">Затем на основе ответов мастер создает рекомендуемую топологию развертывания и схему такого развертывания в формате Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="802d6-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="802d6-107">**Построитель топологий** — это компонент установки Lync Server.</span><span class="sxs-lookup"><span data-stu-id="802d6-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="802d6-108">Построитель топологий используется для создания, настройки и публикации запланированной топологии.</span><span class="sxs-lookup"><span data-stu-id="802d6-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="802d6-109">Также он проверяет вашу топологию до начала установки серверов.</span><span class="sxs-lookup"><span data-stu-id="802d6-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="802d6-110">При установке Lync Server на отдельных серверах серверы просчитываются опубликованную топологию как часть процесса установки, а программа установки развертывает сервер в соответствии с топологией.</span><span class="sxs-lookup"><span data-stu-id="802d6-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="802d6-111">Средство планирования Lync Server</span><span class="sxs-lookup"><span data-stu-id="802d6-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="802d6-112">Средство планирования принимает ответы на вопросы в инструменте и создает топологию на основе рекомендаций Lync Server и рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="802d6-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="802d6-113">В нем также представлено несколько представлений развертывания на основе ваших ответов.</span><span class="sxs-lookup"><span data-stu-id="802d6-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="802d6-114">В нем показано глобальное представление всех сайтов (то есть, включая центральные сайты и сайты филиалов), а также подробные представления, показывающие серверы и другие компоненты на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="802d6-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="802d6-115">Запуск средства планирования не приводит к определенному развертыванию или инициации каких бы то ни было процессов.</span><span class="sxs-lookup"><span data-stu-id="802d6-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="802d6-116">На самом деле, запуск средства планирования даже до того, как план утвержденного плана может быть очень полезен, чтобы узнать о видах вопросов, которые необходимо учитывать в процессе планирования.</span><span class="sxs-lookup"><span data-stu-id="802d6-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="802d6-117">Средство планирования можно запускать несколько раз, отвечать на вопросы по-разному и сравнивать результаты.</span><span class="sxs-lookup"><span data-stu-id="802d6-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="802d6-118">Если у вас есть макет, который обычно удовлетворяет, но вам нужно внести изменения, вы можете вернуться к средству планирования, загрузить проект и внести изменения.</span><span class="sxs-lookup"><span data-stu-id="802d6-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="802d6-119">Для завершения работы средства планирования потребуется около 15 минут.</span><span class="sxs-lookup"><span data-stu-id="802d6-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="802d6-120">После того как вы удовлетворены, вы можете использовать средство планирования для создания схемы запланированного развертывания.</span><span class="sxs-lookup"><span data-stu-id="802d6-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="802d6-121">Вы можете использовать эту схему при создании развертывания в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="802d6-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="802d6-122">В этом выпуске Lync Server 2013 используется предварительная версия средства планирования.</span><span class="sxs-lookup"><span data-stu-id="802d6-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="802d6-123">Обратите внимание, что числа планирования мощности в средстве планирования являются предварительными и не поддерживаются в окончательном выпуске.</span><span class="sxs-lookup"><span data-stu-id="802d6-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="802d6-124">Построитель топологий Lync Server</span><span class="sxs-lookup"><span data-stu-id="802d6-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="802d6-125">Определив план развертывания, вы можете начать развертывание с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="802d6-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="802d6-126">По завершении вы можете использовать построитель топологий для проверки топологии, а затем, если она пройдена, вы можете опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="802d6-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="802d6-127">При публикации топологии Lync Server помещает топологию в центральное хранилище управления, которое создается в данный момент, если оно еще не существует.</span><span class="sxs-lookup"><span data-stu-id="802d6-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="802d6-128">При установке Lync Server на каждом сервере в развертывании сервер считывает топологию из центрального хранилища управления и устанавливается в соответствии с его ролью в развертывании.</span><span class="sxs-lookup"><span data-stu-id="802d6-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="802d6-129">Кроме того, если вы знакомы с Lync Server и вам не нужны более краткие рекомендации, вы можете пропустить средство планирования и использовать мастера в построителе топологий для первоначального дизайна развертывания, а также для проверки и публикации.</span><span class="sxs-lookup"><span data-stu-id="802d6-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="802d6-130">Использование построителя топологий для планирования и публикации топологии является обязательным этапом.</span><span class="sxs-lookup"><span data-stu-id="802d6-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="802d6-131">Вы не можете обходить построитель топологий и устанавливать Lync Server отдельно на серверах в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="802d6-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="802d6-132">Каждый сервер должен считать топологию из проверенной, опубликованной топологии в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="802d6-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="802d6-133">Высокоуровневый процесс планирования</span><span class="sxs-lookup"><span data-stu-id="802d6-133">High-Level Planning Process</span></span>

<span data-ttu-id="802d6-134">Мы рекомендуем использовать следующую общую процедуру для планирования развертывания Lync Server как в документации, так и в средстве планирования.</span><span class="sxs-lookup"><span data-stu-id="802d6-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="802d6-135">Если вы знакомы с предыдущими версиями Lync Server, ознакомьтесь с [новыми функциями Lync server 2013](lync-server-2013-new-features.md) , чтобы ознакомиться с новыми функциями и требованиями в lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="802d6-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="802d6-136">Прочитайте другие темы, приведенные в этом разделе документации: [основы топологии, которые необходимо знать перед планированием для Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [эталонные топологии в Lync Server 2013](lync-server-2013-reference-topologies.md), [начальные решения по планированию для Lync Server 2013](lync-server-2013-initial-planning-decisions.md)и [клиенты для Lync Server 2013](lync-server-2013-clients.md).</span><span class="sxs-lookup"><span data-stu-id="802d6-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="802d6-137">Обратите внимание на решения по планированию, представленные в [эталонных топологиях в Lync Server 2013](lync-server-2013-reference-topologies.md).</span><span class="sxs-lookup"><span data-stu-id="802d6-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="802d6-138">Теперь, когда вы знакомы с функциями Lync Server и видами вопросов, на которые необходимо ответить, запустите средство планирования и просмотрите полученную топологию и сведения о ней.</span><span class="sxs-lookup"><span data-stu-id="802d6-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="802d6-139">Убедитесь, что топология соответствует уникальным требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="802d6-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="802d6-140">Если у вас есть определенные рабочие нагрузки или интересующие вас функции, ознакомьтесь с соответствующими разделами, посвященными [планированию для Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="802d6-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="802d6-141">Снова запустите средство планирования.</span><span class="sxs-lookup"><span data-stu-id="802d6-141">Run the Planning Tool again.</span></span> <span data-ttu-id="802d6-142">Вы можете начать с развертывания, созданного на этапе 3, и изменить полученные данные или начать с самого начала.</span><span class="sxs-lookup"><span data-stu-id="802d6-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="802d6-143">При необходимости запустите средство планирования в третий раз и повторяйте его до тех пор, пока не будет удовлетворен выход.</span><span class="sxs-lookup"><span data-stu-id="802d6-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="802d6-144">После завершения плана топологии используйте средство планирования для создания и печати схемы Visio вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="802d6-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="802d6-145">Вы можете использовать эту распечатку при работе с построителем топологий для ввода топологии.</span><span class="sxs-lookup"><span data-stu-id="802d6-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="802d6-146">Прежде чем приступать к развертыванию, прочтите статью [Определение требований к системе для Lync server 2013](lync-server-2013-determining-your-system-requirements.md) и [Определение требований к инфраструктуре для Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) , чтобы ознакомиться с предварительными требованиями и необходимой инфраструктурой для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="802d6-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="802d6-147">Кроме того, ознакомьтесь со всеми разделами [планирования для Lync Server 2013](lync-server-2013-planning.md) , которые относятся к рабочим нагрузкам и функциям, которые планируется развернуть.</span><span class="sxs-lookup"><span data-stu-id="802d6-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="802d6-148">Миграция с предыдущих версий</span><span class="sxs-lookup"><span data-stu-id="802d6-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="802d6-149">Если вы переноситесь на сервер Lync Server из предыдущей версии, ознакомьтесь с документацией по [миграции](migration.md) , чтобы получить конкретные инструкции по миграции и развертыванию.</span><span class="sxs-lookup"><span data-stu-id="802d6-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

