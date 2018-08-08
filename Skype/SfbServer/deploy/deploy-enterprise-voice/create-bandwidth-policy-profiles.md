---
title: Создание профилей пропускной способности политики в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Создание или изменение политики пропускной способности, которые используются с корпоративной голосовой связи контроля допуска звонков в Скайп для Business Server.
ms.openlocfilehash: ddc74ad5327651225bb6f0e78f83d8248c290806
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986445"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="6c669-103">Создание профилей пропускной способности политики в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="6c669-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="6c669-104">Создание или изменение политики пропускной способности, которые используются с корпоративной голосовой связи контроля допуска звонков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c669-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="6c669-105">Политики пропускной способности определяют ограничения пропускной способности сети для режимов передачи звука и видеоизображения в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="6c669-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="6c669-106">Политики пропускной способности, применяемые tobandwidth политики профилей, которые могут применяться к нескольким сетевых узлов для контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="6c669-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="6c669-107">Для указания, какие пропускной способности ограничивает вы должны в вашем развертывании CAC см [плана для контроля допуска звонков в Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="6c669-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="6c669-p102">Примеры политик, созданных в следующей процедуре, задают ограничения для общего трафика аудиоданных, отдельных аудиосеансов, общего трафика видеоданных и отдельных видеосеансов. Например, профиль политики пропускной способности 5Mb_Link задает следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="6c669-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="6c669-110">Аудиоданные: 2 000 кбит/с</span><span class="sxs-lookup"><span data-stu-id="6c669-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="6c669-111">Аудиосеансы: 200 кбит/с</span><span class="sxs-lookup"><span data-stu-id="6c669-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="6c669-112">Видеоданные: 1 400 кбит/с</span><span class="sxs-lookup"><span data-stu-id="6c669-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="6c669-113">Видеосеансы: 700 кбит/с</span><span class="sxs-lookup"><span data-stu-id="6c669-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="6c669-p103">Минимальное значение для аудиосеанса 40 кбит/с. Минимальное значение для видеосеанса 100 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="6c669-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6c669-116">Создание профилей политики пропускной способности с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="6c669-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6c669-117">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="6c669-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6c669-p104">Выполните командлет New-CsNetworkBandwidthPolicyProfile для каждого создаваемого профиля политики пропускной способности. Пример:</span><span class="sxs-lookup"><span data-stu-id="6c669-p104">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet. For example, run:</span></span>
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6c669-120">Создание профилей политики пропускной способности с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="6c669-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6c669-121">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c669-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6c669-122">В левой области навигации щелкните **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="6c669-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6c669-123">Нажмите кнопку навигации **Профиль политики**.</span><span class="sxs-lookup"><span data-stu-id="6c669-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="6c669-124">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="6c669-124">Click **New**.</span></span>
    
5. <span data-ttu-id="6c669-125">На странице **создания профиля политики** в поле щелкните **Имя**, затем введите имя профиля политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="6c669-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="6c669-126">Щелкните **Ограничение для звукового сеанса**, затем введите максимальную скорость в кбит/с, общую для всех сеансов звуковой связи.</span><span class="sxs-lookup"><span data-stu-id="6c669-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="6c669-127">Щелкните **Ограничение для видео**, затем введите максимальную скорость в кбит/с для отдельного сеанса звуковой связи.</span><span class="sxs-lookup"><span data-stu-id="6c669-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="6c669-128">Щелкните **Ограничение для видео**, затем введите максимальную скорость в кбит/с, общую для всех сеансов видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="6c669-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="6c669-129">Щелкните **Ограничение для видеосеанса**, затем введите максимальную скорость в кбит/с для отдельного сеанса видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="6c669-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="6c669-130">Щелкните **Описание** и введите дополнительные сведения о профиле политики пропускной способности (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="6c669-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="6c669-131">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6c669-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="6c669-132">Чтобы завершить создание профилей политики пропускной способности для топологии, повторите шаги с 4 по 11 для остальных профилей политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="6c669-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6c669-133">См. также</span><span class="sxs-lookup"><span data-stu-id="6c669-133">See also</span></span>

[<span data-ttu-id="6c669-134">Новый CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="6c669-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="6c669-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="6c669-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="6c669-136">SET-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="6c669-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="6c669-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="6c669-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)