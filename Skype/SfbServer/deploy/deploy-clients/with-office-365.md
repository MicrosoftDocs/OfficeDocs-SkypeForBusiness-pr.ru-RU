---
title: Развертывание Систем комнат Skype версии 2 в среде Office 365
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Office 365.
ms.openlocfilehash: cccc86fce3eea00449b7737eabb618fa40afa6a6
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883026"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="05c0f-103">Развертывание Систем комнат Skype версии 2 в среде Office 365 </span><span class="sxs-lookup"><span data-stu-id="05c0f-103">Deploy Skype Room Systems v2 with Office 365</span></span>
 
<span data-ttu-id="05c0f-104">В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Office 365, где оба online находятся в Скайп для бизнеса и Exchange.</span><span class="sxs-lookup"><span data-stu-id="05c0f-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365, where Skype for Business and Exchange are both online.</span></span> 

<span data-ttu-id="05c0f-105">Настройка учетных записей пользователей проще всего настроить их с помощью удаленной оболочки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05c0f-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="05c0f-106">Корпорация Майкрософт предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или validate существующие учетные записи ресурсов, что у вас есть помогающих перевод их в совместимые учетных записей пользователей системы комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="05c0f-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="05c0f-107">При необходимости можно выполните следующие действия, чтобы настроить учетные записи, используемые устройства версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="05c0f-107">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="05c0f-108">Развертывание Систем комнат Skype версии 2 в среде Office 365 </span><span class="sxs-lookup"><span data-stu-id="05c0f-108">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="05c0f-109">Перед развертыванием системы комнаты Скайп версии 2 с Office 365, убедитесь, что удовлетворены требования.</span><span class="sxs-lookup"><span data-stu-id="05c0f-109">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="05c0f-110">Для получения дополнительных сведений см [систем комнаты Скайп версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05c0f-110">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="05c0f-111">Чтобы включить Скайп для бизнеса, необходимо иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="05c0f-111">To enable Skype for Business, you must have the following:</span></span>
  
- <span data-ttu-id="05c0f-112">Скайп для бизнеса в Интернет (план 2 или план на основе предприятия) или более поздней версии в плане Office 365.</span><span class="sxs-lookup"><span data-stu-id="05c0f-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="05c0f-113">Планирование необходимо разрешить возможности конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="05c0f-113">The plan needs to allow dial-in conferencing capabilities.</span></span>
    
- <span data-ttu-id="05c0f-114">Если вам требуется-связь с возможностями собрания, необходимо будет аудиоконференций и лицензии телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="05c0f-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="05c0f-115">Если вам требуется подключение по телефонной линии возможности из собрания, необходимо будет внутри страны или внутреннее и международное вызов план.</span><span class="sxs-lookup"><span data-stu-id="05c0f-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="05c0f-116">Клиент пользователи должны иметь почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="05c0f-116">Your tenant users must have Exchange mailboxes.</span></span>
    
- <span data-ttu-id="05c0f-117">Вашей систем комнаты Скайп версии 2 для учетной записи требуются в минимальный размер Скайп для бизнеса Online (план 2) лицензии, но не требует лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05c0f-117">Your Skype Room Systems v2 account does require at a minumum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span>

<span data-ttu-id="05c0f-118">Дополнительные сведения о Скайп для бизнеса Online планы см [Скайп для описания службы Online бизнеса](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="05c0f-118">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="05c0f-119">Добавление учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="05c0f-119">Add a device account</span></span>

1. <span data-ttu-id="05c0f-120">Для запуска удаленного сеанса Windows PowerShell на ПК и подключитесь к Exchange.</span><span class="sxs-lookup"><span data-stu-id="05c0f-120">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="05c0f-121">Убедитесь, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="05c0f-121">Be sure you have the right permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="05c0f-122">Ниже приведен ряд примеров командлетов, которые можно использовать и изменять в своей среде.</span><span class="sxs-lookup"><span data-stu-id="05c0f-122">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="05c0f-123">После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="05c0f-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="05c0f-124">Это позволит учетной записи для проверки подлинности системы комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="05c0f-124">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
  <span data-ttu-id="05c0f-125">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="05c0f-125">If you are changing an existing resource mailbox:</span></span>
    
```
Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

  <span data-ttu-id="05c0f-126">Если вы создаете новый почтовый ящик ресурса:</span><span class="sxs-lookup"><span data-stu-id="05c0f-126">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="05c0f-p107">Чтобы оптимизировать интерфейс собрания, можно настроить различные свойства Exchange для учетной записи устройства. Описание необходимых настроек приводится в разделе "Свойства Exchange".</span><span class="sxs-lookup"><span data-stu-id="05c0f-p107">Various Exchange properties must be set on the device account to improve the meeting experience. You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. <span data-ttu-id="05c0f-129">Для применения некоторых настроек учетной записи потребуется подключиться к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="05c0f-129">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="05c0f-130">Чтобы подключиться к Azure AD, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="05c0f-130">To connect to Azure AD, run the following cmdlet:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. <span data-ttu-id="05c0f-131">	Чтобы использовать пароль с неограниченным сроком действия, выполните командлет Set-MsolUser с параметром PasswordNeverExpires.  </span><span class="sxs-lookup"><span data-stu-id="05c0f-131">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   <span data-ttu-id="05c0f-132">Вы также можете задать номер телефона для комнаты следующим образом.</span><span class="sxs-lookup"><span data-stu-id="05c0f-132">You can also set a phone number for the room as follows:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. <span data-ttu-id="05c0f-133">Учетная запись устройства должна быть действительной лицензии Office 365 или Exchange и Скайп для бизнеса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="05c0f-133">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="05c0f-134">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="05c0f-134">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="05c0f-135">Get-MsolAccountSku можно использовать для получения списка доступных номеров SKU для клиента Office 365 следующим образом:</span><span class="sxs-lookup"><span data-stu-id="05c0f-135">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
    
   ```
   Get-MsolAccountSku
   ```

   <span data-ttu-id="05c0f-p110">Далее можно добавить лицензию с помощью командлета Set-MsolUserLicense. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="05c0f-p110">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. <span data-ttu-id="05c0f-138">Затем необходимо включить запись устройства с Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="05c0f-138">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="05c0f-139">Убедитесь, что в вашей среде соответствует требованиям, определенным в [системах комнаты Скайп требования к версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05c0f-139">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
    
   <span data-ttu-id="05c0f-140">Для запуска удаленного сеанса Windows PowerShell следующим образом (не забудьте установить Скайп для компонентов Business Online PowerShell):</span><span class="sxs-lookup"><span data-stu-id="05c0f-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="05c0f-141">Затем включите свою учетную запись комнаты систем Скайп версии 2 для Скайп для Business Server, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="05c0f-141">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="05c0f-142">Получите сведения о RegistrarPool из учетной записи пользователя, программа установки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="05c0f-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="05c0f-143">Новые учетные записи пользователей не могут быть созданы на тот же самый пул регистратора, как существующие учетные записи пользователей в клиентов.</span><span class="sxs-lookup"><span data-stu-id="05c0f-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="05c0f-144">Команды выше не позволит ошибок в учетной записи программы установки из-за этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="05c0f-144">The command above will prevent errors in account setup due to this situation.</span></span> 
  
<span data-ttu-id="05c0f-145">После выполнения предыдущего действия, чтобы включить учетную запись комнаты систем Скайп версии 2 в Скайп для бизнеса в Интернет, им необходимо назначить лицензию на устройство систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="05c0f-145">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="05c0f-146">Использование портала администрирования Office 365, назначьте либо Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3) лицензии на устройство.</span><span class="sxs-lookup"><span data-stu-id="05c0f-146">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>
  
### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="05c0f-147">Назначение лицензии учетной записи</span><span class="sxs-lookup"><span data-stu-id="05c0f-147">Assign a license to your account</span></span>

1. <span data-ttu-id="05c0f-148">Входа в систему как администратор клиента откройте административного портала Office 365 и щелкните на приложение администрирования.</span><span class="sxs-lookup"><span data-stu-id="05c0f-148">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="05c0f-149">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="05c0f-149">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="05c0f-150">Выберите учетную запись версии 2 Скайп комнаты систем и щелкните или нажмите значок перо, который означает, что изменение.</span><span class="sxs-lookup"><span data-stu-id="05c0f-150">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>
    
4. <span data-ttu-id="05c0f-151">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="05c0f-151">Click on the **Licenses** option.</span></span>
    
5. <span data-ttu-id="05c0f-152">В разделе **Назначение лицензий** необходимо выбрать Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3), в зависимости от вашей лицензирования и очевидна с точки зрения применения какого корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="05c0f-152">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="05c0f-153">Вам потребуется использовать планирование 3 лицензии, если вы хотите использовать облачных УАТС на систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="05c0f-153">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="05c0f-154">Облачная УАТС потребуется как минимум для подключения к голосовому каналу.</span><span class="sxs-lookup"><span data-stu-id="05c0f-154">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="05c0f-155">Затем настройте гибридную голосовую связь или звонки по ТСОП в соответствии со способом связи с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="05c0f-155">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span>
    
6. <span data-ttu-id="05c0f-156">Чтобы завершить задачу, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="05c0f-156">Click **Save** to complete the task.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="05c0f-157">Пример: Комнаты учетной записи программы установки в Exchange Online и Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="05c0f-157">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com
 -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true
 -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept 
-AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
$false -DeleteSubject $false -RemovePrivateProperty $false
 
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true 
-AdditionalResponse "This is a Rigel room!"
 
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
 
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress

```

> [!NOTE]
> <span data-ttu-id="05c0f-p115">Будут добавлены CloudPBX и PSTNCallingDomesticAndInternational. Кроме того, вам потребуется назначить номер телефона с помощью интерфейса администрирования.</span><span class="sxs-lookup"><span data-stu-id="05c0f-p115">This adds CloudPBX and PSTNCallingDomesticAndInternational. Addtionally, you will need to use the Admin interface to assign a phone number.</span></span> 
  
## <a name="validate"></a><span data-ttu-id="05c0f-160">Проверка</span><span class="sxs-lookup"><span data-stu-id="05c0f-160">Validate</span></span>

<span data-ttu-id="05c0f-161">Для проверки можно использовать любой Скайп для бизнеса клиента для входа в учетную запись, которую вы создали.</span><span class="sxs-lookup"><span data-stu-id="05c0f-161">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>


## <a name="see-also"></a><span data-ttu-id="05c0f-162">См. также</span><span class="sxs-lookup"><span data-stu-id="05c0f-162">See also</span></span>

[<span data-ttu-id="05c0f-163">Настройка учетных записей для систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="05c0f-163">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="05c0f-164">Планирование для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="05c0f-164">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="05c0f-165">Развертывание Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="05c0f-165">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="05c0f-166">Настройка консоли для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="05c0f-166">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="05c0f-167">Управление Системами комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="05c0f-167">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

