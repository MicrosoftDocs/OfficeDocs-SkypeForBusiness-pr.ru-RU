---
title: 'Lync Server 2013: развертывание мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fd56d0c06c9c81eda8cd1d7ef64b57da3219f3e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531176"
---
# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="70f2a-102">Развертывание мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70f2a-102">Deploying monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70f2a-103">_**Последнее изменение темы:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="70f2a-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="70f2a-104">В инфраструктуру мониторинга Microsoft Lync Server 2013 были внесены значительные изменения, начиная с того факта, что роль сервера мониторинга устарела.</span><span class="sxs-lookup"><span data-stu-id="70f2a-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="70f2a-105">Вместо отдельных ролей сервера мониторинга (для чего организациям обычно приходилось настраивать выделенные компьютеры, действующие как серверы мониторинга) службы мониторинга совместно размещаются на каждом интерфейсном сервере.</span><span class="sxs-lookup"><span data-stu-id="70f2a-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="70f2a-106">Среди прочего, это изменение помогает:</span><span class="sxs-lookup"><span data-stu-id="70f2a-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="70f2a-107">Уменьшите число ролей сервера, необходимых при внедрении Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70f2a-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="70f2a-108">В этом случае удаление роли сервера мониторинга также помогает сократить расходы за счет устранения необходимости в выделенных серверах для мониторинга.</span><span class="sxs-lookup"><span data-stu-id="70f2a-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="70f2a-109">Уменьшите сложность установки и администрирования Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70f2a-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="70f2a-110">За счет автоматического совместного размещения служб мониторинга на каждом интерфейсном сервере вам больше не нужно устанавливать, настраивать роль сервера мониторинга и управлять ею.</span><span class="sxs-lookup"><span data-stu-id="70f2a-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70f2a-111">Роль сервера архивации также была устаревшей в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70f2a-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="70f2a-112">Как и службы мониторинга, службы архивации Lync Server 2013 теперь размещены на каждом сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="70f2a-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="70f2a-113">Это важно просто потому, что для мониторинга и архивации часто используется один экземпляр базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70f2a-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="70f2a-114">Как можно ожидать, эти изменения повлияют на то, как устанавливаются и управляются службы мониторинга.</span><span class="sxs-lookup"><span data-stu-id="70f2a-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="70f2a-115">Например, поскольку роль сервера мониторинга больше не существует, узел сервера мониторинга удален из построителя топологий Lync Server; в свою очередь, это означает, что вы больше не используете мастер создания сервера мониторинга топологии, чтобы добавить новый сервер мониторинга в топологию.</span><span class="sxs-lookup"><span data-stu-id="70f2a-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="70f2a-116">(Мастер больше не существует.) Вместо этого, как правило, необходимо реализовать службы мониторинга в пределах топологии, выполнив следующие два действия:</span><span class="sxs-lookup"><span data-stu-id="70f2a-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="70f2a-117">Одновременное включение мониторинга и настройка нового пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70f2a-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="70f2a-118">(В Lync Server 2013 отслеживание включено или отключено для отдельных пулов.) Обратите внимание, что можно включить мониторинг для пула без фактического сбора данных мониторинга, процесс, описанный в разделе Настройка регистрации вызовов и параметров качества взаимодействия в этой документации.</span><span class="sxs-lookup"><span data-stu-id="70f2a-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="70f2a-p107">Свяжите хранилище данных мониторинга (то есть базы данных мониторинга) с новым пулом. Обратите внимание, что одно и то же хранилище данных мониторинга можно связать с несколькими пулами. В зависимости от количества пользователей, размещенных в пулах регистраторов, бассейны, это означает, что не требуется настраивать отдельную базу данных мониторинга для каждого пула. Вместо этого несколько пулов могут использовать одно и то же хранилище данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="70f2a-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="70f2a-p108">Хотя зачастую проще включить мониторинг одновременно с созданием нового пула, также можно создать пул с отключенным мониторингом. В этом случае вы сможете использовать построитель топологии для включения службы в дальнейшем: построитель топологии позволяет включить или отключить мониторинг для пула или связать пул с другим хранилищем данных мониторинга. Имейте в виду, что хотя роли сервера мониторинга больше нет, вам все равно требуется создать одно или несколько хранилищ данных мониторинга: фоновые базы данных, используемые для хранения данных, собранные службами мониторинга. Эти базы данных можно создать с помощью Microsoft SQL Server 2008 R2 или Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="70f2a-p108">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled. If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store. Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service. These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70f2a-127">Если для пула включено наблюдение, процесс сбора данных мониторинга можно отключить без необходимости изменения топологии: Командная консоль Lync Server позволяет отключить (а затем повторно включить) сбор данных о вызовах (CDR) или сбор данных о качестве взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="70f2a-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="70f2a-128">Дополнительные сведения см. в разделе "Настройка регистрации звонков и параметров качества взаимодействия" данной документации.</span><span class="sxs-lookup"><span data-stu-id="70f2a-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="70f2a-129">Еще одно важное улучшение мониторинга в Lync Server 2013 — тот факт, что отчеты мониторинга Lync Server теперь поддерживают IPv6: отчеты, в которых используется поле IP-адрес, будут отображать адреса IPv4 или IPv6 в зависимости от: 1) используемого запроса SQL; и 2), где или не IPv6-адрес хранится в базе данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="70f2a-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70f2a-130">Убедитесь, что тип запуска службы агента SQL Server является автоматическим, а служба агента SQL Server запущена для экземпляра SQL, в котором хранятся базы данных мониторинга, поэтому задания по обслуживанию сервера мониторинга SQL Server по умолчанию могут выполняться по расписанию в зависимости от управления службой агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70f2a-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="70f2a-131">В этой документации описывается процесс установки и настройки отчетов и мониторинга для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70f2a-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="70f2a-132">В документации представлены пошаговые инструкции, позволяющие выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="70f2a-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="70f2a-133">Включить мониторинг в вашей топологии и связать хранилище данных мониторинга с интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="70f2a-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="70f2a-134">Установите службы SQL Server Reporting Services и отчеты мониторинга Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70f2a-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="70f2a-135">Отчеты мониторинга — это предварительно настроенные отчеты, предоставляющие различные представления сведений в базе данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="70f2a-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="70f2a-136">Настроить сбор данных регистрации звонков (CDR) и качества взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="70f2a-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="70f2a-137">Регистрация вызовов — это способ отслеживания использования возможностей Lync Server, таких как телефонные звонки по протоколу VoIP (VoIP). Обмен мгновенными сообщениями (IM); Передача файлов; аудио-и видеоконференции (аудио-и видеоконференций); и сеансов общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="70f2a-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="70f2a-138">Показатели QoE отслеживают качество аудио- и видеозвонков в вашей организации, в том числе такие данные, как число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержек пакетов).</span><span class="sxs-lookup"><span data-stu-id="70f2a-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="70f2a-139">Вручную удалить записи CDR и QoE из базы данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="70f2a-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

