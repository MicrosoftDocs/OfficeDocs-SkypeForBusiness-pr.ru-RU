---
title: Создание Microsoft Teams ресурсов для полос совместной работы Microsoft Teams помощью PowerShell
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
description: Дополнительные сведения о развертывании полос совместной работы для Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115607"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="c67a1-103">Создание учетной Microsoft 365 ресурса с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c67a1-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="c67a1-104">В этой теме вы можете найти сведения о том, как создавать учетные записи ресурсов для полос совместной работы Microsoft Teams с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c67a1-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="c67a1-105">Учетную запись ресурса проще всего создать с помощью Microsoft 365 администрирования.</span><span class="sxs-lookup"><span data-stu-id="c67a1-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="c67a1-106">[См. эту статью о том, как это сделать.](resource-account-ui.md)</span><span class="sxs-lookup"><span data-stu-id="c67a1-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="c67a1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c67a1-107">Requirements</span></span>

<span data-ttu-id="c67a1-108">Прежде чем Комнаты Microsoft Teams с Office 365, убедитесь, что выполнены требования.</span><span class="sxs-lookup"><span data-stu-id="c67a1-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="c67a1-109">Дополнительные сведения см. в [этой](collab-bar-deploy.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c67a1-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="c67a1-110">Если для панели совместной работы требуются возможности ПСПС, вам потребуется телефонная система лицензию.</span><span class="sxs-lookup"><span data-stu-id="c67a1-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="c67a1-111">У учетных записей ресурсов должны быть Exchange почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="c67a1-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="c67a1-112">Так как это учетные записи ресурсов, Exchange лицензия не требуется.</span><span class="sxs-lookup"><span data-stu-id="c67a1-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="c67a1-113">Рекомендуем использовать лицензию "Комнаты собраний" для учетных записей ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c67a1-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="c67a1-114">Добавление учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="c67a1-114">Add a resource account</span></span>

1. <span data-ttu-id="c67a1-115">Подключение Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c67a1-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="c67a1-116">Инструкции см. в Подключение [Exchange Online PowerShell.](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)</span><span class="sxs-lookup"><span data-stu-id="c67a1-116">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="c67a1-117">В Exchange Online PowerShell создайте новый почтовый ящик помещения или измените существующий почтовый ящик комнаты.</span><span class="sxs-lookup"><span data-stu-id="c67a1-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="c67a1-118">Чтобы создать почтовый ящик помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c67a1-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="c67a1-119">В этом примере создается почтовый ящик помещения со следующими настройками:</span><span class="sxs-lookup"><span data-stu-id="c67a1-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="c67a1-120">Имя: Huddle-Room-01</span><span class="sxs-lookup"><span data-stu-id="c67a1-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="c67a1-121">Псевдоним: HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="c67a1-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="c67a1-122">Учетная запись: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c67a1-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="c67a1-123">Пароль учетной записи: P@$$W 0rd242</span><span class="sxs-lookup"><span data-stu-id="c67a1-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="c67a1-124">Чтобы изменить существующий почтовый ящик помещения, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c67a1-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="c67a1-125">В этом примере включается учетная запись существующего почтового ящика комнаты со значением псевдонима HuddleRoom02 и устанавливается пароль 808P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="c67a1-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="c67a1-126">Обратите внимание, что учетная запись HuddleRoom02@contoso.onmicrosoft.com из-за существующего значения псевдонима.</span><span class="sxs-lookup"><span data-stu-id="c67a1-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="c67a1-127">Подробные сведения о синтаксисе и параметрах см. в настройках [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) и [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="c67a1-127">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="c67a1-128">В Exchange Online PowerShell настройте следующие параметры почтового ящика комнаты, чтобы улучшить собрание:</span><span class="sxs-lookup"><span data-stu-id="c67a1-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="c67a1-129">AutomateProcessing: autoAccept (организаторы собраний получают решение о резервировании помещений напрямую без участия человека: free = accept; busy = decline.)</span><span class="sxs-lookup"><span data-stu-id="c67a1-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="c67a1-130">AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему запроса на собрание.)</span><span class="sxs-lookup"><span data-stu-id="c67a1-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="c67a1-131">DeleteComments: $false (Сохранять текст в тексте сообщения входящих запросов на собрания).)</span><span class="sxs-lookup"><span data-stu-id="c67a1-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="c67a1-132">DeleteSubject: $false (Храните тему входящих запросов на собрания.)</span><span class="sxs-lookup"><span data-stu-id="c67a1-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="c67a1-133">RemovePrivateProperty: $false (гарантирует, что личный флажок, отправленный организатором собрания в исходном запросе на собрание, не будет установлен.)</span><span class="sxs-lookup"><span data-stu-id="c67a1-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="c67a1-134">AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)</span><span class="sxs-lookup"><span data-stu-id="c67a1-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="c67a1-135">AdditionalResponse: "В этом помещении есть панели совместной работы для Microsoft Teams!"</span><span class="sxs-lookup"><span data-stu-id="c67a1-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="c67a1-136">(Дополнительный текст, который нужно добавить в запрос на собрание.)</span><span class="sxs-lookup"><span data-stu-id="c67a1-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="c67a1-137">В этом примере эти параметры настраиваются в почтовом ящике комнаты с именем Huddle-Room-01.</span><span class="sxs-lookup"><span data-stu-id="c67a1-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="c67a1-138">Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="c67a1-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="c67a1-139">Подключение в MS Online PowerShell, чтобы создать параметры Active Directory с помощью этого `Connect-MsolService -Credential $cred` mdlet.</span><span class="sxs-lookup"><span data-stu-id="c67a1-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="c67a1-140">Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="c67a1-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="c67a1-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c67a1-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="c67a1-142">Установите пароль для huddleroom01@contoso.onmicrosoft.com, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c67a1-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="c67a1-143">У учетной записи ресурса должна быть действительная Office 365 лицензия, предпочтительно Конференц-зал SKU.</span><span class="sxs-lookup"><span data-stu-id="c67a1-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="c67a1-144">Кроме того, необходимо назначить учетной записи устройства место использования — это определяет, какие номера номеров лицензий доступны для вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c67a1-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="c67a1-145">Вы можете `Get-MsolAccountSku` получить список доступных skUs для Office 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="c67a1-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="c67a1-146">Лицензию можно назначить с помощью Set-MsolUserLicense.</span><span class="sxs-lookup"><span data-stu-id="c67a1-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="c67a1-147">Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с [помощью Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="c67a1-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="c67a1-148">Настройка учетных записей для полос совместной работы Microsoft Teams с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c67a1-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="c67a1-149">Развертывание полос совместной работы для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c67a1-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="c67a1-150">Полосы совместной работы для Microsoft Teams лицензирования</span><span class="sxs-lookup"><span data-stu-id="c67a1-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)