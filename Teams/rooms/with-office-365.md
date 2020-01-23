---
title: Развертывание комнаты Microsoft Teams с Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Сведения о том, как развертывать комнаты Microsoft Teams с помощью Office 365, читайте в этой статье.
ms.openlocfilehash: 6b473fc54574f26909e274662f3c08c1031dfafb
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269205"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="d1e27-103">Развертывание комнаты Microsoft Teams с Office 365</span><span class="sxs-lookup"><span data-stu-id="d1e27-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="d1e27-104">В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams в Office 365, где Microsoft Teams или Skype для бизнеса и Exchange находятся в сети.</span><span class="sxs-lookup"><span data-stu-id="d1e27-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="d1e27-105">Самый простой способ настроить учетные записи пользователей — настроить их с помощью удаленной оболочки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1e27-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="d1e27-106">Корпорация Майкрософт предоставляет [скиперумпровисионингскрипт. ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или проверить имеющиеся учетные записи ресурсов, чтобы их можно было превратить в совместимые учетные записи Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1e27-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="d1e27-107">Если вы предпочитаете, выполните указанные ниже действия, чтобы настроить учетные записи, которые будут использоваться на устройстве комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1e27-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="d1e27-108">Требования</span><span class="sxs-lookup"><span data-stu-id="d1e27-108">Requirements</span></span>

<span data-ttu-id="d1e27-109">Перед развертыванием комнат Microsoft Teams с помощью Office 365 убедитесь, что вы удовлетворены требованиями.</span><span class="sxs-lookup"><span data-stu-id="d1e27-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="d1e27-110">Дополнительные сведения можно найти в разделе [требования к комнатам Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1e27-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="d1e27-111">Чтобы включить Skype для бизнеса, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d1e27-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="d1e27-112">Skype для бизнеса Online (план 2 или план на основе предприятия) или более позднюю версию в плане Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1e27-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="d1e27-113">План должен разрешить возможности конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="d1e27-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="d1e27-114">Если вам понадобятся возможности телефонного подключения к собранию, вам потребуется голосовой Конференц-связь и лицензия на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="d1e27-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="d1e27-115">Если вам нужны возможности исходящих звонков с собрания, вам понадобится план внутренних или внутренних и международных звонков.</span><span class="sxs-lookup"><span data-stu-id="d1e27-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="d1e27-116">Ваши пользователи клиента должны иметь почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="d1e27-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="d1e27-117">Для учетной записи Microsoft Team комнат требуется лицензия Skype для бизнеса Online (план 2), но для нее не требуется лицензия на Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d1e27-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="d1e27-118">Дополнительные сведения см. в разделе [лицензии на комнаты Microsoft Teams](rooms-licensing.md) .</span><span class="sxs-lookup"><span data-stu-id="d1e27-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="d1e27-119">Подробнее о тарифах Skype для бизнеса Online можно найти в [описании службы Skype для бизнеса Online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="d1e27-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="d1e27-120">Добавление учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="d1e27-120">Add a device account</span></span>

1. <span data-ttu-id="d1e27-121">Подключитесь к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1e27-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="d1e27-122">Инструкции можно найти [в разделе Подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="d1e27-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="d1e27-123">В Exchange Online PowerShell создайте новый почтовый ящик помещения или измените существующий почтовый ящик помещения.</span><span class="sxs-lookup"><span data-stu-id="d1e27-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="d1e27-124">По умолчанию для почтовых ящиков в комнате не предусмотрены связанные учетные записи, поэтому при создании или изменении почтового ящика помещения, позволяющего проверять подлинность с помощью системы комнат Skype v2, необходимо добавить учетную запись.</span><span class="sxs-lookup"><span data-stu-id="d1e27-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="d1e27-125">Чтобы создать новый почтовый ящик комнаты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d1e27-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="d1e27-126">В этом примере создается новый почтовый ящик комнаты со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="d1e27-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="d1e27-127">Имя: Project-Рижел-01</span><span class="sxs-lookup"><span data-stu-id="d1e27-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="d1e27-128">Alias (псевдоним): ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="d1e27-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="d1e27-129">Учетная запись: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d1e27-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="d1e27-130">Пароль учетной записи: P@ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="d1e27-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="d1e27-131">Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d1e27-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="d1e27-132">В этом примере включается учетная запись для почтового ящика помещения с параметром Alias ProjectRigel02 и устанавливается пароль для 9898P@ $ $W 0rd.</span><span class="sxs-lookup"><span data-stu-id="d1e27-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="d1e27-133">Обратите внимание, что учетная запись будет ProjectRigel02@contoso.onmicrosoft.com из-за существующего значения псевдонима.</span><span class="sxs-lookup"><span data-stu-id="d1e27-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="d1e27-134">Подробные сведения о синтаксисе и параметрах можно найти в разделе [Создание почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) и [Настройка почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="d1e27-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="d1e27-135">В Exchange Online PowerShell настройте следующие параметры в почтовом ящике комнаты, чтобы улучшить процесс собрания:</span><span class="sxs-lookup"><span data-stu-id="d1e27-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="d1e27-136">Аутоматепроцессинг: с помощью автопринятия (организаторов собраний) получайте решение о резервировании комнаты непосредственно без вмешательства человека: бесплатное = принять; занято = отклонить.)</span><span class="sxs-lookup"><span data-stu-id="d1e27-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="d1e27-137">Аддорганизертосубжект: $false (Организатор собрания не добавляется в тему приглашения на собрание.)</span><span class="sxs-lookup"><span data-stu-id="d1e27-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="d1e27-138">Делетекомментс: $false (Храните текст в тексте сообщения для входящих приглашений на собрания.)</span><span class="sxs-lookup"><span data-stu-id="d1e27-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="d1e27-139">Делетесубжект: $false (сохранить тему приглашений на входящие собрания).</span><span class="sxs-lookup"><span data-stu-id="d1e27-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="d1e27-140">Ремовеприватепроперти: $false (гарантируется, что частный флаг, отправленный организатором собрания в исходном приглашении на собрание, будет установлен.)</span><span class="sxs-lookup"><span data-stu-id="d1e27-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="d1e27-141">Аддаддитионалреспонсе: $true (текст, указанный в параметре Аддитионалреспонсе, добавляется в приглашения на собрание.)</span><span class="sxs-lookup"><span data-stu-id="d1e27-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="d1e27-142">Аддитионалреспонсе: "это комната для собраний Skype!"</span><span class="sxs-lookup"><span data-stu-id="d1e27-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="d1e27-143">(Дополнительный текст, добавляемый в приглашение на собрание.)</span><span class="sxs-lookup"><span data-stu-id="d1e27-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="d1e27-144">Этот пример настраивает эти параметры в почтовом ящике комнаты с именем Project-Рижел-01.</span><span class="sxs-lookup"><span data-stu-id="d1e27-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="d1e27-145">Подробные сведения о синтаксисе и параметрах можно найти в разделе [Set-календарпроцессинг](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="d1e27-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="d1e27-146">Подключитесь к MS Online PowerShell, чтобы настроить параметры Active Directory, `Connect-MsolService -Credential $cred` запустив командлет PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1e27-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="d1e27-147">Подробнее об Active Directory можно узнать в [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="d1e27-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="d1e27-148">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d1e27-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="d1e27-149">Если вы не хотите ограничивать срок действия пароля, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d1e27-149">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="d1e27-150">В этом примере в качестве пароля для учетной записи ProjectRigel01@contoso.onmicrosoft.com никогда не задается срок действия.</span><span class="sxs-lookup"><span data-stu-id="d1e27-150">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="d1e27-151">Вы также можете задать номер телефона для учетной записи, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d1e27-151">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="d1e27-152">Учетная запись устройства должна иметь действительную лицензию на Office 365, либо Exchange и Microsoft Teams или Skype для бизнеса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="d1e27-152">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="d1e27-153">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d1e27-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="d1e27-154">Вы можете использовать`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="d1e27-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="d1e27-155">чтобы получить список доступных SKU для клиента Office 365, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d1e27-155">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="d1e27-156">Затем вы можете добавить лицензию с помощью`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="d1e27-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="d1e27-157">Командлет.</span><span class="sxs-lookup"><span data-stu-id="d1e27-157">cmdlet.</span></span> <span data-ttu-id="d1e27-158">В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="d1e27-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="d1e27-159">Подробные инструкции приведены в разделе [Назначение лицензий учетным записям пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d1e27-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="d1e27-160">Затем вам нужно включить учетную запись устройства в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d1e27-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="d1e27-161">Убедитесь, что ваша среда соответствует требованиям, определенным в [требованиях к комнатам Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1e27-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="d1e27-162">Запустите удаленный [сеанс Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) следующим образом (не забудьте [установить компоненты PowerShell для Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="d1e27-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="d1e27-163">Затем включите на сервер Skype для бизнеса учетную запись Microsoft Teams, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="d1e27-163">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="d1e27-164">Получите сведения о Регистрарпул из новой учетной записи пользователя, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d1e27-164">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="d1e27-165">Новые учетные записи пользователей могут не создаваться в том же пуле регистраторов, что и существующие учетные записи пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="d1e27-165">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="d1e27-166">Приведенная выше команда будет препятствовать ошибкам в настройке учетной записи из-за этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="d1e27-166">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="d1e27-167">После выполнения описанных выше действий для включения учетной записи Microsoft Teams в Microsoft Teams или Skype для бизнеса Online необходимо назначить лицензию для устройства Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1e27-167">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="d1e27-168">С помощью административного портала Office 365 Назначьте устройству Skype для бизнеса Online (план 2) или лицензию Skype для бизнеса Online (план 3).</span><span class="sxs-lookup"><span data-stu-id="d1e27-168">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="d1e27-169">Назначение лицензии учетной записи</span><span class="sxs-lookup"><span data-stu-id="d1e27-169">Assign a license to your account</span></span>

1. <span data-ttu-id="d1e27-170">Войдите в систему как администратор клиента, откройте административный портал Office 365 и щелкните Приложение администратор.</span><span class="sxs-lookup"><span data-stu-id="d1e27-170">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="d1e27-171">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="d1e27-171">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="d1e27-172">Выберите учетную запись комнаты Microsoft Teams, а затем щелкните значок пера, который означает редактирование.</span><span class="sxs-lookup"><span data-stu-id="d1e27-172">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="d1e27-173">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="d1e27-173">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="d1e27-174">В разделе **Назначение лицензий** вам нужно выбрать Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3), в зависимости от вашего лицензирования и от того, что вы решили в условиях потребности в корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="d1e27-174">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="d1e27-175">Если вы хотите использовать облачную УАТС в комнатах Microsoft Teams, вам придется использовать лицензию план 3.</span><span class="sxs-lookup"><span data-stu-id="d1e27-175">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="d1e27-176">Облачная УАТС потребуется как минимум для подключения к голосовому каналу.</span><span class="sxs-lookup"><span data-stu-id="d1e27-176">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="d1e27-177">Затем настройте гибридную голосовую связь или звонки по ТСОП в соответствии со способом связи с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="d1e27-177">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="d1e27-178">Дополнительные сведения см. в разделе [лицензии на комнаты Microsoft Teams](rooms-licensing.md) .</span><span class="sxs-lookup"><span data-stu-id="d1e27-178">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for more details.</span></span>

6. <span data-ttu-id="d1e27-179">Чтобы завершить задачу, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d1e27-179">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="d1e27-180">Пример: Настройка учетной записи комнаты в Exchange Online и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d1e27-180">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="d1e27-181">Команды PowerShell для Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="d1e27-181">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="d1e27-182">Команды PowerShell для Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="d1e27-182">Azure Active Directory PowerShell commands:</span></span>

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

<span data-ttu-id="d1e27-183">Команда PowerShell для Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="d1e27-183">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="d1e27-184">Будут добавлены CloudPBX и PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="d1e27-184">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="d1e27-185">Кроме того, вы должны использовать интерфейс администратора для назначения номера телефона.</span><span class="sxs-lookup"><span data-stu-id="d1e27-185">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="d1e27-186">Действитель</span><span class="sxs-lookup"><span data-stu-id="d1e27-186">Validate</span></span>

<span data-ttu-id="d1e27-187">Для проверки подлинности вы можете использовать любой клиент Skype для бизнеса для входа в созданную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="d1e27-187">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1e27-188">См. также</span><span class="sxs-lookup"><span data-stu-id="d1e27-188">See also</span></span>

[<span data-ttu-id="d1e27-189">Настройка учетных записей для комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1e27-189">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="d1e27-190">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1e27-190">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="d1e27-191">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1e27-191">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="d1e27-192">Настройка консоли Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1e27-192">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="d1e27-193">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="d1e27-193">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="d1e27-194">Лицензирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1e27-194">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
