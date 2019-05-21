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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: В этой статье описано, как отслеживать и устранять проблемы с настройкой прямой маршрутизации.
ms.openlocfilehash: b4d53ad566cd0c31696ce688044ce1587d771a7d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290410"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="0f0bc-103">Отслеживание и устранение неполадок прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="0f0bc-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="0f0bc-104">В этой статье описано, как отслеживать и устранять проблемы с настройкой прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="0f0bc-105">Возможность совершать и принимать звонки с помощью Direct Routing состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="0f0bc-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="0f0bc-106">Контроллеры границ сеансов (SBCs)</span><span class="sxs-lookup"><span data-stu-id="0f0bc-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="0f0bc-107">Прямые компоненты маршрутизации в Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="0f0bc-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="0f0bc-108">Коммуникационные магистрали</span><span class="sxs-lookup"><span data-stu-id="0f0bc-108">Telecom trunks</span></span> 

<span data-ttu-id="0f0bc-109">Если у вас возникли проблемы при устранении неполадок, пожалуйста, открывайте обращение в службу поддержки с поставщиком SBC или корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="0f0bc-110">Корпорация Майкрософт работает над предоставлением дополнительных инструментов для устранения неполадок и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="0f0bc-111">Пожалуйста, периодически проверяйте документацию на наличие обновлений.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="0f0bc-112">Наблюдение за доступностьми контроллеров границ сеанса с помощью сообщений параметров протокола запуска сеанса (SIP)</span><span class="sxs-lookup"><span data-stu-id="0f0bc-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) Options messages</span></span>

<span data-ttu-id="0f0bc-113">Прямая маршрутизация использует параметры SIP, отправленные контроллерами границ сеанса для мониторинга работоспособности SBC.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-113">Direct Routing uses SIP Options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="0f0bc-114">Для включения наблюдения за параметрами SIP в администраторе клиента не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-114">There are no actions required from the tenant administrator to enable the SIP Options monitoring.</span></span> <span data-ttu-id="0f0bc-115">Собранные сведения учитываются при принятии решений о маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="0f0bc-116">Например, если для определенного пользователя доступно несколько однородных данных для маршрутизации звонка, прямая маршрутизация рассматривает сведения о параметрах SIP, полученные от каждого SBC, для определения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP Options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="0f0bc-117">На приведенной ниже схеме показан пример конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-117">The following diagram shows an example of the configuration:</span></span> 

![Пример настройки параметров SIP](media/sip-options-config-example.png)

<span data-ttu-id="0f0bc-119">Когда пользователь выполняет звонок на номер + 1 425 \<любой семь Дигитс_гт_, прямая маршрутизация оценивает маршрут.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="0f0bc-120">В Route: sbc1.contoso.com и sbc2.contoso.com есть две SBCs.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="0f0bc-121">В маршруте есть одинаковый приоритет для обоих SBCs.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="0f0bc-122">Перед тем как выбрать объект SBC, механизм маршрутизации оценивает работоспособность SBCs на основе того, когда SBC отправляет параметры SIP в прошлый раз.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP Options last time.</span></span> 

<span data-ttu-id="0f0bc-123">SBC считается работоспособным, если статистика на момент отправки звонка показывает, что SBC отправляет параметры в обычном диапазоне.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="0f0bc-124">Прямые маршрутизаторы рассчитывают регулярные интервалы на два часа, когда SBC отправляет параметры, прежде чем звонить и добавлять пять минут.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends Options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="0f0bc-125">Например, предположим, что следующее:</span><span class="sxs-lookup"><span data-stu-id="0f0bc-125">For example, assume the following:</span></span> 

- <span data-ttu-id="0f0bc-126">Каждый минутный интерфейс SBC настроен для отправки параметров.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-126">An SBC is configured to send Options every minute.</span></span> 
- <span data-ttu-id="0f0bc-127">SBC был парным в 11,00 AM.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="0f0bc-128">Параметры SBC отправляются в 11,01 AM, 11,02 AM и т. д.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="0f0bc-129">В 11,15 пользователь выполняет звонок, а механизм маршрутизации — для выбора этого SBC.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="0f0bc-130">Применяется следующая логика: два значения интервала, когда параметр SBC отправляет параметры (одна минута плюс одна минута = две минуты) плюс пять минут = семь минут.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-130">The following logic is applied: Two times the average interval when the SBC sends Options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="0f0bc-131">Это значение регулярного интервала для SBC.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="0f0bc-132">Если SBC в нашем примере отправляет параметры в любой точке между 11,08 AM и 11,15 AM (время совершения звонка), это считается работоспособным.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="0f0bc-133">В противном случае SBC будет понижен из маршрута.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="0f0bc-134">Понижение роли означает, что SBC не будет применяться первыми.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="0f0bc-135">Например, у нас есть sbc1.contoso.com и sbc2.contoso.com с одинаковым приоритетом.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="0f0bc-136">Если sbc1.contoso.com не отправляет параметры SIP в обычном интервале, как описано выше, это понизить уровень.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-136">If sbc1.contoso.com does not send SIP Options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="0f0bc-137">Затем sbc2.contoso.com пытается позвонить.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="0f0bc-138">Если sbc2. contoso. Con не может допустить звонок, то sbc1.contoso.com (понижение роли) предпринимается повторно, пока не будет создан сбой.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="0f0bc-139">Наблюдение за анализом качества связи на информационной панели и в журналах SBC</span><span class="sxs-lookup"><span data-stu-id="0f0bc-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="0f0bc-140">В некоторых случаях, особенно при первоначальном связывании, могут возникать проблемы, связанные с невозможностью настройки SBCs и/или прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="0f0bc-141">Для мониторинга конфигурации можно использовать следующие инструменты:</span><span class="sxs-lookup"><span data-stu-id="0f0bc-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="0f0bc-142">Панель мониторинга качества вызовов</span><span class="sxs-lookup"><span data-stu-id="0f0bc-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="0f0bc-143">Журналы SBC</span><span class="sxs-lookup"><span data-stu-id="0f0bc-143">SBC logs</span></span> 

<span data-ttu-id="0f0bc-144">У службы прямой маршрутизации есть очень описательные коды ошибок, которые выводятся в разделе анализ звонков или в журналы SBC.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="0f0bc-145">На панели мониторинга качества звонков содержатся сведения о качестве и надежности связи.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="0f0bc-146">Подробнее о том, как устранять неполадки с помощью средства аналитики звонков, приведены в [статье Включение и использование панели мониторинга качества звонков для Microsoft Teams и Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) и [Использование средства аналитики звонков для устранения](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)некачественной связи.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="0f0bc-147">В случае отказов в вызовах аналитика звонков предлагает стандартные коды SIP, которые помогут вам устранить неполадки.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Образец кода SIP для отказа в звонке](media/failed-response-code.png)

<span data-ttu-id="0f0bc-149">Тем не менее, служба поддержки может помогать вам только в том случае, если во время звонков достигается внутренний компонент Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="0f0bc-150">В случае проблем с связыванием или проблемами с SBC, в которых было отказано в использовании SIP "INVITE" (например, неправильно настроено имя узла магистральной магистрали), средство анализа вызовов не поможет.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="0f0bc-151">В этом случае следует обращаться к журналам SBC.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="0f0bc-152">Прямая маршрутизация отправляет подробное описание проблем с SBCs-записью; Эти проблемы можно прочитать в журналах SBC.</span><span class="sxs-lookup"><span data-stu-id="0f0bc-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
