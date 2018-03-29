---
title: Развертывание Систем комнат Skype версии 2 в среде Exchange Online (гибридное)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Exchange Online.
ms.openlocfilehash: 59724ae9b0fc77f16a072e0e08b125407c6e43e3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online-hybrid"></a><span data-ttu-id="460b5-103">Развертывание Систем комнат Skype версии 2 в среде Exchange Online (гибридное)</span><span class="sxs-lookup"><span data-stu-id="460b5-103">Deploy Skype Room Systems v2 with Exchange Online (Hybrid)</span></span>
 
<span data-ttu-id="460b5-104">В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="460b5-104">Read this topic for information on how to deploy Skype Room Systems v2 with Exchange Online.</span></span>
  
<span data-ttu-id="460b5-105">Если в организации имеется набор служб, с некоторыми размещенных в локальную организацию и некоторые размещаются в сети, конфигурации будут зависеть от размещение каждой службы.</span><span class="sxs-lookup"><span data-stu-id="460b5-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="460b5-106">В этом разделе рассматривается гибридного развертывания в системах комнаты Скайп версии 2 с сервером Exchange, размещенных в Интернете.</span><span class="sxs-lookup"><span data-stu-id="460b5-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted online.</span></span> <span data-ttu-id="460b5-107">Из-за слишком большом числе различные варианты в этом типе развертывания, не поддерживается представлены подробные инструкции по их все.</span><span class="sxs-lookup"><span data-stu-id="460b5-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="460b5-108">Процесс будет работать для многих конфигураций.</span><span class="sxs-lookup"><span data-stu-id="460b5-108">The following process will work for many configurations.</span></span> <span data-ttu-id="460b5-109">Если процесс не подходит для вашей установки, мы рекомендуем использовать Windows PowerShell (содержатся в приложении: PowerShell) для достижения же конечный результат, как описано ниже, а также другие параметры развертывания.</span><span class="sxs-lookup"><span data-stu-id="460b5-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell (see Appendix: PowerShell) to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="460b5-110">Затем следует использовать предоставленный сценарий Windows PowerShell для проверки установки версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="460b5-110">You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup.</span></span> <span data-ttu-id="460b5-111">(См. сценарий проверки учетной записи).</span><span class="sxs-lookup"><span data-stu-id="460b5-111">(See Account Verification Script.)</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="460b5-112">Развертывание Систем комнат Skype версии 2 в среде Exchange Online</span><span class="sxs-lookup"><span data-stu-id="460b5-112">Deploy Skype Room Systems v2 with Exchange Online</span></span>

<span data-ttu-id="460b5-113">Перед развертыванием системы комнаты Скайп версии 2 с Exchange Online убедитесь, что удовлетворены требования.</span><span class="sxs-lookup"><span data-stu-id="460b5-113">Before you deploy Skype Room Systems v2 with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="460b5-114">Для получения дополнительных сведений см [систем комнаты Скайп версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="460b5-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="460b5-115">Развертывание системы комнаты Скайп версии 2 с Exchange Online, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="460b5-115">To deploy Skype Room Systems v2 with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="460b5-116">Убедитесь в том, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="460b5-116">Be sure you have the right permissions to run the associated cmdlets.</span></span> 
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="460b5-117">Создание учетной записи и настройка свойств Exchange</span><span class="sxs-lookup"><span data-stu-id="460b5-117">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="460b5-118">Для запуска удаленного сеанса Windows PowerShell на ПК и подключитесь к Exchange Online, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="460b5-118">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>
    
  ```
  Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic 
-AllowRedirection

  ```

2. <span data-ttu-id="460b5-119">После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="460b5-119">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="460b5-120">Это позволит учетной записи для проверки подлинности в системах комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="460b5-120">This will allow the account to authenticate into Skype Room Systems v2.</span></span>
    
   <span data-ttu-id="460b5-121">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="460b5-121">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="460b5-122">Если вы создаете новый почтовый ящик ресурса:</span><span class="sxs-lookup"><span data-stu-id="460b5-122">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="460b5-123">Чтобы улучшить работу в собрание, то необходимо для задания свойств Exchange учетной записи пользователя следующим образом:</span><span class="sxs-lookup"><span data-stu-id="460b5-123">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="460b5-p105">Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="460b5-p105">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="460b5-127">Выбор **Срок действия пароля не ограничен** является обязательным требованием для Скайп для Business Server 2015 на систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="460b5-127">Selecting **Password never expires** is a requirement for Skype for Business Server 2015 on Skype Room Systems v2.</span></span> <span data-ttu-id="460b5-128">В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена.</span><span class="sxs-lookup"><span data-stu-id="460b5-128">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="460b5-129">Если Да, необходимо создать исключение для каждой учетной записи пользователя систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="460b5-129">If so, you'll need to create an exception for each Skype Room Systems v2 user account.</span></span>
  
5. <span data-ttu-id="460b5-130">Чтобы создать учетную запись, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="460b5-130">Click **Finish** to create the account.</span></span>
    
6. <span data-ttu-id="460b5-p107">После создания учетной записи выполните синхронизацию каталогов. По завершении этого процесса перейдите на страницу пользователей и убедитесь, что две созданные на предыдущих шагах учетные записи объединены.</span><span class="sxs-lookup"><span data-stu-id="460b5-p107">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>
    
7. <span data-ttu-id="460b5-p108">Для применения некоторых настроек учетной записи потребуется подключиться к Azure AD. Для подключения можно использовать следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="460b5-p108">You need to connect to Azure AD to apply some account settings. You can run this cmdlet to connect.</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="460b5-135">Добавление адреса электронной почты для локальной учетной записи домена</span><span class="sxs-lookup"><span data-stu-id="460b5-135">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="460b5-136">Средства **Active Directory — пользователи и компьютеры AD** щелкните правой кнопкой мыши папку или подразделение, что системы комнаты Скайп v2 учетные записи будут создаваться в, нажмите кнопку **Создать**и выберите пункт **пользователь**.</span><span class="sxs-lookup"><span data-stu-id="460b5-136">In **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and the click **User**.</span></span>
    
2. <span data-ttu-id="460b5-p109">Введите отображаемое имя из предыдущего командлета в поле **Полное имя**, а затем псевдоним в поле **Имя входа пользователя**. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="460b5-p109">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>
    
### <a name="assign-an-office-365-license"></a><span data-ttu-id="460b5-139">Назначение лицензии Office 365</span><span class="sxs-lookup"><span data-stu-id="460b5-139">Assign an Office 365 license</span></span>

1. <span data-ttu-id="460b5-140">Учетная запись должна иметь действительной лицензии Office 365, чтобы убедиться, что Скайп для Business Server 2015 и Exchange будут работать.</span><span class="sxs-lookup"><span data-stu-id="460b5-140">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server 2015 will work.</span></span> <span data-ttu-id="460b5-141">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="460b5-141">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="460b5-142">Затем используйте Get-MsolAccountSku для получения списка доступных номеров SKU для клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="460b5-142">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="460b5-p111">После этого вы можете добавить лицензию с помощью командлета Set-MsolUserLicense. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="460b5-p111">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-user-account-with-skype-for-business-server-2015"></a><span data-ttu-id="460b5-145">Включение учетной записи пользователя со Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="460b5-145">Enable the user account with Skype for Business Server 2015</span></span>

1. <span data-ttu-id="460b5-146">Создайте удаленного сеанса Windows PowerShell с ПК, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="460b5-146">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
  ```
  Import-Module LyncOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber

  ```

2. <span data-ttu-id="460b5-147">Включение учетной записи системы комнаты Скайп версии 2 для Скайп для Business Server 2015, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="460b5-147">To enable your Skype Room Systems v2 account for Skype for Business Server 2015, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="460b5-148">Если вы не уверены, используйте для параметра RegistrarPool в вашей среде, можно получить значение из существующего Скайп для пользователя Business Server 2015, с помощью этой команды</span><span class="sxs-lookup"><span data-stu-id="460b5-148">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server 2015 user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-2015-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="460b5-149">Назначение лицензии Skype для бизнеса Server 2015 своей учетной записи Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="460b5-149">Assign a Skype for Business Server 2015 license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="460b5-150">Выполните вход в качестве администратора клиента, откройте административного портала Office 365 и щелкните приложения администрирования.</span><span class="sxs-lookup"><span data-stu-id="460b5-150">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="460b5-151">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="460b5-151">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="460b5-152">Щелкните учетную запись комнаты систем Скайп версии 2 и нажмите кнопку перо значок, чтобы изменить сведения об учетной записи.</span><span class="sxs-lookup"><span data-stu-id="460b5-152">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="460b5-153">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="460b5-153">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="460b5-154">В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="460b5-154">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="460b5-155">Вам потребуется использовать лицензии планирование 3, если вы хотите использовать корпоративной голосовой связи на вашей версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="460b5-155">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="460b5-156">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="460b5-156">Click **Save**.</span></span>
    
<span data-ttu-id="460b5-157">Для проверки можно использовать любой Скайп для бизнеса клиента для входа в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="460b5-157">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="460b5-158">См. также</span><span class="sxs-lookup"><span data-stu-id="460b5-158">See also</span></span>

#### 

[<span data-ttu-id="460b5-159">Планирование для помещения Скайп систем версии 2</span><span class="sxs-lookup"><span data-stu-id="460b5-159">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="460b5-160">Развертывание Скайп комнаты систем версии 2</span><span class="sxs-lookup"><span data-stu-id="460b5-160">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="460b5-161">Настройка консоли систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="460b5-161">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="460b5-162">Управление Скайп комнаты систем версии 2</span><span class="sxs-lookup"><span data-stu-id="460b5-162">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

