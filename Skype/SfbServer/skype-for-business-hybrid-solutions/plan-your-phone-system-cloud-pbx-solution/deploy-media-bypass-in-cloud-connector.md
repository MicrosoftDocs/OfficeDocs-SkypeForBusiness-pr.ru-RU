---
title: Развертывание обхода сервера мультимедиа в Cloud Connector Edition
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
description: В этом разделе приведены инструкции по развертыванию обхода сервера-посредника с помощью Cloud Connector Edition версии 2,0 и более поздних версий.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359315"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="4976b-103">Развертывание обхода сервера мультимедиа в Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="4976b-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="4976b-104">Cloud Connector Edition выйдет 31 июля 2021 вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="4976b-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="4976b-105">После обновления вашей организации до Teams Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="4976b-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="4976b-106">В этом разделе приведены инструкции по развертыванию обхода сервера-посредника с помощью Cloud Connector Edition версии 2,0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="4976b-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="4976b-107">Обход сервера-посредника позволяет клиенту отправлять мультимедиа напрямую на следующий транзитный номер телефонной сети общего пользования (PSTN), шлюз или пограничный контроллер сеансов (SBC), а также удалять компонент Cloud Connector Edition из пути к носителю.</span><span class="sxs-lookup"><span data-stu-id="4976b-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="4976b-108">В этой статье вы также можете найти [обход сервера мультимедиа в Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="4976b-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="4976b-109">Разрешить обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="4976b-109">Enable media bypass</span></span>

<span data-ttu-id="4976b-110">Чтобы включить обход сервера-посредника, необходимо настроить DNS-имя веб-службы обхода сервера-посредника и включить обход сервера-посредника в конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="4976b-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="4976b-111">Веб-служба обхода сервера-посредника развертывается автоматически на каждом сервере-посреднике.</span><span class="sxs-lookup"><span data-stu-id="4976b-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="4976b-112">Администратор клиента должен выбрать имя для гибридной службы голосовой связи (Site), а это имя должно быть из домена SIP, зарегистрированного для гибридной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4976b-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="4976b-113">Имя службы должно быть одинаковым для всех устройств Cloud Connector и всех сайтов PSTN независимо от расположения клиента.</span><span class="sxs-lookup"><span data-stu-id="4976b-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="4976b-114">Веб-служба должна быть доступна только для внутреннего использования в сети.</span><span class="sxs-lookup"><span data-stu-id="4976b-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="4976b-115">Администратор клиента должен настроить запись A DNS во внутреннем рабочем каталоге Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4976b-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="4976b-116">Если у вас сложная среда с несколькими сайтами, ознакомьтесь с примером примера [: обход сервера DNS в сложных средах с несколькими сайтами](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="4976b-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="4976b-117">DNS-запись должна разрешаться только для клиентов внутренней сети; она не должна разрешаться для клиентов внешней сети.</span><span class="sxs-lookup"><span data-stu-id="4976b-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="4976b-118">После настройки DNS подключитесь к Skype для бизнеса Online, используя удаленную оболочку PowerShell с учетными данными администратора Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4976b-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="4976b-119">Для получения дополнительных сведений ознакомьтесь со статьей [Настройка компьютера для Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="4976b-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="4976b-120">В сеансе PowerShell введите следующие команды, чтобы включить обход сервера мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="4976b-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="4976b-121">Включение обхода сервера-посредника состоит из двух этапов.</span><span class="sxs-lookup"><span data-stu-id="4976b-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="4976b-122">Командлет New – Кснетворкмедиа не сохраняет новую конфигурацию сразу. Он только создает параметры в памяти.</span><span class="sxs-lookup"><span data-stu-id="4976b-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="4976b-123">Объект, созданный этим командлетом, должен быть сохранен в переменной, а затем назначен свойству Медиабипасссеттингс конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="4976b-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="4976b-124">Для получения дополнительных сведений см. [Пример: обход DNS-записей веб-сайта в сложных средах с несколькими сайтами](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="4976b-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="4976b-125">Репликация между локальными компонентами и компонентами в сети может занять до 24 часов, поэтому Майкрософт рекомендует выполнить необходимые команды перед включением пользователей.</span><span class="sxs-lookup"><span data-stu-id="4976b-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="4976b-126">Подтверждение параметров обхода сервера мультимедиа</span><span class="sxs-lookup"><span data-stu-id="4976b-126">Confirm media bypass settings</span></span>

<span data-ttu-id="4976b-127">Параметры обхода сервера мультимедиа можно проверить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4976b-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="4976b-128">Чтобы проверить репликацию по сети в пул клиентов, выполните следующую команду в удаленной консоли PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4976b-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="4976b-129">Чтобы проверить локальную репликацию, подключитесь к серверам-посредникам Cloud Connector, выполните следующую команду в PowerShell и убедитесь, что enabled = true и AlwaysBypass = true</span><span class="sxs-lookup"><span data-stu-id="4976b-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="4976b-130">Чтобы проверить параметры клиента, выйдите из клиента Skype для бизнеса, войдите обратно и убедитесь, что клиент получил URL-адрес службы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4976b-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="4976b-131">Открытие%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="4976b-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="4976b-132">Выполните поиск hybridconfigserviceinternalurl и убедитесь, что URL-адрес соответствует заданному.</span><span class="sxs-lookup"><span data-stu-id="4976b-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="4976b-133">Изменение параметров обхода сервера мультимедиа</span><span class="sxs-lookup"><span data-stu-id="4976b-133">Change media bypass parameters</span></span>

<span data-ttu-id="4976b-134">Администраторы клиентов могут изменить DNS-имя веб-службы, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="4976b-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="4976b-135">Клиентам необходимо выйти из службы и войти в нее, чтобы получить новое имя службы и распознать изменение.</span><span class="sxs-lookup"><span data-stu-id="4976b-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="4976b-136">Временное отключение обхода сервера мультимедиа</span><span class="sxs-lookup"><span data-stu-id="4976b-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="4976b-137">Этот сценарий может быть полезен для устранения неполадок и обслуживания.</span><span class="sxs-lookup"><span data-stu-id="4976b-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="4976b-138">Чтобы отключить службу, выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="4976b-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="4976b-139">После внесения изменений репликация на все облачные соединители может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="4976b-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="4976b-140">Чтобы проверить состояние репликации, выполните следующий командлет в PowerShell на серверах-посредниках Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="4976b-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="4976b-141">После репликации изменений веб-служба на сервере-посреднике начнет отклонять запросы клиентов для службы обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="4976b-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="4976b-142">Постоянное отключение обхода сервера мультимедиа</span><span class="sxs-lookup"><span data-stu-id="4976b-142">Disable media bypass permanently</span></span>

<span data-ttu-id="4976b-143">Чтобы окончательно отключить обход сервера клиентского данных, администратору клиента необходимо выполнить следующие команды:</span><span class="sxs-lookup"><span data-stu-id="4976b-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="4976b-144">Кроме того, администратору потребуется удалить веб-адреса для обхода сервера-посредника с внутренних DNS-серверов.</span><span class="sxs-lookup"><span data-stu-id="4976b-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="4976b-145">После внесения изменений может потребоваться некоторое время для репликации изменений на все устройства Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4976b-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="4976b-146">Пример: обход сервера-посредника DNS-записей в сложных средах с несколькими сайтами</span><span class="sxs-lookup"><span data-stu-id="4976b-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="4976b-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="4976b-147"><a name="Example"> </a></span></span>

<span data-ttu-id="4976b-148">Клиенты получат веб-адрес веб-службы обхода сервера-посредника на внутреннем DNS-сервере.</span><span class="sxs-lookup"><span data-stu-id="4976b-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="4976b-149">Имя веб-службы будет одинаковым для всех устройств Cloud Connector и сайтов PSTN Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4976b-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="4976b-150">В сложной среде с несколькими сайтами мы рекомендуем использовать политику DNS Windows 2016 для управления трафиком на основе географических расположений, чтобы клиенты могли перенаправляться в веб-службу, которая является локальной для своей сети.</span><span class="sxs-lookup"><span data-stu-id="4976b-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="4976b-151">Дополнительные сведения о политиках DNS Windows 2016 см. [Использование политики DNS для управления трафиком на основе географических расположений с основными серверами](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="4976b-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="4976b-152">Ниже приведен пример конфигурации для компании с несколькими сайтами, использующей политику DNS Windows 2016 для управления трафиком на основе географических расположений.</span><span class="sxs-lookup"><span data-stu-id="4976b-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="4976b-153">Имя для службы обхода — "hybridvoice.adatum.biz".</span><span class="sxs-lookup"><span data-stu-id="4976b-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="4976b-154">Сайт в Амстердам содержит четыре устройства Cloud Connector, развернутые с помощью следующих IP-адресов сервера-посредника:</span><span class="sxs-lookup"><span data-stu-id="4976b-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="4976b-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="4976b-155">192.168.1.45</span></span>
    
- <span data-ttu-id="4976b-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="4976b-156">192.168.1.46</span></span>
    
- <span data-ttu-id="4976b-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="4976b-157">192.168.1.47</span></span>
    
- <span data-ttu-id="4976b-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="4976b-158">192.168.1.48</span></span>
    
<span data-ttu-id="4976b-159">На сайте в Сиэтле есть три устройства Cloud Connector, развернутые с помощью следующих IP-адресов сервера-посредника:</span><span class="sxs-lookup"><span data-stu-id="4976b-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="4976b-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="4976b-160">10.10.1.8</span></span>
    
- <span data-ttu-id="4976b-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="4976b-161">10.10.1.9</span></span>
    
- <span data-ttu-id="4976b-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="4976b-162">10.10.1.10</span></span>
    
<span data-ttu-id="4976b-163">При использовании управления трафиком на основе географического расположения DNS-серверы будут настроены следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4976b-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="4976b-164">Создайте подсети DNS-клиентов для подсетей "Амстердам" и "Сиэтл".</span><span class="sxs-lookup"><span data-stu-id="4976b-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="4976b-165">Создайте области зоны DNS для adatum.biz как для Амстердам, так и для Сиэтле.</span><span class="sxs-lookup"><span data-stu-id="4976b-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="4976b-166">Создайте записи DNS для каждой области зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="4976b-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="4976b-167">Амстердаме</span><span class="sxs-lookup"><span data-stu-id="4976b-167">Amsterdam</span></span>
    
   - <span data-ttu-id="4976b-168">Введите A;</span><span class="sxs-lookup"><span data-stu-id="4976b-168">Type A;</span></span>
    
   - <span data-ttu-id="4976b-169">Name: hybridvoice в зоне DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4976b-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="4976b-170">Целевой объект: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="4976b-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="4976b-171">Создание дополнительных записей для дополнительных серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="4976b-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="4976b-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="4976b-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="4976b-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="4976b-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="4976b-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="4976b-174">192.168.1.48</span></span>
    
     <span data-ttu-id="4976b-175">Seattle</span><span class="sxs-lookup"><span data-stu-id="4976b-175">Seattle</span></span>
    
   - <span data-ttu-id="4976b-176">Введите A</span><span class="sxs-lookup"><span data-stu-id="4976b-176">Type A</span></span>
    
   - <span data-ttu-id="4976b-177">Name: hybridvoice в зоне DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4976b-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="4976b-178">Целевой объект: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="4976b-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="4976b-179">Создание дополнительных записей для дополнительных серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="4976b-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="4976b-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="4976b-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="4976b-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="4976b-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="4976b-182">Создайте политику DNS, которая подключает клиентские подсети к соответствующим областям зоны, чтобы обеспечить нужное разрешение DNS.</span><span class="sxs-lookup"><span data-stu-id="4976b-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="4976b-183">На этом шаге клиенты, выполняющие DNS-запросы из подсети Амстердам для hybridvoice.adatum.biz, будут возвращать адреса 192.168.1.45, 192.168.1.46, 192.168.1.47 и 192.168.1.48, а клиенты, выполняющие ту же форму запроса, будут возвращать 10.10.1.8, 10.10.1.9 и 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="4976b-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="4976b-184">Если устройство CCE не получает обновленные параметры, проверьте, может ли устройство связываться с клиентом через удаленную оболочку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4976b-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="4976b-185">Вы можете использовать удаленную оболочку PowerShell для проверки состояния устройства с помощью командлета Get/Кшибридпстнапплианце или PowerShell на узле CCE для проверки состояния с помощью командлета Get — Ккапплианцестатус.</span><span class="sxs-lookup"><span data-stu-id="4976b-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="4976b-186">См. также</span><span class="sxs-lookup"><span data-stu-id="4976b-186">See also</span></span>
<span data-ttu-id="4976b-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="4976b-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="4976b-188">Планирование обхода сервера-посредника в Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="4976b-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
