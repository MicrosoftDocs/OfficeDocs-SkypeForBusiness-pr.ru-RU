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
description: Сводка. Узнайте, как настроить взаимодействие между локальным развертыванием и Skype для бизнеса Online.
ms.openlocfilehash: 1b36a25674c3d6690b7490d0cd0793f05131cc12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726789"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="3adc6-103">Настройка гибридной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3adc6-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="3adc6-104">Чтобы настроить гибридную среду Skype для бизнеса, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3adc6-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="3adc6-105">[Настройте службу локальной среды для Федерации с Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="3adc6-105">[Configure your on-premises environment service to federate with Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).</span></span>
- <span data-ttu-id="3adc6-106">[Настройте локальную среду для доверия к office 365 и включите общее адресное пространство SIP с помощью Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="3adc6-106">[Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span></span>
- <span data-ttu-id="3adc6-107">[Включите общее адресное пространство SIP в клиенте Office 365](#enable-shared-sip-address-space-in-your-office-365-tenant).</span><span class="sxs-lookup"><span data-stu-id="3adc6-107">[Enable shared SIP address space in your Office 365 tenant](#enable-shared-sip-address-space-in-your-office-365-tenant).</span></span>

<span data-ttu-id="3adc6-108">Обратите внимание на то, что если у вас есть локальная служба Exchange, может потребоваться настроить OAuth между локальной средой Exchange и средой Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3adc6-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="3adc6-109">Дополнительные сведения можно найти [в статье Управление проверкой подлинности между серверами в Skype для бизнеса Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) и [Планирование интеграции Skype для бизнеса и Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="3adc6-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="3adc6-110">Настройка локальной службы пограничной службы для Федерации с Office 365</span><span class="sxs-lookup"><span data-stu-id="3adc6-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="3adc6-111">Федерация позволяет пользователям в локальном развертывании взаимодействовать с пользователями Office 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3adc6-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="3adc6-112">Чтобы настроить федерацию, выполните следующий командлет в командной консоли Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="3adc6-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

<span data-ttu-id="3adc6-113">Если для параметра "-EnablePartnerDiscovery" задано значение 1, Skype для бизнеса Server будет использовать записи DNS для попытки обнаружения доменных доменов, не указанных в списке Алловеддомаинс.</span><span class="sxs-lookup"><span data-stu-id="3adc6-113">If '-EnablePartnerDiscovery' value set to 1, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="3adc6-114">Если значение равно 0, Skype для бизнеса Server будет использовать только Федерацию с доменами, обнаруженными в списке Алловеддомаинс.</span><span class="sxs-lookup"><span data-stu-id="3adc6-114">If the value set to 0, Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="3adc6-115">Этот параметр необходим, если используется маршрутизация службы DNS.</span><span class="sxs-lookup"><span data-stu-id="3adc6-115">This parameter is required if you use DNS service routing.</span></span>



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="3adc6-116">Настройка локальной среды для включения общего адресного пространства SIP с Office 365</span><span class="sxs-lookup"><span data-stu-id="3adc6-116">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="3adc6-117">Вам также потребуется настроить локальную среду для доверия Office 365 и включить общее адресное пространство SIP с Office 365.</span><span class="sxs-lookup"><span data-stu-id="3adc6-117">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="3adc6-118">Это означает, что в Office 365 потенциально могут размещаться учетные записи пользователей для того же набора доменов SIP, что и в локальной среде, а сообщения могут маршрутизироваться между пользователями, размещенными в локальной среде и в сети.</span><span class="sxs-lookup"><span data-stu-id="3adc6-118">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="3adc6-119">Для этого необходимо настроить поставщика услуг хостинга с ProxyFqdn = sipfed. Online. Lync. com, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="3adc6-119">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="3adc6-120">Сначала убедитесь, что у вас уже есть поставщик услуг хостинга с ProxyFqdn = sipfed. Online. Lync. com.</span><span class="sxs-lookup"><span data-stu-id="3adc6-120">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="3adc6-121">Если он существует, удалите его с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="3adc6-121">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="3adc6-122">Затем создайте нового поставщика услуг хостинга, используя командлет New – CsHostingProvider, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="3adc6-122">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="3adc6-123">Включение общего адресного пространства SIP в клиенте Office 365</span><span class="sxs-lookup"><span data-stu-id="3adc6-123">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="3adc6-124">В дополнение к изменениям, внесенным в локальном развертывании, необходимо внести соответствующие изменения в клиенте Office 365, чтобы включить общее адресное пространство SIP с локальным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="3adc6-124">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="3adc6-125">Чтобы включить общее адресное пространство SIP в клиенте Office 365, установите удаленный сеанс PowerShell с помощью Skype для бизнеса Online, а затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="3adc6-125">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="3adc6-126">Атрибут SharedSipAddressSpace должен иметь значение true до тех пор, пока не будет выполнен переход в оперативный режим, и пользователи не будут сохраняться в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="3adc6-126">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="3adc6-127">Чтобы установить удаленный сеанс PowerShell с Teams или Skype для бизнеса Online, сначала необходимо установить модуль соединителя Skype для бизнеса Online для Windows PowerShell, который вы можете получить [здесь](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="3adc6-127">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="3adc6-128">После установки модуля можно установить удаленный сеанс со следующими командлетами:</span><span class="sxs-lookup"><span data-stu-id="3adc6-128">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="3adc6-129">Дополнительные сведения о том, как установить удаленный сеанс PowerShell с помощью Skype для бизнеса Online, а также как использовать модуль соединителя Skype для бизнеса Online можно в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="3adc6-129">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="3adc6-130">См. также</span><span class="sxs-lookup"><span data-stu-id="3adc6-130">See also</span></span>

[<span data-ttu-id="3adc6-131">New — CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="3adc6-131">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

