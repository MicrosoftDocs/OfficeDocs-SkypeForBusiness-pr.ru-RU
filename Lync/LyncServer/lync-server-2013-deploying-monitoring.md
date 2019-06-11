---
title: 'Lync Server 2013: развертывание мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 584b99b6e5fad72a07a35b748ab9bafa4116701a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="0182a-102">Развертывание мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0182a-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0182a-103">_**Тема последнего изменения:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="0182a-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="0182a-104">Существенные изменения были внесены в инфраструктуру мониторинга Microsoft Lync Server 2013, начиная с того факта, что роль сервера мониторинга устарела.</span><span class="sxs-lookup"><span data-stu-id="0182a-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="0182a-105">Вместо отдельных ролей сервера мониторинга (обычно необходимые Организации для настройки выделенных компьютеров, которые должны выступать в качестве серверов мониторинга), теперь размещаются на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0182a-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="0182a-106">Помимо прочего, это изменение помогает:</span><span class="sxs-lookup"><span data-stu-id="0182a-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="0182a-107">Уменьшите количество ролей сервера, необходимых при внедрении Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0182a-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="0182a-108">В этом случае уменьшением роли сервер мониторинга сервера также способствует снижению расходов, устраняя необходимость поддерживать выделенные серверы для наблюдения.</span><span class="sxs-lookup"><span data-stu-id="0182a-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="0182a-109">Упрощение настройки и администрирования сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="0182a-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="0182a-110">При автоматическом размещении служб наблюдения на каждом сервере переднего плана вам больше не нужно устанавливать и настраивать роль сервера мониторинга, а также управлять ею.</span><span class="sxs-lookup"><span data-stu-id="0182a-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0182a-111">Роль сервера архивации также была устаревшей в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0182a-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="0182a-112">Как и в службах мониторинга, службы архивации Lync Server 2013 теперь выровнены на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0182a-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="0182a-113">Обратите внимание, что это очень важно, так как для наблюдения и архивации часто используются один и тот же экземпляр базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0182a-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="0182a-114">Как и вы, возможно, эти изменения повлияют на то, как устанавливаются и управляются службы наблюдения.</span><span class="sxs-lookup"><span data-stu-id="0182a-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="0182a-115">Например, поскольку роль сервера мониторинга больше не существует, узел сервера мониторинга удаляется из построителя топологии Lync Server. в свою очередь, это означает, что вы больше не используете мастер топологии, новый сервер мониторинга, чтобы добавить новый сервер мониторинга в топологию.</span><span class="sxs-lookup"><span data-stu-id="0182a-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="0182a-116">(Мастер больше не существует.) Вместо этого вы обычно реализуете службы наблюдения в топологии, выполняя следующие два действия:</span><span class="sxs-lookup"><span data-stu-id="0182a-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="0182a-117">Одновременное включение наблюдения за тем же моментом, как настроить новый пул Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0182a-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="0182a-118">(В Lync Server 2013 наблюдение включено или отключено для отдельных групп.) Обратите внимание, что вы можете включить мониторинг для пула без фактического сбора данных мониторинга, процесс, описанный в разделе Настройка записи сведений о звонке и параметров качества обслуживания в этой документации.</span><span class="sxs-lookup"><span data-stu-id="0182a-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="0182a-p107">Свяжите хранилище данных мониторинга (то есть базы данных мониторинга) с новым пулом. Обратите внимание, что одно и то же хранилище данных мониторинга можно связать с несколькими пулами. В зависимости от количества пользователей, размещенных в пулах регистраторов, это означает, что не требуется настраивать отдельную базу данных мониторинга для каждого пула. Вместо этого несколько пулов могут использовать одно и то же хранилище данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="0182a-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="0182a-123">Хотя во многих случаях проще включить мониторинг во время создания нового пула, можно также создать новый пул с отключенным мониторингом.</span><span class="sxs-lookup"><span data-stu-id="0182a-123">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled.</span></span> <span data-ttu-id="0182a-124">Эта служба может быть включена позднее с помощью построителя топологий, который позволяет включать и отключать мониторинг для пула а также связывать пул с другим хранилищем данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="0182a-124">If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store.</span></span> <span data-ttu-id="0182a-125">Имейте в виду, что несмотря на то, что вы больше не используете роль сервера мониторинга, вам по-прежнему потребуется создать одно или несколько хранилищ мониторинга: внутренние базы данных, которые используются для хранения данных, собираемых службой мониторинга.</span><span class="sxs-lookup"><span data-stu-id="0182a-125">Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service.</span></span> <span data-ttu-id="0182a-126">Эти серверные базы данных можно создать как в Microsoft SQL Server 2008 R2, так и в Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="0182a-126">These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0182a-127">Если для пула включена поддержка мониторинга, вы можете отключить процесс сбора данных мониторинга, не изменяя топологию: Командная консоль Lync Server Management Shell позволяет отключить (и затем снова включить) запись сведений о вызове (CDR) или качество сбор данных по интерфейсу (QoE).</span><span class="sxs-lookup"><span data-stu-id="0182a-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="0182a-128">Дополнительные сведения см. в разделе "Настройка регистрации звонков и параметров качества взаимодействия" данной документации.</span><span class="sxs-lookup"><span data-stu-id="0182a-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="0182a-129">Еще одной важной улучшенной возможностью наблюдения в Lync Server 2013 является тот факт, что на сервере Lync Server отслеживаются возможности поддержки IPv6: отчеты, в которых используется поле IP-адреса, отображаются как IPv4-, так и IPv6-адреса в зависимости от: 1) будет использоваться запрос SQL. и 2) там, где или в базе данных мониторинга хранится IPv6-адрес.</span><span class="sxs-lookup"><span data-stu-id="0182a-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0182a-130">Убедитесь, что тип запуска службы агента сервера SQL Server имеет значение "Автоматически", а служба агента SQL Server выполняется для экземпляра SQL, который содержит базы данных мониторинга, чтобы задания мониторинга обслуживания SQL Server по умолчанию выполнялись на запланированной основе под управлением службы агента сервера SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0182a-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="0182a-131">В этой статье описан процесс установки и настройки мониторинга и мониторинга отчетов для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0182a-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="0182a-132">Приведенные в документации пошаговые инструкции позволяют выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0182a-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="0182a-133">Включить мониторинг в вашей топологии и связать хранилище данных мониторинга с интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="0182a-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="0182a-134">Установка служб SQL Server Reporting Services и отчетов мониторинга Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0182a-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="0182a-135">Встроенные отчеты по мониторингу позволяют получить различные представления информации, хранящейся в базе данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="0182a-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="0182a-136">Настройте запись сведений о звонке (CDR) и сбор данных о качестве опыта (QoE).</span><span class="sxs-lookup"><span data-stu-id="0182a-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="0182a-137">Запись сведений о звонке позволяет отслеживать использование возможностей сервера Lync, таких как телефонные звонки через IP (VoIP). Обмен мгновенными сообщениями (IM); Передача файлов; Конференции аудио-и видеосвязи (A/V); и сеансам общего обмена приложениями.</span><span class="sxs-lookup"><span data-stu-id="0182a-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="0182a-138">Показатели QoE отслеживают качество аудио- и видеозвонков в вашей организации, в том числе такие данные, как число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержек пакетов).</span><span class="sxs-lookup"><span data-stu-id="0182a-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="0182a-139">Вручную удалить записи CDR и QoE из базы данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="0182a-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

