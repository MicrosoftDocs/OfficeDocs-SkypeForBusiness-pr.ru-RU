---
title: Развертывание Комнаты Microsoft Teams с Microsoft 365 или Office 365
ms.author: v-cichur
author: cichur
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В этой теме вы можете найти сведения о развертывании Комнаты Microsoft Teams с Microsoft 365 или Office 365, где Teams или Skype для бизнеса и Exchange находятся в сети.
ms.openlocfilehash: 64567cd9925a0a11d9e9b896c522a2c4bfe13f40
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739649"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="ed28d-103">Развертывание Комнаты Microsoft Teams с Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="ed28d-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="ed28d-104">В этой теме вы можете найти сведения о развертывании Комнаты Microsoft Teams с Microsoft 365 или Office 365, где обе Microsoft Teams или Skype для бизнеса и Exchange находятся в сети.</span><span class="sxs-lookup"><span data-stu-id="ed28d-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="ed28d-105">Самый простой способ настроить учетные записи пользователей — настроить их с помощью удаленного Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed28d-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="ed28d-106">Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей или проверить существующие учетные записи ресурсов, чтобы превратить их в совместимые Комнаты Microsoft Teams учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="ed28d-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="ed28d-107">При этом вы можете настроить учетные записи, которые будут Комнаты Microsoft Teams устройство.</span><span class="sxs-lookup"><span data-stu-id="ed28d-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="ed28d-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ed28d-108">Requirements</span></span>

<span data-ttu-id="ed28d-109">Прежде чем Комнаты Microsoft Teams с Microsoft 365 или Office 365, убедитесь, что выполнены требования.</span><span class="sxs-lookup"><span data-stu-id="ed28d-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="ed28d-110">Дополнительные сведения см. в Комнаты Microsoft Teams [требованиях.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="ed28d-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="ed28d-111">Чтобы включить Skype для бизнеса, необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="ed28d-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="ed28d-112">Skype для бизнеса В сети (план 2 или Enterprise на основе плана) или более Microsoft 365 или Office 365 плане.</span><span class="sxs-lookup"><span data-stu-id="ed28d-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="ed28d-113">В плане должны быть возможности для работы сконференцию с телефонным телефоном.</span><span class="sxs-lookup"><span data-stu-id="ed28d-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="ed28d-114">Если вам нужны возможности телефонного дозвона на собрании, вам потребуется лицензия на аудиоконференцию и телефонная система аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="ed28d-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="ed28d-115">Если на собрании вам нужны возможности для телефонного набора, вам потребуется лицензия на аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="ed28d-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="ed28d-116">У пользователей клиента должны быть Exchange почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="ed28d-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="ed28d-117">Для Комнаты Microsoft Teams учетной записи требуется как минимум Skype для бизнеса Online (план 2), но лицензия на Exchange Online не требуется.</span><span class="sxs-lookup"><span data-stu-id="ed28d-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="ed28d-118">Подробные [Комнаты Microsoft Teams лицензии](rooms-licensing.md) см. в этой Комнаты Microsoft Teams лицензиях.</span><span class="sxs-lookup"><span data-stu-id="ed28d-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="ed28d-119">Подробные сведения о планах Skype для бизнеса Online см. в Skype для бизнеса online Service Description (Описание [веб-служб).](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="ed28d-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="ed28d-120">Добавление учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="ed28d-120">Add a device account</span></span>

1. <span data-ttu-id="ed28d-121">Подключение Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed28d-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="ed28d-122">Инструкции см. в Подключение [Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="ed28d-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ed28d-123">В Exchange Online PowerShell создайте новый почтовый ящик помещения или измените существующий почтовый ящик комнаты.</span><span class="sxs-lookup"><span data-stu-id="ed28d-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="ed28d-124">По умолчанию у почтовых ящиков помещений нет связанных учетных записей, поэтому вам потребуется добавить учетную запись при создании или изменении почтового ящика комнаты, который позволяет ей проверку подлинности с помощью Skype Room Systems v2.</span><span class="sxs-lookup"><span data-stu-id="ed28d-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="ed28d-125">Чтобы создать почтовый ящик помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed28d-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="ed28d-126">В этом примере создается почтовый ящик помещения со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="ed28d-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="ed28d-127">Имя: Карель-01</span><span class="sxs-lookup"><span data-stu-id="ed28d-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="ed28d-128">Псевдоним: Иван</span><span class="sxs-lookup"><span data-stu-id="ed28d-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="ed28d-129">Учетная запись: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="ed28d-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="ed28d-130">Пароль учетной записи: P@$$W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="ed28d-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="ed28d-131">Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed28d-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="ed28d-132">В этом примере включается учетная запись существующего почтового ящика комнаты со значением псевдонима «Иван2» и устанавливается значение 9898P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="ed28d-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="ed28d-133">Обратите внимание, что учетная запись будет Rigel2@contoso.onmicrosoft.com из-за существующего значения псевдонима.</span><span class="sxs-lookup"><span data-stu-id="ed28d-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="ed28d-134">Подробные сведения о синтаксисе и параметрах см. в настройках [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="ed28d-134">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="ed28d-135">В Exchange Online PowerShell настройте следующие параметры почтового ящика комнаты, чтобы улучшить собрание:</span><span class="sxs-lookup"><span data-stu-id="ed28d-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="ed28d-136">AutomateProcessing: autoAccept (организаторы собраний получают решение о резервировании помещений напрямую без участия человека: free = accept; busy = decline.)</span><span class="sxs-lookup"><span data-stu-id="ed28d-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="ed28d-137">AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему запроса на собрание.)</span><span class="sxs-lookup"><span data-stu-id="ed28d-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="ed28d-138">DeleteComments: $false (Сохранить текст в тексте сообщения входящих запросов на собрание.)</span><span class="sxs-lookup"><span data-stu-id="ed28d-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="ed28d-139">DeleteSubject: $false (Тема входящих запросов на собрания.)</span><span class="sxs-lookup"><span data-stu-id="ed28d-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="ed28d-140">RemovePrivateProperty: $false (Гарантирует, что личный флажок, отправленный организатором собрания в исходном запросе на собрание, останется указанным.)</span><span class="sxs-lookup"><span data-stu-id="ed28d-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="ed28d-141">AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)</span><span class="sxs-lookup"><span data-stu-id="ed28d-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="ed28d-142">AdditionalResponse: "Это Skype собрание!"</span><span class="sxs-lookup"><span data-stu-id="ed28d-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="ed28d-143">(Дополнительный текст, который нужно добавить в запрос на собрание.)</span><span class="sxs-lookup"><span data-stu-id="ed28d-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="ed28d-144">В этом примере эти параметры настраиваются для почтового ящика комнаты с именем Конюхель-01.</span><span class="sxs-lookup"><span data-stu-id="ed28d-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="ed28d-145">Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="ed28d-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="ed28d-146">Подключение с ms Online PowerShell, чтобы создать параметры Active Directory с помощью `Connect-MsolService -Credential $cred` mdlet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed28d-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="ed28d-147">Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="ed28d-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="ed28d-148">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ed28d-148">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="ed28d-149">Если вы не хотите, чтобы срок действия пароля истекал, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed28d-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="ed28d-150">В этом примере пароль учетной записи Rigel1@contoso.onmicrosoft.com срок действия никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="ed28d-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="ed28d-151">Кроме того, вы можете настроить номер телефона для учетной записи, выстроив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ed28d-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > <span data-ttu-id="ed28d-152">Если для пароля не за установлено действие "Никогда не истекает", учетная запись больше не будет вводиться на устройстве, когда срок действия учетной записи истечет.</span><span class="sxs-lookup"><span data-stu-id="ed28d-152">If the password is not set to Never Expire, the account will no longer sign in on the device when the account reaches the expiry period.</span></span> <span data-ttu-id="ed28d-153">После этого пароль потребуется изменить для учетной записи, а также обновить локально на устройстве MTR.</span><span class="sxs-lookup"><span data-stu-id="ed28d-153">The password will then need to be changed for the account and also updated locally on the MTR device.</span></span>

6. <span data-ttu-id="ed28d-154">У учетной записи устройства должна быть действительная Microsoft 365 или Office 365 лицензия либо Exchange и Microsoft Teams или Skype для бизнеса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="ed28d-154">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="ed28d-155">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ed28d-155">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="ed28d-156">Вы можете использовать `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="ed28d-156">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="ed28d-157">чтобы получить список доступных skUs для вашей Microsoft 365 или Office 365 организации:</span><span class="sxs-lookup"><span data-stu-id="ed28d-157">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="ed28d-158">Затем вы можете добавить лицензию с помощью `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="ed28d-158">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="ed28d-159">Командлет.</span><span class="sxs-lookup"><span data-stu-id="ed28d-159">cmdlet.</span></span> <span data-ttu-id="ed28d-160">В этом примере лицензия Конференц-зал к учетной записи:</span><span class="sxs-lookup"><span data-stu-id="ed28d-160">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="ed28d-161">Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с [помощью Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="ed28d-161">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="ed28d-162">Вы также можете телефонная система возможности для этой учетной записи, но сначала необходимо настроить ее.</span><span class="sxs-lookup"><span data-stu-id="ed28d-162">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="ed28d-163">Дополнительные [сведения см. телефонная система в](../what-is-phone-system-in-office-365.md) этой области.</span><span class="sxs-lookup"><span data-stu-id="ed28d-163">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="ed28d-164">В этом примере добавляется план внутренних и международных звонков по ДНР:</span><span class="sxs-lookup"><span data-stu-id="ed28d-164">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

    > [!NOTE]
    > <span data-ttu-id="ed28d-165">Если вы настраиваете Комнаты Teams только для того, чтобы присоединяться к собраниям Microsoft Teams, не переходите к следующему шагу:</span><span class="sxs-lookup"><span data-stu-id="ed28d-165">If you are configuring Teams Rooms to only natively join Microsoft Teams meetings, you should not proceed with the following step.</span></span> <span data-ttu-id="ed28d-166">Эти возможности необходимы только в том случае, если вы также включит поддержку Skype для бизнеса локальной службе.</span><span class="sxs-lookup"><span data-stu-id="ed28d-166">The following is only required if you will also be enabling support for Skype for Business on-premises.</span></span>

7. <span data-ttu-id="ed28d-167">Чтобы включить учетную запись устройства Skype для бизнеса локальной среде, убедитесь, что ваша среда соответствует требованиям, определенным в Комнаты Microsoft Teams [требованиях](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed28d-167">To enable the device account with Skype for Business on-premises, be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="ed28d-168">Начните сеанс [удаленного](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) Windows PowerShell (не забудьте установить компоненты [Skype для бизнеса Online PowerShell):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="ed28d-168">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   > [!NOTE]
   > <span data-ttu-id="ed28d-169">Skype для бизнеса В настоящее время Online Connector является частью последней версии Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed28d-169">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   >
   > <span data-ttu-id="ed28d-170">Если вы используете последний общедоступный [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="ed28d-170">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   <span data-ttu-id="ed28d-171">Получите данные RegistrarPool из новой учетной записи пользователя, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="ed28d-171">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="ed28d-172">Затем в Комнаты Microsoft Teams учетную запись Skype для бизнеса Server с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ed28d-172">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="ed28d-173">Новые учетные записи пользователей могут не создаваться в том же реестре, что и существующие учетные записи пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="ed28d-173">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="ed28d-174">Эта команда предотвращает ошибки при настройке учетной записи в связи с этой ситуацией.</span><span class="sxs-lookup"><span data-stu-id="ed28d-174">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="ed28d-175">Проверить</span><span class="sxs-lookup"><span data-stu-id="ed28d-175">Validate</span></span>

<span data-ttu-id="ed28d-176">Для проверки вы можете использовать любой клиент Skype для бизнеса войти в созданную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="ed28d-176">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed28d-177">См. также</span><span class="sxs-lookup"><span data-stu-id="ed28d-177">See also</span></span>

[<span data-ttu-id="ed28d-178">Настройка учетных записей для Комнаты Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed28d-178">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="ed28d-179">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed28d-179">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="ed28d-180">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed28d-180">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="ed28d-181">Настройка консоли комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed28d-181">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="ed28d-182">Управление комнатами Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed28d-182">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="ed28d-183">Комнаты Microsoft Teams Лицензирования</span><span class="sxs-lookup"><span data-stu-id="ed28d-183">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
