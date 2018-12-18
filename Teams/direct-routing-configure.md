---
title: Настройка прямой маршрутизации
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Сведения о настройке Microsoft телефонной системы прямой маршрутизации.
ms.openlocfilehash: cf856989cd4f87f4b46e1eb36cbeb403bf92b029
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297913"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="77801-103">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="77801-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="77801-104">Просмотрите следующие сеанса, чтобы узнать о преимуществах прямой маршрутизации, как спланировать его и способе развертывания: [Прямой маршрутизации в группах Майкрософт](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="77801-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="77801-105">Если вы еще не сделали прочитайте [Планирование прямой маршрутизации](direct-routing-plan.md) наличие необходимых компонентов и просмотреть другие действия необходимо выполнить перед настройкой сети Microsoft телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="77801-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review  other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="77801-106">В этой статье описывается настройка прямой маршрутизации Microsoft телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="77801-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="77801-107">Описывается, как связать поддерживаемые пограничный контроллер сеансов (SBC) для прямой маршрутизации и способы настройки групп Майкрософт пользователям использовать прямой маршрутизации для подключения к общедоступной переключения телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="77801-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="77801-108">Для выполнения действий, описанных в данной статье, администраторы должны знакомы с командлеты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77801-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="77801-109">Дополнительные сведения об использовании PowerShell в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="77801-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="77801-110">Рекомендуется, чтобы подтвердить, что пограничного контроллера Сеансов уже настроен соответствии с рекомендациями по своему поставщику SBC:</span><span class="sxs-lookup"><span data-stu-id="77801-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor's:</span></span> 

- [<span data-ttu-id="77801-111">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="77801-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="77801-112">Лента Communications документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="77801-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="77801-113">Можно настроить телефонной системой Microsoft и пользователи могли использовать прямой маршрутизации, а затем настроить группами Майкрософт как предпочитаемый вызывающего клиента, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="77801-113">You can configure your Microsoft Phone System and enable  users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="77801-114">Пары SBC с телефонной системы Microsoft и проверки связывания</span><span class="sxs-lookup"><span data-stu-id="77801-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="77801-115">Включение пользователей для службы напрямую маршрутизации</span><span class="sxs-lookup"><span data-stu-id="77801-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="77801-116">Убедитесь, что группами Майкрософт является предпочтительным вызывающего клиента для пользователей</span><span class="sxs-lookup"><span data-stu-id="77801-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a><span data-ttu-id="77801-117">Пары SBC для направления маршрутизации службы телефонной системой</span><span class="sxs-lookup"><span data-stu-id="77801-117">Pair the SBC to Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="77801-118">Ниже приведены три основных действия можно подключиться или пары SBC интерфейс прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="77801-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="77801-119">Подключение к центру администрирования **Скайп для бизнеса в Интернет** , с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="77801-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="77801-120">Пара SBC</span><span class="sxs-lookup"><span data-stu-id="77801-120">Pair the SBC</span></span> 
- <span data-ttu-id="77801-121">Проверка сопоставления</span><span class="sxs-lookup"><span data-stu-id="77801-121">Validate the pairing</span></span> 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a><span data-ttu-id="77801-122">Подключение к Скайп для бизнеса в Интернет с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="77801-122">Connect to  Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="77801-123">Можно использовать сеанс PowerShell, подключенных к клиенту связать SBC интерфейс прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="77801-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="77801-124">Чтобы открыть сеанс PowerShell, выполните действия, указанные в [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="77801-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="77801-125">После создания удаленного сеанса PowerShell, проверьте, что вы видите команды для управления SBC.</span><span class="sxs-lookup"><span data-stu-id="77801-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="77801-126">Для проверки команды, введите или копирование и вставка в следующем в сеанс PowerShell и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="77801-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
gcm *onlinePSTNGateway*
```

<span data-ttu-id="77801-127">Команда вернет четыре функций, которые будут позволяют управлять их изготовителей.</span><span class="sxs-lookup"><span data-stu-id="77801-127">Your command will return the four functions shown here that will let you manage the SBCs.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="77801-128">Пара SBC к клиенту</span><span class="sxs-lookup"><span data-stu-id="77801-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="77801-129">Связать SBC к клиенту в сеанс PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="77801-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="77801-130">Мы настоятельно рекомендуем Установка ограничения для SBC, с помощью сведений, можно найти в документации по SBC.</span><span class="sxs-lookup"><span data-stu-id="77801-130">We highly recommend setting a limit for the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="77801-131">Ограничение запустит уведомление, если SBC был создан на уровне мощности.</span><span class="sxs-lookup"><span data-stu-id="77801-131">The limit will trigger a notification if SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="77801-132">Вы можете только обеспечить SBC с полным доменным ИМЕНЕМ, где домен часть имени соответствует одной из доменов, зарегистрированных в клиенту, за исключением \*. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="77801-132">You can only pair the SBC with FQDN, where the domain portion of the name matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="77801-133">С помощью \*. omicrosoft.com доменных имен не поддерживается для имен SBC полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="77801-133">Using \*.omicrosoft.com domain names is not supported for the SBC FQDN names.</span></span> <span data-ttu-id="77801-134">Например, если у вас есть два доменных имен:</span><span class="sxs-lookup"><span data-stu-id="77801-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="77801-135">**Contoso**.com</span><span class="sxs-lookup"><span data-stu-id="77801-135">**contoso**.com</span></span><br/><span data-ttu-id="77801-136">**Contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="77801-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="77801-137">Для имени SBC можно использовать имя sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="77801-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="77801-138">При попытке связать SBC с именем sbc.contoso.abc, система не позволит вам, как домен не принадлежит этот клиент.</span><span class="sxs-lookup"><span data-stu-id="77801-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="77801-139">Возвращает:</span><span class="sxs-lookup"><span data-stu-id="77801-139">Returns:</span></span>
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
<span data-ttu-id="77801-140">Доступны дополнительные методы, которые могут быть заданы во время связывания.</span><span class="sxs-lookup"><span data-stu-id="77801-140">There are additional options that can be set during the pairing.</span></span> <span data-ttu-id="77801-141">В предыдущем примере тем не менее, минимально необходимые параметры показаны.</span><span class="sxs-lookup"><span data-stu-id="77801-141">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="77801-142">В следующей таблице перечислены дополнительные параметры, которые можно использовать в настройке параметров для *New-CsOnlinePstnGateway*.</span><span class="sxs-lookup"><span data-stu-id="77801-142">The following table lists the additional parameters that you can use in setting parameters for *New-CsOnlinePstnGateway*.</span></span> 

|<span data-ttu-id="77801-143">Обязательно?</span><span class="sxs-lookup"><span data-stu-id="77801-143">Required?</span></span>|<span data-ttu-id="77801-144">Имя</span><span class="sxs-lookup"><span data-stu-id="77801-144">Name</span></span>|<span data-ttu-id="77801-145">Описание</span><span class="sxs-lookup"><span data-stu-id="77801-145">Description</span></span>|<span data-ttu-id="77801-146">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="77801-146">Default</span></span>|<span data-ttu-id="77801-147">Возможные значения</span><span class="sxs-lookup"><span data-stu-id="77801-147">Possible values</span></span>|<span data-ttu-id="77801-148">Тип и ограничения</span><span class="sxs-lookup"><span data-stu-id="77801-148">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="77801-149">Да</span><span class="sxs-lookup"><span data-stu-id="77801-149">Yes</span></span>|<span data-ttu-id="77801-150">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="77801-150">FQDN</span></span>|<span data-ttu-id="77801-151">Полное ДОМЕННОЕ имя пограничного контроллера Сеансов</span><span class="sxs-lookup"><span data-stu-id="77801-151">The FQDN name of the SBC</span></span> |<span data-ttu-id="77801-152">Нет</span><span class="sxs-lookup"><span data-stu-id="77801-152">None</span></span>|<span data-ttu-id="77801-153">Имя NoneFQDN, ограничение 63 символов</span><span class="sxs-lookup"><span data-stu-id="77801-153">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="77801-154">Строка, список разрешенных и запрещенных символов на [соглашениях об именовании в Active Directory для компьютеров, доменов, сайты и подразделениями](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="77801-154">String,  list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="77801-155">Нет</span><span class="sxs-lookup"><span data-stu-id="77801-155">No</span></span>|<span data-ttu-id="77801-156">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="77801-156">MediaBypass</span></span> |<span data-ttu-id="77801-157">Параметр зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="77801-157">The parameter reserved for future use.</span></span> <span data-ttu-id="77801-158">Параметра, указанное для SBC поддерживает обход сервера-посредника и администратор хочет его использования.</span><span class="sxs-lookup"><span data-stu-id="77801-158">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="77801-159">Нет</span><span class="sxs-lookup"><span data-stu-id="77801-159">None</span></span>|<span data-ttu-id="77801-160">True</span><span class="sxs-lookup"><span data-stu-id="77801-160">True</span></span><br/><span data-ttu-id="77801-161">False</span><span class="sxs-lookup"><span data-stu-id="77801-161">False</span></span>|<span data-ttu-id="77801-162">Логическое</span><span class="sxs-lookup"><span data-stu-id="77801-162">Boolean</span></span>|
|<span data-ttu-id="77801-163">Да</span><span class="sxs-lookup"><span data-stu-id="77801-163">Yes</span></span>|<span data-ttu-id="77801-164">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="77801-164">SipSignallingPort</span></span> |<span data-ttu-id="77801-165">Прослушивающий порт, используемый для взаимодействия со службами прямой маршрутизации с помощью протокола безопасности TLS (Transport Layer).</span><span class="sxs-lookup"><span data-stu-id="77801-165">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="77801-166">Нет</span><span class="sxs-lookup"><span data-stu-id="77801-166">None</span></span>|<span data-ttu-id="77801-167">Любой порт</span><span class="sxs-lookup"><span data-stu-id="77801-167">Any port</span></span>|<span data-ttu-id="77801-168">от 0 до 65535</span><span class="sxs-lookup"><span data-stu-id="77801-168">0 to 65535</span></span> |
|<span data-ttu-id="77801-169">Нет</span><span class="sxs-lookup"><span data-stu-id="77801-169">No</span></span>|<span data-ttu-id="77801-170">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="77801-170">FailoverTimeSeconds</span></span> |<span data-ttu-id="77801-171">Если задано значение 10 (значение по умолчанию), исходящие вызовы, которые не отвечает в течение 10 секунд шлюз направляются Далее доступные линии связи; Если нет дополнительных магистралей, звонок автоматически удаляются.</span><span class="sxs-lookup"><span data-stu-id="77801-171">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="77801-172">В организации с медленными ответами сетей и шлюзов, это может приводить к необязательному пропуску вызовов.</span><span class="sxs-lookup"><span data-stu-id="77801-172">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="77801-173">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="77801-173">The default value is 10.</span></span>|<span data-ttu-id="77801-174"> 10</span><span class="sxs-lookup"><span data-stu-id="77801-174">10</span></span>|<span data-ttu-id="77801-175">Число</span><span class="sxs-lookup"><span data-stu-id="77801-175">Number</span></span>|<span data-ttu-id="77801-176">Int</span><span class="sxs-lookup"><span data-stu-id="77801-176">Int</span></span>|
|<span data-ttu-id="77801-177">Нет</span><span class="sxs-lookup"><span data-stu-id="77801-177">No</span></span>|<span data-ttu-id="77801-178">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="77801-178">ForwardCallHistory</span></span> |<span data-ttu-id="77801-179">Означает, будет ли переадресовываться по магистральному каналу сведения о журнале звонков.</span><span class="sxs-lookup"><span data-stu-id="77801-179">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="77801-180">Если этот параметр включен, прокси-сервер Office 365 ТСОП отправляет два заголовки: сведений журнала и ссылается по.</span><span class="sxs-lookup"><span data-stu-id="77801-180">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="77801-181">Значение по умолчанию — **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="77801-181">The default value is **False** ($False).</span></span> |<span data-ttu-id="77801-182">False</span><span class="sxs-lookup"><span data-stu-id="77801-182">False</span></span>|<span data-ttu-id="77801-183">True</span><span class="sxs-lookup"><span data-stu-id="77801-183">True</span></span><br/><span data-ttu-id="77801-184">False</span><span class="sxs-lookup"><span data-stu-id="77801-184">False</span></span>|<span data-ttu-id="77801-185">Логическое</span><span class="sxs-lookup"><span data-stu-id="77801-185">Boolean</span></span>|
|<span data-ttu-id="77801-186">Нет</span><span class="sxs-lookup"><span data-stu-id="77801-186">No</span></span>|<span data-ttu-id="77801-187">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="77801-187">ForwardPAI</span></span>|<span data-ttu-id="77801-188">Указывает, будет ли переадресовываться заголовок P-Asserted-Identity (PAI) одновременно с вызовом.</span><span class="sxs-lookup"><span data-stu-id="77801-188">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="77801-189">Заголовок PAI предоставляет способ проверки удостоверения абонемента.</span><span class="sxs-lookup"><span data-stu-id="77801-189">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="77801-190">Значение по умолчанию — **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="77801-190">The default value is **False** ($False).</span></span>|<span data-ttu-id="77801-191">False</span><span class="sxs-lookup"><span data-stu-id="77801-191">False</span></span>|<span data-ttu-id="77801-192">True</span><span class="sxs-lookup"><span data-stu-id="77801-192">True</span></span><br/><span data-ttu-id="77801-193">False</span><span class="sxs-lookup"><span data-stu-id="77801-193">False</span></span>|<span data-ttu-id="77801-194">Логическое</span><span class="sxs-lookup"><span data-stu-id="77801-194">Boolean</span></span>|
|<span data-ttu-id="77801-195">Нет</span><span class="sxs-lookup"><span data-stu-id="77801-195">No</span></span>|<span data-ttu-id="77801-196">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="77801-196">SendSIPOptions</span></span> |<span data-ttu-id="77801-197">Определяет, если SBC будет или не будет отправлять параметры SIP.</span><span class="sxs-lookup"><span data-stu-id="77801-197">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="77801-198">Если этот параметр отключен, SBC будут исключены из системы мониторинга и оповещений.</span><span class="sxs-lookup"><span data-stu-id="77801-198">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="77801-199">Настоятельно рекомендуется включить параметры SIP.</span><span class="sxs-lookup"><span data-stu-id="77801-199">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="77801-200">Значение по умолчанию — **True**.</span><span class="sxs-lookup"><span data-stu-id="77801-200">Default value is **True**.</span></span> |<span data-ttu-id="77801-201">True</span><span class="sxs-lookup"><span data-stu-id="77801-201">True</span></span>|<span data-ttu-id="77801-202">True</span><span class="sxs-lookup"><span data-stu-id="77801-202">True</span></span><br/><span data-ttu-id="77801-203">False</span><span class="sxs-lookup"><span data-stu-id="77801-203">False</span></span>|<span data-ttu-id="77801-204">Логическое</span><span class="sxs-lookup"><span data-stu-id="77801-204">Boolean</span></span>|
|<span data-ttu-id="77801-205">Нет</span><span class="sxs-lookup"><span data-stu-id="77801-205">No</span></span>|<span data-ttu-id="77801-206">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="77801-206">MaxConcurrentSessions</span></span> |<span data-ttu-id="77801-207">Используемый предупреждения системы.</span><span class="sxs-lookup"><span data-stu-id="77801-207">Used by alerting system.</span></span> <span data-ttu-id="77801-208">Если любое значение, предупреждения системы будет создать оповещение для администратора клиента, если количество одновременных сеансов является 90% или выше, чем это значение.</span><span class="sxs-lookup"><span data-stu-id="77801-208">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="77801-209">Если параметр не задан, оповещения не создаются.</span><span class="sxs-lookup"><span data-stu-id="77801-209">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="77801-210">Тем не менее система мониторинга сообщает количество одновременных сеансов каждые 24 часа.</span><span class="sxs-lookup"><span data-stu-id="77801-210">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="77801-211">NULL</span><span class="sxs-lookup"><span data-stu-id="77801-211">Null</span></span>|<span data-ttu-id="77801-212">NULL</span><span class="sxs-lookup"><span data-stu-id="77801-212">Null</span></span><br/><span data-ttu-id="77801-213">1 до 100 000</span><span class="sxs-lookup"><span data-stu-id="77801-213">1 to 100,000</span></span> ||
|<span data-ttu-id="77801-214">Нет</span><span class="sxs-lookup"><span data-stu-id="77801-214">No</span></span>|<span data-ttu-id="77801-215">Включено \*</span><span class="sxs-lookup"><span data-stu-id="77801-215">Enabled\*</span></span>|<span data-ttu-id="77801-216">Используется для включения этой SBC для исходящих звонков.</span><span class="sxs-lookup"><span data-stu-id="77801-216">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="77801-217">Можно использовать для временно удалить SBC в процессе обновления или во время обслуживания.</span><span class="sxs-lookup"><span data-stu-id="77801-217">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="77801-218">False</span><span class="sxs-lookup"><span data-stu-id="77801-218">False</span></span>|<span data-ttu-id="77801-219">True</span><span class="sxs-lookup"><span data-stu-id="77801-219">True</span></span><br/><span data-ttu-id="77801-220">False</span><span class="sxs-lookup"><span data-stu-id="77801-220">False</span></span>|<span data-ttu-id="77801-221">Логическое</span><span class="sxs-lookup"><span data-stu-id="77801-221">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="77801-222">Проверка подключения к SBC</span><span class="sxs-lookup"><span data-stu-id="77801-222">Verify the SBC pairing</span></span> 

<span data-ttu-id="77801-223">Проверьте подключение:</span><span class="sxs-lookup"><span data-stu-id="77801-223">Verify the connection:</span></span> 
- <span data-ttu-id="77801-224">Проверьте, если в списке парного SBC будет SBC.</span><span class="sxs-lookup"><span data-stu-id="77801-224">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="77801-225">Проверка параметров SIP.</span><span class="sxs-lookup"><span data-stu-id="77801-225">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="77801-226">Проверить, если SBC находится в списке парного их изготовителей</span><span class="sxs-lookup"><span data-stu-id="77801-226">Validate if SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="77801-227">По окончании пары SBC проверки SBC присутствует в списке парного их изготовителей, выполнив следующую команду в удаленный сеанс PowerShell:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="77801-227">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command  in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="77801-228">Парного шлюза следует отображаются в списке, как показано в следующем примере и убедитесь, что параметр *Enabled* значение **True**.</span><span class="sxs-lookup"><span data-stu-id="77801-228">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="77801-229">Введите:</span><span class="sxs-lookup"><span data-stu-id="77801-229">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="77801-230">Которая возвращает:</span><span class="sxs-lookup"><span data-stu-id="77801-230">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="77801-231">Проверка потока SIP-параметры</span><span class="sxs-lookup"><span data-stu-id="77801-231">Validate SIP Options flow</span></span> 

<span data-ttu-id="77801-232">Для проверки связывания с помощью параметров исходящей SIP, с помощью интерфейса управления SBC и увидеть, что SBC получите 200 OK ответ на исходящие параметры.</span><span class="sxs-lookup"><span data-stu-id="77801-232">To validate the pairing using outgoing SIP Options, use the SBC management interface and see that the SBC get 200 OK responses to the outgoing OPTIONS.</span></span>
  
<span data-ttu-id="77801-233">При прямой маршрутизации видит входящие параметры, он будет запущен процесс исходящей параметры отправки SBC полное доменное имя, настроенных в поле Заголовок контакт входящего сообщения, параметры.</span><span class="sxs-lookup"><span data-stu-id="77801-233">When Direct Routing sees incoming OPTIONS, it will start sending outgoing options to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="77801-234">Для проверки связывания с помощью параметров входящих SIP, с помощью интерфейса управления SBC и увидеть, что SBC получает ответ на параметры сообщения, поступающие из прямой маршрутизации и что код ответа 200 OK.</span><span class="sxs-lookup"><span data-stu-id="77801-234">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC gets reply on the OPTIONS messages coming in from Direct Routing and that the response code is 200 OK.</span></span>  

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="77801-235">Включение пользователей для службы напрямую маршрутизации</span><span class="sxs-lookup"><span data-stu-id="77801-235">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="77801-236">Когда вы готовы к Включение пользователей для службы напрямую маршрутизации, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="77801-236">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="77801-237">Создание пользователя в Office 365 и назначьте лицензии на систему телефона.</span><span class="sxs-lookup"><span data-stu-id="77801-237">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="77801-238">Убедитесь, что пользователь размещенный в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="77801-238">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="77801-239">Настройте номер телефона и включение корпоративной голосовой связи и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="77801-239">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="77801-240">Настройка маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="77801-240">Configure voice routing.</span></span> <span data-ttu-id="77801-241">Маршрут проверяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="77801-241">The route is automatically validated.</span></span>  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="77801-242">Создание пользователя в Office 365 и назначьте лицензии</span><span class="sxs-lookup"><span data-stu-id="77801-242">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="77801-243">Существует два варианта для создания нового пользователя в Office 365.</span><span class="sxs-lookup"><span data-stu-id="77801-243">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="77801-244">Тем не менее рекомендуется выбрать и использовать один из вариантов, чтобы избежать проблем с маршрутизацией вашей организации:</span><span class="sxs-lookup"><span data-stu-id="77801-244">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="77801-245">Создание пользователя в локальной службе Active Directory и синхронизация пользователей в облако.</span><span class="sxs-lookup"><span data-stu-id="77801-245">Create the user in on-premise Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="77801-246">В разделе [Интеграция на локальную каталогов с помощью Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="77801-246">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>  
- <span data-ttu-id="77801-247">Создание пользователя непосредственно в портал администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="77801-247">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="77801-248">В разделе [Добавление пользователей по отдельности или набором для Office 365 — помощь администратора](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="77801-248">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

  <span data-ttu-id="77801-249">При построении в системе, существует с Скайп для бизнеса 2015 или Lync 2010 или 2013 локальной только поддерживаемые параметр — для создания пользователя в локальной службе Active Directory и синхронизации пользователей в облаке (вариант 1).</span><span class="sxs-lookup"><span data-stu-id="77801-249">If you build the system that co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="77801-250">Необходимые лицензии:</span><span class="sxs-lookup"><span data-stu-id="77801-250">Required licenses:</span></span> 

- <span data-ttu-id="77801-251">Office 365 для предприятий E3 (включая SfB Plan2, Exchange Plan2 или группам) телефона системы</span><span class="sxs-lookup"><span data-stu-id="77801-251">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>  
- <span data-ttu-id="77801-252">Office 365 корпоративный E5 (включая SfB Plan2, Exchange Plan2, групп и телефонной системой)</span><span class="sxs-lookup"><span data-stu-id="77801-252">Office 365 Enterprise E5  (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="77801-253">Необязательный лицензии:</span><span class="sxs-lookup"><span data-stu-id="77801-253">Optional licenses:</span></span> 

- <span data-ttu-id="77801-254">Вызов плана</span><span class="sxs-lookup"><span data-stu-id="77801-254">Calling Plan</span></span> 
- <span data-ttu-id="77801-255">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="77801-255">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="77801-256">Пользователь является, размещенными в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="77801-256">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="77801-257">Прямое маршрутизации требует от пользователя быть размещен в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="77801-257">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="77801-258">Вы можете проверить, посмотрев параметр RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="77801-258">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="77801-259">Он должен иметь значение в домене infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="77801-259">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="77801-260">Подключение к удаленной оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77801-260">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="77801-261">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="77801-261">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="77801-262">Настройка номер телефона и включение корпоративной голосовой связи и голосовая почта</span><span class="sxs-lookup"><span data-stu-id="77801-262">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="77801-263">После создания пользователя и назначена лицензия, следующим шагом является настройка их номер телефона и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="77801-263">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="77801-264">Это можно сделать в одном шаге.</span><span class="sxs-lookup"><span data-stu-id="77801-264">This can be done in one step.</span></span> 

<span data-ttu-id="77801-265">Чтобы добавить номер телефона и включить для голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="77801-265">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="77801-266">Подключение удаленного сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77801-266">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="77801-267">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="77801-267">Enter the command:</span></span> 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

<span data-ttu-id="77801-268">Например чтобы добавить номер телефона для пользователя «Иван низкий», необходимо ввести следующее:</span><span class="sxs-lookup"><span data-stu-id="77801-268">For example, to add a phone number for user “Spencer Low,” you would enter the following:</span></span> 

```
Set-CsUser -Identity “Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="77801-269">Номер телефона должен быть настроен как полный номер телефона E.164 с код страны.</span><span class="sxs-lookup"><span data-stu-id="77801-269">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="77801-270">Если номер телефона пользователя управляется локально, используется для настройки номер телефона пользователя в локальной Скайп для бизнеса командную консоль или панель управления.</span><span class="sxs-lookup"><span data-stu-id="77801-270">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="77801-271">Настройка маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="77801-271">Configure Voice Routing</span></span> 

<span data-ttu-id="77801-272">Microsoft телефонной системой имеет маршрутизации механизм, позволяющий звонка для отправки определенных SBC на основе:</span><span class="sxs-lookup"><span data-stu-id="77801-272">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="77801-273">Вызов шаблон номера</span><span class="sxs-lookup"><span data-stu-id="77801-273">Called number pattern</span></span> 
- <span data-ttu-id="77801-274">Вызов шаблон номера + определенного пользователя, который делает вызов</span><span class="sxs-lookup"><span data-stu-id="77801-274">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="77801-275">SBC могут быть обозначены как активных и резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="77801-275">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="77801-276">Который означает, что при недоступности SBC, настроенный как активных этот шаблон номера или шаблон номера + определенного пользователя, а затем звонки будут перенаправляться к резервного копирования SBC.</span><span class="sxs-lookup"><span data-stu-id="77801-276">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="77801-277">Маршрутизация звонков состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="77801-277">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="77801-278">Политика маршрутизации голосовой связи — контейнер для использования ТСОП; можно назначить пользователю или нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="77801-278">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="77801-279">Режимы работы с ТСОП — контейнер для маршрутов голосовых вызовов и использования ТСОП; можно совместно в различные политики маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="77801-279">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="77801-280">Маршруты – шаблон номера и набор Online шлюзы ТСОП, используемый для вызовов, где номер соответствует шаблону голосовой связи</span><span class="sxs-lookup"><span data-stu-id="77801-280">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="77801-281">Online шлюза ТСОП - указатель в SBC, также хранится конфигурация, которая применяется при звонок с помощью SBC, например переадресации P-Asserted-Identity (PAI) или предпочитаемое кодеков; можно добавить в маршрутов голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="77801-281">Online PSTN Gateway - pointer at SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="77801-282">Создание политики маршрутизации голосовых данных с помощью одного работы с ТСОП</span><span class="sxs-lookup"><span data-stu-id="77801-282">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="77801-283">На следующей схеме показана два примера политики маршрутизации голосовых данных в поток вызовов.</span><span class="sxs-lookup"><span data-stu-id="77801-283">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="77801-284">**Вызова потока 1 (слева):** Если пользователь совершает вызов +1 425 XXX XX XX или +1 206 XXX XX XX, звонок перенаправляется в SBC sbc1<span></span>. contoso.biz или sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="77801-284">**Call Flow 1 (on the left):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed  to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="77801-285">Если ни один из sbc1<span></span>. contoso.biz, ни sbc2<span></span>. contoso.biz доступны, вызов отклоняется.</span><span class="sxs-lookup"><span data-stu-id="77801-285">If neither sbc1<span></span>.contoso.biz nor sbc2<span></span>.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="77801-286">**Вызова поток 2 (справа):** Если пользователь совершает вызов +1 425 XXX XX XX или +1 206 XXX XX XX, вызов сначала перенаправляется в SBC sbc1<span></span>. contoso.biz или sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="77801-286">**Call Flow 2 (on the right):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="77801-287">Если ни один из SBC, предпринята попытка маршрут с низким приоритетом (sbc3<span></span>. contoso.biz и sbc4<span></span>. contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="77801-287">If neither SBC is available, the route with lower priority will be tried (sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz).</span></span> <span data-ttu-id="77801-288">Если ни один из их изготовителей недоступен, вызов отклоняется.</span><span class="sxs-lookup"><span data-stu-id="77801-288">If none of the SBCs are available, the call is dropped.</span></span> 

![Показаны примеры политики маршрутизации голосовой связи](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="77801-290">В обоих примерах пока маршрута голосовых вызовов назначается приоритеты, их изготовителей в маршруты проверяются в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="77801-290">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="77801-291">Если у пользователя также нет лицензии Майкрософт вызов планирование, звонков на любое число, кроме номеров, соответствующих шаблонов + +1 425 XXX XX XX или +1 206 XXX XX XX в пример конфигурации удаляются.</span><span class="sxs-lookup"><span data-stu-id="77801-291">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns + +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="77801-292">Если у пользователя есть вызов планирование лицензии, звонок автоматически маршрутизируются в соответствии с политики в планирование вызов Microsoft.</span><span class="sxs-lookup"><span data-stu-id="77801-292">If the user has a Calling Plan license, the call is automatically routed according to the policies of  the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="77801-293">Планирование вызов Microsoft автоматически в качестве последнего маршрута применяется ко всем пользователям с лицензией Microsoft вызов планирование и не требует дополнительных вызовов конфигурации маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="77801-293">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="77801-294">В примере показано на следующей схеме голосового маршрута добавляется для направления вызовов на всех других США и Канада номер (вызовы, которые будут входить называемое шаблон номера + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="77801-294">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Показывает маршрутизации политики третий маршрут голосовой связи](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="77801-296">Если пользователь имеет обе лицензии (Microsoft телефонной системой и вызов планирование Microsoft), для всех других вызовов используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="77801-296">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="77801-297">Если ничего не соответствует шаблоны номеров в созданное администратором online маршруты голосовой связи, маршрут с помощью вызова планирование Microsoft.</span><span class="sxs-lookup"><span data-stu-id="77801-297">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="77801-298">Если у пользователя есть только телефонной системой Microsoft, вызов отклоняется из-за соответствующие правила.</span><span class="sxs-lookup"><span data-stu-id="77801-298">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="77801-299">Значение приоритета для маршрута «Другие + 1» не имеет значения, таким образом, как это делается только один маршрут, который соответствует шаблону + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="77801-299">The Priority value for route “Other +1” doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="77801-300">Если пользователь выполняет запрос 89 89 567 324 + 1 и sbc5.contoso.biz и sbc6.contoso.biz недоступны, вызов отклоняется.</span><span class="sxs-lookup"><span data-stu-id="77801-300">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="77801-301">В следующей таблице обобщаются конфигурации, используя три маршруты голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="77801-301">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="77801-302">В этом примере все три маршруты являются частью одной работы с ТСОП «"Мне Нравится" и Canada».</span><span class="sxs-lookup"><span data-stu-id="77801-302">In this example, all three routes are part of the same PSTN Usage “US and Canada”.</span></span>

|<span data-ttu-id="77801-303">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="77801-303">**PSTN usage**</span></span>|<span data-ttu-id="77801-304">**Маршрут голосовых вызовов**</span><span class="sxs-lookup"><span data-stu-id="77801-304">**Voice route**</span></span>|<span data-ttu-id="77801-305">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="77801-305">**Number pattern**</span></span>|<span data-ttu-id="77801-306">**Приоритет**</span><span class="sxs-lookup"><span data-stu-id="77801-306">**Priority**</span></span>|<span data-ttu-id="77801-307">**SBC**</span><span class="sxs-lookup"><span data-stu-id="77801-307">**SBC**</span></span>|<span data-ttu-id="77801-308">**Описание**</span><span class="sxs-lookup"><span data-stu-id="77801-308">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="77801-309">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="77801-309">US only</span></span>|<span data-ttu-id="77801-310">«Redmond 1»</span><span class="sxs-lookup"><span data-stu-id="77801-310">“Redmond 1”</span></span>|<span data-ttu-id="77801-311">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="77801-311">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="77801-312">1</span><span class="sxs-lookup"><span data-stu-id="77801-312">1</span></span>|<span data-ttu-id="77801-313">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-313">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="77801-314">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-314">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="77801-315">Active маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="77801-315">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="77801-316">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="77801-316">US only</span></span>|<span data-ttu-id="77801-317">«Redmond 2»</span><span class="sxs-lookup"><span data-stu-id="77801-317">“Redmond 2”</span></span>|<span data-ttu-id="77801-318">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="77801-318">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="77801-319">2</span><span class="sxs-lookup"><span data-stu-id="77801-319">2</span></span>|<span data-ttu-id="77801-320">sbc3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-320">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="77801-321">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-321">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="77801-322">Резервного копирования маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="77801-322">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="77801-323">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="77801-323">US only</span></span>|<span data-ttu-id="77801-324">«Другие + 1»</span><span class="sxs-lookup"><span data-stu-id="77801-324">"Other +1”</span></span>|<span data-ttu-id="77801-325">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="77801-325">^\\+1(\d{10})$</span></span>|<span data-ttu-id="77801-326">3</span><span class="sxs-lookup"><span data-stu-id="77801-326">3</span></span>|<span data-ttu-id="77801-327">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-327">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="77801-328">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-328">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="77801-329">Маршрут для вызываемого номера + 1 XXX XXX XX XX (за исключением +1 425 XXX XX XX или +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="77801-329">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="77801-330">Всех маршрутов, связанных с работы с ТСОП «"Мне Нравится" и Canada» и об использовании PSTN связан с политики маршрутизации голосовой связи «Только для США».</span><span class="sxs-lookup"><span data-stu-id="77801-330">All routes are associated with the PSTN Usage “US and Canada” and the PSTN Usage is associated with the Voice Routing Policy “US Only.”</span></span> <span data-ttu-id="77801-331">В этом примере назначается пользователю Spencer Low политику маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="77801-331">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="77801-332">Примеры маршрутов звонков</span><span class="sxs-lookup"><span data-stu-id="77801-332">Examples of call routes</span></span>

<span data-ttu-id="77801-333">В следующем примере мы показываем, как Настройка политики маршрутизации, использования ТСОП и маршрутов и назначить политику для пользователя.</span><span class="sxs-lookup"><span data-stu-id="77801-333">In the following example,  we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="77801-334">**Шаг 1:** Создание работы с ТСОП «США и Канада.»</span><span class="sxs-lookup"><span data-stu-id="77801-334">**Step 1:** Create the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="77801-335">В поле Скайп для сеанса удаленной оболочки PowerShell бизнеса введите:</span><span class="sxs-lookup"><span data-stu-id="77801-335">In a  Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="77801-336">Проверка создания посредством ввода данных об использовании.</span><span class="sxs-lookup"><span data-stu-id="77801-336">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="77801-337">Которого возвращается список имен, которые может усекаться:</span><span class="sxs-lookup"><span data-stu-id="77801-337">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="77801-338">В приведенном ниже примере можно увидеть результат выполнения команды PowerShell *`(Get-CSOnlinePSTNUsage).usage`* Отображение полного названия (не сокращается).</span><span class="sxs-lookup"><span data-stu-id="77801-338">In the example below, you can see the result of the running the PowerShell command *`(Get-CSOnlinePSTNUsage).usage`* to display full names (not truncated).</span></span>    
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

<span data-ttu-id="77801-339">**Шаг 2:** В сеанс PowerShell в Скайп для бизнеса в Интернет, создайте три маршрутов: Redmond 1, Redmond 2 и других + 1, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="77801-339">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other+1, as detailed in the previous table.</span></span> 

<span data-ttu-id="77801-340">Чтобы создать маршрут «Redmond 1», введите:</span><span class="sxs-lookup"><span data-stu-id="77801-340">To create the “Redmond 1” route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="77801-341">Которая возвращает:</span><span class="sxs-lookup"><span data-stu-id="77801-341">Which returns:</span></span>
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
<span data-ttu-id="77801-342">Чтобы создать маршрут Redmond 2, введите:</span><span class="sxs-lookup"><span data-stu-id="77801-342">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="77801-343">Чтобы создать маршрутом + 1, введите:</span><span class="sxs-lookup"><span data-stu-id="77801-343">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="77801-344">Убедитесь в том, что регулярное выражение в качестве атрибута переменной NumberPattern является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="77801-344">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="77801-345">Вы можете проверить ее с помощью этой веб-сайта:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="77801-345">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="77801-346">В некоторых случаях нет необходимости все вызовы направляются в одном SBC; Используйте - переменной NumberPattern «. \*»</span><span class="sxs-lookup"><span data-stu-id="77801-346">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern “.\*”</span></span>

- <span data-ttu-id="77801-347">Маршрутизировать вызовы все же SBC</span><span class="sxs-lookup"><span data-stu-id="77801-347">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="77801-348">Проверьте, что правильно настроены маршрут, выполнив `Get-CSOnlineVoiceRoute` команду Powershell с помощью параметров, как показано:</span><span class="sxs-lookup"><span data-stu-id="77801-348">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` Powershell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="77801-349">Которого должен возвращать:</span><span class="sxs-lookup"><span data-stu-id="77801-349">Which should return:</span></span>
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

<span data-ttu-id="77801-350">В примере, маршрут «Другие + 1» автоматически была назначена приоритет.</span><span class="sxs-lookup"><span data-stu-id="77801-350">In the example, the route “Other +1” was automatically assigned priority.</span></span> 

<span data-ttu-id="77801-351">**Шаг 3:** Создание политики маршрутизации голосовой связи «"мне НРАВИТСЯ" только» и добавить в политику работы с ТСОП «США и Канада.»</span><span class="sxs-lookup"><span data-stu-id="77801-351">**Step 3:** Create a Voice Routing Policy  “US Only” and add to the policy the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="77801-352">В сеанс PowerShell в Скайп для бизнеса в Интернет введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="77801-352">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="77801-353">В этом примере показан результат.</span><span class="sxs-lookup"><span data-stu-id="77801-353">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="77801-354">**Шаг 4:** Предоставление пользователю Спенс Low политику маршрутизации голосовой связи с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77801-354">**Step 4:** Grant to user Spence Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="77801-355">В сеанс Powershell в Скайп для бизнеса в Интернет введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="77801-355">In a Powershell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="77801-356">Проверка назначения политики, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="77801-356">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="77801-357">Которая возвращает:</span><span class="sxs-lookup"><span data-stu-id="77801-357">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="77801-358">Создание политики маршрутизации голосовой связи с несколькими случаев использования PSTN</span><span class="sxs-lookup"><span data-stu-id="77801-358">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="77801-359">Политику маршрутизации голосовой связи, созданную ранее допускает только вызовы на телефонные номера в США и Канада — Если не лицензии Майкрософт вызов планирование также назначается пользователю.</span><span class="sxs-lookup"><span data-stu-id="77801-359">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="77801-360">В этом примере создаются политики маршрутизации голосовой связи «Без ограничений».</span><span class="sxs-lookup"><span data-stu-id="77801-360">In the example that follows, you can create the Voice Routing Policy “No Restrictions.”</span></span> <span data-ttu-id="77801-361">Политики повторно использует режим работы с ТСОП «"Мне Нравится" и Canada» создан в предыдущем примере, а также новые работы с ТСОП «International».</span><span class="sxs-lookup"><span data-stu-id="77801-361">The policy reuses the PSTN Usage “US and Canada” created in the previous example, as well as the new PSTN Usage “International.”</span></span> 

<span data-ttu-id="77801-362">Это направляет все вызовы для их изготовителей sbc2<span></span>. contoso.biz и sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="77801-362">This routes all other calls to the SBCs sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span> <span data-ttu-id="77801-363">Представлены примеры назначить нет ограничения и политики "мне Нравится" только для пользователя «Иван низкий» пользователя «John Woods».</span><span class="sxs-lookup"><span data-stu-id="77801-363">The examples that are shown assign US Only policy to user “Spencer Low,” and No Restrictions to the user “John Woods.”</span></span>

<span data-ttu-id="77801-364">Spencer Low — допускается только в США и Канада числа звонков.</span><span class="sxs-lookup"><span data-stu-id="77801-364">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="77801-365">При вызове диапазон номеров Redmond, необходимо использовать определенный набор SBC.</span><span class="sxs-lookup"><span data-stu-id="77801-365">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="77801-366">Номера не в США не будут направляться, если вызов планирование лицензия назначена для пользователя.</span><span class="sxs-lookup"><span data-stu-id="77801-366">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="77801-367">Джон Вудз – звонки могут любое число.</span><span class="sxs-lookup"><span data-stu-id="77801-367">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="77801-368">При вызове диапазон номеров Redmond, необходимо использовать определенный набор SBC.</span><span class="sxs-lookup"><span data-stu-id="77801-368">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="77801-369">Не в США номера будут направляться через sbc2<span></span>. contoso.biz и sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="77801-369">Non-US numbers will be routed via sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span>

![Отображает политику маршрутизации голосовой связи, назначенной пользователю Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="77801-371">Если пользователь имеет обе лицензии (Microsoft телефонной системой и вызов планирование Microsoft), для всех других вызовов используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="77801-371">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="77801-372">Если ничего не соответствует шаблоны номеров в созданное администратором online маршруты голосовой связи, маршрут с помощью вызова планирование Microsoft.</span><span class="sxs-lookup"><span data-stu-id="77801-372">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="77801-373">Если у пользователя есть только телефонной системой Microsoft, вызов отклоняется из-за соответствующие правила.</span><span class="sxs-lookup"><span data-stu-id="77801-373">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Отображает политику маршрутизации голосовой связи, назначенные для пользователя John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="77801-375">В следующей таблице перечислены маршрутизации сообщений об использовании «Без ограничения» политики и маршруты голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="77801-375">The following table  summarizes routing policy “No Restrictions” usage designations and voice routes.</span></span> 

|<span data-ttu-id="77801-376">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="77801-376">**PSTN usage**</span></span>|<span data-ttu-id="77801-377">**Маршрут голосовых вызовов**</span><span class="sxs-lookup"><span data-stu-id="77801-377">**Voice route**</span></span>|<span data-ttu-id="77801-378">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="77801-378">**Number pattern**</span></span>|<span data-ttu-id="77801-379">**Приоритет**</span><span class="sxs-lookup"><span data-stu-id="77801-379">**Priority**</span></span>|<span data-ttu-id="77801-380">**SBC**</span><span class="sxs-lookup"><span data-stu-id="77801-380">**SBC**</span></span>|<span data-ttu-id="77801-381">**Описание**</span><span class="sxs-lookup"><span data-stu-id="77801-381">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="77801-382">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="77801-382">US Only</span></span>|<span data-ttu-id="77801-383">«Redmond 1»</span><span class="sxs-lookup"><span data-stu-id="77801-383">“Redmond 1”</span></span>|<span data-ttu-id="77801-384">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="77801-384">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="77801-385">1</span><span class="sxs-lookup"><span data-stu-id="77801-385">1</span></span>|<span data-ttu-id="77801-386">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-386">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="77801-387">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-387">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="77801-388">Active маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="77801-388">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="77801-389">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="77801-389">US Only</span></span>|<span data-ttu-id="77801-390">«Redmond 2»</span><span class="sxs-lookup"><span data-stu-id="77801-390">“Redmond 2”</span></span>|<span data-ttu-id="77801-391">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="77801-391">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="77801-392">2</span><span class="sxs-lookup"><span data-stu-id="77801-392">2</span></span>|<span data-ttu-id="77801-393">sbc3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-393">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="77801-394">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-394">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="77801-395">Резервного копирования маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="77801-395">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="77801-396">"Мне НРАВИТСЯ" только</span><span class="sxs-lookup"><span data-stu-id="77801-396">US Only</span></span>|<span data-ttu-id="77801-397">«Другие + 1»</span><span class="sxs-lookup"><span data-stu-id="77801-397">“Other +1”</span></span>|<span data-ttu-id="77801-398">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="77801-398">^\\+1(\d{10})$</span></span>|<span data-ttu-id="77801-399">3</span><span class="sxs-lookup"><span data-stu-id="77801-399">3</span></span>|<span data-ttu-id="77801-400">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-400">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="77801-401">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-401">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="77801-402">Маршрут для вызываемого номера + 1 XXX XXX XX XX (за исключением +1 425 XXX XX XX или +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="77801-402">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="77801-403">International</span><span class="sxs-lookup"><span data-stu-id="77801-403">International</span></span>|<span data-ttu-id="77801-404">International</span><span class="sxs-lookup"><span data-stu-id="77801-404">International</span></span>|<span data-ttu-id="77801-405">\d+</span><span class="sxs-lookup"><span data-stu-id="77801-405">\d+</span></span>|<span data-ttu-id="77801-406">4</span><span class="sxs-lookup"><span data-stu-id="77801-406">4</span></span>|<span data-ttu-id="77801-407">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-407">sbc2<span></span>.contoso.biz</span></span><br/><span data-ttu-id="77801-408">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="77801-408">sbc5<span></span>.contoso.biz</span></span>|<span data-ttu-id="77801-409">Маршрут для любой шаблон номера</span><span class="sxs-lookup"><span data-stu-id="77801-409">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="77801-410">Порядок использования ТСОП в политики маршрутизации голосовой связи крайне важна.</span><span class="sxs-lookup"><span data-stu-id="77801-410">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="77801-411">Примеры использования применяются в порядке, а если совпадение найдено при первом использовании, затем другие режимы работы с никогда не применяются.</span><span class="sxs-lookup"><span data-stu-id="77801-411">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="77801-412">Режим работы с ТСОП «International» должны быть введены после работы с ТСОП «"мне НРАВИТСЯ" только.»</span><span class="sxs-lookup"><span data-stu-id="77801-412">The PSTN Usage “International” must be placed after the PSTN Usage “US Only.”</span></span> <span data-ttu-id="77801-413">Чтобы изменить порядок использования ТСОП, запустите `Set-CSOnlineRouteRoutingPolicy` команды.</span><span class="sxs-lookup"><span data-stu-id="77801-413">To change the order of the PSTN Usages, please run the `Set-CSOnlineRouteRoutingPolicy` command.</span></span> <br/><span data-ttu-id="77801-414">Например, чтобы изменить порядок «США и Канады» выполните первый и «Международный» секунды в порядке, обратном порядку:</span><span class="sxs-lookup"><span data-stu-id="77801-414">For example, to change the order from “US and Canada” first and “International” second to the reverse order run:</span></span><br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="77801-415">Автоматически назначаются приоритет маршруты голосовой связи «International» и «Другие + 1».</span><span class="sxs-lookup"><span data-stu-id="77801-415">The priority for  “Other +1” and “International” Voice routes are assigned automatically.</span></span> <span data-ttu-id="77801-416">Они не имеет значения, поскольку они имеют более низкими приоритетами чем «Redmond 1» и «Redmond 2».</span><span class="sxs-lookup"><span data-stu-id="77801-416">They don’t matter as long as they have lower priorities than “Redmond 1” and “Redmond 2.”</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="77801-417">Пример политики маршрутизации голосовой связи для пользователя John Woods</span><span class="sxs-lookup"><span data-stu-id="77801-417">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="77801-418">Политики маршрутизации «Нет ограничений,» голосовой маршрут «International» голосовой связи действия по созданию работы с ТСОП «International», и назначение пользователя «John Woods» выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="77801-418">The steps to create PSTN Usage “International”, voice route “International,” Voice Routing Policy “No Restrictions,” and then assigning it to the user “John Woods” are as follows.</span></span>


1. <span data-ttu-id="77801-419">Во-первых создайте работы с ТСОП «International».</span><span class="sxs-lookup"><span data-stu-id="77801-419">First, create the PSTN Usage “International."</span></span> <span data-ttu-id="77801-420">В удаленный сеанс PowerShell в Скайп для бизнеса в Интернет введите:</span><span class="sxs-lookup"><span data-stu-id="77801-420">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="77801-421">Создайте новый маршрут голосовой связи «International».</span><span class="sxs-lookup"><span data-stu-id="77801-421">Next, create the new voice route “International.”</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="77801-422">Которая возвращает:</span><span class="sxs-lookup"><span data-stu-id="77801-422">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : \d+
   OnlinePstnUsages          : {International}    
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SupressCallerId           :
   AlternateCallerId         :
   </pre>
3. <span data-ttu-id="77801-423">Создайте политику маршрутизации голосовой связи «Без ограничений».</span><span class="sxs-lookup"><span data-stu-id="77801-423">Next, create a Voice Routing Policy “No Restrictions”.</span></span> <span data-ttu-id="77801-424">Режим работы с ТСОП «Redmond 1» и «Redmond» используются повторно в политике маршрутизации голосовой связи, чтобы сохранить специальная обработка звонков на номер «+1 425 XXX XX XX» и «+1 206 XXX XX XX» как на локальном или локальный.</span><span class="sxs-lookup"><span data-stu-id="77801-424">The PSTN Usage “Redmond 1” and “Redmond “ are reused in this voice routing policy to preserve special handling for calls to number “+1 425 XXX XX XX” and “+1 206 XXX XX XX” as local or on-premise calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”
```

    Take note of the order of PSTN Usages:

    a. If a call made to number “+1425 XXX XX XX” with the usages configured as in the following example, the call follows the route set in “US and Canada” usage and the special routing logic is applied. That is, the call is routed using  sbc1<span></span>.contoso.biz and sbc2<span></span>.contoso.biz first, and then  sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz as the backup routes. 

    b.  If “International” PSTN usage is before “US and Canada,” calls to + 1425 XXX XX XX are routed to sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   <span data-ttu-id="77801-425">Которая возвращает</span><span class="sxs-lookup"><span data-stu-id="77801-425">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="77801-426">Назначение политики маршрутизации голосовой связи для пользователя «John Woods» с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="77801-426">Assign the voice routing policy to the user “John Woods” using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="77801-427">Затем проверьте назначения, с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="77801-427">Then verify the assignment using the command:</span></span>   

   ```
   Get-CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="77801-428">Которая возвращает:</span><span class="sxs-lookup"><span data-stu-id="77801-428">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="77801-429">Результатом будет неограниченный политика голосовой связи, применяются к вызовам, Джон Вудз и выполним логику маршрутизации вызовов для США, Канада и международных звонков.</span><span class="sxs-lookup"><span data-stu-id="77801-429">The result is that the voice policy applied to John Woods’ calls are unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="77801-430">Установка группами Майкрософт по предпочитаемый вызывающего клиента для пользователей</span><span class="sxs-lookup"><span data-stu-id="77801-430">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="77801-431">Прямое маршрутизации только маршруты звонки в и из него пользователей при использовании команды клиента.</span><span class="sxs-lookup"><span data-stu-id="77801-431">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="77801-432">Если ваша организация использует только группы, параметр «Только для команды» режим в политике обновления рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="77801-432">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="77801-433">Если ваша организация использует Скайп для Business Server или Скайп для бизнеса в Интернет, обратитесь к следующей статье для получения дополнительных сведений и выберите соответствующий параметр: [понять сосуществования и обновление пути для Скайп для бизнеса и рабочих групп](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="77801-433">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option:  [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="77801-434">См. также</span><span class="sxs-lookup"><span data-stu-id="77801-434">See also</span></span>

[<span data-ttu-id="77801-435">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="77801-435">Plan Direct Routing</span></span>](direct-routing-plan.md)
