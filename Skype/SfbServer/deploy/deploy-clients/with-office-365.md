---
title: Развертывание Систем комнат Skype версии 2 в среде Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Office 365.
ms.openlocfilehash: 87ae4f7e846cce1cfeca2c7f64fdee93476ae350
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="43597-103">Развертывание Систем комнат Skype версии 2 в среде Office 365 </span><span class="sxs-lookup"><span data-stu-id="43597-103">Deploy Skype Room Systems v2 with Office 365</span></span>
 
<span data-ttu-id="43597-104">В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Office 365.</span><span class="sxs-lookup"><span data-stu-id="43597-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365.</span></span>
  
<span data-ttu-id="43597-105">В этом разделе описывается добавление учетной записи устройства для систем комнаты Скайп v2 при наличии online развертывания Office 365.</span><span class="sxs-lookup"><span data-stu-id="43597-105">This topic describes how to add a device account for Skype Room Systems v2 when you have an Office 365 online deployment.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="43597-106">Развертывание Систем комнат Skype версии 2 в среде Office 365 </span><span class="sxs-lookup"><span data-stu-id="43597-106">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="43597-107">Перед развертыванием системы комнаты Скайп версии 2 с Office 365, убедитесь, что удовлетворены требования.</span><span class="sxs-lookup"><span data-stu-id="43597-107">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="43597-108">Для получения дополнительных сведений см [систем комнаты Скайп версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43597-108">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="43597-109">Чтобы включить Скайп для бизнеса, необходимо иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="43597-109">To enable Skype for Business, you must have the following:</span></span>
  
- <span data-ttu-id="43597-110">Скайп для бизнеса Online (план 2) или более поздней версии в плане Office 365.</span><span class="sxs-lookup"><span data-stu-id="43597-110">Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="43597-111">План должен поддерживать функции конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="43597-111">The plan needs to support conferencing capability.</span></span>
    
- <span data-ttu-id="43597-112">Если вам требуется корпоративной голосовой связи (телефонии PSTN) с помощью службы телефонии для систем комнаты Скайп версии 2 необходимо Скайп для бизнеса Online (план 3).</span><span class="sxs-lookup"><span data-stu-id="43597-112">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
- <span data-ttu-id="43597-113">Клиент пользователи должны иметь почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="43597-113">Your tenant users must have Exchange mailboxes.</span></span>
    
- <span data-ttu-id="43597-114">Вашей системы комнаты Скайп версии 2 для учетной записи требуются Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3) лицензии, но не требует лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="43597-114">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
### <a name="add-a-device-account"></a><span data-ttu-id="43597-115">Добавление учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="43597-115">Add a device account</span></span>

1. <span data-ttu-id="43597-116">Для запуска удаленного сеанса Windows PowerShell на ПК и подключитесь к Exchange.</span><span class="sxs-lookup"><span data-stu-id="43597-116">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="43597-117">Убедитесь, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="43597-117">Be sure you have the right permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="43597-118">Ниже приведен ряд примеров командлетов, которые можно использовать и изменять в своей среде.</span><span class="sxs-lookup"><span data-stu-id="43597-118">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="43597-119">После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="43597-119">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="43597-120">Это позволит учетной записи для проверки подлинности системы комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="43597-120">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
  <span data-ttu-id="43597-121">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="43597-121">If you are changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

  <span data-ttu-id="43597-122">Если вы создаете новый почтовый ящик ресурса:</span><span class="sxs-lookup"><span data-stu-id="43597-122">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="43597-p105">Чтобы оптимизировать интерфейс собрания, можно настроить различные свойства Exchange для учетной записи устройства. Описание необходимых настроек приводится в разделе "Свойства Exchange".</span><span class="sxs-lookup"><span data-stu-id="43597-p105">Various Exchange properties must be set on the device account to improve the meeting experience. You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. <span data-ttu-id="43597-125">Для применения некоторых настроек учетной записи потребуется подключиться к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="43597-125">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="43597-126">Чтобы подключиться к Azure AD, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="43597-126">To connect to Azure AD, run the following cmdlet:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. <span data-ttu-id="43597-127">	Чтобы использовать пароль с неограниченным сроком действия, выполните командлет Set-MsolUser с параметром PasswordNeverExpires.  </span><span class="sxs-lookup"><span data-stu-id="43597-127">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   <span data-ttu-id="43597-128">Вы также можете задать номер телефона для комнаты следующим образом.</span><span class="sxs-lookup"><span data-stu-id="43597-128">You can also set a phone number for the room as follows:</span></span>
    
   ```
   Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. <span data-ttu-id="43597-129">Учетная запись устройства должна быть действительной лицензии Office 365 или Exchange и Скайп для бизнеса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="43597-129">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="43597-130">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="43597-130">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="43597-131">Get-MsolAccountSku можно использовать для получения списка доступных номеров SKU для клиента Office 365 следующим образом:</span><span class="sxs-lookup"><span data-stu-id="43597-131">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
    
   ```
   Get-MsolAccountSku
   ```

   <span data-ttu-id="43597-p108">Далее можно добавить лицензию с помощью командлета Set-MsolUserLicense. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="43597-p108">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. <span data-ttu-id="43597-134">Затем необходимо включить запись устройства с Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="43597-134">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="43597-135">Убедитесь, что в вашей среде соответствует требованиям, определенным в [системах комнаты Скайп требования к версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43597-135">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
    
   <span data-ttu-id="43597-136">Для запуска удаленного сеанса Windows PowerShell следующим образом (не забудьте установить Скайп для компонентов Business Online PowerShell):</span><span class="sxs-lookup"><span data-stu-id="43597-136">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="43597-137">Затем включите свою учетную запись комнаты систем Скайп версии 2 для Скайп для Business Server, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="43597-137">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="43597-138">Получите сведения о RegistrarPool из учетной записи пользователя, программа установки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="43597-138">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="43597-139">Новые учетные записи пользователей не могут быть созданы на тот же самый пул регистратора, как существующие учетные записи пользователей в клиентов.</span><span class="sxs-lookup"><span data-stu-id="43597-139">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="43597-140">Команды выше не позволит ошибок в учетной записи программы установки из-за этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="43597-140">The command above will prevent errors in account setup due to this situation.</span></span> 
  
<span data-ttu-id="43597-141">После выполнения предыдущего действия, чтобы включить учетную запись комнаты систем Скайп версии 2 в Скайп для бизнеса в Интернет, им необходимо назначить лицензию на устройство систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="43597-141">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="43597-142">Использование портала администрирования Office 365, назначьте либо Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3) лицензии на устройство.</span><span class="sxs-lookup"><span data-stu-id="43597-142">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>
  
### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="43597-143">Назначение лицензии учетной записи</span><span class="sxs-lookup"><span data-stu-id="43597-143">Assign a license to your account</span></span>

1. <span data-ttu-id="43597-144">Входа в систему как администратор клиента откройте административного портала Office 365 и щелкните на приложение администрирования.</span><span class="sxs-lookup"><span data-stu-id="43597-144">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="43597-145">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="43597-145">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="43597-146">Выберите учетную запись версии 2 Скайп комнаты систем и щелкните или нажмите значок перо, который означает, что изменение.</span><span class="sxs-lookup"><span data-stu-id="43597-146">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>
    
4. <span data-ttu-id="43597-147">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="43597-147">Click on the **Licenses** option.</span></span>
    
5. <span data-ttu-id="43597-148">В разделе **Назначение лицензий** необходимо выбрать Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3), в зависимости от вашей лицензирования и очевидна с точки зрения применения какого корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="43597-148">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="43597-149">Вам потребуется использовать планирование 3 лицензии, если вы хотите использовать облачных УАТС на систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="43597-149">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="43597-150">Облачная УАТС потребуется как минимум для подключения к голосовому каналу.</span><span class="sxs-lookup"><span data-stu-id="43597-150">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="43597-151">Затем настройте гибридную голосовую связь или звонки по ТСОП в соответствии со способом связи с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="43597-151">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span>
    
6. <span data-ttu-id="43597-152">Чтобы завершить задачу, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="43597-152">Click **Save** to complete the task.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="43597-153">Пример: Комнаты учетной записи программы установки в Exchange Online и Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="43597-153">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

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
> <span data-ttu-id="43597-p113">Будут добавлены CloudPBX и PSTNCallingDomesticAndInternational. Кроме того, вам потребуется назначить номер телефона с помощью интерфейса администрирования.</span><span class="sxs-lookup"><span data-stu-id="43597-p113">This adds CloudPBX and PSTNCallingDomesticAndInternational. Addtionally, you will need to use the Admin interface to assign a phone number.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="43597-156">См. также</span><span class="sxs-lookup"><span data-stu-id="43597-156">See also</span></span>

#### 

[<span data-ttu-id="43597-157">Планирование для помещения Скайп систем версии 2</span><span class="sxs-lookup"><span data-stu-id="43597-157">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="43597-158">Развертывание Скайп комнаты систем версии 2</span><span class="sxs-lookup"><span data-stu-id="43597-158">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="43597-159">Настройка консоли систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="43597-159">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="43597-160">Управление Скайп комнаты систем версии 2</span><span class="sxs-lookup"><span data-stu-id="43597-160">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

