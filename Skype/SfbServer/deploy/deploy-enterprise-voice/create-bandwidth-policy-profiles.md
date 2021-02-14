---
title: Создание профилей политики пропускной способности в Skype для бизнеса Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Создание или изменение политик пропускной способности, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server.
ms.openlocfilehash: ac80ebb8b61a763efc0077f267a024a21a359b5d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824850"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="1d412-103">Создание профилей политики пропускной способности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1d412-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="1d412-104">Создание или изменение политик пропускной способности, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1d412-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="1d412-105">Политики пропускной способности задают ограничения пропускной способности сети для режимов передачи аудио и видеоданных в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="1d412-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="1d412-106">Политики пропускной способности применяются к профилям политикbandwidth, которые можно применять к нескольким сетевым сайтам для контроля допуска вызовов.</span><span class="sxs-lookup"><span data-stu-id="1d412-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="1d412-107">Рекомендации по ограничениям пропускной способности, которые необходимо установить в развертывании КОНТРОЛЯ допуска звонков, см. в документе "Планирование контроля допуска звонков [в Skype для бизнеса Server".](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="1d412-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="1d412-p102">Примеры политик, созданных в следующей процедуре, задают ограничения для общего трафика аудиоданных, отдельных аудиосеансов, общего трафика видеоданных и отдельных видеосеансов. Например, профиль политики пропускной способности 5Mb_Link задает следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="1d412-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="1d412-110">Аудиоданные: 2 000 кбит/с</span><span class="sxs-lookup"><span data-stu-id="1d412-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="1d412-111">Аудиосеансы: 200 кбит/с</span><span class="sxs-lookup"><span data-stu-id="1d412-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="1d412-112">Видеоданные: 1 400 кбит/с</span><span class="sxs-lookup"><span data-stu-id="1d412-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="1d412-113">Видеосеансы: 700 кбит/с</span><span class="sxs-lookup"><span data-stu-id="1d412-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="1d412-p103">Минимальное значение для аудиосеанса 40 кбит/с. Минимальное значение для видеосеанса 100 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="1d412-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1d412-116">Создание профилей политик пропускной способности с помощью skype для бизнеса Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1d412-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="1d412-117">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="1d412-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1d412-118">Выполните командлет New-CsNetworkBandwidthPolicyProfile для каждого создаваемого профиля политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="1d412-118">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="1d412-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="1d412-119">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1d412-120">Создание профилей политики пропускной способности с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1d412-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1d412-121">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1d412-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="1d412-122">В левой панели навигации щелкните **Network Configuration** (Параметры сети).</span><span class="sxs-lookup"><span data-stu-id="1d412-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="1d412-123">Нажмите кнопку навигации **Policy Profile** (Профиль политики).</span><span class="sxs-lookup"><span data-stu-id="1d412-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="1d412-124">Щелкните **New** (Создать).</span><span class="sxs-lookup"><span data-stu-id="1d412-124">Click **New**.</span></span>
    
5. <span data-ttu-id="1d412-125">На странице **New Policy Profile** (Создание профиля политики) введите имя профиля политики пропускной способности в поле **Name** (Имя).</span><span class="sxs-lookup"><span data-stu-id="1d412-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="1d412-126">Щелкните **Audio limit** (Ограничение для аудиоданных) и затем введите максимальную скорость (кбит/с) для всех аудиосеансов.</span><span class="sxs-lookup"><span data-stu-id="1d412-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="1d412-127">Щелкните **Audio session limit** (Ограничение для аудиосеанса) и затем введите максимальную скорость (кбит/с) для отдельного аудиосеанса.</span><span class="sxs-lookup"><span data-stu-id="1d412-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="1d412-128">Щелкните **Video limit** (Ограничение для видеоданных) и затем введите максимальную скорость (кбит/с) для всех видеосеансов.</span><span class="sxs-lookup"><span data-stu-id="1d412-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="1d412-129">Щелкните **Video session limit** (Ограничение для видеосеанса) и затем введите максимальную скорость (кбит/с) для отдельного видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="1d412-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="1d412-130">В поле **Description** (Описание) введите дополнительные сведения о профиле политики пропускной способности (необязательно).</span><span class="sxs-lookup"><span data-stu-id="1d412-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="1d412-131">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="1d412-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="1d412-132">Чтобы завершить создание профилей политики пропускной способности для топологии, повторите шаги с 4 по 11 для остальных профилей политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="1d412-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1d412-133">См. также</span><span class="sxs-lookup"><span data-stu-id="1d412-133">See also</span></span>

[<span data-ttu-id="1d412-134">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="1d412-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="1d412-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="1d412-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="1d412-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="1d412-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="1d412-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="1d412-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
