---
title: Развертывание групп Майкрософт комнат с Exchange Online
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: В данном разделе приведены сведения о развертывании Microsoft группами комнат с Exchange Online.
ms.openlocfilehash: 55b62656d5ddf7fdc7a1139f1c4eaf5c055437fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916271"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="3dace-103">Развертывание групп Майкрософт комнат с Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3dace-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="3dace-104">В данном разделе приведены сведения о том, как развернуть комнатам группы Microsoft Exchange Online и Скайп для Business Server в локальной.</span><span class="sxs-lookup"><span data-stu-id="3dace-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="3dace-105">Если в организации имеется набор служб, с некоторыми размещенных в локальную организацию и некоторые размещаются в сети, конфигурации будут зависеть от размещение каждой службы.</span><span class="sxs-lookup"><span data-stu-id="3dace-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="3dace-106">В этом разделе описываются гибридные развертывания для комнат группами Майкрософт с сервером Exchange, размещенных в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3dace-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="3dace-107">Из-за слишком большом числе различные варианты в этом типе развертывания, не поддерживается представлены подробные инструкции по их все.</span><span class="sxs-lookup"><span data-stu-id="3dace-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="3dace-108">Процесс будет работать для многих конфигураций.</span><span class="sxs-lookup"><span data-stu-id="3dace-108">The following process will work for many configurations.</span></span> <span data-ttu-id="3dace-109">Если процесс не подходит для вашей установки, мы рекомендуем использовать Windows PowerShell для достижения же конечный результат, как описано ниже, а также другие параметры развертывания.</span><span class="sxs-lookup"><span data-stu-id="3dace-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="3dace-110">Настройка учетных записей пользователей проще всего настроить их с помощью удаленной оболочки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dace-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="3dace-111">Корпорация Майкрософт предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или validate существующие учетные записи ресурсов, что у вас есть помогающих перевод их в совместимые учетных записей пользователей комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3dace-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="3dace-112">При необходимости можно выполните следующие действия, чтобы настроить учетные записи, используемые устройства комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3dace-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="3dace-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3dace-113">Requirements</span></span>

<span data-ttu-id="3dace-114">Перед развертыванием комнат группами Майкрософт с Exchange Online убедитесь, что удовлетворены требования.</span><span class="sxs-lookup"><span data-stu-id="3dace-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="3dace-115">Для получения дополнительных сведений в разделе [requirements комнат группами Майкрософт](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dace-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="3dace-116">Чтобы развернуть комнат группами Майкрософт с Exchange Online, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3dace-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="3dace-117">Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="3dace-117">Be sure you have the right permissions to run the associated cmdlets.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="3dace-118">Создание учетной записи и настройка свойств Exchange</span><span class="sxs-lookup"><span data-stu-id="3dace-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="3dace-119">Для запуска удаленного сеанса Windows PowerShell на ПК и подключитесь к Exchange Online, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3dace-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="3dace-120">После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="3dace-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="3dace-121">Это позволит учетной записи для проверки подлинности в комнатах группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3dace-121">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="3dace-122">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="3dace-122">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="3dace-123">Если вы создаете новый почтовый ящик ресурса:</span><span class="sxs-lookup"><span data-stu-id="3dace-123">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="3dace-124">Чтобы улучшить работу в собрание, то необходимо для задания свойств Exchange учетной записи пользователя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3dace-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="3dace-125">Добавление адреса электронной почты для локальной учетной записи домена</span><span class="sxs-lookup"><span data-stu-id="3dace-125">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="3dace-126">Средства **Active Directory — пользователи и компьютеры AD** щелкните правой кнопкой мыши контейнер или подразделение, что вашей комнат группами Майкрософт, учетные записи будут создаваться в, нажмите кнопку **Создать**и выберите пункт **пользователь**.</span><span class="sxs-lookup"><span data-stu-id="3dace-126">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="3dace-127">Введите отображаемое имя (-Identity) из предыдущего командлета (Set-Mailbox или New-Mailbox) в поле **полное имя** и адрес в поле **имя входа пользователя** .</span><span class="sxs-lookup"><span data-stu-id="3dace-127">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="3dace-128">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3dace-128">Click **Next**.</span></span>
3. <span data-ttu-id="3dace-p107">Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="3dace-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3dace-132">Выбор **Срок действия пароля не ограничен** является обязательным требованием для Скайп для Business Server на комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3dace-132">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="3dace-133">В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена.</span><span class="sxs-lookup"><span data-stu-id="3dace-133">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="3dace-134">Если Да, необходимо создать исключение для каждой учетной записи пользователя комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3dace-134">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="3dace-135">Чтобы создать учетную запись, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3dace-135">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="3dace-p109">После создания учетной записи выполните синхронизацию каталогов. По завершении этого процесса перейдите на страницу пользователей и убедитесь, что две созданные на предыдущих шагах учетные записи объединены.</span><span class="sxs-lookup"><span data-stu-id="3dace-p109">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="3dace-138">Назначение лицензии Office 365</span><span class="sxs-lookup"><span data-stu-id="3dace-138">Assign an Office 365 license</span></span>

1. <span data-ttu-id="3dace-139">Во-первых подключение к Azure AD для применения некоторые параметры учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3dace-139">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="3dace-140">Для подключения можно использовать следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="3dace-140">You can run this cmdlet to connect.</span></span> <span data-ttu-id="3dace-141">Для получения дополнительных сведений об Active Directory просмотрите [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="3dace-141">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="3dace-142">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3dace-142">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="3dace-143">Учетная запись должна иметь действительной лицензии Office 365, чтобы убедиться, что Скайп для Business Server и Exchange будут работать.</span><span class="sxs-lookup"><span data-stu-id="3dace-143">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="3dace-144">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3dace-144">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="3dace-145">На следующем этапе будет внести назначения.</span><span class="sxs-lookup"><span data-stu-id="3dace-145">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="3dace-146">Затем используйте`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="3dace-146">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="3dace-147">Для получения списка доступных номеров SKU для клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="3dace-147">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="3dace-148">После список масштабирование номера SKU, можно добавить лицензии с помощью`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="3dace-148">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="3dace-149">командлет.</span><span class="sxs-lookup"><span data-stu-id="3dace-149">cmdlet.</span></span> <span data-ttu-id="3dace-150">В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="3dace-150">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="3dace-151">Включение учетной записи пользователя с помощью Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="3dace-151">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="3dace-152">Создайте удаленного сеанса Windows PowerShell с ПК, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="3dace-152">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="3dace-153">Включение учетной записи Microsoft группами комнат для Скайп для Business Server, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3dace-153">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="3dace-154">Если вы не уверены, используйте для параметра RegistrarPool в вашей среде, можно получить значение из существующего Скайп для пользователя Business Server, с помощью этой команды</span><span class="sxs-lookup"><span data-stu-id="3dace-154">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="3dace-155">Назначение Скайп для лицензий Business Server свою учетную запись Microsoft группами комнат</span><span class="sxs-lookup"><span data-stu-id="3dace-155">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="3dace-156">Выполните вход в качестве администратора клиента, откройте административного портала Office 365 и щелкните приложения администрирования.</span><span class="sxs-lookup"><span data-stu-id="3dace-156">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="3dace-157">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="3dace-157">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="3dace-158">Щелкните учетную запись Microsoft группами комнат и нажмите кнопку перо значок, чтобы изменить сведения об учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3dace-158">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="3dace-159">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="3dace-159">Click **Licenses**.</span></span>
5. <span data-ttu-id="3dace-160">В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="3dace-160">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="3dace-161">Вам потребуется использовать планирование 3 лицензии, если вы хотите использовать корпоративной голосовой связи на комнат группы Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3dace-161">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="3dace-162">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3dace-162">Click **Save**.</span></span>

<span data-ttu-id="3dace-163">Для проверки можно использовать любой Скайп для бизнеса клиента для входа в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="3dace-163">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3dace-164">См. также</span><span class="sxs-lookup"><span data-stu-id="3dace-164">See also</span></span>

[<span data-ttu-id="3dace-165">Настройка учетных записей для комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3dace-165">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="3dace-166">Планирование для групп Майкрософт комнат</span><span class="sxs-lookup"><span data-stu-id="3dace-166">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="3dace-167">Развертывание групп Майкрософт комнат</span><span class="sxs-lookup"><span data-stu-id="3dace-167">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="3dace-168">Настройка консоли комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3dace-168">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="3dace-169">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="3dace-169">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
