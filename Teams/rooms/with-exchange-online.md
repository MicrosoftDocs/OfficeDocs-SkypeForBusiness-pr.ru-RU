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
description: Дополнительные сведения о развертывании Комнаты Microsoft Teams с Exchange Online и Skype для бизнеса Server локальной основе.
ms.openlocfilehash: 2f92f85ddf39c5e1a813492b3092eeeef9b77e4c
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796683"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="7869a-103">Развертывание комнаты Microsoft Teams с Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7869a-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="7869a-104">Дополнительные сведения о развертывании Комнаты Microsoft Teams с Exchange Online и Skype для бизнеса Server локальной основе.</span><span class="sxs-lookup"><span data-stu-id="7869a-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="7869a-105">Если в вашей организации есть несколько служб с некоторыми из локальной службы, а другие — через Интернет, то конфигурация будет зависеть от того, где именно находится та или иная служба.</span><span class="sxs-lookup"><span data-stu-id="7869a-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="7869a-106">В этой теме описывается гибридное развертывание Комнаты Microsoft Teams с Exchange размещены в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7869a-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="7869a-107">Так как в этом типе развертывания очень много вариантов, предоставить подробные инструкции для всех из них невозможно.</span><span class="sxs-lookup"><span data-stu-id="7869a-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="7869a-108">Этот процесс будет работать для многих конфигураций.</span><span class="sxs-lookup"><span data-stu-id="7869a-108">The following process will work for many configurations.</span></span> <span data-ttu-id="7869a-109">Если процесс не подгоняет под установку, рекомендуем использовать Windows PowerShell, чтобы получить такой же конечный результат, как описано здесь, а также для других вариантов развертывания.</span><span class="sxs-lookup"><span data-stu-id="7869a-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="7869a-110">Самый простой способ настроить учетные записи пользователей — настроить их с помощью удаленного Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7869a-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="7869a-111">Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей или проверить существующие учетные записи ресурсов, чтобы сделать их совместимыми Комнаты Microsoft Teams пользователями.</span><span class="sxs-lookup"><span data-stu-id="7869a-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="7869a-112">При этом вы можете настроить учетные записи, которые будут Комнаты Microsoft Teams устройство.</span><span class="sxs-lookup"><span data-stu-id="7869a-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="7869a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7869a-113">Requirements</span></span>

<span data-ttu-id="7869a-114">Прежде чем Комнаты Microsoft Teams с Exchange Online, убедитесь, что выполнены требования.</span><span class="sxs-lookup"><span data-stu-id="7869a-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="7869a-115">Дополнительные сведения см. в Комнаты Microsoft Teams [требованиях.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="7869a-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="7869a-116">Чтобы развернуть Комнаты Microsoft Teams с Exchange Online, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7869a-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="7869a-117">Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="7869a-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="7869a-118">Модуль Azure Active Directory для [Windows PowerShell](/powershell/azure/active-directory/overview?view=azureadps-1.0) в этом разделе (например, Set-MsolUser) протестирован при настройке учетных записей для Комнаты Microsoft Teams устройств.</span><span class="sxs-lookup"><span data-stu-id="7869a-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="7869a-119">Возможно, другие cmdlets могут работать, но они не были протестированы в этом конкретном сценарии.</span><span class="sxs-lookup"><span data-stu-id="7869a-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="7869a-120">Если вы развернули службы федерации Active Directory (AD FS), вам может потребоваться преобразовать учетную запись пользователя в управляемого пользователя, прежде чем выполнять эти действия, а затем преобразовать пользователя обратно в федератора.</span><span class="sxs-lookup"><span data-stu-id="7869a-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="7869a-121">Создание учетной записи и настройка свойств Exchange</span><span class="sxs-lookup"><span data-stu-id="7869a-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="7869a-122">Начните удаленный сеанс Windows PowerShell на компьютере и подключите его к Exchange Online следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7869a-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="7869a-123">После создания сеанса вам нужно создать новый почтовый ящик и включить его в качестве учетной записи RoomMailboxAccount или изменить параметры существующего почтового ящика комнаты.</span><span class="sxs-lookup"><span data-stu-id="7869a-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="7869a-124">Это позволит учетной записи в Комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7869a-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="7869a-125">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="7869a-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="7869a-126">Если вы создаете новый почтовый ящик ресурса:</span><span class="sxs-lookup"><span data-stu-id="7869a-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="7869a-127">Чтобы улучшить собрание, необходимо настроить свойства Exchange для учетной записи пользователя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7869a-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="7869a-128">Добавление адреса электронной почты для локальной учетной записи домена</span><span class="sxs-lookup"><span data-stu-id="7869a-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="7869a-129">В **средстве Active Directory Users and Computers AD** щелкните правой кнопкой мыши контейнер или организационную единицу, в котором будут созданы учетные записи Комнаты Microsoft Teams, нажмите кнопку Создать **и** выберите пользователь **.**</span><span class="sxs-lookup"><span data-stu-id="7869a-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="7869a-130">В поле Полное имя введите отображаемого имени (- удостоверение) из предыдущего cmdlet (Set-Mailbox  или New-Mailbox) и псевдоним в поле Имя пользователя. </span><span class="sxs-lookup"><span data-stu-id="7869a-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="7869a-131">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7869a-131">Click **Next**.</span></span>
3. <span data-ttu-id="7869a-p108">Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="7869a-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7869a-135">Выбор пароля **сроком действия не истекает** — это требование для Skype для бизнеса Server в Комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7869a-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="7869a-136">В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена.</span><span class="sxs-lookup"><span data-stu-id="7869a-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="7869a-137">В этом случае необходимо создать исключение для каждой учетной записи Комнаты Microsoft Teams пользователя.</span><span class="sxs-lookup"><span data-stu-id="7869a-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="7869a-138">Чтобы создать учетную запись, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7869a-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="7869a-139">После создания учетной записи запустите синхронизацию каталогов.</span><span class="sxs-lookup"><span data-stu-id="7869a-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="7869a-140">Для этого можно использовать [set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7869a-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="7869a-141">После этого перейдите на страницу пользователи и убедитесь, что две учетные записи, созданные на предыдущих шагах, объединены.</span><span class="sxs-lookup"><span data-stu-id="7869a-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="7869a-142">Назначение лицензии Microsoft 365 или Office 365 лицензии</span><span class="sxs-lookup"><span data-stu-id="7869a-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="7869a-143">Сначала подключите Azure AD, чтобы применить некоторые параметры учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7869a-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="7869a-144">Для подключения можно использовать следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="7869a-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="7869a-145">Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="7869a-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="7869a-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="7869a-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="7869a-147">У учетной записи пользователя должна быть действительная лицензия Microsoft 365 или Office 365, чтобы Exchange и Skype для бизнеса Server работать.</span><span class="sxs-lookup"><span data-stu-id="7869a-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="7869a-148">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7869a-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="7869a-149">Задание вы получите в следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="7869a-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="7869a-150">Затем используйте `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="7869a-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="7869a-151">чтобы получить список доступных skUs для вашей Microsoft 365 или Office 365 организации.</span><span class="sxs-lookup"><span data-stu-id="7869a-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="7869a-152">После добавления номеров номеров номеров ВКК вы можете добавить лицензию с помощью `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="7869a-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="7869a-153">Командлет.</span><span class="sxs-lookup"><span data-stu-id="7869a-153">cmdlet.</span></span> <span data-ttu-id="7869a-154">В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="7869a-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="7869a-155">Включить учетную запись пользователя с помощью Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7869a-155">Enable the user account with Skype for Business Server</span></span>

> [!NOTE]
> <span data-ttu-id="7869a-156">Если вы настраиваете Комнаты Teams только для Microsoft Teams собраний, вам не нужно делать следующее:</span><span class="sxs-lookup"><span data-stu-id="7869a-156">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="7869a-157">Следующие действия необходимы только в том случае, если вы хотите включить поддержку Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7869a-157">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="7869a-158">Создайте удаленный сеанс Windows PowerShell на компьютере следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7869a-158">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="7869a-159">Skype для бизнеса В настоящее время Online Connector является частью последней версии Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7869a-159">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="7869a-160">Если вы используете последний общедоступный [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="7869a-160">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. <span data-ttu-id="7869a-161">Чтобы включить учетную запись Комнаты Microsoft Teams для Skype для бизнеса Server, с помощью этой команды:</span><span class="sxs-lookup"><span data-stu-id="7869a-161">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="7869a-162">Если вы не знаете, какое значение нужно использовать для параметра RegistrarPool в вашей среде, вы можете получить это значение от существующего пользователя Skype для бизнеса Server с помощью этой команды</span><span class="sxs-lookup"><span data-stu-id="7869a-162">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="7869a-163">Назначение лицензии Skype для бизнеса Server вашей учетной записи Комнаты Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7869a-163">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

> [!NOTE]
> <span data-ttu-id="7869a-164">Если вы настраиваете Комнаты Teams только для Microsoft Teams собраний, вам не нужно делать следующее:</span><span class="sxs-lookup"><span data-stu-id="7869a-164">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="7869a-165">Следующие действия необходимы только в том случае, если вы хотите включить поддержку Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7869a-165">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="7869a-166">Войдите в систему как администратор клиента, откройте центр администрирования Microsoft 365 и щелкните приложение Администратор.</span><span class="sxs-lookup"><span data-stu-id="7869a-166">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="7869a-167">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="7869a-167">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="7869a-168">Щелкните Комнаты Microsoft Teams учетной записи, а затем щелкните значок пера, чтобы изменить сведения об учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7869a-168">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="7869a-169">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="7869a-169">Click **Licenses**.</span></span>
5. <span data-ttu-id="7869a-170">В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7869a-170">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="7869a-171">Если вы хотите использовать Корпоративная голосовая связь плана 3, Комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7869a-171">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="7869a-172">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7869a-172">Click **Save**.</span></span>

<span data-ttu-id="7869a-173">Для проверки вы сможете использовать любой клиент Skype для бизнеса для входа в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="7869a-173">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="7869a-174">Если вы используете ВКП E1, E3, E4 или E5 с Skype для бизнеса плана 2 с аудиоконференцией или с телефонная система и планом звонков, эти функции будут продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="7869a-174">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="7869a-175">Однако следует двигаться на более простую модель лицензирования, как описано в Teams Конференц-зал лицензирования [,](rooms-licensing.md)после истечения срока действия текущих лицензий.</span><span class="sxs-lookup"><span data-stu-id="7869a-175">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7869a-176">Если вы используете Skype для бизнеса 2, вы можете использовать Комнаты Microsoft Teams только в режиме Skype для бизнеса, то есть все собрания будут Skype для бизнеса собраниями.</span><span class="sxs-lookup"><span data-stu-id="7869a-176">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="7869a-177">Чтобы включить в комнате для Microsoft Teams собрания, рекомендуем приобрести лицензию Конференц-зал собрания.</span><span class="sxs-lookup"><span data-stu-id="7869a-177">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7869a-178">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7869a-178">Related topics</span></span>

[<span data-ttu-id="7869a-179">Настройка учетных записей для Комнаты Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7869a-179">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="7869a-180">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7869a-180">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="7869a-181">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7869a-181">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="7869a-182">Настройка консоли комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7869a-182">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="7869a-183">Управление комнатами Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7869a-183">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
