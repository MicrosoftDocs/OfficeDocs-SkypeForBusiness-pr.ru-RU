---
title: Предоставление пользователям доступа к корпоративной голосовой связи через сеть и к голосовой почте по телефонной линии
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Узнайте, как включить голосовые службы телефонной системы для пользователей Skype для бизнеса.
ms.openlocfilehash: bbcf8b35d91015067943eec2cbe43525e952a7f7
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569361"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="e8d49-103">Предоставление пользователям доступа к корпоративной голосовой связи через сеть и к голосовой почте по телефонной линии</span><span class="sxs-lookup"><span data-stu-id="e8d49-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="e8d49-104">Skype для бизнеса Online будет отменен 31 июля 2021 г., после чего служба будет больше недоступна.</span><span class="sxs-lookup"><span data-stu-id="e8d49-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="e8d49-105">Кроме того, подключение PSTN между локальной средой, будь то Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online, больше не будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="e8d49-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="e8d49-106">Узнайте, как подключить сеть локальной телефонии к Teams с помощью [прямого маршрутного маршрутинга.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="e8d49-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="e8d49-107">Узнайте, как включить голосовые службы телефонной системы для пользователей Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e8d49-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="e8d49-108">Заключительный шаг в развертывании телефонной системы с локальной подключением PSTN — включить пользователей для телефонной системы и голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="e8d49-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="e8d49-109">Чтобы включить эти возможности, необходимо быть пользователем с ролью глобального администратора и иметь возможность запуска удаленной PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8d49-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="e8d49-110">Необходимо следовать шагам в этом разделе для всех учетных записей пользователей, которые еще не Корпоративная голосовая связь для Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e8d49-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="e8d49-111">Включить голосовые службы телефонной системы</span><span class="sxs-lookup"><span data-stu-id="e8d49-111">Enable Phone System voice services</span></span>

<span data-ttu-id="e8d49-112">Чтобы включить пользователя для голосовой связи и голосовой почты системы телефонной системы, необходимо выполнить некоторые начальные действия, например проверить, развернут ли соединиттель Skype для бизнеса Online на серверах и включить пользователей для размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="e8d49-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="e8d49-113">Чтобы включить пользователей для голосовой и голосовой почты телефонной системы</span><span class="sxs-lookup"><span data-stu-id="e8d49-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="e8d49-114">Соединитель Skype для бизнеса в Интернете в настоящее время является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8d49-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="e8d49-115">Если вы используете последний общедоступный [выпуск Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e8d49-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="e8d49-116">Перед началом проверьте, установлен ли модуль Teams PowerShell на переднем сервере.</span><span class="sxs-lookup"><span data-stu-id="e8d49-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="e8d49-117">Если это не так, установите, пожалуйста, с помощью инструкций по установке [модулей Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="e8d49-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="e8d49-118">Начните Windows PowerShell в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="e8d49-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="e8d49-119">Введите следующее и нажмите кнопку Ввод:</span><span class="sxs-lookup"><span data-stu-id="e8d49-119">Type the following and press Enter:</span></span>
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. <span data-ttu-id="e8d49-120">Используйте Set-CsUser для назначения свойств $EnterpriseVoiceEnabled и $HostedVoiceMail пользователю следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e8d49-120">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="e8d49-121">Например:</span><span class="sxs-lookup"><span data-stu-id="e8d49-121">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="e8d49-122">Вы также можете указать пользователя по его SIP-адресу, основному имени пользователя (UPN), домену и имени пользователя (domain\username) и отобразить имя в Active Directory ("Боб Келли").</span><span class="sxs-lookup"><span data-stu-id="e8d49-122">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="e8d49-123">Обновление строки URI и набора номера для пользователей, включенных для телефонной системы</span><span class="sxs-lookup"><span data-stu-id="e8d49-123">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="e8d49-124">В этом разделе описывается обновление строки URI и набора номера для пользователей, включенных для телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="e8d49-124">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="e8d49-125">Обновление строки URI</span><span class="sxs-lookup"><span data-stu-id="e8d49-125">To update the Line URI</span></span>

1. <span data-ttu-id="e8d49-126">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e8d49-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e8d49-127">Чтобы открыть панель управления Skype для бизнес-серверов, используйте меню Пуск или ярлык рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="e8d49-127">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e8d49-128">Вы также можете открыть окно браузера, а затем ввести URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="e8d49-128">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="e8d49-129">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="e8d49-129">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="e8d49-130">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="e8d49-130">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="e8d49-131">В таблице щелкните учетную запись пользователя Skype для бизнеса, которую необходимо изменить строку URI.</span><span class="sxs-lookup"><span data-stu-id="e8d49-131">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="e8d49-132">Щелкните **строку URI** и введите уникальный, нормализованный номер телефона (например, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="e8d49-132">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="e8d49-133">Затем нажмите **кнопку Фиксация**.</span><span class="sxs-lookup"><span data-stu-id="e8d49-133">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="e8d49-134">Обновление набора набора с помощью локального Windows PowerShell-кодлетов</span><span class="sxs-lookup"><span data-stu-id="e8d49-134">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="e8d49-135">Вы можете назначить для каждого пользователя планы набора с помощью Windows PowerShell и [cmdlet Grant-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e8d49-135">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="e8d49-136">Этот комлет можно выполнить либо из Skype для бизнеса Server 2015, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8d49-136">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="e8d49-137">Назначение набора для каждого пользователя одному пользователю</span><span class="sxs-lookup"><span data-stu-id="e8d49-137">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="e8d49-138">Чтобы назначить пользователю Кену Мьеру наборную плану RedmondDialPlan для каждого пользователя, используйте коммюнике [Grant-CsDialPlan:](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e8d49-138">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="e8d49-139">Назначение набора для каждого пользователя нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="e8d49-139">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="e8d49-140">Следующая команда назначает для каждого пользователя наборную плану RedmondDialPlan всем пользователям, которые работают в городе Редмонд.</span><span class="sxs-lookup"><span data-stu-id="e8d49-140">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="e8d49-141">Дополнительные сведения о параметре LdapFilter, используемом в этой команде, см. в документации для [командлета Get-CsUser:](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e8d49-141">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="e8d49-142">Вы можете использовать глобальные или пользовательские наборные планы для пользователей в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e8d49-142">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="e8d49-143">Планы набора веб-сайтов нельзя использовать, так как они применяются только к пользователям, которые находятся в помещении и назначены локальному сайту.</span><span class="sxs-lookup"><span data-stu-id="e8d49-143">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="e8d49-144">Чтобы отоименить телефонную плану для каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="e8d49-144">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="e8d49-145">Используйте [комлет Grant-CsDialPlan,](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) чтобы отогнать любую заданную ранее телефонную плану на одного пользователя Кену Myer.</span><span class="sxs-lookup"><span data-stu-id="e8d49-145">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="e8d49-146">После того, как телефонная система для каждого пользователя не назначена, управление кеном Myer будет автоматически происходить с помощью глобальной шкалы или набора номера службы, назначенного его шлюзу Registrar или PSTN.</span><span class="sxs-lookup"><span data-stu-id="e8d49-146">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="e8d49-147">Перед глобальной шкалой набора номеров области службы имеется преимущество:</span><span class="sxs-lookup"><span data-stu-id="e8d49-147">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="e8d49-148">Обновление политик маршрутики голосовой маршрутики с помощью локального Windows PowerShell-кодлетов</span><span class="sxs-lookup"><span data-stu-id="e8d49-148">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="e8d49-149">В этом разделе описывается обновление политик маршрутики голосовой связи для пользователей, включенных в телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="e8d49-149">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="e8d49-150">Пользователи телефонной системы должны иметь политику маршрутизов голосовой связи, назначенную им для успешного маршрута звонков.</span><span class="sxs-lookup"><span data-stu-id="e8d49-150">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="e8d49-151">Это отличается от локального бизнеса голосовых пользователей, которым требуется, чтобы им была назначена голосовая политика для успешного маршрута вызовов.</span><span class="sxs-lookup"><span data-stu-id="e8d49-151">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="e8d49-152">Политика маршрутизации голосовой связи должна содержать использование PSTN, определяющие разрешенные вызовы и маршруты для пользователей телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="e8d49-152">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="e8d49-153">Эти ПСПС можно скопировать из существующих голосовых политик в новые политики маршрутивки голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="e8d49-153">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="e8d49-154">Дополнительные сведения см. [в рублях New-CsVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e8d49-154">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8d49-155">Всем пользователям телефонной системы назначена та же политика голосовой связи в Интернете с именем BusinessVoice, которая определяет разрешенные функции вызова; например, разрешить одновременное кольцо.</span><span class="sxs-lookup"><span data-stu-id="e8d49-155">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="e8d49-156">Назначение политики маршрутинга голосовых данных для каждого пользователя одному пользователю</span><span class="sxs-lookup"><span data-stu-id="e8d49-156">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="e8d49-157">Используйте [кодлет Grant-CsVoiceRoutingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) чтобы назначить политику маршрутизации голосовой маршрутизации для каждого пользователя RedmondVoiceRoutingPolicy пользователю Кену Мойеру:</span><span class="sxs-lookup"><span data-stu-id="e8d49-157">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="e8d49-158">Назначение политики маршрутинга голосовой маршрутики для каждого пользователя нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="e8d49-158">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="e8d49-159">Следующая команда назначает политику маршрутизации голосовых данных для каждого пользователя RedmondVoiceRoutingPolicy всем пользователям, которые работают в городе Редмонд.</span><span class="sxs-lookup"><span data-stu-id="e8d49-159">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="e8d49-160">Дополнительные сведения о параметре LdapFilter, используемом в этой команде, см. [в пункте Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e8d49-160">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="e8d49-161">Вы можете использовать политики маршрутинга голосовой маршрутики global или User для пользователей в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e8d49-161">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="e8d49-162">Политики маршрутинга голосового голоса на сайте не могут использоваться, поскольку они применяются только к пользователям, которые находятся в помещении и назначены локальному сайту.</span><span class="sxs-lookup"><span data-stu-id="e8d49-162">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="e8d49-163">Чтобы отогласить политику маршрутизования голосовых данных для каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="e8d49-163">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="e8d49-164">Используйте Grant-CsVoiceRoutingPolicy, чтобы отогнать любую политику маршрутизования голосовых данных для каждого пользователя, ранее назначенную Кену Myer.</span><span class="sxs-lookup"><span data-stu-id="e8d49-164">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="e8d49-165">После того, как политика маршрутизировки голосовых данных для каждого пользователя не назначена, управление ken Myer будет автоматически происходить с помощью глобальной политики маршрутизировки голосовых данных.</span><span class="sxs-lookup"><span data-stu-id="e8d49-165">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="e8d49-166">Дополнительные сведения см. [в рублях Grant-CsVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e8d49-166">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

