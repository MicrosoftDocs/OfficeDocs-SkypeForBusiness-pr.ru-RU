---
title: Развертывание комнат Microsoft Teams с помощью Microsoft 365 или Office 365
ms.author: v-lanac
author: lanachin
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
description: В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams с помощью Microsoft 365 или Office 365, где в сети могут быть установлены команды или Skype для бизнеса и Exchange.
ms.openlocfilehash: ee1f4da5cbcb65ab58c032ac651e0b563167a35b
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814798"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="efdf8-103">Развертывание комнат Microsoft Teams с помощью Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="efdf8-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="efdf8-104">В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams в Microsoft 365 или Office 365, где Microsoft Teams или Skype для бизнеса и Exchange находятся в сети.</span><span class="sxs-lookup"><span data-stu-id="efdf8-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="efdf8-105">Самый простой способ настроить учетные записи пользователей — настроить их с помощью удаленной оболочки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efdf8-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="efdf8-106">Microsoft предлагает [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей или проверить существующие учетные записи ресурсов, чтобы их можно было превратить в совместимые учетные записи Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="efdf8-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="efdf8-107">Если вы предпочитаете, выполните указанные ниже действия, чтобы настроить учетные записи, которые будут использоваться на устройстве комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="efdf8-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="efdf8-108">Требования</span><span class="sxs-lookup"><span data-stu-id="efdf8-108">Requirements</span></span>

<span data-ttu-id="efdf8-109">Перед развертыванием комнат Microsoft Teams с помощью Microsoft 365 или Office 365 убедитесь, что вы удовлетворены требованиями.</span><span class="sxs-lookup"><span data-stu-id="efdf8-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="efdf8-110">Дополнительные сведения можно найти в разделе [требования к комнатам Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efdf8-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="efdf8-111">Чтобы включить Skype для бизнеса, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="efdf8-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="efdf8-112">Skype для бизнеса Online (план 2 или план на основе предприятия) или более позднюю версию в плане Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="efdf8-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="efdf8-113">План должен разрешить возможности конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="efdf8-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="efdf8-114">Если вам понадобятся возможности телефонного подключения к собранию, вам потребуется голосовой Конференц-связь и лицензия на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="efdf8-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="efdf8-115">Если вам понадобятся возможности удаленного доступа с собрания, вам понадобится лицензия на голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="efdf8-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="efdf8-116">Ваши пользователи клиента должны иметь почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="efdf8-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="efdf8-117">Для учетной записи Microsoft Team комнат требуется лицензия Skype для бизнеса Online (план 2), но для нее не требуется лицензия на Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="efdf8-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="efdf8-118">Дополнительные сведения см. в разделе [лицензии на комнаты Microsoft Teams](rooms-licensing.md) .</span><span class="sxs-lookup"><span data-stu-id="efdf8-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="efdf8-119">Подробнее о тарифах Skype для бизнеса Online можно найти в [описании службы Skype для бизнеса Online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="efdf8-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="efdf8-120">Добавление учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="efdf8-120">Add a device account</span></span>

1. <span data-ttu-id="efdf8-121">Подключитесь к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efdf8-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="efdf8-122">Инструкции можно найти [в разделе Подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="efdf8-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="efdf8-123">В Exchange Online PowerShell создайте новый почтовый ящик помещения или измените существующий почтовый ящик помещения.</span><span class="sxs-lookup"><span data-stu-id="efdf8-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="efdf8-124">По умолчанию для почтовых ящиков в комнате не предусмотрены связанные учетные записи, поэтому при создании или изменении почтового ящика помещения, позволяющего проверять подлинность с помощью системы комнат Skype v2, необходимо добавить учетную запись.</span><span class="sxs-lookup"><span data-stu-id="efdf8-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="efdf8-125">Чтобы создать новый почтовый ящик комнаты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efdf8-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="efdf8-126">В этом примере создается новый почтовый ящик комнаты со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="efdf8-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="efdf8-127">Name (имя): Rigel-01</span><span class="sxs-lookup"><span data-stu-id="efdf8-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="efdf8-128">Alias (псевдоним): Rigel1</span><span class="sxs-lookup"><span data-stu-id="efdf8-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="efdf8-129">Учетная запись: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="efdf8-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="efdf8-130">Пароль учетной записи: P@ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="efdf8-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="efdf8-131">Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efdf8-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="efdf8-132">В этом примере включается учетная запись для почтового ящика помещения с параметром Alias Rigel2 и устанавливается пароль для 9898P@ $ $W 0rd.</span><span class="sxs-lookup"><span data-stu-id="efdf8-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="efdf8-133">Обратите внимание, что учетная запись будет Rigel2@contoso.onmicrosoft.com из-за существующего значения псевдонима.</span><span class="sxs-lookup"><span data-stu-id="efdf8-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="efdf8-134">Подробные сведения о синтаксисе и параметрах можно найти в разделе [Создание почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) и [Настройка почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="efdf8-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="efdf8-135">В Exchange Online PowerShell настройте следующие параметры в почтовом ящике комнаты, чтобы улучшить процесс собрания:</span><span class="sxs-lookup"><span data-stu-id="efdf8-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="efdf8-136">AutomateProcessing: с помощью автопринятия (организаторов собраний) получайте решение о резервировании комнаты непосредственно без вмешательства человека: бесплатное = принять; занято = отклонить.)</span><span class="sxs-lookup"><span data-stu-id="efdf8-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="efdf8-137">AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему приглашения на собрание.)</span><span class="sxs-lookup"><span data-stu-id="efdf8-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="efdf8-138">DeleteComments: $false (Храните текст в тексте сообщения для входящих приглашений на собрания.)</span><span class="sxs-lookup"><span data-stu-id="efdf8-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="efdf8-139">DeleteSubject: $false (сохранить тему приглашений на входящие собрания).</span><span class="sxs-lookup"><span data-stu-id="efdf8-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="efdf8-140">RemovePrivateProperty: $false (гарантируется, что частный флаг, отправленный организатором собрания в исходном приглашении на собрание, будет установлен.)</span><span class="sxs-lookup"><span data-stu-id="efdf8-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="efdf8-141">AddAdditionalResponse: $true (текст, указанный в параметре AdditionalResponse, добавляется в приглашения на собрание.)</span><span class="sxs-lookup"><span data-stu-id="efdf8-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="efdf8-142">AdditionalResponse: "это комната для собраний Skype!"</span><span class="sxs-lookup"><span data-stu-id="efdf8-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="efdf8-143">(Дополнительный текст, добавляемый в приглашение на собрание.)</span><span class="sxs-lookup"><span data-stu-id="efdf8-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="efdf8-144">В этом примере эти параметры настраиваются в почтовом ящике комнаты с именем Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="efdf8-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="efdf8-145">Подробные сведения о синтаксисе и параметрах можно найти в разделе [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="efdf8-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="efdf8-146">Подключитесь к MS Online PowerShell, чтобы настроить параметры Active Directory, запустив `Connect-MsolService -Credential $cred` командлет PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efdf8-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="efdf8-147">Подробнее об Active Directory можно узнать в [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="efdf8-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="efdf8-148">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="efdf8-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="efdf8-149">Если вы не хотите ограничивать срок действия пароля, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="efdf8-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```
   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="efdf8-150">В этом примере в качестве пароля для учетной записи Rigel1@contoso.onmicrosoft.com никогда не задается срок действия.</span><span class="sxs-lookup"><span data-stu-id="efdf8-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName Rigel1@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="efdf8-151">Вы также можете задать номер телефона для учетной записи, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="efdf8-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="efdf8-152">Учетная запись устройства должна иметь действительную лицензию Microsoft 365 или Office 365, либо Exchange и Microsoft Teams или Skype для бизнеса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="efdf8-152">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="efdf8-153">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="efdf8-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="efdf8-154">Вы можете использовать `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="efdf8-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="efdf8-155">чтобы получить список доступных SKU для вашей организации Microsoft 365 или Office 365, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="efdf8-155">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```
   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="efdf8-156">Затем вы можете добавить лицензию с помощью `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="efdf8-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="efdf8-157">Командлет.</span><span class="sxs-lookup"><span data-stu-id="efdf8-157">cmdlet.</span></span> <span data-ttu-id="efdf8-158">В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="efdf8-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ``` 
   <!-- 
   ```Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="efdf8-159">Подробные инструкции приведены в разделе [Назначение лицензий учетным записям пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="efdf8-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="efdf8-160">Затем вам нужно включить учетную запись устройства в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="efdf8-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="efdf8-161">Убедитесь, что ваша среда соответствует требованиям, определенным в [требованиях к комнатам Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efdf8-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="efdf8-162">Запустите удаленный [сеанс Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) следующим образом (не забудьте [установить компоненты PowerShell для Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="efdf8-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>
   
> [!NOTE]
> <span data-ttu-id="efdf8-163">Skype для бизнеса Online уже входит в состав последнего модуля PowerShell для Teams.</span><span class="sxs-lookup"><span data-stu-id="efdf8-163">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="efdf8-164">Если вы используете последнюю версию [общедоступной оболочки для Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="efdf8-164">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="efdf8-165">Затем включите на сервер Skype для бизнеса учетную запись Microsoft Teams, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="efdf8-165">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   $rm="Rigel1@contoso.onmicrosoft.com"
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="efdf8-166">Получите сведения о RegistrarPool из новой учетной записи пользователя, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="efdf8-166">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    $rm="Rigel1@contoso.onmicrosoft.com"
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > New user accounts might not be created on the same registrar pool as existing user accounts in the tenant. The command above will prevent errors in account setup due to this situation.

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="efdf8-167">Назначение лицензии учетной записи</span><span class="sxs-lookup"><span data-stu-id="efdf8-167">Assign a license to your account</span></span>

1. <span data-ttu-id="efdf8-168">Войдите в систему как администратор клиента, откройте центр администрирования Microsoft 365 и щелкните Приложение администратор.</span><span class="sxs-lookup"><span data-stu-id="efdf8-168">Login as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>

2. <span data-ttu-id="efdf8-169">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="efdf8-169">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="efdf8-170">Выберите учетную запись комнаты Microsoft Teams, а затем щелкните значок пера, который означает редактирование.</span><span class="sxs-lookup"><span data-stu-id="efdf8-170">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="efdf8-171">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="efdf8-171">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="efdf8-172">В разделе **Назначение лицензий** вам нужно выбрать Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3), в зависимости от вашего лицензирования и от того, что вы решили в условиях потребности в корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="efdf8-172">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="efdf8-173">Если вы хотите использовать облачную УАТС в комнатах Microsoft Teams, вам придется использовать лицензию план 3.</span><span class="sxs-lookup"><span data-stu-id="efdf8-173">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="efdf8-174">Облачная УАТС потребуется как минимум для подключения к голосовому каналу.</span><span class="sxs-lookup"><span data-stu-id="efdf8-174">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="efdf8-175">Затем настройте гибридную голосовую связь или звонки по ТСОП в соответствии со способом связи с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="efdf8-175">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="efdf8-176">Дополнительные сведения см. в разделе [лицензии на комнаты Microsoft Teams](rooms-licensing.md) .</span><span class="sxs-lookup"><span data-stu-id="efdf8-176">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for more details.</span></span>

6. <span data-ttu-id="efdf8-177">Чтобы завершить задачу, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="efdf8-177">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="efdf8-178">Пример: Настройка учетной записи комнаты в Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="efdf8-178">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="efdf8-179">Команды PowerShell для Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="efdf8-179">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="efdf8-180">Команды PowerShell для Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="efdf8-180">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="efdf8-181">Команда PowerShell для Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="efdf8-181">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="efdf8-182">Будут добавлены CloudPBX и PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="efdf8-182">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="efdf8-183">Кроме того, вы должны использовать интерфейс администратора для назначения номера телефона.</span><span class="sxs-lookup"><span data-stu-id="efdf8-183">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="efdf8-184">Действитель</span><span class="sxs-lookup"><span data-stu-id="efdf8-184">Validate</span></span>

<span data-ttu-id="efdf8-185">Для проверки подлинности вы можете использовать любой клиент Skype для бизнеса для входа в созданную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="efdf8-185">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="efdf8-186">См. также</span><span class="sxs-lookup"><span data-stu-id="efdf8-186">See also</span></span>

[<span data-ttu-id="efdf8-187">Настройка учетных записей для комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efdf8-187">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="efdf8-188">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efdf8-188">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="efdf8-189">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efdf8-189">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="efdf8-190">Настройка консоли комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efdf8-190">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="efdf8-191">Управление комнатами Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efdf8-191">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="efdf8-192">Лицензирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efdf8-192">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
