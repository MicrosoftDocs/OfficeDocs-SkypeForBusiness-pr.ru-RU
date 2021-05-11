---
title: Настройка гибридной среды Skype для бизнеса
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Сводка. Сведения о настройке взаимодействия между локальной развертыванием и Teams.
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305973"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="62ead-103">Настройка гибридной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="62ead-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="62ead-104">Чтобы настроить гибридную среду Skype для бизнеса, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="62ead-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="62ead-105">[Настройка локальной службы Edge для федерации с помощью Teams.](#configure-your-on-premises-edge-service-to-federate-with-teams)</span><span class="sxs-lookup"><span data-stu-id="62ead-105">[Configure your on-premises Edge service to federate with Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).</span></span>
- <span data-ttu-id="62ead-106">[Настройте локальное окружение,](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)чтобы доверять Teams и включить общее пространство адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="62ead-106">[Configure your on-premises environment to trust Teams and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams).</span></span>
- <span data-ttu-id="62ead-107">[Включить общее пространство адресов SIP](#enable-shared-sip-address-space-in-your-organization)в Teams организации.</span><span class="sxs-lookup"><span data-stu-id="62ead-107">[Enable shared SIP address space in your Teams organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="62ead-108">Если у вас Exchange локальной среды, может потребоваться настроить OAuth между локальной Exchange и Skype для бизнеса среде Online.</span><span class="sxs-lookup"><span data-stu-id="62ead-108">If you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="62ead-109">Дополнительные сведения см. в [веб-сведениях Управление](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) проверкой подлинности от сервера к серверу в Skype для бизнеса Server и планирование интеграции Skype для бизнеса [и Exchange.](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)</span><span class="sxs-lookup"><span data-stu-id="62ead-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a><span data-ttu-id="62ead-110">Настройка локальной службы Edge для федерации с помощью Teams</span><span class="sxs-lookup"><span data-stu-id="62ead-110">Configure your on-premises Edge service to federate with Teams</span></span>

<span data-ttu-id="62ead-111">Федерация позволяет пользователям локального развертывания общаться с Teams и Skype для бизнеса пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="62ead-111">Federation allows users in your on-premises deployment to communicate with Teams and Skype for Business Online  users in your organization.</span></span> <span data-ttu-id="62ead-112">Чтобы настроить федерацию, запустите следующий cmdlet в Skype для бизнеса Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="62ead-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="62ead-113">Если значение '-EnablePartnerDiscovery' установлено $True, Skype для бизнеса Server записи DNS будут использовать для обнаружения доменов партнеров, не указанных в списке AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="62ead-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="62ead-114">Если значение задается для $False, Skype для бизнеса Server только федерация с доменами, найденными в списке AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="62ead-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="62ead-115">Этот параметр необходим, если используется маршрутизация службы DNS.</span><span class="sxs-lookup"><span data-stu-id="62ead-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="62ead-116">Дополнительные сведения о включании федерации между пользователями локального развертывания Skype для бизнеса и пользователями организации Microsoft 365 см. в материале [Configuring federation support for a Microsoft 365 клиента в Skype для бизнеса Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span><span class="sxs-lookup"><span data-stu-id="62ead-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Microsoft 365 organization, see [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a><span data-ttu-id="62ead-117">Настройка локальной среды, чтобы включить общее пространство адресов SIP с Teams</span><span class="sxs-lookup"><span data-stu-id="62ead-117">Configure your on-premises environment to enable shared SIP address space with Teams</span></span>

<span data-ttu-id="62ead-118">Кроме того, необходимо настроить локальное окружение, чтобы доверять Teams и включить общее пространство адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="62ead-118">You must also configure your on-premises environment to trust Teams and enable shared SIP address space.</span></span> <span data-ttu-id="62ead-119">Эта конфигурация Teams потенциально может принимать учетные записи пользователей для того же набора доменов SIP, что и локальной среды, а сообщения можно отправлять между пользователями, установленными в помещениях и в Интернете.</span><span class="sxs-lookup"><span data-stu-id="62ead-119">This configuration means Teams can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span> <span data-ttu-id="62ead-120">Настройка поставщика хостинга с помощью ProxyFqdn=sipfed.online.lync.com, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="62ead-120">You configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="62ead-121">Сначала проверьте, есть ли у вас поставщик хостинга с ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="62ead-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="62ead-122">Если существует, удалите его с помощью следующей команды в командной Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="62ead-122">If one exists, then remove it by using the following command in the Skype for Business Server Management Shell:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="62ead-123">Затем создайте нового поставщика хостинга с помощью New-CsHostingProvider следующим образом:</span><span class="sxs-lookup"><span data-stu-id="62ead-123">Then create a new hosting provider by using the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="62ead-124">Включить общее пространство адресов SIP в организации</span><span class="sxs-lookup"><span data-stu-id="62ead-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="62ead-125">Помимо изменений, которые были сделаны в локальном развертывании, необходимо внести соответствующие изменения в организацию Teams, чтобы включить общее адресное пространство SIP с локальной развертыванием.</span><span class="sxs-lookup"><span data-stu-id="62ead-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Teams organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="62ead-126">Чтобы включить общее пространство адресов SIP в организации, создайте удаленный сеанс PowerShell с Teams, а затем запустите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="62ead-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Teams, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="62ead-127">Атрибут SharedSipAddressSpace должен оставаться "True", пока переход к сети не будет окончательным, и никакие пользователи не останутся на месте.</span><span class="sxs-lookup"><span data-stu-id="62ead-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="62ead-128">Чтобы установить удаленный сеанс PowerShell с Teams (или Skype для бизнеса Online), сначала необходимо установить модуль Teams [PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="62ead-128">To establish a remote PowerShell session with Teams (or Skype for Business Online), you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span> <span data-ttu-id="62ead-129">Модуль Teams PowerShell заменяет Skype соединитель Busines Online, который был снят.</span><span class="sxs-lookup"><span data-stu-id="62ead-129">The Teams PowerShell module replaces the Skype for Busines Online Connector module, which has been retired.</span></span>
  
<span data-ttu-id="62ead-130">После установки модуля можно установить удаленный сеанс со следующими командлетами:</span><span class="sxs-lookup"><span data-stu-id="62ead-130">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="62ead-131">Дополнительные сведения о создании удаленного сеанса PowerShell с Teams и использовании модуля Teams PowerShell см. в этой ссылке Настройка компьютера для Windows PowerShell [.](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="62ead-131">For more information about how to establish a remote PowerShell session with Teams, and how to use the Teams PowerShell module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="62ead-132">См. также</span><span class="sxs-lookup"><span data-stu-id="62ead-132">See also</span></span>

[<span data-ttu-id="62ead-133">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="62ead-133">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
