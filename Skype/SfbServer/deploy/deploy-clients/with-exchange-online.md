---
title: Развертывание Систем комнат Skype версии 2 в среде Exchange Online
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Exchange Online.
ms.openlocfilehash: 51a1f4089dfb3453802e8d3241869c3c325c904c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883246"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="9886d-103">Развертывание Систем комнат Skype версии 2 в среде Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9886d-103">Deploy Skype Room Systems v2 with Exchange Online</span></span> 
 
<span data-ttu-id="9886d-104">В данном разделе приведены сведения о развертывании версии 2 Скайп комнаты систем на базе Exchange Online и Скайп для Business Server локальных.</span><span class="sxs-lookup"><span data-stu-id="9886d-104">Read this topic for information on how to deploy Skype Room Systems v2 with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="9886d-105">Если в организации имеется набор служб, с некоторыми размещенных в локальную организацию и некоторые размещаются в сети, конфигурации будут зависеть от размещение каждой службы.</span><span class="sxs-lookup"><span data-stu-id="9886d-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="9886d-106">В этом разделе рассматривается гибридного развертывания в системах комнаты Скайп версии 2 с сервером Exchange, размещенных в Интернете.</span><span class="sxs-lookup"><span data-stu-id="9886d-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted online.</span></span> <span data-ttu-id="9886d-107">Из-за слишком большом числе различные варианты в этом типе развертывания, не поддерживается представлены подробные инструкции по их все.</span><span class="sxs-lookup"><span data-stu-id="9886d-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="9886d-108">Процесс будет работать для многих конфигураций.</span><span class="sxs-lookup"><span data-stu-id="9886d-108">The following process will work for many configurations.</span></span> <span data-ttu-id="9886d-109">Если процесс не подходит для вашей установки, мы рекомендуем использовать Windows PowerShell для достижения же конечный результат, как описано ниже, а также другие параметры развертывания.</span><span class="sxs-lookup"><span data-stu-id="9886d-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> 

<span data-ttu-id="9886d-110">Настройка учетных записей пользователей проще всего настроить их с помощью удаленной оболочки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9886d-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="9886d-111">Корпорация Майкрософт предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или validate существующие учетные записи ресурсов, что у вас есть помогающих перевод их в совместимые учетных записей пользователей системы комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="9886d-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="9886d-112">При необходимости можно выполните следующие действия, чтобы настроить учетные записи, используемые устройства версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="9886d-112">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>


  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="9886d-113">Развертывание Систем комнат Skype версии 2 в среде Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9886d-113">Deploy Skype Room Systems v2 with Exchange Online</span></span>

<span data-ttu-id="9886d-114">Перед развертыванием системы комнаты Скайп версии 2 с Exchange Online убедитесь, что удовлетворены требования.</span><span class="sxs-lookup"><span data-stu-id="9886d-114">Before you deploy Skype Room Systems v2 with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="9886d-115">Для получения дополнительных сведений см [систем комнаты Скайп версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9886d-115">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="9886d-116">Развертывание системы комнаты Скайп версии 2 с Exchange Online, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9886d-116">To deploy Skype Room Systems v2 with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="9886d-117">Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="9886d-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="9886d-118">Создание учетной записи и настройка свойств Exchange</span><span class="sxs-lookup"><span data-stu-id="9886d-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="9886d-119">Для запуска удаленного сеанса Windows PowerShell на ПК и подключитесь к Exchange Online, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9886d-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="9886d-120">После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="9886d-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="9886d-121">Это позволит учетной записи для проверки подлинности в системах комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="9886d-121">This will allow the account to authenticate into Skype Room Systems v2.</span></span>
    
   <span data-ttu-id="9886d-122">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="9886d-122">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="9886d-123">Если вы создаете новый почтовый ящик ресурса:</span><span class="sxs-lookup"><span data-stu-id="9886d-123">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="9886d-124">Чтобы улучшить работу в собрание, то необходимо для задания свойств Exchange учетной записи пользователя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9886d-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. <span data-ttu-id="9886d-p106">Для применения некоторых настроек учетной записи потребуется подключиться к Azure AD. Для подключения можно использовать следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="9886d-p106">You need to connect to Azure AD to apply some account settings. You can run this cmdlet to connect.</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="9886d-127">Добавление адреса электронной почты для локальной учетной записи домена</span><span class="sxs-lookup"><span data-stu-id="9886d-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="9886d-128">Средства **Active Directory — пользователи и компьютеры AD** щелкните правой кнопкой мыши папку или подразделение, что системы комнаты Скайп v2 учетные записи будут создаваться в, нажмите кнопку **Создать**и выберите пункт **пользователь**.</span><span class="sxs-lookup"><span data-stu-id="9886d-128">In **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and the click **User**.</span></span>
    
2. <span data-ttu-id="9886d-p107">Введите отображаемое имя из предыдущего командлета в поле **Полное имя**, а затем псевдоним в поле **Имя входа пользователя**. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9886d-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>


3. <span data-ttu-id="9886d-p108">Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="9886d-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9886d-134">Выбор **Срок действия пароля не ограничен** является обязательным требованием для Скайп для Business Server на Скайп комнаты систем версии 2.</span><span class="sxs-lookup"><span data-stu-id="9886d-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="9886d-135">В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена.</span><span class="sxs-lookup"><span data-stu-id="9886d-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="9886d-136">Если Да, необходимо создать исключение для каждой учетной записи пользователя систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="9886d-136">If so, you'll need to create an exception for each Skype Room Systems v2 user account.</span></span>
  
4. <span data-ttu-id="9886d-137">Чтобы создать учетную запись, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9886d-137">Click **Finish** to create the account.</span></span>
    
5. <span data-ttu-id="9886d-p110">После создания учетной записи выполните синхронизацию каталогов. По завершении этого процесса перейдите на страницу пользователей и убедитесь, что две созданные на предыдущих шагах учетные записи объединены.</span><span class="sxs-lookup"><span data-stu-id="9886d-p110">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>
    
### <a name="assign-an-office-365-license"></a><span data-ttu-id="9886d-140">Назначение лицензии Office 365</span><span class="sxs-lookup"><span data-stu-id="9886d-140">Assign an Office 365 license</span></span>

1. <span data-ttu-id="9886d-141">Учетная запись должна иметь действительной лицензии Office 365, чтобы убедиться, что Скайп для Business Server и Exchange будут работать.</span><span class="sxs-lookup"><span data-stu-id="9886d-141">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="9886d-142">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="9886d-142">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="9886d-143">Затем используйте Get-MsolAccountSku для получения списка доступных номеров SKU для клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="9886d-143">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="9886d-p112">После этого вы можете добавить лицензию с помощью командлета Set-MsolUserLicense. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="9886d-p112">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="9886d-146">Включение учетной записи пользователя с помощью Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="9886d-146">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="9886d-147">Создайте удаленного сеанса Windows PowerShell с ПК, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="9886d-147">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="9886d-148">Включение учетной записи системы комнаты Скайп версии 2 для Скайп для Business Server, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9886d-148">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="9886d-149">Если вы не уверены, используйте для параметра RegistrarPool в вашей среде, можно получить значение из существующего Скайп для пользователя Business Server, с помощью этой команды</span><span class="sxs-lookup"><span data-stu-id="9886d-149">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="9886d-150">Назначение Скайп лицензию Business Server для учетной записи системы комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="9886d-150">Assign a Skype for Business Server license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="9886d-151">Выполните вход в качестве администратора клиента, откройте административного портала Office 365 и щелкните приложения администрирования.</span><span class="sxs-lookup"><span data-stu-id="9886d-151">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="9886d-152">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="9886d-152">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="9886d-153">Щелкните учетную запись комнаты систем Скайп версии 2 и нажмите кнопку перо значок, чтобы изменить сведения об учетной записи.</span><span class="sxs-lookup"><span data-stu-id="9886d-153">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="9886d-154">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="9886d-154">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="9886d-155">В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9886d-155">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="9886d-156">Вам потребуется использовать лицензии планирование 3, если вы хотите использовать корпоративной голосовой связи на вашей версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="9886d-156">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="9886d-157">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="9886d-157">Click **Save**.</span></span>
    
<span data-ttu-id="9886d-158">Для проверки можно использовать любой Скайп для бизнеса клиента для входа в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="9886d-158">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9886d-159">См. также</span><span class="sxs-lookup"><span data-stu-id="9886d-159">See also</span></span>

[<span data-ttu-id="9886d-160">Настройка учетных записей для систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="9886d-160">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="9886d-161">Планирование для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="9886d-161">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="9886d-162">Развертывание Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="9886d-162">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="9886d-163">Настройка консоли для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="9886d-163">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="9886d-164">Управление Системами комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="9886d-164">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

