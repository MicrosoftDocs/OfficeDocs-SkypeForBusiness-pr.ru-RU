---
title: 'Lync Server 2013: задачи развертывания для удаленного управления звонками'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63c9cba56ccedf3559b1e9f1da1ee58cc03e195
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="97e9a-102">Задачи развертывания для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97e9a-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97e9a-103">_**Тема последнего изменения:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="97e9a-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="97e9a-104">В этой статье описаны задачи развертывания, которые необходимо выполнить, чтобы включить удаленное управление звонками для пользователей в среде Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97e9a-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97e9a-105">Если вы переносите в Microsoft Office Communicator 2007 R2 пользователей, для которых уже разрешено удаленное управление звонками, необходимо выполнить дополнительные действия по развертыванию, прежде чем приступить к выполнению задач по удалению удаленного управления звонками, описанным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="97e9a-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="97e9a-106">В процессе миграции на Lync Server вы должны удалить доверенные записи приложения (ранее известные как <EM>Авторизованные записи узла</EM>) с помощью средств администрирования Office Communications Server 2007 R2, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="97e9a-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="97e9a-107">Подробнее об удалении авторизованных узлов можно узнать <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">в разделе Удаление устаревшего авторизованного узла в Lync Server 2013 (необязательно)</A>.</span><span class="sxs-lookup"><span data-stu-id="97e9a-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="97e9a-108">Шаг 1: Установка и Настройка шлюза SIP/КСТА для связи с АТС</span><span class="sxs-lookup"><span data-stu-id="97e9a-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="97e9a-109">Для обеспечения функций управления удаленными звонками для пользователей необходимо установить по крайней мере один шлюз SIP/КСТА, который может подключаться к обоим серверам Lync и существующим частным филиалам (УАТС) в своей среде.</span><span class="sxs-lookup"><span data-stu-id="97e9a-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="97e9a-110">Шлюз SIP/КСТА — это шлюз между SIP и коммуникационной программой, поддерживаемой компьютером (КСТА).</span><span class="sxs-lookup"><span data-stu-id="97e9a-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="97e9a-111">При установке нескольких шлюзов или только одного из них можно настроить только один шлюз или УАТС.</span><span class="sxs-lookup"><span data-stu-id="97e9a-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="97e9a-112">Если у существующей АТС нет интерфейса SIP/КСТА, убедитесь, что вы разворачиваете шлюз SIP/КСТА, поддерживающий УАТС, в том числе поддержку специальных протоколов передачи сигналов для фирменной АТС.</span><span class="sxs-lookup"><span data-stu-id="97e9a-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="97e9a-113">Сведения о возможностях можно найти в статьях каждого поставщика напрямую.</span><span class="sxs-lookup"><span data-stu-id="97e9a-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="97e9a-114">Когда вы будете готовы к развертыванию шлюза SIP/КСТА, который может интегрироваться с сервером Lync Server для удаленного управления звонками, также обратитесь к поставщику шлюза или документации поставщика, в соответствии с синтаксисом, требуемым шлюзом для указанных ниже данных.</span><span class="sxs-lookup"><span data-stu-id="97e9a-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="97e9a-115">Универсальный код ресурса (URI) основного сервера</span><span class="sxs-lookup"><span data-stu-id="97e9a-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="97e9a-116">Универсальный код ресурса (URI) для пользователей, которые будут назначены шлюзу</span><span class="sxs-lookup"><span data-stu-id="97e9a-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="97e9a-117">Указанные выше параметры необходимы во время настройки пользователя и должны быть указаны надлежащим образом шлюзом для маршрутизации и подключения к УАТС.</span><span class="sxs-lookup"><span data-stu-id="97e9a-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="97e9a-118">Вы можете обратиться к разработчикам на веб-сайте Microsoft Unified Communications Open Program для [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)взаимодействия по адресу.</span><span class="sxs-lookup"><span data-stu-id="97e9a-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="97e9a-119">Шаг 2: Настройка сервера Lync Server для маршрутизации запросов КСТА на шлюз SIP/КСТА</span><span class="sxs-lookup"><span data-stu-id="97e9a-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="97e9a-120">Вы должны создать статические маршруты для групп Lync Server на целевом адресе (URI сервера) всех шлюзов SIP/КСТА в развертывании, которому планируется перенаправлять запросы на управление удаленными звонками.</span><span class="sxs-lookup"><span data-stu-id="97e9a-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="97e9a-121">Кроме того, необходимо создать надежную запись приложения, соответствующую каждому адресу назначения.</span><span class="sxs-lookup"><span data-stu-id="97e9a-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="97e9a-122">Назначение шлюза в качестве надежного приложения означает, что состояние Trusted является надежным для работы в рамках среды Lync Server, несмотря на то что оно создано сторонним производителем (и запускается как *внешняя служба* ), так как это служба, которая не является встроенный компонент продукта).</span><span class="sxs-lookup"><span data-stu-id="97e9a-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="97e9a-123">Наконец, если Lync Server подключается к шлюзу SIP/КСТА с помощью TCP-соединения вместо подключения TLS, необходимо также определить IP-адрес шлюза с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="97e9a-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="97e9a-124">Дополнительные сведения о настройке статических маршрутов можно найти [в разделе Настройка статического маршрута для удаленного управления звонком в Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="97e9a-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="97e9a-125">Подробнее о настройке записей доверенных приложений можно узнать [в разделе Настройка надежной записи приложения для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="97e9a-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="97e9a-126">Сведения о том, как определить IP-адрес шлюза SIP/КСТА в построителе топологии, можно найти в разделе [Определение IP-адреса шлюза SIP/кста в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span><span class="sxs-lookup"><span data-stu-id="97e9a-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="97e9a-127">Шаг 3: Настройка пользователей Lync для удаленного управления звонками</span><span class="sxs-lookup"><span data-stu-id="97e9a-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="97e9a-128">После того как пользователи будут включены в Lync Server, вы можете включить их для удаленного управления звонками с помощью панели управления Lync Server или командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="97e9a-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="97e9a-129">На этом этапе развертывания вы назначаете каждому пользователю URI сервера линии и универсальный код ресурса (URI) для строки.</span><span class="sxs-lookup"><span data-stu-id="97e9a-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="97e9a-130">Универсальный код ресурса (URI) сервера линии — это URI SIP шлюза SIP/КСТА, который вы планируете назначить пользователю.</span><span class="sxs-lookup"><span data-stu-id="97e9a-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="97e9a-131">Универсальный код ресурса (URI) строки — это уникальный номер телефона, назначенный пользователю.</span><span class="sxs-lookup"><span data-stu-id="97e9a-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="97e9a-132">Подробнее о настройке пользователей для удаленного управления звонками можно узнать [в разделе Включение пользователей Lync для удаленного управления звонками в Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="97e9a-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="97e9a-133">Действие 4: определение правил нормализации номера телефона сервера Lync Server</span><span class="sxs-lookup"><span data-stu-id="97e9a-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="97e9a-134">В сценариях удаленного управления звонками Lync Server использует правила нормализации номера телефона для преобразования телефонных номеров, полученных от шлюза SIP/КСТА, в формат E. 164.</span><span class="sxs-lookup"><span data-stu-id="97e9a-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="97e9a-135">Для правильного функционирования функций удаленного управления звонками номера телефонов должны быть в этом стандартном формате.</span><span class="sxs-lookup"><span data-stu-id="97e9a-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="97e9a-136">Удаленное управление звонками использует те же правила нормализации номеров телефонов, которые настроены для нормализации номеров телефонов службы адресной книги, которые отличаются от правил нормализации номеров телефонов, используемых для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="97e9a-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="97e9a-137">Сведения о том, как удаленное управление звонками использует правила нормализации номера телефона, описаны [в разделе Удаленное управление звонками и нормализация номеров в Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span><span class="sxs-lookup"><span data-stu-id="97e9a-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="97e9a-138">Дополнительные сведения о правилах нормализации номеров телефонов в службе "Адресная книга" можно найти в разделе [Администрирование службы адресной книги в Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="97e9a-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

