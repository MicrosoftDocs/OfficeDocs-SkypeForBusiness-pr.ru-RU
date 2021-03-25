---
title: Отслеживание и устранение неполадок прямой маршрутизации
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, как отслеживать и устранять неполадки с прямой маршрутией, включая контроллеры границ сеанса, компоненты прямой маршрутации и линии связи.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121407"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="c0d5e-103">Отслеживание и устранение неполадок прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="c0d5e-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="c0d5e-104">В этой статье описано, как отслеживать и устранять неполадки с конфигурацией direct Routing.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="c0d5e-105">Возможность звонить и принимать звонки с помощью прямой маршрутинга включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="c0d5e-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="c0d5e-106">Контроллеры границ сеанса (SBCs)</span><span class="sxs-lookup"><span data-stu-id="c0d5e-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="c0d5e-107">Компоненты прямой маршрутки в Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="c0d5e-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="c0d5e-108">Телекоммуникационные связи</span><span class="sxs-lookup"><span data-stu-id="c0d5e-108">Telecom trunks</span></span> 

<span data-ttu-id="c0d5e-109">Если у вас возникли сложности с устранением неполадок, вы можете открыть запрос в службу поддержки поставщику или корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="c0d5e-110">Корпорация Майкрософт работает над предоставлением дополнительных средств для устранения неполадок и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="c0d5e-111">Периодически проверяйте документацию на новости.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="c0d5e-112">Отслеживание доступности граничных геймпадов сеанса с помощью параметров протокола SIP</span><span class="sxs-lookup"><span data-stu-id="c0d5e-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="c0d5e-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="c0d5e-114">Для того чтобы включить мониторинг параметров SIP, администратор клиента не должен ничего делать.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="c0d5e-115">Собранные сведения принимаются во внимание при принятии решений о маршрутке.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="c0d5e-116">Например, если для определенного пользователя существует несколько SBCs, доступных для перенаправки звонка, Direct Routing рассматривает сведения о параметрах SIP, полученные с каждого SBC для определения маршрутов.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="c0d5e-117">На следующей схеме показан пример конфигурации:</span><span class="sxs-lookup"><span data-stu-id="c0d5e-117">The following diagram shows an example of the configuration:</span></span> 

![Пример конфигурации параметров SIP](media/sip-options-config-example.png)

<span data-ttu-id="c0d5e-119">Когда пользователь звонит на номер +1 425, прямая маршрутка оценивает \<any seven digits> маршрут.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="c0d5e-120">В маршруте есть две SBCs: sbc1.contoso.com и sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="c0d5e-121">Обе SBCs имеют одинаковый приоритет в маршруте.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="c0d5e-122">Прежде чем выбирать SBC, механизм маршрутации оценивает состояние SBCs на основе времени последней передачи параметров SIP.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="c0d5e-123">SBC считается полезным, если согласно статистике на момент отправки звонка параметры отправляются каждую минуту.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="c0d5e-124">При звонок применяется следующая логика:</span><span class="sxs-lookup"><span data-stu-id="c0d5e-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="c0d5e-125">Запрос SBC был сопряжен в 11:00.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="c0d5e-126">Параметры SBC отправляются в 11:01, 11:02 и так далее.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="c0d5e-127">В 11:15 пользователь звонит, и механизм маршрутации выбирает этот SBC.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="c0d5e-128">При прямой маршрутике интервалы обычно забираются три раза (обычный интервал составляет одну минуту).</span><span class="sxs-lookup"><span data-stu-id="c0d5e-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="c0d5e-129">Если параметры были отправляться в течение последних трех минут, SBC считается здоровой.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="c0d5e-130">Если SBC в примере отправлен параметры в любой период между 11:12 и 11:15 (время звонка), он считается полезным.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="c0d5e-131">В этом случае SBC будет понижен с маршрута.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="c0d5e-132">Понижение означает, что сначала не будет опробовательна SBC.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="c0d5e-133">Например, у нас есть sbc1.contoso.com и sbc2.contoso.com с одинаковым приоритетом.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="c0d5e-134">Если sbc1.contoso.com не отправляют параметры SIP через регулярный интервал времени, как описано выше, он будет понижен.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="c0d5e-135">После этого sbc2.contoso.com попытается позвонить.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="c0d5e-136">Если sbc2.contoso.con не удается доставить звонок, то перед тем как сбой будет создан, sbc1.contoso.com (понизить его) будет повторить попытку.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="c0d5e-137">Если два (или более) SBCs в одном маршруте считаются полезными и равными, для распространения звонков между ними применяется Fisher-Yates в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="c0d5e-138">Мониторинг панели мониторинга аналитики качества звонка и журналов SBC</span><span class="sxs-lookup"><span data-stu-id="c0d5e-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="c0d5e-139">В некоторых случаях, особенно при начальной связи, могут возникнуть проблемы, связанные с неправильной оптимизацией SBCs или службы прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="c0d5e-140">Для отслеживания конфигурации можно использовать следующие средства:</span><span class="sxs-lookup"><span data-stu-id="c0d5e-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="c0d5e-141">Панель мониторинга качества вызовов</span><span class="sxs-lookup"><span data-stu-id="c0d5e-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="c0d5e-142">Журналы SBC</span><span class="sxs-lookup"><span data-stu-id="c0d5e-142">SBC logs</span></span> 

<span data-ttu-id="c0d5e-143">Служба direct Routing имеет очень описательные коды ошибок, которые были сообщались в средстве аналитики вызовов или журналах SBC.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="c0d5e-144">Информационная панель качества звонка предоставляет сведения о качестве и надежности звонка.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="c0d5e-145">Чтобы узнать больше об устранении неполадок с использованием средства аналитики звонков, см. включение и использование панели мониторинга качества звонков в Microsoft Teams и Skype для бизнеса [Online,](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) а также использование средства аналитики звонков для устранения неполадок с качеством [звонков.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="c0d5e-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="c0d5e-146">В случае сбоев средства аналитики вызовов предоставляют стандартные SIP-коды для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Пример кода SIP для сбоя вызова](media/failed-response-code.png)

<span data-ttu-id="c0d5e-148">Однако средству аналитики звонков может быть нужна только связь с внутренними компонентами прямой маршрутки и сбой.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="c0d5e-149">В случае проблем с парой SBC или из-за проблем с отклонением приглашения SIP (например, неправильно задано имя FQDN для связи), аналитика вызовов не поможет.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="c0d5e-150">В этом случае обратитесь к журналам SBC.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="c0d5e-151">Direct Routing отправляет подробное описание проблем в SBCs; эти проблемы можно прочитать в журналах SBC.</span><span class="sxs-lookup"><span data-stu-id="c0d5e-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span>