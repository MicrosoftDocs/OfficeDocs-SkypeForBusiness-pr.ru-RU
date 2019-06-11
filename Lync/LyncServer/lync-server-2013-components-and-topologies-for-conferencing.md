---
title: 'Lync Server 2013: компоненты и топологии для конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5caf5ba33e863e08bf4f728d2bf11394f37f20b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="6f5a3-102">Компоненты и топологии для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f5a3-102">Components and topologies for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f5a3-103">_**Тема последнего изменения:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="6f5a3-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="6f5a3-104">Когда вы выбираете конференцию в построителе топологии, конференции развертываются как часть сервера переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="6f5a3-105">Для конференц-связи с телефонным подключением и совместное использование PowerPoint требуются дополнительные компоненты и параметры настройки.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="6f5a3-106">В следующих разделах описаны поддерживаемые компоненты и топологии для веб-конференций, Конференции и конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="6f5a3-107">Поддерживаемые компоненты</span><span class="sxs-lookup"><span data-stu-id="6f5a3-107">Supported Components</span></span>

<span data-ttu-id="6f5a3-108">Для веб-конференций, а также для проведения видеоконференций и серверов Standard Edition требуются серверы.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="6f5a3-109">Список требований к оборудованию и программному обеспечению для серверов переднего плана и стандартных серверов выпусков приведен в разделе [поддерживаемое оборудование для Lync server 2013](lync-server-2013-supported-hardware.md) и [серверного программного обеспечения и поддержки инфраструктуры в Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a3-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="6f5a3-110">Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки общего просмотра и отрисовки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="6f5a3-111">Подробнее об установке и настройке сервера Office Web Apps можно узнать в разделе [Настройка интеграции с Office Web Apps Server и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a3-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="6f5a3-112">В дополнение к требованиям для веб-конференций и конференций/V Конференц-связь с телефонным подключением использует следующие компоненты Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="6f5a3-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="6f5a3-113">\*\*\*\*   Служба приложений службы приложений предоставляет платформу для развертывания приложений Объединенных коммуникаций и управления ими.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="6f5a3-114">Конференц-связь с телефонным подключением использует два приложения UC, для которых требуется служба приложений: извещение и конференции конференций.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="6f5a3-115">Служба приложения устанавливается и активируется по умолчанию на каждом сервере переднего плана в пуле переднего плана и на каждом сервере Standard Edition при развертывании рабочей нагрузки для конференций и выборе параметра Конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="6f5a3-116">\*\*\*\*   Участие в конференциях приложений для конференц-связи — это единое коммуникационное приложение, принимающее вызовы по коммутируемой телефонной сети (PSTN), воспроизводит запросы и присоединяется к Конференции a/V.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="6f5a3-117">Приложение для конференц-связи устанавливается и активируется по умолчанию при развертывании рабочей нагрузки, а также в разделе Выбор конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="6f5a3-118">\*\*\*\*   Объявление Конференции приложение извещение конференции — это единое коммуникационное приложение, которое воспроизводит звуки и запросы для пользователей, которые будут выполнять определенные действия, например, когда участники присоединяются к Конференции или оставляют на ней собрания. участники отключены или отключены. кто-то пойдет в зал ожидания или на Конференции блокируется или разблокируется.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="6f5a3-119">Приложение для объявлений конференций также поддерживает команды многочастотной многострочности (DTMF) на клавиатуре телефона.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="6f5a3-120">Приложение извещений о конференции автоматически устанавливается и активируется по умолчанию при развертывании рабочей нагрузки и выборе параметра конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="6f5a3-121">**Страница параметров конференц-связи**   с телефонным подключением. на странице параметров конференц-связи с телефонным подключением отображаются номера для телефонной конференции на их доступных языках, назначенные сведения о Конференции (то есть для собраний, которые не требуется планировать), а также Встроенные элементы управления DTMF и поддерживают управление личными идентификационными номерами (ПИН-кодом) и назначенные сведения о конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="6f5a3-122">Страница параметров конференц-связи с телефонным подключением устанавливается автоматически в составе веб-служб.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="6f5a3-123">**Для Lync Server 2013, сервер-посредника и**   Конференц-связь с телефонным подключением для шлюза PSTN требуется сервер-посредник для перевода сигналов (и носителей в некоторых конфигурациях) между Lync Server 2013 и шлюзом PSTN и шлюзом PSTN для перевода сигнализация и носители между сервером и шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="6f5a3-124">Для конференц-связи с телефонным подключением необходимо развернуть хотя бы один сервер-посредник и хотя бы один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="6f5a3-125">Шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="6f5a3-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="6f5a3-126">IP-УАТС</span><span class="sxs-lookup"><span data-stu-id="6f5a3-126">IP-PBX</span></span>
    
      - <span data-ttu-id="6f5a3-127">пограничный контроллер сеансов (SBC) для поставщика услуг Интернет-телефонии, подключение к которому выполняется путем настройки канала SIP.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6f5a3-128">Кроме того, если вы разворачиваете корпоративный голосовую почту, сервер исправлений и шлюзы PSTN являются частью корпоративного развертывания.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="6f5a3-129">Если вы не развертываете корпоративную голосовую почту, вам нужно развернуть по крайней мере один сервер-посредник и по крайней мере один шлюз PSTN, IP-УАТС или SBC для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="6f5a3-130">\*\*\*\*   Хранилище файлов в хранилище файлов используется для звуковых файлов с записанными именами.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="6f5a3-131">Хранилище файлов является стандартным компонентом в каждом развертывании корпоративного или стандартного выпуска.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="6f5a3-132">\*\*\*\* Магазин пользователей магазина Users используется для хранения контактов пользователей Lync Server 2013.   </span><span class="sxs-lookup"><span data-stu-id="6f5a3-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="6f5a3-133">Контакты хэшируются.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-133">PINs are hashed.</span></span> <span data-ttu-id="6f5a3-134">Магазин пользователей является стандартным компонентом в каждом развертывании Enterprise Edition или Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="6f5a3-135">**Панель управления Lync Server**   . Некоторые параметры телефонного подключения можно настроить с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="6f5a3-136">**Командная консоль Lync Server Management Shell**   можно настроить с помощью командлетов командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="6f5a3-137">Командлеты командной консоли Lync Server можно использовать для развертывания, настройки, запуска, мониторинга и устранения неполадок в приложениях и объявлениях конференц-связи с приложениями и конференций.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="6f5a3-138">Подробные сведения о конкретных командлетах можно найти в документации по среде Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="6f5a3-139">Поддерживаемые топологии</span><span class="sxs-lookup"><span data-stu-id="6f5a3-139">Supported Topologies</span></span>

<span data-ttu-id="6f5a3-140">В Lync Server 2013 сервер, на котором запущены службы конференций, всегда размещается на серверах переднего плана или стандартных серверах выпуска.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="6f5a3-141">В ходе первоначального развертывания построитель топологии предлагает вариант включения конференций в топологию.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="6f5a3-142">Кроме того, в построителе топологий можно добавить конференц-связь к существующему развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="6f5a3-143">Подробные сведения можно найти [в разделе Определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a3-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="6f5a3-144">Топлогиес конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="6f5a3-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="6f5a3-145">Вы можете развернуть Конференц-связь с телефонным подключением в указанных ниже топологиях и конфигурациях.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="6f5a3-146">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6f5a3-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="6f5a3-147">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="6f5a3-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="6f5a3-148">при наличии или отсутствии корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="6f5a3-149">Вы можете развернуть службу приложений, приложение для участников Конференции и конференц-связь на центральном сайте, но не на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f5a3-150">Если вы развертываете Конференц-связь с телефонным подключением, вы должны развернуть ее в каждом пуле, где развертываются конференции Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="6f5a3-151">Назначать номера доступа в каждом пуле не требуется, но функция конференц-связи с телефонным подключением должна быть развернута в каждом пуле.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="6f5a3-152">Это требование поддерживает функцию записи имени, когда пользователь вызывает номер доступа из одного пула для присоединения к конференции Lync Server 2013 в другом пуле.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="6f5a3-153">Поддерживаемые топологии для Lync Server 2013 и Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="6f5a3-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="6f5a3-154">Lync Server 2013 предоставляет следующие возможности для настройки сервера Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="6f5a3-155">Выберите вариант в зависимости от конкретных задач.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="6f5a3-156">**Установите как Lync Server 2013, так и сервер Office Web Apps локально за брандмауэром организации и в той же сетевой зоне.**</span><span class="sxs-lookup"><span data-stu-id="6f5a3-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="6f5a3-157">В этой топологии внешний доступ к серверу Office Web Apps будет предоставляться через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="6f5a3-158">Как Lync Server 2013, так и сервер Office Web Apps (или ферма серверов Office Web Apps) устанавливаются локально и за брандмауэром вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="6f5a3-159">В идеале вы должны установить сервер Office Web Apps в той же сетевой зоне, что и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="6f5a3-160">Внешние клиенты Lync могут подключаться к Lync Server 2013 и Office Web Apps Server с помощью обратного прокси-сервера, который является сервером, который принимает запросы из Интернета и перенаправляет их во внутреннюю сеть.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="6f5a3-161">(Для внутренних клиентов не требуется использовать обратный прокси-сервер, так как они могут подключаться к серверу Office Web Apps напрямую.) Эта топология удобна, если вы хотите использовать выделенную ферму серверов Office Web Apps, которая используется только в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="6f5a3-162">**Использование внешнего развернутого сервера Office Web Apps**</span><span class="sxs-lookup"><span data-stu-id="6f5a3-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="6f5a3-163">В этой топологии Lync Server 2013 развертывается локально и использует сервер Office Web Apps, развернутый за пределами сетевой зоны Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="6f5a3-164">Это может быть вызвано тем, что сервер Office Web Apps является общим для нескольких приложений в корпорации и развернут в сети, требующей от сервера Lync Server использования внешнего интерфейса сервера Office Web Apps, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="6f5a3-165">Вам не нужно устанавливать обратный прокси-сервер; Вместо этого все запросы с сервера Office Web Apps на Lync Server 2013 пересылаются через пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="6f5a3-166">Как внутренние, так и внешние клиенты Lync подключаются к серверу Office Web Apps с помощью внешнего URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="6f5a3-167">Если сервер Office Web Apps развернут за пределами внутреннего межсетевого экрана, выберите вариант **развертывание сервера Office Web Apps во внешней сети (то есть в демилитаризованной зоне или Интернете)** в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="6f5a3-168">Дополнительные сведения: [Настройка интеграции с Office Web Apps Server и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="6f5a3-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="6f5a3-169">Независимо от выбранной топологии обязательно должны быть открыты правильные порты брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="6f5a3-170">Убедитесь, что DNS-имена, IP-адреса и порты не заблокированы брандмауэрами на сервере Office Web Apps, службе балансировки нагрузки или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f5a3-171">Еще один способ предоставления внешнего доступа к серверу Office Web Apps — развертывание сервера в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="6f5a3-172">Если вы решите сделать это, помните, что для установки сервера Office Web Apps требуется, чтобы сервер был членом домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="6f5a3-173">Если политика сети не допускает, чтобы компьютеры в демилитаризованной зоне были членами домена Active Directory, рекомендуется не устанавливать сервер Office Web Apps в демилитаризованную сеть.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="6f5a3-174">Вместо этого необходимо установить сервер Office Web Apps во внутренней сети и предоставить доступ к внешним пользователям через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="6f5a3-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

