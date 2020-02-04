---
title: 'Lync Server 2013: советы и рекомендации по работе с серверными средами Lync'
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
ms.openlocfilehash: bf207f4cd0303330ccb01dc56e28b949c1df22f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="879bd-102">Рекомендации по работе с средами Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="879bd-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="879bd-103">_**Тема последнего изменения:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="879bd-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="879bd-104">Следующие общие принципы должны применяться к текущим операциям системы:</span><span class="sxs-lookup"><span data-stu-id="879bd-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="879bd-105">**Общие сведения и использование MOF**   MOF — это набор рекомендаций, принципов и моделей, которые предоставляют организациям технические рекомендации по управлению ИТ-ресурсами, например, ежедневных операций Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="879bd-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="879bd-106">Ниже приведены рекомендации по использованию MOF, которые помогут вам добиться критической надежности, доступности, обеспечения поддержки и управляемости продуктов Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="879bd-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="879bd-107">Дополнительные сведения можно найти в разделе [Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span><span class="sxs-lookup"><span data-stu-id="879bd-107">For more information, see [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="879bd-108">**Ознакомьтесь**   с рекомендациями по работе с Lync Server 2013 мы рекомендуем реализовать практичные и проверенные процедуры для управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="879bd-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="879bd-109">Использование проверенных, протестированных и документированных методов управления операциями может быть более эффективной, чем разработка собственных методов.</span><span class="sxs-lookup"><span data-stu-id="879bd-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="879bd-110">**Разделяйте операции на ежедневные, еженедельные и ежемесячные процессы**   , задокументируйте необходимые рабочие задачи, которые будут регулярно выполняться.</span><span class="sxs-lookup"><span data-stu-id="879bd-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="879bd-111">Сведения о том, как выполнять задачи, помогают удостовериться в том, что информация сохраняется при изменении в рабочей среде, например при развертывании новых технологий или изменении штатных обязанностей.</span><span class="sxs-lookup"><span data-stu-id="879bd-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="879bd-112">Рекомендуется разделить операционные задачи на управляемые рабочие нагрузки, где задачи выполняются ежедневно, еженедельно и ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="879bd-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="879bd-113">Ежедневные задачи будут сосредоточиться на работе системы, а ежемесячные задачи — сосредоточиться на долгосрочной работоспособности системы.</span><span class="sxs-lookup"><span data-stu-id="879bd-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="879bd-114">Этот документ можно использовать в средах, в которых развертываются только компоненты обмена мгновенными сообщениями и присутствия (IM/P), а также обмен мгновенными сообщениями с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="879bd-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="879bd-115">Если задачи или контрольный список относятся к корпоративной голосовой связи, это упомянуто, и если в вашей среде не указана корпоративная голосовая связь, часть может быть пропущена.</span><span class="sxs-lookup"><span data-stu-id="879bd-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="879bd-116">**Развертывание средств, необходимых для работы в Lync Server 2013**   многие инструменты помогут вам устранить проблемы, автоматизировать задачи, а также отслеживать и поддерживать среду Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="879bd-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="879bd-117">Определите стандартный набор инструментов для Организации, чтобы задачи, выполняемые командой операций, выполнялись корректно, эффективно, своевременно и в контролируемом виде.</span><span class="sxs-lookup"><span data-stu-id="879bd-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="879bd-118">Кроме того, необходимо реализовать процессы для отслеживания происшествий и существенных изменений в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="879bd-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="879bd-119">Справка</span><span class="sxs-lookup"><span data-stu-id="879bd-119">Reference</span></span>

<span data-ttu-id="879bd-120">Для тех, кто еще не знаком с основами управления серверами в целом, мы предлагаем общие рекомендации по управлению сервером.</span><span class="sxs-lookup"><span data-stu-id="879bd-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="879bd-121">Читатели, уже знакомые с управлением сервером, могут пропустить этот раздел.</span><span class="sxs-lookup"><span data-stu-id="879bd-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="879bd-122">Рекомендации — это рекомендации, которые основываются на наборе знаний и опыте, когда ИТ-специалисты посмотрелись в разных средах.</span><span class="sxs-lookup"><span data-stu-id="879bd-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="879bd-123">Они предоставляют стандартные процедуры для типичных задач, которые администраторы сервера Lync Server должны выполнять ежедневно, и перечень средств, которые должны использоваться для управления средой Lync Server.</span><span class="sxs-lookup"><span data-stu-id="879bd-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="879bd-124">К типичным задачам для администраторов Lync относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="879bd-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="879bd-125">**Управление емкостью и**   обеспечением доступности. Определите, как и что следует измерять, чтобы прогнозировать будущие требования к мощности и сообщать о производительности, надежности и доступности систем.</span><span class="sxs-lookup"><span data-stu-id="879bd-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="879bd-126">Необходимо убедиться в том, что на серверах, на которых работает Lync Server, определена размер для обработки нагрузки системы, а незапланированные простои остаются на уровнях, определенных в соглашении об уровне обслуживания (SLA).</span><span class="sxs-lookup"><span data-stu-id="879bd-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="879bd-127">Кроме того, вам потребуется обновить оборудование, чтобы оно продолжало соответствовать определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="879bd-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="879bd-128">**Управление изменениями и управлением конфигурацией**   определяют, как изменения вносятся в ИТ – системы.</span><span class="sxs-lookup"><span data-stu-id="879bd-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="879bd-129">Это должно включать тестирование, планы обратной связи с приложениями и ограничений на непредвиденные случаи, документацию по всем изменениям и одобрение управления в случае возникновения проблем.</span><span class="sxs-lookup"><span data-stu-id="879bd-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="879bd-130">Храните запись программного обеспечения и ресурсов оборудования и их конфигураций.</span><span class="sxs-lookup"><span data-stu-id="879bd-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="879bd-131">\*\*\*\*   Стандартные методы структуры системного администратора для выполнения административных задач, таких как администрирование базы данных и администрирование сайта.</span><span class="sxs-lookup"><span data-stu-id="879bd-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="879bd-132">**У администратора**   безопасности есть детальная политика и планирование, защищающие конфиденциальность данных, целостность данных и доступность данных в ИТ-инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="879bd-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="879bd-133">Сюда входят повседневные мероприятия и задачи, связанные с обслуживанием и настройкой инфраструктуры ИТ-безопасности.</span><span class="sxs-lookup"><span data-stu-id="879bd-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="879bd-134">**Способы устранения неполадок**   , связанных с ошибками системы, в том числе шаги для предотвращения подобных проблем в будущем.</span><span class="sxs-lookup"><span data-stu-id="879bd-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="879bd-135">**Соглашение об уровне обслуживания**   поддерживает набор целей для производительности ИТ-систем и регулярно измеряет производительность по сравнению с этими целями.</span><span class="sxs-lookup"><span data-stu-id="879bd-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="879bd-136">\*\*\*\*   Стандартные процедуры документированных документов, такие как сведения о конфигурации и выученные уроки, и делают их доступными для сотрудников, которым они нужны.</span><span class="sxs-lookup"><span data-stu-id="879bd-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="879bd-137">После внесения изменений в конфигурацию Обновите документацию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="879bd-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="879bd-138">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="879bd-138">Related Sections</span></span>

<span data-ttu-id="879bd-139">Прежде чем продолжить, ознакомьтесь со следующими разделами, посвященными системным операциям.</span><span class="sxs-lookup"><span data-stu-id="879bd-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="879bd-140">Управление емкостью и доступностью в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="879bd-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="879bd-141">Управление изменениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="879bd-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="879bd-142">Управление конфигурацией в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="879bd-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="879bd-143">Администрирование системы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="879bd-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="879bd-144">Соглашения об уровне обслуживания в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="879bd-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="879bd-145">Документация в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="879bd-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="879bd-146">Стандартные процедуры в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="879bd-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="879bd-147">Процедуры для экстренного реагирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="879bd-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="879bd-148">См. также</span><span class="sxs-lookup"><span data-stu-id="879bd-148">See Also</span></span>


[<span data-ttu-id="879bd-149">Microsoft Operations Framework 4,0</span><span class="sxs-lookup"><span data-stu-id="879bd-149">Microsoft Operations Framework 4.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

