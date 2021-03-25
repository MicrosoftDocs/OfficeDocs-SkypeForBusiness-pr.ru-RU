---
title: Развертывание комнаты Microsoft Teams с Exchange Online
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Сведения о том, как развернуть комнаты Microsoft Teams с Exchange Online и локальной службой Skype для бизнеса Server, можно найти в этой теме.
ms.openlocfilehash: 5e3446349be8aaef666c02c73370758027736181
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117347"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="5b4cb-103">Развертывание комнаты Microsoft Teams с Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5b4cb-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="5b4cb-104">Сведения о том, как развернуть комнаты Microsoft Teams с Exchange Online и локальной службой Skype для бизнеса Server, можно найти в этой теме.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="5b4cb-105">Если в вашей организации имеется сочетание служб, одни из которых локально, а другие — в Интернете, то конфигурация будет зависеть от того, где именно.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="5b4cb-106">В этой теме описывается гибридное развертывание комнат Microsoft Teams с Exchange, размещенной в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="5b4cb-107">Так как в развертывании такого типа много разных вариантов, предоставить подробные инструкции для всех из них невозможно.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="5b4cb-108">Для многих конфигураций будет работать следующий процесс:</span><span class="sxs-lookup"><span data-stu-id="5b4cb-108">The following process will work for many configurations.</span></span> <span data-ttu-id="5b4cb-109">Если процесс не подгоняет целевую настройку, рекомендуем использовать Windows PowerShell для достижения того же результата, что и здесь, а также для других вариантов развертывания.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="5b4cb-110">Проще всего настроить учетные записи пользователей с помощью удаленной Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="5b4cb-111">Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который помогает создавать новые учетные записи пользователей или проверять существующие учетные записи ресурсов, чтобы превратить их в совместимые учетные записи пользователей комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="5b4cb-112">При этом вы можете настроить учетные записи, которые будут использовать устройства с комнатами Microsoft Teams, следуя этим шагам.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="5b4cb-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5b4cb-113">Requirements</span></span>

<span data-ttu-id="5b4cb-114">Прежде чем развернуть комнаты Microsoft Teams в Exchange Online, убедитесь, что выполнены все требования.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="5b4cb-115">Дополнительные сведения см. в требованиях к комнатам [Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5b4cb-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="5b4cb-116">Чтобы развернуть комнаты Microsoft Teams с Exchange Online, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5b4cb-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="5b4cb-117">Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="5b4cb-118">Модуль [Azure Active Directory](/powershell/azure/active-directory/overview?view=azureadps-1.0) для Windows PowerShell в этом разделе (например, Set-MsolUser) был протестирован при настройке учетных записей для устройств с комнатами Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="5b4cb-119">Возможно, другие cmdlets могут работать, но в этом сценарии они не тестировали.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="5b4cb-120">При развертывании служб федерации Active Directory (AD FS) может потребоваться преобразовать учетную запись пользователя в управляемого пользователя, а затем после выполнения этих действий снова преобразовать его в федератора.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="5b4cb-121">Создание учетной записи и настройка свойств Exchange</span><span class="sxs-lookup"><span data-stu-id="5b4cb-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="5b4cb-122">Начните удаленный Windows PowerShell на компьютере и подключите к Exchange Online следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5b4cb-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="5b4cb-123">После создания сеанса вам нужно будет создать новый почтовый ящик и включить его в качестве учетной записи RoomMailboxAccount или изменить параметры для существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="5b4cb-124">Это позволит учетной записи аутентификацию в комнатах Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="5b4cb-125">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="5b4cb-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="5b4cb-126">Если вы создаете новый почтовый ящик ресурса:</span><span class="sxs-lookup"><span data-stu-id="5b4cb-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="5b4cb-127">Чтобы повысить эффективность собрания, необходимо настроить свойства Exchange для учетной записи пользователя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5b4cb-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="5b4cb-128">Добавление адреса электронной почты для локальной учетной записи домена</span><span class="sxs-lookup"><span data-stu-id="5b4cb-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="5b4cb-129">В **средстве Active Directory Users and Computers AD** щелкните правой кнопкой мыши контейнер или подразделение, в котором будут созданы учетные записи комнат Microsoft Teams, нажмите кнопку "Создать" и выберите **"Пользователь".**</span><span class="sxs-lookup"><span data-stu-id="5b4cb-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="5b4cb-130">В поле "Полное имя" введите отображаемого имени (-Identity) из предыдущего cmdlet (Set-Mailbox или New-Mailbox) и псевдоним в поле "Имя **пользователя".** </span><span class="sxs-lookup"><span data-stu-id="5b4cb-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="5b4cb-131">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-131">Click **Next**.</span></span>
3. <span data-ttu-id="5b4cb-p108">Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b4cb-135">Выбор пароля **"Срок действия не истекает"** является требованием для сервера Skype для бизнеса в комнатах Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="5b4cb-136">В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="5b4cb-137">В этом случае необходимо создать исключение для каждой учетной записи пользователя комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="5b4cb-138">Чтобы создать учетную запись, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="5b4cb-139">После создания учетной записи запустите синхронизацию каталогов.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="5b4cb-140">Для этого можно использовать [set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="5b4cb-141">После этого перейдите на страницу пользователей и убедитесь, что две учетные записи, созданные на предыдущих шагах, объединены.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="5b4cb-142">Назначение лицензии на Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="5b4cb-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="5b4cb-143">Сначала подключите Azure AD, чтобы применить некоторые параметры учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="5b4cb-144">Для подключения можно использовать следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="5b4cb-145">Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="5b4cb-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="5b4cb-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="5b4cb-147">Учетная запись пользователя должна иметь действуемую лицензию Microsoft 365 или Office 365, чтобы обеспечить работу Exchange и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="5b4cb-148">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="5b4cb-149">Задание нужно сделать в следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="5b4cb-150">Затем используйте `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="5b4cb-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="5b4cb-151">, чтобы получить список доступных skus для вашей организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="5b4cb-152">После добавления номеров skus вы можете добавить лицензию с помощью `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="5b4cb-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="5b4cb-153">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-153">cmdlet.</span></span> <span data-ttu-id="5b4cb-154">В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="5b4cb-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="5b4cb-155">Включить учетную запись пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5b4cb-155">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="5b4cb-156">Создайте удаленный Windows PowerShell с компьютера следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5b4cb-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="5b4cb-157">Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-157">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="5b4cb-158">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-158">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. <span data-ttu-id="5b4cb-159">Чтобы включить учетную запись комнат Microsoft Teams для Skype для бизнеса Server, запустите эту команду:</span><span class="sxs-lookup"><span data-stu-id="5b4cb-159">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="5b4cb-160">Если вы не знаете, какое значение нужно использовать для параметра RegistrarPool в вашей среде, вы можете получить значение от существующего пользователя Skype для бизнеса Server с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-160">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="5b4cb-161">Назначение лицензии на Сервер Skype для бизнеса учетной записи комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b4cb-161">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="5b4cb-162">Войдите в систему как администратор клиента, откройте Центр администрирования Microsoft 365 и щелкните приложение "Администратор".</span><span class="sxs-lookup"><span data-stu-id="5b4cb-162">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="5b4cb-163">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-163">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="5b4cb-164">Щелкните учетную запись комнат Microsoft Teams, а затем щелкните значок пера, чтобы изменить сведения об учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-164">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="5b4cb-165">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-165">Click **Licenses**.</span></span>
5. <span data-ttu-id="5b4cb-166">В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-166">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="5b4cb-167">Если вы хотите использовать план 3, вам необходимо будет использовать Корпоративная голосовая связь в комнатах Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-167">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="5b4cb-168">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-168">Click **Save**.</span></span>

<span data-ttu-id="5b4cb-169">Для проверки вы сможете войти в эту учетную запись с помощью любого клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-169">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="5b4cb-170">Если вы используете номера skus для E1, E3, E4 или E5 в Skype для бизнеса (план 2) с аудиоконференцией или телефонной системой и планом звонков, эти функции будут продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-170">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="5b4cb-171">Однако по истечении срока действия текущих лицензий следует двигаться на более простую модель лицензирования, как описано в обновлении лицензирования комнаты собраний [Teams.](rooms-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="5b4cb-171">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b4cb-172">Если вы используете Skype для бизнеса (план 2), вы можете использовать только комнаты Microsoft Teams в режиме "Только Skype для бизнеса", то есть все ваши собрания будут собраниями Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-172">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="5b4cb-173">Чтобы включить комнату для собраний Microsoft Teams, мы рекомендуем приобрести лицензию на нее.</span><span class="sxs-lookup"><span data-stu-id="5b4cb-173">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5b4cb-174">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5b4cb-174">Related topics</span></span>

[<span data-ttu-id="5b4cb-175">Настройка учетных записей для комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b4cb-175">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="5b4cb-176">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b4cb-176">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="5b4cb-177">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b4cb-177">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="5b4cb-178">Настройка консоли комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b4cb-178">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="5b4cb-179">Управление комнатами Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b4cb-179">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)