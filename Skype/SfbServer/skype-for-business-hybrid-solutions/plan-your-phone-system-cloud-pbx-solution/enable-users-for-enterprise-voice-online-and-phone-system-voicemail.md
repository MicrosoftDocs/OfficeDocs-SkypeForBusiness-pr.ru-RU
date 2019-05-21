---
title: Предоставление пользователям доступа к корпоративной голосовой связи через сеть и телефонной системе в голосовой почте Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Сведения о том, как включить телефонную систему в службах голосовой связи Office 365 для пользователей Skype для бизнеса.
ms.openlocfilehash: 1305f4045d4de86a65e0286938d22490f577507c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287505"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="cd85d-103">Предоставление пользователям доступа к корпоративной голосовой связи через сеть и телефонной системе в голосовой почте Office 365</span><span class="sxs-lookup"><span data-stu-id="cd85d-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="cd85d-104">Сведения о том, как включить телефонную систему в службах голосовой связи Office 365 для пользователей Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cd85d-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="cd85d-105">Последним шагом при развертывании телефонной системы в Office 365 с помощью локальной сети PSTN является предоставление пользователям телефонной системы в Office 365 и голосовой почте.</span><span class="sxs-lookup"><span data-stu-id="cd85d-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="cd85d-106">Активировать эти возможности может пользователь Office 365 с ролью "Глобальный администратор", который может управлять PowerShell в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="cd85d-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="cd85d-107">Выполните действия, описанные в этом разделе, с учетными записями всех пользователей, для которых еще не активирована корпоративная голосовая связь для Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="cd85d-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="cd85d-108">Включение телефонной системы в службах голосовой связи Office 365</span><span class="sxs-lookup"><span data-stu-id="cd85d-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="cd85d-109">Чтобы включить пользователя для телефонной системы в Office 365 голосовой и голосовой почте, вам потребуется выполнить некоторые начальные действия, например проверить, развернут ли соединитель Skype для бизнеса Online на ваших серверах, и разрешить вашим пользователям размещенную голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="cd85d-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="cd85d-110">Предоставление пользователям телефонной системы Office 365 голосовой и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="cd85d-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="cd85d-111">Прежде чем начать, убедитесь, что на серверах переднего плана развернут соединитель Skype для бизнеса Online (модуль Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="cd85d-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="cd85d-112">Если это не так, вы можете скачать его из [центра загрузки](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="cd85d-112">If it's not, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="cd85d-113">Дополнительные сведения об использовании этого модуля можно найти в разделе [Настройка компьютера для управления Skype для бизнеса Online](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="cd85d-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="cd85d-114">Запустите Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="cd85d-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="cd85d-115">Введите следующую команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="cd85d-115">Type the following and press Enter:</span></span>
    
   ```
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="cd85d-116">Введите следующую команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="cd85d-116">Type the following and press Enter:</span></span>
    
   ```
   $cred = Get-Credential
   ```

    <span data-ttu-id="cd85d-117">После нажатия клавиши ВВОД появится диалоговое окно "Учетные данные Windows PowerShell".</span><span class="sxs-lookup"><span data-stu-id="cd85d-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="cd85d-118">Введите имя пользователя администратора клиента и пароль, нажмите клавишу **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cd85d-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="cd85d-119">В окне PowerShell введите следующую команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="cd85d-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="cd85d-120">Импортируйте сеанс с помощью следующего командлета.</span><span class="sxs-lookup"><span data-stu-id="cd85d-120">Import the session by typing the following cmdlet:</span></span>
    
   ```
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="cd85d-121">При запуске PowerShell на сервере Skype для бизнеса, когда вы открываете PowerShell, они уже загружаются в качестве локальных командлетов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="cd85d-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="cd85d-122">Необходимо указать параметр-Алловклоббер, чтобы разрешить интерактивным командлетам перезаписать локальные командлеты с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="cd85d-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="cd85d-123">Выполните командлет Set-CsUser, чтобы назначить свойства $EnterpriseVoiceEnabled и $HostedVoiceMail пользователю:</span><span class="sxs-lookup"><span data-stu-id="cd85d-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="cd85d-124">Например:</span><span class="sxs-lookup"><span data-stu-id="cd85d-124">For example:</span></span>
    
   ```
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="cd85d-125">Вы можете определить пользователя по адресу SIP, по имени участника-пользователя (UPN), по имени домена и имени пользователи (домен\имя пользователя) и по отображаемому имени Active Directory (Bob Kelly).</span><span class="sxs-lookup"><span data-stu-id="cd85d-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="cd85d-126">Обновление универсального кода ресурса (URI) и абонентской группы для пользователей, для которых включена телефонная система в Office 365</span><span class="sxs-lookup"><span data-stu-id="cd85d-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="cd85d-127">В этом разделе объясняется, как обновить универсальный код ресурса (URI) и абонентскую группу для пользователей, для которых включена телефонная система в Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd85d-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="cd85d-128">Обновление URI линии</span><span class="sxs-lookup"><span data-stu-id="cd85d-128">To update the Line URI</span></span>

1. <span data-ttu-id="cd85d-129">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cd85d-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cd85d-130">Откройте панель управления Skype для бизнеса Server, используя меню "Пуск" или ярлык на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="cd85d-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cd85d-131">Кроме того, можно открыть окно браузера и ввести URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cd85d-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="cd85d-132">На панели навигации слева щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="cd85d-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="cd85d-133">В поле **Поиск пользователей** введите отображаемое имя или его начальный фрагмент, имя, фамилию, имя учетной записи (диспетчера учетных записей безопасности (SAM), SIP-адрес или строку универсального кода ресурса (URI) из учетной записи пользователя, которому требуется предоставить доступ, затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="cd85d-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="cd85d-134">В таблице щелкните учетную запись пользователя Skype для бизнеса, для которой необходимо изменить URI линии.</span><span class="sxs-lookup"><span data-stu-id="cd85d-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="cd85d-p104">Щелкните **URI строки** и введите уникальный нормализованный номер телефона (например, tel:+14255550200). Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cd85d-p104">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="cd85d-137">Обновление абонентской группы с использованием локальных командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd85d-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="cd85d-138">Вы можете назначить абонентские планы для пользователей с помощью Windows PowerShell и командлетом [Grant-ксдиалплан](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="cd85d-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="cd85d-139">Этот командлет можно выполнить либо из Skype для бизнеса Server 2015, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd85d-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="cd85d-140">Назначение абонентской группы на уровне пользователей отдельному пользователю</span><span class="sxs-lookup"><span data-stu-id="cd85d-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="cd85d-141">С помощью командлета [Grant-ксдиалплан](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) можно назначить пользователю RedmondDialPlan абонентской группы для пользователей мер:</span><span class="sxs-lookup"><span data-stu-id="cd85d-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="cd85d-142">Назначение абонентской группы на уровне пользователей нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="cd85d-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="cd85d-143">Следующая команда назначает абонентскую группу на уровне пользователей RedmondDialPlan всем пользователям, работающим в городе Редмонд (Redmond).</span><span class="sxs-lookup"><span data-stu-id="cd85d-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="cd85d-144">Дополнительные сведения о параметре Лдапфилтер, используемом в этой команде, можно найти в документации по командлету [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="cd85d-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="cd85d-p107">Для пользователей в сети можно использовать глобальные или пользовательские абонентские группы. Невозможно использовать абонентские группы сайта, так как они применимы только к тем пользователям, которые размещены локально и которым назначен локальный сайт.</span><span class="sxs-lookup"><span data-stu-id="cd85d-p107">You may use either Global or User dial plans for online users. Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="cd85d-147">Назначение абонентской группы на уровне пользователей</span><span class="sxs-lookup"><span data-stu-id="cd85d-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="cd85d-148">Используйте командлет [Grant-ксдиалплан](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) , чтобы отменить назначение каждому пользователю абонентского плана, ранее назначенного для Кен мер.</span><span class="sxs-lookup"><span data-stu-id="cd85d-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="cd85d-149">После отмены назначения абонентской группы на уровне пользователей управление пользователем Ken Myer автоматически осуществляется с помощью глобальной абонентской группы или абонентской группы уровня службы, назначенной его службе Registrar или шлюзу ТСОП.</span><span class="sxs-lookup"><span data-stu-id="cd85d-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="cd85d-150">Абонентская группа уровня службы обладает приоритетом по отношению к глобальной абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="cd85d-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="cd85d-151">Обновление политик маршрутизации голосовых вызовов с помощью локальных командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd85d-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="cd85d-152">В этом разделе объясняется, как обновить политики голосовой маршрутизации для пользователей, для которых включена телефонная система в Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd85d-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="cd85d-153">Телефонная система для пользователей Office 365 должна иметь политику маршрутизации голосовой связи, назначенную им для успешной отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="cd85d-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="cd85d-154">В этом заключается отличие от локальных пользователей голосовой бизнес-связи, которым необходимо назначить политику голосовой связи для успешной маршрутизации вызовов.</span><span class="sxs-lookup"><span data-stu-id="cd85d-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="cd85d-155">Политика маршрутизации голосовой связи должна включать в себя использование PSTN, определяющее авторизованные звонки и маршруты для телефонной системы пользователей Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd85d-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="cd85d-156">Можно скопировать эти параметры из существующих политик голосовых вызовов в новые политики маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="cd85d-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="cd85d-157">Дополнительные сведения см. в разделе [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cd85d-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd85d-158">Вся телефонная система в Office 365 назначается одной и той же политике голосовой связи по сети с именем Бусинессвоице, которая определяет разрешенные функции звонка; Например, разрешите Одновременный звонок.</span><span class="sxs-lookup"><span data-stu-id="cd85d-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="cd85d-159">Назначение политики маршрутизации голосовых вызовов на уровне пользователя одному пользователю</span><span class="sxs-lookup"><span data-stu-id="cd85d-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="cd85d-160">Используйте командлет [Grant-ксвоицераутингполици](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) , чтобы назначить политику голосовой маршрутизации для каждого пользователя Редмондвоицераутингполици пользователю Кен мер:</span><span class="sxs-lookup"><span data-stu-id="cd85d-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="cd85d-161">Назначение политики маршрутизации голосовых вызовов на уровне пользователя для нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="cd85d-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="cd85d-162">Следующая команда назначает политику голосовой маршрутизации для каждого пользователя, Редмондвоицераутингполици всем пользователям, которые работают в городе Redmond.</span><span class="sxs-lookup"><span data-stu-id="cd85d-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="cd85d-163">Дополнительные сведения о параметре Лдапфилтер, используемом в этой команде, см. в разделе [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cd85d-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="cd85d-p111">Для пользователей в сети можно использовать глобальные или пользовательские политики маршрутизации голосовых вызовов. Невозможно использовать политики маршрутизации голосовых вызовов сайта, так как они применимы только к тем пользователям, которые размещены локально и которым назначен локальный сайт.</span><span class="sxs-lookup"><span data-stu-id="cd85d-p111">You may use either Global or User voice routing policies for online users. Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="cd85d-166">Отмена назначения политики маршрутизации голосовых вызовов на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="cd85d-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="cd85d-167">Используйте Grant-Ксвоицераутингполици для отмены назначения любой политики голосовой маршрутизации для каждого пользователя, ранее назначенной для Кен мер.</span><span class="sxs-lookup"><span data-stu-id="cd85d-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="cd85d-168">После отмены политики на уровне пользователя к пользователю Ken Myer будет автоматически применяться глобальная политика маршрутизации голосовых звонков.</span><span class="sxs-lookup"><span data-stu-id="cd85d-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="cd85d-169">Дополнительные сведения см. в разделе [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cd85d-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

