---
title: Настройка локального развертывания для трансляции собраний Skype
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Сводка: Сведения о действиях, которые необходимо выполнить для настройки Скайп собрания вещания для вашей локальной Скайп для гибридного развертывания Business Server.'
ms.openlocfilehash: 09b99cab45b8832be34a3219a222324d199c5195
ms.sourcegitcommit: 4967c9b1010a444475dcfbdb6dd3c058494449d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2019
ms.locfileid: "30069471"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="8a295-103">Configure your on-premises deployment for Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="8a295-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="8a295-104">**Сводка:** Узнайте о действиях, которые необходимо выполнить для настройки Скайп собрания вещания для вашей локальной Скайп для гибридного развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="8a295-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="8a295-105">Широковещательные собрания Скайп — это сетевая служба, входящий в состав Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a295-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="8a295-106">Если выполняется Скайп для Business Server локальных и требуется использовать Скайп собрания вещания в вашей среде, то необходимо необходимо выполнить действия по настройке в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="8a295-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="8a295-107">Прежде чем начать, среде необходимо настроить для гибридной среды с Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="8a295-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="8a295-108">Дополнительные сведения см. в разделах [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) и [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8a295-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="8a295-109">Настройте гибридную среду для вещания Скайп собрания</span><span class="sxs-lookup"><span data-stu-id="8a295-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="8a295-110">Вам потребуется выполните следующие действия для подготовки среды к Скайп собрания вещания:</span><span class="sxs-lookup"><span data-stu-id="8a295-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="8a295-111">Настройка федерации с Скайп для бизнеса в Интернет ресурсы</span><span class="sxs-lookup"><span data-stu-id="8a295-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="8a295-112">Настройка федеративных доменов SIP</span><span class="sxs-lookup"><span data-stu-id="8a295-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="8a295-113">Настройка федерации с Скайп для бизнеса в Интернет ресурсы</span><span class="sxs-lookup"><span data-stu-id="8a295-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="8a295-114">Чтобы включить федерацию с Скайп для бизнеса в Интернет ресурсы, необходимо настроить внешний доступ для федеративного поставщика SIP.</span><span class="sxs-lookup"><span data-stu-id="8a295-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="8a295-115">Для этого с помощью Скайп для панели управления Business Server выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8a295-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="8a295-116">Запустите Скайп для панели управления Business Server и слева выберите **Внешний доступ** .</span><span class="sxs-lookup"><span data-stu-id="8a295-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="8a295-117">Выберите **Федеративные поставщики SIP** и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8a295-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="8a295-118">Задайте для нового поставщика следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="8a295-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="8a295-119">**Разрешить взаимодействие с этим поставщиком:**</span><span class="sxs-lookup"><span data-stu-id="8a295-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="8a295-120">выбрано</span><span class="sxs-lookup"><span data-stu-id="8a295-120">Selected</span></span>  <br/> |
|<span data-ttu-id="8a295-121">**Имя поставщика:**</span><span class="sxs-lookup"><span data-stu-id="8a295-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="8a295-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="8a295-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="8a295-123">**Служба пограничного доступа (полное доменное имя):**</span><span class="sxs-lookup"><span data-stu-id="8a295-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="8a295-124">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a295-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="8a295-125">**Уровень проверки по умолчанию:**</span><span class="sxs-lookup"><span data-stu-id="8a295-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="8a295-126">Разрешить пользователям взаимодействовать со всеми, кто работает с тем же поставщиком.</span><span class="sxs-lookup"><span data-stu-id="8a295-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="8a295-127">Можно также включить федерацию с Скайп для бизнеса в Интернет ресурсы, выполнив следующий командлет в Скайп для консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="8a295-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="8a295-128">Настройка федеративных доменов SIP</span><span class="sxs-lookup"><span data-stu-id="8a295-128">Configure SIP federated domains</span></span>

<span data-ttu-id="8a295-129">Затем необходимо добавить в список разрешенных доменов SIP федеративные домены.</span><span class="sxs-lookup"><span data-stu-id="8a295-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="8a295-130">Повторите эти шаги для каждого из четырех указанных доменов, создав четыре новых федеративных домена SIP.</span><span class="sxs-lookup"><span data-stu-id="8a295-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="8a295-131">Включить эти домены для региональных данных центры используется в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="8a295-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="8a295-132">Запустите Скайп для панели управления Business Server и слева выберите **Внешний доступ** .</span><span class="sxs-lookup"><span data-stu-id="8a295-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="8a295-133">Выберите **Федеративные поставщики SIP** и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8a295-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="8a295-134">В поле **Имя домена (или полное доменное имя)** введите домен, повторив этот шаг для каждого из указанных ниже доменов.</span><span class="sxs-lookup"><span data-stu-id="8a295-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="8a295-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a295-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="8a295-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a295-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="8a295-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a295-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="8a295-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a295-138">resources.lync.com</span></span>
    
<span data-ttu-id="8a295-139">Можно также настроить внешнего доступа для федеративных доменов SIP, выполнив следующие командлеты в Скайп для консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="8a295-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="8a295-140">После выполнения этих действий можно начать с помощью Скайп собрания вещания в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="8a295-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="8a295-141">Дополнительные сведения о Скайп вещания собрания можно [возможности собраний Скайп, широковещательного?](https://go.microsoft.com/fwlink/?LinkId=617071) и [Руководстве вещания администратора Скайп собрания](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="8a295-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

