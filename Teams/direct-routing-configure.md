---
title: Настройка прямой маршрутизации
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Сведения о настройке Microsoft телефонной системы прямой маршрутизации.
ms.openlocfilehash: 514be758042284f40dfab055eacf5b0f3222afd7
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402525"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="04cea-103">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="04cea-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="04cea-104">Просмотрите следующие сеанса, чтобы узнать о преимуществах прямой маршрутизации, как спланировать его и способе развертывания: [Прямой маршрутизации в группах Майкрософт](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="04cea-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="04cea-105">Если вы еще не сделали прочитайте [Планирование прямой маршрутизации](direct-routing-plan.md) наличие необходимых компонентов и просмотреть другие действия необходимо выполнить перед настройкой сети Microsoft телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="04cea-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="04cea-106">В этой статье описывается настройка прямой маршрутизации Microsoft телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="04cea-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="04cea-107">Описывается, как связать поддерживаемые пограничный контроллер сеансов (SBC) для прямой маршрутизации и способы настройки групп Майкрософт пользователям использовать прямой маршрутизации для подключения к общедоступной переключения телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="04cea-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="04cea-108">Для выполнения действий, описанных в данной статье, администраторы должны знакомы с командлеты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04cea-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="04cea-109">Дополнительные сведения об использовании PowerShell в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="04cea-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="04cea-110">Рекомендуется, чтобы подтвердить, что пограничного контроллера Сеансов уже настроен как рекомендовано поставщиком SBC:</span><span class="sxs-lookup"><span data-stu-id="04cea-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="04cea-111">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="04cea-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="04cea-112">Лента Communications документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="04cea-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="04cea-113">Можно настроить телефонной системой Microsoft и пользователи могли использовать прямой маршрутизации, а затем настроить группами Майкрософт как предпочитаемый вызывающего клиента, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="04cea-113">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="04cea-114">Пары SBC с телефонной системы Microsoft и проверки связывания</span><span class="sxs-lookup"><span data-stu-id="04cea-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="04cea-115">Включение пользователей для службы напрямую маршрутизации</span><span class="sxs-lookup"><span data-stu-id="04cea-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="04cea-116">Убедитесь, что группами Майкрософт является предпочтительным вызывающего клиента для пользователей</span><span class="sxs-lookup"><span data-stu-id="04cea-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="04cea-117">Пары SBC для непосредственного маршрутизации службы телефонной системой</span><span class="sxs-lookup"><span data-stu-id="04cea-117">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="04cea-118">Ниже приведены три основных действия можно подключиться или пары SBC интерфейс прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="04cea-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="04cea-119">Подключение к центру администрирования **Скайп для бизнеса в Интернет** , с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="04cea-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="04cea-120">Пара SBC</span><span class="sxs-lookup"><span data-stu-id="04cea-120">Pair the SBC</span></span> 
- <span data-ttu-id="04cea-121">Проверка сопоставления</span><span class="sxs-lookup"><span data-stu-id="04cea-121">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="04cea-122">Подключение к Скайп для бизнеса в Интернет с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="04cea-122">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="04cea-123">Можно использовать сеанс PowerShell, подключенных к клиенту связать SBC интерфейс прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="04cea-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="04cea-124">Чтобы открыть сеанс PowerShell, выполните действия, указанные в [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="04cea-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="04cea-125">После создания удаленного сеанса PowerShell, проверьте, что вы видите команды для управления SBC.</span><span class="sxs-lookup"><span data-stu-id="04cea-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="04cea-126">Для проверки команды, введите или копирование и вставка в следующем в сеанс PowerShell и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="04cea-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="04cea-127">Команда вернет четыре функций, которые будут позволяют управлять SBC.</span><span class="sxs-lookup"><span data-stu-id="04cea-127">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="04cea-128">Пара SBC к клиенту</span><span class="sxs-lookup"><span data-stu-id="04cea-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="04cea-129">Связать SBC к клиенту в сеанс PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="04cea-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="04cea-130">Мы настоятельно рекомендуем задание ограничений максимально допустимое число вызовов в SBC, с помощью сведений, можно найти в документации по SBC.</span><span class="sxs-lookup"><span data-stu-id="04cea-130">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="04cea-131">Ограничение запустит уведомление, если SBC был создан на уровне мощности.</span><span class="sxs-lookup"><span data-stu-id="04cea-131">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="04cea-132">Только вы можете обеспечить SBC Если часть домена его полному доменному ИМЕНИ соответствует одному из доменов, зарегистрированных в клиенту, за исключением \*. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="04cea-132">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="04cea-133">С помощью \*. onmicrosoft.com доменных имен не поддерживается для SBC полное ДОМЕННОЕ имя.</span><span class="sxs-lookup"><span data-stu-id="04cea-133">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="04cea-134">Например, если у вас есть два доменных имен:</span><span class="sxs-lookup"><span data-stu-id="04cea-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="04cea-135">**Contoso**.com</span><span class="sxs-lookup"><span data-stu-id="04cea-135">**contoso**.com</span></span><br/><span data-ttu-id="04cea-136">**Contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="04cea-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="04cea-137">Для имени SBC можно использовать имя sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="04cea-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="04cea-138">При попытке связать SBC с именем sbc.contoso.abc, система не позволит вам, как домен не принадлежит этот клиент.</span><span class="sxs-lookup"><span data-stu-id="04cea-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="04cea-139">Возвращает:</span><span class="sxs-lookup"><span data-stu-id="04cea-139">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="04cea-140">Доступны дополнительные методы, которые могут быть заданы во время процесса связывания.</span><span class="sxs-lookup"><span data-stu-id="04cea-140">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="04cea-141">В предыдущем примере тем не менее, минимально необходимые параметры показаны.</span><span class="sxs-lookup"><span data-stu-id="04cea-141">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="04cea-142">В следующей таблице приведены дополнительные параметры, которые можно использовать в настройке параметров для`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="04cea-142">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="04cea-143">Обязательно?</span><span class="sxs-lookup"><span data-stu-id="04cea-143">Required?</span></span>|<span data-ttu-id="04cea-144">Имя</span><span class="sxs-lookup"><span data-stu-id="04cea-144">Name</span></span>|<span data-ttu-id="04cea-145">Описание</span><span class="sxs-lookup"><span data-stu-id="04cea-145">Description</span></span>|<span data-ttu-id="04cea-146">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="04cea-146">Default</span></span>|<span data-ttu-id="04cea-147">Возможные значения</span><span class="sxs-lookup"><span data-stu-id="04cea-147">Possible values</span></span>|<span data-ttu-id="04cea-148">Тип и ограничения</span><span class="sxs-lookup"><span data-stu-id="04cea-148">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04cea-149">Да</span><span class="sxs-lookup"><span data-stu-id="04cea-149">Yes</span></span>|<span data-ttu-id="04cea-150">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="04cea-150">FQDN</span></span>|<span data-ttu-id="04cea-151">Полное ДОМЕННОЕ имя пограничного контроллера Сеансов</span><span class="sxs-lookup"><span data-stu-id="04cea-151">The FQDN name of the SBC</span></span> |<span data-ttu-id="04cea-152">Нет</span><span class="sxs-lookup"><span data-stu-id="04cea-152">None</span></span>|<span data-ttu-id="04cea-153">Имя NoneFQDN, ограничение 63 символов</span><span class="sxs-lookup"><span data-stu-id="04cea-153">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="04cea-154">Строка, список разрешенных и запрещенных символов на [соглашениях об именовании в Active Directory для компьютеров, доменов, сайты и подразделениями](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="04cea-154">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="04cea-155">Нет</span><span class="sxs-lookup"><span data-stu-id="04cea-155">No</span></span>|<span data-ttu-id="04cea-156">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="04cea-156">MediaBypass</span></span> |<span data-ttu-id="04cea-157">Параметр зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="04cea-157">The parameter reserved for future use.</span></span> <span data-ttu-id="04cea-158">Параметра, указанное для SBC поддерживает обход сервера-посредника и администратор хочет его использования.</span><span class="sxs-lookup"><span data-stu-id="04cea-158">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="04cea-159">Нет</span><span class="sxs-lookup"><span data-stu-id="04cea-159">None</span></span>|<span data-ttu-id="04cea-160">True</span><span class="sxs-lookup"><span data-stu-id="04cea-160">True</span></span><br/><span data-ttu-id="04cea-161">False</span><span class="sxs-lookup"><span data-stu-id="04cea-161">False</span></span>|<span data-ttu-id="04cea-162">Boolean</span><span class="sxs-lookup"><span data-stu-id="04cea-162">Boolean</span></span>|
|<span data-ttu-id="04cea-163">Да</span><span class="sxs-lookup"><span data-stu-id="04cea-163">Yes</span></span>|<span data-ttu-id="04cea-164">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="04cea-164">SipSignallingPort</span></span> |<span data-ttu-id="04cea-165">Прослушивающий порт, используемый для взаимодействия со службами прямой маршрутизации с помощью протокола безопасности TLS (Transport Layer).</span><span class="sxs-lookup"><span data-stu-id="04cea-165">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="04cea-166">Нет</span><span class="sxs-lookup"><span data-stu-id="04cea-166">None</span></span>|<span data-ttu-id="04cea-167">Любой порт</span><span class="sxs-lookup"><span data-stu-id="04cea-167">Any port</span></span>|<span data-ttu-id="04cea-168">от 0 до 65535</span><span class="sxs-lookup"><span data-stu-id="04cea-168">0 to 65535</span></span> |
|<span data-ttu-id="04cea-169">Нет</span><span class="sxs-lookup"><span data-stu-id="04cea-169">No</span></span>|<span data-ttu-id="04cea-170">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="04cea-170">FailoverTimeSeconds</span></span> |<span data-ttu-id="04cea-171">Если задано значение 10 (значение по умолчанию), исходящие вызовы, которые не отвечает в течение 10 секунд шлюз направляются Далее доступные линии связи; Если нет дополнительных магистралей, звонок автоматически удаляются.</span><span class="sxs-lookup"><span data-stu-id="04cea-171">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="04cea-172">В организации с медленными ответами сетей и шлюзов, это может приводить к необязательному пропуску вызовов.</span><span class="sxs-lookup"><span data-stu-id="04cea-172">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="04cea-173">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="04cea-173">The default value is 10.</span></span>|<span data-ttu-id="04cea-174">10</span><span class="sxs-lookup"><span data-stu-id="04cea-174">10</span></span>|<span data-ttu-id="04cea-175">Число</span><span class="sxs-lookup"><span data-stu-id="04cea-175">Number</span></span>|<span data-ttu-id="04cea-176">Int</span><span class="sxs-lookup"><span data-stu-id="04cea-176">Int</span></span>|
|<span data-ttu-id="04cea-177">Нет</span><span class="sxs-lookup"><span data-stu-id="04cea-177">No</span></span>|<span data-ttu-id="04cea-178">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="04cea-178">ForwardCallHistory</span></span> |<span data-ttu-id="04cea-179">Означает, будет ли переадресовываться по магистральному каналу сведения о журнале звонков.</span><span class="sxs-lookup"><span data-stu-id="04cea-179">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="04cea-180">Если этот параметр включен, прокси-сервер Office 365 ТСОП отправляет два заголовки: сведений журнала и ссылается по.</span><span class="sxs-lookup"><span data-stu-id="04cea-180">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="04cea-181">Значение по умолчанию — **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="04cea-181">The default value is **False** ($False).</span></span> |<span data-ttu-id="04cea-182">False</span><span class="sxs-lookup"><span data-stu-id="04cea-182">False</span></span>|<span data-ttu-id="04cea-183">True</span><span class="sxs-lookup"><span data-stu-id="04cea-183">True</span></span><br/><span data-ttu-id="04cea-184">False</span><span class="sxs-lookup"><span data-stu-id="04cea-184">False</span></span>|<span data-ttu-id="04cea-185">Boolean</span><span class="sxs-lookup"><span data-stu-id="04cea-185">Boolean</span></span>|
|<span data-ttu-id="04cea-186">Нет</span><span class="sxs-lookup"><span data-stu-id="04cea-186">No</span></span>|<span data-ttu-id="04cea-187">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="04cea-187">ForwardPAI</span></span>|<span data-ttu-id="04cea-188">Указывает, будет ли переадресовываться заголовок P-Asserted-Identity (PAI) одновременно с вызовом.</span><span class="sxs-lookup"><span data-stu-id="04cea-188">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="04cea-189">Заголовок PAI предоставляет способ проверки удостоверения абонемента.</span><span class="sxs-lookup"><span data-stu-id="04cea-189">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="04cea-190">Если этот параметр включен конфиденциальности: код будет отправлен заголовок.</span><span class="sxs-lookup"><span data-stu-id="04cea-190">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="04cea-191">Значение по умолчанию — **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="04cea-191">The default value is **False** ($False).</span></span>|<span data-ttu-id="04cea-192">False</span><span class="sxs-lookup"><span data-stu-id="04cea-192">False</span></span>|<span data-ttu-id="04cea-193">True</span><span class="sxs-lookup"><span data-stu-id="04cea-193">True</span></span><br/><span data-ttu-id="04cea-194">False</span><span class="sxs-lookup"><span data-stu-id="04cea-194">False</span></span>|<span data-ttu-id="04cea-195">Boolean</span><span class="sxs-lookup"><span data-stu-id="04cea-195">Boolean</span></span>|
|<span data-ttu-id="04cea-196">Нет</span><span class="sxs-lookup"><span data-stu-id="04cea-196">No</span></span>|<span data-ttu-id="04cea-197">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="04cea-197">SendSIPOptions</span></span> |<span data-ttu-id="04cea-198">Определяет, если SBC будет или не будет отправлять параметры SIP.</span><span class="sxs-lookup"><span data-stu-id="04cea-198">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="04cea-199">Если этот параметр отключен, SBC будут исключены из системы мониторинга и оповещений.</span><span class="sxs-lookup"><span data-stu-id="04cea-199">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="04cea-200">Настоятельно рекомендуется включить параметры SIP.</span><span class="sxs-lookup"><span data-stu-id="04cea-200">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="04cea-201">Значение по умолчанию — **True**.</span><span class="sxs-lookup"><span data-stu-id="04cea-201">Default value is **True**.</span></span> |<span data-ttu-id="04cea-202">True</span><span class="sxs-lookup"><span data-stu-id="04cea-202">True</span></span>|<span data-ttu-id="04cea-203">True</span><span class="sxs-lookup"><span data-stu-id="04cea-203">True</span></span><br/><span data-ttu-id="04cea-204">False</span><span class="sxs-lookup"><span data-stu-id="04cea-204">False</span></span>|<span data-ttu-id="04cea-205">Boolean</span><span class="sxs-lookup"><span data-stu-id="04cea-205">Boolean</span></span>|
|<span data-ttu-id="04cea-206">Нет</span><span class="sxs-lookup"><span data-stu-id="04cea-206">No</span></span>|<span data-ttu-id="04cea-207">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="04cea-207">MaxConcurrentSessions</span></span> |<span data-ttu-id="04cea-208">Используемый предупреждения системы.</span><span class="sxs-lookup"><span data-stu-id="04cea-208">Used by alerting system.</span></span> <span data-ttu-id="04cea-209">Если любое значение, предупреждения системы будет создать оповещение для администратора клиента, если количество одновременных сеансов является 90% или выше, чем это значение.</span><span class="sxs-lookup"><span data-stu-id="04cea-209">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="04cea-210">Если параметр не задан, оповещения не создаются.</span><span class="sxs-lookup"><span data-stu-id="04cea-210">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="04cea-211">Тем не менее система мониторинга сообщает количество одновременных сеансов каждые 24 часа.</span><span class="sxs-lookup"><span data-stu-id="04cea-211">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="04cea-212">NULL</span><span class="sxs-lookup"><span data-stu-id="04cea-212">Null</span></span>|<span data-ttu-id="04cea-213">NULL</span><span class="sxs-lookup"><span data-stu-id="04cea-213">Null</span></span><br/><span data-ttu-id="04cea-214">1 до 100 000</span><span class="sxs-lookup"><span data-stu-id="04cea-214">1 to 100,000</span></span> ||
|<span data-ttu-id="04cea-215">Нет</span><span class="sxs-lookup"><span data-stu-id="04cea-215">No</span></span>|<span data-ttu-id="04cea-216">Включено \*</span><span class="sxs-lookup"><span data-stu-id="04cea-216">Enabled\*</span></span>|<span data-ttu-id="04cea-217">Используется для включения этой SBC для исходящих звонков.</span><span class="sxs-lookup"><span data-stu-id="04cea-217">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="04cea-218">Можно использовать для временно удалить SBC в процессе обновления или во время обслуживания.</span><span class="sxs-lookup"><span data-stu-id="04cea-218">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="04cea-219">False</span><span class="sxs-lookup"><span data-stu-id="04cea-219">False</span></span>|<span data-ttu-id="04cea-220">True</span><span class="sxs-lookup"><span data-stu-id="04cea-220">True</span></span><br/><span data-ttu-id="04cea-221">False</span><span class="sxs-lookup"><span data-stu-id="04cea-221">False</span></span>|<span data-ttu-id="04cea-222">Boolean</span><span class="sxs-lookup"><span data-stu-id="04cea-222">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="04cea-223">Проверка подключения к SBC</span><span class="sxs-lookup"><span data-stu-id="04cea-223">Verify the SBC pairing</span></span> 

<span data-ttu-id="04cea-224">Проверьте подключение:</span><span class="sxs-lookup"><span data-stu-id="04cea-224">Verify the connection:</span></span> 
- <span data-ttu-id="04cea-225">Проверьте, если в списке парного SBC будет SBC.</span><span class="sxs-lookup"><span data-stu-id="04cea-225">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="04cea-226">Проверка параметров SIP.</span><span class="sxs-lookup"><span data-stu-id="04cea-226">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="04cea-227">Проверить, если SBC находится в списке парного их изготовителей</span><span class="sxs-lookup"><span data-stu-id="04cea-227">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="04cea-228">По окончании пары SBC проверки SBC присутствует в списке парного их изготовителей, выполнив следующую команду в удаленный сеанс PowerShell:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="04cea-228">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="04cea-229">Парного шлюза следует отображаются в списке, как показано в следующем примере и убедитесь, что параметр *Enabled* значение **True**.</span><span class="sxs-lookup"><span data-stu-id="04cea-229">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="04cea-230">Введите:</span><span class="sxs-lookup"><span data-stu-id="04cea-230">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="04cea-231">Которая возвращает:</span><span class="sxs-lookup"><span data-stu-id="04cea-231">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="04cea-232">Проверка потока SIP-параметры</span><span class="sxs-lookup"><span data-stu-id="04cea-232">Validate SIP Options flow</span></span> 

<span data-ttu-id="04cea-233">Для проверки связывания с помощью параметров исходящей SIP, с помощью интерфейса управления SBC и убедитесь, что SBC получает 200 OK ответы на свои исходящие сообщения параметры.</span><span class="sxs-lookup"><span data-stu-id="04cea-233">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="04cea-234">При прямой маршрутизации видит входящие параметры, он будет запущен процесс отправки исходящих SIP-сообщения, чтобы полное доменное имя пограничного контроллера Сеансов настраиваемые параметры в поле Заголовок контакт входящего сообщения, параметры.</span><span class="sxs-lookup"><span data-stu-id="04cea-234">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="04cea-235">Для проверки, с помощью параметров входящих SIP-связывания, используйте интерфейс управления SBC и увидеть, что SBC отправляет ответ на параметры сообщения, поступающие из прямой маршрутизации и код ответа, которые он отправляет равно 200 OK.</span><span class="sxs-lookup"><span data-stu-id="04cea-235">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="04cea-236">Включение пользователей для службы напрямую маршрутизации</span><span class="sxs-lookup"><span data-stu-id="04cea-236">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="04cea-237">Когда вы готовы к Включение пользователей для службы напрямую маршрутизации, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="04cea-237">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="04cea-238">Создание пользователя в Office 365 и назначьте лицензии на систему телефона.</span><span class="sxs-lookup"><span data-stu-id="04cea-238">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="04cea-239">Убедитесь, что пользователь размещенный в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="04cea-239">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="04cea-240">Настройте номер телефона и включение корпоративной голосовой связи и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="04cea-240">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="04cea-241">Настройка маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="04cea-241">Configure voice routing.</span></span> <span data-ttu-id="04cea-242">Маршрут проверяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="04cea-242">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="04cea-243">Создание пользователя в Office 365 и назначьте лицензии</span><span class="sxs-lookup"><span data-stu-id="04cea-243">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="04cea-244">Существует два варианта для создания нового пользователя в Office 365.</span><span class="sxs-lookup"><span data-stu-id="04cea-244">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="04cea-245">Тем не менее рекомендуется выбрать и использовать один из вариантов, чтобы избежать проблем с маршрутизацией вашей организации:</span><span class="sxs-lookup"><span data-stu-id="04cea-245">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="04cea-246">Создание пользователя в локальной службе Active Directory и синхронизация пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="04cea-246">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="04cea-247">В разделе [Интеграция на локальную каталогов с помощью Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="04cea-247">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="04cea-248">Создание пользователя непосредственно в портал администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="04cea-248">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="04cea-249">В разделе [Добавление пользователей по отдельности или набором для Office 365 — помощь администратора](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="04cea-249">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="04cea-250">Если ваше Скайп для бизнеса в Интернет развертывания совместного с Скайп для бизнеса 2015 или Lync 2010 или 2013 локальных, единственным вариантом поддерживаемые является создание пользователя в локальной службе Active Directory и синхронизация пользователей в облаке (вариант 1).</span><span class="sxs-lookup"><span data-stu-id="04cea-250">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="04cea-251">Необходимые лицензии:</span><span class="sxs-lookup"><span data-stu-id="04cea-251">Required licenses:</span></span> 

- <span data-ttu-id="04cea-252">Office 365 для предприятий E3 (включая SfB Plan2, Exchange Plan2 или группам) телефона системы</span><span class="sxs-lookup"><span data-stu-id="04cea-252">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="04cea-253">Office 365 корпоративный E5 (включая SfB Plan2, Exchange Plan2, групп и телефонной системой)</span><span class="sxs-lookup"><span data-stu-id="04cea-253">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="04cea-254">Необязательный лицензии:</span><span class="sxs-lookup"><span data-stu-id="04cea-254">Optional licenses:</span></span> 

- <span data-ttu-id="04cea-255">Вызов плана</span><span class="sxs-lookup"><span data-stu-id="04cea-255">Calling Plan</span></span> 
- <span data-ttu-id="04cea-256">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="04cea-256">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="04cea-257">Пользователь является, размещенными в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="04cea-257">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="04cea-258">Прямое маршрутизации требует от пользователя быть размещен в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="04cea-258">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="04cea-259">Вы можете проверить, посмотрев параметр RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="04cea-259">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="04cea-260">Он должен иметь значение в домене infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="04cea-260">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="04cea-261">Подключение к удаленной оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04cea-261">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="04cea-262">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="04cea-262">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="04cea-263">Настройка номер телефона и включение корпоративной голосовой связи и голосовая почта</span><span class="sxs-lookup"><span data-stu-id="04cea-263">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="04cea-264">После создания пользователя и назначена лицензия, следующим шагом является настройка их номер телефона и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="04cea-264">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="04cea-265">Это можно сделать в одном шаге.</span><span class="sxs-lookup"><span data-stu-id="04cea-265">This can be done in one step.</span></span> 

<span data-ttu-id="04cea-266">Чтобы добавить номер телефона и включить для голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="04cea-266">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="04cea-267">Подключение удаленного сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04cea-267">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="04cea-268">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="04cea-268">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="04cea-269">Например чтобы добавить номер телефона для пользователя «Иван низкий», необходимо ввести следующее:</span><span class="sxs-lookup"><span data-stu-id="04cea-269">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="04cea-270">Номер телефона должен быть настроен как полный номер телефона E.164 с код страны.</span><span class="sxs-lookup"><span data-stu-id="04cea-270">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="04cea-271">Если номер телефона пользователя управляется локально, используется для настройки номер телефона пользователя в локальной Скайп для бизнеса командную консоль или панель управления.</span><span class="sxs-lookup"><span data-stu-id="04cea-271">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="04cea-272">Настройка маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="04cea-272">Configure Voice Routing</span></span> 

<span data-ttu-id="04cea-273">Microsoft телефонной системой имеет маршрутизации механизм, позволяющий звонка для отправки определенных SBC на основе:</span><span class="sxs-lookup"><span data-stu-id="04cea-273">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="04cea-274">Вызов шаблон номера</span><span class="sxs-lookup"><span data-stu-id="04cea-274">Called number pattern</span></span> 
- <span data-ttu-id="04cea-275">Вызов шаблон номера + определенного пользователя, который делает вызов</span><span class="sxs-lookup"><span data-stu-id="04cea-275">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="04cea-276">SBC могут быть обозначены как активных и резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="04cea-276">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="04cea-277">Который означает, что при недоступности SBC, настроенный как активных этот шаблон номера или шаблон номера + определенного пользователя, а затем звонки будут перенаправляться к резервного копирования SBC.</span><span class="sxs-lookup"><span data-stu-id="04cea-277">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="04cea-278">Маршрутизация звонков состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="04cea-278">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="04cea-279">Политика маршрутизации голосовой связи — контейнер для использования ТСОП; можно назначить пользователю или нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="04cea-279">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="04cea-280">Режимы работы с ТСОП — контейнер для маршрутов голосовых вызовов и использования ТСОП; можно совместно в различные политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="04cea-280">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="04cea-281">Маршруты – шаблон номера и набор Online шлюзы ТСОП, используемый для вызовов, где номер соответствует шаблону голосовой связи</span><span class="sxs-lookup"><span data-stu-id="04cea-281">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="04cea-282">Online шлюза ТСОП - указатель SBC, также хранится конфигурация, которая применяется при звонок с помощью SBC, например переадресации P-Asserted-Identity (PAI) или предпочитаемое кодеков; можно добавить в маршрутов голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="04cea-282">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="04cea-283">Создание политики маршрутизации голосовых данных с помощью одного работы с ТСОП</span><span class="sxs-lookup"><span data-stu-id="04cea-283">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="04cea-284">На следующей схеме показана два примера политики маршрутизации голосовых данных в поток вызовов.</span><span class="sxs-lookup"><span data-stu-id="04cea-284">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="04cea-285">**Вызова потока 1 (слева):** Если пользователь совершает вызов +1 425 XXX XX XX или +1 206 XXX XX XX, звонок перенаправляется в SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="04cea-285">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="04cea-286">Если ни sbc1.contoso.biz, ни sbc2.contoso.biz недоступен, вызов отклоняется.</span><span class="sxs-lookup"><span data-stu-id="04cea-286">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="04cea-287">**Вызова поток 2 (справа):** Если пользователь совершает вызов +1 425 XXX XX XX или +1 206 XXX XX XX, вызов сначала перенаправляется в SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="04cea-287">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="04cea-288">Если ни один из SBC доступен, маршрут с низким приоритетом будет предпринята попытка (sbc3.contoso.biz и sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="04cea-288">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="04cea-289">Если ни один из их изготовителей недоступен, вызов отклоняется.</span><span class="sxs-lookup"><span data-stu-id="04cea-289">If none of the SBCs are available, the call is dropped.</span></span> 

![Показаны примеры политики маршрутизации голосовой связи](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="04cea-291">В обоих примерах пока маршрута голосовых вызовов назначается приоритеты, их изготовителей в маршруты проверяются в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="04cea-291">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="04cea-292">Если у пользователя также нет лицензии Майкрософт вызов планирование, звонков на любое число, кроме номеров, соответствующих шаблонов +1 425 XXX XX XX или +1 206 XXX XX XX в пример конфигурации удаляются.</span><span class="sxs-lookup"><span data-stu-id="04cea-292">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="04cea-293">Если у пользователя есть вызов планирование лицензии, звонок автоматически маршрутизируются в соответствии с политики в планирование вызов Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04cea-293">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="04cea-294">Планирование вызов Microsoft автоматически в качестве последнего маршрута применяется ко всем пользователям с лицензией Microsoft вызов планирование и не требует дополнительных вызовов конфигурации маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="04cea-294">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="04cea-295">В примере показано на следующей схеме голосового маршрута добавляется для направления вызовов на всех других США и Канада номер (вызовы, которые будут входить называемое шаблон номера + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="04cea-295">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Показывает маршрутизации политики третий маршрут голосовой связи](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="04cea-297">Если пользователь имеет обе лицензии (Microsoft телефонной системой и вызов планирование Microsoft), для всех других вызовов используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="04cea-297">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="04cea-298">Если ничего не соответствует шаблоны номеров в созданное администратором online маршруты голосовой связи, маршрут с помощью вызова планирование Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04cea-298">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="04cea-299">Если у пользователя есть только телефонной системой Microsoft, вызов отклоняется из-за соответствующие правила.</span><span class="sxs-lookup"><span data-stu-id="04cea-299">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="04cea-300">Значение приоритета для маршрута «Другие + 1» не имеет значения, таким образом, как это делается только один маршрут, который соответствует шаблону + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="04cea-300">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="04cea-301">Если пользователь выполняет запрос 89 89 567 324 + 1 и sbc5.contoso.biz и sbc6.contoso.biz недоступны, вызов отклоняется.</span><span class="sxs-lookup"><span data-stu-id="04cea-301">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="04cea-302">В следующей таблице обобщаются конфигурации, используя три маршруты голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="04cea-302">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="04cea-303">В этом примере все три маршруты являются частью одной работы с ТСОП «"Мне Нравится" и Canada».</span><span class="sxs-lookup"><span data-stu-id="04cea-303">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="04cea-304">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="04cea-304">**PSTN usage**</span></span>|<span data-ttu-id="04cea-305">**Маршрут голосовых вызовов**</span><span class="sxs-lookup"><span data-stu-id="04cea-305">**Voice route**</span></span>|<span data-ttu-id="04cea-306">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="04cea-306">**Number pattern**</span></span>|<span data-ttu-id="04cea-307">**Priority**</span><span class="sxs-lookup"><span data-stu-id="04cea-307">**Priority**</span></span>|<span data-ttu-id="04cea-308">**SBC**</span><span class="sxs-lookup"><span data-stu-id="04cea-308">**SBC**</span></span>|<span data-ttu-id="04cea-309">**Описание**</span><span class="sxs-lookup"><span data-stu-id="04cea-309">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04cea-310">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="04cea-310">US only</span></span>|<span data-ttu-id="04cea-311">«Redmond 1»</span><span class="sxs-lookup"><span data-stu-id="04cea-311">"Redmond 1"</span></span>|<span data-ttu-id="04cea-312">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="04cea-312">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="04cea-313">1</span><span class="sxs-lookup"><span data-stu-id="04cea-313">1</span></span>|<span data-ttu-id="04cea-314">sbc1.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-314">sbc1.contoso.biz</span></span><br/><span data-ttu-id="04cea-315">sbc2.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-315">sbc2.contoso.biz</span></span>|<span data-ttu-id="04cea-316">Active маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="04cea-316">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="04cea-317">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="04cea-317">US only</span></span>|<span data-ttu-id="04cea-318">«Redmond 2»</span><span class="sxs-lookup"><span data-stu-id="04cea-318">"Redmond 2"</span></span>|<span data-ttu-id="04cea-319">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="04cea-319">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="04cea-320">2</span><span class="sxs-lookup"><span data-stu-id="04cea-320">2</span></span>|<span data-ttu-id="04cea-321">sbc3.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-321">sbc3.contoso.biz</span></span><br/><span data-ttu-id="04cea-322">sbc4.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-322">sbc4.contoso.biz</span></span>|<span data-ttu-id="04cea-323">Резервного копирования маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="04cea-323">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="04cea-324">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="04cea-324">US only</span></span>|<span data-ttu-id="04cea-325">«Другие + 1»</span><span class="sxs-lookup"><span data-stu-id="04cea-325">"Other +1"</span></span>|<span data-ttu-id="04cea-326">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="04cea-326">^\\+1(\d{10})$</span></span>|<span data-ttu-id="04cea-327">3</span><span class="sxs-lookup"><span data-stu-id="04cea-327">3</span></span>|<span data-ttu-id="04cea-328">sbc5.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-328">sbc5.contoso.biz</span></span><br/><span data-ttu-id="04cea-329">sbc6.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-329">sbc6.contoso.biz</span></span>|<span data-ttu-id="04cea-330">Маршрут для вызываемого номера + 1 XXX XXX XX XX (за исключением +1 425 XXX XX XX или +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="04cea-330">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="04cea-331">Всех маршрутов, связанных с работы с ТСОП «"Мне Нравится" и Canada» и об использовании PSTN связан с политики маршрутизации голосовой связи «Только для США».</span><span class="sxs-lookup"><span data-stu-id="04cea-331">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="04cea-332">В этом примере назначается пользователю Spencer Low политику маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="04cea-332">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="04cea-333">Примеры маршрутов звонков</span><span class="sxs-lookup"><span data-stu-id="04cea-333">Examples of call routes</span></span>

<span data-ttu-id="04cea-334">В следующем примере мы показываем, как Настройка политики маршрутизации, использования ТСОП и маршрутов и назначить политику для пользователя.</span><span class="sxs-lookup"><span data-stu-id="04cea-334">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="04cea-335">**Шаг 1:** Создайте работы с ТСОП «США и Канада».</span><span class="sxs-lookup"><span data-stu-id="04cea-335">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="04cea-336">В поле Скайп для сеанса удаленной оболочки PowerShell бизнеса введите:</span><span class="sxs-lookup"><span data-stu-id="04cea-336">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="04cea-337">Проверка создания посредством ввода данных об использовании.</span><span class="sxs-lookup"><span data-stu-id="04cea-337">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="04cea-338">Которого возвращается список имен, которые может усекаться:</span><span class="sxs-lookup"><span data-stu-id="04cea-338">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="04cea-339">В приведенном ниже примере можно увидеть результат выполнения команды PowerShell `(Get-CSOnlinePSTNUsage).usage` Отображение полного названия (не сокращается).</span><span class="sxs-lookup"><span data-stu-id="04cea-339">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

<span data-ttu-id="04cea-340">**Шаг 2:** В сеанс PowerShell в Скайп для бизнеса в Интернет, создайте три маршрутов: Redmond 1, Redmond 2 и других + 1, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="04cea-340">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="04cea-341">Чтобы создать маршрут «Redmond 1», введите:</span><span class="sxs-lookup"><span data-stu-id="04cea-341">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="04cea-342">Которая возвращает:</span><span class="sxs-lookup"><span data-stu-id="04cea-342">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
<span data-ttu-id="04cea-343">Чтобы создать маршрут Redmond 2, введите:</span><span class="sxs-lookup"><span data-stu-id="04cea-343">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="04cea-344">Чтобы создать маршрутом + 1, введите:</span><span class="sxs-lookup"><span data-stu-id="04cea-344">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="04cea-345">Убедитесь в том, что регулярное выражение в качестве атрибута переменной NumberPattern является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="04cea-345">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="04cea-346">Вы можете проверить ее с помощью этой веб-сайта:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="04cea-346">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="04cea-347">В некоторых случаях нет необходимости все вызовы направляются в одном SBC; Используйте - переменной NumberPattern «. \*»</span><span class="sxs-lookup"><span data-stu-id="04cea-347">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="04cea-348">Маршрутизировать вызовы все же SBC</span><span class="sxs-lookup"><span data-stu-id="04cea-348">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="04cea-349">Проверьте, что правильно настроены маршрут, выполнив `Get-CSOnlineVoiceRoute` команду PowerShell с помощью параметров, как показано:</span><span class="sxs-lookup"><span data-stu-id="04cea-349">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="04cea-350">Которого должен возвращать:</span><span class="sxs-lookup"><span data-stu-id="04cea-350">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="04cea-351">В примере, маршрут «Другие + 1» автоматически была назначена приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="04cea-351">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="04cea-352">**Шаг 3:** Создание политики маршрутизации голосовой связи «"мне НРАВИТСЯ" только» и добавить в политику работы с ТСОП «США и Канада.»</span><span class="sxs-lookup"><span data-stu-id="04cea-352">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="04cea-353">В сеанс PowerShell в Скайп для бизнеса в Интернет введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="04cea-353">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="04cea-354">В этом примере показан результат.</span><span class="sxs-lookup"><span data-stu-id="04cea-354">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="04cea-355">**Шаг 4:** Предоставление пользователю Spencer Low политики маршрутизации голосовых данных с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04cea-355">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="04cea-356">В сеанс PowerShell в Скайп для бизнеса в Интернет введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="04cea-356">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="04cea-357">Проверка назначения политики, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="04cea-357">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="04cea-358">Которая возвращает:</span><span class="sxs-lookup"><span data-stu-id="04cea-358">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="04cea-359">Создание политики маршрутизации голосовой связи с несколькими случаев использования PSTN</span><span class="sxs-lookup"><span data-stu-id="04cea-359">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="04cea-360">Политику маршрутизации голосовой связи, созданную ранее допускает только вызовы на телефонные номера в США и Канада — Если не лицензии Майкрософт вызов планирование также назначается пользователю.</span><span class="sxs-lookup"><span data-stu-id="04cea-360">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="04cea-361">В этом примере создаются политики маршрутизации голосовой связи «Без ограничений».</span><span class="sxs-lookup"><span data-stu-id="04cea-361">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="04cea-362">Политики повторно использует режим работы с ТСОП «"Мне Нравится" и Canada» создан в предыдущем примере, а также новые работы с ТСОП «International».</span><span class="sxs-lookup"><span data-stu-id="04cea-362">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="04cea-363">Это направляет все вызовы для их изготовителей sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="04cea-363">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="04cea-364">Представлены примеры назначение политики "мне Нравится" только для пользователя «Иван низкий» и нет ограничений пользователя «John Woods».</span><span class="sxs-lookup"><span data-stu-id="04cea-364">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="04cea-365">Spencer Low — допускается только в США и Канада числа звонков.</span><span class="sxs-lookup"><span data-stu-id="04cea-365">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="04cea-366">При вызове диапазон номеров Redmond, необходимо использовать определенный набор SBC.</span><span class="sxs-lookup"><span data-stu-id="04cea-366">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="04cea-367">Номера не в США не будут направляться, если вызов планирование лицензия назначена для пользователя.</span><span class="sxs-lookup"><span data-stu-id="04cea-367">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="04cea-368">Джон Вудз – звонки могут любое число.</span><span class="sxs-lookup"><span data-stu-id="04cea-368">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="04cea-369">При вызове диапазон номеров Redmond, необходимо использовать определенный набор SBC.</span><span class="sxs-lookup"><span data-stu-id="04cea-369">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="04cea-370">Не в США номера будут направляться через sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="04cea-370">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Отображает политику маршрутизации голосовой связи, назначенной пользователю Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="04cea-372">Если пользователь имеет обе лицензии (Microsoft телефонной системой и вызов планирование Microsoft), для всех других вызовов используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="04cea-372">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="04cea-373">Если ничего не соответствует шаблоны номеров в созданное администратором online маршруты голосовой связи, маршрут с помощью вызова планирование Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04cea-373">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="04cea-374">Если у пользователя есть только телефонной системой Microsoft, вызов отклоняется из-за соответствующие правила.</span><span class="sxs-lookup"><span data-stu-id="04cea-374">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Отображает политику маршрутизации голосовой связи, назначенные для пользователя John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="04cea-376">В следующей таблице перечислены маршрутизации сообщений об использовании «Без ограничения» политики и маршруты голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="04cea-376">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="04cea-377">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="04cea-377">**PSTN usage**</span></span>|<span data-ttu-id="04cea-378">**Маршрут голосовых вызовов**</span><span class="sxs-lookup"><span data-stu-id="04cea-378">**Voice route**</span></span>|<span data-ttu-id="04cea-379">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="04cea-379">**Number pattern**</span></span>|<span data-ttu-id="04cea-380">**Priority**</span><span class="sxs-lookup"><span data-stu-id="04cea-380">**Priority**</span></span>|<span data-ttu-id="04cea-381">**SBC**</span><span class="sxs-lookup"><span data-stu-id="04cea-381">**SBC**</span></span>|<span data-ttu-id="04cea-382">**Описание**</span><span class="sxs-lookup"><span data-stu-id="04cea-382">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04cea-383">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="04cea-383">US Only</span></span>|<span data-ttu-id="04cea-384">«Redmond 1»</span><span class="sxs-lookup"><span data-stu-id="04cea-384">"Redmond 1"</span></span>|<span data-ttu-id="04cea-385">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="04cea-385">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="04cea-386">1</span><span class="sxs-lookup"><span data-stu-id="04cea-386">1</span></span>|<span data-ttu-id="04cea-387">sbc1.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-387">sbc1.contoso.biz</span></span><br/><span data-ttu-id="04cea-388">sbc2.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-388">sbc2.contoso.biz</span></span>|<span data-ttu-id="04cea-389">Active маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="04cea-389">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="04cea-390">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="04cea-390">US Only</span></span>|<span data-ttu-id="04cea-391">«Redmond 2»</span><span class="sxs-lookup"><span data-stu-id="04cea-391">"Redmond 2"</span></span>|<span data-ttu-id="04cea-392">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="04cea-392">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="04cea-393">2</span><span class="sxs-lookup"><span data-stu-id="04cea-393">2</span></span>|<span data-ttu-id="04cea-394">sbc3.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-394">sbc3.contoso.biz</span></span><br/><span data-ttu-id="04cea-395">sbc4.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-395">sbc4.contoso.biz</span></span>|<span data-ttu-id="04cea-396">Резервного копирования маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="04cea-396">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="04cea-397">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="04cea-397">US Only</span></span>|<span data-ttu-id="04cea-398">«Другие + 1»</span><span class="sxs-lookup"><span data-stu-id="04cea-398">"Other +1"</span></span>|<span data-ttu-id="04cea-399">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="04cea-399">^\\+1(\d{10})$</span></span>|<span data-ttu-id="04cea-400">3</span><span class="sxs-lookup"><span data-stu-id="04cea-400">3</span></span>|<span data-ttu-id="04cea-401">sbc5.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-401">sbc5.contoso.biz</span></span><br/><span data-ttu-id="04cea-402">sbc6>.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-402">sbc6>.contoso.biz</span></span>|<span data-ttu-id="04cea-403">Маршрут для вызываемого номера + 1 XXX XXX XX XX (за исключением +1 425 XXX XX XX или +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="04cea-403">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="04cea-404">International</span><span class="sxs-lookup"><span data-stu-id="04cea-404">International</span></span>|<span data-ttu-id="04cea-405">International</span><span class="sxs-lookup"><span data-stu-id="04cea-405">International</span></span>|<span data-ttu-id="04cea-406">\d+</span><span class="sxs-lookup"><span data-stu-id="04cea-406">\d+</span></span>|<span data-ttu-id="04cea-407">4</span><span class="sxs-lookup"><span data-stu-id="04cea-407">4</span></span>|<span data-ttu-id="04cea-408">sbc2.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-408">sbc2.contoso.biz</span></span><br/><span data-ttu-id="04cea-409">sbc5.contoso.Biz</span><span class="sxs-lookup"><span data-stu-id="04cea-409">sbc5.contoso.biz</span></span>|<span data-ttu-id="04cea-410">Маршрут для любой шаблон номера</span><span class="sxs-lookup"><span data-stu-id="04cea-410">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="04cea-411">Порядок использования ТСОП в политики маршрутизации голосовой связи крайне важна.</span><span class="sxs-lookup"><span data-stu-id="04cea-411">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="04cea-412">Примеры использования применяются в порядке, а если совпадение найдено при первом использовании, затем другие режимы работы с никогда не применяются.</span><span class="sxs-lookup"><span data-stu-id="04cea-412">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="04cea-413">Режим работы с ТСОП «International» должны быть введены после работы с ТСОП «"мне НРАВИТСЯ" только.»</span><span class="sxs-lookup"><span data-stu-id="04cea-413">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="04cea-414">Чтобы изменить порядок использования ТСОП, запустите `Set-CSOnlineVoiceRoutingPolicy` команды.</span><span class="sxs-lookup"><span data-stu-id="04cea-414">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="04cea-415">Например, чтобы изменить порядок «США и Канады» выполните первый и «Международный» секунды в порядке, обратном порядку:</span><span class="sxs-lookup"><span data-stu-id="04cea-415">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="04cea-416">Автоматически назначаются приоритет маршруты голосовой связи «International» и «Другие + 1».</span><span class="sxs-lookup"><span data-stu-id="04cea-416">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="04cea-417">Они не имеет значения, поскольку они имеют более низкими приоритетами чем «Redmond 1» и «Redmond 2».</span><span class="sxs-lookup"><span data-stu-id="04cea-417">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="04cea-418">Пример политики маршрутизации голосовой связи для пользователя John Woods</span><span class="sxs-lookup"><span data-stu-id="04cea-418">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="04cea-419">Политики маршрутизации «Нет ограничений,» голосовой маршрут «International» голосовой связи действия по созданию работы с ТСОП «International», и назначение пользователя «John Woods» выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="04cea-419">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="04cea-420">Во-первых создайте работы с ТСОП «International».</span><span class="sxs-lookup"><span data-stu-id="04cea-420">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="04cea-421">В удаленный сеанс PowerShell в Скайп для бизнеса в Интернет введите:</span><span class="sxs-lookup"><span data-stu-id="04cea-421">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="04cea-422">Создайте новый маршрут голосовой связи «International».</span><span class="sxs-lookup"><span data-stu-id="04cea-422">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="04cea-423">Которая возвращает:</span><span class="sxs-lookup"><span data-stu-id="04cea-423">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SuppressCallerId          :
   AlternateCallerId         :
   </pre>
3. <span data-ttu-id="04cea-424">Создайте политику маршрутизации голосовой связи «Без ограничений».</span><span class="sxs-lookup"><span data-stu-id="04cea-424">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="04cea-425">Режим работы с ТСОП «Redmond 1» и «Redmond» используются повторно в политике маршрутизации голосовой связи, чтобы сохранить специальная обработка звонков на номер «+1 425 XXX XX XX» и «+1 206 XXX XX XX» как локальная или локальных вызовов.</span><span class="sxs-lookup"><span data-stu-id="04cea-425">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="04cea-426">Которая возвращает</span><span class="sxs-lookup"><span data-stu-id="04cea-426">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="04cea-427">Назначение политики маршрутизации голосовой связи для пользователя «John Woods» с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="04cea-427">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="04cea-428">Затем проверьте назначения, с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="04cea-428">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="04cea-429">Которая возвращает:</span><span class="sxs-lookup"><span data-stu-id="04cea-429">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="04cea-430">Результатом является не ограничено политика голосовой связи, применяются к вызовам, Джон Вудз и выполним логику маршрутизации вызовов для США, Канада и международных звонков.</span><span class="sxs-lookup"><span data-stu-id="04cea-430">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="04cea-431">Установка группами Майкрософт по предпочитаемый вызывающего клиента для пользователей</span><span class="sxs-lookup"><span data-stu-id="04cea-431">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="04cea-432">Прямое маршрутизации только маршруты звонки в и из него пользователей при использовании команды клиента.</span><span class="sxs-lookup"><span data-stu-id="04cea-432">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="04cea-433">Если ваша организация использует только группы, параметр «Только для команды» режим в политике обновления рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="04cea-433">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="04cea-434">Если ваша организация использует Скайп для Business Server или Скайп для бизнеса в Интернет, обратитесь к следующей статье для получения дополнительных сведений и выберите соответствующий параметр: [понять сосуществования и обновление пути для Скайп для бизнеса и рабочих групп](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="04cea-434">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="04cea-435">См. также</span><span class="sxs-lookup"><span data-stu-id="04cea-435">See also</span></span>

[<span data-ttu-id="04cea-436">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="04cea-436">Plan Direct Routing</span></span>](direct-routing-plan.md)
