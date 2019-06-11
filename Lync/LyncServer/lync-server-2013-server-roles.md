---
title: 'Lync Server 2013: роли сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b8c5b052defcdc1d60ef9900c283f9f50b3809
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="4b30e-102">Роли сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b30e-102">Server roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b30e-103">_**Тема последнего изменения:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="4b30e-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="4b30e-104">Каждый сервер, на котором работает Lync Server, выполняет одну или несколько *ролей сервера*.</span><span class="sxs-lookup"><span data-stu-id="4b30e-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="4b30e-105">Роль сервера — это определенный набор функциональных возможностей Lync Server, предоставляемых этим сервером.</span><span class="sxs-lookup"><span data-stu-id="4b30e-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="4b30e-106">Вам не нужно развертывать все доступные роли сервера в сети.</span><span class="sxs-lookup"><span data-stu-id="4b30e-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="4b30e-107">Установите только те роли сервера, которые предоставляют нужные функции.</span><span class="sxs-lookup"><span data-stu-id="4b30e-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="4b30e-108">Даже если вы не знакомы с ролями сервера в Lync Server, в средстве планирования вы можете воспользоваться лучшим решением для серверов, которые нужно развернуть, в зависимости от необходимых функций.</span><span class="sxs-lookup"><span data-stu-id="4b30e-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="4b30e-109">В этом разделе представлен краткий обзор ролей сервера и общих функций, которые они предоставляют.</span><span class="sxs-lookup"><span data-stu-id="4b30e-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="4b30e-110">Сервер выпуска Standard Edition</span><span class="sxs-lookup"><span data-stu-id="4b30e-110">Standard Edition Server</span></span>

  - <span data-ttu-id="4b30e-111">Сервер переднего плана и внутренний сервер</span><span class="sxs-lookup"><span data-stu-id="4b30e-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="4b30e-112">пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="4b30e-112">Edge Server</span></span>

  - <span data-ttu-id="4b30e-113">посредник</span><span class="sxs-lookup"><span data-stu-id="4b30e-113">Mediation Server</span></span>

  - <span data-ttu-id="4b30e-114">Директор</span><span class="sxs-lookup"><span data-stu-id="4b30e-114">Director</span></span>

  - <span data-ttu-id="4b30e-115">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="4b30e-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="4b30e-116">Хранилище сохраняемого чата (сохраняемый сервер обратного чата)</span><span class="sxs-lookup"><span data-stu-id="4b30e-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="4b30e-117">Хранилище соответствия требованиям сохраняемого чата (сохраняемый сервер соответствия требованиям к чат)</span><span class="sxs-lookup"><span data-stu-id="4b30e-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="4b30e-118">В целях улучшения масштабируемости и высокой доступности для большинства ролей серверов можно развертывать *пулы*, состоящие из нескольких серверов, на которых запущена одна и та же роль сервера.</span><span class="sxs-lookup"><span data-stu-id="4b30e-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="4b30e-119">Каждый сервер в пуле должен содержать идентичные роли сервера.</span><span class="sxs-lookup"><span data-stu-id="4b30e-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="4b30e-120">Для большинства типов пулов в Lync Server необходимо развернуть подсистему балансировки нагрузки, чтобы распределить трафик между различными серверами в пуле.</span><span class="sxs-lookup"><span data-stu-id="4b30e-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="4b30e-121">Lync Server поддерживает как службу доменных имен (DNS), так и подсистемы балансировки нагрузки для оборудования.</span><span class="sxs-lookup"><span data-stu-id="4b30e-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="4b30e-122">Сервер выпуска Standard Edition</span><span class="sxs-lookup"><span data-stu-id="4b30e-122">Standard Edition Server</span></span>

<span data-ttu-id="4b30e-123">Сервер Standard Edition разработан для малых организаций, а также для пилотных проектов больших организаций.</span><span class="sxs-lookup"><span data-stu-id="4b30e-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="4b30e-124">Она включает многие возможности Lync Server, в том числе необходимые базы данных, которые можно запускать на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="4b30e-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="4b30e-125">Это позволяет использовать функциональность Lync Server для более ранних расходов, но не предоставляет полноценное решение для высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="4b30e-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="4b30e-126">Сервер Standard Edition позволяет использовать обмен мгновенными сообщениями, сведения о присутствии, Конференц-связь и корпоративное голосовое приложение на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="4b30e-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="4b30e-127">Для решения с высокой степенью доступности используйте Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4b30e-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="4b30e-128">Сервер переднего плана и внутренний сервер</span><span class="sxs-lookup"><span data-stu-id="4b30e-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="4b30e-129">В Lync Server Enterprise Edition сервер переднего плана является основным серверной ролью и выполняет большое количество основных функций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b30e-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="4b30e-130">Сервер переднего плана наряду с серверами обратной связи — это единственные роли сервера, необходимые для развертывания Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4b30e-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="4b30e-131">*Пул переднего плана* — это набор серверов переднего плана, настроенных одинаково, совместное использование для предоставления служб для общей группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b30e-131">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="4b30e-132">Пул обеспечивает для пользователей возможности масштабируемости и отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="4b30e-132">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="4b30e-133">Сервер переднего плана включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="4b30e-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="4b30e-134">Проверка подлинности и регистрация пользователей</span><span class="sxs-lookup"><span data-stu-id="4b30e-134">User authentication and registration</span></span>

  - <span data-ttu-id="4b30e-135">Сведения о присутствии и обмен карточками контактов</span><span class="sxs-lookup"><span data-stu-id="4b30e-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="4b30e-136">Развертывание службы адресной книги и списка рассылки</span><span class="sxs-lookup"><span data-stu-id="4b30e-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="4b30e-137">Возможности обмена мгновенными сообщениями, в том числе многосторонние конференции</span><span class="sxs-lookup"><span data-stu-id="4b30e-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="4b30e-138">Интернет-конференции, одновременная Конференц-связь с телефонным подключением и видеоконференции (если она развернута)</span><span class="sxs-lookup"><span data-stu-id="4b30e-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="4b30e-139">Размещение приложений для обоих приложений, входящих в состав Lync Server (например, "участие в конференциях" и "группа ответа"), а сторонние приложения</span><span class="sxs-lookup"><span data-stu-id="4b30e-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="4b30e-140">дополнительно: мониторинг для сбора сведений об использовании в форме записей регистрации вызовов и записей ошибок вызовов.</span><span class="sxs-lookup"><span data-stu-id="4b30e-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="4b30e-141">Эта информация содержит метрики о качестве мультимедиа (звуковых и видеофайлов), которые просматривают сеть как для корпоративных голосовых вызовов, так и для конференций/V.</span><span class="sxs-lookup"><span data-stu-id="4b30e-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="4b30e-142">веб-компоненты для поддержки веб-задач, таких как веб-планировщик и компонент обеспечения процесса присоединения.</span><span class="sxs-lookup"><span data-stu-id="4b30e-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="4b30e-143">дополнительно: архивация как отдельных мгновенных сообщений, так и собраний для соответствия нормативным требованиям.</span><span class="sxs-lookup"><span data-stu-id="4b30e-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="4b30e-144">Подробности можно найти [в разделе Планирование архивации в Lync Server 2013](lync-server-2013-planning-for-archiving.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="4b30e-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="4b30e-145">В Lync Server 2010 и более ранних версиях наблюдение и архивация были отдельными серверными ролями, но не выровненными на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4b30e-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="4b30e-146">При необходимости, если сохраняемый чат включен, веб-службы сохраняемого чата для управления комнатами чата и веб-службы сохраняемого чата для передачи и загрузки файлов.</span><span class="sxs-lookup"><span data-stu-id="4b30e-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="4b30e-p109">Пулы переднего плана – это также основное хранилище для данных пользователей и конференций. Информация о каждом пользователе реплицируется среди трех серверов переднего плана в пуле, а ее резервная копия создается на фоновых серверах.</span><span class="sxs-lookup"><span data-stu-id="4b30e-p109">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="4b30e-149">Кроме того, для одного пула переднего плана в развертывании также запускается *центральный сервер управления*, который управляет и разворачивает основные данные конфигурации для всех серверов, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b30e-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="4b30e-150">Центральный сервер управления также предоставляет командную консоль управления Lync Server и возможности передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="4b30e-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="4b30e-151">Серверными серверами являются серверы баз данных Microsoft SQL Server, обеспечивающие работу служб баз данных для пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4b30e-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="4b30e-152">Фоновые серверы служат хранилищем резервного копирования для данных пользователей и конференций пула и основным хранилищем для других баз данных, таких как база данных группы ответа.</span><span class="sxs-lookup"><span data-stu-id="4b30e-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="4b30e-153">Вы можете использовать один сервер, но решение, в котором используется зеркальное отображение SQL Server, рекомендуется для отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="4b30e-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="4b30e-154">Серверные программы Lync Server не работают на серверах с обратной стороны.</span><span class="sxs-lookup"><span data-stu-id="4b30e-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4b30e-155">Мы не рекомендуем выполняйте размещение баз данных Lync Server вместе с другими базами данных.</span><span class="sxs-lookup"><span data-stu-id="4b30e-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="4b30e-156">В противном случае может пострадать доступность и производительность.</span><span class="sxs-lookup"><span data-stu-id="4b30e-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="4b30e-157">Данные, хранящиеся в базах данных фонового сервера, включают сведения о присутствии, контактные списки пользователей, данные конференций, включая постоянные данные о состоянии всех текущих конференций, а также данные планирования конференций.</span><span class="sxs-lookup"><span data-stu-id="4b30e-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="4b30e-158">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="4b30e-158">Edge Server</span></span>

<span data-ttu-id="4b30e-159">Пограничный сервер позволяет пользователям общаться и работать совместно с пользователями за пределами брандмауэров организации.</span><span class="sxs-lookup"><span data-stu-id="4b30e-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="4b30e-160">Эти внешние пользователи могут включать пользователей, которые в настоящее время работают за пределами Организации, и пользователей из организаций федеративных партнеров, а также пользователей, которые были приглашены на участие в конференциях, размещенных на вашем развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b30e-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="4b30e-161">Кроме того, пограничный сервер предоставляет возможность подключения к общедоступным службам обмена мгновенными\!сообщениями, включая Windows Live, AOL, Yahoo и Google.</span><span class="sxs-lookup"><span data-stu-id="4b30e-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="4b30e-162">По состоянию на 1 сентября 2012, лицензия на подписку на общедоступные службы обмена мгновенными сообщениями в Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="4b30e-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="4b30e-163">Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="4b30e-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="4b30e-164">Messenger, пока служба не отключается.</span><span class="sxs-lookup"><span data-stu-id="4b30e-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="4b30e-165">Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня.</span><span class="sxs-lookup"><span data-stu-id="4b30e-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="4b30e-166">было объявлено.</span><span class="sxs-lookup"><span data-stu-id="4b30e-166">has been announced.</span></span> <span data-ttu-id="4b30e-167">Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4b30e-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="4b30e-168">УСЛ PIC является лицензией на ежемесячную подписку для пользователей Lync Server или Office Communications Server, которая требуется для Федерации с помощью Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="4b30e-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="4b30e-169">Messenger.</span><span class="sxs-lookup"><span data-stu-id="4b30e-169">Messenger.</span></span> <span data-ttu-id="4b30e-170">Возможность предоставления этой услуги корпорацией Майкрософт зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="4b30e-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="4b30e-171">В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру.</span><span class="sxs-lookup"><span data-stu-id="4b30e-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="4b30e-172">Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств за пределами стандартной клиентской лицензии Lync.</span><span class="sxs-lookup"><span data-stu-id="4b30e-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="4b30e-173">В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут общаться с сотнями миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="4b30e-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="4b30e-174">Развертывание пограничного сервера также включает службы Mobility Services, поддерживающие функциональность Lync на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="4b30e-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="4b30e-175">Пользователи могут использовать поддерживаемые мобильные устройства Apple iOS, Android, Windows Phone или Nokia для выполнения таких операций, как отправка и получение мгновенных сообщений, просмотр контактов и Просмотр сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="4b30e-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="4b30e-176">Кроме того, мобильные устройства поддерживают некоторые корпоративные функции голосовой связи, например, для присоединения к Конференции, звонков через Skype, голосовую почту и пропущенных звонков.</span><span class="sxs-lookup"><span data-stu-id="4b30e-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="4b30e-177">Функция Mobility также поддерживает *Push-уведомления* для мобильных устройств, которые не поддерживают приложения, работающие в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="4b30e-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="4b30e-178">Push-уведомление — это уведомление, которое отправляется на мобильное устройство для события, которое происходит, когда мобильное приложение неактивно.</span><span class="sxs-lookup"><span data-stu-id="4b30e-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="4b30e-179">Пограничные серверы также включают полностью интегрированный прокси-сервер XMPP, при этом шлюз XMPP встроен в серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4b30e-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="4b30e-180">Эти компоненты КСМПП можно настроить таким образом, чтобы пользователи Lync Server 2013 могли добавлять контакты из КСМПП-партнеров (например, Google чата) для обмена мгновенными сообщениями и их присутствия.</span><span class="sxs-lookup"><span data-stu-id="4b30e-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="4b30e-181">Подробности можно найти [в разделе Планирование доступа внешних пользователей в Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="4b30e-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="4b30e-182">посредник</span><span class="sxs-lookup"><span data-stu-id="4b30e-182">Mediation Server</span></span>

<span data-ttu-id="4b30e-183">Сервер-посредник является обязательным компонентом для внедрения корпоративной голосовой связи и конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="4b30e-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="4b30e-184">Сервер-посредник переводит сигналы, а также в некоторых конфигурациях, носители между внутренней инфраструктурой сервера Lync и шлюзом КОММУТИРУЕМой телефонной сети, IP-УАТС или SIP.</span><span class="sxs-lookup"><span data-stu-id="4b30e-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="4b30e-185">Вы можете запустить сервер-посредника, размещенный на том же сервере, что и сервер переднего плана, или разделить его на пул серверов изолированных исправлений.</span><span class="sxs-lookup"><span data-stu-id="4b30e-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="4b30e-186">Подробности можно найти [в разделе Сервер исправлений в Lync server 2013](lync-server-2013-mediation-server-component.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="4b30e-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="4b30e-187">Директор</span><span class="sxs-lookup"><span data-stu-id="4b30e-187">Director</span></span>

<span data-ttu-id="4b30e-188">Режиссеры могут проверять подлинность запросов пользователей Lync Server, но они не являются домашними учетными записями пользователей или предоставляют услуги по обеспечению присутствия или конференции.</span><span class="sxs-lookup"><span data-stu-id="4b30e-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="4b30e-189">Директоры оказываются особенно полезными при необходимости повышения уровня безопасности в развертываниях, где необходим доступ внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="4b30e-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="4b30e-190">Директор может выполнять проверку подлинности запросов, прежде чем передавать эти запросы внутренним серверам.</span><span class="sxs-lookup"><span data-stu-id="4b30e-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="4b30e-191">В случае атак типа "отказ в обслуживании" они заканчиваются на директоре и не достигают серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4b30e-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="4b30e-192">Дополнительные сведения можно найти в разделе [сценарии для режиссера в Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="4b30e-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="4b30e-193">Роли сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="4b30e-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="4b30e-p121">Возможности сохраняемого чата позволяют пользователям участвовать в многопользовательских тематических беседах, которые подлежат сохранению. На сервере переднего плана сохраняемого чата работает служба сохраняемого чата. Внутренний сервер сохраняемого чата хранит данные журнала бесед и сведения о категориях и комнатах чата. Дополнительный внутренний сервер сохраняемого чата для соответствия требованиям может хранить содержимое чата и события соответствия, которые будут использоваться для обеспечения соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4b30e-p121">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="4b30e-198">Серверы, на которых работает Lync Server Standard Edition, также могут запускать сохраняемый чат, размещенный на одном и том же сервере.</span><span class="sxs-lookup"><span data-stu-id="4b30e-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="4b30e-199">Вы не можете разгруппировать сохраняемый серверный текст чата с помощью сервера переднего плана Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4b30e-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="4b30e-200">Подробные сведения можно найти [в разделе Планирование сохраняемого сервера чата в Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="4b30e-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b30e-201">См. также</span><span class="sxs-lookup"><span data-stu-id="4b30e-201">See Also</span></span>


[<span data-ttu-id="4b30e-202">Компонент сервера «исправления» в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b30e-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="4b30e-203">Планирование архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b30e-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="4b30e-204">Планирование доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b30e-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="4b30e-205">Сценарии для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b30e-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="4b30e-206">Планирование сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b30e-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

