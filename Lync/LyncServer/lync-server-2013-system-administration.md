---
title: 'Lync Server 2013: Системное администрирование'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e910da744bf88b485fc693c02544ad8a7093ead
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="c26f4-102">Администрирование системы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c26f4-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c26f4-103">_**Последнее изменение темы:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="c26f4-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="c26f4-104">Системное администрирование включает повседневные административные задачи, как запланированные, так и по требованию, которые необходимы для обеспечения бесперебойной работы системы.</span><span class="sxs-lookup"><span data-stu-id="c26f4-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="c26f4-105">Как правило, для задач по администрированию системы используются написанные процедуры.</span><span class="sxs-lookup"><span data-stu-id="c26f4-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="c26f4-106">Эти процедуры гарантируют, что одни и те же стандартные средства и методы используются всеми сотрудниками службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="c26f4-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="c26f4-107">В среде Lync типичные задачи по администрированию системы включают резервное копирование и архивацию пулов, мониторинг журналов, создание пользователей и управление ими, а также обновление антивирусного программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="c26f4-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="c26f4-108">Устранение неполадок системы</span><span class="sxs-lookup"><span data-stu-id="c26f4-108">System troubleshooting</span></span>

<span data-ttu-id="c26f4-109">Организация должна быть подготовлена к работе с непредвиденными проблемами и должна содержать процедуру по управлению проблемами с момента их устранения.</span><span class="sxs-lookup"><span data-stu-id="c26f4-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="c26f4-110">Сведения о том, как сотрудники службы поддержки определили проблемы, которые необходимо записать и использовать в будущем, чтобы избежать ненужной повторяющейся выполненной работы.</span><span class="sxs-lookup"><span data-stu-id="c26f4-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="c26f4-111">Процесс устранения неполадок системы</span><span class="sxs-lookup"><span data-stu-id="c26f4-111">System troubleshooting process</span></span>

<span data-ttu-id="c26f4-112">На следующей схеме показан процесс устранения неполадок системы и взаимодействия с другими ролями операций.</span><span class="sxs-lookup"><span data-stu-id="c26f4-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="c26f4-113">**Блок-схема устранения неполадок системы**</span><span class="sxs-lookup"><span data-stu-id="c26f4-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="c26f4-114">![Блок-схема устранения неполадок системы](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Блок-схема устранения неполадок системы")</span><span class="sxs-lookup"><span data-stu-id="c26f4-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="c26f4-115">**Классификация и определение приоритетов**   эта задача обычно выполняется службой Service Desk.</span><span class="sxs-lookup"><span data-stu-id="c26f4-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="c26f4-116">Например, ошибка может быть сгруппирована как ошибка программного обеспечения или аппаратная ошибка.</span><span class="sxs-lookup"><span data-stu-id="c26f4-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="c26f4-117">Затем эта ошибка перенаправляется в соответствующую группу поддержки для изучения.</span><span class="sxs-lookup"><span data-stu-id="c26f4-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="c26f4-118">Правила определения приоритета проблемы, а также время для ответа и время для разрешения, обычно определяются в соглашении об уровне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="c26f4-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="c26f4-119">**Изучите и выявите**   соответствующую команду поддержки, чтобы решить проблему и предложить изменения, необходимые для устранения проблемы.</span><span class="sxs-lookup"><span data-stu-id="c26f4-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="c26f4-120">Если решение является простым и не нуждается в контроле изменений, решение можно применить немедленно.</span><span class="sxs-lookup"><span data-stu-id="c26f4-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="c26f4-121">Если решение непростое, должно быть вызвано требование на изменение, а в процессе управления изменениями, как правило, используется процедура "Fast-Track".</span><span class="sxs-lookup"><span data-stu-id="c26f4-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="c26f4-122">Все внесенные изменения необходимо записать с помощью процесса управления конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="c26f4-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="c26f4-123">**Закрытие и запись**   после проверки решения проблемы необходимо закрыть.</span><span class="sxs-lookup"><span data-stu-id="c26f4-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="c26f4-124">Если есть уроки, которые следует изучить из этой ситуации, в базе знаний необходимо создать запись.</span><span class="sxs-lookup"><span data-stu-id="c26f4-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="c26f4-125">\*\*\*\*   Для определения тенденций проблем следует выполнить анализ и анализ периодических просмотров последних проблем.</span><span class="sxs-lookup"><span data-stu-id="c26f4-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="c26f4-126">Например, если у пользователей часто возникают проблемы с медленным входом на сайты Lync, это может быть вызвано проблемами с пропускной способностью сети.</span><span class="sxs-lookup"><span data-stu-id="c26f4-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="c26f4-127">Устранение проблем с устранением проблем, а также результат, влияющий на доступность системы, и их сравнение с соглашением об уровне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="c26f4-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="c26f4-128">Пользователь, взаимодействует с клиентом при возникновении проблем со службой, таких как менеджер по работе с учетными записями, должен сообщить о значительных проблемах.</span><span class="sxs-lookup"><span data-stu-id="c26f4-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="c26f4-129">Средства управления проблемами</span><span class="sxs-lookup"><span data-stu-id="c26f4-129">Issue management tools</span></span>

<span data-ttu-id="c26f4-130">Средства службы поддержки позволяют сотрудникам записывать, классифицировать и определять приоритет новых проблем.</span><span class="sxs-lookup"><span data-stu-id="c26f4-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="c26f4-131">Затем средства предоставляют рабочие процессы для управления запросом на обслуживание проблемы с помощью расследования и диагностики, как правило, с помощью более одной команды поддержки.</span><span class="sxs-lookup"><span data-stu-id="c26f4-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="c26f4-132">Средства, которые часто предоставляют отчеты о времени разрешения и прошлых тенденциях, также могут включать базу данных базы знаний, которая может использоваться для поиска в прошлых вопросах.</span><span class="sxs-lookup"><span data-stu-id="c26f4-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="c26f4-133">База знаний Майкрософт — это полезная запись проблем поддержки, обнаруженных корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c26f4-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="c26f4-134">Для получения дополнительных сведений посетите веб-сайт поддержки Майкрософт<https://go.microsoft.com/fwlink/?linkid=14898>().</span><span class="sxs-lookup"><span data-stu-id="c26f4-134">For more information, see the Microsoft Support website (<https://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="c26f4-135">Программное обеспечение сторонних производителей обычно требует настройки в соответствии с потребностями Организации, такими как Организация Teams, требования к отчетности и меры, необходимые для соглашения об уровне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="c26f4-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="c26f4-136">Централизованное и децентрализованное администрирование</span><span class="sxs-lookup"><span data-stu-id="c26f4-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="c26f4-137">Роли и обязанности по выполнению задач системы администрирования зависят от того, соответствует ли Организация централизованной модели, децентрализованной модели или их комбинации.</span><span class="sxs-lookup"><span data-stu-id="c26f4-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="c26f4-138">**Централизованная модель**   централизованной модели одна или несколько административных групп обеспечивают полный контроль над всей средой Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c26f4-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="c26f4-139">Эта административная модель напоминает центр обработки данных, в котором все задачи администрирования выполняются одной группой информационных технологий.</span><span class="sxs-lookup"><span data-stu-id="c26f4-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="c26f4-140">Роли и ответственность в группе должны определяться в соответствии с опытом и квалификацией.</span><span class="sxs-lookup"><span data-stu-id="c26f4-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="c26f4-141">**Децентрализованная модель**   децентрализованных организаций размещается в нескольких географических расположениях и работает с серверами Lync Server и Teams в различных расположениях.</span><span class="sxs-lookup"><span data-stu-id="c26f4-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="c26f4-142">Например, для каждой страны или региона может быть местный персонал администрирования и один или несколько серверов, на которых работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c26f4-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="c26f4-143">Возможно также, что существует пул серверов, на которых работает Lync Server 2013 и административная группа для Северной Америки и одна для Европы.</span><span class="sxs-lookup"><span data-stu-id="c26f4-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="c26f4-144">Иногда администраторы могут быть ответственны только за собственную географическую область и ограничивать разрешения на администрирование ресурсов в других областях.</span><span class="sxs-lookup"><span data-stu-id="c26f4-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="c26f4-145">Lync Server также позволяет делегировать конкретные задачи администрирования определенным пользователям или группам с помощью управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="c26f4-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="c26f4-146">RBAC позволяет администраторам делегировать определенные права пользователей и разрешения другим администраторам для выполнения подмножества возможных административных задач.</span><span class="sxs-lookup"><span data-stu-id="c26f4-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="c26f4-147">С помощью RBAC пользователи могут выполнять определенные задачи администрирования, зависящие от ролей RBAC, назначенных пользователю.</span><span class="sxs-lookup"><span data-stu-id="c26f4-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="c26f4-148">RBAC предоставляет список командлетов, которые пользователь может запускать на основе ролей RBAC, участником которых является пользователь.</span><span class="sxs-lookup"><span data-stu-id="c26f4-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

