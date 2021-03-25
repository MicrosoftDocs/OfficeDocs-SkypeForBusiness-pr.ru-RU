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
description: Сводка. Сведения о настройке взаимодействия между локальной развертыванием и Skype для бизнеса Online.
ms.openlocfilehash: e2af514ef1a10d652abae7bdd39a923dc52e1c4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118948"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="196c8-103">Настройка гибридной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="196c8-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="196c8-104">Чтобы настроить гибридную среду Skype для бизнеса, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="196c8-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="196c8-105">[Настройка локальной службы Edge для федерации с помощью Microsoft 365 или Office 365.](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)</span><span class="sxs-lookup"><span data-stu-id="196c8-105">[Configure your on-premises Edge service to federate with Microsoft 365 or Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="196c8-106">Настройте локальное окружение, чтобы доверять [Microsoft 365 или Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)и включить общее пространство адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="196c8-106">[Configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="196c8-107">[Включить общее пространство адресов SIP в организации Microsoft 365 или Office 365.](#enable-shared-sip-address-space-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="196c8-107">[Enable shared SIP address space in your Microsoft 365 or Office 365 organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="196c8-108">Обратите внимание, что если у вас есть локальное приложение Exchange, вам может потребоваться настроить OAuth между локальной средой Exchange и средой Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="196c8-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="196c8-109">Дополнительные сведения см. в рублях Управление проверкой подлинности от сервера к серверу в [Skype для бизнес-сервера](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) и планирование интеграции [Skype для бизнеса и Exchange.](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)</span><span class="sxs-lookup"><span data-stu-id="196c8-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a><span data-ttu-id="196c8-110">Настройка локальной службы Edge для федерации с помощью Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="196c8-110">Configure your on-premises Edge service to federate with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="196c8-111">Федерация позволяет пользователям локального развертывания общаться с пользователями Microsoft 365 или Office 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="196c8-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="196c8-112">Чтобы настроить федерацию, запустите следующий комдлет в оболочке управления skype для бизнес-серверов:</span><span class="sxs-lookup"><span data-stu-id="196c8-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="196c8-113">Если значение "EnablePartnerDiscovery" установлено $True, Skype для бизнеса Server будет использовать записи DNS для обнаружения доменов партнеров, не указанных в списке AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="196c8-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="196c8-114">Если значение задается $False, Skype для бизнеса Server будет только федератом с доменами, найденными в списке AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="196c8-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="196c8-115">Этот параметр необходим, если используется маршрутизация службы DNS.</span><span class="sxs-lookup"><span data-stu-id="196c8-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="196c8-116">Дополнительные сведения о включании федерации между пользователями локального развертывания Skype для бизнеса и пользователями организации Skype для бизнеса в Интернете см. в материале Настройка поддержки федерации для клиента Skype для бизнеса Online в [Skype для](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)бизнеса Server .</span><span class="sxs-lookup"><span data-stu-id="196c8-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a><span data-ttu-id="196c8-117">Настройка локальной среды, чтобы включить общее пространство адресов SIP с Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="196c8-117">Configure your on-premises environment to enable shared SIP address space with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="196c8-118">Кроме того, необходимо настроить локальное окружение, чтобы доверять Microsoft 365 или Office 365 и включить общее пространство адресов SIP.</span><span class="sxs-lookup"><span data-stu-id="196c8-118">You must also configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space.</span></span> <span data-ttu-id="196c8-119">Это означает, что Microsoft 365 или Office 365 потенциально могут принимать учетные записи пользователей для того же набора доменов SIP, что и локальной среды, и сообщения могут отправляться между пользователями, которые будут отправляться в локальной и интерактивной среде.</span><span class="sxs-lookup"><span data-stu-id="196c8-119">This means Microsoft 365 or Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="196c8-120">Это необходимо, настроив поставщика хостинга на proxyFqdn=sipfed.online.lync.com, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="196c8-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="196c8-121">Сначала проверьте, есть ли у вас поставщик хостинга с ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="196c8-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="196c8-122">Если существует, удалите его с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="196c8-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="196c8-123">Затем создайте нового поставщика хостинга, используйте New-CsHostingProvider кодлета следующим образом:</span><span class="sxs-lookup"><span data-stu-id="196c8-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="196c8-124">Включить общее пространство адресов SIP в организации</span><span class="sxs-lookup"><span data-stu-id="196c8-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="196c8-125">Помимо изменений, которые были сделаны в локальном развертывании, необходимо внести соответствующие изменения в организации Microsoft 365 или Office 365 для включения общего пространства адресов SIP с локальной развертыванием.</span><span class="sxs-lookup"><span data-stu-id="196c8-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Microsoft 365 or Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="196c8-126">Чтобы включить общее пространство адресов SIP в организации, создайте удаленный сеанс PowerShell в Skype для бизнеса Online и запустите следующий раздел:</span><span class="sxs-lookup"><span data-stu-id="196c8-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="196c8-127">Атрибут SharedSipAddressSpace должен оставаться "True", пока переход к сети не будет окончательным, и никакие пользователи не останутся на месте.</span><span class="sxs-lookup"><span data-stu-id="196c8-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="196c8-128">Чтобы установить удаленный сеанс PowerShell в Teams или Skype для бизнеса Online, сначала необходимо установить [модуль Teams PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="196c8-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
  
<span data-ttu-id="196c8-129">После установки модуля можно установить удаленный сеанс со следующими командлетами:</span><span class="sxs-lookup"><span data-stu-id="196c8-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="196c8-130">Дополнительные сведения о создании удаленного сеанса PowerShell в Skype для бизнеса Online и использовании модуля соединитель Skype для бизнеса в Интернете см. в Windows PowerShell [.](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="196c8-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="196c8-131">См. также</span><span class="sxs-lookup"><span data-stu-id="196c8-131">See also</span></span>

[<span data-ttu-id="196c8-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="196c8-132">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)