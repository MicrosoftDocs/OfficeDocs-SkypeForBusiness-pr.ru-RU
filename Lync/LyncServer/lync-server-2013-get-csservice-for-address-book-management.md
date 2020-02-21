---
title: 'Lync Server 2013: Get – CsService для управления адресной книгой'
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
ms.openlocfilehash: 8a9e8be425a86eef0d548493e1466888d3d8728c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="6c565-102">Get – CsService для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c565-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c565-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6c565-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6c565-p101">По умолчанию право на локальный запуск командлета Get-CsService имеют члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6c565-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="6c565-106">Get-CsService является ценным для получения и отображения текущей конфигурации определенных веб-служб инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="6c565-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="6c565-107">Если указать полное доменное имя пула и параметр WebServer, командлет возвращает веб-службы, предлагаемые сервером, в том числе URI обработчика адресной книги и расширения списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="6c565-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="6c565-108">Например:</span><span class="sxs-lookup"><span data-stu-id="6c565-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="6c565-109">Этот командлет возвращает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6c565-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="6c565-110">Identity::pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="6c565-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="6c565-111">Хранилище файлов::DC01 хранилища файлов. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="6c565-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="6c565-112">UserServer: UserServer:pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="6c565-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="6c565-113">Примарихттппорт: 80</span><span class="sxs-lookup"><span data-stu-id="6c565-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="6c565-114">Примарихттпспорт: 443</span><span class="sxs-lookup"><span data-stu-id="6c565-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="6c565-115">Екстерналхттппорт: 8080</span><span class="sxs-lookup"><span data-stu-id="6c565-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="6c565-116">Екстерналхттпспорт: 4443</span><span class="sxs-lookup"><span data-stu-id="6c565-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="6c565-117">Публишедпримарихттппорт: 80</span><span class="sxs-lookup"><span data-stu-id="6c565-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="6c565-118">Публишедпримарихттпспорт: 443</span><span class="sxs-lookup"><span data-stu-id="6c565-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="6c565-119">Публишедекстерналхттппорт: 80</span><span class="sxs-lookup"><span data-stu-id="6c565-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="6c565-120">Публишедекстерналхттпспорт: 443</span><span class="sxs-lookup"><span data-stu-id="6c565-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="6c565-121">Реачпримарипсомсерверпорт: 8060</span><span class="sxs-lookup"><span data-stu-id="6c565-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="6c565-122">Реачекстерналпсомсерверпорт: 8061</span><span class="sxs-lookup"><span data-stu-id="6c565-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="6c565-123">Аппшарингпортстарт: 49152</span><span class="sxs-lookup"><span data-stu-id="6c565-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="6c565-124">Аппшарингпорткаунт: 16383</span><span class="sxs-lookup"><span data-stu-id="6c565-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="6c565-125">Лисервицеинтерналури:https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="6c565-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="6c565-126">Абхандлеринтерналури:https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="6c565-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="6c565-127">Абхандлерекстерналури:https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="6c565-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="6c565-128">Длекспансионинтерналури:https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="6c565-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="6c565-129">Длекспансионекстерналури:https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="6c565-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="6c565-130">Кахандлеринтерналури:https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="6c565-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="6c565-131">Кахандлеринтерналанонури:http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="6c565-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="6c565-132">Коллабконтентинтерналури:https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="6c565-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="6c565-133">Коллабконтентекстерналури:https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="6c565-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="6c565-134">Кахандлерекстерналури:https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="6c565-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="6c565-135">Девицеупдатедовнлоадинтерналури:https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="6c565-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="6c565-136">Девицеупдатедовнлоадекстерналури:https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="6c565-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="6c565-137">Девицеупдатестореинтерналури:http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="6c565-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="6c565-138">Девицеупдатесторикстерналури:https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="6c565-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="6c565-139">Ргсажентсервицеинтерналури:https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="6c565-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="6c565-140">Ргсажентсервицеекстерналури:https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="6c565-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="6c565-141">Митекстерналури:https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="6c565-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="6c565-142">Диалинекстерналури:https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="6c565-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="6c565-143">Кскпинтерналури:https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="6c565-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="6c565-144">Реачекстерналури:https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="6c565-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="6c565-145">Реачинтерналури:https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="6c565-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="6c565-146">Вебтиккетекстерналури:https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="6c565-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="6c565-147">Вебтиккетинтерналури:https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="6c565-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="6c565-148">Екстерналфкдн: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c565-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="6c565-149">Интерналфкдн: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6c565-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="6c565-150">Депендентсервицелист: {регистратор:pool01. contoso. NET, КонференЦингсервер:pool01. contoso. NET}</span><span class="sxs-lookup"><span data-stu-id="6c565-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="6c565-151">ServiceId: 1 — WebService — 1</span><span class="sxs-lookup"><span data-stu-id="6c565-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="6c565-152">Сайт: сайт: Redmond</span><span class="sxs-lookup"><span data-stu-id="6c565-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="6c565-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6c565-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="6c565-154">Версия: 5</span><span class="sxs-lookup"><span data-stu-id="6c565-154">Version : 5</span></span>

<span data-ttu-id="6c565-155">Роль: сервер</span><span class="sxs-lookup"><span data-stu-id="6c565-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6c565-156">См. также</span><span class="sxs-lookup"><span data-stu-id="6c565-156">See Also</span></span>


[<span data-ttu-id="6c565-157">Get — CsService</span><span class="sxs-lookup"><span data-stu-id="6c565-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

