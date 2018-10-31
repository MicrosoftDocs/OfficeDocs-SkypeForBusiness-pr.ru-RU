---
title: Настройка Скайп для гибридных бизнеса
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Сводка: Узнайте, как настроить взаимодействие между локальным развертыванием и Скайп для бизнеса в Интернет.'
ms.openlocfilehash: db03636d412caa72a3b7a38d0c1d691c83d96a5b
ms.sourcegitcommit: a54864c3fcd1b8d240d0f7f2ccf68f8cba566e47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2018
ms.locfileid: "25849350"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="d83c6-103">Настройка Скайп для гибридных бизнеса</span><span class="sxs-lookup"><span data-stu-id="d83c6-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="d83c6-104">Чтобы настроить Скайп для гибридных бизнеса, необходимо:</span><span class="sxs-lookup"><span data-stu-id="d83c6-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="d83c6-105">Настройка в локальной среде в федерацию с Office 365.</span><span class="sxs-lookup"><span data-stu-id="d83c6-105">Configure your on-premises environment to federate with Office 365.</span></span>](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [<span data-ttu-id="d83c6-106">Настройте в локальной среде для управления безопасностью Office 365 и включение общее адресное пространство SIP с помощью Office 365.</span><span class="sxs-lookup"><span data-stu-id="d83c6-106">Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span>](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [<span data-ttu-id="d83c6-107">Включение общее адресное пространство SIP в клиент Office 365.</span><span class="sxs-lookup"><span data-stu-id="d83c6-107">Enable shared SIP address space in your Office 365 tenant.</span></span>](#configure-server-to-server-authentication-if-required)

> [!NOTE]
> <span data-ttu-id="d83c6-108">Если у вас есть локальную систему Exchange, может потребоваться настройка OAuth между локальную систему Exchange и Скайп для бизнеса в Интернет сред.</span><span class="sxs-lookup"><span data-stu-id="d83c6-108">If you have Exchange on-premises, then you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="d83c6-109">Для получения дополнительных сведений см. [Управление проверки подлинности сервер сервер в Скайп для Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) и [Планирование интеграции Скайп для бизнеса и Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="d83c6-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="d83c6-110">Для настройки локального пограничного сервера в федерацию с Office 365</span><span class="sxs-lookup"><span data-stu-id="d83c6-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="d83c6-111">Федерации пользователи в вашем развертывании локальных для взаимодействия с пользователями Office 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d83c6-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="d83c6-112">Для настройки федерации, выполните следующий командлет в Скайп для консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="d83c6-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="d83c6-113">Настройка в локальной среде для включения общее адресное пространство SIP с помощью Office 365</span><span class="sxs-lookup"><span data-stu-id="d83c6-113">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="d83c6-114">Также необходимо настроить среду для локальной для управления безопасностью Office 365 и включение общее адресное пространство SIP с помощью Office 365.</span><span class="sxs-lookup"><span data-stu-id="d83c6-114">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="d83c6-115">Это означает, что Office 365 могут обращаться к учетных записей пользователей для тот же набор доменов SIP, как в локальной среде и сообщения могут быть маршрутизацией между пользователями, размещенного на локальном и online.</span><span class="sxs-lookup"><span data-stu-id="d83c6-115">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="d83c6-116">Это делается путем настройки поставщика услуг размещения с ProxyFqdn=sipfed.online.lync.com, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="d83c6-116">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="d83c6-117">Во-первых проверьте, если у вас уже есть поставщика услуг размещения с ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d83c6-117">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="d83c6-118">Если он существует, затем удалите его с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="d83c6-118">If one exists, then remove it by using the following command:</span></span>

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="d83c6-119">Затем создайте нового поставщика услуг размещения, используйте командлет New-CsHostingProvider следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d83c6-119">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="d83c6-120">Включение общее адресное пространство SIP в клиент Office 365</span><span class="sxs-lookup"><span data-stu-id="d83c6-120">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="d83c6-121">Помимо изменения, внесенные в локальном развертывании вам потребуется внести соответствующие изменения в клиент Office 365 включено общее адресное пространство SIP с помощью локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="d83c6-121">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="d83c6-122">Чтобы включить общее адресное пространство SIP в клиент Office 365, создания удаленного сеанса PowerShell с Скайп для бизнеса в Интернет и затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="d83c6-122">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="d83c6-123">Атрибут SharedSipAddressSpace должен иметь значение True вплоть до перемещения в сеть, а в локальной системе не должны остаться пользователи.</span><span class="sxs-lookup"><span data-stu-id="d83c6-123">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="d83c6-124">Для создания удаленного сеанса PowerShell с группами или Скайп для бизнеса в Интернет, необходимо сначала установить Скайп для бизнеса в Интернет модуля соединитель для Windows PowerShell, который вы можете получить [здесь](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="d83c6-124">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="d83c6-125">После установки модуля можно запустить удаленный сеанс с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="d83c6-125">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="d83c6-126">Дополнительные сведения о том, как установить удаленный сеанс PowerShell с Скайп для бизнеса в Интернет и использование Скайп в модуле Business Online Connector в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d83c6-126">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="d83c6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d83c6-127">See also</span></span>

[<span data-ttu-id="d83c6-128">Новый CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="d83c6-128">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

