---
title: Создание учетных записей Microsoft Teams для панелей совместной работы в Microsoft Teams с помощью PowerShell
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В этой статье приведены сведения о том, как развертывать панели совместной работы в Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268049"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="d8cbb-103">Создание учетной записи ресурса Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8cbb-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="d8cbb-104">В этой статье приведены сведения о том, как создавать учетные записи ресурсов для панелей совместной работы в Microsoft Teams с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="d8cbb-105">Самый простой способ создать учетную запись ресурса — с помощью центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="d8cbb-106">[В этой статье показано, как это сделать](resource-account-ui.md).</span><span class="sxs-lookup"><span data-stu-id="d8cbb-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="d8cbb-107">Требования</span><span class="sxs-lookup"><span data-stu-id="d8cbb-107">Requirements</span></span>

<span data-ttu-id="d8cbb-108">Перед развертыванием комнат Microsoft Teams с помощью Office 365 убедитесь, что вы удовлетворены требованиями.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="d8cbb-109">Дополнительные сведения можно найти в разделе [Развертывание панелей совместной работы в Microsoft Teams](collab-bar-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="d8cbb-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="d8cbb-110">Если вам понадобятся возможности PSTN для панели совместной работы, вам понадобится лицензия на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="d8cbb-111">Ваши учетные записи ресурсов должны иметь почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="d8cbb-112">Так как это учетные записи ресурсов, лицензия Exchange не требуется.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="d8cbb-113">Мы рекомендуем использовать лицензию на использование комнат для собраний для учетных записей ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="d8cbb-114">Добавление учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="d8cbb-114">Add a resource account</span></span>

1. <span data-ttu-id="d8cbb-115">Подключитесь к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="d8cbb-116">Инструкции можно найти [в разделе Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span><span class="sxs-lookup"><span data-stu-id="d8cbb-116">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="d8cbb-117">В Exchange Online PowerShell создайте новый почтовый ящик помещения или измените существующий почтовый ящик помещения.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="d8cbb-118">Чтобы создать новый почтовый ящик комнаты, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d8cbb-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="d8cbb-119">В этом примере создается новый почтовый ящик комнаты со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="d8cbb-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="d8cbb-120">Name (имя): Huddle-Room-01</span><span class="sxs-lookup"><span data-stu-id="d8cbb-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="d8cbb-121">Alias (псевдоним): HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="d8cbb-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="d8cbb-122">Учетная запись: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d8cbb-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="d8cbb-123">Пароль учетной записи: P@ $ $W 0rd242</span><span class="sxs-lookup"><span data-stu-id="d8cbb-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="d8cbb-124">Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d8cbb-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="d8cbb-125">В этом примере включается учетная запись для почтового ящика помещения с параметром Alias HuddleRoom02 и устанавливается пароль для 808P@ $ $W 0rd.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="d8cbb-126">Обратите внимание, что учетная запись будет HuddleRoom02@contoso.onmicrosoft.com из-за существующего значения псевдонима.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="d8cbb-127">Подробные сведения о синтаксисе и параметрах можно найти в разделе [Создание почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) и [Настройка почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="d8cbb-127">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="d8cbb-128">В Exchange Online PowerShell настройте следующие параметры в почтовом ящике комнаты, чтобы улучшить процесс собрания:</span><span class="sxs-lookup"><span data-stu-id="d8cbb-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="d8cbb-129">AutomateProcessing: с помощью автопринятия (организаторов собраний) получайте решение о резервировании комнаты непосредственно без вмешательства человека: бесплатное = принять; занято = отклонить.)</span><span class="sxs-lookup"><span data-stu-id="d8cbb-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="d8cbb-130">AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему приглашения на собрание.)</span><span class="sxs-lookup"><span data-stu-id="d8cbb-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="d8cbb-131">DeleteComments: $false (Храните текст в тексте сообщения для входящих приглашений на собрания.)</span><span class="sxs-lookup"><span data-stu-id="d8cbb-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="d8cbb-132">DeleteSubject: $false (сохранить тему приглашений на входящие собрания).</span><span class="sxs-lookup"><span data-stu-id="d8cbb-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="d8cbb-133">RemovePrivateProperty: $false (гарантируется, что частный флаг, отправленный организатором собрания в исходном приглашении на собрание, будет установлен.)</span><span class="sxs-lookup"><span data-stu-id="d8cbb-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="d8cbb-134">AddAdditionalResponse: $true (текст, указанный в параметре AdditionalResponse, добавляется в приглашения на собрание.)</span><span class="sxs-lookup"><span data-stu-id="d8cbb-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="d8cbb-135">AdditionalResponse: "в этой комнате есть панель совместной работы для Microsoft Teams!"</span><span class="sxs-lookup"><span data-stu-id="d8cbb-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="d8cbb-136">(Дополнительный текст, добавляемый в приглашение на собрание.)</span><span class="sxs-lookup"><span data-stu-id="d8cbb-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="d8cbb-137">В этом примере эти параметры настраиваются в почтовом ящике комнаты с именем Huddle-Room-01.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="d8cbb-138">Подробные сведения о синтаксисе и параметрах можно найти в разделе [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="d8cbb-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="d8cbb-139">Подключитесь к MS Online PowerShell, чтобы настроить параметры Active Directory, запустив `Connect-MsolService -Credential $cred` командлет PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="d8cbb-140">Подробнее об Active Directory можно узнать в [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="d8cbb-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="d8cbb-141">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="d8cbb-142">Установите для пароля huddleroom01@contoso.onmicrosoft.com значение Not Expires, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d8cbb-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="d8cbb-143">Для учетной записи ресурса требуется действительная лицензия Office 365, предпочтительная SKU для помещения для собраний.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="d8cbb-144">Кроме того, необходимо назначить место использования учетной записи устройства, чтобы определить, какие SKU лицензий будут доступны для вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="d8cbb-145">Вы можете использовать `Get-MsolAccountSku` для получения списка доступных SKU для вашего клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="d8cbb-146">Вы можете назначить лицензию с помощью Set-MsolUserLicense.</span><span class="sxs-lookup"><span data-stu-id="d8cbb-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="d8cbb-147">Подробные инструкции приведены в разделе [Назначение лицензий учетным записям пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d8cbb-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="d8cbb-148">Настройка учетных записей для панелей совместной работы в Microsoft Teams с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8cbb-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="d8cbb-149">Развертывание панелей совместной работы в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8cbb-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="d8cbb-150">Панели совместной работы для лицензирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8cbb-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)


