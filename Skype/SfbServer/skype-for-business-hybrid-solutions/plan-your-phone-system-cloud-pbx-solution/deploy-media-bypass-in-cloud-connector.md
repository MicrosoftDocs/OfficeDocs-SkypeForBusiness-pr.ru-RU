---
title: Развертывание обхода мультимедиа в Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: В этом разделе вы узнаете о действиях по развертыванию обхода мультимедиа в Cloud Connector Edition версии 2.0 и более поздних версий.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359315"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="4ff91-103">Развертывание обхода мультимедиа в Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="4ff91-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="4ff91-104">Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="4ff91-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="4ff91-105">После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="4ff91-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="4ff91-106">В этом разделе вы узнаете о действиях по развертыванию обхода мультимедиа в Cloud Connector Edition версии 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="4ff91-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="4ff91-107">Обход мультимедиа позволяет клиенту отправлять мультимедиа напрямую на следующий прыжок PSTN (шлюз или пограничный контроллер сеансов) и исключить компонент Cloud Connector Edition из пути мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="4ff91-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="4ff91-108">См. также [планирование обхода мультимедиа в Cloud Connector Edition.](plan-for-media-bypass-in-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="4ff91-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="4ff91-109">Разрешить обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="4ff91-109">Enable media bypass</span></span>

<span data-ttu-id="4ff91-110">Чтобы включить обход мультимедиа, необходимо настроить DNS-имя веб-службы обхода мультимедиа и включить обход мультимедиа в конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="4ff91-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="4ff91-111">Веб-служба обхода сервера-посредника автоматически развертывается на каждом сервере-посреднике.</span><span class="sxs-lookup"><span data-stu-id="4ff91-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="4ff91-112">Администратор клиента должен выбрать имя для службы гибридной голосовой связи (сайта), и это имя должно быть из домена SIP, зарегистрированного для гибридной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4ff91-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="4ff91-113">Имя службы должно быть одинаковым для всех устройств Cloud Connector и всех сайтов STN независимо от расположения клиента.</span><span class="sxs-lookup"><span data-stu-id="4ff91-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="4ff91-114">Веб-служба должна быть доступна только внутри сети.</span><span class="sxs-lookup"><span data-stu-id="4ff91-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="4ff91-115">Администратор клиента должен настроить запись A DNS во внутренней производственной службе Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4ff91-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="4ff91-116">Если у вас сложная многосайтовая среда, см. пример в примере: записи DNS для обхода веб-сайта-посредника [в сложных](deploy-media-bypass-in-cloud-connector.md#Example)многосайтовые среды.</span><span class="sxs-lookup"><span data-stu-id="4ff91-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="4ff91-117">Запись DNS должна разрешаться только для внутренних сетевых клиентов; Она не должна разрешаться для внешних сетевых клиентов.</span><span class="sxs-lookup"><span data-stu-id="4ff91-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="4ff91-118">После настройки DNS подключите Skype для бизнеса Online с помощью удаленной powerShell с учетными данными администратора Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4ff91-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="4ff91-119">Дополнительные сведения [см.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) в этой Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ff91-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="4ff91-120">В сеансе PowerShell введите следующие команды, чтобы включить обход мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="4ff91-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="4ff91-121">Включение обхода мультимедиа — это двухшаговая процедура.</span><span class="sxs-lookup"><span data-stu-id="4ff91-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="4ff91-122">Этот New-CsNetworkMedia не сразу сохраняет новую конфигурацию; Он создает только параметры в памяти.</span><span class="sxs-lookup"><span data-stu-id="4ff91-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="4ff91-123">Объект, созданный этим cmdlet, должен быть сохранен в переменную, а затем назначен свойству MediaBypassSettings конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="4ff91-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="4ff91-124">Дополнительные сведения см. в примере: записи DNS веб-сайта обхода мультимедиа [в сложных многосайтовые среды.](deploy-media-bypass-in-cloud-connector.md#Example)</span><span class="sxs-lookup"><span data-stu-id="4ff91-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="4ff91-125">Репликация между локальной и сетевой компонентами может занять до 24 часов, поэтому корпорация Майкрософт рекомендует выполнить необходимые команды перед включением пользователей.</span><span class="sxs-lookup"><span data-stu-id="4ff91-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="4ff91-126">Подтверждение параметров обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="4ff91-126">Confirm media bypass settings</span></span>

<span data-ttu-id="4ff91-127">Параметры обхода мультимедиа можно проверить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4ff91-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="4ff91-128">Чтобы проверить репликацию через Интернет в пуле клиентов, в удаленной powerShell запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4ff91-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="4ff91-129">Для проверки локальной репликации подключите серверы-посредники Cloud Connector, запустите следующую команду в PowerShell и убедитесь, что enabled=True и AlwaysBypass=True</span><span class="sxs-lookup"><span data-stu-id="4ff91-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="4ff91-130">Чтобы проверить параметры клиента, вы можете выйти из клиента Skype для бизнеса, войти обратно и подтвердить, что клиент получил URL-адрес службы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4ff91-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="4ff91-131">Откройте %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="4ff91-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="4ff91-132">Найди hybridconfigserviceinternalurl и подтвердив, что URL-адрес совпадает с заданным вами.</span><span class="sxs-lookup"><span data-stu-id="4ff91-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="4ff91-133">Изменение параметров обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="4ff91-133">Change media bypass parameters</span></span>

<span data-ttu-id="4ff91-134">Администраторы клиента могут изменить DNS-имя веб-службы, выдав следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4ff91-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="4ff91-135">Клиенты должны выйти и войти, чтобы получить новое имя службы и распознать изменение.</span><span class="sxs-lookup"><span data-stu-id="4ff91-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="4ff91-136">Временное отключение обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="4ff91-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="4ff91-137">Этот сценарий может быть полезен для устранения неполадок или обслуживания.</span><span class="sxs-lookup"><span data-stu-id="4ff91-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="4ff91-138">Чтобы отключить службу, запустите следующие cmdlets:</span><span class="sxs-lookup"><span data-stu-id="4ff91-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="4ff91-139">После внесения изменений может занять некоторое время, чтобы изменения реплицироваться на все cloud Connectors.</span><span class="sxs-lookup"><span data-stu-id="4ff91-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="4ff91-140">Чтобы проверить состояние репликации, запустите следующий cmdlet в PowerShell на серверах-посредниках Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="4ff91-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="4ff91-141">После репликации изменений веб-служба на сервере-посреднике начнет отклонить запросы клиентов для службы обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="4ff91-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="4ff91-142">Окончательное отключение обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="4ff91-142">Disable media bypass permanently</span></span>

<span data-ttu-id="4ff91-143">Чтобы окончательно отключить обход мультимедиа, администратор клиента должен выполнить следующие команды:</span><span class="sxs-lookup"><span data-stu-id="4ff91-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="4ff91-144">Администратору также потребуется удалить веб-адреса для обхода сервера-посредника с внутренних DNS-серверов.</span><span class="sxs-lookup"><span data-stu-id="4ff91-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="4ff91-145">После внесения изменений может занять некоторое время, чтобы изменения реплицироваться на все устройства Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ff91-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="4ff91-146">Пример: записи DNS для обхода веб-сайта-посредника в сложных многосайтовые среды</span><span class="sxs-lookup"><span data-stu-id="4ff91-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="4ff91-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="4ff91-147"><a name="Example"> </a></span></span>

<span data-ttu-id="4ff91-148">Клиенты получат веб-адрес веб-службы обхода сервера-посредника от внутреннего DNS-сервера.</span><span class="sxs-lookup"><span data-stu-id="4ff91-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="4ff91-149">Имя веб-службы будет одинаковым на всех устройствах Cloud Connector и сайтах STN Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ff91-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="4ff91-150">В сложной многосайтовой среде рекомендуется использовать политику DNS Windows 2016 для управления трафиком Geo-Location, чтобы клиенты могли перенаправляться на веб-службу, которая является локальной для их сети.</span><span class="sxs-lookup"><span data-stu-id="4ff91-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="4ff91-151">Дополнительные сведения о политиках DNS Для Windows 2016 см. в Geo-Location управления трафиком на основе Geo-Location с [основными серверами.](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)</span><span class="sxs-lookup"><span data-stu-id="4ff91-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="4ff91-152">Ниже приводится пример конфигурации для компании с несколькими сайтами, использующими политику DNS Windows 2016 для Geo-Location трафика.</span><span class="sxs-lookup"><span data-stu-id="4ff91-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="4ff91-153">Имя службы обхода — hybridvoice.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="4ff91-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="4ff91-154">На сайте в Амстердаме развернуты четыре устройства Cloud Connector со следующими IP-адресами сервера-посредника:</span><span class="sxs-lookup"><span data-stu-id="4ff91-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="4ff91-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="4ff91-155">192.168.1.45</span></span>
    
- <span data-ttu-id="4ff91-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="4ff91-156">192.168.1.46</span></span>
    
- <span data-ttu-id="4ff91-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="4ff91-157">192.168.1.47</span></span>
    
- <span data-ttu-id="4ff91-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="4ff91-158">192.168.1.48</span></span>
    
<span data-ttu-id="4ff91-159">На сайте в Сиэтле развернуты три устройства Cloud Connector со следующими IP-адресами сервера-посредника:</span><span class="sxs-lookup"><span data-stu-id="4ff91-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="4ff91-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="4ff91-160">10.10.1.8</span></span>
    
- <span data-ttu-id="4ff91-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="4ff91-161">10.10.1.9</span></span>
    
- <span data-ttu-id="4ff91-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="4ff91-162">10.10.1.10</span></span>
    
<span data-ttu-id="4ff91-163">Используя Geo-Location трафика, DNS-серверы будут настроены следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4ff91-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="4ff91-164">Создайте клиентские подсети DNS для подсетей в Амстердаме и Сиэтле.</span><span class="sxs-lookup"><span data-stu-id="4ff91-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="4ff91-165">Создайте области зон DNS для adatum.biz в Амстердаме и Сиэтле.</span><span class="sxs-lookup"><span data-stu-id="4ff91-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="4ff91-166">Создайте записи DNS в каждой области зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="4ff91-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="4ff91-167">Амстердам</span><span class="sxs-lookup"><span data-stu-id="4ff91-167">Amsterdam</span></span>
    
   - <span data-ttu-id="4ff91-168">Введите A;</span><span class="sxs-lookup"><span data-stu-id="4ff91-168">Type A;</span></span>
    
   - <span data-ttu-id="4ff91-169">Name : hybridvoice in the adatum.biz DNS zone</span><span class="sxs-lookup"><span data-stu-id="4ff91-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="4ff91-170">Целевой объект: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="4ff91-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="4ff91-171">Создание дополнительных записей для дополнительных серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="4ff91-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="4ff91-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="4ff91-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="4ff91-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="4ff91-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="4ff91-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="4ff91-174">192.168.1.48</span></span>
    
     <span data-ttu-id="4ff91-175">Сиэтл</span><span class="sxs-lookup"><span data-stu-id="4ff91-175">Seattle</span></span>
    
   - <span data-ttu-id="4ff91-176">Тип A</span><span class="sxs-lookup"><span data-stu-id="4ff91-176">Type A</span></span>
    
   - <span data-ttu-id="4ff91-177">Name : hybridvoice in adatum.biz DNS zone</span><span class="sxs-lookup"><span data-stu-id="4ff91-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="4ff91-178">Целевой объект: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="4ff91-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="4ff91-179">Создание дополнительных записей для дополнительных серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="4ff91-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="4ff91-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="4ff91-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="4ff91-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="4ff91-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="4ff91-182">Создайте политику DNS, которая подключает клиентские подсети к соответствующим зонам, чтобы обеспечить необходимое разрешение DNS.</span><span class="sxs-lookup"><span data-stu-id="4ff91-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="4ff91-183">На этом этапе клиенты, делая запросы DNS из подсети Амстердама для hybridvoice.adatum.biz, возвращают 192.168.1.45, Адреса 192.168.1.46, 192.168.1.47 и 192.168.1.48, а клиенты, делая ту же форму запроса Seattle, возвращают 10.10.1.8, 10.10.1.9 и 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="4ff91-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="4ff91-184">Если устройство CCE не получает обновленные параметры, проверьте, может ли устройство связаться с клиентом с помощью удаленной powerShell.</span><span class="sxs-lookup"><span data-stu-id="4ff91-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="4ff91-185">С помощью удаленной powerShell можно проверить состояние устройства с помощью Get-CsHybridPSTNAppliance или с помощью PowerShell на хост-сайте CCE проверить состояние с помощью Get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="4ff91-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="4ff91-186">См. также</span><span class="sxs-lookup"><span data-stu-id="4ff91-186">See also</span></span>
<span data-ttu-id="4ff91-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="4ff91-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="4ff91-188">Планирование обхода сервера-посредника в Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="4ff91-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
