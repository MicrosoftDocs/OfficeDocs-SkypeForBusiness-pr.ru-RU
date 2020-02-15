---
title: Роли сервера Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 093161cec5a13ac12840776dec731773782966c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="798c8-102">Роли сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="798c8-102">Server roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="798c8-103">_**Последнее изменение темы:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="798c8-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="798c8-104">Каждый сервер, на котором работает Lync Server, выполняет одну или несколько *ролей сервера*.</span><span class="sxs-lookup"><span data-stu-id="798c8-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="798c8-105">Роль сервера — это определенный набор функций Lync Server, предоставляемых этим сервером.</span><span class="sxs-lookup"><span data-stu-id="798c8-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="798c8-106">Нет необходимости развертывать все доступные роли сервера в сети.</span><span class="sxs-lookup"><span data-stu-id="798c8-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="798c8-107">Установите только те роли сервера, которые предоставляют нужные функции.</span><span class="sxs-lookup"><span data-stu-id="798c8-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="798c8-108">Даже если вы не знакомы с ролями серверов в Lync Server, в средстве планирования можно придуматься к оптимальному решению для серверов, которые необходимо развернуть, в зависимости от требуемых функций.</span><span class="sxs-lookup"><span data-stu-id="798c8-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="798c8-109">В этом разделе предоставляется краткой описание ролей сервера и предоставляемых ими общих функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="798c8-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="798c8-110">Сервер выпуска Standard Edition</span><span class="sxs-lookup"><span data-stu-id="798c8-110">Standard Edition Server</span></span>

  - <span data-ttu-id="798c8-111">Сервер переднего плана и внутренний сервер</span><span class="sxs-lookup"><span data-stu-id="798c8-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="798c8-112">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="798c8-112">Edge Server</span></span>

  - <span data-ttu-id="798c8-113">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="798c8-113">Mediation Server</span></span>

  - <span data-ttu-id="798c8-114">Режиссер</span><span class="sxs-lookup"><span data-stu-id="798c8-114">Director</span></span>

  - <span data-ttu-id="798c8-115">Сервер переднего плана сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="798c8-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="798c8-116">Хранилище сохраняемого чата (фоновый сервер сохраняемого чата)</span><span class="sxs-lookup"><span data-stu-id="798c8-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="798c8-117">Хранилище сохраняемого чата соответствия требованиям (фоновый сервер сохраняемого чата для соответствия требованиям)</span><span class="sxs-lookup"><span data-stu-id="798c8-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="798c8-118">В целях улучшения масштабируемости и высокой доступности для большинства ролей серверов можно развертывать *пулы*, состоящие из нескольких серверов, на которых запущена одна и та же роль сервера.</span><span class="sxs-lookup"><span data-stu-id="798c8-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="798c8-119">Каждый сервер в пуле должен содержать идентичные роли сервера.</span><span class="sxs-lookup"><span data-stu-id="798c8-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="798c8-120">Для большинства типов пулов в Lync Server необходимо развернуть подсистему балансировки нагрузки для распределения трафика между различными серверами в пуле.</span><span class="sxs-lookup"><span data-stu-id="798c8-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="798c8-121">Lync Server поддерживает балансировку нагрузки службы доменных имен (DNS) и аппаратные подсистемы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="798c8-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="798c8-122">Сервер выпуска Standard Edition</span><span class="sxs-lookup"><span data-stu-id="798c8-122">Standard Edition Server</span></span>

<span data-ttu-id="798c8-123">Сервер Standard Edition предназначен для небольших организаций, а также для пилотных проектов в крупных организациях.</span><span class="sxs-lookup"><span data-stu-id="798c8-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="798c8-124">Она включает многие функции Lync Server, в том числе необходимые базы данных, для запуска на отдельном сервере.</span><span class="sxs-lookup"><span data-stu-id="798c8-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="798c8-125">Это позволяет использовать функциональность Lync Server для более низкой стоимости, но не предоставляет полноценное решение для высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="798c8-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="798c8-126">Сервер Standard Edition позволяет использовать обмен мгновенными сообщениями, сведения о присутствии, Конференц-связь и корпоративную голосовую связь, которые работают на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="798c8-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="798c8-127">Для решения высокой доступности используйте Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="798c8-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="798c8-128">Сервер переднего плана и внутренний сервер</span><span class="sxs-lookup"><span data-stu-id="798c8-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="798c8-129">В Lync Server Enterprise Edition сервер переднего плана является основным ролью сервера и выполняет многие основные функции Lync Server.</span><span class="sxs-lookup"><span data-stu-id="798c8-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="798c8-130">Сервер переднего плана, а также внутренние серверы — это единственные роли сервера, которые должны находиться в любом развертывании Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="798c8-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="798c8-p106">*Пул переднего плана* — это набор настроенных идентичным образом серверов переднего плана, которые работают вместе для предоставления служб общей группе пользователей. Пул обеспечивает для пользователей возможности масштабируемости и отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="798c8-p106">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users. A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="798c8-133">Сервер переднего плана предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="798c8-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="798c8-134">проверка подлинности и регистрация пользователей;</span><span class="sxs-lookup"><span data-stu-id="798c8-134">User authentication and registration</span></span>

  - <span data-ttu-id="798c8-135">сведения о присутствии и обмен карточками контактов;</span><span class="sxs-lookup"><span data-stu-id="798c8-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="798c8-136">службы адресной книги и расширение списка рассылки;</span><span class="sxs-lookup"><span data-stu-id="798c8-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="798c8-137">функции обмена мгновенными сообщениями, включая многопользовательские беседы;</span><span class="sxs-lookup"><span data-stu-id="798c8-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="798c8-138">веб-конференции, конференц-связь с телефонным подключением через ТСОП, аудио- и видеоконференции (если они развернуты)</span><span class="sxs-lookup"><span data-stu-id="798c8-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="798c8-139">Размещение приложений для обоих приложений, входящих в состав Lync Server (например, помощник по конференц-связи и приложения группы ответа), а также сторонние приложения.</span><span class="sxs-lookup"><span data-stu-id="798c8-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="798c8-140">дополнительно: мониторинг для сбора сведений об использовании в форме записей регистрации вызовов и записей ошибок вызовов.</span><span class="sxs-lookup"><span data-stu-id="798c8-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="798c8-141">Эта информация содержит метрики о качестве мультимедиа (аудио-и видеосвязи), которые проходят по сети как для звонков на предприятии, так и для конференций аудио-и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="798c8-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="798c8-142">веб-компоненты для поддержки веб-задач, таких как веб-планировщик и компонент обеспечения процесса присоединения.</span><span class="sxs-lookup"><span data-stu-id="798c8-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="798c8-143">дополнительно: архивация как отдельных мгновенных сообщений, так и собраний для соответствия нормативным требованиям.</span><span class="sxs-lookup"><span data-stu-id="798c8-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="798c8-144">Дополнительные сведения приведены в статье [Планирование архивации в Lync Server 2013](lync-server-2013-planning-for-archiving.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="798c8-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="798c8-145">В Lync Server 2010 и более ранних версиях мониторинг и архивация были отдельными ролями серверов, не размещенными на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="798c8-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="798c8-146">При необходимости, если сохраняемый чат включен, веб-службы сохраняемого чата для управления комнатами чата и веб-службы сохраняемого чата для передачи и загрузки файлов.</span><span class="sxs-lookup"><span data-stu-id="798c8-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="798c8-p109">Пулы переднего плана — это также основное хранилище для данных пользователей и конференций. Информация о каждом пользователе реплицируется среди трех серверов переднего плана в пуле, а ее резервная копия создается на фоновых серверах.</span><span class="sxs-lookup"><span data-stu-id="798c8-p109">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="798c8-149">Кроме того, один интерфейсный пул в развертывании также выполняет *центральный сервер управления*, который управляет и развертывает основные данные конфигурации для всех серверов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="798c8-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="798c8-150">Центральный сервер управления также предоставляет командную консоль Lync Server и возможности передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="798c8-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="798c8-151">Фоновые серверы — это серверы баз данных, на которых работает Microsoft SQL Server, предоставляющий службы баз данных для интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="798c8-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="798c8-152">Фоновые серверы служат хранилищем резервного копирования для данных пользователей и конференций пула, и основным хранилищем для других баз данных, таких как база данных группы ответа.</span><span class="sxs-lookup"><span data-stu-id="798c8-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="798c8-153">Для отработки отказа рекомендуется использовать один сервер внутреннего сервера, но решение, использующее зеркальное отображение SQL Server, рекомендуется для отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="798c8-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="798c8-154">Внутренние серверы не работают с программным обеспечением Lync Server.</span><span class="sxs-lookup"><span data-stu-id="798c8-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="798c8-155">Не рекомендуется разсовместное размещение баз данных Lync Server с другими базами данных.</span><span class="sxs-lookup"><span data-stu-id="798c8-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="798c8-156">В противном случае может пострадать доступность и производительность.</span><span class="sxs-lookup"><span data-stu-id="798c8-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="798c8-157">Данные, хранящиеся в базах данных фонового сервера, включают сведения о присутствии, контактные списки пользователей, данные конференций, включая постоянные данные о состоянии всех текущих конференций, а также данные планирования конференций.</span><span class="sxs-lookup"><span data-stu-id="798c8-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="798c8-158">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="798c8-158">Edge Server</span></span>

<span data-ttu-id="798c8-159">Пограничный сервер позволяет пользователям общаться и взаимодействовать с пользователями, находящимися за прерядом брандмауэров организации.</span><span class="sxs-lookup"><span data-stu-id="798c8-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="798c8-160">Эти внешние пользователи могут включать пользователей организации, которые в настоящее время работают автономно, пользователей из федеративных партнерских организаций и внешних пользователей, которые были приглашены на участие в конференциях, размещенных в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="798c8-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="798c8-161">Пограничный сервер также обеспечивает возможность подключения к общедоступным службам связи обмена мгновенными сообщениями, включая Windows Live, AOL, Yahoo\!и Google говорите.</span><span class="sxs-lookup"><span data-stu-id="798c8-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="798c8-162">С 1 сентября 2012 г. лицензия подписки на общедоступные службы обмена мгновенными сообщениями Microsoft Lync ("PIC усл") больше недоступна для приобретения новых или обновленных договоров.</span><span class="sxs-lookup"><span data-stu-id="798c8-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="798c8-163">Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="798c8-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="798c8-164">Messenger до даты завершения работы службы.</span><span class="sxs-lookup"><span data-stu-id="798c8-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="798c8-165">Дата окончания срока жизни 2014 для AOL и Yahoo!</span><span class="sxs-lookup"><span data-stu-id="798c8-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="798c8-166">объявлено.</span><span class="sxs-lookup"><span data-stu-id="798c8-166">has been announced.</span></span> <span data-ttu-id="798c8-167">Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="798c8-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="798c8-168">УСЛ PIC является лицензией на месяц на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с помощью Yahoo!</span><span class="sxs-lookup"><span data-stu-id="798c8-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="798c8-169">Messenger.</span><span class="sxs-lookup"><span data-stu-id="798c8-169">Messenger.</span></span> <span data-ttu-id="798c8-170">Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого выполняется обмотка.</span><span class="sxs-lookup"><span data-stu-id="798c8-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="798c8-171">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="798c8-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="798c8-172">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL.</span><span class="sxs-lookup"><span data-stu-id="798c8-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="798c8-173">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="798c8-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="798c8-174">Развертывание пограничного сервера также включает службы Mobility Services, поддерживающие функциональность Lync на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="798c8-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="798c8-175">Пользователи могут использовать поддерживаемые мобильные устройства Apple iOS, Android, Windows Phone или Nokia для выполнения таких действий, как отправка и получение мгновенных сообщений, просмотр контактов и Просмотр сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="798c8-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="798c8-176">Кроме того, мобильными устройствами поддерживаются некоторые возможности корпоративной голосовой связи (Enterprise Voice), такие как присоединение к конференции по щелчку, звонок с работы (Call via Work), многосторонняя связь по одному номеру, голосовая почта и пропущенные вызовы.</span><span class="sxs-lookup"><span data-stu-id="798c8-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="798c8-177">Функция Mobility также поддерживает *Push-уведомления* для мобильных устройств, которые не поддерживают приложения, работающие в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="798c8-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="798c8-178">Push-уведомление — это уведомление, которое отправляется на мобильное устройство, связанное с событием, которое происходит, когда мобильное приложение неактивно.</span><span class="sxs-lookup"><span data-stu-id="798c8-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="798c8-179">Пограничные серверы также включают полностью интегрированный прокси-сервер XMPP, при этом шлюз XMPP встроен в серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="798c8-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="798c8-180">Вы можете настроить эти компоненты XMPP, чтобы позволить пользователям Lync Server 2013 добавлять контакты из партнеров на основе XMPP (таких как Google говорите) для обмена мгновенными сообщениями и присутствия.</span><span class="sxs-lookup"><span data-stu-id="798c8-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="798c8-181">Дополнительные сведения приведены в статье [Планирование доступа внешних пользователей в Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="798c8-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="798c8-182">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="798c8-182">Mediation Server</span></span>

<span data-ttu-id="798c8-183">Сервер-посредник является необходимым компонентом для внедрения корпоративной голосовой связи и конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="798c8-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="798c8-184">Сервер-посредник переводит сигнал, и в некоторых конфигурациях мультимедиа между внутренней инфраструктурой Lync Server и шлюзом телефонной сети общего пользования (PSTN), IP-УАТС или магистральным протоколом SIP.</span><span class="sxs-lookup"><span data-stu-id="798c8-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="798c8-185">Сервер-посредник может работать на одном компьютере с сервером переднего плана или может быть выделен в отдельный пул серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="798c8-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="798c8-186">Дополнительные сведения: [компонент сервер-посредник в Lync server 2013](lync-server-2013-mediation-server-component.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="798c8-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="798c8-187">Режиссер</span><span class="sxs-lookup"><span data-stu-id="798c8-187">Director</span></span>

<span data-ttu-id="798c8-188">Директоры могут выполнять проверку подлинности запросов пользователей Lync Server, но они не являются домашними учетными записями пользователей или предоставляют услуги по присутствию или конференции.</span><span class="sxs-lookup"><span data-stu-id="798c8-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="798c8-189">Директоры оказываются особенно полезными при необходимости повышения уровня безопасности в развертываниях, где необходим доступ внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="798c8-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="798c8-190">Директор может выполнять проверку подлинности запросов, прежде чем передавать эти запросы на внутренние серверы.</span><span class="sxs-lookup"><span data-stu-id="798c8-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="798c8-191">При начале атак по принципу отказа в обслуживании атаки заканчиваются на директоре и не достигают серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="798c8-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="798c8-192">Дополнительные сведения: [сценарии для директора в Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="798c8-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="798c8-193">Роли сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="798c8-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="798c8-p121">Возможности сохраняемого чата позволяют пользователям участвовать в многопользовательских тематических беседах, которые подлежат сохранению. На сервере переднего плана сохраняемого чата работает служба сохраняемого чата. Внутренний сервер сохраняемого чата хранит данные журнала бесед и сведения о категориях и комнатах чата. Дополнительный внутренний сервер сохраняемого чата для соответствия требованиям может хранить содержимое чата и события соответствия, которые будут использоваться для обеспечения соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="798c8-p121">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="798c8-198">Серверы, на которых работает Lync Server Standard Edition, также могут запускать сохраняемый чат, размещенный на том же сервере.</span><span class="sxs-lookup"><span data-stu-id="798c8-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="798c8-199">Сервер переднего плана сохраняемого чата не может совместно работать с сервером переднего плана Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="798c8-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="798c8-200">Дополнительные сведения см. [в статье Планирование сервера сохраняемого чата в Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="798c8-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="798c8-201">См. также</span><span class="sxs-lookup"><span data-stu-id="798c8-201">See Also</span></span>


[<span data-ttu-id="798c8-202">Компонент сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="798c8-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="798c8-203">Планирование архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="798c8-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="798c8-204">Планирование доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="798c8-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="798c8-205">Сценарии для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="798c8-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="798c8-206">Планирование сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="798c8-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

