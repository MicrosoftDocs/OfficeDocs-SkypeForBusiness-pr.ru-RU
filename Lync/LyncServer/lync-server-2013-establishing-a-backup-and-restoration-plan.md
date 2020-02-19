---
title: 'Lync Server 2013: Установка плана резервного копирования и восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0edc085ae57c8d261111726768b8ca3309c87dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="8fb9a-102">Создание плана резервного копирования и восстановления для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fb9a-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fb9a-103">_**Последнее изменение темы:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="8fb9a-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="8fb9a-104">Создание плана резервного копирования и восстановления состоит из следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="8fb9a-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="8fb9a-105">Разработка плана.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-105">Developing the plan.</span></span>

  - <span data-ttu-id="8fb9a-106">Реализация плана.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-106">Implementing the plan.</span></span>

  - <span data-ttu-id="8fb9a-107">Обслуживание плана.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="8fb9a-108">Разработка плана резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="8fb9a-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="8fb9a-109">После того как вы разрабатываете стратегию резервного копирования и восстановления для Lync Server, используйте ее для документирования подробного плана резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="8fb9a-110">Ваш план должен ясно передавать приоритеты и требования для резервного копирования данных и параметров.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="8fb9a-111">Вы можете использовать информацию о [создании стратегии резервного копирования и восстановления для Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) и таблиц в [таблицах резервного копирования и восстановления для Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) , чтобы упростить документацию по стратегии.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="8fb9a-112">План также должен содержать критерии, позволяющие решить, когда и как восстанавливать службу.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="8fb9a-113">При разработке плана необходимо учесть следующие условия, а также учесть следующие условия.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="8fb9a-114">Как будут восстанавливаться серверы на новом оборудовании.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="8fb9a-115">Способ восстановления служб, требующих действия, в части нескольких бизнес-областей или отделов.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="8fb9a-116">Как быстро можно получить резервные серверы.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="8fb9a-117">Время, необходимое для восстановления с помощью стратегии.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="8fb9a-118">Рассмотрите требования Организации к целевому времени восстановления (RTO).</span><span class="sxs-lookup"><span data-stu-id="8fb9a-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="8fb9a-119">Изменяйте процедуры резервного копирования и восстановления в этом разделе, добавляя и удаляя необходимые процедуры для отражения серверов и компонентов в развертывании.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="8fb9a-120">Вы также можете добавить соответствующие сведения, такие как расписание резервного копирования, в соответствующие процедуры, чтобы убедиться, что информация не отображается.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8fb9a-121">Рекомендуется создавать скрипты для максимально возможного количества действий, чтобы обеспечить качество и репродуЦибилити процедур.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="8fb9a-122">В своем плане укажите, кто отвечает за просмотр плана, кто отвечает за тестирование и проверку новых процедур и средств, а также кто должен утверждать изменения в плане и связанных процедурах.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="8fb9a-123">Чтобы убедиться в том, что план резервного копирования и восстановления полностью соответствует всем установленным целям и приоритетам, прежде чем приступать к внедрению плана, ознакомьтесь с утверждением соответствующих ответственных за принятие бизнес-решений и специалистами по техническим решениям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="8fb9a-124">Реализация плана резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="8fb9a-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="8fb9a-125">Для реализации плана резервного копирования и восстановления необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8fb9a-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="8fb9a-126">Тестирование и проверка плана.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="8fb9a-127">Связь с планом.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-127">Communicating the plan.</span></span>

  - <span data-ttu-id="8fb9a-128">Проверка операций резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="8fb9a-129">Тестирование и проверка плана</span><span class="sxs-lookup"><span data-stu-id="8fb9a-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="8fb9a-130">Описанные здесь процедуры были протестированы и проверены в лабораторной среде.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="8fb9a-131">Чтобы убедиться, что эти или другие процедуры работают в вашей среде, необходимо протестировать и проверить каждую процедуру, которую планируется реализовать.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="8fb9a-132">Прополните тестирование и проверку перед отправкой плана для окончательного утверждения.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="8fb9a-133">Связь с планом</span><span class="sxs-lookup"><span data-stu-id="8fb9a-133">Communicating the Plan</span></span>

<span data-ttu-id="8fb9a-134">План резервного копирования и восстановления должен ясно описать, кто реализует процедуры и пошаговые инструкции по выполнению процедур.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="8fb9a-135">Необходимо убедиться, что все, кто отвечает за любой аспект резервного копирования и восстановления, понимают план, как он должен быть реализован и какова его роль.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="8fb9a-136">Сюда входят все требования к реализации для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="8fb9a-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="8fb9a-137">Резервное копирование пула и сервера.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-137">Pool and server backup.</span></span>

  - <span data-ttu-id="8fb9a-138">Восстановление службы.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-138">Restoration of service.</span></span>

<span data-ttu-id="8fb9a-139">**Резервное копирование пула и сервера**</span><span class="sxs-lookup"><span data-stu-id="8fb9a-139">**Pool and server backup**</span></span>

<span data-ttu-id="8fb9a-140">План резервного копирования и восстановления должен включать все сведения, необходимые для выполнения процедур резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-140">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis.</span></span> <span data-ttu-id="8fb9a-141">Основные сведения, которые будут переданы ответственным участникам группы, включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="8fb9a-141">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="8fb9a-142">Группа или пользователь (указанный как отдельный пользователь или роль), отвечающий за резервное копирование каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="8fb9a-143">Конкретные расписания резервного копирования каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="8fb9a-144">Расположения резервных копий для каждого типа данных (параметры, базы данных и файловые ресурсы).</span><span class="sxs-lookup"><span data-stu-id="8fb9a-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="8fb9a-145">Процедуры резервного копирования, которые необходимо использовать, в том числе инструменты, необходимые для выполнения каждой процедуры.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="8fb9a-146">Сведения, необходимые для выполнения резервного копирования, как описано в [таблицах резервного копирования и восстановления для Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="8fb9a-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="8fb9a-147">Методы проверки, обеспечивающие правильную резервное копирование данных и параметров, а также возможность восстановления, в том числе периодическое и тестовое восстановление.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="8fb9a-148">**Восстановление службы**</span><span class="sxs-lookup"><span data-stu-id="8fb9a-148">**Restoration of service**</span></span>

<span data-ttu-id="8fb9a-149">План резервного копирования и восстановления должен включать всю информацию, необходимую для восстановления службы, в случае, если один или несколько серверов применяют потерю, которая делает службу недоступной.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="8fb9a-150">Основные сведения, которые будут переданы ответственным участникам группы, включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="8fb9a-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="8fb9a-151">Группа или пользователь (заданный в качестве отдельного пользователя или роли), отвечающий за определение того, когда требуется восстановление службы, и процедуры, которые необходимо использовать для восстановления службы, а также группы или лица, ответственные за реализацию процедур для каждого сценарий восстановления.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="8fb9a-152">Критерии для определения процедур восстановления, наиболее подходящих для конкретной ситуации.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="8fb9a-153">Оценка времени для восстановления цели обслуживания и времени восстановления (RTO) в каждом сценарии восстановления.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="8fb9a-154">Используемые процедуры восстановления, в том числе инструменты, необходимые для выполнения каждой процедуры.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="8fb9a-155">Сведения, необходимые для восстановления данных и параметров.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-155">Information required to restore data and settings.</span></span> <span data-ttu-id="8fb9a-156">Таблицы представлены в [таблицах резервного копирования и восстановления для Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="8fb9a-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="8fb9a-157">Проверка операций резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="8fb9a-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="8fb9a-158">После выполнения начальных действий по резервному копированию в рабочей среде и заданных интервалах (как описано в плане резервного копирования и восстановления) необходимо проверить следующее:</span><span class="sxs-lookup"><span data-stu-id="8fb9a-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="8fb9a-159">Резервные копии происходят по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="8fb9a-160">Резервные данные и параметры доступны для чтения.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="8fb9a-161">Процедуры восстановления можно выполнить в пределах целевого значения времени восстановления (RTO), указанного в плане резервного копирования и восстановления, а результаты удовлетворяют всем бизнес-требованиям.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="8fb9a-162">Резервные листы заполнены и проверены и хранятся в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="8fb9a-163">Эти листы предоставляются в [таблицах резервного копирования и восстановления для Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="8fb9a-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="8fb9a-164">Процедуры восстановления были протестированы и проверены на работу должным образом, как указано в плане резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="8fb9a-165">Обслуживание плана резервного копирования и восстановления</span><span class="sxs-lookup"><span data-stu-id="8fb9a-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="8fb9a-166">Топология Lync Server — это динамическая среда, которая изменяется в Организации.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="8fb9a-167">Оцените план резервного копирования и восстановления в соответствии с изменениями Организации и периодически изучите его, чтобы убедиться, что он продолжает отвечать потребностям вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8fb9a-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

