---
title: Развертывание обхода сервера-посредника в Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Прочтите этот раздел, чтобы узнать о шаги развертывания, что сервера-посредника Edition соединителя облачных версии 2.0 и более поздней версии с.
ms.openlocfilehash: a9f03d1d83d398a6aa78f90a4741d0010ea50392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="7a5f6-103">Развертывание обхода сервера-посредника в Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="7a5f6-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="7a5f6-104">Прочтите этот раздел, чтобы узнать о шаги развертывания, что сервера-посредника Edition соединителя облачных версии 2.0 и более поздней версии с.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="7a5f6-105">Обход сервера-посредника позволяет клиентским отправить мультимедиа следующего прыжка общедоступных переключения телефонной сети общего пользования (PSTN) — шлюза или пограничный контроллер сеансов (SBC) — и ликвидировать компонент Edition соединителя облака из пути.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="7a5f6-106">Смотрите также [Планирование мультимедиа обходить в облаке соединителя Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="7a5f6-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="7a5f6-107">Разрешить обход сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="7a5f6-107">Enable media bypass</span></span>

<span data-ttu-id="7a5f6-108">Чтобы разрешить обход сервера-посредника, необходимо настроить DNS-имя веб-службы обхода сервера-посредника, а также включить эту функцию обхода в конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="7a5f6-109">Веб-служба обхода сервера-посредника развертывается автоматически на каждом сервере-посреднике.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="7a5f6-110">Администратор клиента должен выбрать имя гибридной службы голосовой связи (сайт), которое должно принадлежать домену SIP, зарегистрированному для гибридной службы голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="7a5f6-111">Имя службы должны совпадать на всех устройств для облачных соединителя и все сайты PSTN, независимо от расположения клиента.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="7a5f6-112">Эта веб-служба должна быть доступна только внутри сети.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="7a5f6-113">Администратор клиента должен настроить запись DNS A во внутренней рабочей среде Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="7a5f6-114">Если у вас есть сложных сред нескольких сайтах, см в [Пример: веб-узла DNS-записей в сложных средах с несколькими веб-посредника](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="7a5f6-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="7a5f6-115">Эта запись DNS должна разрешаться только для внутренних, а не для внешних клиентов сети.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="7a5f6-116">После настройки DNS подключитесь к Skype для бизнеса Online с использованием удаленной среды PowerShell, указав учетные данные администратора Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="7a5f6-117">Для получения дополнительных сведений см [Скайп для бизнеса в Интернет с помощью Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="7a5f6-117">For more information, see [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="7a5f6-118">В сеансе PowerShell введите следующие команды, чтобы разрешить обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="7a5f6-119">Включение обхода сервера-посредника осуществляется в два этапа.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="7a5f6-120">Командлет New-CsNetworkMedia не выполняет немедленное сохранение новой конфигурации и лишь создает параметры в памяти.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="7a5f6-121">Объект, созданный данным командлетом, должен быть сохранен в переменную и затем передан в качестве параметра MediaBypassSettings конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="7a5f6-122">Дополнительные сведения можно [Пример: веб-узел DNS-записей в сложных средах с несколькими веб-посредника](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="7a5f6-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="7a5f6-123">Репликации между локальной и компонентов online может занять более 24 часов, корпорация Майкрософт рекомендует выполните необходимые команды перед включением пользователей.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="7a5f6-124">Подтвердить параметры обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="7a5f6-124">Confirm media bypass settings</span></span>

<span data-ttu-id="7a5f6-125">Можно проверить параметры обхода сервера-посредника следующим образом. </span><span class="sxs-lookup"><span data-stu-id="7a5f6-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="7a5f6-126">Для проверки сети репликации в пул клиента, выполните следующую команду в удаленной оболочки PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7a5f6-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore

```

<span data-ttu-id="7a5f6-127">Установите флажок репликация локальных, подключиться к серверов-посредников соединителя облаке, выполните следующую команду в PowerShell и убедитесь, что включено — значение True, а параметру AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="7a5f6-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="7a5f6-128">Чтобы проверить параметры клиента, выход из Скайп для клиента Business, снова выполните вход и убедитесь, что клиент получил URL-адрес службы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7a5f6-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="7a5f6-129">Откройте %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. </span><span class="sxs-lookup"><span data-stu-id="7a5f6-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="7a5f6-130">Поиск hybridconfigserviceinternalurl и убедитесь, что URL-адрес совпадает с тем, которую вы задали.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="7a5f6-131">Изменить параметры обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="7a5f6-131">Change media bypass parameters</span></span>

<span data-ttu-id="7a5f6-132">Администраторы клиента могут изменить имя DNS для веб-службы, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="7a5f6-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="7a5f6-133">Клиентам необходимо выйти из системы и войти в нее, чтобы получить новое имя службы и определить изменение. </span><span class="sxs-lookup"><span data-stu-id="7a5f6-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="7a5f6-134">Временно отключить обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="7a5f6-p106">Этот сценарий может быть полезен для устранения неполадок или обслуживания. Чтобы отключить службу, запустите следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="7a5f6-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="7a5f6-137">Тиражирование внесенных изменений на все экземпляры Cloud Connector может занять определенное время.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="7a5f6-138">Чтобы проверить состояние репликации, выполните следующий командлет в PowerShell на серверы-посредники соединителя облаке:</span><span class="sxs-lookup"><span data-stu-id="7a5f6-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="7a5f6-139">После репликации изменений веб-служба на сервере-посреднике начнет отклонять запросы клиентов для службы обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="7a5f6-140">Отключить обход сервера-посредника навсегда</span><span class="sxs-lookup"><span data-stu-id="7a5f6-140">Disable media bypass permanently</span></span>

<span data-ttu-id="7a5f6-141">Чтобы навсегда отключить обход сервера-посредника, администратору клиента необходимо выполнить следующие команды. </span><span class="sxs-lookup"><span data-stu-id="7a5f6-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="7a5f6-142">Кроме того, администратор должен удалить веб-адреса для обхода севера-посредника с внутренних DNS-серверов.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="7a5f6-143">После внесения изменений, может занять некоторое время изменения будут реплицированы во всех устройств для соединителя облака.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="7a5f6-144">Пример. Записи DNS веб-сайта обхода сервера-посредника в сложных многосайтовых средах</span><span class="sxs-lookup"><span data-stu-id="7a5f6-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="7a5f6-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="7a5f6-145"></span></span>

<span data-ttu-id="7a5f6-146">Клиенты будут получать веб-адреса веб-службы обхода сервера-посредника с внутреннего DNS-сервера.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="7a5f6-147">Имя веб-службы будет совпадать во всех устройств для облачных соединителя и облачных соединителя PSTN сайтов.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="7a5f6-148">В сложной многосайтовой среде рекомендуется использовать политику DNS Windows 2016 для управления трафиком на основе геолокации, благодаря чему клиенты могут перенаправляться в веб-службу, являющуюся локальной для их сети.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="7a5f6-149">Дополнительные сведения о политиках DNS 2016 Windows [Использовать DNS политику для управления трафика на основе географического расположения, с основным серверами](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location)см.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="7a5f6-150">Ниже приведен пример конфигурации для компании с несколькими сайтами с использованием политики DNS Windows 2016 для управления трафиком на основе геолокации.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="7a5f6-151">Имя службы сервера-посредника — «hybridvoice.adatum.biz».</span><span class="sxs-lookup"><span data-stu-id="7a5f6-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="7a5f6-152">Сайт в Амстердам имеет четыре appliances соединителя облачных развернуты следующие Mediation Server IP-адреса:</span><span class="sxs-lookup"><span data-stu-id="7a5f6-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="7a5f6-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="7a5f6-153">192.168.1.45</span></span>
    
- <span data-ttu-id="7a5f6-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="7a5f6-154">192.168.1.46</span></span>
    
- <span data-ttu-id="7a5f6-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="7a5f6-155">192.168.1.47</span></span>
    
- <span data-ttu-id="7a5f6-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="7a5f6-156">192.168.1.48</span></span>
    
<span data-ttu-id="7a5f6-157">Сайт в Сиэтл содержит три облака соединителя устройств для развертывания следующих Mediation Server IP-адреса:</span><span class="sxs-lookup"><span data-stu-id="7a5f6-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="7a5f6-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="7a5f6-158">10.10.1.8</span></span>
    
- <span data-ttu-id="7a5f6-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="7a5f6-159">10.10.1.9</span></span>
    
- <span data-ttu-id="7a5f6-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="7a5f6-160">10.10.1.10</span></span>
    
<span data-ttu-id="7a5f6-161">С помощью управления трафиком на основе геолокации DNS-серверы будут настроены следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="7a5f6-162">Создайте подсети DNS-клиентов для подсетей в Амстердаме и Сиэтле.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="7a5f6-163">Создайте области зоны DNS для adatum.biz в Амстердаме и Сиэтле.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="7a5f6-164">Создавайте записи DNS в каждой области зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="7a5f6-165">Амстердам</span><span class="sxs-lookup"><span data-stu-id="7a5f6-165">Amsterdam</span></span>
    
  - <span data-ttu-id="7a5f6-166">Тип A</span><span class="sxs-lookup"><span data-stu-id="7a5f6-166">Type A;</span></span>
    
  - <span data-ttu-id="7a5f6-167">Имя hybridvoice в зоне DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="7a5f6-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="7a5f6-168">Целевой объект: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="7a5f6-168">Target: 192.168.1.45</span></span>
    
    <span data-ttu-id="7a5f6-169">Создайте дополнительные записи для дополнительных серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-169">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="7a5f6-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="7a5f6-170">192.168.1.46</span></span>
    
  - <span data-ttu-id="7a5f6-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="7a5f6-171">192.168.1.47</span></span>
    
  - <span data-ttu-id="7a5f6-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="7a5f6-172">192.168.1.48</span></span>
    
    <span data-ttu-id="7a5f6-173">Сиэтл</span><span class="sxs-lookup"><span data-stu-id="7a5f6-173">Seattle</span></span>
    
  - <span data-ttu-id="7a5f6-174">Тип A</span><span class="sxs-lookup"><span data-stu-id="7a5f6-174">Type A</span></span>
    
  - <span data-ttu-id="7a5f6-175">Имя hybridvoice в зоне DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="7a5f6-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="7a5f6-176">Целевой объект: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="7a5f6-176">Target: 10.10.1.8</span></span>
    
    <span data-ttu-id="7a5f6-177">Создайте дополнительные записи для дополнительных серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-177">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="7a5f6-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="7a5f6-178">10.10.1.9</span></span>
    
  - <span data-ttu-id="7a5f6-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="7a5f6-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="7a5f6-180">Создайте политику DNS, которая подключает клиентские подсети к соответствующим областям зоны, чтобы обеспечить требуемое разрешение DNS.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="7a5f6-181">В таком случае клиентам, создающим DNS-запросы для hybridvoice.adatum.biz из подсети в Амстердаме, вернутся адреса 192.168.1.45, 192.168.1.46, 192.168.1.47 и 192.168.1.48, тогда как клиентам, создающим ту же форму запроса в Сиэтле, вернутся 10.10.1.8, 10.10.1.9 и 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7a5f6-182">Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-182">See also</span></span>
<span data-ttu-id="7a5f6-183"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="7a5f6-183"></span></span>

#### 

[<span data-ttu-id="7a5f6-184">Планирование для сервера-посредника в облаке соединителя Edition</span><span class="sxs-lookup"><span data-stu-id="7a5f6-184">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)

