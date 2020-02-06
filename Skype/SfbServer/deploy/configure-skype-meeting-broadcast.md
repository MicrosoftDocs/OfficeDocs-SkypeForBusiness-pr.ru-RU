---
title: Настройка локального развертывания для трансляции собраний Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Сводка: Узнайте, какие действия необходимо выполнить, чтобы настроить трансляцию собраний Skype для локального гибридного развертывания Skype для бизнеса Server.'
ms.openlocfilehash: 8bdbb163f5ef867711ce109bc923ba0ec8401ffa
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790947"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="d352f-103">Configure your on-premises deployment for Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="d352f-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="d352f-104">**Сводка:** Узнайте, какие действия необходимо выполнить, чтобы настроить трансляцию собраний Skype для локального гибридного развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d352f-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="d352f-105">Трансляция собрания Skype — это веб-служба, которая входит в состав Office 365.</span><span class="sxs-lookup"><span data-stu-id="d352f-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="d352f-106">Если вы используете локальную версию Skype для бизнеса Server и хотите использовать трансляцию собраний Skype в своей среде, необходимо выполнить действия по настройке, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d352f-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="d352f-107">Прежде чем приступить к работе, необходимо настроить гибридную среду в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d352f-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="d352f-108">Дополнительные сведения см. в разделах [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) и [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="d352f-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="d352f-109">Настройка гибридной среды для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="d352f-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="d352f-110">Для подготовки среды для трансляции собраний Skype вам потребуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d352f-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="d352f-111">Настройка Федерации с помощью ресурсов Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d352f-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="d352f-112">Настройка федеративных доменов SIP</span><span class="sxs-lookup"><span data-stu-id="d352f-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="d352f-113">Настройка Федерации с помощью ресурсов Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d352f-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="d352f-114">Чтобы включить федерацию для ресурсов Skype для бизнеса Online, вам нужно настроить внешний доступ для поставщика федерации SIP.</span><span class="sxs-lookup"><span data-stu-id="d352f-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="d352f-115">Чтобы сделать это с помощью панели управления Skype для бизнеса Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d352f-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="d352f-116">Откройте панель управления Skype для бизнеса Server и выберите **внешний доступ** слева.</span><span class="sxs-lookup"><span data-stu-id="d352f-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="d352f-117">Выберите **Федеративные поставщики SIP** и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d352f-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="d352f-118">Задайте для нового поставщика следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="d352f-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="d352f-119">**Включите связь с этим поставщиком:**</span><span class="sxs-lookup"><span data-stu-id="d352f-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="d352f-120">выбрано</span><span class="sxs-lookup"><span data-stu-id="d352f-120">Selected</span></span>  <br/> |
|<span data-ttu-id="d352f-121">**Имя поставщика:**</span><span class="sxs-lookup"><span data-stu-id="d352f-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="d352f-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="d352f-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="d352f-123">**Служба пограничного доступа (полное доменное имя):**</span><span class="sxs-lookup"><span data-stu-id="d352f-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="d352f-124">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d352f-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="d352f-125">**Уровень проверки по умолчанию:**</span><span class="sxs-lookup"><span data-stu-id="d352f-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="d352f-126">Разрешить пользователям взаимодействовать со всеми, кто работает с тем же поставщиком.</span><span class="sxs-lookup"><span data-stu-id="d352f-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="d352f-127">Вы также можете включить федерацию с ресурсами Skype для бизнеса Online, выполнив следующий командлет в командной консоли управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="d352f-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="d352f-128">Настройка федеративных доменов SIP</span><span class="sxs-lookup"><span data-stu-id="d352f-128">Configure SIP federated domains</span></span>

<span data-ttu-id="d352f-129">Затем необходимо добавить федеративные домены SIP в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="d352f-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="d352f-130">Повторите эти шаги для каждого из четырех указанных доменов, создав четыре новых федеративных домена SIP.</span><span class="sxs-lookup"><span data-stu-id="d352f-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="d352f-131">Эти домены относятся к региональным центрам обработки данных, используемым в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d352f-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="d352f-132">Откройте панель управления Skype для бизнеса Server и выберите **внешний доступ** слева.</span><span class="sxs-lookup"><span data-stu-id="d352f-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="d352f-133">Выберите **Федеративные поставщики SIP** и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d352f-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="d352f-134">В поле **Имя домена (или полное доменное имя)** введите домен, повторив этот шаг для каждого из указанных ниже доменов.</span><span class="sxs-lookup"><span data-stu-id="d352f-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="d352f-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d352f-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="d352f-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d352f-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="d352f-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="d352f-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="d352f-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="d352f-138">resources.lync.com</span></span>
    
<span data-ttu-id="d352f-139">Вы также можете настроить внешний доступ для федеративных доменов SIP, выполнив следующие командлеты в командной консоли управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="d352f-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="d352f-140">После выполнения этих шагов настройки вы сможете начать использование трансляции собраний Skype в развертывании.</span><span class="sxs-lookup"><span data-stu-id="d352f-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="d352f-141">Дополнительные сведения о трансляции собраний Skype можно найти [в статье что такое трансляция собраний Skype](https://go.microsoft.com/fwlink/?LinkId=617071) и [Руководство администратора трансляции собраний Skype](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="d352f-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

