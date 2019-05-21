---
title: Развертывание обхода сервера-посредника в Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: В этой статье приведены инструкции по развертыванию обхода мультимедиа с помощью Cloud Connector Edition версии 2,0 и более поздних версий.
ms.openlocfilehash: 6f3ad140d25d5f1d03196e576ac57dc56e905d44
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287547"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="8aeb3-103">Развертывание обхода сервера-посредника в Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="8aeb3-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="8aeb3-104">В этой статье приведены инструкции по развертыванию обхода мультимедиа с помощью Cloud Connector Edition версии 2,0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="8aeb3-105">Обход мультимедиа позволяет клиенту отправлять носители прямо в телефонную сеть с открытым коммутируемым подключением (КТСОП) следующего прыжка (PSTN), например, для связи между шлюзом или сеансом (SBC), и удаления компонента Cloud Connector Edition из пути к носителю.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="8aeb3-106">Ознакомьтесь также [с планами обхода мультимедийных файлов в облаке Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="8aeb3-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="8aeb3-107">Разрешить обход сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="8aeb3-107">Enable media bypass</span></span>

<span data-ttu-id="8aeb3-108">Чтобы разрешить обход сервера-посредника, необходимо настроить DNS-имя веб-службы обхода сервера-посредника, а также включить эту функцию обхода в конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="8aeb3-109">Веб-служба обхода сервера-посредника развертывается автоматически на каждом сервере-посреднике.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="8aeb3-110">Администратор клиента должен выбрать имя гибридной службы голосовой связи (сайт), которое должно принадлежать домену SIP, зарегистрированному для гибридной службы голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="8aeb3-111">Имя службы должно быть одинаковым на всех устройствах с облаком, а также на всех сайтах PSTN, независимо от местонахождения клиента.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="8aeb3-112">Эта веб-служба должна быть доступна только внутри сети.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="8aeb3-113">Администратор клиента должен настроить запись DNS A в службе каталогов Active Directory для внутреннего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="8aeb3-114">Если у вас сложная среда с несколькими сайтами, ознакомьтесь с примером примера [: обход мультимедиа-записей в сложных средах с несколькими сайтами](deploy-media-bypass-in-cloud-connector.md#Example)с помощью DNS.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="8aeb3-115">DNS-запись должна разрешаться только для клиентов внутренней сети; они не должны разрешаться для внешних клиентов сети.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="8aeb3-116">После настройки DNS подключитесь к Skype для бизнеса Online с использованием удаленной среды PowerShell, указав учетные данные администратора Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="8aeb3-117">Дополнительные сведения можно найти в разделе [Настройка компьютера для Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="8aeb3-117">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="8aeb3-118">В сеансе PowerShell введите следующие команды, чтобы разрешить обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="8aeb3-119">Включение обхода мультимедиа состоит из двух этапов.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="8aeb3-120">Командлет New-Кснетворкмедиа не позволяет немедленно сохранить новую конфигурацию; Она только создает параметры в памяти.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="8aeb3-121">Объект, созданный этим командлетом, должен быть сохранен в переменной, а затем назначен свойству Медиабипасссеттингс сетевой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="8aeb3-122">Дополнительные сведения можно найти [в статье пример: обход записей DNS для веб-сайтов в сложных средах с несколькими сайтами](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="8aeb3-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="8aeb3-123">Репликация между локальными компонентами и компонентами в сети может занять до 24 часов, поэтому Майкрософт рекомендует выполнить необходимые команды перед включением пользователей.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="8aeb3-124">Подтвердить параметры обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="8aeb3-124">Confirm media bypass settings</span></span>

<span data-ttu-id="8aeb3-125">Можно проверить параметры обхода сервера-посредника следующим образом. </span><span class="sxs-lookup"><span data-stu-id="8aeb3-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="8aeb3-126">Чтобы проверить репликацию в сети в пул клиентов, выполните в удаленной оболочке PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8aeb3-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="8aeb3-127">Чтобы проверить локальную репликацию, подключитесь к серверам с исправлениями в облаке, выполните следующую команду в PowerShell и убедитесь, что enabled = true и Алвайсбипасс = true</span><span class="sxs-lookup"><span data-stu-id="8aeb3-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="8aeb3-128">Чтобы проверить параметры клиента, выйдите из клиента Skype для бизнеса, войдите в него и убедитесь, что клиент получил URL-адрес службы, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="8aeb3-129">Откройте %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="8aeb3-130">Найдите hybridconfigserviceinternalurl и проверьте, что URL-адрес совпадает с указанным вами.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="8aeb3-131">Изменить параметры обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="8aeb3-131">Change media bypass parameters</span></span>

<span data-ttu-id="8aeb3-132">Администраторы клиента могут изменить имя DNS для веб-службы, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="8aeb3-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="8aeb3-133">Клиентам необходимо выйти из системы и войти в нее, чтобы получить новое имя службы и определить изменение. </span><span class="sxs-lookup"><span data-stu-id="8aeb3-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="8aeb3-134">Временно отключить обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="8aeb3-p106">Этот сценарий может быть полезен для устранения неполадок или обслуживания. Чтобы отключить службу, запустите следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="8aeb3-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="8aeb3-137">Тиражирование внесенных изменений на все экземпляры Cloud Connector может занять определенное время.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="8aeb3-138">Чтобы проверить состояние репликации, выполните следующий командлет в PowerShell на серверах с исправлениями облачного соединителя:</span><span class="sxs-lookup"><span data-stu-id="8aeb3-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="8aeb3-139">После репликации изменений веб-служба на сервере-посреднике начнет отклонять запросы клиентов для службы обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="8aeb3-140">Отключить обход сервера-посредника навсегда</span><span class="sxs-lookup"><span data-stu-id="8aeb3-140">Disable media bypass permanently</span></span>

<span data-ttu-id="8aeb3-141">Чтобы навсегда отключить обход сервера-посредника, администратору клиента необходимо выполнить следующие команды.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="8aeb3-142">Кроме того, администратор должен удалить веб-адреса для обхода севера-посредника с внутренних DNS-серверов.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="8aeb3-143">После внесения изменений может потребоваться некоторое время, чтобы изменения были реплицированы на все устройства облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="8aeb3-144">Пример. Записи DNS веб-сайта обхода сервера-посредника в сложных многосайтовых средах</span><span class="sxs-lookup"><span data-stu-id="8aeb3-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="8aeb3-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="8aeb3-145"></span></span>

<span data-ttu-id="8aeb3-146">Клиенты будут получать веб-адреса веб-службы обхода сервера-посредника с внутреннего DNS-сервера.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="8aeb3-147">Имя веб-службы будет одинаково на всех устройствах с облачным соединителем и на сайтах PSTN-соединителя.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="8aeb3-148">В сложной многосайтовой среде рекомендуется использовать политику DNS Windows 2016 для управления трафиком на основе геолокации, благодаря чему клиенты могут перенаправляться в веб-службу, являющуюся локальной для их сети.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="8aeb3-149">Дополнительные сведения о политиках DNS для Windows 2016 см. [в разделе использование DNS-политики для управления трафиком на основе географических расположений с основными серверами](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="8aeb3-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="8aeb3-150">Ниже приведен пример конфигурации для компании с несколькими сайтами с использованием политики DNS Windows 2016 для управления трафиком на основе геолокации.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="8aeb3-151">Имя для службы пропуска — "hybridvoice.adatum.biz".</span><span class="sxs-lookup"><span data-stu-id="8aeb3-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="8aeb3-152">На сайте Амстердам есть четыре устройства облачного соединителя, развернутые с IP-адресами серверов-исправлений.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="8aeb3-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="8aeb3-153">192.168.1.45</span></span>
    
- <span data-ttu-id="8aeb3-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="8aeb3-154">192.168.1.46</span></span>
    
- <span data-ttu-id="8aeb3-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="8aeb3-155">192.168.1.47</span></span>
    
- <span data-ttu-id="8aeb3-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="8aeb3-156">192.168.1.48</span></span>
    
<span data-ttu-id="8aeb3-157">На сайте в Сиэтле есть три устройства облачного соединителя, развернутые с IP-адресами серверов-исправлений.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="8aeb3-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="8aeb3-158">10.10.1.8</span></span>
    
- <span data-ttu-id="8aeb3-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="8aeb3-159">10.10.1.9</span></span>
    
- <span data-ttu-id="8aeb3-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="8aeb3-160">10.10.1.10</span></span>
    
<span data-ttu-id="8aeb3-161">С помощью управления трафиком на основе геолокации DNS-серверы будут настроены следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="8aeb3-162">Создайте подсети DNS-клиентов для подсетей в Амстердаме и Сиэтле.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="8aeb3-163">Создайте области зоны DNS для adatum.biz в Амстердаме и Сиэтле.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="8aeb3-164">Создавайте записи DNS в каждой области зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="8aeb3-165">Амстердам</span><span class="sxs-lookup"><span data-stu-id="8aeb3-165">Amsterdam</span></span>
    
   - <span data-ttu-id="8aeb3-166">Тип A</span><span class="sxs-lookup"><span data-stu-id="8aeb3-166">Type A;</span></span>
    
   - <span data-ttu-id="8aeb3-167">Имя hybridvoice в зоне DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8aeb3-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="8aeb3-168">Целевой объект: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="8aeb3-168">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="8aeb3-169">Создайте дополнительные записи для дополнительных серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-169">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="8aeb3-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="8aeb3-170">192.168.1.46</span></span>
    
   - <span data-ttu-id="8aeb3-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="8aeb3-171">192.168.1.47</span></span>
    
   - <span data-ttu-id="8aeb3-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="8aeb3-172">192.168.1.48</span></span>
    
     <span data-ttu-id="8aeb3-173">Сиэтл</span><span class="sxs-lookup"><span data-stu-id="8aeb3-173">Seattle</span></span>
    
   - <span data-ttu-id="8aeb3-174">Тип A</span><span class="sxs-lookup"><span data-stu-id="8aeb3-174">Type A</span></span>
    
   - <span data-ttu-id="8aeb3-175">Имя hybridvoice в зоне DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8aeb3-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="8aeb3-176">Целевой объект: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="8aeb3-176">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="8aeb3-177">Создайте дополнительные записи для дополнительных серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-177">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="8aeb3-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="8aeb3-178">10.10.1.9</span></span>
    
   - <span data-ttu-id="8aeb3-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="8aeb3-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="8aeb3-180">Создайте политику DNS, которая подключает клиентские подсети к соответствующим областям зоны, чтобы обеспечить требуемое разрешение DNS.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="8aeb3-181">В таком случае клиентам, создающим DNS-запросы для hybridvoice.adatum.biz из подсети в Амстердаме, вернутся адреса 192.168.1.45, 192.168.1.46, 192.168.1.47 и 192.168.1.48, тогда как клиентам, создающим ту же форму запроса в Сиэтле, вернутся 10.10.1.8, 10.10.1.9 и 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="8aeb3-182">Если устройство КЦЕ не получает обновленные параметры, проверьте, может ли устройство связаться с клиентом через удаленную оболочку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-182">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="8aeb3-183">Вы можете использовать удаленную оболочку PowerShell для проверки состояния устройства с помощью Get-Кшибридпстнапплианце или PowerShell на узле КЦЕ для проверки состояния с помощью Get-Ккапплианцестатус.</span><span class="sxs-lookup"><span data-stu-id="8aeb3-183">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="8aeb3-184">См. также</span><span class="sxs-lookup"><span data-stu-id="8aeb3-184">See also</span></span>
<span data-ttu-id="8aeb3-185"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="8aeb3-185"></span></span>

[<span data-ttu-id="8aeb3-186">Планирование обхода сервера-посредника в Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="8aeb3-186">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
