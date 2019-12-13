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
- M365-voice
appliesto:
- Microsoft Teams
description: Сведения о том, как настроить прямую маршрутизацию Microsoft Phone System.
ms.openlocfilehash: 55f4fbb0f4faa70f73c742e8e849bc258dbfd481
ms.sourcegitcommit: c2e315d0fcec742d2e1ba5ad90dffd1a1157a466
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/13/2019
ms.locfileid: "40002303"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="2ca12-103">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="2ca12-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="2ca12-104">Просмотрите следующий сеанс, чтобы узнать о преимуществах прямой маршрутизации, о том, как ее спланировать и развертывание: [Прямая маршрутизация в Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="2ca12-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="2ca12-105">Если вы еще не сделали этого, прочтите [маршрут на прямую маршрутизацию](direct-routing-plan.md) для необходимых компонентов и просмотрите другие действия, которые необходимо выполнить перед настройкой сети Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="2ca12-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="2ca12-106">В этой статье описано, как настроить прямую маршрутизацию Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="2ca12-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="2ca12-107">В нем показано, как связать поддерживаемый контроллер границ сеанса (SBC) для прямой маршрутизации и настроить пользователей Microsoft Teams для подключения к телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="2ca12-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="2ca12-108">Чтобы выполнить шаги, описанные в этой статье, администраторы должны ознакомиться с командлетами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ca12-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="2ca12-109">Дополнительные сведения об использовании PowerShell можно найти в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2ca12-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="2ca12-110">Мы рекомендуем убедиться, что ваш SBC уже настроен так, как рекомендовано вашим поставщиком SBC.</span><span class="sxs-lookup"><span data-stu-id="2ca12-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="2ca12-111">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="2ca12-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="2ca12-112">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="2ca12-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="2ca12-113">Документация по развертыванию связи с лентой</span><span class="sxs-lookup"><span data-stu-id="2ca12-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="2ca12-114">Документация по развертыванию системы TE (аниноде)</span><span class="sxs-lookup"><span data-stu-id="2ca12-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="2ca12-115">Вы можете настроить телефонную систему Microsoft и разрешить пользователям использовать прямую маршрутизацию, а затем настроить Microsoft Teams в качестве основного клиента, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2ca12-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="2ca12-116">Связывание SBC с телефонной системой Microsoft и проверка связывания</span><span class="sxs-lookup"><span data-stu-id="2ca12-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="2ca12-117">Включение поддержки прямой маршрутизации для пользователей</span><span class="sxs-lookup"><span data-stu-id="2ca12-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- <span data-ttu-id="2ca12-118">Убедитесь в том, что Microsoft Teams является предпочтительным клиентским абонентом для пользователей</span><span class="sxs-lookup"><span data-stu-id="2ca12-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="2ca12-119">Связывание SBC с прямой маршрутизацией в телефонной системе</span><span class="sxs-lookup"><span data-stu-id="2ca12-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="2ca12-120">Ниже приведены три высокоуровневые действия, позволяющие подключать и связывать одноранговые SBC-интерфейсы с прямыми маршрутами.</span><span class="sxs-lookup"><span data-stu-id="2ca12-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="2ca12-121">Подключение к центру администрирования **Skype для бизнеса Online** с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ca12-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="2ca12-122">Связывание SBC</span><span class="sxs-lookup"><span data-stu-id="2ca12-122">Pair the SBC</span></span> 
- <span data-ttu-id="2ca12-123">Проверка связывания</span><span class="sxs-lookup"><span data-stu-id="2ca12-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="2ca12-124">Подключение к Skype для бизнеса Online с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ca12-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="2ca12-125">Вы можете использовать сеанс PowerShell, подключенный к клиенту, для связывания SBC с интерфейсом Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="2ca12-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="2ca12-126">Чтобы открыть сеанс PowerShell, выполните шаги, описанные в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2ca12-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="2ca12-127">После установки удаленного сеанса PowerShell убедитесь, что вы видите команды для управления SBC.</span><span class="sxs-lookup"><span data-stu-id="2ca12-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="2ca12-128">Чтобы проверить команды, введите (или скопируйте или вставьте) в сеансе PowerShell следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="2ca12-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="2ca12-129">Ваша команда вернет четыре показанные здесь функции, которые позволят вам управлять этим SBC.</span><span class="sxs-lookup"><span data-stu-id="2ca12-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="2ca12-130">Связывание SBC с клиентом</span><span class="sxs-lookup"><span data-stu-id="2ca12-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="2ca12-131">Чтобы связать SBC с клиентом, в сеансе PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="2ca12-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="2ca12-132">Мы настоятельно рекомендуем задать максимальное количество вызовов в SBC, используя сведения, которые можно найти в документации по SBC.</span><span class="sxs-lookup"><span data-stu-id="2ca12-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="2ca12-133">Это ограничение инициирует уведомление, если объект SBC находится на уровне емкости.</span><span class="sxs-lookup"><span data-stu-id="2ca12-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="2ca12-134">Вы можете присвоить значение SBC только в том случае, если доменная часть своего полного доменного имени соответствует одному из \*доменов, зарегистрированных в вашем клиенте, за исключением onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2ca12-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="2ca12-135">Использование \*доменных имен onmicrosoft.com не поддерживается для полного доменного имени SBC.</span><span class="sxs-lookup"><span data-stu-id="2ca12-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="2ca12-136">Например, если у вас есть два доменных имен:</span><span class="sxs-lookup"><span data-stu-id="2ca12-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="2ca12-137">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="2ca12-137">**contoso**.com</span></span><br/><span data-ttu-id="2ca12-138">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2ca12-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="2ca12-139">Для имени SBC можно использовать имя sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2ca12-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="2ca12-140">При попытке связывания SBC с именем SBC. contoso. ABC система не позволит вам, так как домен не принадлежит этому клиенту.</span><span class="sxs-lookup"><span data-stu-id="2ca12-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="2ca12-141">Помимо домена, зарегистрированного в клиенте, важно, чтобы пользователь с этим доменом и назначенной лицензией E3 или водо.</span><span class="sxs-lookup"><span data-stu-id="2ca12-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="2ca12-142">В противном случае появится следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="2ca12-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="2ca12-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="2ca12-143"></span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="2ca12-144">Дает</span><span class="sxs-lookup"><span data-stu-id="2ca12-144">Returns:</span></span>
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
<span data-ttu-id="2ca12-145">В процессе связывания можно настроить дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="2ca12-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="2ca12-146">Однако в предыдущем примере показаны только минимально необходимые параметры.</span><span class="sxs-lookup"><span data-stu-id="2ca12-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="2ca12-147">В таблице ниже перечислены дополнительные параметры, которые можно использовать при настройке параметров для`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="2ca12-147">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="2ca12-148">Обязательно?</span><span class="sxs-lookup"><span data-stu-id="2ca12-148">Required?</span></span>|<span data-ttu-id="2ca12-149">Имя</span><span class="sxs-lookup"><span data-stu-id="2ca12-149">Name</span></span>|<span data-ttu-id="2ca12-150">Описание</span><span class="sxs-lookup"><span data-stu-id="2ca12-150">Description</span></span>|<span data-ttu-id="2ca12-151">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="2ca12-151">Default</span></span>|<span data-ttu-id="2ca12-152">Возможные значения</span><span class="sxs-lookup"><span data-stu-id="2ca12-152">Possible values</span></span>|<span data-ttu-id="2ca12-153">Тип и ограничения</span><span class="sxs-lookup"><span data-stu-id="2ca12-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2ca12-154">Да</span><span class="sxs-lookup"><span data-stu-id="2ca12-154">Yes</span></span>|<span data-ttu-id="2ca12-155">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="2ca12-155">FQDN</span></span>|<span data-ttu-id="2ca12-156">Полное доменное имя SBC</span><span class="sxs-lookup"><span data-stu-id="2ca12-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="2ca12-157">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-157">None</span></span>|<span data-ttu-id="2ca12-158">Нонефкдн имя, ограничение 63 символов</span><span class="sxs-lookup"><span data-stu-id="2ca12-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="2ca12-159">Строка, список допустимых и недопустимых символов в [соглашениях об именовании в Active Directory для компьютеров, доменов, сайтов и подразделений](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="2ca12-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="2ca12-160">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-160">No</span></span>|<span data-ttu-id="2ca12-161">медиабипасс</span><span class="sxs-lookup"><span data-stu-id="2ca12-161">MediaBypass</span></span> |<span data-ttu-id="2ca12-162">Параметр, обозначенный SBC, поддерживает обход мультимедиа, и администратор хочет использовать его.</span><span class="sxs-lookup"><span data-stu-id="2ca12-162">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="2ca12-163">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-163">None</span></span>|<span data-ttu-id="2ca12-164">Верно</span><span class="sxs-lookup"><span data-stu-id="2ca12-164">True</span></span><br/><span data-ttu-id="2ca12-165">False</span><span class="sxs-lookup"><span data-stu-id="2ca12-165">False</span></span>|<span data-ttu-id="2ca12-166">Boolean</span><span class="sxs-lookup"><span data-stu-id="2ca12-166">Boolean</span></span>|
|<span data-ttu-id="2ca12-167">Да</span><span class="sxs-lookup"><span data-stu-id="2ca12-167">Yes</span></span>|<span data-ttu-id="2ca12-168">сипсигналлингпорт</span><span class="sxs-lookup"><span data-stu-id="2ca12-168">SipSignallingPort</span></span> |<span data-ttu-id="2ca12-169">Порт прослушивания, используемый для связи с прямыми службами маршрутизации с помощью протокола TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="2ca12-169">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="2ca12-170">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-170">None</span></span>|<span data-ttu-id="2ca12-171">Любой порт</span><span class="sxs-lookup"><span data-stu-id="2ca12-171">Any port</span></span>|<span data-ttu-id="2ca12-172">от 0 до 65535</span><span class="sxs-lookup"><span data-stu-id="2ca12-172">0 to 65535</span></span> |
|<span data-ttu-id="2ca12-173">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-173">No</span></span>|<span data-ttu-id="2ca12-174">фаиловертимесекондс</span><span class="sxs-lookup"><span data-stu-id="2ca12-174">FailoverTimeSeconds</span></span> |<span data-ttu-id="2ca12-175">Если для этого параметра установлено значение 10 (значения по умолчанию), исходящие вызовы, которые не ответили шлюзом в течение 10 секунд, пересылаются на следующую доступную магистраль. Если дополнительных каналов связи нет, Звонок автоматически удаляется.</span><span class="sxs-lookup"><span data-stu-id="2ca12-175">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="2ca12-176">В организации с медленными ответами сетей и шлюзов, это может приводить к необязательному пропуску вызовов.</span><span class="sxs-lookup"><span data-stu-id="2ca12-176">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="2ca12-177">Значение по умолчанию — 10.</span><span class="sxs-lookup"><span data-stu-id="2ca12-177">The default value is 10.</span></span>|<span data-ttu-id="2ca12-178">5-10</span><span class="sxs-lookup"><span data-stu-id="2ca12-178">10</span></span>|<span data-ttu-id="2ca12-179">Число</span><span class="sxs-lookup"><span data-stu-id="2ca12-179">Number</span></span>|<span data-ttu-id="2ca12-180">Типом</span><span class="sxs-lookup"><span data-stu-id="2ca12-180">Int</span></span>|
|<span data-ttu-id="2ca12-181">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-181">No</span></span>|<span data-ttu-id="2ca12-182">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="2ca12-182">ForwardCallHistory</span></span> |<span data-ttu-id="2ca12-183">Означает, будет ли переадресовываться по магистральному каналу сведения о журнале звонков.</span><span class="sxs-lookup"><span data-stu-id="2ca12-183">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="2ca12-184">Если этот флажок установлен, прокси-сервер Office 365 КТСОП отправляет два заголовка: журнал — информация и на которую указывает обращение.</span><span class="sxs-lookup"><span data-stu-id="2ca12-184">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="2ca12-185">Значением по умолчанию является **ложь** ($false).</span><span class="sxs-lookup"><span data-stu-id="2ca12-185">The default value is **False** ($False).</span></span> |<span data-ttu-id="2ca12-186">False</span><span class="sxs-lookup"><span data-stu-id="2ca12-186">False</span></span>|<span data-ttu-id="2ca12-187">Верно</span><span class="sxs-lookup"><span data-stu-id="2ca12-187">True</span></span><br/><span data-ttu-id="2ca12-188">False</span><span class="sxs-lookup"><span data-stu-id="2ca12-188">False</span></span>|<span data-ttu-id="2ca12-189">Boolean</span><span class="sxs-lookup"><span data-stu-id="2ca12-189">Boolean</span></span>|
|<span data-ttu-id="2ca12-190">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-190">No</span></span>|<span data-ttu-id="2ca12-191">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="2ca12-191">ForwardPAI</span></span>|<span data-ttu-id="2ca12-192">Указывает, будет ли переадресовываться заголовок P-Asserted-Identity (PAI) одновременно с вызовом.</span><span class="sxs-lookup"><span data-stu-id="2ca12-192">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="2ca12-193">Заголовок PAI предоставляет способ проверки удостоверения абонемента.</span><span class="sxs-lookup"><span data-stu-id="2ca12-193">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="2ca12-194">Если включено, будет также отправлен заголовок "Конфиденциальность: ИД".</span><span class="sxs-lookup"><span data-stu-id="2ca12-194">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="2ca12-195">Значением по умолчанию является **ложь** ($false).</span><span class="sxs-lookup"><span data-stu-id="2ca12-195">The default value is **False** ($False).</span></span>|<span data-ttu-id="2ca12-196">False</span><span class="sxs-lookup"><span data-stu-id="2ca12-196">False</span></span>|<span data-ttu-id="2ca12-197">Верно</span><span class="sxs-lookup"><span data-stu-id="2ca12-197">True</span></span><br/><span data-ttu-id="2ca12-198">False</span><span class="sxs-lookup"><span data-stu-id="2ca12-198">False</span></span>|<span data-ttu-id="2ca12-199">Boolean</span><span class="sxs-lookup"><span data-stu-id="2ca12-199">Boolean</span></span>|
|<span data-ttu-id="2ca12-200">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-200">No</span></span>|<span data-ttu-id="2ca12-201">сендсипоптионс</span><span class="sxs-lookup"><span data-stu-id="2ca12-201">SendSIPOptions</span></span> |<span data-ttu-id="2ca12-202">Определяет, будет ли SBC или не будет отправлять параметры SIP.</span><span class="sxs-lookup"><span data-stu-id="2ca12-202">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="2ca12-203">Если отключено, SBC будет исключен из системы мониторинга и оповещения.</span><span class="sxs-lookup"><span data-stu-id="2ca12-203">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="2ca12-204">Настоятельно рекомендуем включить параметры SIP.</span><span class="sxs-lookup"><span data-stu-id="2ca12-204">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="2ca12-205">Значение по умолчанию — **true**.</span><span class="sxs-lookup"><span data-stu-id="2ca12-205">Default value is **True**.</span></span> |<span data-ttu-id="2ca12-206">Верно</span><span class="sxs-lookup"><span data-stu-id="2ca12-206">True</span></span>|<span data-ttu-id="2ca12-207">Верно</span><span class="sxs-lookup"><span data-stu-id="2ca12-207">True</span></span><br/><span data-ttu-id="2ca12-208">False</span><span class="sxs-lookup"><span data-stu-id="2ca12-208">False</span></span>|<span data-ttu-id="2ca12-209">Boolean</span><span class="sxs-lookup"><span data-stu-id="2ca12-209">Boolean</span></span>|
|<span data-ttu-id="2ca12-210">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-210">No</span></span>|<span data-ttu-id="2ca12-211">максконкуррентсессионс</span><span class="sxs-lookup"><span data-stu-id="2ca12-211">MaxConcurrentSessions</span></span> |<span data-ttu-id="2ca12-212">Используется системой оповещения.</span><span class="sxs-lookup"><span data-stu-id="2ca12-212">Used by alerting system.</span></span> <span data-ttu-id="2ca12-213">Если задано какое либо значение, система оповещения создаст оповещение для администратора клиента, если число параллельных сеансов составляет 90% или выше этого значения.</span><span class="sxs-lookup"><span data-stu-id="2ca12-213">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="2ca12-214">Если параметр не задан, оповещения не создаются.</span><span class="sxs-lookup"><span data-stu-id="2ca12-214">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="2ca12-215">Тем не менее, система мониторинга будет сообщать количество параллельных сеансов каждые 24 часа.</span><span class="sxs-lookup"><span data-stu-id="2ca12-215">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="2ca12-216">Значения</span><span class="sxs-lookup"><span data-stu-id="2ca12-216">Null</span></span>|<span data-ttu-id="2ca12-217">Значения</span><span class="sxs-lookup"><span data-stu-id="2ca12-217">Null</span></span><br/><span data-ttu-id="2ca12-218">от 1 до 100 000</span><span class="sxs-lookup"><span data-stu-id="2ca12-218">1 to 100,000</span></span> ||
|<span data-ttu-id="2ca12-219">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-219">No</span></span>|<span data-ttu-id="2ca12-220">медиарелайраутинглокатионоверриде</span><span class="sxs-lookup"><span data-stu-id="2ca12-220">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="2ca12-221">Позволяет выбрать путь для мультимедиа вручную.</span><span class="sxs-lookup"><span data-stu-id="2ca12-221">Allows selecting path for media manually.</span></span> <span data-ttu-id="2ca12-222">Прямая маршрутизация назначает центр обработки данных для пути к носителю, основываясь на общедоступном IP-адресе SBC.</span><span class="sxs-lookup"><span data-stu-id="2ca12-222">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="2ca12-223">Мы всегда Выбери ближайший вариант в центре обработки данных SBC.</span><span class="sxs-lookup"><span data-stu-id="2ca12-223">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="2ca12-224">Тем не менее, в некоторых случаях публичный IP-адрес, например диапазон US, может быть назначен для SBC, находящегося в Европе.</span><span class="sxs-lookup"><span data-stu-id="2ca12-224">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="2ca12-225">В этом случае мы будем использовать не оптимальный путь к носителю.</span><span class="sxs-lookup"><span data-stu-id="2ca12-225">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="2ca12-226">Этот параметр позволяет вручную настроить предпочтительный регион для передачи данных мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="2ca12-226">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="2ca12-227">Мы рекомендуем установить этот параметр только в том случае, если журнал звонков явно указывает на то, что автоматическое назначение центра обработки данных для пути к носителю не присвоено ближайшему элементу в центре обработки данных SBC.</span><span class="sxs-lookup"><span data-stu-id="2ca12-227">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="2ca12-228">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-228">None</span></span>|<span data-ttu-id="2ca12-229">Коды стран в формате ISO</span><span class="sxs-lookup"><span data-stu-id="2ca12-229">Country codes in ISO format</span></span>||
|<span data-ttu-id="2ca12-230">Нет</span><span class="sxs-lookup"><span data-stu-id="2ca12-230">No</span></span>|<span data-ttu-id="2ca12-231">Включено</span><span class="sxs-lookup"><span data-stu-id="2ca12-231">Enabled</span></span>|<span data-ttu-id="2ca12-232">Используется для включения этого SBC для исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="2ca12-232">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="2ca12-233">Можно использовать для временного удаления SBC, в то время как он обновляется или идет на обслуживание.</span><span class="sxs-lookup"><span data-stu-id="2ca12-233">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="2ca12-234">False</span><span class="sxs-lookup"><span data-stu-id="2ca12-234">False</span></span>|<span data-ttu-id="2ca12-235">Верно</span><span class="sxs-lookup"><span data-stu-id="2ca12-235">True</span></span><br/><span data-ttu-id="2ca12-236">False</span><span class="sxs-lookup"><span data-stu-id="2ca12-236">False</span></span>|<span data-ttu-id="2ca12-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="2ca12-237">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="2ca12-238">Проверка связывания SBC</span><span class="sxs-lookup"><span data-stu-id="2ca12-238">Verify the SBC pairing</span></span> 

<span data-ttu-id="2ca12-239">Проверьте подключение:</span><span class="sxs-lookup"><span data-stu-id="2ca12-239">Verify the connection:</span></span> 
- <span data-ttu-id="2ca12-240">Убедитесь, что SBC есть в списке парных SBCs.</span><span class="sxs-lookup"><span data-stu-id="2ca12-240">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="2ca12-241">Проверьте параметры SIP.</span><span class="sxs-lookup"><span data-stu-id="2ca12-241">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="2ca12-242">Проверка того, что SBC находится в списке парных SBCs</span><span class="sxs-lookup"><span data-stu-id="2ca12-242">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="2ca12-243">После связывания SBC убедитесь, что SBC представлен в списке парных SBCs, выполнив следующую команду в удаленном сеансе PowerShell.`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="2ca12-243">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="2ca12-244">Попарный шлюз должен отображаться в списке, как показано в приведенном ниже примере, и убедитесь, что параметр *Enabled* отображает значение **Истина**.</span><span class="sxs-lookup"><span data-stu-id="2ca12-244">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="2ca12-245">Ведите</span><span class="sxs-lookup"><span data-stu-id="2ca12-245">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="2ca12-246">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="2ca12-246">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="2ca12-247">Проверка потока параметров SIP</span><span class="sxs-lookup"><span data-stu-id="2ca12-247">Validate SIP Options flow</span></span> 

<span data-ttu-id="2ca12-248">Для проверки связывания с помощью исходящих параметров SIP используйте интерфейс управления SBC и убедитесь, что SBC получает ответы на 200 ОК в сообщениях с параметрами исходящих параметров.</span><span class="sxs-lookup"><span data-stu-id="2ca12-248">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="2ca12-249">Когда прямая маршрутизация видит параметры входящего трафика, она начнет отправлять сообщения параметров исходящих модулей SIP в FQDN, настроенном в поле "заголовок" в сообщении "параметры входящих".</span><span class="sxs-lookup"><span data-stu-id="2ca12-249">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="2ca12-250">Для проверки связывания с помощью параметров входящего SIP используйте интерфейс управления SBC и посмотрите, что SBC отправляет ответы на сообщения параметров, поступившие от Direct Routing, и что код ответа, который он отправляет, — 200 ОК.</span><span class="sxs-lookup"><span data-stu-id="2ca12-250">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="2ca12-251">Включение поддержки прямой маршрутизации для пользователей</span><span class="sxs-lookup"><span data-stu-id="2ca12-251">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="2ca12-252">Когда вы будете готовы включить пользователей для службы прямой маршрутизации, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2ca12-252">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="2ca12-253">Создание пользователя в Office 365 и назначение лицензии на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="2ca12-253">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="2ca12-254">Убедитесь в том, что пользователь размещен в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2ca12-254">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="2ca12-255">Настройте номер телефона и включите поддержку корпоративной голосовой и голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="2ca12-255">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="2ca12-256">Настройка голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="2ca12-256">Configure voice routing.</span></span> <span data-ttu-id="2ca12-257">Маршрут будет проверяться автоматически.</span><span class="sxs-lookup"><span data-stu-id="2ca12-257">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="2ca12-258">Создание пользователя в Office 365 и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="2ca12-258">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="2ca12-259">Существует два способа создания нового пользователя в Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ca12-259">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="2ca12-260">Однако мы рекомендуем выбрать и использовать один из вариантов для устранения проблем с маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="2ca12-260">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="2ca12-261">Создайте пользователя в локальной службе каталогов Active Directory и синхронизируйте пользователя с облаком.</span><span class="sxs-lookup"><span data-stu-id="2ca12-261">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="2ca12-262">Откройте раздел [интеграция локальных каталогов с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="2ca12-262">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="2ca12-263">Создайте пользователя прямо на портале администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ca12-263">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="2ca12-264">В разделе [Добавление пользователей по отдельности или массово в Office 365 — Справка для администраторов](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="2ca12-264">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="2ca12-265">Если развертывание Skype для бизнеса Online осуществляется совместно со Skype для бизнеса 2015 или Lync 2010/2013 локально, единственным поддерживаемым вариантом будет создание пользователя в локальной службе каталогов Active Directory и синхронизация пользователя с облаком (вариант 1).</span><span class="sxs-lookup"><span data-stu-id="2ca12-265">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="2ca12-266">Обязательные лицензии:</span><span class="sxs-lookup"><span data-stu-id="2ca12-266">Required licenses:</span></span> 

- <span data-ttu-id="2ca12-267">Office 365 Корпоративная E3 (в том числе SfB Plan2, Exchange Plan2 и Teams) + телефонная система</span><span class="sxs-lookup"><span data-stu-id="2ca12-267">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="2ca12-268">Office 365 Корпоративная + + + (в том числе SfB Plan2, Exchange Plan2, Teams и Phone System)</span><span class="sxs-lookup"><span data-stu-id="2ca12-268">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="2ca12-269">Необязательные лицензии:</span><span class="sxs-lookup"><span data-stu-id="2ca12-269">Optional licenses:</span></span> 

- <span data-ttu-id="2ca12-270">План звонков</span><span class="sxs-lookup"><span data-stu-id="2ca12-270">Calling Plan</span></span> 
- <span data-ttu-id="2ca12-271">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="2ca12-271">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="2ca12-272">Убедитесь в том, что пользователь размещен в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2ca12-272">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="2ca12-273">Для прямой маршрутизации требуется, чтобы пользователь был подключен в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="2ca12-273">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="2ca12-274">Чтобы проверить это, Взгляните на параметр Регистрарпул.</span><span class="sxs-lookup"><span data-stu-id="2ca12-274">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="2ca12-275">В домене infra.lync.com должно быть значение.</span><span class="sxs-lookup"><span data-stu-id="2ca12-275">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="2ca12-276">Подключитесь к удаленной оболочке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ca12-276">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="2ca12-277">Выдайте команду:</span><span class="sxs-lookup"><span data-stu-id="2ca12-277">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="2ca12-278">Настройка номера телефона и включение корпоративной голосовой и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="2ca12-278">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="2ca12-279">После создания пользователя и назначения лицензии следует настроить свой номер телефона и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="2ca12-279">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="2ca12-280">Это можно сделать одним из шагов.</span><span class="sxs-lookup"><span data-stu-id="2ca12-280">This can be done in one step.</span></span> 

<span data-ttu-id="2ca12-281">Чтобы добавить номер телефона и включить голосовую почту, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2ca12-281">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="2ca12-282">Подключитесь к удаленному сеансу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ca12-282">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="2ca12-283">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="2ca12-283">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="2ca12-284">Например, чтобы добавить номер телефона пользователя "Спенцер Low", введите следующее:</span><span class="sxs-lookup"><span data-stu-id="2ca12-284">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="2ca12-285">Номер телефона должен быть настроен как полный E. 164 номер телефона с кодом страны.</span><span class="sxs-lookup"><span data-stu-id="2ca12-285">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="2ca12-286">Если в качестве номера телефона пользователя используется локальный, используйте локальную среду управления и панель управления Skype для бизнеса, чтобы настроить номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="2ca12-286">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="2ca12-287">Настройка голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="2ca12-287">Configure Voice Routing</span></span> 

<span data-ttu-id="2ca12-288">В телефонной системе Microsoft есть механизм маршрутизации, который позволяет отправлять звонки на определенный SBC, основанный на следующих устройствах:</span><span class="sxs-lookup"><span data-stu-id="2ca12-288">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="2ca12-289">Названный шаблон номера</span><span class="sxs-lookup"><span data-stu-id="2ca12-289">Called number pattern</span></span> 
- <span data-ttu-id="2ca12-290">Вызываемый шаблон номера + определенный пользователь, который выполняет Звонок</span><span class="sxs-lookup"><span data-stu-id="2ca12-290">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="2ca12-291">SBCs можно назначить активными и архивировать.</span><span class="sxs-lookup"><span data-stu-id="2ca12-291">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="2ca12-292">Это означает, что если объект SBC, настроенный как активный для этого шаблона номера, или шаблон числа + определенного пользователя, недоступен, звонки будут перенаправляться в одноэлементный объект SBC.</span><span class="sxs-lookup"><span data-stu-id="2ca12-292">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="2ca12-293">Маршрутизация звонков состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="2ca12-293">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="2ca12-294">Политика маршрутизации голосовой связи — контейнер использования КТСОП; может назначаться пользователю или нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="2ca12-294">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="2ca12-295">Использование PSTN — контейнер для голосовых маршрутов и использование PSTN; могут совместно использоваться в разных политиках голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="2ca12-295">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="2ca12-296">Маршруты голосовой связи — шаблон номера и набор шлюзов в Интернет-шлюзах, которые должны использоваться для звонков, где номер звонка соответствует шаблону</span><span class="sxs-lookup"><span data-stu-id="2ca12-296">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="2ca12-297">Сетевой шлюз PSTN — указатель на SBC, также хранит конфигурацию, которая применяется при помещении звонка через SBC, например переадресация с подлинным идентификатором P-утвержденного (паи) или Предпочтительные кодеки. можно добавлять в Голосовые маршруты</span><span class="sxs-lookup"><span data-stu-id="2ca12-297">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="2ca12-298">Создание политики голосовой маршрутизации с использованием одной PSTN</span><span class="sxs-lookup"><span data-stu-id="2ca12-298">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="2ca12-299">На приведенной ниже схеме показаны два примера политик маршрутизации голосовой связи в потоке вызовов.</span><span class="sxs-lookup"><span data-stu-id="2ca12-299">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="2ca12-300">**Поток звонков 1 (слева):** Если пользователь выполняет вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов передается на SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2ca12-300">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="2ca12-301">Если ни sbc1.contoso.biz, ни sbc2.contoso.biz недоступны, вызов отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="2ca12-301">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="2ca12-302">**Направление звонка 2 (справа):** Если пользователь совершает вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов сначала пересылается на SBC sbc1.contoso.biz или sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2ca12-302">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="2ca12-303">Если ни один из SBC недоступен, будет применяться маршрут с более низким приоритетом (sbc3.contoso.biz и sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="2ca12-303">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="2ca12-304">Если ни одна из этих SBCs недоступна, вызов отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="2ca12-304">If none of the SBCs are available, the call is dropped.</span></span> 

![Примеры политики голосовой маршрутизации](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="2ca12-306">В обоих примерах, когда маршрут голоса назначается приоритетами, однобайтовые данные маршрутов выполняются в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="2ca12-306">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2ca12-307">Если у пользователя нет лицензии на план звонков Microsoft, звонки на любое число, кроме номеров, соответствующих шаблонам + 1 425 XXX XX XX или + 1 206 XXX XX XX, удаляются.</span><span class="sxs-lookup"><span data-stu-id="2ca12-307">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="2ca12-308">Если у пользователя есть лицензия на план звонков, этот звонок автоматически маршрутизируется согласно политикам плана вызовов Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ca12-308">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="2ca12-309">План звонков Microsoft автоматически применяется к последнему маршруту для всех пользователей с лицензией на план звонков Microsoft и не требует дополнительной настройки маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="2ca12-309">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="2ca12-310">В примере на приведенной ниже схеме маршрут голосовой связи добавляется для отправки звонков на все остальные звонки в США и Канаде (звонки, находящиеся под названием "номер" + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="2ca12-310">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Политика маршрутизации голосовой связи с третьим маршрутом](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="2ca12-312">Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="2ca12-312">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="2ca12-313">Если ничего не соответствует шаблонам, созданным администратором в онлайновых голосовых маршрутах, направьте его через план звонков Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ca12-313">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="2ca12-314">Если у пользователя есть только телефонная система Microsoft, вызов отклоняется из-за того, что нет доступных правил сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2ca12-314">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2ca12-315">Значение приоритета для маршрута "Other + 1" в этом случае не имеет значения, так как есть только один маршрут, соответствующий шаблону + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="2ca12-315">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="2ca12-316">Если пользователь вызывает + 1 324 567 89 89, а оба sbc5.contoso.biz и sbc6.contoso.biz недоступны, Звонок отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="2ca12-316">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="2ca12-317">В приведенной ниже таблице перечислены конфигурации с тремя голосовыми маршрутами.</span><span class="sxs-lookup"><span data-stu-id="2ca12-317">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="2ca12-318">В этом примере все три маршрута являются частью одного и того же использования КТСОП "США и Канада".</span><span class="sxs-lookup"><span data-stu-id="2ca12-318">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="2ca12-319">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="2ca12-319">**PSTN usage**</span></span>|<span data-ttu-id="2ca12-320">**Маршрут голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="2ca12-320">**Voice route**</span></span>|<span data-ttu-id="2ca12-321">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="2ca12-321">**Number pattern**</span></span>|<span data-ttu-id="2ca12-322">**Priority**</span><span class="sxs-lookup"><span data-stu-id="2ca12-322">**Priority**</span></span>|<span data-ttu-id="2ca12-323">**БАЙТОВ**</span><span class="sxs-lookup"><span data-stu-id="2ca12-323">**SBC**</span></span>|<span data-ttu-id="2ca12-324">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2ca12-324">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2ca12-325">Только для США</span><span class="sxs-lookup"><span data-stu-id="2ca12-325">US only</span></span>|<span data-ttu-id="2ca12-326">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="2ca12-326">"Redmond 1"</span></span>|<span data-ttu-id="2ca12-327">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="2ca12-327">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2ca12-328">1</span><span class="sxs-lookup"><span data-stu-id="2ca12-328">1</span></span>|<span data-ttu-id="2ca12-329">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-329">sbc1.contoso.biz</span></span><br/><span data-ttu-id="2ca12-330">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-330">sbc2.contoso.biz</span></span>|<span data-ttu-id="2ca12-331">Активный маршрут для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2ca12-331">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2ca12-332">Только для США</span><span class="sxs-lookup"><span data-stu-id="2ca12-332">US only</span></span>|<span data-ttu-id="2ca12-333">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="2ca12-333">"Redmond 2"</span></span>|<span data-ttu-id="2ca12-334">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="2ca12-334">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2ca12-335">2</span><span class="sxs-lookup"><span data-stu-id="2ca12-335">2</span></span>|<span data-ttu-id="2ca12-336">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-336">sbc3.contoso.biz</span></span><br/><span data-ttu-id="2ca12-337">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-337">sbc4.contoso.biz</span></span>|<span data-ttu-id="2ca12-338">Маршрут резервного копирования для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2ca12-338">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2ca12-339">Только для США</span><span class="sxs-lookup"><span data-stu-id="2ca12-339">US only</span></span>|<span data-ttu-id="2ca12-340">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="2ca12-340">"Other +1"</span></span>|<span data-ttu-id="2ca12-341">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="2ca12-341">^\\+1(\d{10})$</span></span>|<span data-ttu-id="2ca12-342">3</span><span class="sxs-lookup"><span data-stu-id="2ca12-342">3</span></span>|<span data-ttu-id="2ca12-343">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-343">sbc5.contoso.biz</span></span><br/><span data-ttu-id="2ca12-344">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-344">sbc6.contoso.biz</span></span>|<span data-ttu-id="2ca12-345">Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="2ca12-345">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="2ca12-346">Все маршруты связаны с использованием КТСОП "США и Канада", а использование КТСОП связано с политикой голосовой маршрутизации "только США".</span><span class="sxs-lookup"><span data-stu-id="2ca12-346">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="2ca12-347">В этом примере политика голосовой маршрутизации назначена пользователю Спенцер Low.</span><span class="sxs-lookup"><span data-stu-id="2ca12-347">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="2ca12-348">Примеры маршрутов звонков</span><span class="sxs-lookup"><span data-stu-id="2ca12-348">Examples of call routes</span></span>

<span data-ttu-id="2ca12-349">В приведенном ниже примере мы покажем, как настроить маршруты, использование PSTN и политики маршрутизации, а также назначить политику для пользователя.</span><span class="sxs-lookup"><span data-stu-id="2ca12-349">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="2ca12-350">**Действие 1:** Создайте использование КТСОП "США и Канада".</span><span class="sxs-lookup"><span data-stu-id="2ca12-350">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="2ca12-351">В удаленном сеансе PowerShell в Skype для бизнеса введите:</span><span class="sxs-lookup"><span data-stu-id="2ca12-351">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="2ca12-352">Убедитесь в том, что использование было создано путем ввода:</span><span class="sxs-lookup"><span data-stu-id="2ca12-352">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="2ca12-353">Возвращающий список имен, которые могут быть усечены:</span><span class="sxs-lookup"><span data-stu-id="2ca12-353">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="2ca12-354">В примере ниже показано, как можно просмотреть результаты выполнения команды `(Get-CSOnlinePSTNUsage).usage` PowerShell для отображения полных имен (не усеченных).</span><span class="sxs-lookup"><span data-stu-id="2ca12-354">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
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

<span data-ttu-id="2ca12-355">**Шаг 2.** В сеансе PowerShell в Skype для бизнеса Online создайте три маршрута: Redmond 1, Redmond 2 и другой + 1, как описано в предыдущей таблице.</span><span class="sxs-lookup"><span data-stu-id="2ca12-355">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="2ca12-356">Чтобы создать маршрут "Redmond 1", введите:</span><span class="sxs-lookup"><span data-stu-id="2ca12-356">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="2ca12-357">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="2ca12-357">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
</pre>
<span data-ttu-id="2ca12-358">Чтобы создать маршрут на 2 Redmond, введите:</span><span class="sxs-lookup"><span data-stu-id="2ca12-358">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="2ca12-359">Чтобы создать другой маршрут + 1, введите:</span><span class="sxs-lookup"><span data-stu-id="2ca12-359">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="2ca12-360">Убедитесь, что регулярное выражение в атрибуте Нумберпаттерн является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="2ca12-360">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="2ca12-361">Вы можете протестировать его с помощью этого веб-сайта:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="2ca12-361">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="2ca12-362">В некоторых случаях необходимо перенаправлять все вызовы на один и тот же SBC; Пожалуйста, используйте-Нумберпаттерн ". \*"</span><span class="sxs-lookup"><span data-stu-id="2ca12-362">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="2ca12-363">Перенаправлять все вызовы в один и тот же SBC</span><span class="sxs-lookup"><span data-stu-id="2ca12-363">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="2ca12-364">Проверьте, правильно ли вы настроили маршрут, выполнив команду `Get-CSOnlineVoiceRoute` PowerShell, используя указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="2ca12-364">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="2ca12-365">Что должно вернуть:</span><span class="sxs-lookup"><span data-stu-id="2ca12-365">Which should return:</span></span>
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

<span data-ttu-id="2ca12-366">В примере для маршрута "Other + 1" автоматически назначается приоритет 4.</span><span class="sxs-lookup"><span data-stu-id="2ca12-366">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="2ca12-367">**Шаг 3.** Создайте политику голосовой маршрутизации "только США" и добавьте в политику использование КТСОП "США и Канада".</span><span class="sxs-lookup"><span data-stu-id="2ca12-367">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="2ca12-368">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="2ca12-368">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="2ca12-369">Результат показан в этом примере:</span><span class="sxs-lookup"><span data-stu-id="2ca12-369">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="2ca12-370">**Шаг 4:** Предоставьте пользователю Спенцер низкий уровень политики голосовой маршрутизации с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ca12-370">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="2ca12-371">В сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="2ca12-371">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="2ca12-372">Чтобы проверить назначение политики, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2ca12-372">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="2ca12-373">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="2ca12-373">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="2ca12-374">Создание политики голосовой маршрутизации с несколькими использованием PSTN</span><span class="sxs-lookup"><span data-stu-id="2ca12-374">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="2ca12-375">Политика маршрутизации голосовой связи, созданная ранее, позволяет звонить только в США и Канаде (за исключением случаев, когда у пользователя также выделена лицензия на план звонков Microsoft).</span><span class="sxs-lookup"><span data-stu-id="2ca12-375">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="2ca12-376">В приведенном ниже примере вы можете создать политику маршрутизации голосовой связи "нет ограничений".</span><span class="sxs-lookup"><span data-stu-id="2ca12-376">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="2ca12-377">Политика повторно использует использование КТСОП "США и Канада", созданное в предыдущем примере, а также новую использование PSTN "Международная".</span><span class="sxs-lookup"><span data-stu-id="2ca12-377">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="2ca12-378">При этом все другие звонки на SBCs sbc2.contoso.biz и sbc5.contoso.biz переправляются.</span><span class="sxs-lookup"><span data-stu-id="2ca12-378">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="2ca12-379">Приведенные примеры применяют политику "только для США" для пользователя "Спенцер Low" и никаких ограничений для пользователя "John лесу".</span><span class="sxs-lookup"><span data-stu-id="2ca12-379">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="2ca12-380">Спенцер низкий – звонки разрешены только в США и Канаде.</span><span class="sxs-lookup"><span data-stu-id="2ca12-380">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="2ca12-381">При обращении к диапазону номеров Redmond необходимо использовать определенный набор SBC.</span><span class="sxs-lookup"><span data-stu-id="2ca12-381">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="2ca12-382">Номера, не относящиеся к США, не будут маршрутизироваться, если пользователю не назначена лицензия на план звонков.</span><span class="sxs-lookup"><span data-stu-id="2ca12-382">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="2ca12-383">Джон лесу – звонки разрешены любому номеру.</span><span class="sxs-lookup"><span data-stu-id="2ca12-383">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="2ca12-384">При обращении к диапазону номеров Redmond необходимо использовать определенный набор SBC.</span><span class="sxs-lookup"><span data-stu-id="2ca12-384">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="2ca12-385">Номера, не относящиеся к США, будут маршрутизироваться через sbc2.contoso.biz и sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2ca12-385">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Политика маршрутизации голосовой связи, назначенная пользователю Спенцер низкий](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="2ca12-387">Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут.</span><span class="sxs-lookup"><span data-stu-id="2ca12-387">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="2ca12-388">Если ничего не соответствует шаблонам, созданным администратором в онлайновых голосовых маршрутах, направьте его через план звонков Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ca12-388">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="2ca12-389">Если у пользователя есть только телефонная система Microsoft, вызов отклоняется из-за того, что нет доступных правил сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2ca12-389">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Политика маршрутизации голосовой связи, назначенная пользователю John лесу](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="2ca12-391">В таблице ниже приведено краткое описание политики маршрутизации "без ограничений" и для голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="2ca12-391">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="2ca12-392">**Использование ТСОП**</span><span class="sxs-lookup"><span data-stu-id="2ca12-392">**PSTN usage**</span></span>|<span data-ttu-id="2ca12-393">**Маршрут голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="2ca12-393">**Voice route**</span></span>|<span data-ttu-id="2ca12-394">**Шаблон номеров**</span><span class="sxs-lookup"><span data-stu-id="2ca12-394">**Number pattern**</span></span>|<span data-ttu-id="2ca12-395">**Priority**</span><span class="sxs-lookup"><span data-stu-id="2ca12-395">**Priority**</span></span>|<span data-ttu-id="2ca12-396">**БАЙТОВ**</span><span class="sxs-lookup"><span data-stu-id="2ca12-396">**SBC**</span></span>|<span data-ttu-id="2ca12-397">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2ca12-397">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2ca12-398">Только для США</span><span class="sxs-lookup"><span data-stu-id="2ca12-398">US Only</span></span>|<span data-ttu-id="2ca12-399">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="2ca12-399">"Redmond 1"</span></span>|<span data-ttu-id="2ca12-400">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="2ca12-400">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2ca12-401">1</span><span class="sxs-lookup"><span data-stu-id="2ca12-401">1</span></span>|<span data-ttu-id="2ca12-402">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-402">sbc1.contoso.biz</span></span><br/><span data-ttu-id="2ca12-403">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-403">sbc2.contoso.biz</span></span>|<span data-ttu-id="2ca12-404">Активный маршрут для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2ca12-404">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2ca12-405">Только для США</span><span class="sxs-lookup"><span data-stu-id="2ca12-405">US Only</span></span>|<span data-ttu-id="2ca12-406">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="2ca12-406">"Redmond 2"</span></span>|<span data-ttu-id="2ca12-407">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="2ca12-407">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2ca12-408">2</span><span class="sxs-lookup"><span data-stu-id="2ca12-408">2</span></span>|<span data-ttu-id="2ca12-409">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-409">sbc3.contoso.biz</span></span><br/><span data-ttu-id="2ca12-410">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-410">sbc4.contoso.biz</span></span>|<span data-ttu-id="2ca12-411">Маршрут резервного копирования для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2ca12-411">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2ca12-412">Только для США</span><span class="sxs-lookup"><span data-stu-id="2ca12-412">US Only</span></span>|<span data-ttu-id="2ca12-413">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="2ca12-413">"Other +1"</span></span>|<span data-ttu-id="2ca12-414">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="2ca12-414">^\\+1(\d{10})$</span></span>|<span data-ttu-id="2ca12-415">3</span><span class="sxs-lookup"><span data-stu-id="2ca12-415">3</span></span>|<span data-ttu-id="2ca12-416">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-416">sbc5.contoso.biz</span></span><br/><span data-ttu-id="2ca12-417">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-417">sbc6>.contoso.biz</span></span>|<span data-ttu-id="2ca12-418">Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="2ca12-418">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="2ca12-419">International</span><span class="sxs-lookup"><span data-stu-id="2ca12-419">International</span></span>|<span data-ttu-id="2ca12-420">International</span><span class="sxs-lookup"><span data-stu-id="2ca12-420">International</span></span>|<span data-ttu-id="2ca12-421">\d +</span><span class="sxs-lookup"><span data-stu-id="2ca12-421">\d+</span></span>|<span data-ttu-id="2ca12-422">4</span><span class="sxs-lookup"><span data-stu-id="2ca12-422">4</span></span>|<span data-ttu-id="2ca12-423">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-423">sbc2.contoso.biz</span></span><br/><span data-ttu-id="2ca12-424">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2ca12-424">sbc5.contoso.biz</span></span>|<span data-ttu-id="2ca12-425">Маршрут для любого числового шаблона</span><span class="sxs-lookup"><span data-stu-id="2ca12-425">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="2ca12-426">Порядок использования PSTN в политиках маршрутизации голосовой связи очень важен.</span><span class="sxs-lookup"><span data-stu-id="2ca12-426">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="2ca12-427">Использование применяется по порядку, и если соответствие обнаружено при первом использовании, другие варианты использования никогда не оцениваются.</span><span class="sxs-lookup"><span data-stu-id="2ca12-427">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="2ca12-428">Использование КТСОП "Международная" должно быть размещено после использования КТСОП "только США".</span><span class="sxs-lookup"><span data-stu-id="2ca12-428">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="2ca12-429">Чтобы изменить порядок использования PSTN, выполните `Set-CSOnlineVoiceRoutingPolicy` команду.</span><span class="sxs-lookup"><span data-stu-id="2ca12-429">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="2ca12-430">Например, чтобы изменить порядок с "США и Канада", сначала и "международные" секунд на обратный порядок, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2ca12-430">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="2ca12-431">Приоритет для голосовых маршрутов "другие + 1" и "международные" назначаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="2ca12-431">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="2ca12-432">Они не имеют значения, если у них более низкие приоритеты, чем "Redmond 1" и "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="2ca12-432">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="2ca12-433">Пример политики голосовой маршрутизации для пользователя John лесу</span><span class="sxs-lookup"><span data-stu-id="2ca12-433">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="2ca12-434">Действия по созданию использования PSTN "международные", Голосовые маршруты "Международная", "политика маршрутизации голосовой связи", "нет ограничений", а затем назначение ее пользователю "John лесу".</span><span class="sxs-lookup"><span data-stu-id="2ca12-434">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="2ca12-435">Сначала необходимо создать использование КТСОП "Международная".</span><span class="sxs-lookup"><span data-stu-id="2ca12-435">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="2ca12-436">В удаленном сеансе PowerShell в Skype для бизнеса Online введите:</span><span class="sxs-lookup"><span data-stu-id="2ca12-436">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="2ca12-437">Затем создайте новый голосовой маршрут "Международная".</span><span class="sxs-lookup"><span data-stu-id="2ca12-437">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="2ca12-438">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="2ca12-438">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   </pre>
3. <span data-ttu-id="2ca12-439">Затем создайте политику маршрутизации голосовой связи "без ограничений".</span><span class="sxs-lookup"><span data-stu-id="2ca12-439">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="2ca12-440">Использование PSTN "Redmond 1" и "Redmond" используются в этой политике маршрутизации голосовой связи для сохранения особой обработки звонков на номера "+ 1 425 XXX XX XX" и "+ 1 206 XXX XX XX" как локальных, так и локальных звонков.</span><span class="sxs-lookup"><span data-stu-id="2ca12-440">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

   ```
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

    <span data-ttu-id="2ca12-441">Обратите внимание на порядок использования PSTN:</span><span class="sxs-lookup"><span data-stu-id="2ca12-441">Take note of the order of PSTN Usages:</span></span>

    <span data-ttu-id="2ca12-442">a)</span><span class="sxs-lookup"><span data-stu-id="2ca12-442">a.</span></span> <span data-ttu-id="2ca12-443">Если вы вызываете число "+ 1 425 XXX XX XX" с использованием описанных ниже способов, вызов проходит по маршруту, заданному в разделе "США и Канада", и применяется специальная логика маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="2ca12-443">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="2ca12-444">Таким образом, вызов пересылается сначала с помощью sbc1.contoso.biz и sbc2.contoso.biz, а затем sbc3.contoso.biz и sbc4.contoso.biz в качестве маршрутов резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="2ca12-444">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span> 

    <span data-ttu-id="2ca12-445">б)</span><span class="sxs-lookup"><span data-stu-id="2ca12-445">b.</span></span>  <span data-ttu-id="2ca12-446">Если "Международная" использование PSTN перед "US и Канада", то звонки в + 1 425 XXX XX XX пересылаются в sbc2.contoso.biz и sbc5.contoso.biz как часть логики маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="2ca12-446">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="2ca12-447">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="2ca12-447">Enter the command:</span></span>

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="2ca12-448">Который возвращает</span><span class="sxs-lookup"><span data-stu-id="2ca12-448">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="2ca12-449">Назначьте политику маршрутизации голосовой связи пользователю John лесу с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="2ca12-449">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="2ca12-450">Затем проверьте назначение с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="2ca12-450">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="2ca12-451">Возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="2ca12-451">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="2ca12-452">Результат заключается в том, что политика голосовой связи, примененная к вызовам Джон лесу, не ограничена, и она будет соответствовать логике маршрутизации звонков, доступной для США, Канады и международных звонков.</span><span class="sxs-lookup"><span data-stu-id="2ca12-452">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="2ca12-453">Назначение режима "только для Teams" для пользователей, которые должны обеспечивать звонки в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ca12-453">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="2ca12-454">Для прямой маршрутизации необходимо, чтобы пользователи были в режиме "только Teams", чтобы обеспечить поступление входящих звонков в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="2ca12-454">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="2ca12-455">Чтобы перевести пользователей в режиме "только Teams", назначьте им экземпляр "Упградетотеамс" для Теамсупградеполици.</span><span class="sxs-lookup"><span data-stu-id="2ca12-455">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="2ca12-456">Если в вашей организации используется Skype для бизнеса Server или Skype для бизнеса Online, ознакомьтесь со статьей взаимодействие между Skype и Teams, а также [руководство по переходу и взаимодействию для организаций, использующих Teams вместе с Skype для бизнеса](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="2ca12-456">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information interoperability between Skype and Teams: [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="2ca12-457">Настройка отправки звонков непосредственно в голосовую почту</span><span class="sxs-lookup"><span data-stu-id="2ca12-457">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="2ca12-458">Прямая маршрутизация позволяет прекратить звонок пользователю и отправить его прямо на голосовую почту пользователей.</span><span class="sxs-lookup"><span data-stu-id="2ca12-458">Direct Routing allows you to end the call to a user and send it directly to the users' voicemail.</span></span> <span data-ttu-id="2ca12-459">Если вы хотите отправить звонок прямо в голосовую почту, прикрепите непрозрачность = App: голосовой почте к заголовку URI запроса.</span><span class="sxs-lookup"><span data-stu-id="2ca12-459">If you want to send the call directly to voicemail, please attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="2ca12-460">Например, "SIP: user@yourdomain. com; непрозрачный = App: голосовой почты".</span><span class="sxs-lookup"><span data-stu-id="2ca12-460">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span>
<span data-ttu-id="2ca12-461">В этом случае пользователь Teams не получит уведомление о звонке, Звонок будет подключен непосредственно к голосовой почте пользователя.</span><span class="sxs-lookup"><span data-stu-id="2ca12-461">In this case the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ca12-462">См. также</span><span class="sxs-lookup"><span data-stu-id="2ca12-462">See also</span></span>

[<span data-ttu-id="2ca12-463">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="2ca12-463">Plan Direct Routing</span></span>](direct-routing-plan.md)
