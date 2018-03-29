---
title: Настройка федерации в Skype для бизнеса Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Сводка: Узнайте, как настроить взаимодействие между локальным развертыванием и Скайп для бизнеса в Интернет.'
ms.openlocfilehash: 1a08fdb9ad9522e50bc412adcc9214fff3bbb924
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-federation-with-skype-for-business-online"></a><span data-ttu-id="81349-103">Настройка федерации в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="81349-103">Configure federation with Skype for Business Online</span></span>
 
<span data-ttu-id="81349-104">**Сводка:** Узнайте, как настроить взаимодействие между локальным развертыванием и Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="81349-104">**Summary:** Learn how to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
<span data-ttu-id="81349-105">Следуйте инструкциям в данном разделе по настройке взаимодействия между локальным развертыванием и Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="81349-105">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="81349-106">Для настройки локального пограничного сервера для федерации с Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="81349-106">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="81349-107">Федерации пользователи в вашем развертывании локальных для взаимодействия с пользователями Office 365 в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="81349-107">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="81349-108">Для настройки федерации, выполните следующие командлеты в Скайп для консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="81349-108">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="81349-109">Настройка вашей Скайп для бизнеса в Интернет для клиентов для общее адресное пространство SIP</span><span class="sxs-lookup"><span data-stu-id="81349-109">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="81349-110">Адрес по протоколу SIP – это уникальный идентификатор каждого пользователя в сети, подобный номеру телефона или адресу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="81349-110">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="81349-111">Прежде чем переместить пользователей из локальной Скайп для бизнеса в Интернет, вам потребуются для настройки клиента Office 365 для совместного использования общих Session Initiation Protocol (SIP) адресное пространство с локальным развертыванием.</span><span class="sxs-lookup"><span data-stu-id="81349-111">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="81349-112">Если оно не настроено, может отображаться следующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="81349-112">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="81349-113">Move-CsUser: Сбой регистр: Error=(510), описания = (клиент этого пользователя не включен для общего адресного пространства sip).</span><span class="sxs-lookup"><span data-stu-id="81349-113">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="81349-114">Чтобы настроить общее адресное пространство SIP, создания удаленного сеанса PowerShell с Скайп для бизнеса в Интернет и затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="81349-114">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="81349-115">Атрибут SharedSipAddressSpace должен иметь значение True вплоть до перемещения в сеть, а в локальной системе не должны остаться пользователи.</span><span class="sxs-lookup"><span data-stu-id="81349-115">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="81349-116">Для создания удаленного сеанса PowerShell с Скайп для бизнеса в Интернет, необходимо сначала установить Скайп для бизнеса в Интернет модуля соединитель для Windows PowerShell, который вы можете получить здесь: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="81349-116">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="81349-117">После установки модуля можно запустить удаленный сеанс с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="81349-117">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
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

<span data-ttu-id="81349-118">Дополнительные сведения о том, как установить удаленный сеанс PowerShell с Скайп для бизнеса в Интернет можно [подключение к Lync Online с помощью Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span><span class="sxs-lookup"><span data-stu-id="81349-118">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Lync Online By Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span></span>
  
<span data-ttu-id="81349-119">Дополнительные сведения об использовании Скайп для бизнеса в Интернет модуль PowerShell соединитель можно [С помощью Windows PowerShell для управления Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span><span class="sxs-lookup"><span data-stu-id="81349-119">For more information about using the Skype for Business Online connector PowerShell module, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="81349-120">См. также</span><span class="sxs-lookup"><span data-stu-id="81349-120">See also</span></span>

#### 

[<span data-ttu-id="81349-121">Новый CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="81349-121">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

