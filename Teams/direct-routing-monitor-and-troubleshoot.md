---
title: Мониторинг и устранение неполадок прямой маршрутизации
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: ''
description: В этой статье описывается, как для мониторинга и устранения неполадок конфигурации прямой маршрутизации.
ms.openlocfilehash: 92a7f0ed27549ace44bf962a1aa7bb47e24b4ab4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23857189"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="10822-103">Мониторинг и устранение неполадок прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="10822-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="10822-104">В этой статье описывается, как для мониторинга и устранения неполадок конфигурации прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="10822-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="10822-105">Возможность выполнение и прием звонков с помощью прямой маршрутизации состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="10822-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="10822-106">Пограничных контроллеров сеансов (SBC)</span><span class="sxs-lookup"><span data-stu-id="10822-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="10822-107">Прямое подключение компоненты маршрутизации в облаке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="10822-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="10822-108">Телекоммуникации магистральных линий связи</span><span class="sxs-lookup"><span data-stu-id="10822-108">Telecom trunks</span></span> 

<span data-ttu-id="10822-109">Если возникают проблемы, устранение неполадок, связанных откройте дела поддержки с SBC поставщика или Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10822-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="10822-110">Корпорация Майкрософт работает на предоставление дополнительные средства для наблюдения и устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="10822-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="10822-111">Обратитесь к документации периодически для обновления.</span><span class="sxs-lookup"><span data-stu-id="10822-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="10822-112">Мониторинг доступность пограничных контроллеров сеансов с помощью параметров Session Initiation Protocol (SIP) сообщений</span><span class="sxs-lookup"><span data-stu-id="10822-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) Options messages</span></span>

<span data-ttu-id="10822-113">Прямое маршрутизации использует параметры SIP, отправленный пограничных контроллеров сеансов для отслеживания работоспособности SBC.</span><span class="sxs-lookup"><span data-stu-id="10822-113">Direct Routing uses SIP Options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="10822-114">Отсутствуют действия требуется для разрешить мониторинг параметры SIP от администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="10822-114">There are no actions required from the tenant administrator to enable the SIP Options monitoring.</span></span> <span data-ttu-id="10822-115">Собранные сведения — это принять во внимание при внесении решений о маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="10822-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="10822-116">Например если для определенного пользователя существует несколько их изготовителей, доступные для маршрутизации вызовов, прямой маршрутизации считает SIP-параметры сведения, полученные от каждого SBC для определения маршрута.</span><span class="sxs-lookup"><span data-stu-id="10822-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP Options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="10822-117">Ниже показан пример конфигурации:</span><span class="sxs-lookup"><span data-stu-id="10822-117">The following diagram shows an example of the configuration:</span></span> 

![Пример конфигурации параметров SIP](media/sip-options-config-example.png)

<span data-ttu-id="10822-119">Когда пользователь выбирает вызова на номер +1 425 \<любого семь цифр >, прямой маршрутизации оценивает маршрут.</span><span class="sxs-lookup"><span data-stu-id="10822-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="10822-120">Существует два SBC в маршруте: sbc1.contoso.com и sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="10822-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="10822-121">Оба SBC имеют одинаковый приоритет в маршруте.</span><span class="sxs-lookup"><span data-stu-id="10822-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="10822-122">Прежде чем комплектации SBC механизм маршрутизации проверяет работоспособность их изготовителей, при отправке SBC параметры SIP на основе времени последнего.</span><span class="sxs-lookup"><span data-stu-id="10822-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP Options last time.</span></span> 

<span data-ttu-id="10822-123">SBC считается работоспособны, если статистика в настоящее время отправки вызова показывает, что SBC отправляет параметры на определенный интервал.</span><span class="sxs-lookup"><span data-stu-id="10822-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="10822-124">Прямое маршрутизации вычисляет регулярные интервалы времени, используя два раза среднего значения, когда SBC отправляет параметры перед вызовом и добавлением пять минут.</span><span class="sxs-lookup"><span data-stu-id="10822-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends Options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="10822-125">Предположим, например, следующие:</span><span class="sxs-lookup"><span data-stu-id="10822-125">For example, assume the following:</span></span> 

- <span data-ttu-id="10822-126">SBC настроена для отправки параметры каждую минуту.</span><span class="sxs-lookup"><span data-stu-id="10822-126">An SBC is configured to send Options every minute.</span></span> 
- <span data-ttu-id="10822-127">SBC был в сочетании с 11.00 AM.</span><span class="sxs-lookup"><span data-stu-id="10822-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="10822-128">SBC отправляет параметры 11.01 AM, 11.02 AM и т. д.</span><span class="sxs-lookup"><span data-stu-id="10822-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="10822-129">В 11.15 выполняется вызов и механизм маршрутизации выбирает этот пограничный контроллер Сеансов.</span><span class="sxs-lookup"><span data-stu-id="10822-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="10822-130">Применить следующую логику: два интервалов среднее при SBC отправляет параметры (одну минуту плюс одну минуту = две минуты) плюс пять минут = 7 минут.</span><span class="sxs-lookup"><span data-stu-id="10822-130">The following logic is applied: Two times the average interval when the SBC sends Options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="10822-131">Это значение интервалом для SBC.</span><span class="sxs-lookup"><span data-stu-id="10822-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="10822-132">Если SBC в нашем примере отправлено параметры в любой период между 11.08 AM и 11.15 AM (время звонка), он считается работоспособны.</span><span class="sxs-lookup"><span data-stu-id="10822-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="10822-133">В противном случае будут понижены SBC из маршрута.</span><span class="sxs-lookup"><span data-stu-id="10822-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="10822-134">Понижение уровня означает, что SBC будет не применять в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="10822-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="10822-135">Например у нас есть sbc1.contoso.com и sbc2.contoso.com с одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="10822-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="10822-136">Sbc1.contoso.com не отправляет параметры SIP на определенный интервал, как описано выше, ранге.</span><span class="sxs-lookup"><span data-stu-id="10822-136">If sbc1.contoso.com does not send SIP Options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="10822-137">Рассмотрим процедуру sbc2.contoso.com попытается для вызова.</span><span class="sxs-lookup"><span data-stu-id="10822-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="10822-138">Если sbc2.contoso.con не удается доставить звонок, sbc1.contoso.com (понижен) производится попытка еще раз, перед тем, как сбой.</span><span class="sxs-lookup"><span data-stu-id="10822-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="10822-139">Мониторинг Analytics качества звонков панели мониторинга и журналы SBC</span><span class="sxs-lookup"><span data-stu-id="10822-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="10822-140">В некоторых случаях особенно во время начальной связывания, могут возникнуть вопросы, связанные с неправильной настройке SBC и/или службы прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="10822-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="10822-141">Можно использовать следующие средства для наблюдения за вашей конфигурации:</span><span class="sxs-lookup"><span data-stu-id="10822-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="10822-142">Панель мониторинга качества звонка</span><span class="sxs-lookup"><span data-stu-id="10822-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="10822-143">Журналы SBC</span><span class="sxs-lookup"><span data-stu-id="10822-143">SBC logs</span></span> 

<span data-ttu-id="10822-144">Служба прямой маршрутизации имеет отчеты вызова аналитики или журналы SBC коды очень описанием ошибки.</span><span class="sxs-lookup"><span data-stu-id="10822-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="10822-145">Панель мониторинга качества звонков предоставляет сведения о качестве вызовов и надежности.</span><span class="sxs-lookup"><span data-stu-id="10822-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="10822-146">Дополнительные сведения об устранении проблем с помощью вызова Analytics содержатся [для включения и с помощью вызова панели мониторинга качества для групп Майкрософт и Скайп для бизнеса в Интернет](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) и [Аналитических звонков использовать для устранения неполадок вызовов плохого качества](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="10822-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="10822-147">В случае сбоев вызова вызова Analytics предоставляет стандартные коды SIP для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="10822-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Пример кода SIP для сбоя вызова](media/failed-response-code.png)

<span data-ttu-id="10822-149">Когда reach внутренних компонентов прямой маршрутизации вызовов и не вызова Analytics может помочь только.</span><span class="sxs-lookup"><span data-stu-id="10822-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="10822-150">В случае проблемы, связанные с SBC связывания или проблем, где был отклонен SIP «Пригласить» (например, имя линии связи, которые неправильно настроено полное доменное имя) не поможет вызова аналитики.</span><span class="sxs-lookup"><span data-stu-id="10822-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="10822-151">В этом случае обратитесь за помощью в SBC журналы.</span><span class="sxs-lookup"><span data-stu-id="10822-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="10822-152">Прямое маршрутизации отправляет подробное описание проблемы на их изготовителей; Эти проблемы могут читать из журналов SBC.</span><span class="sxs-lookup"><span data-stu-id="10822-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
