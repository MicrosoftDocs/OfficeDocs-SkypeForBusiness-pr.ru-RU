---
title: Развертывание Систем комнат Skype версии 2 в среде Office 365
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
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Office 365.
ms.openlocfilehash: a931ec6cb55e654612c451f15d4a4895f61ba990
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "30645389"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="9b7dc-103">Развертывание Систем комнат Skype версии 2 в среде Office 365 </span><span class="sxs-lookup"><span data-stu-id="9b7dc-103">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="9b7dc-104">В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Office 365, где оба online находятся в Скайп для бизнеса и Exchange.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365, where Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="9b7dc-105">Настройка учетных записей пользователей проще всего настроить их с помощью удаленной оболочки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="9b7dc-106">Корпорация Майкрософт предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или validate существующие учетные записи ресурсов, что у вас есть помогающих перевод их в совместимые учетных записей пользователей системы комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="9b7dc-107">При необходимости можно выполните следующие действия, чтобы настроить учетные записи, используемые устройства версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-107">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="9b7dc-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9b7dc-108">Requirements</span></span>

<span data-ttu-id="9b7dc-109">Перед развертыванием системы комнаты Скайп версии 2 с Office 365, убедитесь, что удовлетворены требования.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-109">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="9b7dc-110">Дополнительные сведения см. в разделе [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-110">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

<span data-ttu-id="9b7dc-111">Чтобы включить Скайп для бизнеса, необходимо иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="9b7dc-112">Скайп для бизнеса в Интернет (план 2 или план на основе предприятия) или более поздней версии в плане Office 365.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="9b7dc-113">Планирование необходимо разрешить возможности конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="9b7dc-114">Если вам требуется-связь с возможностями собрания, необходимо будет аудиоконференций и лицензии телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="9b7dc-115">Если вам требуется подключение по телефонной линии возможности из собрания, необходимо будет внутри страны или внутреннее и международное вызов план.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="9b7dc-116">Клиент пользователи должны иметь почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="9b7dc-117">Учетной записи системы комнаты Скайп версии 2 требуется по крайней мере Скайп для бизнеса Online (план 2) лицензии, но не требует лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-117">Your Skype Room Systems v2 account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="9b7dc-118">Дополнительные сведения см [Лицензирование систем комнаты Скайп версии 2](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) .</span><span class="sxs-lookup"><span data-stu-id="9b7dc-118">See [Skype Room Systems v2 Licensing](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="9b7dc-119">Дополнительные сведения о Скайп для бизнеса Online планы см [Скайп для описания службы Online бизнеса](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="9b7dc-120">Добавление учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="9b7dc-120">Add a device account</span></span>

https://docs.microsoft.com/en-us/powershell/module/msonline/?view=azureadps-1.0

https://docs.microsoft.com/en-us/powershell/module/Azuread/?view=azureadps-2.0 


1. <span data-ttu-id="9b7dc-121">Подключение к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="9b7dc-122">Сведения содержатся в разделе [подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="9b7dc-123">В Exchange Online PowerShell создание почтового ящика комнаты или изменения существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="9b7dc-124">По умолчанию почтовый ящик помещения не имеют связанных учетных записей, поэтому вам потребуется добавить учетную запись, при создании или изменении почтового ящика помещения, который будет выполнять проверку подлинности с системами комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="9b7dc-125">Чтобы создать новый почтовый ящик помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="9b7dc-126">В этом примере создается новый почтовый ящик места со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="9b7dc-127">Имя: Проект Rigel-01</span><span class="sxs-lookup"><span data-stu-id="9b7dc-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="9b7dc-128">Псевдоним: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="9b7dc-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="9b7dc-129">Учетная запись: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9b7dc-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="9b7dc-130">Пароль для учетной записи: P@$$W0rd5959</span><span class="sxs-lookup"><span data-stu-id="9b7dc-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="9b7dc-131">Для изменения существующего почтового ящика помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="9b7dc-132">В этом примере включается учетная запись для существующего почтового ящика помещения, который имеет значение псевдоним ProjectRigel02 и задает пароль для 9898P@$$W0rd.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="9b7dc-133">Обратите внимание на то, что учетной записи будет ProjectRigel02@contoso.onmicrosoft.com из-за существующее значение псевдоним.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="9b7dc-134">Подробный синтаксис и сведений о параметрах в разделе [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="9b7dc-135">В Exchange Online PowerShell настройте следующие параметры на почтовый ящик помещения, чтобы улучшить работу в собрание:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="9b7dc-136">AutomateProcessing: AutoAccept (организаторам собрания принимать решение резервирования помещений напрямую без участия: свободен = принять; занят = отклонить.)</span><span class="sxs-lookup"><span data-stu-id="9b7dc-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="9b7dc-137">AddOrganizerToSubject: $false (организатор собрания не добавляется к теме запроса на проведение собрания).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="9b7dc-138">DeleteComments: $false (сохранения любого текста в теле сообщения входящих приглашений на собрания).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="9b7dc-139">DeleteSubject: $false (Keep темы входящих приглашений на собрания).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="9b7dc-140">RemovePrivateProperty: $false (гарантирует пометку "частное", которые были отправлены организатором собрания в исходное приглашение на собрание запросить остается как указано).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="9b7dc-141">AddAdditionalResponse: $true (текста, указанного с помощью параметра AdditionalResponse добавляется для приглашений на собрания).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="9b7dc-142">AdditionalResponse: «это Скайп конференц-зала!»</span><span class="sxs-lookup"><span data-stu-id="9b7dc-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="9b7dc-143">(Дополнительный текст для добавления в запрос на собрание.)</span><span class="sxs-lookup"><span data-stu-id="9b7dc-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="9b7dc-144">В этом примере настраивается эти параметры в почтовый ящик помещения, с именем Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="9b7dc-145">Подробный синтаксис и сведений о параметрах в разделе [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="9b7dc-146">Подключитесь к PowerShell Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-146">Connect to Azure Active Directory PowerShell.</span></span> <span data-ttu-id="9b7dc-147">Сведения содержатся в разделе [подключение с помощью Azure Active Directory PowerShell для модуля "график"](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="9b7dc-147">For instructions, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span></span>

5. <span data-ttu-id="9b7dc-148">Если вы не хотите истечения срока действия пароля, используйте следующий синтаксис в Windows Azure Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-148">If you do not want the password to expire, use the following syntax in Azure Active Directory PowerShell:</span></span>

   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```

   <span data-ttu-id="9b7dc-149">В этом примере задается пароль для учетной записи ProjectRigel01@contoso.onmicrosoft.com никогда не истек.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-149">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ```

   <span data-ttu-id="9b7dc-150">Также можно задать номер телефона для учетной записи, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-150">You can also set a phone number for the account by running the following command:</span></span>

   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```

6. <span data-ttu-id="9b7dc-151">Учетная запись устройства должна быть действительной лицензии Office 365 или Exchange и Скайп для бизнеса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-151">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="9b7dc-152">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-152">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="9b7dc-153">Get-AzureADSubscribedSku можно использовать для получения списка доступных номеров SKU для клиента Office 365 следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-153">You can use Get-AzureADSubscribedSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```

   <span data-ttu-id="9b7dc-154">Теперь можно добавить лицензии, с помощью командлета Set-AzureADUserLicense.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-154">Next, you can add a license using the Set-AzureADUserLicense cmdlet.</span></span> <span data-ttu-id="9b7dc-155">В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-155">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

   <span data-ttu-id="9b7dc-156">Подробные сведения содержатся в разделе [Назначение лицензий для учетных записей пользователей с Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-156">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="9b7dc-157">Затем необходимо включить запись устройства с Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-157">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="9b7dc-158">Ваша среда должна соответствовать требованиям, определенным в разделе [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b7dc-158">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

   <span data-ttu-id="9b7dc-159">Для запуска удаленного [сеанса Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) (не забудьте [установить Скайп для компонентов Business Online PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-159">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="9b7dc-160">Затем включите свою учетную запись комнаты систем Скайп версии 2 для Скайп для Business Server, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-160">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="9b7dc-161">Получите сведения о RegistrarPool из учетной записи пользователя, программа установки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-161">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="9b7dc-162">Новые учетные записи пользователей не могут быть созданы на тот же самый пул регистратора, как существующие учетные записи пользователей в клиентов.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-162">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="9b7dc-163">Команды выше не позволит ошибок в учетной записи программы установки из-за этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-163">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="9b7dc-164">После выполнения предыдущего действия, чтобы включить учетную запись комнаты систем Скайп версии 2 в Скайп для бизнеса в Интернет, им необходимо назначить лицензию на устройство систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-164">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="9b7dc-165">Использование портала администрирования Office 365, назначьте либо Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3) лицензии на устройство.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-165">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="9b7dc-166">Назначение лицензии учетной записи</span><span class="sxs-lookup"><span data-stu-id="9b7dc-166">Assign a license to your account</span></span>

1. <span data-ttu-id="9b7dc-167">Входа в систему как администратор клиента откройте административного портала Office 365 и щелкните на приложение администрирования.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-167">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="9b7dc-168">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-168">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="9b7dc-169">Выберите учетную запись версии 2 Скайп комнаты систем и щелкните или нажмите значок перо, который означает, что изменение.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-169">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="9b7dc-170">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-170">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="9b7dc-171">В разделе **Назначение лицензий** необходимо выбрать Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3), в зависимости от вашей лицензирования и очевидна с точки зрения применения какого корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-171">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="9b7dc-172">Вам потребуется использовать планирование 3 лицензии, если вы хотите использовать облачных УАТС на систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-172">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="9b7dc-173">Облачная УАТС потребуется как минимум для подключения к голосовому каналу.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-173">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="9b7dc-174">Затем настройте гибридную голосовую связь или звонки по ТСОП в соответствии со способом связи с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-174">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="9b7dc-175">В разделе [лицензий v2 систем комнаты Скайп](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) более подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-175">See [Skype Room Systems v2 licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="9b7dc-176">Чтобы завершить задачу, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-176">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="9b7dc-177">Пример: Комнаты учетной записи программы установки в Exchange Online и Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="9b7dc-177">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="9b7dc-178">Exchange Online PowerShell команды:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-178">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="9b7dc-179">Команды Azure Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-179">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<span data-ttu-id="9b7dc-180">Скайп для команды PowerShell бизнеса:</span><span class="sxs-lookup"><span data-stu-id="9b7dc-180">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="9b7dc-181">Будут добавлены CloudPBX и PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-181">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="9b7dc-182">Кроме того необходимо использовать в интерфейс администратора для назначения номера телефона.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-182">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="9b7dc-183">Проверка</span><span class="sxs-lookup"><span data-stu-id="9b7dc-183">Validate</span></span>

<span data-ttu-id="9b7dc-184">Для проверки можно использовать любой Скайп для бизнеса клиента для входа в учетную запись, которую вы создали.</span><span class="sxs-lookup"><span data-stu-id="9b7dc-184">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b7dc-185">См. также</span><span class="sxs-lookup"><span data-stu-id="9b7dc-185">See also</span></span>

[<span data-ttu-id="9b7dc-186">Настройка учетных записей для систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="9b7dc-186">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="9b7dc-187">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="9b7dc-187">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="9b7dc-188">Развертывание Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="9b7dc-188">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)

[<span data-ttu-id="9b7dc-189">Настройка консоли для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="9b7dc-189">Configure a Skype Room Systems v2 console</span></span>](console.md)

[<span data-ttu-id="9b7dc-190">Управление Системами комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="9b7dc-190">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[<span data-ttu-id="9b7dc-191">Лицензирование v2 систем Скайп комнаты</span><span class="sxs-lookup"><span data-stu-id="9b7dc-191">Skype Room Systems v2 Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
