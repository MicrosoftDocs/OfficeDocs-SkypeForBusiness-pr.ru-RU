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
ms.openlocfilehash: c39520a54ae664a1eddf241cbf1d8d27fe858510
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="b57eb-102">Get – CsService для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b57eb-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b57eb-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b57eb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b57eb-p101">По умолчанию право на локальный запуск командлета Get-CsService имеют члены следующих групп: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b57eb-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="b57eb-106">Get-CsService является ценным для получения и отображения текущей конфигурации определенных веб-служб инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="b57eb-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="b57eb-107">Если указать полное доменное имя пула и параметр WebServer, командлет возвращает веб-службы, предлагаемые сервером, в том числе URI обработчика адресной книги и расширения списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="b57eb-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="b57eb-108">Например:</span><span class="sxs-lookup"><span data-stu-id="b57eb-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="b57eb-109">Этот командлет возвращает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="b57eb-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="b57eb-110">Identity::pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="b57eb-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="b57eb-111">Хранилище файлов::DC01 хранилища файлов. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="b57eb-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="b57eb-112">UserServer: UserServer:pool01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="b57eb-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="b57eb-113">Примарихттппорт: 80</span><span class="sxs-lookup"><span data-stu-id="b57eb-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="b57eb-114">Примарихттпспорт: 443</span><span class="sxs-lookup"><span data-stu-id="b57eb-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="b57eb-115">Екстерналхттппорт: 8080</span><span class="sxs-lookup"><span data-stu-id="b57eb-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="b57eb-116">Екстерналхттпспорт: 4443</span><span class="sxs-lookup"><span data-stu-id="b57eb-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="b57eb-117">Публишедпримарихттппорт: 80</span><span class="sxs-lookup"><span data-stu-id="b57eb-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="b57eb-118">Публишедпримарихттпспорт: 443</span><span class="sxs-lookup"><span data-stu-id="b57eb-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="b57eb-119">Публишедекстерналхттппорт: 80</span><span class="sxs-lookup"><span data-stu-id="b57eb-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="b57eb-120">Публишедекстерналхттпспорт: 443</span><span class="sxs-lookup"><span data-stu-id="b57eb-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="b57eb-121">Реачпримарипсомсерверпорт: 8060</span><span class="sxs-lookup"><span data-stu-id="b57eb-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="b57eb-122">Реачекстерналпсомсерверпорт: 8061</span><span class="sxs-lookup"><span data-stu-id="b57eb-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="b57eb-123">Аппшарингпортстарт: 49152</span><span class="sxs-lookup"><span data-stu-id="b57eb-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="b57eb-124">Аппшарингпорткаунт: 16383</span><span class="sxs-lookup"><span data-stu-id="b57eb-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="b57eb-125">Лисервицеинтерналури:https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="b57eb-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="b57eb-126">Абхандлеринтерналури:https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="b57eb-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="b57eb-127">Абхандлерекстерналури:https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="b57eb-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="b57eb-128">Длекспансионинтерналури:https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="b57eb-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="b57eb-129">Длекспансионекстерналури:https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="b57eb-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="b57eb-130">Кахандлеринтерналури:https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="b57eb-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="b57eb-131">Кахандлеринтерналанонури:http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="b57eb-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="b57eb-132">Коллабконтентинтерналури:https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="b57eb-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="b57eb-133">Коллабконтентекстерналури:https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="b57eb-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="b57eb-134">Кахандлерекстерналури:https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="b57eb-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="b57eb-135">Девицеупдатедовнлоадинтерналури:https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="b57eb-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="b57eb-136">Девицеупдатедовнлоадекстерналури:https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="b57eb-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="b57eb-137">Девицеупдатестореинтерналури:http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="b57eb-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="b57eb-138">Девицеупдатесторикстерналури:https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="b57eb-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="b57eb-139">Ргсажентсервицеинтерналури:https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="b57eb-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="b57eb-140">Ргсажентсервицеекстерналури:https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="b57eb-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="b57eb-141">Митекстерналури:https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="b57eb-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="b57eb-142">Диалинекстерналури:https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="b57eb-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="b57eb-143">Кскпинтерналури:https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="b57eb-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="b57eb-144">Реачекстерналури:https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="b57eb-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="b57eb-145">Реачинтерналури:https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="b57eb-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="b57eb-146">Вебтиккетекстерналури:https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="b57eb-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="b57eb-147">Вебтиккетинтерналури:https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="b57eb-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="b57eb-148">Екстерналфкдн: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b57eb-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="b57eb-149">Интерналфкдн: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b57eb-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="b57eb-150">Депендентсервицелист: {регистратор:pool01. contoso. NET, КонференЦингсервер:pool01. contoso. NET}</span><span class="sxs-lookup"><span data-stu-id="b57eb-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="b57eb-151">ServiceId: 1 — WebService — 1</span><span class="sxs-lookup"><span data-stu-id="b57eb-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="b57eb-152">Сайт: сайт: Redmond</span><span class="sxs-lookup"><span data-stu-id="b57eb-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="b57eb-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b57eb-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="b57eb-154">Версия: 5</span><span class="sxs-lookup"><span data-stu-id="b57eb-154">Version : 5</span></span>

<span data-ttu-id="b57eb-155">Роль: сервер</span><span class="sxs-lookup"><span data-stu-id="b57eb-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b57eb-156">См. также</span><span class="sxs-lookup"><span data-stu-id="b57eb-156">See Also</span></span>


[<span data-ttu-id="b57eb-157">Get — CsService</span><span class="sxs-lookup"><span data-stu-id="b57eb-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

