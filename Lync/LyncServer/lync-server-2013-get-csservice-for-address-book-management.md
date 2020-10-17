---
title: 'Lync Server 2013: Get-CsService для управления адресной книгой'
description: 'Lync Server 2013: Get-CsService для управления адресной книгой.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e46173429988d87022c13fab33e3778279dd0e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554655"
---
# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="da135-103">Get-CsService для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da135-103">Get-CsService for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da135-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="da135-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="da135-p101">По умолчанию право на локальный запуск командлета Get-CsService имеют члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="da135-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="da135-107">Get-CsService полезен для получения и отображения текущей конфигурации определенных веб-служб инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="da135-107">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="da135-108">Если указать полное доменное имя пула и параметр WebServer, командлет возвращает веб-службы, предлагаемые сервером, в том числе URI обработчика адресной книги и расширения списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="da135-108">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="da135-109">Например:</span><span class="sxs-lookup"><span data-stu-id="da135-109">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="da135-110">Этот командлет возвращает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="da135-110">This cmdlet returns the following:</span></span>

<span data-ttu-id="da135-111">Identity::pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="da135-111">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="da135-112">Хранилище файлов::DC01 хранилища файлов. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="da135-112">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="da135-113">UserServer: UserServer:pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="da135-113">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="da135-114">Примарихттппорт: 80</span><span class="sxs-lookup"><span data-stu-id="da135-114">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="da135-115">Примарихттпспорт: 443</span><span class="sxs-lookup"><span data-stu-id="da135-115">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="da135-116">Екстерналхттппорт: 8080</span><span class="sxs-lookup"><span data-stu-id="da135-116">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="da135-117">Екстерналхттпспорт: 4443</span><span class="sxs-lookup"><span data-stu-id="da135-117">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="da135-118">Публишедпримарихттппорт: 80</span><span class="sxs-lookup"><span data-stu-id="da135-118">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="da135-119">Публишедпримарихттпспорт: 443</span><span class="sxs-lookup"><span data-stu-id="da135-119">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="da135-120">Публишедекстерналхттппорт: 80</span><span class="sxs-lookup"><span data-stu-id="da135-120">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="da135-121">Публишедекстерналхттпспорт: 443</span><span class="sxs-lookup"><span data-stu-id="da135-121">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="da135-122">Реачпримарипсомсерверпорт: 8060</span><span class="sxs-lookup"><span data-stu-id="da135-122">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="da135-123">Реачекстерналпсомсерверпорт: 8061</span><span class="sxs-lookup"><span data-stu-id="da135-123">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="da135-124">Аппшарингпортстарт: 49152</span><span class="sxs-lookup"><span data-stu-id="da135-124">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="da135-125">Аппшарингпорткаунт: 16383</span><span class="sxs-lookup"><span data-stu-id="da135-125">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="da135-126">Лисервицеинтерналури: https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="da135-126">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="da135-127">Абхандлеринтерналури: https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="da135-127">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="da135-128">Абхандлерекстерналури: https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="da135-128">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="da135-129">Длекспансионинтерналури: https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="da135-129">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="da135-130">Длекспансионекстерналури: https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="da135-130">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="da135-131">Кахандлеринтерналури: https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="da135-131">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="da135-132">Кахандлеринтерналанонури: http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="da135-132">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="da135-133">Коллабконтентинтерналури: https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="da135-133">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="da135-134">Коллабконтентекстерналури: https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="da135-134">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="da135-135">Кахандлерекстерналури: https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="da135-135">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="da135-136">Девицеупдатедовнлоадинтерналури: https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="da135-136">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="da135-137">Девицеупдатедовнлоадекстерналури: https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="da135-137">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="da135-138">Девицеупдатестореинтерналури: http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="da135-138">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="da135-139">Девицеупдатесторикстерналури: https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="da135-139">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="da135-140">Ргсажентсервицеинтерналури: https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="da135-140">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="da135-141">Ргсажентсервицеекстерналури: https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="da135-141">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="da135-142">Митекстерналури: https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="da135-142">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="da135-143">Диалинекстерналури: https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="da135-143">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="da135-144">Кскпинтерналури: https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="da135-144">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="da135-145">Реачекстерналури: https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="da135-145">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="da135-146">Реачинтерналури: https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="da135-146">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="da135-147">Вебтиккетекстерналури: https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="da135-147">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="da135-148">Вебтиккетинтерналури: https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="da135-148">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="da135-149">Екстерналфкдн: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="da135-149">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="da135-150">Интерналфкдн: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="da135-150">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="da135-151">Депендентсервицелист: {регистратор:pool01. contoso. NET, КонференЦингсервер:pool01. contoso. NET}</span><span class="sxs-lookup"><span data-stu-id="da135-151">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="da135-152">ServiceId: 1 — WebService — 1</span><span class="sxs-lookup"><span data-stu-id="da135-152">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="da135-153">Сайт: сайт: Redmond</span><span class="sxs-lookup"><span data-stu-id="da135-153">SiteId : Site:Redmond</span></span>

<span data-ttu-id="da135-154">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="da135-154">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="da135-155">Версия: 5</span><span class="sxs-lookup"><span data-stu-id="da135-155">Version : 5</span></span>

<span data-ttu-id="da135-156">Роль: сервер</span><span class="sxs-lookup"><span data-stu-id="da135-156">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="da135-157">См. также</span><span class="sxs-lookup"><span data-stu-id="da135-157">See Also</span></span>


[<span data-ttu-id="da135-158">Get — CsService</span><span class="sxs-lookup"><span data-stu-id="da135-158">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

