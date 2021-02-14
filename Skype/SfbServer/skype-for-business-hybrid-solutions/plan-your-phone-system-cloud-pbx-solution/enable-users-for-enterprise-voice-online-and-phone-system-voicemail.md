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
description: Узнайте, как включить службы голосовой связи телефонной системы для пользователей Skype для бизнеса.
ms.openlocfilehash: 76fbc20b11c0ec91685479d768b88abf71b65d21
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625115"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="0e32a-103">Предоставление пользователям доступа к корпоративной голосовой связи через сеть и к голосовой почте по телефонной линии</span><span class="sxs-lookup"><span data-stu-id="0e32a-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="0e32a-104">Skype для бизнеса Online будет отменен 31 июля 2021 г., после чего служба станет недоступна.</span><span class="sxs-lookup"><span data-stu-id="0e32a-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="0e32a-105">Кроме того, подключение по STN между локальной средой через Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online больше не будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="0e32a-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="0e32a-106">Узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутки.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="0e32a-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="0e32a-107">Узнайте, как включить службы голосовой связи телефонной системы для пользователей Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0e32a-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="0e32a-108">Последний шаг в развертывании телефонной системы с локальной связью через STN — включить для пользователей телефонную систему и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="0e32a-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="0e32a-109">Чтобы включить эти возможности, необходимо быть пользователем с ролью глобального администратора и иметь возможность запускать удаленную точки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e32a-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="0e32a-110">В этом разделе необходимо выполнять действия для всех учетных записей пользователей, для Корпоративная голосовая связь в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="0e32a-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="0e32a-111">Включить голосовую службу телефонной системы</span><span class="sxs-lookup"><span data-stu-id="0e32a-111">Enable Phone System voice services</span></span>

<span data-ttu-id="0e32a-112">Чтобы включить для пользователя голосовую связь и голосовую почту телефонной системы, необходимо выполнить некоторые начальные действия, например проверить, развернут ли на серверах skype для бизнеса Online Connector, и включить для пользователей размещенную голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="0e32a-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="0e32a-113">Чтобы пользователи могли использовать голосовую и голосовую почту телефонной системы</span><span class="sxs-lookup"><span data-stu-id="0e32a-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="0e32a-114">Skype для бизнеса Online Connector в настоящее время входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e32a-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="0e32a-115">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="0e32a-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="0e32a-116">Перед началом убедитесь, что модуль Teams PowerShell установлен на серверах переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="0e32a-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="0e32a-117">Если это не так, установите его с помощью инструкций в установке модуля [Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="0e32a-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="0e32a-118">Начните Windows PowerShell администратором.</span><span class="sxs-lookup"><span data-stu-id="0e32a-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="0e32a-119">Введите следующую кнопку и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="0e32a-119">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   ```

4. <span data-ttu-id="0e32a-120">Введите следующую кнопку и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="0e32a-120">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="0e32a-121">После нажатие на ввод должно отвести Windows PowerShell учетных данных.</span><span class="sxs-lookup"><span data-stu-id="0e32a-121">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="0e32a-122">Введите имя пользователя и пароль администратора клиента и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="0e32a-122">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="0e32a-123">В окне PowerShell введите следующую кнопку и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="0e32a-123">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="0e32a-124">Импорт сеанса путем ввода следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0e32a-124">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="0e32a-125">При запуске PowerShell в Skype для бизнеса Server локальные cmdlets Skype для бизнеса уже загружаются при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e32a-125">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="0e32a-126">Необходимо указать параметр -AllowClobber, чтобы разрешить сетевым cmdlets переоценку локального cmdlets с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="0e32a-126">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="0e32a-127">Используйте Set-CsUser для назначения свойств $EnterpriseVoiceEnabled и $HostedVoiceMail пользователю следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0e32a-127">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="0e32a-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="0e32a-128">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="0e32a-129">Вы также можете указать пользователя по его SIP-адресу, имени пользователя-пользователя, домену и имени пользователя (домен\имя пользователя) и отображаемом имени в Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="0e32a-129">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="0e32a-130">Обновление URI линии и телефонной линии для пользователей с включенной телефонной системой</span><span class="sxs-lookup"><span data-stu-id="0e32a-130">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="0e32a-131">В этом разделе описывается обновление URI линии и телефонной линии для пользователей с включенной телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="0e32a-131">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="0e32a-132">Обновление URI линии</span><span class="sxs-lookup"><span data-stu-id="0e32a-132">To update the Line URI</span></span>

1. <span data-ttu-id="0e32a-133">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0e32a-133">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0e32a-134">Используйте меню "Пуск" или ярлык на рабочем столе, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0e32a-134">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e32a-135">Вы также можете открыть окно браузера, а затем ввести URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0e32a-135">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="0e32a-136">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="0e32a-136">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="0e32a-137">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="0e32a-137">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="0e32a-138">В таблице щелкните учетную запись пользователя Skype для бизнеса, которую вы хотите изменить URI строки.</span><span class="sxs-lookup"><span data-stu-id="0e32a-138">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="0e32a-139">Щелкните **URI** линии и введите уникальный нормализованный номер телефона (например, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="0e32a-139">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="0e32a-140">Затем нажмите **кнопку "Зафиксировать".**</span><span class="sxs-lookup"><span data-stu-id="0e32a-140">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="0e32a-141">Обновление телефонной системы с помощью Windows PowerShell локальной системы</span><span class="sxs-lookup"><span data-stu-id="0e32a-141">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="0e32a-142">Вы можете назначать пользовательские наборы с помощью Windows PowerShell и с помощью Windows PowerShell [Grant-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0e32a-142">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="0e32a-143">Вы можете запустить этот этотлет в Skype для бизнеса Server 2015 или в удаленном сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e32a-143">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="0e32a-144">Назначение отдельной пользовательской телефонной плана одному пользователю</span><span class="sxs-lookup"><span data-stu-id="0e32a-144">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="0e32a-145">Используйте для назначения пользователю Ken Myer пользовательской телефонной плана RedmondDialPlan с помощьюлета [Grant-CsDialPlan:](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0e32a-145">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="0e32a-146">Назначение набора номера на пользователя нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="0e32a-146">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="0e32a-147">Следующая команда назначает пользовательскую телефонную план RedmondDialPlan всем пользователям, которые работают в городе Редмонд.</span><span class="sxs-lookup"><span data-stu-id="0e32a-147">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="0e32a-148">Дополнительные сведения о параметре LdapFilter, используемом в этой команде, см. в документации по командлету [Get-CsUser:](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0e32a-148">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="0e32a-149">Вы можете использовать глобальные или пользовательские наборы для пользователей в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0e32a-149">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="0e32a-150">Нельзя использовать наборные планы сайта, так как они применяются только к пользователям, которые находятся локально и назначены локальному сайту.</span><span class="sxs-lookup"><span data-stu-id="0e32a-150">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="0e32a-151">Чтобы отоименовать телефонную план на пользователя</span><span class="sxs-lookup"><span data-stu-id="0e32a-151">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="0e32a-152">Используйте для [этого cmdlet Grant-CsDialPlan,](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) чтобы отоименовать любую пользовательская телефонная плана, ранее назначенная пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="0e32a-152">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="0e32a-153">После того как на уровне пользователей не назначена, управление пользователем Ken Myer будет автоматически происходить с помощью глобальной или на уровне службы, назначенной его регистратору или шлюзу STN.</span><span class="sxs-lookup"><span data-stu-id="0e32a-153">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="0e32a-154">Над глобальной телефонной сетью имеет приоритет dial plan области службы:</span><span class="sxs-lookup"><span data-stu-id="0e32a-154">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="0e32a-155">Обновление политик маршрутки голосовой почты с помощью Windows PowerShell локальной системы</span><span class="sxs-lookup"><span data-stu-id="0e32a-155">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="0e32a-156">В этом разделе описывается обновление политик маршрутки голосовых данных для пользователей, включенных в телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="0e32a-156">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="0e32a-157">Для успешной маршрутки звонков пользователям телефонной системы должна быть назначена политика маршрутов голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0e32a-157">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="0e32a-158">Это отличается от пользователей локальной бизнес-голосовой связи, которым требуется, чтобы им была назначена политика голосовой связи для успешной маршрутки вызовов.</span><span class="sxs-lookup"><span data-stu-id="0e32a-158">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="0e32a-159">Политика маршрутизации голосовой связи должна содержать использование PSTN, определяющие авторизованные вызовы и маршруты для пользователей телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="0e32a-159">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="0e32a-160">Вы можете скопировать эти функции работы с PSTN из существующих политик голосовой почты в новые политики маршрутной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="0e32a-160">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="0e32a-161">Дополнительные сведения см. в [new-CsVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0e32a-161">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e32a-162">Всем пользователям телефонной системы назначена та же политика голосовой связи в Интернете с именем BusinessVoice, которая определяет разрешенные функции звонков; например, разрешить одновременный звонок.</span><span class="sxs-lookup"><span data-stu-id="0e32a-162">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="0e32a-163">Назначение политики маршрутки голосовой почты на одного пользователя одному пользователю</span><span class="sxs-lookup"><span data-stu-id="0e32a-163">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="0e32a-164">Чтобы назначить политику маршрутизации голосовой почты на пользователя RedmondVoiceRoutingPolicy пользователю Ken Myer, используйте его с помощью cmdlet [Grant-CsVoiceRoutingPolicy:](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0e32a-164">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="0e32a-165">Назначение политики маршрутки голосовой почты на пользователя нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="0e32a-165">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="0e32a-166">Следующая команда назначает политику маршрутизации голосовых данных на пользователя RedmondVoiceRoutingPolicy всем пользователям, которые работают в городе Редмонд.</span><span class="sxs-lookup"><span data-stu-id="0e32a-166">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="0e32a-167">Дополнительные сведения о параметре LdapFilter, используемом в этой команде, см. в командной [команде Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0e32a-167">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="0e32a-168">Вы можете использовать глобальные или пользовательские политики маршрутинга голосовой почты для пользователей в Интернете.</span><span class="sxs-lookup"><span data-stu-id="0e32a-168">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="0e32a-169">Политики маршрутки голосовой почты сайта нельзя использовать, так как они применяются только к пользователям, которые находятся локально и назначены локальному сайту.</span><span class="sxs-lookup"><span data-stu-id="0e32a-169">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="0e32a-170">Чтобы отоименовать политику маршрутизатики голосовой почты на пользователя, необходимо</span><span class="sxs-lookup"><span data-stu-id="0e32a-170">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="0e32a-171">Используйте эту Grant-CsVoiceRoutingPolicy, чтобы отоименовать любую политику маршрутки голосовой почты на пользователя, ранее назначенную пользователю Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="0e32a-171">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="0e32a-172">После того как политика маршрутки голосовой почты на уровне пользователя не назначена, ken Myer будет автоматически управляться с помощью глобальной политики маршрутизировки голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="0e32a-172">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="0e32a-173">Дополнительные сведения [см. в поддоме "Grant-CsVoiceRoutingPolicy".](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0e32a-173">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

