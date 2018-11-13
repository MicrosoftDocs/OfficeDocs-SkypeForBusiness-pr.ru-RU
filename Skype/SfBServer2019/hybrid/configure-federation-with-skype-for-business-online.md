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
ms.openlocfilehash: fb04ecd53c93ae7bd64fca760b752d2d69324c3d
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295357"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="0da04-103">Настройка Скайп для гибридных бизнеса</span><span class="sxs-lookup"><span data-stu-id="0da04-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="0da04-104">Чтобы настроить Скайп для гибридных бизнеса, необходимо:</span><span class="sxs-lookup"><span data-stu-id="0da04-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="0da04-105">Настройка федерации</span><span class="sxs-lookup"><span data-stu-id="0da04-105">Configure federation</span></span>](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [<span data-ttu-id="0da04-106">Настройте общее адресное пространство Session Initiation Protocol (SIP)</span><span class="sxs-lookup"><span data-stu-id="0da04-106">Configure a shared Session Initiation Protocol (SIP) address space</span></span>](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [<span data-ttu-id="0da04-107">Настройка проверки подлинности сервер сервер, если необходимо</span><span class="sxs-lookup"><span data-stu-id="0da04-107">Configure server-to-server authentication if required</span></span>](#configure-server-to-server-authentication-if-required)
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="0da04-108">Для настройки локального пограничного сервера для федерации с Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="0da04-108">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="0da04-109">Федерации пользователи в вашем развертывании локальных для взаимодействия с пользователями Office 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0da04-109">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="0da04-110">Для настройки федерации, выполните следующие командлеты в Скайп для консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="0da04-110">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="0da04-111">Настройка вашей Скайп для бизнеса в Интернет для клиентов для общее адресное пространство SIP</span><span class="sxs-lookup"><span data-stu-id="0da04-111">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="0da04-112">Адрес по протоколу SIP – это уникальный идентификатор каждого пользователя в сети, подобный номеру телефона или адресу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0da04-112">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="0da04-113">Прежде чем переместить пользователей из локальной Скайп для бизнеса в Интернет, вам потребуются для настройки клиента Office 365 для совместного использования общих Session Initiation Protocol (SIP) адресное пространство с локальным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="0da04-113">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="0da04-114">Если оно не настроено, может отображаться следующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="0da04-114">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="0da04-115">Move-CsUser: Сбой регистр: Error=(510), описания = (клиент этого пользователя не включен для общего адресного пространства sip).</span><span class="sxs-lookup"><span data-stu-id="0da04-115">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="0da04-116">Чтобы настроить общее адресное пространство SIP, создания удаленного сеанса PowerShell с Скайп для бизнеса в Интернет и затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="0da04-116">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="0da04-117">Атрибут SharedSipAddressSpace должен иметь значение True вплоть до перемещения в сеть, а в локальной системе не должны остаться пользователи.</span><span class="sxs-lookup"><span data-stu-id="0da04-117">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="0da04-118">Для создания удаленного сеанса PowerShell с Скайп для бизнеса в Интернет, необходимо сначала установить Скайп для бизнеса в Интернет модуля соединитель для Windows PowerShell, который вы можете получить [здесь](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="0da04-118">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="0da04-119">После установки модуля можно запустить удаленный сеанс с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="0da04-119">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

<span data-ttu-id="0da04-120">Дополнительные сведения о том, как установить удаленный сеанс PowerShell с Скайп для бизнеса в Интернет и использование Скайп в модуле Business Online Connector в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0da04-120">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="configure-server-to-server-authentication-if-required"></a><span data-ttu-id="0da04-121">Настройка проверки подлинности сервер сервер, если необходимо</span><span class="sxs-lookup"><span data-stu-id="0da04-121">Configure server-to-server authentication if required</span></span>

<span data-ttu-id="0da04-122">В зависимости от типа гибридной среды, которые вы настраиваете может потребоваться настройка проверки подлинности сервер сервер.</span><span class="sxs-lookup"><span data-stu-id="0da04-122">Depending on the type of hybrid environment you are configuring, you may need to configure server-to-server authentication.</span></span>  <span data-ttu-id="0da04-123">Для получения дополнительных сведений см. [Проверка подлинности сервер сервер управление в Скайп для Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span><span class="sxs-lookup"><span data-stu-id="0da04-123">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span></span>


## <a name="see-also"></a><span data-ttu-id="0da04-124">См. также</span><span class="sxs-lookup"><span data-stu-id="0da04-124">See also</span></span>

[<span data-ttu-id="0da04-125">Новый CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="0da04-125">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

