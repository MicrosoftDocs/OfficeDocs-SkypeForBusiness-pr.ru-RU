---
title: 'Lync Server 2013: Настройка поддержки для больших собраний'
description: 'Lync Server 2013: Настройка поддержки для больших собраний.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb04b4192c6daa9e6ea255b52566dacee1bd2dcd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554215"
---
# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="31fa1-103">Настройка поддержки больших собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31fa1-103">Setting up support for large meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31fa1-104">_**Последнее изменение темы:** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="31fa1-104">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="31fa1-105">Для поддержки больших собраний с числом пользователей до 1000 необходимо создать соответствующую топологию, выполнить обязательные требования к оборудованию и программному обеспечению и соответствующим образом настроить среду.</span><span class="sxs-lookup"><span data-stu-id="31fa1-105">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="31fa1-106">Требования к топологии</span><span class="sxs-lookup"><span data-stu-id="31fa1-106">Topology Requirements</span></span>

<span data-ttu-id="31fa1-107">Для одного большого собрания требуется по крайней мере один сервер переднего плана и один фоновый сервер.</span><span class="sxs-lookup"><span data-stu-id="31fa1-107">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="31fa1-108">Тем не менее, для обеспечения высокой доступности мы рекомендуем использовать два пула серверов переднего плана с зеркальными серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="31fa1-108">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="31fa1-109">Учетная запись пользователя, размещающего большие собрания, должна размещаться в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="31fa1-109">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="31fa1-110">Однако не рекомендуется размещать в этом пуле учетные записи других пользователей.</span><span class="sxs-lookup"><span data-stu-id="31fa1-110">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="31fa1-111">Используйте его только для больших собраний.</span><span class="sxs-lookup"><span data-stu-id="31fa1-111">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="31fa1-112">Рекомендуется создать в этом пуле специальную учетную запись пользователя, используемую только для размещения больших собраний.</span><span class="sxs-lookup"><span data-stu-id="31fa1-112">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="31fa1-113">Так как большой параметр собраний оптимизирован для производительности, использование его в качестве обычного пользователя может привести к проблемам, например, невозможности продвижения сеанса P2P на собрание, когда задействована конечная точка PSTN.</span><span class="sxs-lookup"><span data-stu-id="31fa1-113">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="31fa1-114">При управлении пулом с двумя серверами переднего плана необходимо учитывать некоторые особенности.</span><span class="sxs-lookup"><span data-stu-id="31fa1-114">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="31fa1-115">Для получения дополнительных сведений см [топология и компоненты для серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии в Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="31fa1-115">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="31fa1-116">Кроме того, если вы хотите дополнительно создать резервную копию аварийного восстановления и отработку отказа для пула, используемого для больших собраний, вы можете связать его с аналогичной настройкой выделенного пула в другом центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="31fa1-116">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="31fa1-117">Дополнительные сведения см [в разделе Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="31fa1-117">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="31fa1-118">![Конфигурация пула больших собраний](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Конфигурация пула больших собраний")</span><span class="sxs-lookup"><span data-stu-id="31fa1-118">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="31fa1-119">Дополнительные замечания о топологии</span><span class="sxs-lookup"><span data-stu-id="31fa1-119">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="31fa1-120">Файловый ресурс необходим для хранения контента собрания и, если сервер архивации развернут и включен, для хранения файлов архива.</span><span class="sxs-lookup"><span data-stu-id="31fa1-120">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="31fa1-121">Общая папка может быть выделена для пула или использоваться совместно с другим пулом на сайте, на котором развернут пул.</span><span class="sxs-lookup"><span data-stu-id="31fa1-121">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="31fa1-122">Подробнее о настройке общего файлового ресурса можно узнать в статье [Настройка хранилища файлов для Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="31fa1-122">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="31fa1-123">Сервер Office Web Apps необходим для реализации функциональных возможностей презентации PowerPoint на больших собраниях.</span><span class="sxs-lookup"><span data-stu-id="31fa1-123">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="31fa1-124">Сервер Office Web Apps может быть выделен для пула больших собраний или может быть одним и тем же сервером Office Web Apps, используемым другими пулами на сайте, в котором развернут выделенный пул.</span><span class="sxs-lookup"><span data-stu-id="31fa1-124">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="31fa1-125">Балансировка нагрузки на серверах переднего плана требует аппаратной балансировки нагрузки для трафика HTTP (например, для скачивания контента собраний).</span><span class="sxs-lookup"><span data-stu-id="31fa1-125">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="31fa1-126">Балансировка нагрузки DNS рекомендуется для трафика SIP.</span><span class="sxs-lookup"><span data-stu-id="31fa1-126">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="31fa1-127">Дополнительные сведения см. в статье [требования к балансировке нагрузки для Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31fa1-127">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="31fa1-128">Если вы хотите использовать сервер мониторинга для выделенного пула больших собраний, рекомендуется использовать сервер мониторинга и базу данных, общие для всех пулов серверов переднего плана в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31fa1-128">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="31fa1-129">Требования к оборудованию и программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="31fa1-129">Hardware and Software Requirements</span></span>

<span data-ttu-id="31fa1-130">Требования к оборудованию для серверов в выделенном пуле больших собраний те же, что и для других серверов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31fa1-130">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="31fa1-131">Сведения о требованиях к оборудованию приведены в разделе "[аппаратные платформы сервера для Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="31fa1-131">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="31fa1-132">Серверы в выделенном пуле больших собраний должны соответствовать всем требованиям к программному обеспечению Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31fa1-132">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="31fa1-133">Подробные сведения о требованиях к программному обеспечению см. в следующей документации.</span><span class="sxs-lookup"><span data-stu-id="31fa1-133">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="31fa1-134">Поддержка серверов и средств операционной системы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31fa1-134">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="31fa1-135">Поддержка программного обеспечения баз данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31fa1-135">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="31fa1-136">Дополнительные требования к программному обеспечению для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31fa1-136">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="31fa1-137">Кроме того, для Lync Server 2013 и всех клиентов Lync Server 2013 должны быть установлены последние обновления.</span><span class="sxs-lookup"><span data-stu-id="31fa1-137">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="31fa1-138">Требования к конфигурации</span><span class="sxs-lookup"><span data-stu-id="31fa1-138">Configuration Requirements</span></span>

<span data-ttu-id="31fa1-p110">Рекомендуется создать новую политику конференц-связи специально для больших собраний, а затем назначить эту политику пользователям, размещенным в выделенном пуле больших собраний. Настройте эту политику конференц-связи, используя следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="31fa1-p110">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool. Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="31fa1-p111">Для параметра **MaxMeetingSize** установите значение **1000** (значение по умолчанию — **250**).</span><span class="sxs-lookup"><span data-stu-id="31fa1-p111">Set the **MaxMeetingSize** option to **1000**. (The default is **250**.)</span></span>

  - <span data-ttu-id="31fa1-143">Для параметра **AllowLargeMeetings** установите значение **True**.</span><span class="sxs-lookup"><span data-stu-id="31fa1-143">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="31fa1-144">Для параметра **EnableAppDesktopSharing** установите значение **None**.</span><span class="sxs-lookup"><span data-stu-id="31fa1-144">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="31fa1-145">Для параметра **AllowUserToScheduleMeetingsWithAppSharing** установите значение **False**.</span><span class="sxs-lookup"><span data-stu-id="31fa1-145">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="31fa1-146">Для параметра **AllowSharedNotes** установите значение **False**.</span><span class="sxs-lookup"><span data-stu-id="31fa1-146">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="31fa1-147">Для параметра **AllowAnnotations** установите значение **False**.</span><span class="sxs-lookup"><span data-stu-id="31fa1-147">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="31fa1-148">Для параметра **DisablePowerPointAnnotations** установите значение **True**.</span><span class="sxs-lookup"><span data-stu-id="31fa1-148">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="31fa1-149">Для параметра **AllowMultiview** установите значение **False**.</span><span class="sxs-lookup"><span data-stu-id="31fa1-149">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="31fa1-150">Для параметра **EnableMultiviewJoin** установите значение **False**.</span><span class="sxs-lookup"><span data-stu-id="31fa1-150">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31fa1-151">Для поддержки 1000 пользователей больших собраний в Lync Server 2013 необходимо, чтобы параметр <STRONG>алловларжемитингс</STRONG> в политике конференц-связи для планировщика собраний был установлен в значение true.</span><span class="sxs-lookup"><span data-stu-id="31fa1-151">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="31fa1-152">Если для этого параметра задано значение true, взаимодействие с Lync будет оптимизировано для дополнительных больших собраний, когда пользователи присоединяются к этому собранию.</span><span class="sxs-lookup"><span data-stu-id="31fa1-152">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="31fa1-153">В частности, в большом собрании Lync не показывает первоначальное или обновление полного списка участников собрания, что является узким местом производительности для клиента и сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31fa1-153">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="31fa1-154">Вместо этого Lync будет показывать только сведения о пользователе и список докладчиков собрания.</span><span class="sxs-lookup"><span data-stu-id="31fa1-154">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="31fa1-155">Lync по-прежнему будет правильно отображать общее количество участников, доступных в больших собраниях.</span><span class="sxs-lookup"><span data-stu-id="31fa1-155">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="31fa1-156">За исключением параметра **Maximum meeting size (Максимальный размер собрания)**, все остальные представленные здесь параметры политики конференц-связи требуются для того, чтобы отключить возможности конференц-связи, которые не нужны в больших собраниях.</span><span class="sxs-lookup"><span data-stu-id="31fa1-156">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="31fa1-157">Кроме того, необходимо настроить выделенный пул больших собраний, чтобы каждый пользователь Lync Server 2013, размещенный в пуле и ответственный за управление расписанием собраний, получил соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="31fa1-157">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="31fa1-158">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="31fa1-158">To do this, do the following:</span></span>

  - <span data-ttu-id="31fa1-p114">Для параметра **Designate as presenter (Назначить выступающим)** установите значение **None (Нет)**. Обычно только несколько человек (или даже один) среди всех участников больших собраний являются выступающими, поэтому участников не следует автоматически допускать к собраниям в качестве выступающих. Выступающие должны явно назначаться во время планирования собрания или явно выдвигаться во время самого собрания.</span><span class="sxs-lookup"><span data-stu-id="31fa1-p114">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="31fa1-162">Убедитесь, что флажок **Assigned conference type by default (Назначенный тип конференции по умолчанию)** снят.</span><span class="sxs-lookup"><span data-stu-id="31fa1-162">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="31fa1-163">Этот параметр определяет, будет ли надстройка "собрание по сети" для Lync 2013 всегда запланировать конференции с помощью назначенной конференции организатора, что означает, что для запланированных собраний используются одинаковые URL-адреса и звуковые сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="31fa1-163">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="31fa1-164">В сценариях совместной работы небольших групп такой назначенный тип конференции работает хорошо, поскольку у каждого есть своя собственная назначенная конференция, и постоянный URL-адрес присоединения и аудиоданные помогают упростить быстрое присоединение к собранию.</span><span class="sxs-lookup"><span data-stu-id="31fa1-164">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="31fa1-165">Однако в сценариях больших собраний персонал поддержки планирует большие собрания с помощью одного набора пользовательских учетных данных, а затем предоставляет URL-адреса для присоединения и аудиоданные инициаторам собраний.</span><span class="sxs-lookup"><span data-stu-id="31fa1-165">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="31fa1-166">В этом случае лучше работает использование разных URL-адресов для присоединения к разным собраниям.</span><span class="sxs-lookup"><span data-stu-id="31fa1-166">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="31fa1-167">Убедитесь, что флажок **Admit anonymous users by default (Допускать анонимных пользователей по умолчанию)** снят, если только он не требуется в вашем случае.</span><span class="sxs-lookup"><span data-stu-id="31fa1-167">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="31fa1-168">Этот параметр влияет на тип доступа к собранию по умолчанию, запланированный надстройкой "собрание по сети" для Lync 2013, когда не используется назначенная конференция.</span><span class="sxs-lookup"><span data-stu-id="31fa1-168">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="31fa1-169">Подходящий вариант для этого параметра зависит от потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="31fa1-169">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="31fa1-170">Если большинство больших собраний в организации составляют внутренние собрания, не следует устанавливать этот флажок.</span><span class="sxs-lookup"><span data-stu-id="31fa1-170">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="31fa1-171">Если в большинстве больших собраний требуется присутствие внешних пользователей, установите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="31fa1-171">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

