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
ms.openlocfilehash: ccf140b62cdbad11605c99fe1cb0cc66aa1ee4dd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780108"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="0eced-103">Настройка гибридной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0eced-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="0eced-104">Чтобы настроить гибридную среду Skype для бизнеса, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0eced-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="0eced-105">[Настройте локальную пограничной службу для Федерации с Office 365 или другой организацией](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization).</span><span class="sxs-lookup"><span data-stu-id="0eced-105">[Configure your on-premises Edge service to federate with Office 365 or another organization](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization).</span></span>
- <span data-ttu-id="0eced-106">[Настройте локальную среду для доверия к office 365 и включите общее адресное пространство SIP с помощью Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="0eced-106">[Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span></span>
- <span data-ttu-id="0eced-107">[Включите общее адресное пространство SIP в организации Office 365](#enable-shared-sip-address-space-in-your-office-365-organization).</span><span class="sxs-lookup"><span data-stu-id="0eced-107">[Enable shared SIP address space in your Office 365 organization](#enable-shared-sip-address-space-in-your-office-365-organization).</span></span>

<span data-ttu-id="0eced-108">Обратите внимание на то, что если у вас есть локальная служба Exchange, может потребоваться настроить OAuth между локальной средой Exchange и средой Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="0eced-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="0eced-109">Дополнительные сведения можно найти [в статье Управление проверкой подлинности между серверами в Skype для бизнеса Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) и [Планирование интеграции Skype для бизнеса и Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="0eced-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization"></a><span data-ttu-id="0eced-110">Настройка локальной службы пограничной службы для Федерации с Office 365 или другой организацией</span><span class="sxs-lookup"><span data-stu-id="0eced-110">Configure your on-premises Edge service to federate with Office 365 or another organization</span></span>

<span data-ttu-id="0eced-111">Федерация позволяет пользователям в локальном развертывании общаться с Microsoft 365 или Office 365 для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0eced-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="0eced-112">Чтобы настроить федерацию, выполните следующий командлет в командной консоли Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="0eced-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="0eced-113">Если параметру "-EnablePartnerDiscovery" присвоено значение $True, Skype для бизнеса Server будет использовать DNS-записи для попытки обнаружения доменных доменов, не указанных в списке Алловеддомаинс.</span><span class="sxs-lookup"><span data-stu-id="0eced-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="0eced-114">Если параметру присвоено значение $False, Skype для бизнеса Server будет использовать только Федерацию с доменами, обнаруженными в списке Алловеддомаинс.</span><span class="sxs-lookup"><span data-stu-id="0eced-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="0eced-115">Этот параметр необходим, если используется маршрутизация службы DNS.</span><span class="sxs-lookup"><span data-stu-id="0eced-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="0eced-116">Дополнительные сведения о включении Федерации между пользователями локального развертывания Skype для бизнеса и пользователей в Организации Skype для бизнеса Online приведены [в статье Настройка поддержки федерации для клиента Skype для бизнеса Online в Skype для бизнеса Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span><span class="sxs-lookup"><span data-stu-id="0eced-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="0eced-117">Настройка локальной среды для включения общего адресного пространства SIP с Office 365</span><span class="sxs-lookup"><span data-stu-id="0eced-117">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="0eced-118">Вам также потребуется настроить локальную среду для доверия Office 365 и включить общее адресное пространство SIP с Office 365.</span><span class="sxs-lookup"><span data-stu-id="0eced-118">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="0eced-119">Это означает, что в Office 365 потенциально могут размещаться учетные записи пользователей для того же набора доменов SIP, что и в локальной среде, а сообщения могут маршрутизироваться между пользователями, размещенными в локальной среде и в сети.</span><span class="sxs-lookup"><span data-stu-id="0eced-119">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="0eced-120">Для этого необходимо настроить поставщика услуг хостинга с ProxyFqdn = sipfed. Online. Lync. com, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="0eced-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="0eced-121">Сначала убедитесь, что у вас уже есть поставщик услуг хостинга с ProxyFqdn = sipfed. Online. Lync. com.</span><span class="sxs-lookup"><span data-stu-id="0eced-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="0eced-122">Если он существует, удалите его с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="0eced-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="0eced-123">Затем создайте нового поставщика услуг хостинга, используя командлет New – CsHostingProvider, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="0eced-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-organization"></a><span data-ttu-id="0eced-124">Включение общего адресного пространства SIP в организации Office 365</span><span class="sxs-lookup"><span data-stu-id="0eced-124">Enable shared SIP address space in your Office 365 organization</span></span>
  
<span data-ttu-id="0eced-125">В дополнение к изменениям, внесенным в локальном развертывании, необходимо внести соответствующие изменения в организации Office 365, чтобы она включала общее адресное пространство SIP с локальным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="0eced-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="0eced-126">Чтобы включить общее адресное пространство SIP в организации Office 365, установите удаленный сеанс PowerShell с помощью Skype для бизнеса Online, а затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="0eced-126">To enable shared SIP address space in your Office 365 organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="0eced-127">Атрибут SharedSipAddressSpace должен иметь значение true до тех пор, пока не будет выполнен переход в оперативный режим, и пользователи не будут сохраняться в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="0eced-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="0eced-128">Чтобы установить удаленный сеанс PowerShell с Teams или Skype для бизнеса Online, сначала необходимо установить модуль соединителя Skype для бизнеса Online для Windows PowerShell, который вы можете получить [здесь](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="0eced-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="0eced-129">После установки модуля можно установить удаленный сеанс со следующими командлетами:</span><span class="sxs-lookup"><span data-stu-id="0eced-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="0eced-130">Дополнительные сведения о том, как установить удаленный сеанс PowerShell с помощью Skype для бизнеса Online, а также как использовать модуль соединителя Skype для бизнеса Online можно в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0eced-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="0eced-131">См. также</span><span class="sxs-lookup"><span data-stu-id="0eced-131">See also</span></span>

[<span data-ttu-id="0eced-132">New — CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="0eced-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
