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
description: Узнайте, как отслеживать и устранять неполадки с прямой маршрутией, включая контроллеры границ сеанса, компоненты прямой маршрутации и линии связи Telecom.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121407"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="4aa83-103">Отслеживание и устранение неполадок прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="4aa83-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="4aa83-104">В этой статье описано, как отслеживать и устранять неполадки с настройкой прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="4aa83-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="4aa83-105">Возможность звонить и принимать звонки с помощью прямой маршрутизов включает в себя следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="4aa83-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="4aa83-106">Контроллеры границ сеанса (SBCs)</span><span class="sxs-lookup"><span data-stu-id="4aa83-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="4aa83-107">Компоненты прямой маршрутии в Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="4aa83-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="4aa83-108">Телекоммуникационные связи</span><span class="sxs-lookup"><span data-stu-id="4aa83-108">Telecom trunks</span></span> 

<span data-ttu-id="4aa83-109">Если у вас возникают сложности при устранении неполадок, вы можете открыть запрос в службу поддержки у поставщика SBC или корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4aa83-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="4aa83-110">Корпорация Майкрософт работает над предоставлением дополнительных средств для устранения неполадок и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4aa83-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="4aa83-111">Периодически проверяйте документацию на новости.</span><span class="sxs-lookup"><span data-stu-id="4aa83-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="4aa83-112">Мониторинг доступности контроллеров границ сеанса с помощью сообщений параметров SIP</span><span class="sxs-lookup"><span data-stu-id="4aa83-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="4aa83-113">Прямая маршрутия использует параметры SIP, отправленные контроллерами границ сеанса для отслеживания состояния SBC.</span><span class="sxs-lookup"><span data-stu-id="4aa83-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="4aa83-114">Для того чтобы включить мониторинг параметров SIP, администратор клиента не должен ничего делать.</span><span class="sxs-lookup"><span data-stu-id="4aa83-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="4aa83-115">Собранные сведения принимаются во внимание при принятии решений о маршрутике.</span><span class="sxs-lookup"><span data-stu-id="4aa83-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="4aa83-116">Например, если для определенного пользователя существует несколько SBCs, доступных для перенаправки звонка, прямая маршрутия рассматривает сведения о параметрах SIP, полученные от каждого SBC, чтобы определить маршрутику.</span><span class="sxs-lookup"><span data-stu-id="4aa83-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="4aa83-117">На следующей схеме показан пример конфигурации:</span><span class="sxs-lookup"><span data-stu-id="4aa83-117">The following diagram shows an example of the configuration:</span></span> 

![Пример конфигурации параметров SIP](media/sip-options-config-example.png)

<span data-ttu-id="4aa83-119">Когда пользователь звонит на номер +1 425, прямая маршрутная \<any seven digits> маршрутия оценивает маршрут.</span><span class="sxs-lookup"><span data-stu-id="4aa83-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="4aa83-120">В маршруте есть два SBCs: sbc1.contoso.com и sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4aa83-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="4aa83-121">У обеих УАЦ одинаковый приоритет в маршруте.</span><span class="sxs-lookup"><span data-stu-id="4aa83-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="4aa83-122">Прежде чем выбирать SBC, механизм маршрутации оценивает состояние SBCs на основе времени последней передачи параметров SIP.</span><span class="sxs-lookup"><span data-stu-id="4aa83-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="4aa83-123">SBC считается полезным, если статистика на момент отправки звонка показывает, что параметры SBC отправляются каждую минуту.</span><span class="sxs-lookup"><span data-stu-id="4aa83-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="4aa83-124">При звонии применяется следующая логика:</span><span class="sxs-lookup"><span data-stu-id="4aa83-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="4aa83-125">SBC был сопряжен в 11:00.</span><span class="sxs-lookup"><span data-stu-id="4aa83-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="4aa83-126">Параметры SBC отправляются в 11:01, 11:02 и так далее.</span><span class="sxs-lookup"><span data-stu-id="4aa83-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="4aa83-127">В 11:15 пользователь звонит, и этот SBC выбирается с учетом механизмов маршрутации.</span><span class="sxs-lookup"><span data-stu-id="4aa83-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="4aa83-128">Прямая маршрутная маршрутия принимает параметры интервалов три раза (обычный интервал составляет одну минуту).</span><span class="sxs-lookup"><span data-stu-id="4aa83-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="4aa83-129">Если параметры были отправляться в течение последних трех минут, то SBC считается полезным.</span><span class="sxs-lookup"><span data-stu-id="4aa83-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="4aa83-130">Если параметры SBC в примере отправлены в любой период между 11:12 и 11:15 (время звонка), он считается полезным.</span><span class="sxs-lookup"><span data-stu-id="4aa83-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="4aa83-131">В этом случае SBC будет понижен с маршрута.</span><span class="sxs-lookup"><span data-stu-id="4aa83-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="4aa83-132">Понижение означает, что SBC не будет сначала опробоваться.</span><span class="sxs-lookup"><span data-stu-id="4aa83-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="4aa83-133">Например, у нас есть sbc1.contoso.com и sbc2.contoso.com с равным приоритетом.</span><span class="sxs-lookup"><span data-stu-id="4aa83-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="4aa83-134">Если sbc1.contoso.com SIP не отправляет параметры SIP через равные интервалы, как описано выше, он будет понижен.</span><span class="sxs-lookup"><span data-stu-id="4aa83-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="4aa83-135">Затем sbc2.contoso.com пытается позвонить.</span><span class="sxs-lookup"><span data-stu-id="4aa83-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="4aa83-136">Если sbc2.contoso.con не удается доставить звонок, sbc1.contoso.com (понизить его) перед сбоем.</span><span class="sxs-lookup"><span data-stu-id="4aa83-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="4aa83-137">Если два (или более) SBCs в одном маршруте считаются полезными и равными, Fisher-Yates применяется Fisher-Yates для распространения звонков между ними.</span><span class="sxs-lookup"><span data-stu-id="4aa83-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="4aa83-138">Мониторинг панели мониторинга средств аналитики качества звонка и журналов SBC</span><span class="sxs-lookup"><span data-stu-id="4aa83-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="4aa83-139">В некоторых случаях, особенно во время начальной связи, могут возникнуть проблемы, связанные с неправильнойнастройкой SBCs или службы прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="4aa83-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="4aa83-140">Для отслеживания конфигурации можно использовать следующие средства:</span><span class="sxs-lookup"><span data-stu-id="4aa83-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="4aa83-141">Панель мониторинга качества вызовов</span><span class="sxs-lookup"><span data-stu-id="4aa83-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="4aa83-142">Журналы SBC</span><span class="sxs-lookup"><span data-stu-id="4aa83-142">SBC logs</span></span> 

<span data-ttu-id="4aa83-143">В службе Direct Routing есть очень описательные коды ошибок, которые печатались в средствах аналитики вызовов или журналах SBC.</span><span class="sxs-lookup"><span data-stu-id="4aa83-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="4aa83-144">Информационная панель качества звонка содержит сведения о качестве и надежности звонка.</span><span class="sxs-lookup"><span data-stu-id="4aa83-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="4aa83-145">Дополнительные информацию об устранении неполадок с помощью средства аналитики вызовов см. в вопросах Включение и использование панели мониторинга качества звонка для Microsoft Teams и [Skype для бизнеса Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) и Устранение неполадок с качеством звонка с помощью средства аналитики вызовов. [](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="4aa83-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="4aa83-146">При сбоях вызовов средства аналитики вызовов предоставляют стандартные SIP-коды, которые помогут вам устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="4aa83-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Пример кода SIP для сбоя звонка](media/failed-response-code.png)

<span data-ttu-id="4aa83-148">Однако средству аналитики звонков может помочь только то, что звонки перенаправят на внутренние компоненты прямой маршрутки и сбой.</span><span class="sxs-lookup"><span data-stu-id="4aa83-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="4aa83-149">При проблемах с сопряжением SBC или проблемах, из-за которых SIP "Пригласить" была отклонена (например, неправильно задано имя FQDN для связи), аналитика вызовов не поможет.</span><span class="sxs-lookup"><span data-stu-id="4aa83-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="4aa83-150">В этом случае обратитесь к журналам SBC.</span><span class="sxs-lookup"><span data-stu-id="4aa83-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="4aa83-151">Direct Routing отправляет подробное описание проблем на SBCs; эти проблемы можно прочитать в журналах SBC.</span><span class="sxs-lookup"><span data-stu-id="4aa83-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span>