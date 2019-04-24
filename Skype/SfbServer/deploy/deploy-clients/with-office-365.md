---
title: Развертывание групп Майкрософт комнат с Office 365
ms.author: jambirk
author: jambirk
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В данном разделе приведены сведения о развертывании Microsoft комнат групп с помощью Office 365.
ms.openlocfilehash: 5ef6c4ea8b76a34b19da6a74d82badf8000e007c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214844"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="7d429-103">Развертывание групп Майкрософт комнат с Office 365</span><span class="sxs-lookup"><span data-stu-id="7d429-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="7d429-104">В данном разделе приведены сведения о том, как развернуть комнат группами Майкрософт в Office 365, где оба online находятся в Скайп для бизнеса и Exchange.</span><span class="sxs-lookup"><span data-stu-id="7d429-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="7d429-105">Настройка учетных записей пользователей проще всего настроить их с помощью удаленной оболочки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d429-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="7d429-106">Корпорация Майкрософт предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или validate существующие учетные записи ресурсов, что у вас есть помогающих перевод их в совместимые учетных записей пользователей комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7d429-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="7d429-107">При необходимости можно выполните следующие действия, чтобы настроить учетные записи, используемые устройства комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7d429-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d429-108">Требования</span><span class="sxs-lookup"><span data-stu-id="7d429-108">Requirements</span></span>

<span data-ttu-id="7d429-109">Перед развертыванием комнат команды Microsoft Office 365, убедитесь, что удовлетворены требования.</span><span class="sxs-lookup"><span data-stu-id="7d429-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="7d429-110">Для получения дополнительных сведений в разделе [requirements комнат группами Майкрософт](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d429-110">For more information, see [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

<span data-ttu-id="7d429-111">Чтобы включить Скайп для бизнеса, необходимо иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="7d429-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="7d429-112">Скайп для бизнеса в Интернет (план 2 или план на основе предприятия) или более поздней версии в плане Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d429-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="7d429-113">Планирование необходимо разрешить возможности конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="7d429-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="7d429-114">Если вам требуется-связь с возможностями собрания, необходимо будет аудиоконференций и лицензии телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="7d429-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="7d429-115">Если вам требуется подключение по телефонной линии возможности из собрания, необходимо будет внутри страны или внутреннее и международное вызов план.</span><span class="sxs-lookup"><span data-stu-id="7d429-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="7d429-116">Клиент пользователи должны иметь почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="7d429-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="7d429-117">Учетной записи Microsoft группами комнат требуется по крайней мере Скайп для бизнеса Online (план 2) лицензии, но не требует лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7d429-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="7d429-118">Просмотрите [Лицензирования комнат группами Майкрософт](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="7d429-118">See [Microsoft Teams Rooms Licensing](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="7d429-119">Дополнительные сведения о Скайп для бизнеса Online планы см [Скайп для описания службы Online бизнеса](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="7d429-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="7d429-120">Добавление учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="7d429-120">Add a device account</span></span>

1. <span data-ttu-id="7d429-121">Подключение к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d429-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="7d429-122">Сведения содержатся в разделе [подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="7d429-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="7d429-123">В Exchange Online PowerShell создание почтового ящика комнаты или изменения существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="7d429-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="7d429-124">По умолчанию почтовый ящик помещения не имеют связанных учетных записей, поэтому вам потребуется добавить учетную запись, при создании или изменении почтового ящика помещения, который будет выполнять проверку подлинности с системами комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="7d429-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="7d429-125">Чтобы создать новый почтовый ящик помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="7d429-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="7d429-126">В этом примере создается новый почтовый ящик места со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="7d429-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="7d429-127">Имя: Проект Rigel-01</span><span class="sxs-lookup"><span data-stu-id="7d429-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="7d429-128">Псевдоним: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="7d429-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="7d429-129">Учетная запись: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7d429-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="7d429-130">Пароль для учетной записи: P@$$W0rd5959</span><span class="sxs-lookup"><span data-stu-id="7d429-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="7d429-131">Для изменения существующего почтового ящика помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="7d429-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="7d429-132">В этом примере включается учетная запись для существующего почтового ящика помещения, который имеет значение псевдоним ProjectRigel02 и задает пароль для 9898P@$$W0rd.</span><span class="sxs-lookup"><span data-stu-id="7d429-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="7d429-133">Обратите внимание на то, что учетной записи будет ProjectRigel02@contoso.onmicrosoft.com из-за существующее значение псевдоним.</span><span class="sxs-lookup"><span data-stu-id="7d429-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="7d429-134">Подробный синтаксис и сведений о параметрах в разделе [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="7d429-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="7d429-135">В Exchange Online PowerShell настройте следующие параметры на почтовый ящик помещения, чтобы улучшить работу в собрание:</span><span class="sxs-lookup"><span data-stu-id="7d429-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="7d429-136">AutomateProcessing: AutoAccept (организаторам собрания принимать решение резервирования помещений напрямую без участия: свободен = принять; занят = отклонить.)</span><span class="sxs-lookup"><span data-stu-id="7d429-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="7d429-137">AddOrganizerToSubject: $false (организатор собрания не добавляется к теме запроса на проведение собрания).</span><span class="sxs-lookup"><span data-stu-id="7d429-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="7d429-138">DeleteComments: $false (сохранения любого текста в теле сообщения входящих приглашений на собрания).</span><span class="sxs-lookup"><span data-stu-id="7d429-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="7d429-139">DeleteSubject: $false (Keep темы входящих приглашений на собрания).</span><span class="sxs-lookup"><span data-stu-id="7d429-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="7d429-140">RemovePrivateProperty: $false (гарантирует пометку "частное", которые были отправлены организатором собрания в исходное приглашение на собрание запросить остается как указано).</span><span class="sxs-lookup"><span data-stu-id="7d429-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="7d429-141">AddAdditionalResponse: $true (текста, указанного с помощью параметра AdditionalResponse добавляется для приглашений на собрания).</span><span class="sxs-lookup"><span data-stu-id="7d429-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="7d429-142">AdditionalResponse: «это Скайп конференц-зала!»</span><span class="sxs-lookup"><span data-stu-id="7d429-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="7d429-143">(Дополнительный текст для добавления в запрос на собрание.)</span><span class="sxs-lookup"><span data-stu-id="7d429-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="7d429-144">В этом примере настраивается эти параметры в почтовый ящик помещения, с именем Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="7d429-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="7d429-145">Подробный синтаксис и сведений о параметрах в разделе [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="7d429-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="7d429-146">Подключение к MS Online PowerShell, чтобы сделать параметрами Active Directory, выполнив `Connect-MsolService -Credential $cred` командлета powershell.</span><span class="sxs-lookup"><span data-stu-id="7d429-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="7d429-147">Для получения дополнительных сведений об Active Directory просмотрите [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="7d429-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> <!-- or [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) for the new module -->  
    1. <span data-ttu-id="7d429-148">Если вы не хотите истечения срока действия пароля, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="7d429-148">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="7d429-149">В этом примере задается пароль для учетной записи ProjectRigel01@contoso.onmicrosoft.com никогда не истек.</span><span class="sxs-lookup"><span data-stu-id="7d429-149">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="7d429-150">Также можно задать номер телефона для учетной записи, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7d429-150">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="7d429-151">Учетная запись устройства должна быть действительной лицензии Office 365 или Exchange и Скайп для бизнеса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="7d429-151">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="7d429-152">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7d429-152">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="7d429-153">Вы можете использовать`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="7d429-153">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="7d429-154">Для получения списка доступных номеров SKU для клиента Office 365 следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7d429-154">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="7d429-155">Теперь можно добавить лицензии с помощью`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="7d429-155">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="7d429-156">командлет.</span><span class="sxs-lookup"><span data-stu-id="7d429-156">cmdlet.</span></span> <span data-ttu-id="7d429-157">В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="7d429-157">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="7d429-158">Подробные сведения содержатся в разделе [Назначение лицензий для учетных записей пользователей с Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7d429-158">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="7d429-159">Затем необходимо включить запись устройства с Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7d429-159">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="7d429-160">Убедитесь, что в вашей среде соответствует требованиям, определенным в [требования к комнат группами Майкрософт](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d429-160">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

   <span data-ttu-id="7d429-161">Для запуска удаленного [сеанса Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) (не забудьте [установить Скайп для компонентов Business Online PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7d429-161">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="7d429-162">Затем включите свою учетную запись Microsoft группами комнат для Скайп для Business Server, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="7d429-162">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="7d429-163">Получите сведения о RegistrarPool из учетной записи пользователя, программа установки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7d429-163">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="7d429-164">Новые учетные записи пользователей не могут быть созданы на тот же самый пул регистратора, как существующие учетные записи пользователей в клиентов.</span><span class="sxs-lookup"><span data-stu-id="7d429-164">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="7d429-165">Команды выше не позволит ошибок в учетной записи программы установки из-за этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="7d429-165">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="7d429-166">После выполнения предыдущего действия, чтобы включить учетную запись комнаты группами Майкрософт в Скайп для бизнеса в Интернет, им необходимо назначить лицензию на устройство комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7d429-166">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="7d429-167">Использование портала администрирования Office 365, назначьте либо Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3) лицензии на устройство.</span><span class="sxs-lookup"><span data-stu-id="7d429-167">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="7d429-168">Назначение лицензии учетной записи</span><span class="sxs-lookup"><span data-stu-id="7d429-168">Assign a license to your account</span></span>

1. <span data-ttu-id="7d429-169">Входа в систему как администратор клиента откройте административного портала Office 365 и щелкните на приложение администрирования.</span><span class="sxs-lookup"><span data-stu-id="7d429-169">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="7d429-170">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="7d429-170">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="7d429-171">Выберите учетную запись Microsoft группами комнат и щелкните или нажмите значок перо, который означает, что изменение.</span><span class="sxs-lookup"><span data-stu-id="7d429-171">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="7d429-172">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="7d429-172">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="7d429-173">В разделе **Назначение лицензий** необходимо выбрать Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3), в зависимости от вашей лицензирования и очевидна с точки зрения применения какого корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7d429-173">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="7d429-174">Вам потребуется использовать планирование 3 лицензии, если вы хотите использовать УАТС облака на комнат группы Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7d429-174">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="7d429-175">Облачная УАТС потребуется как минимум для подключения к голосовому каналу.</span><span class="sxs-lookup"><span data-stu-id="7d429-175">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="7d429-176">Затем настройте гибридную голосовую связь или звонки по ТСОП в соответствии со способом связи с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="7d429-176">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="7d429-177">Просмотрите [лицензий комнат группами Майкрософт](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="7d429-177">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="7d429-178">Чтобы завершить задачу, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7d429-178">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="7d429-179">Пример: Комнаты учетной записи программы установки в Exchange Online и Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="7d429-179">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="7d429-180">Exchange Online PowerShell команды:</span><span class="sxs-lookup"><span data-stu-id="7d429-180">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="7d429-181">Команды Azure Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7d429-181">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="7d429-182">Скайп для команды PowerShell бизнеса:</span><span class="sxs-lookup"><span data-stu-id="7d429-182">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="7d429-183">Будут добавлены CloudPBX и PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="7d429-183">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="7d429-184">Кроме того необходимо использовать в интерфейс администратора для назначения номера телефона.</span><span class="sxs-lookup"><span data-stu-id="7d429-184">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="7d429-185">Проверка</span><span class="sxs-lookup"><span data-stu-id="7d429-185">Validate</span></span>

<span data-ttu-id="7d429-186">Для проверки можно использовать любой Скайп для бизнеса клиента для входа в учетную запись, которую вы создали.</span><span class="sxs-lookup"><span data-stu-id="7d429-186">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d429-187">См. также</span><span class="sxs-lookup"><span data-stu-id="7d429-187">See also</span></span>

[<span data-ttu-id="7d429-188">Настройка учетных записей для комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7d429-188">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="7d429-189">Планирование для групп Майкрософт комнат</span><span class="sxs-lookup"><span data-stu-id="7d429-189">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="7d429-190">Развертывание групп Майкрософт комнат</span><span class="sxs-lookup"><span data-stu-id="7d429-190">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="7d429-191">Настройка консоли комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7d429-191">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="7d429-192">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="7d429-192">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[<span data-ttu-id="7d429-193">Лицензирование комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7d429-193">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
