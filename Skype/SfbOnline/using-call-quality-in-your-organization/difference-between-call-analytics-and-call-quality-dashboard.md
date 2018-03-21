---
title: "В чем разница между средством аналитики звонков и панелью мониторинга качества звонков?"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Learn about Call Analytics and Call Quality Dashboard and when to use them to monitor and troubleshoot call-quality problems in Skype for Business.
ms.openlocfilehash: 6c8eb372388ae42863292dbf00a70c5ddd19118d
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2018
---
# <a name="whats-the-difference-between-call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="4f6a2-103">В чем разница между средством аналитики звонков и панелью мониторинга качества звонков?</span><span class="sxs-lookup"><span data-stu-id="4f6a2-103">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>

<span data-ttu-id="4f6a2-p101">[] В Skype для бизнеса проблемы с качеством звонков можно отслеживать и устранять двумя способами (с помощью средства аналитики звонков и панели мониторинга качества звонков), которые описываются в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4f6a2-p101">Skype for Business gives you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard. This article describes both and tells you when to use each one.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f6a2-p102">На данный момент доступна лишь предварительная версия средства аналитики звонков. Описание и изображения в этой статье могут не соответствовать фактическому интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="4f6a2-p102">Call Analytics is currently in preview. Text and images described here may not match your experience.</span></span> 
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="4f6a2-108">Что представляет собой средство аналитики звонков и для чего оно предназначено?</span><span class="sxs-lookup"><span data-stu-id="4f6a2-108">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="4f6a2-p103">В средстве аналитики звонков представлены подробные сведения об устройствах, сетях и соединениях, связанных с конкретными звонками, для каждого пользователя в учетной записи Skype для бизнеса. Администраторы Skype для бизнеса могут использовать это средство для устранения неполадок с качеством звонков в Skype для бизнеса и проблем с соединением.</span><span class="sxs-lookup"><span data-stu-id="4f6a2-p103">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Skype for Business account. If you're a Skype for Business admin, you can use Call Analytics to troubleshoot Skype for Business call quality and connection problems.</span></span>
  
<span data-ttu-id="4f6a2-111">Если вы хотите предоставить доступ к средству аналитики звонков пользователям без прав администратора (например, агентам службы технической поддержки стороннего поставщика), следует назначить им разрешения на доступ к этому средству, запретив при этом доступ к остальным компонентам Центра администрирования Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="4f6a2-111">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics but they can't access the rest of the Skype for Business Admin center:</span></span> 
  
- <span data-ttu-id="4f6a2-p104">**Агенты службы технической поддержки с разрешениями уровня 1**. Могут просматривать ограниченный набор личных сведений в средстве аналитики звонков. Могут устранять неполадки со звонками, но проблемы с собраниями переадресуют агентам уровня 2.</span><span class="sxs-lookup"><span data-stu-id="4f6a2-p104">**Helpdesk agents with Tier 1 permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics. They can troubleshoot calls, but they will hand off problems with meetings to a Tier 2 agent.</span></span>
    
- <span data-ttu-id="4f6a2-p105">**Агенты службы технической поддержки с разрешениями уровня 1**. Могут просматривать все доступные в средстве аналитики звонков данные, а также устранять неполадки со звонками и собраниями. Имеют полный доступ к журналам звонков и сведениям о клиенте.</span><span class="sxs-lookup"><span data-stu-id="4f6a2-p105">**Helpdesk agents with Tier 2 permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings. They have full access to call logs and customer information.</span></span>
    
<span data-ttu-id="4f6a2-116">Для получения дополнительных сведений о настройке вызова Analytics см [Скайп для вызова бизнес-аналитики](set-up-call-analytics.md).</span><span class="sxs-lookup"><span data-stu-id="4f6a2-116">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="4f6a2-117">Дополнительные сведения о работе агенты служба технической поддержки с помощью вызова анализа [Использования вызова аналитики для устранения неполадок вызовов плохого качества](use-call-analytics-to-troubleshoot-poor-call-quality.md)см.</span><span class="sxs-lookup"><span data-stu-id="4f6a2-117">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="4f6a2-118">Что представляет собой панель мониторинга качества звонков и для чего она предназначена?</span><span class="sxs-lookup"><span data-stu-id="4f6a2-118">What's the Call Quality Dashboard, and when should I use it?</span></span>

<span data-ttu-id="4f6a2-p107">В средстве аналитики звонков приводится детализированная информация о качестве звонков пользователей. Например, если пользователь пожаловался на плохое качество звонка, администратор Skype для бизнеса или подготовленный агент службы технической поддержки может с его помощью проанализировать состояние устройства, сети, соединения и другие факторы, связанные с этим звонком.</span><span class="sxs-lookup"><span data-stu-id="4f6a2-p107">Call Analytics gives you detailed, specific information about the call quality experienced by users. Why did user Tony Smith have a poor call this afternoon? Using Call Analytics, a Skype for Business admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to Tony's call.</span></span>
  
<span data-ttu-id="4f6a2-p108">В отличие от этого средства, с помощью панели мониторинга качества звонков администраторы Skype для бизнеса и сетевые инженеры могут оптимизировать характеристики сети на основе сведений на уровне всей организации Skype для бизнеса, а не отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4f6a2-p108">Where CA is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Skype for Business admins and network engineers optimize a network. CQD shifts focus from specific users and instead looks at aggregate information for an entire Skype for Business organization.</span></span> 
  
<span data-ttu-id="4f6a2-p109">В приведенном выше примере плохое качество звонка может быть связано с проблемами в сети, которые могут затрагивать множество других пользователей. В панели мониторинга качества звонков нельзя просмотреть сведения об отдельном звонке  в ней обобщается информация обо всех звонках, выполненных с помощью Skype для бизнеса. Это позволяет проанализировать общие тенденции и проблемы, благодаря чему сетевые инженеры могут получить взвешенную оценку качества звонков. В этой панели мониторинга представлены отчеты по показателям, определяющим общее качество звонков, потоки сервер-клиент и клиент-клиент, а также [соглашения о качестве голосовой связи](https://go.microsoft.com/fwlink/p/?linkid=846252).</span><span class="sxs-lookup"><span data-stu-id="4f6a2-p109">Maybe Tony's poor call quality is due to a network issue that's also affecting many other users. Tony's individual call experience isn't visible in CQD, but the overall quality of calls made using Skype for Business is captured. With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality. CQD provides reports of call quality metrics that give you insights into overall call quality, server-client and client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
<span data-ttu-id="4f6a2-130">Дополнительные сведения см. в разделе [Функции панели мониторинга качества вызовов для Skype для бизнеса Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span><span class="sxs-lookup"><span data-stu-id="4f6a2-130">For more details, see [Features of the Call Quality Dashboard for Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="4f6a2-p111">Средство аналитики звонков и панель мониторинга качества звонков выполняются параллельно и могут использоваться независимо друг от друга. Допустим, агент уровня 1 решает, что для устранения проблемы со звонком требуется дополнительная помощь. В этом случае звонок передается агенту уровня 2, который имеет доступ к более широкому набору сведений в средстве аналитики звонков. Агент уровня 2, в свою очередь, может оповестить о проблеме сетевого инженера. С помощью панели мониторинга качества звонков сетевой инженер может выявить и проанализировать общие проблемы, влияющие на качество звонков.</span><span class="sxs-lookup"><span data-stu-id="4f6a2-p111">Call Analytics and CQD run in parallel and can be used independently or together. For example, say a Tier 1 agent determines that they need more help troubleshooting a call problem. The Tier 1 agent passes the call to a Tier 2 agent, who has access to more information in Call Analytics than the Tier 1 agent. In turn, the Tier 2 agent can alert a network engineer to an issue. The network engineer may check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>
  
<span data-ttu-id="4f6a2-136">Дополнительные сведения о CQD можно [Включить и с помощью вызова панели мониторинга качества для групп Майкрософт и Скайп для бизнеса в Интернет](turning-on-and-using-call-quality-dashboard.md) и [измерения и меры, доступные в вызов качества панели мониторинга для групп Майкрософт и Скайп для бизнеса в Интернет](dimensions-and-measures-available-in-call-quality-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="4f6a2-136">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4f6a2-137">See also</span><span class="sxs-lookup"><span data-stu-id="4f6a2-137">Related topics</span></span>
[<span data-ttu-id="4f6a2-138">Настройка средства аналитики звонков в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4f6a2-138">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="4f6a2-139">Использование средства аналитики звонков для устранения проблем с низким качеством звонков в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4f6a2-139">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

## <a name="feedback"></a><span data-ttu-id="4f6a2-140">Отзыв?</span><span class="sxs-lookup"><span data-stu-id="4f6a2-140">Feedback?</span></span>
<span data-ttu-id="4f6a2-141">Для предоставления продукта свои отзывы и предложения или сообщите нам знать, как в нашем [Скайп для бизнеса свои отзывы и предложения](https://www.skypefeedback.com)см.</span><span class="sxs-lookup"><span data-stu-id="4f6a2-141">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>