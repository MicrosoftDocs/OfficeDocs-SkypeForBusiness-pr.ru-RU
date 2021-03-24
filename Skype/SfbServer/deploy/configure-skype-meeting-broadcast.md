---
title: Настройка локального развертывания для трансляции собраний Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: Сводка. Сведения о действиях, которые необходимо выполнить для настройки трансляции собраний Skype для локального гибридного развертывания Skype для бизнес-сервера.
ms.openlocfilehash: b70272ee90146bdac87264acf0c7673b8def05c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103695"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="32fd9-103">Настройка локального развертывания для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="32fd9-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="32fd9-104">**Сводка:** Узнайте о действиях, которые необходимо выполнить для настройки трансляции собраний Skype для локального гибридного развертывания Skype для бизнес-сервера.</span><span class="sxs-lookup"><span data-stu-id="32fd9-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="32fd9-105">Skype Meeting Broadcast — это онлайн-служба, которая является частью Office 365.</span><span class="sxs-lookup"><span data-stu-id="32fd9-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="32fd9-106">Если вы работаете на локальном сервере Skype для бизнеса и хотите использовать трансляцию собраний Skype в вашей среде, необходимо следовать шагам по настройке в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="32fd9-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="32fd9-107">Перед началом работы необходимо настроить среду для гибридного приложения Skype для бизнеса в Интернете.</span><span class="sxs-lookup"><span data-stu-id="32fd9-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="32fd9-108">Дополнительные сведения см. в сайте Plan [hybrid connectivity between Skype for Business Server и Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) и Deploy hybrid [connectivity between Skype for Business Server and Skype for Business Online.](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="32fd9-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="32fd9-109">Настройка гибридной среды для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="32fd9-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="32fd9-110">Чтобы подготовить среду для трансляции собраний Skype, необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="32fd9-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="32fd9-111">Настройка федерации с помощью ресурсов Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="32fd9-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="32fd9-112">Настройка федераированных доменов SIP</span><span class="sxs-lookup"><span data-stu-id="32fd9-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="32fd9-113">Настройка федерации с помощью ресурсов Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="32fd9-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="32fd9-114">Чтобы включить федерацию с помощью ресурсов Skype для бизнеса Online, необходимо настроить внешний доступ для поставщика SIP Federated.</span><span class="sxs-lookup"><span data-stu-id="32fd9-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="32fd9-115">Для этого с помощью панели управления Skype для бизнес-серверов выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="32fd9-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="32fd9-116">Запустите панель управления Skype для бизнес-серверов и выберите **внешний** доступ слева.</span><span class="sxs-lookup"><span data-stu-id="32fd9-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="32fd9-117">Выберите **поставщиков SIP Federated и** нажмите **кнопку New**.</span><span class="sxs-lookup"><span data-stu-id="32fd9-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="32fd9-118">Настройка нового поставщика с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="32fd9-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="32fd9-119">**Включить связь с этим поставщиком:**</span><span class="sxs-lookup"><span data-stu-id="32fd9-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="32fd9-120">выбрано</span><span class="sxs-lookup"><span data-stu-id="32fd9-120">Selected</span></span>  <br/> |
|<span data-ttu-id="32fd9-121">**Имя поставщика:**</span><span class="sxs-lookup"><span data-stu-id="32fd9-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="32fd9-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="32fd9-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="32fd9-123">**Служба пограничного доступа (полное доменное имя):**</span><span class="sxs-lookup"><span data-stu-id="32fd9-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="32fd9-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="32fd9-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="32fd9-125">**Уровень проверки по умолчанию:**</span><span class="sxs-lookup"><span data-stu-id="32fd9-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="32fd9-126">Разрешить пользователям общаться со всеми пользователями с помощью этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="32fd9-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="32fd9-127">Вы также можете включить федерацию с помощью ресурсов Skype для бизнеса Online, заняв следующие команды в оболочке управления серверами Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="32fd9-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="32fd9-128">Настройка федераированных доменов SIP</span><span class="sxs-lookup"><span data-stu-id="32fd9-128">Configure SIP federated domains</span></span>

<span data-ttu-id="32fd9-129">Далее необходимо добавить федераированные домены SIP в разрешенный список доменов.</span><span class="sxs-lookup"><span data-stu-id="32fd9-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="32fd9-130">Повторите эти действия для каждого из перечисленных доменов, создав 4 новых федераированных домена SIP.</span><span class="sxs-lookup"><span data-stu-id="32fd9-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="32fd9-131">Эти домены относятся к региональным центрам обработки данных, используемым в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="32fd9-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="32fd9-132">Запустите панель управления Skype для бизнес-серверов и выберите **внешний** доступ слева.</span><span class="sxs-lookup"><span data-stu-id="32fd9-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="32fd9-133">Выберите **SIP федераированные домены** и нажмите **кнопку New**.</span><span class="sxs-lookup"><span data-stu-id="32fd9-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="32fd9-134">Для имени **домена (или FQDN):** введите домен, повторив эту процедуру для каждого из следующих доменов:</span><span class="sxs-lookup"><span data-stu-id="32fd9-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="32fd9-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="32fd9-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="32fd9-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="32fd9-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="32fd9-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="32fd9-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="32fd9-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="32fd9-138">resources.lync.com</span></span>
    
<span data-ttu-id="32fd9-139">Вы также можете настроить внешний доступ для федераированных доменов SIP, заняв следующие команды в оболочке управления Skype для бизнес-серверов:</span><span class="sxs-lookup"><span data-stu-id="32fd9-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="32fd9-140">После завершения этих действий по настройке можно приступить к использованию Skype Meeting Broadcast в развертывании.</span><span class="sxs-lookup"><span data-stu-id="32fd9-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="32fd9-141">Дополнительные сведения о трансляции собраний Skype см. [](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)в руководстве по администрированию собраний [Skype.](https://go.microsoft.com/fwlink/?LinkId=617071)</span><span class="sxs-lookup"><span data-stu-id="32fd9-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md).</span></span>
