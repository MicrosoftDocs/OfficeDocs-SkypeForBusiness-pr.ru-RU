---
title: 'Lync Server 2013: рекомендации для сред Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d02d9ed669cf9404b1bf8d07db32c9d331769ec9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="3dde2-102">Рекомендации по работе с средами Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dde2-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dde2-103">_**Последнее изменение темы:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="3dde2-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="3dde2-104">К текущим операциям системы следует применять следующие общие принципы:</span><span class="sxs-lookup"><span data-stu-id="3dde2-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="3dde2-105">**Общие сведения и использование MOF**   MOF — это набор рекомендаций, принципов и моделей, которые предоставляют организациям технические рекомендации по управлению ИТ-ресурсами, например, ежедневных операций Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3dde2-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="3dde2-106">Следующие рекомендации по MOF могут помочь в достижении критической надежности, доступности, поддержки и управляемости продуктов корпорации Майкрософт для производственной системы.</span><span class="sxs-lookup"><span data-stu-id="3dde2-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="3dde2-107">Дополнительные сведения см. в [статье Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span><span class="sxs-lookup"><span data-stu-id="3dde2-107">For more information, see [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="3dde2-108">**Ознакомьтесь с рекомендациями по Lync Server 2013**   мы рекомендуем реализовать практические и проверенные процедуры для управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3dde2-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="3dde2-109">Использование проверенных, проверенных и документированных методов управления операциями может оказаться более эффективным, чем разработка собственных методов.</span><span class="sxs-lookup"><span data-stu-id="3dde2-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="3dde2-110">**Разделяйте операции на ежедневные, еженедельные и ежемесячные процессы**   , задокументируйте необходимые операционные задачи, которые будут регулярно выполняться.</span><span class="sxs-lookup"><span data-stu-id="3dde2-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="3dde2-111">Сведения о том, как выполнять задачи, помогут убедиться в том, что ваши сведения сохраняются при изменении рабочей среды, например при развертывании новых технологий или при изменении персонала.</span><span class="sxs-lookup"><span data-stu-id="3dde2-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="3dde2-112">Рекомендуется разделить операционные задачи на управляемые рабочие нагрузки, в которых задачи выполняются ежедневно, еженедельно и ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="3dde2-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="3dde2-113">Ежедневные задачи приведут к работе с системой, а ежемесячные задачи приведут к большему числу долгосрочной работоспособности системы.</span><span class="sxs-lookup"><span data-stu-id="3dde2-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="3dde2-114">Этот документ можно использовать в средах для развертывания только компонентов обмена мгновенными сообщениями и присутствия (IM/P) или обмена мгновенными сообщениями с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="3dde2-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="3dde2-115">Если задачи или контрольный список относятся к корпоративной голосовой связи, это упоминается, и если ваша среда не включает корпоративную голосовую связь, часть может быть пропущена.</span><span class="sxs-lookup"><span data-stu-id="3dde2-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="3dde2-116">**Deploy Tools, необходимое для работы с Lync Server 2013**   многие средства помогут вам устранить проблемы, автоматизировать задачи и отслеживать и поддерживать среду Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3dde2-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="3dde2-117">Определите стандартный набор средств для Организации, чтобы задачи, выполняемые Группой операций, выполнялись правильно, эффективно, согласованно и контролироваться.</span><span class="sxs-lookup"><span data-stu-id="3dde2-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="3dde2-118">Также следует реализовать процессы для отслеживания непредвиденных ситуаций и существенных изменений конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3dde2-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="3dde2-119">Справка</span><span class="sxs-lookup"><span data-stu-id="3dde2-119">Reference</span></span>

<span data-ttu-id="3dde2-120">Чтобы воспользоваться преимуществами читателей, еще не знакомых с основами управления серверами в целом, мы предоставляем обзор методик управления сервером.</span><span class="sxs-lookup"><span data-stu-id="3dde2-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="3dde2-121">Читатели, уже знакомые с управлением сервером, могут пропустить этот раздел.</span><span class="sxs-lookup"><span data-stu-id="3dde2-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="3dde2-122">Рекомендации — это рекомендации, основанные на знаний и опыте, которые ИТ-специалисты побрали во многих средах.</span><span class="sxs-lookup"><span data-stu-id="3dde2-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="3dde2-123">Они предоставляют стандартные процедуры для типичных задач, которые администраторы Lync Server должны выполнять ежедневно, а также перечисление средств, которые следует использовать для управления средой Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3dde2-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="3dde2-124">К типичным задачам для администраторов Lync относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="3dde2-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="3dde2-125">**Управление емкостью и**   обеспечением доступности определите, как и какие меры необходимо оценить для предсказания будущих требований к емкости, а также для создания отчетов о емкости, надежности и доступности систем.</span><span class="sxs-lookup"><span data-stu-id="3dde2-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="3dde2-126">Необходимо убедиться в том, что размер серверов, на которых работает Lync Server, для обработки нагрузки на систему, а также что незапланированные простои хранятся на уровнях, определенных в соглашении об уровне обслуживания (SLA).</span><span class="sxs-lookup"><span data-stu-id="3dde2-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="3dde2-127">Кроме того, необходимо обновить оборудование, чтобы оно продолжало соответствовать определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="3dde2-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="3dde2-128">**Управление изменениями и управление**   конфигурацией управляют внесением изменений в системы ИТ.</span><span class="sxs-lookup"><span data-stu-id="3dde2-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="3dde2-129">К ним относятся тестирование, Отзывы о приложениях и планы на непредвиденные случаи, документация по всем изменениям и одобрение управления в случае возникновения проблем.</span><span class="sxs-lookup"><span data-stu-id="3dde2-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="3dde2-130">Храните записи о программном обеспечении и аппаратных ресурсах и их конфигурациях.</span><span class="sxs-lookup"><span data-stu-id="3dde2-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="3dde2-131">\*\*\*\*   Стандартные методы структуры администрирования системы для работы с административными задачами, такими как администрирование баз данных и администрирование сайтов.</span><span class="sxs-lookup"><span data-stu-id="3dde2-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="3dde2-132">**Администратор безопасности имеет**   подробные сведения о политике и плане защиты конфиденциальности данных, целостности данных и доступности данных ИТ – инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="3dde2-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="3dde2-133">Это относится к повседневным действиям и задачам, связанным с обслуживанием и настройкой инфраструктуры безопасности ИТ.</span><span class="sxs-lookup"><span data-stu-id="3dde2-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="3dde2-134">**В разделе Устранение неполадок**   структуры описаны методы для работы с неожиданными проблемами, включая действия по предотвращению подобных проблем в будущем.</span><span class="sxs-lookup"><span data-stu-id="3dde2-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="3dde2-135">**Соглашения об уровне обслуживания**   обеспечивают набор целей для производительности ИТ – систем и регулярно измеряют производительность по сравнению с этими целями.</span><span class="sxs-lookup"><span data-stu-id="3dde2-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="3dde2-136">\*\*\*\*   Стандартные процедуры документирования документации, такие как сведения о конфигурации и изученные уроки, и делают их доступными для сотрудников, которым они нужны.</span><span class="sxs-lookup"><span data-stu-id="3dde2-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="3dde2-137">После внесения изменений в конфигурацию Обновите документацию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="3dde2-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="3dde2-138">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3dde2-138">Related Sections</span></span>

<span data-ttu-id="3dde2-139">Прежде чем продолжить, ознакомьтесь со следующими разделами, посвященными системным операциям:</span><span class="sxs-lookup"><span data-stu-id="3dde2-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="3dde2-140">Управление емкостью и доступностью в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dde2-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="3dde2-141">Управление изменениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dde2-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="3dde2-142">Управление конфигурацией в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dde2-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="3dde2-143">Администрирование системы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dde2-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="3dde2-144">Соглашения об уровне обслуживания в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dde2-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="3dde2-145">Документация в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dde2-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="3dde2-146">Стандартные процедуры в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dde2-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="3dde2-147">Экстренные процедуры в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dde2-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3dde2-148">См. также</span><span class="sxs-lookup"><span data-stu-id="3dde2-148">See Also</span></span>


[<span data-ttu-id="3dde2-149">Microsoft Operations Framework 4,0</span><span class="sxs-lookup"><span data-stu-id="3dde2-149">Microsoft Operations Framework 4.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

