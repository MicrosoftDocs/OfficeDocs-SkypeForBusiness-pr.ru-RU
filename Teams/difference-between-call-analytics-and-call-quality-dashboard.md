---
title: Вызов аналитики и панель мониторинга качества звонка
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Узнайте о вызова аналитики и панель мониторинга качества звонков и когда следует использовать их для мониторинга и устранения проблем качества звонка.
ms.openlocfilehash: 8d41e051a7f55c24c3388e707648970bb1ab64df
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013549"
---
# <a name="call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="87037-103">Вызов аналитики и панель мониторинга качества звонка</span><span class="sxs-lookup"><span data-stu-id="87037-103">Call Analytics and Call Quality Dashboard</span></span>

<span data-ttu-id="87037-104">Microsoft групп и Скайп для бизнеса предоставляют два способа наблюдения и устранения неполадок в качестве вызовов: вызова аналитики и панель мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="87037-104">Microsoft Teams and Skype for Business give you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard.</span></span> <span data-ttu-id="87037-105">В этой статье описывается, как и о том, когда следует использовать каждый из них.</span><span class="sxs-lookup"><span data-stu-id="87037-105">This article describes both and tells you when to use each one.</span></span>
  
<span data-ttu-id="87037-106">**Вызов Analytics теперь доступен в группами Майкрософт и Скайп по центру администрирования бизнес.**</span><span class="sxs-lookup"><span data-stu-id="87037-106">**Call Analytics is now available in the Microsoft Teams and Skype for Business Admin Center.**</span></span> <span data-ttu-id="87037-107">Чтобы просмотреть все сведения о вызовах и данные для пользователя, используйте вкладку **Журнал звонков** . Это можно сделать, нужна на странице профиля пользователя выполнить поиск по словам для пользователей из панели мониторинга или поиск пользователя от **пользователей** в левой панели навигации.</span><span class="sxs-lookup"><span data-stu-id="87037-107">To see all of the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by either searching for the user from the dashboard or finding the user from **Users** in the left navigation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87037-108">Служба технической поддержки агента разрешения и отправка топологии сети будут доступны в новый портал администрирования в течение нескольких месяцев.</span><span class="sxs-lookup"><span data-stu-id="87037-108">Helpdesk agent permissions and network topology upload will be available in the new admin portal in the coming months.</span></span> <span data-ttu-id="87037-109">В это время, могут продолжить использовать https://adminportal.services.skypeforbusiness.com для уровня 1 и 2 уровня доступа служба технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="87037-109">In the meantime, you can continue to use  https://adminportal.services.skypeforbusiness.com for Tier 1 and Tier 2 helpdesk access.</span></span>
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="87037-110">Что представляет собой средство аналитики звонков и для чего оно предназначено?</span><span class="sxs-lookup"><span data-stu-id="87037-110">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="87037-111">Аналитика вызова отображаются подробные сведения о устройств, сетей и подключения, относящиеся к определенным звонков и собрания для каждого пользователя в группами Майкрософт или Скайп для учетной записи Business.</span><span class="sxs-lookup"><span data-stu-id="87037-111">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="87037-112">Если вы администратор Office 365, можно использовать вызова Analytics неполадок вызов качества и подключения в группами Майкрософт и Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="87037-112">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems in Microsoft Teams and Skype for Business.</span></span>

<span data-ttu-id="87037-113">Чтобы увидеть эти сведения для пользователя в Microsoft групп и Скайп по центру администрирования Business, перейдите на вкладку **Журнал звонков** для этого пользователя на странице сведений пользователя, отображающая звонков и собрания этого пользователя участвовал в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="87037-113">To see this information for a user in the Microsoft Teams and Skype for Business Admin Center, click on the **Call History** tab for that user in the user detail page, showing all the calls and meetings that user has participated in for the last 30 days.</span></span>

![Вызов аналитических данных пользователя.](media/call-analytics-user-data.png)

<span data-ttu-id="87037-115">Для получения дополнительных сведений о конкретного сеанса, включая подробные мультимедиа и статистики к сети, нажмите кнопку сеанса, чтобы ознакомиться с подробными сведениями.</span><span class="sxs-lookup"><span data-stu-id="87037-115">To get additional information about a given session including detailed media and networking statistics, click on a session to see the details.</span></span>

![Вызов аналитических данных сеанса пользователя.](media/call-analytics-user-data-session.png)

<span data-ttu-id="87037-117">Если вы хотите предоставить доступ к средству аналитики звонков пользователям без прав администратора (например, агентам службы технической поддержки стороннего поставщика), следует назначить им разрешения на доступ к этому средству, запретив при этом доступ к остальным компонентам Центра администрирования Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="87037-117">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics but they can't access the rest of the Skype for Business Admin center:</span></span> 
  
- <span data-ttu-id="87037-p105">**Агенты службы технической поддержки с разрешениями уровня 1**. Могут просматривать ограниченный набор личных сведений в средстве аналитики звонков. Могут устранять неполадки со звонками, но проблемы с собраниями переадресуют агентам уровня 2.</span><span class="sxs-lookup"><span data-stu-id="87037-p105">**Helpdesk agents with Tier 1 permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics. They can troubleshoot calls, but they will hand off problems with meetings to a Tier 2 agent.</span></span>
    
- <span data-ttu-id="87037-p106">**Агенты службы технической поддержки с разрешениями уровня 1**. Могут просматривать все доступные в средстве аналитики звонков данные, а также устранять неполадки со звонками и собраниями. Имеют полный доступ к журналам звонков и сведениям о клиенте.</span><span class="sxs-lookup"><span data-stu-id="87037-p106">**Helpdesk agents with Tier 2 permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings. They have full access to call logs and customer information.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87037-122">Служба технической поддержки агента разрешения и отправка топологии сети будут доступны в новый портал администрирования в течение нескольких месяцев.</span><span class="sxs-lookup"><span data-stu-id="87037-122">Helpdesk agent permissions and network topology upload will be available in the new admin portal in the coming months.</span></span> <span data-ttu-id="87037-123">В это время, могут продолжить использовать https://adminportal.services.skypeforbusiness.com для уровня 1 и 2 уровня доступа служба технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="87037-123">In the meantime, you can continue to use  https://adminportal.services.skypeforbusiness.com for Tier 1 and Tier 2 helpdesk access.</span></span>
    
<span data-ttu-id="87037-124">Для получения дополнительных сведений о настройке вызова Analytics см [Скайп для вызова бизнес-аналитики](set-up-call-analytics.md).</span><span class="sxs-lookup"><span data-stu-id="87037-124">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="87037-125">Дополнительные сведения о работе агенты служба технической поддержки с помощью вызова анализа [Использования вызова аналитики для устранения неполадок вызовов плохого качества](use-call-analytics-to-troubleshoot-poor-call-quality.md)см.</span><span class="sxs-lookup"><span data-stu-id="87037-125">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="87037-126">Что представляет собой панель мониторинга качества звонков и для чего она предназначена?</span><span class="sxs-lookup"><span data-stu-id="87037-126">What's the Call Quality Dashboard, and when should I use it?</span></span>

<span data-ttu-id="87037-127">Вызов Analytics предоставляет подробную информацию о качестве вызовов, из-за пользователей определенного.</span><span class="sxs-lookup"><span data-stu-id="87037-127">Call Analytics gives you detailed, specific information about the call quality experienced by users.</span></span> <span data-ttu-id="87037-128">Почему было пользователя Tony Smith процента звонков обеда?</span><span class="sxs-lookup"><span data-stu-id="87037-128">Why did user Tony Smith have a poor call this afternoon?</span></span> <span data-ttu-id="87037-129">С помощью вызова Analytics, группами Майкрософт или Скайп для бизнес-администратором или агент обученные служба технической поддержки могут исследовать устройства, сети, подключения и другие факторы, связанные с вызова Тони Tony).</span><span class="sxs-lookup"><span data-stu-id="87037-129">Using Call Analytics, a Microsoft Teams or Skype for Business admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to Tony's call.</span></span>
  
<span data-ttu-id="87037-p110">В отличие от этого средства, с помощью панели мониторинга качества звонков администраторы Skype для бизнеса и сетевые инженеры могут оптимизировать характеристики сети на основе сведений на уровне всей организации Skype для бизнеса, а не отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="87037-p110">Where CA is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Skype for Business admins and network engineers optimize a network. CQD shifts focus from specific users and instead looks at aggregate information for an entire Skype for Business organization.</span></span> 
  
<span data-ttu-id="87037-p111">В приведенном выше примере плохое качество звонка может быть связано с проблемами в сети, которые могут затрагивать множество других пользователей. В панели мониторинга качества звонков нельзя просмотреть сведения об отдельном звонке  в ней обобщается информация обо всех звонках, выполненных с помощью Skype для бизнеса. Это позволяет проанализировать общие тенденции и проблемы, благодаря чему сетевые инженеры могут получить взвешенную оценку качества звонков. В этой панели мониторинга представлены отчеты по показателям, определяющим общее качество звонков, потоки сервер-клиент и клиент-клиент, а также [соглашения о качестве голосовой связи](https://go.microsoft.com/fwlink/p/?linkid=846252).</span><span class="sxs-lookup"><span data-stu-id="87037-p111">Maybe Tony's poor call quality is due to a network issue that's also affecting many other users. Tony's individual call experience isn't visible in CQD, but the overall quality of calls made using Skype for Business is captured. With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality. CQD provides reports of call quality metrics that give you insights into overall call quality, server-client and client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](media/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
<span data-ttu-id="87037-138">Дополнительные сведения см. в разделе [Функции панели мониторинга качества вызовов для Skype для бизнеса Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span><span class="sxs-lookup"><span data-stu-id="87037-138">For more details, see [Features of the Call Quality Dashboard for Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="87037-p113">Средство аналитики звонков и панель мониторинга качества звонков выполняются параллельно и могут использоваться независимо друг от друга. Допустим, агент уровня 1 решает, что для устранения проблемы со звонком требуется дополнительная помощь. В этом случае звонок передается агенту уровня 2, который имеет доступ к более широкому набору сведений в средстве аналитики звонков. Агент уровня 2, в свою очередь, может оповестить о проблеме сетевого инженера. С помощью панели мониторинга качества звонков сетевой инженер может выявить и проанализировать общие проблемы, влияющие на качество звонков.</span><span class="sxs-lookup"><span data-stu-id="87037-p113">Call Analytics and CQD run in parallel and can be used independently or together. For example, say a Tier 1 agent determines that they need more help troubleshooting a call problem. The Tier 1 agent passes the call to a Tier 2 agent, who has access to more information in Call Analytics than the Tier 1 agent. In turn, the Tier 2 agent can alert a network engineer to an issue. The network engineer may check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>
  
<span data-ttu-id="87037-144">Дополнительные сведения о CQD можно [Включить и с помощью вызова панели мониторинга качества для групп Майкрософт и Скайп для бизнеса в Интернет](turning-on-and-using-call-quality-dashboard.md) и [измерения и меры, доступные в вызов качества панели мониторинга для групп Майкрософт и Скайп для бизнеса в Интернет](dimensions-and-measures-available-in-call-quality-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="87037-144">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="87037-145">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="87037-145">Related topics</span></span>
[<span data-ttu-id="87037-146">Настройка вызова аналитики</span><span class="sxs-lookup"><span data-stu-id="87037-146">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="87037-147">Устранение неполадок с качеством звонков с помощью средства аналитики звонков</span><span class="sxs-lookup"><span data-stu-id="87037-147">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)