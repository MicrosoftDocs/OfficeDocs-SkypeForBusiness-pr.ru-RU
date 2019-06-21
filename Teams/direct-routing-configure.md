---
title: Настройка прямой маршрутизации
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Сведения о том, как настроить прямую маршрутизацию Microsoft Phone System.
ms.openlocfilehash: 1c93d8b028da3fb1aaf68241a974170d0045b950
ms.sourcegitcommit: 1786d4beccc8749e20709d2360d90e2bf7634925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2019
ms.locfileid: "35116019"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="9a356-103">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="9a356-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="9a356-104">Просмотрите следующий сеанс, чтобы узнать о преимуществах прямой маршрутизации, о том, как ее спланировать и развертывание: [Прямая маршрутизация в Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="9a356-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="9a356-105">Если вы еще не сделали этого, прочтите [маршрут на прямую маршрутизацию](direct-routing-plan.md) для необходимых компонентов и просмотрите другие действия, которые необходимо выполнить перед настройкой сети Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="9a356-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="9a356-106">В этой статье описано, как настроить прямую маршрутизацию Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="9a356-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="9a356-107">В нем показано, как связать поддерживаемый контроллер границ сеанса (SBC) для прямой маршрутизации и настроить пользователей Microsoft Teams для подключения к телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="9a356-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="9a356-108">Чтобы выполнить шаги, описанные в этой статье, администраторы должны ознакомиться с командлетами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a356-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="9a356-109">Дополнительные сведения об использовании PowerShell можно найти в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9a356-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="9a356-110">Мы рекомендуем убедиться, что ваш SBC уже настроен так, как рекомендовано вашим поставщиком SBC.</span><span class="sxs-lookup"><span data-stu-id="9a356-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="9a356-111">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="9a356-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="9a356-112">Документация по развертыванию связи с лентой</span><span class="sxs-lookup"><span data-stu-id="9a356-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="9a356-113">Вы можете настроить телефонную систему Microsoft и разрешить пользователям использовать прямую маршрутизацию, а затем настроить Microsoft Teams в качестве основного клиента, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9a356-113">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="9a356-114">Связывание SBC с телефонной системой Microsoft и проверка связывания</span><span class="sxs-lookup"><span data-stu-id="9a356-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="9a356-115">Включение поддержки прямой маршрутизации для пользователей</span><span class="sxs-lookup"><span data-stu-id="9a356-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="9a356-116">Убедитесь в том, что Microsoft Teams является предпочтительным клиентским абонентом для пользователей</span><span class="sxs-lookup"><span data-stu-id="9a356-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="9a356-117">Связывание SBC с прямой маршрутизацией в телефонной системе</span><span class="sxs-lookup"><span data-stu-id="9a356-117">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="9a356-118">Ниже приведены три высокоуровневые действия, позволяющие подключать и связывать одноранговые SBC-интерфейсы с прямыми маршрутами.</span><span class="sxs-lookup"><span data-stu-id="9a356-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="9a356-119">Подключение к центру администрирования **Skype для бизнеса Online** с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a356-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="9a356-120">Связывание SBC</span><span class="sxs-lookup"><span data-stu-id="9a356-120">Pair the SBC</span></span> 
- <span data-ttu-id="9a356-121">Проверка связывания</span><span class="sxs-lookup"><span data-stu-id="9a356-121">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="9a356-122">Подключение к Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a356-122">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="9a356-123">Вы можете использовать сеанс PowerShell, подключенный к клиенту, для связывания SBC с интерфейсом Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="9a356-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="9a356-124">Чтобы открыть сеанс PowerShell, выполните шаги, описанные в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9a356-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="9a356-125">После установки удаленного сеанса PowerShell убедитесь, что вы видите команды для управления SBC.</span><span class="sxs-lookup"><span data-stu-id="9a356-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="9a356-126">Чтобы проверить команды, введите (или скопируйте или вставьте) в сеансе PowerShell следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="9a356-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="9a356-127">Ваша команда вернет четыре показанные здесь функции, которые позволят вам управлять этим SBC.</span><span class="sxs-lookup"><span data-stu-id="9a356-127">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="9a356-128">Связывание SBC с клиентом</span><span class="sxs-lookup"><span data-stu-id="9a356-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="9a356-129">Чтобы связать SBC с клиентом, в сеансе PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="9a356-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="9a356-130">Мы настоятельно рекомендуем задать максимальное количество вызовов в SBC, используя сведения, которые можно найти в документации по SBC.</span><span class="sxs-lookup"><span data-stu-id="9a356-130">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="9a356-131">Это ограничение инициирует уведомление, если объект SBC находится на уровне емкости.</span><span class="sxs-lookup"><span data-stu-id="9a356-131">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="9a356-132">Вы можете присвоить значение SBC только в том случае, если доменная часть своего полного доменного имени соответствует одному из \*доменов, зарегистрированных в вашем клиенте, за исключением onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="9a356-132">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="9a356-133">Использование \*доменных имен onmicrosoft.com не поддерживается для полного доменного имени SBC.</span><span class="sxs-lookup"><span data-stu-id="9a356-133">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="9a356-134">Например, если у вас есть два доменных имен:</span><span class="sxs-lookup"><span data-stu-id="9a356-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="9a356-135">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="9a356-135">**contoso**.com</span></span><br/><span data-ttu-id="9a356-136">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9a356-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="9a356-137">Для имени SBC можно использовать имя sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9a356-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="9a356-138">При попытке связывания SBC с именем SBC. contoso. ABC система не позволит вам, так как домен не принадлежит этому клиенту.</span><span class="sxs-lookup"><span data-stu-id="9a356-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="9a356-139">Дает</span><span class="sxs-lookup"><span data-stu-id="9a356-139">Returns:</span></span>
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
<span data-ttu-id="9a356-140">В процессе связывания можно настроить дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="9a356-140">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="9a356-141">Однако в предыдущем примере показаны только минимально необходимые параметры.</span><span class="sxs-lookup"><span data-stu-id="9a356-141">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="9a356-142">В таблице ниже перечислены дополнительные параметры, которые можно использовать при настройке параметров для`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="9a356-142">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="9a356-143">Обязательно?</span><span class="sxs-lookup"><span data-stu-id="9a356-143">Required?</span></span>|<span data-ttu-id="9a356-144">Имя</span><span class="sxs-lookup"><span data-stu-id="9a356-144">Name</span></span>|<span data-ttu-id="9a356-145">Описание</span><span class="sxs-lookup"><span data-stu-id="9a356-145">Description</span></span>|<span data-ttu-id="9a356-146">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="9a356-146">Default</span></span>|<span data-ttu-id="9a356-147">Возможные значения</span><span class="sxs-lookup"><span data-stu-id="9a356-147">Possible values</span></span>|<span data-ttu-id="9a356-148">Тип и ограничения</span><span class="sxs-lookup"><span data-stu-id="9a356-148">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9a356-149">Да</span><span class="sxs-lookup"><span data-stu-id="9a356-149">Yes</span></span>|<span data-ttu-id="9a356-150">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="9a356-150">FQDN</span></span>|<span data-ttu-id="9a356-151">Полное доменное имя SBC</span><span class="sxs-lookup"><span data-stu-id="9a356-151">The FQDN name of the SBC</span></span> |<span data-ttu-id="9a356-152">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-152">None</span></span>|<span data-ttu-id="9a356-153">Нонефкдн имя, ограничение 63 символов</span><span class="sxs-lookup"><span data-stu-id="9a356-153">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="9a356-154">Строка, список допустимых и недопустимых символов в [соглашениях об именовании в Active Directory для компьютеров, доменов, сайтов и](https://support.microsoft.com/help/909264) подразделений</span><span class="sxs-lookup"><span data-stu-id="9a356-154">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="9a356-155">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-155">No</span></span>|<span data-ttu-id="9a356-156">Медиабипасс</span><span class="sxs-lookup"><span data-stu-id="9a356-156">MediaBypass</span></span> |<span data-ttu-id="9a356-157">Параметр зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="9a356-157">The parameter reserved for future use.</span></span> <span data-ttu-id="9a356-158">Параметр, обозначенный SBC, поддерживает обход мультимедиа, и администратор хочет использовать его.</span><span class="sxs-lookup"><span data-stu-id="9a356-158">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="9a356-159">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-159">None</span></span>|<span data-ttu-id="9a356-160">True</span><span class="sxs-lookup"><span data-stu-id="9a356-160">True</span></span><br/><span data-ttu-id="9a356-161">False</span><span class="sxs-lookup"><span data-stu-id="9a356-161">False</span></span>|<span data-ttu-id="9a356-162">Boolean</span><span class="sxs-lookup"><span data-stu-id="9a356-162">Boolean</span></span>|
|<span data-ttu-id="9a356-163">Да</span><span class="sxs-lookup"><span data-stu-id="9a356-163">Yes</span></span>|<span data-ttu-id="9a356-164">Сипсигналлингпорт</span><span class="sxs-lookup"><span data-stu-id="9a356-164">SipSignallingPort</span></span> |<span data-ttu-id="9a356-165">Порт прослушивания, используемый для связи с прямыми службами маршрутизации с помощью протокола TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="9a356-165">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="9a356-166">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-166">None</span></span>|<span data-ttu-id="9a356-167">Любой порт</span><span class="sxs-lookup"><span data-stu-id="9a356-167">Any port</span></span>|<span data-ttu-id="9a356-168">от 0 до 65535</span><span class="sxs-lookup"><span data-stu-id="9a356-168">0 to 65535</span></span> |
|<span data-ttu-id="9a356-169">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-169">No</span></span>|<span data-ttu-id="9a356-170">Фаиловертимесекондс</span><span class="sxs-lookup"><span data-stu-id="9a356-170">FailoverTimeSeconds</span></span> |<span data-ttu-id="9a356-171">Если для этого параметра установлено значение 10 (значения по умолчанию), исходящие вызовы, которые не ответили шлюзом в течение 10 секунд, пересылаются на следующую доступную магистраль. Если дополнительных каналов связи нет, Звонок автоматически удаляется.</span><span class="sxs-lookup"><span data-stu-id="9a356-171">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="9a356-172">В организации с медленными ответами сетей и шлюзов, это может приводить к необязательному пропуску вызовов.</span><span class="sxs-lookup"><span data-stu-id="9a356-172">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="9a356-173">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="9a356-173">The default value is 10.</span></span>|<span data-ttu-id="9a356-174">5-10</span><span class="sxs-lookup"><span data-stu-id="9a356-174">10</span></span>|<span data-ttu-id="9a356-175">Число</span><span class="sxs-lookup"><span data-stu-id="9a356-175">Number</span></span>|<span data-ttu-id="9a356-176">Типом</span><span class="sxs-lookup"><span data-stu-id="9a356-176">Int</span></span>|
|<span data-ttu-id="9a356-177">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-177">No</span></span>|<span data-ttu-id="9a356-178">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="9a356-178">ForwardCallHistory</span></span> |<span data-ttu-id="9a356-179">Означает, будет ли переадресовываться по магистральному каналу сведения о журнале звонков.</span><span class="sxs-lookup"><span data-stu-id="9a356-179">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="9a356-180">Если этот флажок установлен, прокси-сервер Office 365 КТСОП отправляет два заголовка: журнал — информация и на которую указывает обращение.</span><span class="sxs-lookup"><span data-stu-id="9a356-180">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="9a356-181">Значением по умолчанию является **ложь** ($false).</span><span class="sxs-lookup"><span data-stu-id="9a356-181">The default value is **False** ($False).</span></span> |<span data-ttu-id="9a356-182">False</span><span class="sxs-lookup"><span data-stu-id="9a356-182">False</span></span>|<span data-ttu-id="9a356-183">True</span><span class="sxs-lookup"><span data-stu-id="9a356-183">True</span></span><br/><span data-ttu-id="9a356-184">False</span><span class="sxs-lookup"><span data-stu-id="9a356-184">False</span></span>|<span data-ttu-id="9a356-185">Boolean</span><span class="sxs-lookup"><span data-stu-id="9a356-185">Boolean</span></span>|
|<span data-ttu-id="9a356-186">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-186">No</span></span>|<span data-ttu-id="9a356-187">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="9a356-187">ForwardPAI</span></span>|<span data-ttu-id="9a356-188">Указывает, будет ли переадресовываться заголовок P-Asserted-Identity (PAI) одновременно с вызовом.</span><span class="sxs-lookup"><span data-stu-id="9a356-188">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="9a356-189">Заголовок PAI предоставляет способ проверки удостоверения абонемента.</span><span class="sxs-lookup"><span data-stu-id="9a356-189">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="9a356-190">Если включено, будет также отправлен заголовок "Конфиденциальность: ИД".</span><span class="sxs-lookup"><span data-stu-id="9a356-190">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="9a356-191">Значением по умолчанию является **ложь** ($false).</span><span class="sxs-lookup"><span data-stu-id="9a356-191">The default value is **False** ($False).</span></span>|<span data-ttu-id="9a356-192">False</span><span class="sxs-lookup"><span data-stu-id="9a356-192">False</span></span>|<span data-ttu-id="9a356-193">True</span><span class="sxs-lookup"><span data-stu-id="9a356-193">True</span></span><br/><span data-ttu-id="9a356-194">False</span><span class="sxs-lookup"><span data-stu-id="9a356-194">False</span></span>|<span data-ttu-id="9a356-195">Boolean</span><span class="sxs-lookup"><span data-stu-id="9a356-195">Boolean</span></span>|
|<span data-ttu-id="9a356-196">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-196">No</span></span>|<span data-ttu-id="9a356-197">Сендсипоптионс</span><span class="sxs-lookup"><span data-stu-id="9a356-197">SendSIPOptions</span></span> |<span data-ttu-id="9a356-198">Определяет, будет ли SBC или не будет отправлять параметры SIP.</span><span class="sxs-lookup"><span data-stu-id="9a356-198">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="9a356-199">Если отключено, SBC будет исключен из системы мониторинга и оповещения.</span><span class="sxs-lookup"><span data-stu-id="9a356-199">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="9a356-200">Настоятельно рекомендуем включить параметры SIP.</span><span class="sxs-lookup"><span data-stu-id="9a356-200">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="9a356-201">Значение по умолчанию — **true**.</span><span class="sxs-lookup"><span data-stu-id="9a356-201">Default value is **True**.</span></span> |<span data-ttu-id="9a356-202">True</span><span class="sxs-lookup"><span data-stu-id="9a356-202">True</span></span>|<span data-ttu-id="9a356-203">True</span><span class="sxs-lookup"><span data-stu-id="9a356-203">True</span></span><br/><span data-ttu-id="9a356-204">False</span><span class="sxs-lookup"><span data-stu-id="9a356-204">False</span></span>|<span data-ttu-id="9a356-205">Boolean</span><span class="sxs-lookup"><span data-stu-id="9a356-205">Boolean</span></span>|
|<span data-ttu-id="9a356-206">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-206">No</span></span>|<span data-ttu-id="9a356-207">Максконкуррентсессионс</span><span class="sxs-lookup"><span data-stu-id="9a356-207">MaxConcurrentSessions</span></span> |<span data-ttu-id="9a356-208">Используется системой оповещения.</span><span class="sxs-lookup"><span data-stu-id="9a356-208">Used by alerting system.</span></span> <span data-ttu-id="9a356-209">Если задано какое либо значение, система оповещения создаст оповещение для администратора клиента, если число параллельных сеансов составляет 90% или выше этого значения.</span><span class="sxs-lookup"><span data-stu-id="9a356-209">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="9a356-210">Если параметр не задан, оповещения не создаются.</span><span class="sxs-lookup"><span data-stu-id="9a356-210">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="9a356-211">Тем не менее, система мониторинга будет сообщать количество параллельных сеансов каждые 24 часа.</span><span class="sxs-lookup"><span data-stu-id="9a356-211">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="9a356-212">Значения</span><span class="sxs-lookup"><span data-stu-id="9a356-212">Null</span></span>|<span data-ttu-id="9a356-213">Значения</span><span class="sxs-lookup"><span data-stu-id="9a356-213">Null</span></span><br/><span data-ttu-id="9a356-214">от 1 до 100 000</span><span class="sxs-lookup"><span data-stu-id="9a356-214">1 to 100,000</span></span> ||
|<span data-ttu-id="9a356-215">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-215">No</span></span>|<span data-ttu-id="9a356-216">Медиарелайраутинглокатионоверриде</span><span class="sxs-lookup"><span data-stu-id="9a356-216">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="9a356-217">Позволяет выбрать путь для мультимедиа вручную.</span><span class="sxs-lookup"><span data-stu-id="9a356-217">Allows selecting path for media manually.</span></span> <span data-ttu-id="9a356-218">Прямая маршрутизация назначает центр обработки данных для пути к носителю, основываясь на общедоступном IP-адресе SBC.</span><span class="sxs-lookup"><span data-stu-id="9a356-218">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="9a356-219">Мы всегда Выбери ближайший вариант в центре обработки данных SBC.</span><span class="sxs-lookup"><span data-stu-id="9a356-219">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="9a356-220">Тем не менее, в некоторых случаях публичный IP-адрес, например диапазон US, может быть назначен для SBC, находящегося в Европе.</span><span class="sxs-lookup"><span data-stu-id="9a356-220">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="9a356-221">В этом случае мы будем использовать не оптимальный путь к носителю.</span><span class="sxs-lookup"><span data-stu-id="9a356-221">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="9a356-222">Этот параметр позволяет вручную настроить предпочтительный регион для передачи данных мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9a356-222">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="9a356-223">Мы рекомендуем установить этот параметр только в том случае, если журнал звонков явно указывает на то, что автоматическое назначение центра обработки данных для пути к носителю не присвоено ближайшему элементу в центре обработки данных SBC.</span><span class="sxs-lookup"><span data-stu-id="9a356-223">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="9a356-224">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-224">None</span></span>|<span data-ttu-id="9a356-225">Коды стран в формате ISO</span><span class="sxs-lookup"><span data-stu-id="9a356-225">Country codes in ISO format</span></span>||
|<span data-ttu-id="9a356-226">Нет</span><span class="sxs-lookup"><span data-stu-id="9a356-226">No</span></span>|<span data-ttu-id="9a356-227">Включено</span><span class="sxs-lookup"><span data-stu-id="9a356-227">Enabled</span></span>|<span data-ttu-id="9a356-228">Используется для включения этого SBC для исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="9a356-228">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="9a356-229">Можно использовать для временного удаления SBC, в то время как он обновляется или идет на обслуживание.</span><span class="sxs-lookup"><span data-stu-id="9a356-229">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="9a356-230">False</span><span class="sxs-lookup"><span data-stu-id="9a356-230">False</span></span>|<span data-ttu-id="9a356-231">True</span><span class="sxs-lookup"><span data-stu-id="9a356-231">True</span></span><br/><span data-ttu-id="9a356-232">False</span><span class="sxs-lookup"><span data-stu-id="9a356-232">False</span></span>|<span data-ttu-id="9a356-233">Boolean</span><span class="sxs-lookup"><span data-stu-id="9a356-233">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="9a356-234">Проверка связывания SBC</span><span class="sxs-lookup"><span data-stu-id="9a356-234">Verify the SBC pairing</span></span> 

<span data-ttu-id="9a356-235">Проверьте подключение:</span><span class="sxs-lookup"><span data-stu-id="9a356-235">Verify the connection:</span></span> 
- <span data-ttu-id="9a356-236">Убедитесь, что SBC есть в списке парных SBCs.</span><span class="sxs-lookup"><span data-stu-id="9a356-236">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="9a356-237">Проверьте параметры SIP.</span><span class="sxs-lookup"><span data-stu-id="9a356-237">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="9a356-238">Проверка того, что SBC находится в списке парных SBCs</span><span class="sxs-lookup"><span data-stu-id="9a356-238">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="9a356-239">После связывания SBC убедитесь, что SBC представлен в списке парных SBCs, выполнив следующую команду в удаленном сеансе PowerShell.`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="9a356-239">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="9a356-240">Попарный шлюз должен отображаться в списке, как показано в приведенном ниже примере, и убедитесь, что параметр *Enabled* отображает значение **Истина**.</span><span class="sxs-lookup"><span data-stu-id="9a356-240">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="9a356-241">Ведите</span><span class="sxs-lookup"><span data-stu-id="9a356-241">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="9a356-242">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="9a356-242">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="9a356-243">Проверка потока параметров SIP</span><span class="sxs-lookup"><span data-stu-id="9a356-243">Validate SIP Options flow</span></span> 

<span data-ttu-id="9a356-244">Для проверки связывания с помощью исходящих параметров SIP используйте интерфейс управления SBC и убедитесь, что SBC получает ответы на 200 ОК в сообщениях с параметрами исходящих параметров.</span><span class="sxs-lookup"><span data-stu-id="9a356-244">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="9a356-245">Когда прямая маршрутизация видит параметры входящего трафика, она начнет отправлять сообщения параметров исходящих модулей SIP в FQDN, настроенном в поле "заголовок" в сообщении "параметры входящих".</span><span class="sxs-lookup"><span data-stu-id="9a356-245">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="9a356-246">Для проверки связывания с помощью параметров входящего SIP используйте интерфейс управления SBC и посмотрите, что SBC отправляет ответы на сообщения параметров, поступившие от Direct Routing, и что код ответа, который он отправляет, — 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="9a356-246">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="9a356-247">Включение поддержки прямой маршрутизации для пользователей</span><span class="sxs-lookup"><span data-stu-id="9a356-247">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="9a356-248">Когда вы будете готовы включить пользователей для службы прямой маршрутизации, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9a356-248">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="9a356-249">Создание пользователя в Office 365 и назначение лицензии на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="9a356-249">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="9a356-250">Убедитесь в том, что пользователь размещен в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="9a356-250">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="9a356-251">Настройте номер телефона и включите поддержку корпоративной голосовой и голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="9a356-251">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="9a356-252">Настройка голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="9a356-252">Configure voice routing.</span></span> <span data-ttu-id="9a356-253">Маршрут будет проверяться автоматически.</span><span class="sxs-lookup"><span data-stu-id="9a356-253">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="9a356-254">Создание пользователя в Office 365 и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="9a356-254">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="9a356-255">Существует два способа создания нового пользователя в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a356-255">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="9a356-256">Однако мы рекомендуем выбрать и использовать один из вариантов для устранения проблем с маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="9a356-256">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="9a356-257">Создайте пользователя в локальной службе каталогов Active Directory и синхронизируйте пользователя с облаком.</span><span class="sxs-lookup"><span data-stu-id="9a356-257">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="9a356-258">Откройте раздел [интеграция локальных каталогов с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="9a356-258">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="9a356-259">Создайте пользователя прямо на портале администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a356-259">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="9a356-260">В разделе [Добавление пользователей по отдельности или массово в Office 365 — Справка для администраторов](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="9a356-260">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="9a356-261">Если развертывание Skype для бизнеса Online осуществляется совместно со Skype для бизнеса 2015 или Lync 2010/2013 локально, единственным поддерживаемым вариантом будет создание пользователя в локальной службе каталогов Active Directory и синхронизация пользователя с облаком (вариант 1).</span><span class="sxs-lookup"><span data-stu-id="9a356-261">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="9a356-262">Обязательные лицензии:</span><span class="sxs-lookup"><span data-stu-id="9a356-262">Required licenses:</span></span> 

- <span data-ttu-id="9a356-263">Office 365 Корпоративная E3 (в том числе SfB Plan2, Exchange Plan2 и Teams) + телефонная система</span><span class="sxs-lookup"><span data-stu-id="9a356-263">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="9a356-264">Office 365 Корпоративная + + + (в том числе SfB Plan2, Exchange Plan2, Teams и Phone System)</span><span class="sxs-lookup"><span data-stu-id="9a356-264">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="9a356-265">Необязательные лицензии:</span><span class="sxs-lookup"><span data-stu-id="9a356-265">Optional licenses:</span></span> 

- <span data-ttu-id="9a356-266">План звонков</span><span class="sxs-lookup"><span data-stu-id="9a356-266">Calling Plan</span></span> 
- <span data-ttu-id="9a356-267">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="9a356-267">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="9a356-268">Убедитесь в том, что пользователь размещен в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9a356-268">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="9a356-269">Для прямой маршрутизации требуется, чтобы пользователь был подключен в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="9a356-269">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="9a356-270">Чтобы проверить это, Взгляните на параметр Регистрарпул.</span><span class="sxs-lookup"><span data-stu-id="9a356-270">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="9a356-271">В домене infra.lync.com должно быть значение.</span><span class="sxs-lookup"><span data-stu-id="9a356-271">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="9a356-272">Подключитесь к удаленной оболочке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a356-272">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="9a356-273">Выдайте команду:</span><span class="sxs-lookup"><span data-stu-id="9a356-273">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="9a356-274">Настройка номера телефона и включение корпоративной голосовой и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="9a356-274">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="9a356-275">После создания пользователя и назначения лицензии следует настроить свой номер телефона и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="9a356-275">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="9a356-276">Это можно сделать одним из шагов.</span><span class="sxs-lookup"><span data-stu-id="9a356-276">This can be done in one step.</span></span> 

<span data-ttu-id="9a356-277">Чтобы добавить номер телефона и включить голосовую почту, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9a356-277">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="9a356-278">Подключитесь к удаленному сеансу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a356-278">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="9a356-279">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="9a356-279">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="9a356-280">Например, чтобы добавить номер телефона пользователя "Спенцер Low", введите следующее:</span><span class="sxs-lookup"><span data-stu-id="9a356-280">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="9a356-281">Номер телефона должен быть настроен как полный E. 164 номер телефона с кодом страны.</span><span class="sxs-lookup"><span data-stu-id="9a356-281">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="9a356-282">Если в качестве номера телефона пользователя используется локальный, используйте локальную среду управления и панель управления Skype для бизнеса, чтобы настроить номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a356-282">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="9a356-283">Настройка голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="9a356-283">Configure Voice Routing</span></span> 

<span data-ttu-id="9a356-284">В телефонной системе Microsoft есть механизм маршрутизации, который позволяет отправлять звонки на определенный SBC, основанный на следующих устройствах:</span><span class="sxs-lookup"><span data-stu-id="9a356-284">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="9a356-285">Названный шаблон номера</span><span class="sxs-lookup"><span data-stu-id="9a356-285">Called number pattern</span></span> 
- <span data-ttu-id="9a356-286">Вызываемый шаблон номера + определенный пользователь, который выполняет Звонок</span><span class="sxs-lookup"><span data-stu-id="9a356-286">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="9a356-287">SBCs можно назначить активными и архивировать.</span><span class="sxs-lookup"><span data-stu-id="9a356-287">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="9a356-288">Это означает, что если объект SBC, настроенный как активный для этого шаблона номера, или шаблон числа + определенного пользователя, недоступен, звонки будут перенаправляться в одноэлементный объект SBC.</span><span class="sxs-lookup"><span data-stu-id="9a356-288">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="9a356-289">Маршрутизация звонков состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="9a356-289">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="9a356-290">Политика маршрутизации голосовой связи — контейнер использования КТСОП; может назначаться пользователю или нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="9a356-290">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="9a356-291">Использование PSTN — контейнер для голосовых маршрутов и использование PSTN; могут совместно использоваться в разных политиках голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="9a356-291">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="9a356-292">Маршруты голосовой связи — шаблон номера и набор шлюзов в Интернет-шлюзах, которые должны использоваться для звонков, где номер звонка соответствует шаблону</span><span class="sxs-lookup"><span data-stu-id="9a356-292">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="9a356-293">Сетевой шлюз PSTN — указатель на SBC, также хранит конфигурацию, которая применяется при помещении звонка через SBC, например переадресация с подлинным идентификатором P-утвержденного (паи) или Предпочтительные кодеки. можно добавлять в Голосовые маршруты</span><span class="sxs-lookup"><span data-stu-id="9a356-293">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="9a356-294">Создание политики голосовой маршрутизации с использованием одной PSTN</span><span class="sxs-lookup"><span data-stu-id="9a356-294">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="9a356-295">На приведенной ниже схеме показаны два примера политик маршрутизации голосовой связи в потоке вызовов.</span><span class="sxs-lookup"><span data-stu-id="9a356-295">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="9a356-296">**Поток звонков 1 (слева):** Если пользователь выполняет вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов передается на SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="9a356-296">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="9a356-297">Если ни sbc1.contoso.biz, ни sbc2.contoso.biz недоступны, вызов отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="9a356-297">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="9a356-298">**Направление звонка 2 (справа):** Если пользователь совершает вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов сначала пересылается на SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="9a356-298">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="9a356-299">Если ни один из SBC недоступен, будет применяться маршрут с более низким приоритетом (sbc3.contoso.biz и sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="9a356-299">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="9a356-300">Если ни одна из этих SBCs недоступна, вызов отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="9a356-300">If none of the SBCs are available, the call is dropped.</span></span> 

![Примеры политики голосовой маршрутизации](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="9a356-302">В обоих примерах, когда маршрут голоса назначается приоритетами, однобайтовые данные маршрутов выполняются в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="9a356-302">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9a356-303">Если у пользователя нет лицензии на план звонков Microsoft, звонки на любое число, кроме номеров, соответствующих шаблонам + 1 425 XXX XX XX или + 1 206 XXX XX XX, удаляются.</span><span class="sxs-lookup"><span data-stu-id="9a356-303">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="9a356-304">Если у пользователя есть лицензия на план звонков, этот звонок автоматически маршрутизируется согласно политикам плана вызовов Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9a356-304">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="9a356-305">План звонков Microsoft автоматически применяется к последнему маршруту для всех пользователей с лицензией на план звонков Microsoft и не требует дополнительной настройки маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="9a356-305">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="9a356-306">В примере на приведенной ниже схеме маршрут голосовой связи добавляется для отправки звонков на все остальные звонки в США и Канаде (звонки, находящиеся под названием "номер" + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="9a356-306">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Политика маршрутизации голосовой связи с третьим маршрутом](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="9a356-308">Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="9a356-308">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="9a356-309">Если ничего не соответствует шаблонам, созданным администратором в онлайновых голосовых маршрутах, направьте его через план звонков Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9a356-309">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="9a356-310">Если у пользователя есть только телефонная система Microsoft, вызов отклоняется из-за того, что нет доступных правил сопоставления.</span><span class="sxs-lookup"><span data-stu-id="9a356-310">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9a356-311">Значение приоритета для маршрута "Other + 1" в этом случае не имеет значения, так как есть только один маршрут, соответствующий шаблону + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="9a356-311">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="9a356-312">Если пользователь вызывает + 1 324 567 89 89, а оба sbc5.contoso.biz и sbc6.contoso.biz недоступны, Звонок отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="9a356-312">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="9a356-313">В приведенной ниже таблице перечислены конфигурации с тремя голосовыми маршрутами.</span><span class="sxs-lookup"><span data-stu-id="9a356-313">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="9a356-314">В этом примере все три маршрута являются частью одного и того же использования КТСОП "США и Канада".</span><span class="sxs-lookup"><span data-stu-id="9a356-314">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="9a356-315">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="9a356-315">**PSTN usage**</span></span>|<span data-ttu-id="9a356-316">**Маршрут голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="9a356-316">**Voice route**</span></span>|<span data-ttu-id="9a356-317">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="9a356-317">**Number pattern**</span></span>|<span data-ttu-id="9a356-318">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9a356-318">**Priority**</span></span>|<span data-ttu-id="9a356-319">**БАЙТОВ**</span><span class="sxs-lookup"><span data-stu-id="9a356-319">**SBC**</span></span>|<span data-ttu-id="9a356-320">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9a356-320">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9a356-321">Только для США</span><span class="sxs-lookup"><span data-stu-id="9a356-321">US only</span></span>|<span data-ttu-id="9a356-322">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="9a356-322">"Redmond 1"</span></span>|<span data-ttu-id="9a356-323">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="9a356-323">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9a356-324">1</span><span class="sxs-lookup"><span data-stu-id="9a356-324">1</span></span>|<span data-ttu-id="9a356-325">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-325">sbc1.contoso.biz</span></span><br/><span data-ttu-id="9a356-326">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-326">sbc2.contoso.biz</span></span>|<span data-ttu-id="9a356-327">Активный маршрут для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="9a356-327">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9a356-328">Только для США</span><span class="sxs-lookup"><span data-stu-id="9a356-328">US only</span></span>|<span data-ttu-id="9a356-329">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="9a356-329">"Redmond 2"</span></span>|<span data-ttu-id="9a356-330">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="9a356-330">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9a356-331">2</span><span class="sxs-lookup"><span data-stu-id="9a356-331">2</span></span>|<span data-ttu-id="9a356-332">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-332">sbc3.contoso.biz</span></span><br/><span data-ttu-id="9a356-333">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-333">sbc4.contoso.biz</span></span>|<span data-ttu-id="9a356-334">Маршрут резервного копирования для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="9a356-334">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9a356-335">Только для США</span><span class="sxs-lookup"><span data-stu-id="9a356-335">US only</span></span>|<span data-ttu-id="9a356-336">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="9a356-336">"Other +1"</span></span>|<span data-ttu-id="9a356-337">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="9a356-337">^\\+1(\d{10})$</span></span>|<span data-ttu-id="9a356-338">3</span><span class="sxs-lookup"><span data-stu-id="9a356-338">3</span></span>|<span data-ttu-id="9a356-339">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-339">sbc5.contoso.biz</span></span><br/><span data-ttu-id="9a356-340">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-340">sbc6.contoso.biz</span></span>|<span data-ttu-id="9a356-341">Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="9a356-341">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="9a356-342">Все маршруты связаны с использованием КТСОП "США и Канада", а использование КТСОП связано с политикой голосовой маршрутизации "только США".</span><span class="sxs-lookup"><span data-stu-id="9a356-342">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="9a356-343">В этом примере политика голосовой маршрутизации назначена пользователю Спенцер Low.</span><span class="sxs-lookup"><span data-stu-id="9a356-343">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="9a356-344">Примеры маршрутов звонков</span><span class="sxs-lookup"><span data-stu-id="9a356-344">Examples of call routes</span></span>

<span data-ttu-id="9a356-345">В приведенном ниже примере мы покажем, как настроить маршруты, использование PSTN и политики маршрутизации, а также назначить политику для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a356-345">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="9a356-346">**Действие 1:** Создайте использование КТСОП "США и Канада".</span><span class="sxs-lookup"><span data-stu-id="9a356-346">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="9a356-347">В удаленном сеансе PowerShell в Skype для бизнеса введите:</span><span class="sxs-lookup"><span data-stu-id="9a356-347">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="9a356-348">Убедитесь в том, что использование было создано путем ввода:</span><span class="sxs-lookup"><span data-stu-id="9a356-348">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="9a356-349">Возвращающий список имен, которые могут быть усечены:</span><span class="sxs-lookup"><span data-stu-id="9a356-349">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="9a356-350">В примере ниже показано, как можно просмотреть результаты выполнения команды `(Get-CSOnlinePSTNUsage).usage` PowerShell для отображения полных имен (не усеченных).</span><span class="sxs-lookup"><span data-stu-id="9a356-350">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
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

<span data-ttu-id="9a356-351">**Шаг 2.** В сеансе PowerShell в Skype для бизнеса Online создайте три маршрута: Redmond 1, Redmond 2 и другой + 1, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="9a356-351">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="9a356-352">Чтобы создать маршрут "Redmond 1", введите:</span><span class="sxs-lookup"><span data-stu-id="9a356-352">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="9a356-353">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="9a356-353">Which returns:</span></span>
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
<span data-ttu-id="9a356-354">Чтобы создать маршрут на 2 Redmond, введите:</span><span class="sxs-lookup"><span data-stu-id="9a356-354">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="9a356-355">Чтобы создать другой маршрут + 1, введите:</span><span class="sxs-lookup"><span data-stu-id="9a356-355">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="9a356-356">Убедитесь, что регулярное выражение в атрибуте Нумберпаттерн является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="9a356-356">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="9a356-357">Вы можете протестировать его с помощью этого веб-сайта:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="9a356-357">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="9a356-358">В некоторых случаях необходимо перенаправлять все вызовы на один и тот же SBC; Пожалуйста, используйте-Нумберпаттерн ". \*"</span><span class="sxs-lookup"><span data-stu-id="9a356-358">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="9a356-359">Перенаправлять все вызовы в один и тот же SBC</span><span class="sxs-lookup"><span data-stu-id="9a356-359">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="9a356-360">Проверьте, правильно ли вы настроили маршрут, выполнив команду `Get-CSOnlineVoiceRoute` PowerShell, используя указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="9a356-360">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="9a356-361">Что должно вернуть:</span><span class="sxs-lookup"><span data-stu-id="9a356-361">Which should return:</span></span>
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

<span data-ttu-id="9a356-362">В примере для маршрута "Other + 1" автоматически назначается приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="9a356-362">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="9a356-363">**Шаг 3.** Создайте политику голосовой маршрутизации "только США" и добавьте в политику использование КТСОП "США и Канада".</span><span class="sxs-lookup"><span data-stu-id="9a356-363">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="9a356-364">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="9a356-364">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="9a356-365">Результат показан в этом примере:</span><span class="sxs-lookup"><span data-stu-id="9a356-365">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="9a356-366">**Шаг 4:** Предоставьте пользователю Спенцер низкий уровень политики голосовой маршрутизации с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a356-366">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="9a356-367">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="9a356-367">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="9a356-368">Чтобы проверить назначение политики, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9a356-368">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="9a356-369">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="9a356-369">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="9a356-370">Создание политики голосовой маршрутизации с несколькими использованием PSTN</span><span class="sxs-lookup"><span data-stu-id="9a356-370">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="9a356-371">Политика маршрутизации голосовой связи, созданная ранее, позволяет звонить только в США и Канаде (за исключением случаев, когда у пользователя также выделена лицензия на план звонков Microsoft).</span><span class="sxs-lookup"><span data-stu-id="9a356-371">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="9a356-372">В приведенном ниже примере вы можете создать политику маршрутизации голосовой связи "нет ограничений".</span><span class="sxs-lookup"><span data-stu-id="9a356-372">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="9a356-373">Политика повторно использует использование КТСОП "США и Канада", созданное в предыдущем примере, а также новую использование PSTN "Международная".</span><span class="sxs-lookup"><span data-stu-id="9a356-373">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="9a356-374">При этом все другие звонки на SBCs sbc2.contoso.biz и sbc5.contoso.biz переправляются.</span><span class="sxs-lookup"><span data-stu-id="9a356-374">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="9a356-375">Приведенные примеры применяют политику "только для США" для пользователя "Спенцер Low" и никаких ограничений для пользователя "John лесу".</span><span class="sxs-lookup"><span data-stu-id="9a356-375">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="9a356-376">Спенцер низкий – звонки разрешены только в США и Канаде.</span><span class="sxs-lookup"><span data-stu-id="9a356-376">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="9a356-377">При обращении к диапазону номеров Redmond необходимо использовать определенный набор SBC.</span><span class="sxs-lookup"><span data-stu-id="9a356-377">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="9a356-378">Номера, не относящиеся к США, не будут маршрутизироваться, если пользователю не назначена лицензия на план звонков.</span><span class="sxs-lookup"><span data-stu-id="9a356-378">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="9a356-379">Джон лесу – звонки разрешены любому номеру.</span><span class="sxs-lookup"><span data-stu-id="9a356-379">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="9a356-380">При обращении к диапазону номеров Redmond необходимо использовать определенный набор SBC.</span><span class="sxs-lookup"><span data-stu-id="9a356-380">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="9a356-381">Номера, не относящиеся к США, будут маршрутизироваться через sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="9a356-381">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Политика маршрутизации голосовой связи, назначенная пользователю Спенцер низкий](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="9a356-383">Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="9a356-383">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="9a356-384">Если ничего не соответствует шаблонам, созданным администратором в онлайновых голосовых маршрутах, направьте его через план звонков Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9a356-384">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="9a356-385">Если у пользователя есть только телефонная система Microsoft, вызов отклоняется из-за того, что нет доступных правил сопоставления.</span><span class="sxs-lookup"><span data-stu-id="9a356-385">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Политика маршрутизации голосовой связи, назначенная пользователю John лесу](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="9a356-387">В таблице ниже приведено краткое описание политики маршрутизации "без ограничений" и для голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="9a356-387">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="9a356-388">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="9a356-388">**PSTN usage**</span></span>|<span data-ttu-id="9a356-389">**Маршрут голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="9a356-389">**Voice route**</span></span>|<span data-ttu-id="9a356-390">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="9a356-390">**Number pattern**</span></span>|<span data-ttu-id="9a356-391">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9a356-391">**Priority**</span></span>|<span data-ttu-id="9a356-392">**БАЙТОВ**</span><span class="sxs-lookup"><span data-stu-id="9a356-392">**SBC**</span></span>|<span data-ttu-id="9a356-393">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9a356-393">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9a356-394">Только для США</span><span class="sxs-lookup"><span data-stu-id="9a356-394">US Only</span></span>|<span data-ttu-id="9a356-395">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="9a356-395">"Redmond 1"</span></span>|<span data-ttu-id="9a356-396">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="9a356-396">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9a356-397">1</span><span class="sxs-lookup"><span data-stu-id="9a356-397">1</span></span>|<span data-ttu-id="9a356-398">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-398">sbc1.contoso.biz</span></span><br/><span data-ttu-id="9a356-399">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-399">sbc2.contoso.biz</span></span>|<span data-ttu-id="9a356-400">Активный маршрут для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="9a356-400">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9a356-401">Только для США</span><span class="sxs-lookup"><span data-stu-id="9a356-401">US Only</span></span>|<span data-ttu-id="9a356-402">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="9a356-402">"Redmond 2"</span></span>|<span data-ttu-id="9a356-403">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="9a356-403">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="9a356-404">2</span><span class="sxs-lookup"><span data-stu-id="9a356-404">2</span></span>|<span data-ttu-id="9a356-405">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-405">sbc3.contoso.biz</span></span><br/><span data-ttu-id="9a356-406">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-406">sbc4.contoso.biz</span></span>|<span data-ttu-id="9a356-407">Маршрут резервного копирования для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="9a356-407">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="9a356-408">Только для США</span><span class="sxs-lookup"><span data-stu-id="9a356-408">US Only</span></span>|<span data-ttu-id="9a356-409">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="9a356-409">"Other +1"</span></span>|<span data-ttu-id="9a356-410">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="9a356-410">^\\+1(\d{10})$</span></span>|<span data-ttu-id="9a356-411">3</span><span class="sxs-lookup"><span data-stu-id="9a356-411">3</span></span>|<span data-ttu-id="9a356-412">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-412">sbc5.contoso.biz</span></span><br/><span data-ttu-id="9a356-413">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-413">sbc6>.contoso.biz</span></span>|<span data-ttu-id="9a356-414">Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="9a356-414">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="9a356-415">International</span><span class="sxs-lookup"><span data-stu-id="9a356-415">International</span></span>|<span data-ttu-id="9a356-416">International</span><span class="sxs-lookup"><span data-stu-id="9a356-416">International</span></span>|<span data-ttu-id="9a356-417">\d +</span><span class="sxs-lookup"><span data-stu-id="9a356-417">\d+</span></span>|<span data-ttu-id="9a356-418">4</span><span class="sxs-lookup"><span data-stu-id="9a356-418">4</span></span>|<span data-ttu-id="9a356-419">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-419">sbc2.contoso.biz</span></span><br/><span data-ttu-id="9a356-420">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="9a356-420">sbc5.contoso.biz</span></span>|<span data-ttu-id="9a356-421">Маршрут для любого числового шаблона</span><span class="sxs-lookup"><span data-stu-id="9a356-421">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="9a356-422">Порядок использования PSTN в политиках маршрутизации голосовой связи очень важен.</span><span class="sxs-lookup"><span data-stu-id="9a356-422">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="9a356-423">Использование применяется по порядку, и если соответствие обнаружено при первом использовании, другие варианты использования никогда не оцениваются.</span><span class="sxs-lookup"><span data-stu-id="9a356-423">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="9a356-424">Использование КТСОП "Международная" должно быть размещено после использования КТСОП "только США".</span><span class="sxs-lookup"><span data-stu-id="9a356-424">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="9a356-425">Чтобы изменить порядок использования PSTN, выполните `Set-CSOnlineVoiceRoutingPolicy` команду.</span><span class="sxs-lookup"><span data-stu-id="9a356-425">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="9a356-426">Например, чтобы изменить порядок с "США и Канада", сначала и "международные" секунд на обратный порядок, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9a356-426">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="9a356-427">Приоритет для голосовых маршрутов "другие + 1" и "международные" назначаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="9a356-427">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="9a356-428">Они не имеют значения, если у них более низкие приоритеты, чем "Redmond 1" и "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="9a356-428">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="9a356-429">Пример политики голосовой маршрутизации для пользователя John лесу</span><span class="sxs-lookup"><span data-stu-id="9a356-429">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="9a356-430">Действия по созданию использования PSTN "международные", Голосовые маршруты "Международная", "политика маршрутизации голосовой связи", "нет ограничений", а затем назначение ее пользователю "John лесу".</span><span class="sxs-lookup"><span data-stu-id="9a356-430">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="9a356-431">Сначала необходимо создать использование КТСОП "Международная".</span><span class="sxs-lookup"><span data-stu-id="9a356-431">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="9a356-432">В удаленном сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="9a356-432">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="9a356-433">Затем создайте новый голосовой маршрут "Международная".</span><span class="sxs-lookup"><span data-stu-id="9a356-433">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="9a356-434">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="9a356-434">Which returns:</span></span>

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
3. <span data-ttu-id="9a356-435">Затем создайте политику маршрутизации голосовой связи "без ограничений".</span><span class="sxs-lookup"><span data-stu-id="9a356-435">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="9a356-436">Использование PSTN "Redmond 1" и "Redmond" используются в этой политике маршрутизации голосовой связи для сохранения особой обработки звонков на номера "+ 1 425 XXX XX XX" и "+ 1 206 XXX XX XX" как локальных, так и локальных звонков.</span><span class="sxs-lookup"><span data-stu-id="9a356-436">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="9a356-437">Который возвращает</span><span class="sxs-lookup"><span data-stu-id="9a356-437">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="9a356-438">Назначьте политику маршрутизации голосовой связи пользователю John лесу с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="9a356-438">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="9a356-439">Затем проверьте назначение с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="9a356-439">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="9a356-440">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="9a356-440">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="9a356-441">Результат заключается в том, что политика голосовой связи, примененная к вызовам Джон лесу, не ограничена, и она будет соответствовать логике маршрутизации звонков, доступной для США, Канады и международных звонков.</span><span class="sxs-lookup"><span data-stu-id="9a356-441">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="9a356-442">Настройка Microsoft Teams в качестве предпочтительного телефонного клиента для пользователей</span><span class="sxs-lookup"><span data-stu-id="9a356-442">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="9a356-443">Прямая маршрутизация направляет звонки только пользователям, использующим клиент Teams, и от пользователей.</span><span class="sxs-lookup"><span data-stu-id="9a356-443">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="9a356-444">Если в вашей организации используются только группы, рекомендуется задать режим "только для Teams" в политике обновления.</span><span class="sxs-lookup"><span data-stu-id="9a356-444">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="9a356-445">Если в организации используется Skype для бизнеса Server или Skype для бизнеса Online, ознакомьтесь со следующей статьей для получения дополнительных сведений и выберите подходящий вариант: [Общие сведения о сосуществовании и обновлении для Skype для бизнеса и рабочих групп](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="9a356-445">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="9a356-446">См. также</span><span class="sxs-lookup"><span data-stu-id="9a356-446">See also</span></span>

[<span data-ttu-id="9a356-447">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="9a356-447">Plan Direct Routing</span></span>](direct-routing-plan.md)
