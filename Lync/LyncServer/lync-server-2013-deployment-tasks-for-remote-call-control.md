---
title: 'Lync Server 2013: задачи развертывания для удаленного управления звонками'
description: 'Lync Server 2013: задачи развертывания для удаленного управления звонками.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61d0d57489bd93d7e6ce0209c605f05a2417bded
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553585"
---
# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="2fa17-103">Задачи развертывания для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fa17-103">Deployment tasks for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fa17-104">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="2fa17-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="2fa17-105">В этом разделе описываются задачи развертывания, которые необходимо выполнить, чтобы включить удаленное управление звонками для пользователей в среде Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2fa17-105">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2fa17-106">Если вы переносите пользователей, для которых ранее было включено удаленное управление звонками в Microsoft Office Communicator 2007 R2, перед выполнением задач по развертыванию удаленного управления звонками, описанных в этом разделе, необходимо выполнить дополнительную задачу развертывания.</span><span class="sxs-lookup"><span data-stu-id="2fa17-106">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="2fa17-107">В процессе миграции на Lync Server записи доверенных приложений (ранее известные как <EM>Авторизованные записи узла</EM>) необходимо удалить с помощью средств администрирования Office Communications Server 2007 R2, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="2fa17-107">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="2fa17-108">Более подробную информацию об удалении авторизованных узлов можно узнать <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">в статье удаление устаревшего авторизованного узла в Lync Server 2013 (необязательно)</A>.</span><span class="sxs-lookup"><span data-stu-id="2fa17-108">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="2fa17-109">Шаг 1. Установка и настройка шлюза SIP/CSTA для взаимодействия с PBX</span><span class="sxs-lookup"><span data-stu-id="2fa17-109">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="2fa17-110">Необходимо установить по крайней мере один шлюз SIP/CSTA, который может подключаться к Lync Server и существующей УАТС в вашей среде, чтобы обеспечить функции управления удаленными звонками для пользователей.</span><span class="sxs-lookup"><span data-stu-id="2fa17-110">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="2fa17-111">Шлюз SIP/CSTA — это шлюз между SIP и телекоммуникационным приложением с компьютерной поддержкой (CSTA).</span><span class="sxs-lookup"><span data-stu-id="2fa17-111">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="2fa17-112">Вне зависимости от того, сколько шлюзов вы устанавливаете (несколько или всего один), для каждого пользователя можно настроить только один шлюз или PBX.</span><span class="sxs-lookup"><span data-stu-id="2fa17-112">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="2fa17-113">Если у существующей системы PBX отсутствует интерфейс SIP/CSTA, обязательно разверните шлюз SIP/CSTA, который может поддерживать PBX, включая поддержку служебных сигнальных протоколов PBX конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="2fa17-113">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="2fa17-114">Для получения подробных сведений о возможностях обращайтесь непосредственно к каждому поставщику.</span><span class="sxs-lookup"><span data-stu-id="2fa17-114">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="2fa17-115">Когда вы будете готовы развернуть шлюз SIP/CSTA, который может интегрироваться с Lync Server для удаленного управления звонками, также обратитесь к поставщику шлюза или документации шлюза поставщика относительно синтаксиса, требуемого шлюзом, для получения следующих сведений:</span><span class="sxs-lookup"><span data-stu-id="2fa17-115">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="2fa17-116">Линейный серверный идентификатор URI шлюза</span><span class="sxs-lookup"><span data-stu-id="2fa17-116">Line server URI of the gateway</span></span>

  - <span data-ttu-id="2fa17-117">Линейный идентификатор URI для пользователей, которые будут назначены шлюзу</span><span class="sxs-lookup"><span data-stu-id="2fa17-117">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="2fa17-118">Предыдущие параметры являются обязательными при конфигурировании пользователя и должны быть указаны в соответствии с требованиями шлюза для надлежащей маршрутизации и подключения к PBX.</span><span class="sxs-lookup"><span data-stu-id="2fa17-118">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="2fa17-119">Вы можете обращаться к поставщикам на веб-сайте с открытым программным обеспечением Microsoft Unified Communications [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) .</span><span class="sxs-lookup"><span data-stu-id="2fa17-119">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="2fa17-120">Шаг 2. Настройка сервера Lync для маршрутизации запросов CSTA, передаваемых на шлюз SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="2fa17-120">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="2fa17-121">Статические маршруты на пулах Lync Server необходимо создать в конечном адресе (URI сервера) всех шлюзов SIP/CSTA в развертывании, к которым планируется маршрутизировать запросы на управление удаленными звонками.</span><span class="sxs-lookup"><span data-stu-id="2fa17-121">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="2fa17-122">Необходимо также создать запись доверенного приложения, соответствующую каждому адресу назначения.</span><span class="sxs-lookup"><span data-stu-id="2fa17-122">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="2fa17-123">При назначении шлюза в качестве доверенного приложения оно получает состояние доверия для запуска в среде Lync Server, несмотря на то, что оно разработано сторонним производителем (и выполняет то, что называется *внешней службой* , так как это служба, которая не является встроенной частью продукта).</span><span class="sxs-lookup"><span data-stu-id="2fa17-123">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="2fa17-124">Наконец, если Lync Server будет подключаться к шлюзу SIP/CSTA с использованием TCP-подключения, а не подключения TLS, необходимо также определить IP-адрес шлюза с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="2fa17-124">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="2fa17-125">Подробнее о настройке статических маршрутов можно узнать [в статье Настройка статического маршрута для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="2fa17-125">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="2fa17-126">Дополнительные сведения о настройке записей доверенных приложений можно найти [в статье Настройка надежной записи приложения для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="2fa17-126">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="2fa17-127">Дополнительные сведения об определении IP-адреса шлюза SIP/CSTA в построителе топологий можно узнать в статье [Определение IP-адреса шлюза SIP/CSTA в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span><span class="sxs-lookup"><span data-stu-id="2fa17-127">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="2fa17-128">Шаг 3: Настройка пользователей Lync для удаленного управления звонками</span><span class="sxs-lookup"><span data-stu-id="2fa17-128">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="2fa17-129">После включения для пользователей Lync Server вы можете включить их для удаленного управления вызовами с помощью панели управления Lync Server или командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2fa17-129">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="2fa17-130">На этом этапе развертывания вы назначаете каждому пользователю линейный серверный идентификатор URI и линейный идентификатор URI.</span><span class="sxs-lookup"><span data-stu-id="2fa17-130">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="2fa17-131">Линейный серверный идентификатор URI — это идентификатор URI SIP шлюза SIP/CSTA, который вы собираетесь назначить пользователю.</span><span class="sxs-lookup"><span data-stu-id="2fa17-131">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="2fa17-132">Линейный идентификатор URI — это уникальный телефонный номер, назначаемый пользователю.</span><span class="sxs-lookup"><span data-stu-id="2fa17-132">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="2fa17-133">Дополнительные сведения о настройке пользователей для удаленного управления звонками можно узнать [в статье Включение удаленного управления звонками для пользователей Lync в Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="2fa17-133">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="2fa17-134">Шаг 4. Определение правил нормализации номеров телефона сервера Lync Server</span><span class="sxs-lookup"><span data-stu-id="2fa17-134">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="2fa17-135">В сценариях удаленного управления звонками Lync Server использует правила нормализации телефонных номеров для преобразования телефонных номеров, получаемых с шлюза SIP/CSTA, в формат E. 164.</span><span class="sxs-lookup"><span data-stu-id="2fa17-135">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="2fa17-136">Для правильного функционирования функций удаленного управления звонками в этом стандартизированном формате должны использоваться номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="2fa17-136">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="2fa17-137">Удаленное управление звонками использует те же правила нормализации телефонных номеров, которые настроены для нормализации номера телефона службы адресной книги, которые отличаются от правил нормализации телефонных номеров, используемых для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2fa17-137">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="2fa17-138">Сведения о том, как удаленный контроль звонков использует правила нормализации телефонных номеров, приведен [в статье Remote Call Control и нормализация телефонных номеров в Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span><span class="sxs-lookup"><span data-stu-id="2fa17-138">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="2fa17-139">Дополнительные сведения о правилах нормализации телефонных номеров для службы адресной книги можно найти в статье [Администрирование службы адресной книги в Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="2fa17-139">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

