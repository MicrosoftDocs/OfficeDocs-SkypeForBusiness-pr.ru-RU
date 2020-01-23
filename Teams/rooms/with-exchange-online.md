---
title: Развертывание комнаты Microsoft Teams с Exchange Online
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Сведения о том, как развертывать комнаты Microsoft Teams с помощью Exchange Online, читайте в этой статье.
ms.openlocfilehash: fc403e2553fce157737b1bdda75c821563e6b0dd
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269207"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="77a78-103">Развертывание комнаты Microsoft Teams с Exchange Online</span><span class="sxs-lookup"><span data-stu-id="77a78-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="77a78-104">В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams с помощью Exchange Online и Skype для бизнеса Server в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="77a78-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="77a78-105">Если в вашей организации есть смесь служб, а некоторые размещены в локальной сети, а некоторые — в Интернете, ваша конфигурация будет зависеть от того, где размещена каждая служба.</span><span class="sxs-lookup"><span data-stu-id="77a78-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="77a78-106">В этой статье рассказывается о гибридных развертываниях комнат Microsoft Teams с Exchange, размещенных в Интернете.</span><span class="sxs-lookup"><span data-stu-id="77a78-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="77a78-107">Так как в этом типе развертывания существует множество различных вариантов, невозможно предоставить подробные инструкции для всех.</span><span class="sxs-lookup"><span data-stu-id="77a78-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="77a78-108">Для многих конфигураций будет работать следующий процесс.</span><span class="sxs-lookup"><span data-stu-id="77a78-108">The following process will work for many configurations.</span></span> <span data-ttu-id="77a78-109">Если вы не можете выполнить процесс настройки, мы рекомендуем использовать Windows PowerShell, чтобы получить тот же самый конечный результат, который вы описывали здесь, и для других вариантов развертывания.</span><span class="sxs-lookup"><span data-stu-id="77a78-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="77a78-110">Самый простой способ настроить учетные записи пользователей — настроить их с помощью удаленной оболочки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77a78-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="77a78-111">Корпорация Майкрософт предоставляет [скиперумпровисионингскрипт. ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или проверить имеющиеся учетные записи ресурсов, чтобы их можно было превратить в совместимые учетные записи Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77a78-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="77a78-112">Если вы предпочитаете, выполните указанные ниже действия, чтобы настроить учетные записи, которые будут использоваться на устройстве комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77a78-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="77a78-113">Требования</span><span class="sxs-lookup"><span data-stu-id="77a78-113">Requirements</span></span>

<span data-ttu-id="77a78-114">Перед развертыванием комнат Microsoft Teams в Exchange Online убедитесь, что вы удовлетворены требованиями.</span><span class="sxs-lookup"><span data-stu-id="77a78-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="77a78-115">Дополнительные сведения можно найти в разделе [требования к комнатам Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77a78-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="77a78-116">Чтобы развернуть комнаты Microsoft Teams в Exchange Online, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="77a78-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="77a78-117">Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="77a78-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="77a78-118">[Модуль Azure Active Directory для командлетов Windows PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) в этом разделе (например, Set-MsolUser) был протестирован в настройке учетных записей для устройств Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77a78-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="77a78-119">Возможно, другие командлеты работают, но они не тестировались в этом конкретном сценарии.</span><span class="sxs-lookup"><span data-stu-id="77a78-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="77a78-120">Создание учетной записи и настройка свойств Exchange</span><span class="sxs-lookup"><span data-stu-id="77a78-120">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="77a78-121">Запустите удаленный сеанс Windows PowerShell на компьютере и подключитесь к Exchange Online, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="77a78-121">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
Import-PSSession $Session -DisableNameChecking
```

2. <span data-ttu-id="77a78-122">После установления сеанса вы сможете создать новый почтовый ящик и включить его в качестве Руммаилбоксаккаунт или изменить параметры существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="77a78-122">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="77a78-123">Это позволит вашей учетной записи проходить проверку подлинности в комнатах Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77a78-123">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="77a78-124">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="77a78-124">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="77a78-125">Если вы создаете новый почтовый ящик ресурса, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="77a78-125">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="77a78-126">Чтобы улучшить взаимодействие с собраниями, необходимо настроить свойства Exchange для учетной записи пользователя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="77a78-126">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="77a78-127">Добавление адреса электронной почты для локальной учетной записи домена</span><span class="sxs-lookup"><span data-stu-id="77a78-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="77a78-128">В средстве **AD Active Directory — пользователи и компьютеры** , щелкните правой кнопкой мыши контейнер или подразделение, в котором будут создаваться учетные записи Microsoft Teams, а затем нажмите кнопку " **создать**", а затем выберите пункт " **пользователь**".</span><span class="sxs-lookup"><span data-stu-id="77a78-128">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="77a78-129">Введите отображаемое имя (-Identity) из предыдущего командлета (Set-Mailbox или New-Mailbox) в поле **полное имя** и псевдоним в поле **имя пользователя для входа** .</span><span class="sxs-lookup"><span data-stu-id="77a78-129">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="77a78-130">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="77a78-130">Click **Next**.</span></span>
3. <span data-ttu-id="77a78-p108">Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="77a78-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="77a78-134">Выбор **срока действия пароля неограничен** — требование для сервера Skype для бизнеса в комнатах Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77a78-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="77a78-135">В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена.</span><span class="sxs-lookup"><span data-stu-id="77a78-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="77a78-136">Если да, вам потребуется создать исключение для каждой учетной записи пользователя комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77a78-136">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="77a78-137">Чтобы создать учетную запись, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="77a78-137">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="77a78-138">Создав учетную запись, выполните синхронизацию службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="77a78-138">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="77a78-139">Это можно сделать с помощью [Set-мсолдирсинкконфигуратион](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77a78-139">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="77a78-140">После этого перейдите на страницу "Пользователи" и убедитесь в том, что две учетные записи, созданные в предыдущих шагах, объединены.</span><span class="sxs-lookup"><span data-stu-id="77a78-140">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="77a78-141">Назначение лицензии Office 365</span><span class="sxs-lookup"><span data-stu-id="77a78-141">Assign an Office 365 license</span></span>

1. <span data-ttu-id="77a78-142">Сначала подключитесь к Azure AD, чтобы применить некоторые параметры учетной записи.</span><span class="sxs-lookup"><span data-stu-id="77a78-142">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="77a78-143">Для подключения можно использовать следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="77a78-143">You can run this cmdlet to connect.</span></span> <span data-ttu-id="77a78-144">Подробнее об Active Directory можно узнать в [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="77a78-144">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="77a78-145">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="77a78-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="77a78-146">Для обеспечения работоспособности Exchange и Skype для бизнеса сервер учетной записи пользователя должен быть действительной лицензией Office 365.</span><span class="sxs-lookup"><span data-stu-id="77a78-146">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="77a78-147">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="77a78-147">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="77a78-148">Назначение будет проводиться на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="77a78-148">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="77a78-149">Затем используйте`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="77a78-149">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="77a78-150">Получение списка доступных SKU для клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="77a78-150">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="77a78-151">После того как вы выйдете список SKU, вы можете добавить лицензию с помощью`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="77a78-151">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="77a78-152">Командлет.</span><span class="sxs-lookup"><span data-stu-id="77a78-152">cmdlet.</span></span> <span data-ttu-id="77a78-153">В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="77a78-153">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

  ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="77a78-154">Включение учетной записи пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77a78-154">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="77a78-155">Создайте удаленный сеанс Windows PowerShell на компьютере, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="77a78-155">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="77a78-156">Чтобы включить учетные записи Microsoft Teams для Skype для бизнеса Server, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="77a78-156">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="77a78-157">Если вы не знаете, какое значение использовать для параметра Регистрарпул в вашей среде, вы можете получить значение из существующего пользователя Skype для бизнеса Server с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="77a78-157">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="77a78-158">Назначение лицензии Skype для бизнеса Server для учетной записи комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77a78-158">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="77a78-159">Войдите в систему как администратор клиента, откройте административный портал Office 365 и щелкните Приложение администратор.</span><span class="sxs-lookup"><span data-stu-id="77a78-159">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="77a78-160">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="77a78-160">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="77a78-161">Щелкните учетную запись комнаты Microsoft Teams, а затем щелкните значок пера, чтобы изменить данные учетной записи.</span><span class="sxs-lookup"><span data-stu-id="77a78-161">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="77a78-162">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="77a78-162">Click **Licenses**.</span></span>
5. <span data-ttu-id="77a78-163">В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="77a78-163">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="77a78-164">Если вы хотите использовать корпоративную голосовую связь в комнатах Microsoft Teams, вам придется использовать лицензию на план 3.</span><span class="sxs-lookup"><span data-stu-id="77a78-164">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="77a78-165">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="77a78-165">Click **Save**.</span></span>

<span data-ttu-id="77a78-166">Для проверки подлинности вы можете войти в эту учетную запись с помощью любого клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="77a78-166">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="77a78-167">См. также</span><span class="sxs-lookup"><span data-stu-id="77a78-167">See also</span></span>

[<span data-ttu-id="77a78-168">Настройка учетных записей для комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77a78-168">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="77a78-169">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77a78-169">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="77a78-170">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77a78-170">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="77a78-171">Настройка консоли Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77a78-171">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="77a78-172">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="77a78-172">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
