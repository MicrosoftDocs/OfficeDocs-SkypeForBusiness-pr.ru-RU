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
description: Сводка. Сведения о действиях, необходимых для настройки трансляции собраний Skype для локального гибридного развертывания Skype для бизнеса Server.
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820709"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="774cb-103">Настройка локального развертывания для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="774cb-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="774cb-104">**Сводка:** Узнайте о действиях, которые необходимо выполнить для настройки трансляции собраний Skype для локального гибридного развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="774cb-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="774cb-105">Трансляция собраний Skype — это веб-служба, которая входит в состав Office 365.</span><span class="sxs-lookup"><span data-stu-id="774cb-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="774cb-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span><span class="sxs-lookup"><span data-stu-id="774cb-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="774cb-107">Перед началом работы необходимо настроить среду для гибридной среды со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="774cb-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="774cb-108">Дополнительные сведения см. в сведениях о планировании гибридного подключения [между Skype](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) для бизнеса Server и Skype для бизнеса Online и развертывании гибридного подключения между Skype для бизнеса Server и Skype для бизнеса [Online.](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="774cb-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="774cb-109">Настройка гибридной среды для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="774cb-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="774cb-110">Для подготовки среды к трансляции собраний Skype необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="774cb-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="774cb-111">Настройка федерации с ресурсами Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="774cb-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="774cb-112">Настройка федераированных доменов SIP</span><span class="sxs-lookup"><span data-stu-id="774cb-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="774cb-113">Настройка федерации с ресурсами Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="774cb-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="774cb-114">Чтобы включить федерацию с ресурсами Skype для бизнеса Online, необходимо настроить внешний доступ для федератного поставщика SIP.</span><span class="sxs-lookup"><span data-stu-id="774cb-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="774cb-115">Для этого с помощью панели управления Skype для бизнеса Server выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="774cb-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="774cb-116">Запустите панель управления Skype для бизнеса Server и выберите **внешний доступ** слева.</span><span class="sxs-lookup"><span data-stu-id="774cb-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="774cb-117">Выберите **федеражных поставщиков SIP** и нажмите кнопку **"Новый".**</span><span class="sxs-lookup"><span data-stu-id="774cb-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="774cb-118">Настройте нового поставщика с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="774cb-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="774cb-119">**В связи с этим поставщиком:**</span><span class="sxs-lookup"><span data-stu-id="774cb-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="774cb-120">выбрано</span><span class="sxs-lookup"><span data-stu-id="774cb-120">Selected</span></span>  <br/> |
|<span data-ttu-id="774cb-121">**Имя поставщика:**</span><span class="sxs-lookup"><span data-stu-id="774cb-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="774cb-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="774cb-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="774cb-123">**Служба пограничного доступа (полное доменное имя):**</span><span class="sxs-lookup"><span data-stu-id="774cb-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="774cb-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="774cb-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="774cb-125">**Уровень проверки по умолчанию:**</span><span class="sxs-lookup"><span data-stu-id="774cb-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="774cb-126">Разрешить пользователям взаимодействовать со всеми, кто использует этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="774cb-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="774cb-127">Вы также можете включить федерацию с ресурсами Skype для бизнеса Online, задав следующий cmdlet в оболочке управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="774cb-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="774cb-128">Настройка федераированных доменов SIP</span><span class="sxs-lookup"><span data-stu-id="774cb-128">Configure SIP federated domains</span></span>

<span data-ttu-id="774cb-129">Далее необходимо добавить федераированные домены SIP в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="774cb-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="774cb-130">Повторите эти действия для каждого из указанных доменов, создав 4 новых федераированных домена SIP.</span><span class="sxs-lookup"><span data-stu-id="774cb-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="774cb-131">Эти домены относятся к региональным центрам обработки данных, используемым в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="774cb-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="774cb-132">Запустите панель управления Skype для бизнеса Server и выберите **внешний доступ** слева.</span><span class="sxs-lookup"><span data-stu-id="774cb-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="774cb-133">Выберите **федераированные** домены SIP и нажмите кнопку **"Новый".**</span><span class="sxs-lookup"><span data-stu-id="774cb-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="774cb-134">Для имени **домена (или FQDN):** введите домен, повторив эту процедуру для каждого из следующих доменов:</span><span class="sxs-lookup"><span data-stu-id="774cb-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="774cb-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="774cb-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="774cb-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="774cb-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="774cb-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="774cb-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="774cb-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="774cb-138">resources.lync.com</span></span>
    
<span data-ttu-id="774cb-139">Вы также можете настроить внешний доступ для федераированных доменов SIP, задав следующие команды в оболочке управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="774cb-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="774cb-140">После завершения этих действий по настройке можно приступить к использованию трансляции собраний Skype в развертывании.</span><span class="sxs-lookup"><span data-stu-id="774cb-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="774cb-141">Дополнительные сведения о трансляции собраний Skype см. в руководстве администратора по трансляции собраний [Skype.](https://go.microsoft.com/fwlink/?LinkId=617071) [](https://go.microsoft.com/fwlink/?LinkId=617075)</span><span class="sxs-lookup"><span data-stu-id="774cb-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

