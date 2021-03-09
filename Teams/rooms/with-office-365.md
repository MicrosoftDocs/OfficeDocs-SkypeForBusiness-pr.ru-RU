---
title: Развертывание комнат Microsoft Teams с Microsoft 365 или Office 365
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
description: В этой теме вы можете найти сведения о развертывании комнат Microsoft Teams с Microsoft 365 или Office 365, где обе службы Teams или Skype для бизнеса и Exchange находятся в сети.
ms.openlocfilehash: 7a25fb17e4b9fce4a51c6e2be5828ecafff59894
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569125"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="3ef1b-103">Развертывание комнат Microsoft Teams с Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="3ef1b-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="3ef1b-104">В этой теме вы можете найти сведения о развертывании комнат Microsoft Teams с Microsoft 365 или Office 365, где microsoft Teams, Skype для бизнеса и Exchange находятся в сети.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="3ef1b-105">Проще всего настроить учетные записи пользователей с помощью удаленного Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="3ef1b-106">Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который помогает создавать новые учетные записи пользователей или проверять существующие учетные записи ресурсов, чтобы превратить их в совместимые учетные записи пользователей комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="3ef1b-107">При этом вы можете настроить учетные записи, которые будут использовать ваше устройство Microsoft Teams Rooms, следуя этим шагам.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="3ef1b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="3ef1b-108">Requirements</span></span>

<span data-ttu-id="3ef1b-109">Прежде чем развернуть комнаты Microsoft Teams с Microsoft 365 или Office 365, убедитесь, что выполнили требования.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="3ef1b-110">Дополнительные сведения см. в требованиях к комнатам [Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="3ef1b-111">Чтобы включить Skype для бизнеса, у вас должны быть следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="3ef1b-112">Skype для бизнеса Online (план 2 или корпоративный план) или более высокого уровня в вашем плане Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="3ef1b-113">В плане должны быть разрешается использовать функции для работы сконференцией с dial-in.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="3ef1b-114">Если на собрании вам нужны функции телефонного звонка, вам потребуется лицензия на аудиоконференцию и телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="3ef1b-115">Если на собрании вам нужны функции телефонного дозвона, вам потребуется лицензия на аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="3ef1b-116">У пользователей клиента должны быть почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="3ef1b-117">Для учетной записи комнат Microsoft Teams требуется как минимум лицензия на Skype для бизнеса Online (план 2), но лицензия на Exchange Online не требуется.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="3ef1b-118">Подробные [сведения см. в лицензиях на комнаты Microsoft Teams.](rooms-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="3ef1b-119">Подробные сведения о планах Skype для бизнеса Online см. в описании [службы Skype для бизнеса Online.](https://technet.microsoft.com/library/jj822172.aspx)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="3ef1b-120">Добавление учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="3ef1b-120">Add a device account</span></span>

1. <span data-ttu-id="3ef1b-121">Подключите Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="3ef1b-122">Инструкции см. в [инструкциях по подключению к Exchange Online PowerShell.](https://go.microsoft.com/fwlink/p/?linkid=396554)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="3ef1b-123">В Exchange Online PowerShell создайте почтовый ящик новой комнаты или измените существующий.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="3ef1b-124">По умолчанию у почтовых ящиков помещений нет связанных учетных записей, поэтому вам потребуется добавить учетную запись при создании или изменении почтового ящика комнаты, которая позволяет ей аутентификацию с помощью систем комнат Skype 2.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="3ef1b-125">Чтобы создать почтовый ящик помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="3ef1b-126">В этом примере создается почтовый ящик помещения со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="3ef1b-127">Имя: Карель-01</span><span class="sxs-lookup"><span data-stu-id="3ef1b-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="3ef1b-128">Псевдоним: Дарел1</span><span class="sxs-lookup"><span data-stu-id="3ef1b-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="3ef1b-129">Учетная запись: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3ef1b-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="3ef1b-130">Пароль учетной записи: P@$$W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="3ef1b-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="3ef1b-131">Чтобы изменить почтовый ящик помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="3ef1b-132">В этом примере включается учетная запись существующего почтового ящика помещения, который имеет значение псевдонима "Иван2", и устанавливает пароль 9898P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="3ef1b-133">Обратите внимание, что учетная запись будет Rigel2@contoso.onmicrosoft.com из-за существующего значения псевдонима.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="3ef1b-134">Подробные сведения о синтаксисах и параметрах см. в настройках [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) [и Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="3ef1b-135">В Exchange Online PowerShell настройте следующие параметры почтового ящика помещения, чтобы улучшить качество собрания:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="3ef1b-136">AutomateProcessing: autoAccept (организаторы собраний принимают решение о резервировании помещений напрямую без участия человека: free = accept; busy = decline.)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="3ef1b-137">AddOrganizerToSubject: $false (организатор собрания не добавляется в тему запроса на собрание.)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="3ef1b-138">DeleteComments: $false (Текст должен быть в тексте входящих запросов на собрания).)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="3ef1b-139">DeleteSubject: $false (Храните тему входящих запросов на собрания.)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="3ef1b-140">RemovePrivateProperty: $false (Гарантирует, что личный флаг, отправленный организатором собрания в исходном запросе собрания, останется указанным.)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="3ef1b-141">AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="3ef1b-142">AdditionalResponse: "Это комната для собраний Skype!"</span><span class="sxs-lookup"><span data-stu-id="3ef1b-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="3ef1b-143">(Дополнительный текст, который нужно добавить в запрос на собрание.)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="3ef1b-144">В этом примере эти параметры настраиваются для почтового ящика помещения с именем Карели-01.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="3ef1b-145">Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="3ef1b-146">Подключите MS Online PowerShell, чтобы внести параметры Active Directory, задав их с помощью `Connect-MsolService -Credential $cred` cmdlet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="3ef1b-147">Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="3ef1b-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="3ef1b-149">Если вы не хотите, чтобы срок действия пароля истекал, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="3ef1b-150">В этом примере пароль учетной записи Rigel1@contoso.onmicrosoft.com срок действия никогда не истекает.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="3ef1b-151">Кроме того, можно настроить номер телефона для учетной записи, вы можете с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> <span data-ttu-id="3ef1b-152">Если для пароля не установлено действие "Никогда не истекает", учетная запись больше не будет вводиться на устройстве, когда срок действия учетной записи истечет.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-152">If the password is not set to Never Expire, the account will no longer sign in on the device when the account reaches the expiry period.</span></span> <span data-ttu-id="3ef1b-153">После этого потребуется изменить пароль для учетной записи, а также обновить его локально на устройстве MTR.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-153">The password will then need to be changed for the account and also updated locally on the MTR device.</span></span>

6. <span data-ttu-id="3ef1b-154">У учетной записи устройства должна быть действительная лицензия Microsoft 365 или Office 365 либо exchange, Microsoft Teams или Skype для бизнеса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-154">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="3ef1b-155">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-155">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="3ef1b-156">Вы можете использовать `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="3ef1b-156">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="3ef1b-157">чтобы получить список доступных skus для вашей организации Microsoft 365 или Office 365:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-157">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="3ef1b-158">Затем вы можете добавить лицензию с помощью `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="3ef1b-158">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="3ef1b-159">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-159">cmdlet.</span></span> <span data-ttu-id="3ef1b-160">В этом примере лицензия на комнату для собраний добавляется к учетной записи:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-160">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="3ef1b-161">Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с помощью [Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-161">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="3ef1b-162">Вы также можете добавить функции телефонной системы в эту учетную запись, но сначала необходимо ее настроить.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-162">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="3ef1b-163">Дополнительные сведения см. в [подмносях "Телефонная](../what-is-phone-system-in-office-365.md) система".</span><span class="sxs-lookup"><span data-stu-id="3ef1b-163">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="3ef1b-164">В этом примере добавляется план внутренних и международных звонков по ПС:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-164">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. <span data-ttu-id="3ef1b-165">Затем необходимо включить учетную запись устройства в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-165">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="3ef1b-166">Убедитесь, что ваша среда соответствует требованиям, определенным в требованиях к комнатам [Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-166">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="3ef1b-167">Начните [удаленный Windows PowerShell с](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) помощью таких компонентов (обязательно установите компоненты Skype для [бизнеса Online PowerShell):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="3ef1b-167">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

> [!NOTE]
> <span data-ttu-id="3ef1b-168">Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-168">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="3ef1b-169">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-169">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   <span data-ttu-id="3ef1b-170">Получите данные RegistrarPool из новой учетной записи пользователя, как показано в примере:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-170">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="3ef1b-171">Затем вите свою учетную запись комнат Microsoft Teams для Skype для бизнеса Server с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="3ef1b-171">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="3ef1b-172">Возможно, новые учетные записи пользователей не будут созданы в том же пуле реестра, что и существующие учетные записи пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-172">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="3ef1b-173">Эта команда предотвращает ошибки при настройке учетной записи в связи с этой ситуацией.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-173">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="3ef1b-174">Проверить</span><span class="sxs-lookup"><span data-stu-id="3ef1b-174">Validate</span></span>

<span data-ttu-id="3ef1b-175">Для проверки вы сможете войти в созданную учетную запись с помощью любого клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3ef1b-175">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ef1b-176">См. также</span><span class="sxs-lookup"><span data-stu-id="3ef1b-176">See also</span></span>

[<span data-ttu-id="3ef1b-177">Настройка учетных записей для комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ef1b-177">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="3ef1b-178">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ef1b-178">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="3ef1b-179">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ef1b-179">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="3ef1b-180">Настройка консоли комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ef1b-180">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="3ef1b-181">Управление комнатами Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ef1b-181">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="3ef1b-182">Лицензирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ef1b-182">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
