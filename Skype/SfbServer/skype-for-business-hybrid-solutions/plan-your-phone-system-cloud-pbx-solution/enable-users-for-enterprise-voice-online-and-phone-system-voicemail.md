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
ms.openlocfilehash: ed5e571976a032facc70b2e602d4b0ea7fd01afc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359185"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="7f623-103">Предоставление пользователям доступа к корпоративной голосовой связи через сеть и к голосовой почте по телефонной линии</span><span class="sxs-lookup"><span data-stu-id="7f623-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="7f623-104">Skype для бизнеса Online будет прекращен до 31 июля, 2021 после чего служба станет недоступна.</span><span class="sxs-lookup"><span data-stu-id="7f623-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="7f623-105">Кроме того, связь по протоколу PSTN между локальной средой и в Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online больше не будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="7f623-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="7f623-106">Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="7f623-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="7f623-107">Узнайте, как включить службы голосовой связи телефонной системы для пользователей Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7f623-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="7f623-108">Последним шагом в развертывании телефонной системы с локальной сетью PSTN является предоставление пользователям доступа к телефонной системе и голосовой почте.</span><span class="sxs-lookup"><span data-stu-id="7f623-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="7f623-109">Чтобы включить эти возможности, необходимо быть пользователем с ролью глобального администратора и иметь возможность запускать удаленную оболочку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f623-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="7f623-110">Необходимо выполнить действия, описанные в этом разделе, для всех учетных записей пользователей, для которых еще не включена поддержка корпоративной голосовой связи в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="7f623-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="7f623-111">Включение служб голосовой связи телефонной системы</span><span class="sxs-lookup"><span data-stu-id="7f623-111">Enable Phone System voice services</span></span>

<span data-ttu-id="7f623-112">Чтобы включить поддержку голосовой и голосовой почты для телефонной системы, необходимо выполнить некоторые начальные действия, например проверить, развернут ли соединитель Skype для бизнеса Online на ваших серверах и разрешить ли пользователям размещенную голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="7f623-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="7f623-113">Предоставление пользователям голосовой и голосовой почты телефонной системы</span><span class="sxs-lookup"><span data-stu-id="7f623-113">To enable your users for Phone System voice and voicemail</span></span>

1. <span data-ttu-id="7f623-114">Прежде чем приступать к работе, убедитесь, что на серверах переднего плана развернут соединитель Skype для бизнеса Online (модуль Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="7f623-114">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="7f623-115">Если это не так, вы можете скачать его из [центра загрузки](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="7f623-115">If it's not, you can download it from [the download center](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="7f623-116">Дополнительные сведения об использовании этого модуля можно найти в странице [Настройка компьютера для управления Skype для бизнеса Online](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="7f623-116">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="7f623-117">Запустите Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="7f623-117">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="7f623-118">Введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="7f623-118">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="7f623-119">Введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="7f623-119">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="7f623-120">После нажатия клавиши Ввод появится диалоговое окно учетные данные Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f623-120">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="7f623-121">Введите имя пользователя и пароль администратора клиента и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7f623-121">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="7f623-122">В окне PowerShell введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="7f623-122">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="7f623-123">Чтобы импортировать сеанс, введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="7f623-123">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="7f623-124">При запуске PowerShell в Skype для бизнеса Server локальные командлеты Skype для бизнеса уже загружены при открытии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f623-124">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="7f623-125">Необходимо указать параметр-Алловклоббер, чтобы разрешить интерактивным командлетам перезаписать локальные командлеты с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="7f623-125">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="7f623-126">Используйте командлет Set – CsUser, чтобы назначить для пользователя свойства $EnterpriseVoiceEnabled и $HostedVoiceMail следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7f623-126">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="7f623-127">Например:</span><span class="sxs-lookup"><span data-stu-id="7f623-127">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="7f623-128">Вы также можете указать пользователя по его адресу SIP, имени участника-пользователя (UPN), имени домена и имени пользователя (домен \ имя_пользователя) и отображаемому имени в Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="7f623-128">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="7f623-129">Обновление URI линии и абонентской группы для пользователей, поддерживающих телефонную систему</span><span class="sxs-lookup"><span data-stu-id="7f623-129">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="7f623-130">В этом разделе описывается обновление универсального кода ресурса (URI) и абонентской группы для пользователей с включенной поддержкой телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="7f623-130">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="7f623-131">Обновление URI линии</span><span class="sxs-lookup"><span data-stu-id="7f623-131">To update the Line URI</span></span>

1. <span data-ttu-id="7f623-132">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7f623-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7f623-133">Используйте меню "Пуск" или ярлык на рабочем столе, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7f623-133">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7f623-134">Вы также можете открыть окно браузера, а затем ввести URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7f623-134">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="7f623-135">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="7f623-135">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7f623-136">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="7f623-136">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="7f623-137">В таблице щелкните учетную запись пользователя Skype для бизнеса, для которой требуется изменить URI линии.</span><span class="sxs-lookup"><span data-stu-id="7f623-137">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="7f623-138">Щелкните **URI строки**и введите уникальный нормализованный номер телефона (например, Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="7f623-138">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="7f623-139">Затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7f623-139">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="7f623-140">Обновление абонентской группы с помощью локальных командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f623-140">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="7f623-141">Абонентские группы для отдельных пользователей можно назначить с помощью Windows PowerShell и командлета [Grant – CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="7f623-141">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="7f623-142">Этот командлет можно выполнить как из Skype для бизнеса Server 2015, так и из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f623-142">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="7f623-143">Назначение абонентской группы отдельных пользователей одному пользователю</span><span class="sxs-lookup"><span data-stu-id="7f623-143">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="7f623-144">С помощью командлета [Grant – CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) назначьте абонентскую абонентскую систему абонентскую redmonddialplan пользователю Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="7f623-144">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="7f623-145">Назначение абонентской группы на уровне пользователей нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="7f623-145">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="7f623-146">Следующая команда назначает абонентскую абонентскую систему абонентскую redmonddialplan всем пользователям, которые работают в городе Redmond.</span><span class="sxs-lookup"><span data-stu-id="7f623-146">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="7f623-147">Для получения дополнительных сведений о параметре LdapFilter, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="7f623-147">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="7f623-148">Для пользователей в сети можно использовать как глобальные, так и пользовательские абонентские группы.</span><span class="sxs-lookup"><span data-stu-id="7f623-148">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="7f623-149">Абонентские группы сайта не могут использоваться, так как они применимы только к пользователям, размещенным локально и назначены локальному сайту.</span><span class="sxs-lookup"><span data-stu-id="7f623-149">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="7f623-150">Отмена назначения абонентской группы на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="7f623-150">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="7f623-151">Используйте командлет [Grant – CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) , чтобы отменить назначение абонентской группы на уровне пользователей, ранее назначенных Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="7f623-151">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="7f623-152">После назначения абонентской группы на уровне пользователя Ken Myer будет автоматически управляться с помощью глобальной абонентской группы или абонентской группы уровня службы, назначенной регистратору или шлюзу PSTN.</span><span class="sxs-lookup"><span data-stu-id="7f623-152">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="7f623-153">Абонентская абонентская область службы имеет приоритет над глобальной абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="7f623-153">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="7f623-154">Обновление политик маршрутизации голосовых вызовов с помощью локальных командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f623-154">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="7f623-155">В этом разделе описывается, как обновить политики маршрутизации голосовых вызовов для пользователей, для которых включена поддержка телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="7f623-155">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="7f623-156">Пользователям телефонной системы должна быть назначена политика маршрутизации голосовой связи для успешной маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="7f623-156">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="7f623-157">Это отличается от пользователей локальной деловой голосовой связи, которым необходимо назначить политику голосовой связи, чтобы разрешить успешные звонки.</span><span class="sxs-lookup"><span data-stu-id="7f623-157">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="7f623-158">Политика маршрутизации голосовой связи должна содержать сведения об использовании PSTN, определяющие авторизованные вызовы и маршруты для пользователей телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="7f623-158">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="7f623-159">Вы можете скопировать использование PSTN из существующих политик голосовой связи в новые политики маршрутизации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7f623-159">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="7f623-160">Дополнительные сведения см. в статье [New – CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7f623-160">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f623-161">Всем пользователям телефонной системы назначается одна и та же политика голосовой связи с именем BusinessVoice, которая определяет разрешенные функции звонков; Например, разрешить Одновременный звонок.</span><span class="sxs-lookup"><span data-stu-id="7f623-161">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="7f623-162">Назначение политики маршрутизации голосовых вызовов для отдельных пользователей одному пользователю</span><span class="sxs-lookup"><span data-stu-id="7f623-162">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="7f623-163">Используйте командлет [Grant – CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) для назначения политики маршрутизации голосовых вызовов на уровне пользователя RedmondVoiceRoutingPolicy пользователю Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="7f623-163">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="7f623-164">Назначение политики маршрутизации голосовых вызовов на уровне пользователей нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="7f623-164">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="7f623-165">Следующая команда назначает политику маршрутизации голосовых вызовов на уровне пользователя RedmondVoiceRoutingPolicy всем пользователям, которые работают в городе Redmond.</span><span class="sxs-lookup"><span data-stu-id="7f623-165">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="7f623-166">Для получения дополнительных сведений о параметре LdapFilter, используемом в этой команде, обратитесь к разделу [Get – CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7f623-166">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="7f623-167">Для пользователей Online можно использовать глобальные или пользовательские политики маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="7f623-167">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="7f623-168">Политики маршрутизации голосовой связи сайта не могут использоваться, так как они применяются только к пользователям, размещенным локально и назначенные локальному сайту.</span><span class="sxs-lookup"><span data-stu-id="7f623-168">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="7f623-169">Отмена назначения политики маршрутизации голосовых вызовов на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="7f623-169">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="7f623-170">С помощью GRANT – CsVoiceRoutingPolicy можно отменить назначение любой политики маршрутизации голосовых вызовов на уровне пользователя, ранее назначенной Кен Myer.</span><span class="sxs-lookup"><span data-stu-id="7f623-170">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="7f623-171">После назначения политики маршрутизации голосовых вызовов на уровне пользователя Ken Myer будет автоматически управляться с помощью глобальной политики маршрутизации голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="7f623-171">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="7f623-172">Дополнительные сведения см. в разделе [Grant – CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7f623-172">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

