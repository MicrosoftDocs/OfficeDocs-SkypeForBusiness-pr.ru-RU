---
title: Компоненты и топологии Lync Server 2013 для конференц-связи
description: Компоненты и топологии Lync Server 2013 для конференц-связи.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 719fe81d0f634b1eab1e79c2e7e665e89b0a791a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576865"
---
# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="e21c9-103">Компоненты и топологии для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e21c9-103">Components and topologies for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e21c9-104">_**Последнее изменение темы:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="e21c9-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="e21c9-105">При выборе конференции в построителе топологий Конференц-связь развертывается в составе сервера переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e21c9-105">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="e21c9-106">Для общего доступа к конференц-связи с телефонным подключением и PowerPoint требуются дополнительные компоненты и настройка.</span><span class="sxs-lookup"><span data-stu-id="e21c9-106">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="e21c9-107">В следующих разделах описываются поддерживаемые компоненты и топологии для веб-конференций, аудио- и видеоконференций и конференций с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e21c9-107">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="e21c9-108">Поддерживаемые компоненты</span><span class="sxs-lookup"><span data-stu-id="e21c9-108">Supported Components</span></span>

<span data-ttu-id="e21c9-109">Для веб-конференций и аудио-и видеоконференций необходимы только серверы переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e21c9-109">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="e21c9-110">Список требований к оборудованию и программному обеспечению для серверов переднего плана и серверов Standard Edition приведен в разделе [Supported Hardware for Lync server 2013](lync-server-2013-supported-hardware.md) and [Server Software and Infrastructure support в Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="e21c9-110">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="e21c9-111">Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки совместного использования и отрисовки презентаций PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="e21c9-111">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="e21c9-112">Дополнительные сведения об установке и настройке сервера Office Web Apps приведены в статье [Настройка интеграции с сервером Office Web Apps и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="e21c9-112">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="e21c9-113">В дополнение к требованиям для веб-конференций и аудио-и видеоконференций, Конференц-связь с телефонным подключением использует следующие компоненты Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="e21c9-113">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="e21c9-114">**Служба приложений**     Служба приложений предоставляет платформу для развертывания и управления приложениями объединенных коммуникаций (UC).</span><span class="sxs-lookup"><span data-stu-id="e21c9-114">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="e21c9-115">Конференц-связь с телефонным подключением использует два приложения UC, для которых требуется служба приложений: помощник по конференц-связи и извещение конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e21c9-115">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="e21c9-116">По умолчанию служба приложения устанавливается и активируется по умолчанию на каждом сервере переднего плана в интерфейсном пуле и на каждом сервере Standard Edition при развертывании рабочей нагрузки конференц-связи и выборе варианта конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e21c9-116">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="e21c9-117">Приложение "помощник по **Конференц**     -связи" Приложение "помощник по конференц-связи" — это единое приложение для обмена данными, принимающее вызовы телефонной сети общего пользования (PSTN), воспроизводит приглашения и присоединяется к Конференции аудио-и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="e21c9-117">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="e21c9-118">Приложение "помощник по конференц-связи" устанавливается и активируется по умолчанию при развертывании рабочей нагрузки конференц-связи и выборе варианта конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e21c9-118">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="e21c9-119">Приложение извещений конференц-связи **Conferencing Announcement application**     Извещение конференц-связи — это единое приложение для общения, которое воспроизводит звуки и запрашивает участников PSTN в определенных действиях, например при присоединении или выходе из Конференции участников, если участники присоединяются к Конференции или отправляются из нее, кто-то входит в Конференц-зал или блокирует или разблокирует конференцию.</span><span class="sxs-lookup"><span data-stu-id="e21c9-119">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="e21c9-120">Приложение для проведения конференций также поддерживает команды с двумя тонами (DTMF) на клавиатуре телефона.</span><span class="sxs-lookup"><span data-stu-id="e21c9-120">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="e21c9-121">Приложение извещений конференц-связи автоматически устанавливается и активируется по умолчанию при развертывании рабочей нагрузки конференц-связи и выборе варианта конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e21c9-121">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="e21c9-122">Страница параметров Конференц **-связи с телефонным подключением**     На странице параметров конференц-связи с телефонным подключением отображаются номера подключений к конференц-связи с доступными языками, назначены сведения о конференциях (то есть для собраний, которые не нуждаются в планировании), а также входящие в систему управления DTMF и поддерживают управление личным идентификационным номером (ПИН-кодом) и назначенной информацией о конференциях.</span><span class="sxs-lookup"><span data-stu-id="e21c9-122">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="e21c9-123">Страница параметров конференц-связи с телефонным подключением устанавливается автоматически как часть веб-служб.</span><span class="sxs-lookup"><span data-stu-id="e21c9-123">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="e21c9-124">**Lync server 2013, сервер-посредник и шлюз PSTN**     Для конференц-связи с телефонным подключением требуется сервер-посредник для перевода сигналов (и носителей, в некоторых конфигурациях) между Lync Server 2013 и шлюзом PSTN, а шлюз PSTN для перевода сигналов и мультимедиа между сервером-посредником и шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="e21c9-124">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="e21c9-125">Для конференц-связи с телефонным подключением необходимо развернуть по крайней мере один сервер-посредник и хотя бы один из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="e21c9-125">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="e21c9-126">шлюз ТСОП;</span><span class="sxs-lookup"><span data-stu-id="e21c9-126">PSTN gateway</span></span>
    
      - <span data-ttu-id="e21c9-127">IP-УАТС</span><span class="sxs-lookup"><span data-stu-id="e21c9-127">IP-PBX</span></span>
    
      - <span data-ttu-id="e21c9-128">пограничный контроллер сеансов (SBC) для поставщика услуг Интернет-телефонии, подключение к которому выполняется путем настройки канала SIP.</span><span class="sxs-lookup"><span data-stu-id="e21c9-128">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e21c9-129">Если вы также выполняете развертывание корпоративной голосовой связи, сервер-посредник и шлюзы PSTN являются частью развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e21c9-129">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="e21c9-130">Если вы не развертываете корпоративную голосовую связь, необходимо развернуть по крайней мере один сервер-посредник и по крайней мере один шлюз PSTN, IP-УАТС или SBC для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e21c9-130">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="e21c9-131">**Хранилище файлов**     Хранилище файлов используется для музыкальных файлов с записанными именами.</span><span class="sxs-lookup"><span data-stu-id="e21c9-131">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="e21c9-132">Хранилище файлов является стандартным компонентом в каждом развертывании Enterprise Edition или Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e21c9-132">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="e21c9-133">**Пользовательское хранилище**     Хранилище пользователей используется для хранения ПИН-кодов пользователей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e21c9-133">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="e21c9-134">ПИН-коды хэшируются.</span><span class="sxs-lookup"><span data-stu-id="e21c9-134">PINs are hashed.</span></span> <span data-ttu-id="e21c9-135">Хранилище пользователей является стандартным компонентом в каждом развертывании Enterprise Edition или Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e21c9-135">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="e21c9-136">Панель управления Lync **Server**     Некоторые параметры телефонной связи можно настроить с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e21c9-136">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="e21c9-137">**Командная консоль**     Lync Server Все параметры телефонного подключения можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e21c9-137">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="e21c9-138">Командлеты командной консоли Lync Server доступны для развертывания, настройки, запуска, мониторинга и устранения неполадок приложения и объявления конференц-связи для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e21c9-138">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="e21c9-139">Подробные сведения об определенных командлетах представлены в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e21c9-139">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="e21c9-140">Поддерживаемые топологии</span><span class="sxs-lookup"><span data-stu-id="e21c9-140">Supported Topologies</span></span>

<span data-ttu-id="e21c9-141">В Lync Server 2013 сервер, на котором запущены службы конференций, всегда размещен на серверах переднего плана или серверах Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e21c9-141">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="e21c9-142">Во время первоначального развертывания построитель топологий дает возможность включить Конференц-связь в топологию.</span><span class="sxs-lookup"><span data-stu-id="e21c9-142">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="e21c9-143">Вы также можете использовать построитель топологий для добавления конференций к существующему развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e21c9-143">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="e21c9-144">Дополнительные сведения см [в статье определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="e21c9-144">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="e21c9-145">Топологии конференций с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="e21c9-145">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="e21c9-146">Конференц-связь с телефонным подключением можно разворачивать в следующих топологиях:</span><span class="sxs-lookup"><span data-stu-id="e21c9-146">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="e21c9-147">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="e21c9-147">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="e21c9-148">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e21c9-148">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="e21c9-149">С корпоративной голосовой связью или без нее</span><span class="sxs-lookup"><span data-stu-id="e21c9-149">With or without Enterprise Voice</span></span>

<span data-ttu-id="e21c9-150">Вы можете развернуть службу приложений, приложение-помощник по конференц-связи и приложение извещения о конференции на центральном сайте, но не на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="e21c9-150">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e21c9-151">Если вы развертываете Конференц-связь с телефонным подключением, необходимо развернуть ее в каждом пуле, где развертывается Конференц-связь Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e21c9-151">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="e21c9-152">Назначать номера доступа в каждом пуле не обязательно, но функция конференц-связи с телефонным подключением должна быть развернута в каждом пуле.</span><span class="sxs-lookup"><span data-stu-id="e21c9-152">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="e21c9-153">Это требование поддерживает функцию записи имени, когда пользователь вызывает номер доступа из одного пула для присоединения к конференции Lync Server 2013 в другом пуле.</span><span class="sxs-lookup"><span data-stu-id="e21c9-153">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="e21c9-154">Поддерживаемые топологии для Lync Server 2013 и Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="e21c9-154">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="e21c9-155">Lync Server 2013 предоставляет следующие способы настройки сервера Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="e21c9-155">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="e21c9-156">В зависимости от имеющихся потребностей вам доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="e21c9-156">Depending on your needs you can:</span></span>

  - <span data-ttu-id="e21c9-157">**Установите как Lync Server 2013, так и сервер Office Web Apps локально за брандмауэром организации и в той же сетевой зоне.**</span><span class="sxs-lookup"><span data-stu-id="e21c9-157">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="e21c9-158">В этой топологии внешний доступ к серверу Office Web Apps будет предоставляться через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="e21c9-158">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="e21c9-159">Как Lync Server 2013, так и сервер Office Web Apps (или ферма сервер Office Web Apps) устанавливаются локально и позади брандмауэра организации.</span><span class="sxs-lookup"><span data-stu-id="e21c9-159">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="e21c9-160">В идеале сервер Office Web Apps следует устанавливать в той же зоне сети, что и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e21c9-160">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="e21c9-161">Внешние клиенты Lync могут подключаться к Lync Server 2013 и Office Web Apps Server с помощью обратного прокси-сервера, который представляет собой сервер, который принимает запросы из Интернета и пересылает их во внутреннюю сеть.</span><span class="sxs-lookup"><span data-stu-id="e21c9-161">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="e21c9-162">(Внутренним клиентам не требуется использовать обратный прокси-сервер, так как они могут подключаться к серверу Office Web Apps напрямую). Эта топология лучше всего подходит для использования выделенной фермы серверов Office Web Apps, которая используется только Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e21c9-162">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="e21c9-163">**Использование внешнего развернутого сервера Office Web Apps**</span><span class="sxs-lookup"><span data-stu-id="e21c9-163">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="e21c9-164">В этой топологии Lync Server 2013 развернут локально и использует сервер Office Web Apps, развернутый вне зоны сети Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e21c9-164">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="e21c9-165">Это может произойти, если сервер Office Web Apps совместно используется несколькими приложениями в корпорации и развернут в сети, требующей Lync Server для использования внешнего интерфейса сервера Office Web Apps, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="e21c9-165">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="e21c9-166">Нет необходимости устанавливать обратный прокси-сервер; Вместо этого все запросы от сервера Office Web Apps к Lync Server 2013 маршрутизируются через пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="e21c9-166">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="e21c9-167">Как внутренний, так и внешний клиенты Lync подключаются к серверу Office Web Apps с использованием внешнего URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="e21c9-167">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="e21c9-168">Если сервер Office Web Apps развернут за пределами внутреннего брандмауэра, выберите параметр **сервер Office Web Apps развернут во внешней сети (периметр/Интернет)** в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="e21c9-168">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="e21c9-169">Более подробную информацию можно узнать [в статье Настройка интеграции с сервером Office Web Apps и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="e21c9-169">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="e21c9-170">Независимо от выбранной топологии крайне важно открыть правильные порты брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="e21c9-170">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="e21c9-171">Необходимо убедиться, что DNS-имена, IP-адреса и порты не заблокированы брандмауэрами на сервере Office Web Apps, подсистеме балансировки нагрузки или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e21c9-171">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e21c9-172">Кроме того, для предоставления внешнего доступа к серверу Office Web Apps необходимо развернуть сервер в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="e21c9-172">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="e21c9-173">Если вы сделаете это, помните, что для установки сервера Office Web Apps сервер должен быть членом домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e21c9-173">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="e21c9-174">Если политика сети не допускает, чтобы компьютеры в сети периметра были членами домена Active Directory, не рекомендуется устанавливать сервер Office Web Apps в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="e21c9-174">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="e21c9-175">Вместо этого следует установить сервер Office Web Apps во внутренней сети и предоставить доступ внешним пользователям через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="e21c9-175">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

