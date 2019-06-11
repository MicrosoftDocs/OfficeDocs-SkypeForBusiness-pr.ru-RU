---
title: 'Lync Server 2013: начало процесса планирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582769109a3792ddc2efdbef5d4a557b781c39b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="de8ad-102">Начало процесса планирования для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de8ad-102">Beginning the planning process for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de8ad-103">_**Тема последнего изменения:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="de8ad-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="de8ad-104">При планировании локального развертывания унифицированных коммуникаций может показаться интимидатинг, что в Lync Server есть два полезных средства, которые помогут вам.</span><span class="sxs-lookup"><span data-stu-id="de8ad-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="de8ad-105">**Инструмент "планирование"** — это мастер, который представляет собой серию вопросов о вашей организации, функциях Lync Server, которые вы хотите включить, и требования к планированию мощностей.</span><span class="sxs-lookup"><span data-stu-id="de8ad-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="de8ad-106">После этого она создаст рекомендованную топологию развертывания на основе ваших ответов и создаст схему Microsoft Visio для этого развертывания.</span><span class="sxs-lookup"><span data-stu-id="de8ad-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="de8ad-107">**Topology Builder** — это компонент установки Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de8ad-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="de8ad-108">С помощью Topology Builder вы можете создавать, изменять и публиковать запланированные топологии.</span><span class="sxs-lookup"><span data-stu-id="de8ad-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="de8ad-109">Она также проверяет топологию до начала установки сервера.</span><span class="sxs-lookup"><span data-stu-id="de8ad-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="de8ad-110">При установке сервера Lync Server на отдельных серверах серверы проводят опубликованную топологию в рамках процесса установки, и программа установки развертывает сервер в соответствии с топологией.</span><span class="sxs-lookup"><span data-stu-id="de8ad-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="de8ad-111">Средство планирования Lync Server</span><span class="sxs-lookup"><span data-stu-id="de8ad-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="de8ad-112">Средство планирования принимает ответы на вопросы в инструменте и создает топологию на основе руководств и рекомендаций по Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de8ad-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="de8ad-113">Она также предоставляет несколько представлений развертывания на основе ваших ответов.</span><span class="sxs-lookup"><span data-stu-id="de8ad-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="de8ad-114">В нем показано глобальное представление всех сайтов (включая центральные сайты и сайты филиалов), а также подробные представления, в которых показаны серверы и другие компоненты на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="de8ad-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="de8ad-115">Запуск средства планирования не приводит к определению каких – либо конкретных развертываний или запуску каких – либо процессов.</span><span class="sxs-lookup"><span data-stu-id="de8ad-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="de8ad-116">На самом деле запуск средства планирования даже до того, как вы предполагали план, может оказаться очень полезным способом понять вопросы, которые необходимо учитывать в процессе планирования.</span><span class="sxs-lookup"><span data-stu-id="de8ad-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="de8ad-117">Средство планирования можно запускать несколько способами, отвечать на вопросы по-другому и сравнивать результаты.</span><span class="sxs-lookup"><span data-stu-id="de8ad-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="de8ad-118">Если вы обычно удовлетворены макетом, но вам нужно внести изменения, вы можете вернуться к инструменту планирование, загрузить дизайн и внести изменения.</span><span class="sxs-lookup"><span data-stu-id="de8ad-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="de8ad-119">Это займет около 15 минут, чтобы завершить работу с инструментом планирования один раз.</span><span class="sxs-lookup"><span data-stu-id="de8ad-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="de8ad-120">После того как вы удовлетворены, вы можете использовать средство планирования для создания схемы запланированного развертывания.</span><span class="sxs-lookup"><span data-stu-id="de8ad-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="de8ad-121">Вы можете использовать эту схему при создании развертывания в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="de8ad-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de8ad-122">В этом выпуске Lync Server 2013 указана Предварительная версия средства планирования.</span><span class="sxs-lookup"><span data-stu-id="de8ad-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="de8ad-123">Обратите внимание, что числа планирования мощности в средстве планирования являются предварительными и не поддерживаются в окончательном выпуске.</span><span class="sxs-lookup"><span data-stu-id="de8ad-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="de8ad-124">Построитель топологии Lync Server</span><span class="sxs-lookup"><span data-stu-id="de8ad-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="de8ad-125">После того как вы решили свой план развертывания, начните развертывание с помощью Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="de8ad-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="de8ad-126">По завершении вы используете Topology Builder для проверки топологии, а затем, если она пройдет, вы можете опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="de8ad-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="de8ad-127">При публикации топологии Lync Server помещает топологию в хранилище Central Management, которое создается в данный момент, если оно еще не существует.</span><span class="sxs-lookup"><span data-stu-id="de8ad-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="de8ad-128">При установке сервера Lync Server на каждом сервере в развертывании сервер считывает топологию из хранилища Central Management и устанавливается в соответствии с его ролью.</span><span class="sxs-lookup"><span data-stu-id="de8ad-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="de8ad-129">Кроме того, если вы хорошо знакомы с Lync Server и вам нужны менее информативные инструкции, вы можете пропустить средство планирования и использовать мастера в Topology Builder для первоначального проектирования развертывания, а также для проверки и выполнения процедуры публикации.</span><span class="sxs-lookup"><span data-stu-id="de8ad-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="de8ad-130">Использование построителя топологии для планирования и публикации топологии является обязательным шагом.</span><span class="sxs-lookup"><span data-stu-id="de8ad-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="de8ad-131">Вы не можете отказаться от построителя топологии и установить Lync Server отдельно на серверах вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="de8ad-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="de8ad-132">Каждый сервер должен прочитать топологию из проверенной, опубликованной топологии в хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="de8ad-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="de8ad-133">Процесс планирования высокого уровня</span><span class="sxs-lookup"><span data-stu-id="de8ad-133">High-Level Planning Process</span></span>

<span data-ttu-id="de8ad-134">Мы рекомендуем использовать следующий общий процесс для планирования развертывания Lync Server с помощью документации и средства планирования.</span><span class="sxs-lookup"><span data-stu-id="de8ad-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="de8ad-135">Если вы знакомы с предыдущими версиями Lync Server, ознакомьтесь с [новыми возможностями Lync server 2013](lync-server-2013-new-features.md) , чтобы ознакомиться с новыми функциями и требованиями в lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de8ad-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="de8ad-136">Ознакомьтесь с другими разделами, приведенными в этом разделе документации. [основы топологии, которые необходимо знать перед планированием для Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [базовых топологий в Lync Server 2013](lync-server-2013-reference-topologies.md), [первоначальных решений по планированию для Lync Server 2013](lync-server-2013-initial-planning-decisions.md)и [ Клиенты для Lync Server 2013](lync-server-2013-clients.md).</span><span class="sxs-lookup"><span data-stu-id="de8ad-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="de8ad-137">Обратите внимание на решения по планированию, представленные в [эталонной топологии в Lync Server 2013](lync-server-2013-reference-topologies.md).</span><span class="sxs-lookup"><span data-stu-id="de8ad-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="de8ad-138">Теперь, когда вы знакомы с возможностями Lync Server и видами вопросов, на которые необходимо ответить, запустите средство планирования и просмотрите конечную топологию и сведения о ней.</span><span class="sxs-lookup"><span data-stu-id="de8ad-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="de8ad-139">Убедитесь в том, что топология соответствует уникальным требованиям для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="de8ad-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="de8ad-140">Если у вас есть определенные рабочие нагрузки или функции, которые вам интересны или вам нужно изучить, ознакомьтесь с соответствующими разделами [планирования для Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="de8ad-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="de8ad-141">Запустите средство планирования еще раз.</span><span class="sxs-lookup"><span data-stu-id="de8ad-141">Run the Planning Tool again.</span></span> <span data-ttu-id="de8ad-142">Вы можете начать работу с развертыванием, созданным на этапе 3, и изменить результаты или начать с начала.</span><span class="sxs-lookup"><span data-stu-id="de8ad-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="de8ad-143">При необходимости запустите средство планирования в третий раз и повторяйте его до тех пор, пока не будут удовлетворены.</span><span class="sxs-lookup"><span data-stu-id="de8ad-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="de8ad-144">После завершения плана топологии используйте средство планирования для создания и печати схемы Visio вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="de8ad-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="de8ad-145">Вы можете использовать эту распечатку при работе с построителем топологии для ввода топологии.</span><span class="sxs-lookup"><span data-stu-id="de8ad-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="de8ad-146">Прежде чем приступить к развертыванию, прочитайте [Определение требований к системе для Lync server 2013](lync-server-2013-determining-your-system-requirements.md) и [Определение требований к инфраструктуре для Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) , чтобы ознакомиться с необходимыми требованиями и инфраструктурой для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="de8ad-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="de8ad-147">Кроме того, убедитесь в том, что вы прочитали все разделы [планирования для Lync Server 2013](lync-server-2013-planning.md) , которые относятся к рабочим нагрузкам и функциям, которые вы планируете развернуть.</span><span class="sxs-lookup"><span data-stu-id="de8ad-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="de8ad-148">Переход с предыдущих версий</span><span class="sxs-lookup"><span data-stu-id="de8ad-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="de8ad-149">Если вы выполняете миграцию на сервер Lync из предыдущей версии, ознакомьтесь с документацией по [миграции](migration.md) , чтобы получить подробные инструкции по миграции и развертыванию.</span><span class="sxs-lookup"><span data-stu-id="de8ad-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

