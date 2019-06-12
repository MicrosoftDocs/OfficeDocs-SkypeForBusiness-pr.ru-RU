---
title: 'Lync Server 2013: Настройка поддержки для крупных собраний'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03196c705253320e31e2483cc89b2aca386ff1af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="516d1-102">Настройка поддержки большого количества собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="516d1-102">Setting up support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="516d1-103">_**Тема последнего изменения:** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="516d1-103">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="516d1-104">Поддержка большого количества собраний до 1000 пользователи должны создать подходящую топологию, установить требования к оборудованию и программному обеспечению, а также настроить среду соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="516d1-104">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="516d1-105">Требования к топологии</span><span class="sxs-lookup"><span data-stu-id="516d1-105">Topology Requirements</span></span>

<span data-ttu-id="516d1-106">Для одного большого собрания требуется хотя бы один сервер переднего плана и один внутренний сервер.</span><span class="sxs-lookup"><span data-stu-id="516d1-106">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="516d1-107">Однако для обеспечения высокой доступности мы рекомендуем использовать два пула серверов переднего плана с зеркальными серверами обратного доступа.</span><span class="sxs-lookup"><span data-stu-id="516d1-107">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="516d1-108">У пользователя, на котором размещены большие собрания, должна быть учетная запись пользователя в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="516d1-108">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="516d1-109">Однако не рекомендуется размещать в этом пуле учетные записи других пользователей.</span><span class="sxs-lookup"><span data-stu-id="516d1-109">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="516d1-110">Выделите его специально для больших собраний.</span><span class="sxs-lookup"><span data-stu-id="516d1-110">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="516d1-111">Предпочтительно создать в этом пуле особую учетную запись пользователя, предназначенную только для проведения больших собраний.</span><span class="sxs-lookup"><span data-stu-id="516d1-111">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="516d1-112">Поскольку настройка для крупных собраний оптимизирована для повышения производительности, ее применение обычным пользователем может привести к неполадкам, такие как невозможность преобразовать сеанс одноранговой связи в собрание, если задействована конечная точка ТСОП.</span><span class="sxs-lookup"><span data-stu-id="516d1-112">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="516d1-113">Управление пулом, содержащим ровно два сервера переднего плана, имеет некоторые особенности.</span><span class="sxs-lookup"><span data-stu-id="516d1-113">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="516d1-114">Дополнительные сведения можно найти [в разделе топологии и компоненты для серверов переднего плана, обмена мгновенными сообщениями и присутствия в Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="516d1-114">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="516d1-115">Кроме того, если вы хотите создать резервную копию аварийного восстановления и отработку отказа для пула, используемого для крупных собраний, вы можете связать ее с выделенным пулом в другом центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="516d1-115">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="516d1-116">Подробные сведения можно найти [в разделе Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="516d1-116">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="516d1-117">![Настройка пула больших собраний] (images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Настройка пула больших собраний")</span><span class="sxs-lookup"><span data-stu-id="516d1-117">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="516d1-118">Дополнительные замечания о топологии</span><span class="sxs-lookup"><span data-stu-id="516d1-118">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="516d1-119">Файловый общий доступ необходим для хранения содержимого собрания и, если сервер архивации развернут и включен, для хранения архивных файлов.</span><span class="sxs-lookup"><span data-stu-id="516d1-119">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="516d1-120">Общий доступ к общему файловому адресу может быть выделен для пула или может быть таким же, как и для другого пула на сайте, на котором развернут пул.</span><span class="sxs-lookup"><span data-stu-id="516d1-120">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="516d1-121">Подробнее о настройке общего доступа к файлам можно узнать в разделе [Настройка хранилища файлов для Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="516d1-121">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="516d1-122">Сервер Office Web Apps является обязательным для включения функций презентации PowerPoint в крупных собраниях.</span><span class="sxs-lookup"><span data-stu-id="516d1-122">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="516d1-123">Сервер Office Web Apps может быть выделен для большого пула собраний или может быть таким же, как и тот же сервер Office Web Apps, который используется другими пулами на сайте, на котором развернут выделенный пул.</span><span class="sxs-lookup"><span data-stu-id="516d1-123">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="516d1-124">Балансировка нагрузки серверов переднего плана требует аппаратной балансировки нагрузки для трафика HTTP (например, для загрузки содержимого собрания).</span><span class="sxs-lookup"><span data-stu-id="516d1-124">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="516d1-125">Балансировка нагрузки DNS рекомендуется для трафика SIP.</span><span class="sxs-lookup"><span data-stu-id="516d1-125">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="516d1-126">Подробнее смотрите [требования к балансировке нагрузки для Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="516d1-126">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="516d1-127">Если вы хотите использовать сервер мониторинга для выделенного пула больших собраний, мы рекомендуем использовать сервер мониторинга и базу данных, которые совместно используются всеми пулами серверов переднего плана в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="516d1-127">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="516d1-128">Требования к оборудованию и программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="516d1-128">Hardware and Software Requirements</span></span>

<span data-ttu-id="516d1-129">Требования к оборудованию для серверов в выделенном пуле больших объемов собраний одинаковы, как и для других серверов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="516d1-129">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="516d1-130">Сведения о требованиях к оборудованию можно найти в разделе "[аппаратные платформы сервера для Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="516d1-130">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="516d1-131">Серверы в специальном пуле для крупных собраний должны соответствовать всем требованиям к программному обеспечению Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="516d1-131">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="516d1-132">Дополнительные сведения о требованиях к программному обеспечению можно найти в следующей документации:</span><span class="sxs-lookup"><span data-stu-id="516d1-132">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="516d1-133">Поддержка сервера и средств в операционной системе в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="516d1-133">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="516d1-134">Поддержка программного обеспечения баз данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="516d1-134">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="516d1-135">Дополнительные требования к программному обеспечению для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="516d1-135">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="516d1-136">Кроме того, для Lync Server 2013 и всех клиентов Lync Server 2013 должны быть установлены последние обновления.</span><span class="sxs-lookup"><span data-stu-id="516d1-136">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="516d1-137">Требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="516d1-137">Configuration Requirements</span></span>

<span data-ttu-id="516d1-138">Рекомендуется создать новую политику конференций для крупных собраний, а затем назначить политику конференций пользователям, которые находятся в выделенном пуле больших собраний.</span><span class="sxs-lookup"><span data-stu-id="516d1-138">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="516d1-139">Настройте параметры этой политики конференц-связи следующим образом.</span><span class="sxs-lookup"><span data-stu-id="516d1-139">Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="516d1-140">Установите для параметра **максмитингсизе** значение **1000**.</span><span class="sxs-lookup"><span data-stu-id="516d1-140">Set the **MaxMeetingSize** option to **1000**.</span></span> <span data-ttu-id="516d1-141">(Значение по умолчанию — **250**.)</span><span class="sxs-lookup"><span data-stu-id="516d1-141">(The default is **250**.)</span></span>

  - <span data-ttu-id="516d1-142">Для параметра **AllowLargeMeetings** задайте значение **True**.</span><span class="sxs-lookup"><span data-stu-id="516d1-142">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="516d1-143">Для параметра **EnableAppDesktopSharing** задайте значение **None**.</span><span class="sxs-lookup"><span data-stu-id="516d1-143">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="516d1-144">Для параметра **AllowUserToScheduleMeetingsWithAppSharing** задайте значение **False**.</span><span class="sxs-lookup"><span data-stu-id="516d1-144">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="516d1-145">Для параметра **AllowSharedNotes** задайте значение **False**.</span><span class="sxs-lookup"><span data-stu-id="516d1-145">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="516d1-146">Для параметра **AllowAnnotations** задайте значение **False**.</span><span class="sxs-lookup"><span data-stu-id="516d1-146">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="516d1-147">Для параметра **DisablePowerPointAnnotations** задайте значение **True**.</span><span class="sxs-lookup"><span data-stu-id="516d1-147">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="516d1-148">Для параметра **AllowMultiview** задайте значение **False**.</span><span class="sxs-lookup"><span data-stu-id="516d1-148">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="516d1-149">Для параметра **EnableMultiviewJoin** задайте значение **False**.</span><span class="sxs-lookup"><span data-stu-id="516d1-149">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="516d1-150">Для поддержки пользователей 1000 большого количества собраний в Lync Server 2013 требуется параметр <STRONG>алловларжемитингс</STRONG> в политике конференц-связи для планировщика собраний с заданным значением true.</span><span class="sxs-lookup"><span data-stu-id="516d1-150">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="516d1-151">Если для этого параметра установлено значение true, возможности Lync будут оптимизированы для более крупных собраний, когда пользователь присоединяется к такому собранию.</span><span class="sxs-lookup"><span data-stu-id="516d1-151">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="516d1-152">В частности, в крупном собрании Lync не показывает первоначальное или обновление полного списка участников собрания, что является узким местом производительности для клиента и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="516d1-152">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="516d1-153">Вместо этого Lync будет показывать только сведения о пользователе и список докладчиков собрания.</span><span class="sxs-lookup"><span data-stu-id="516d1-153">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="516d1-154">Lync по-прежнему будет правильно отображать общее количество участников, доступных на больших собраниях.</span><span class="sxs-lookup"><span data-stu-id="516d1-154">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="516d1-155">За исключением параметра **Максимальный размер собрания**, все указанные здесь параметры политики конференц-связи задаются для отключения функциональных возможностей конференц-связи, которые не требуются на больших собраниях.</span><span class="sxs-lookup"><span data-stu-id="516d1-155">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="516d1-156">Кроме того, необходимо настроить выделенный пул больших объемов собраний, чтобы каждый пользователь Lync Server 2013, размещенный в пуле и ответственный за управление расписанием собраний, получил соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="516d1-156">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="516d1-157">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="516d1-157">To do this, do the following:</span></span>

  - <span data-ttu-id="516d1-p114">Для параметра **Назначить в качестве выступающего** задайте значение **Нет**. Обычно на больших собраниях требуется только один или несколько докладчиков, поэтому участники не должны автоматически допускаться к большим собраниям в качестве докладчиков. Следует в явном виде назначать докладчиков при планировании собрания или предоставлять отдельным участникам права докладчиков во время собрания.</span><span class="sxs-lookup"><span data-stu-id="516d1-p114">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="516d1-161">Убедитесь в том, что флажок **Назначаемый тип конференции по умолчанию** снят.</span><span class="sxs-lookup"><span data-stu-id="516d1-161">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="516d1-162">Этот параметр определяет, будет ли надстройка "собрание по сети" для Lync 2013 всегда планировать конференции с помощью назначенной конференции организатора, а это значит, что на запланированных собраниях используются одинаковые URL-адреса и звуковые данные для объединения.</span><span class="sxs-lookup"><span data-stu-id="516d1-162">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="516d1-163">В ситуациях совместной работы небольших групп назначать тип конференции таким образом удобно, так как каждому пользователю назначается собственная конференция; в этом случае постоянный URL-адрес для присоединения и одинаковые аудиоданные позволяют ускорить присоединение к собранию.</span><span class="sxs-lookup"><span data-stu-id="516d1-163">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="516d1-164">Однако в ситуациях больших собраний сотрудники службы поддержки планируют большие собрания по одному набору учетных данных пользователя, а затем предоставляют URL-адреса для присоединения и аудиоданные инициаторам собраний.</span><span class="sxs-lookup"><span data-stu-id="516d1-164">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="516d1-165">В этом случае лучше присоединяться к каждому собранию по отдельному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="516d1-165">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="516d1-166">Убедитесь в том, что флажок **Допуск анонимных пользователей по умолчанию** снят, если он не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="516d1-166">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="516d1-167">Этот параметр влияет на тип доступа к собранию по умолчанию, запланированный надстройкой "собрание по сети" для Lync 2013, если вы не используете назначенную конференцию.</span><span class="sxs-lookup"><span data-stu-id="516d1-167">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="516d1-168">Выбор подходящего варианта зависит от потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="516d1-168">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="516d1-169">Если большие собрания в организации преимущественно являются внутренними, устанавливать этот флажок не следует.</span><span class="sxs-lookup"><span data-stu-id="516d1-169">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="516d1-170">Если на больших собраниях, как правило, требуется возможность присоединения внешних пользователей, установите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="516d1-170">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

