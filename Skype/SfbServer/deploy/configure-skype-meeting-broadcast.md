---
title: Настройка локального развертывания для трансляции собраний Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Сводка: Узнайте, какие действия необходимо выполнить, чтобы настроить трансляцию собраний Skype для локального гибридного развертывания Skype для бизнеса Server.'
ms.openlocfilehash: ac08707a60e0c71719ab2cb85141e89329a947f9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002809"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="8b6a5-103">Configure your on-premises deployment for Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="8b6a5-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="8b6a5-104">**Сводка:** Узнайте, какие действия необходимо выполнить, чтобы настроить трансляцию собраний Skype для локального гибридного развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="8b6a5-105">Трансляция собрания Skype — это веб-служба, которая входит в состав Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="8b6a5-106">Если вы используете локальную версию Skype для бизнеса Server и хотите использовать трансляцию собраний Skype в своей среде, необходимо выполнить действия по настройке, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="8b6a5-107">Прежде чем приступить к работе, необходимо настроить гибридную среду в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="8b6a5-108">Дополнительные сведения см. в разделах [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) и [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8b6a5-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="8b6a5-109">Настройка гибридной среды для трансляции собраний Skype</span><span class="sxs-lookup"><span data-stu-id="8b6a5-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="8b6a5-110">Для подготовки среды для трансляции собраний Skype вам потребуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8b6a5-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="8b6a5-111">Настройка Федерации с помощью ресурсов Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8b6a5-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="8b6a5-112">Настройка федеративных доменов SIP</span><span class="sxs-lookup"><span data-stu-id="8b6a5-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="8b6a5-113">Настройка Федерации с помощью ресурсов Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8b6a5-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="8b6a5-114">Чтобы включить федерацию для ресурсов Skype для бизнеса Online, вам нужно настроить внешний доступ для поставщика федерации SIP.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="8b6a5-115">Чтобы сделать это с помощью панели управления Skype для бизнеса Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="8b6a5-116">Откройте панель управления Skype для бизнеса Server и выберите **внешний доступ** слева.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="8b6a5-117">Выберите **Федеративные поставщики SIP** и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="8b6a5-118">Задайте для нового поставщика следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="8b6a5-119">**Включите связь с этим поставщиком:**</span><span class="sxs-lookup"><span data-stu-id="8b6a5-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="8b6a5-120">выбрано</span><span class="sxs-lookup"><span data-stu-id="8b6a5-120">Selected</span></span>  <br/> |
|<span data-ttu-id="8b6a5-121">**Имя поставщика:**</span><span class="sxs-lookup"><span data-stu-id="8b6a5-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="8b6a5-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="8b6a5-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="8b6a5-123">**Служба пограничного доступа (полное доменное имя):**</span><span class="sxs-lookup"><span data-stu-id="8b6a5-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="8b6a5-124">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8b6a5-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="8b6a5-125">**Уровень проверки по умолчанию:**</span><span class="sxs-lookup"><span data-stu-id="8b6a5-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="8b6a5-126">Разрешить пользователям взаимодействовать со всеми, кто работает с тем же поставщиком.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="8b6a5-127">Вы также можете включить федерацию с ресурсами Skype для бизнеса Online, выполнив следующий командлет в командной консоли управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="8b6a5-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="8b6a5-128">Настройка федеративных доменов SIP</span><span class="sxs-lookup"><span data-stu-id="8b6a5-128">Configure SIP federated domains</span></span>

<span data-ttu-id="8b6a5-129">Затем необходимо добавить федеративные домены SIP в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="8b6a5-130">Повторите эти шаги для каждого из четырех указанных доменов, создав четыре новых федеративных домена SIP.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="8b6a5-131">Эти домены относятся к региональным центрам обработки данных, используемым в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="8b6a5-132">Откройте панель управления Skype для бизнеса Server и выберите **внешний доступ** слева.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="8b6a5-133">Выберите **Федеративные поставщики SIP** и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="8b6a5-134">В поле **Имя домена (или полное доменное имя)** введите домен, повторив этот шаг для каждого из указанных ниже доменов.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="8b6a5-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="8b6a5-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="8b6a5-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="8b6a5-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="8b6a5-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="8b6a5-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="8b6a5-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="8b6a5-138">resources.lync.com</span></span>
    
<span data-ttu-id="8b6a5-139">Вы также можете настроить внешний доступ для федеративных доменов SIP, выполнив следующие командлеты в командной консоли управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="8b6a5-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="8b6a5-140">После выполнения этих шагов настройки вы сможете начать использование трансляции собраний Skype в развертывании.</span><span class="sxs-lookup"><span data-stu-id="8b6a5-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="8b6a5-141">Дополнительные сведения о трансляции собраний Skype можно найти [в статье что такое трансляция собраний Skype](https://go.microsoft.com/fwlink/?LinkId=617071) и [Руководство администратора трансляции собраний Skype](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="8b6a5-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

