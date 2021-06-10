---
title: Развертывание Комнаты Microsoft Teams с Exchange локальной системы
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: В этой теме вы также ознакомьтесь с информацией о развертывании Комнаты Microsoft Teams в гибридной среде с Exchange локальной среде.
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117357"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="4f492-103">Развертывание комнаты Microsoft Teams в локальной среде Exchange</span><span class="sxs-lookup"><span data-stu-id="4f492-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="4f492-104">В этой теме вы также ознакомьтесь с информацией о развертывании Комнаты Microsoft Teams в гибридной среде с локальной Exchange локальной Microsoft Teams или Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="4f492-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="4f492-105">Если в вашей организации есть несколько служб с некоторыми из локальной службы, а другие — через Интернет, то конфигурация будет зависеть от того, где именно находится та или иная служба.</span><span class="sxs-lookup"><span data-stu-id="4f492-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="4f492-106">В этой теме описывается гибридное развертывание Комнаты Microsoft Teams с локальной Exchange развертывания.</span><span class="sxs-lookup"><span data-stu-id="4f492-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="4f492-107">Так как в развертывании такого типа много разных вариантов, предоставить подробные инструкции для всех из них невозможно.</span><span class="sxs-lookup"><span data-stu-id="4f492-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="4f492-108">Этот процесс будет работать для многих конфигураций.</span><span class="sxs-lookup"><span data-stu-id="4f492-108">The following process will work for many configurations.</span></span> <span data-ttu-id="4f492-109">Если процесс не подгоняет под установку, рекомендуем использовать Windows PowerShell, чтобы получить такой же конечный результат, как описано здесь, а также для других вариантов развертывания.</span><span class="sxs-lookup"><span data-stu-id="4f492-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="4f492-110">Корпорация Майкрософт [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей или проверить существующие учетные записи ресурсов, чтобы превратить их в совместимые Комнаты Microsoft Teams учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="4f492-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="4f492-111">При этом вы можете настроить учетные записи, которые будут Комнаты Microsoft Teams устройство.</span><span class="sxs-lookup"><span data-stu-id="4f492-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4f492-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4f492-112">Requirements</span></span>

<span data-ttu-id="4f492-113">Прежде чем развертывать Комнаты Microsoft Teams с локальной Exchange, убедитесь, что выполнили требования.</span><span class="sxs-lookup"><span data-stu-id="4f492-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="4f492-114">Дополнительные сведения см. в Комнаты Microsoft Teams [требованиях.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="4f492-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="4f492-115">При развертывании Комнаты Microsoft Teams локальной Exchange вы будете использовать средства администрирования Active Directory, чтобы добавить адрес электронной почты для локальной учетной записи домена.</span><span class="sxs-lookup"><span data-stu-id="4f492-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="4f492-116">Эта учетная запись будет синхронизирована с Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="4f492-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="4f492-117">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4f492-117">You will need to:</span></span>
  
- <span data-ttu-id="4f492-118">Создайте учетную запись и синхронизируйте ее с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4f492-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="4f492-119">Включите удаленный почтовый ящик и задайте его свойства.</span><span class="sxs-lookup"><span data-stu-id="4f492-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="4f492-120">Назначьте Microsoft 365 или Office 365 лицензию.</span><span class="sxs-lookup"><span data-stu-id="4f492-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="4f492-121">В этой записи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f492-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="4f492-122">Для включения учетной записи устройства в вашей среде должны выполняться указанные ниже предварительные требования.</span><span class="sxs-lookup"><span data-stu-id="4f492-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="4f492-123">Вам потребуется в Skype для бизнеса Online (план 2) или более Microsoft 365 или Office 365 план.</span><span class="sxs-lookup"><span data-stu-id="4f492-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="4f492-124">План должен поддерживать функции конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="4f492-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="4f492-125">Если для Корпоративная голосовая связь телефонии (телефонии ОКП) необходимо использовать поставщиков услуг телефонии для Комнаты Microsoft Teams необходимо Skype для бизнеса Online (план 3).</span><span class="sxs-lookup"><span data-stu-id="4f492-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>

  - <span data-ttu-id="4f492-126">При настройке учетной записи комнаты в Microsoft Teams или Skype для бизнеса Online номер телефона должен быть назначен до включения учетной записи в качестве учетной записи комнаты.</span><span class="sxs-lookup"><span data-stu-id="4f492-126">When configuring a room account with Microsoft Teams or Skype for Business Online, the phone number should be assigned prior to the account being enabled as a room account.</span></span>
  
  - <span data-ttu-id="4f492-127">У пользователей клиента должны быть Exchange почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="4f492-127">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="4f492-128">Для Комнаты Microsoft Teams учетной записи требуется лицензия Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3), но лицензия на Exchange Online не требуется.</span><span class="sxs-lookup"><span data-stu-id="4f492-128">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="4f492-129">Назначьте Skype для бизнеса Server вашей учетной записи Комнаты Microsoft Teams лицензию.</span><span class="sxs-lookup"><span data-stu-id="4f492-129">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="4f492-130">Создание учетной записи и ее синхронизация с Active Directory</span><span class="sxs-lookup"><span data-stu-id="4f492-130">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="4f492-131">В **средстве "Пользователи** и компьютеры" Active Directory щелкните правой кнопкой мыши папку или организационную единицу, в которую будут созданы учетные записи Комнаты Microsoft Teams, нажмите кнопку Создать и выберите пользователь **.** </span><span class="sxs-lookup"><span data-stu-id="4f492-131">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="4f492-p107">Введите отображаемое имя из предыдущего командлета в поле **Полное имя**, а затем псевдоним в поле **Имя входа пользователя**. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4f492-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="4f492-p108">Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="4f492-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4f492-137">Выбор пароля **сроком действия не истекает** — это требование для Skype для бизнеса Server в Комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f492-137">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="4f492-138">В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена.</span><span class="sxs-lookup"><span data-stu-id="4f492-138">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="4f492-139">В этом случае необходимо создать исключение для каждой учетной записи Комнаты Microsoft Teams устройства.</span><span class="sxs-lookup"><span data-stu-id="4f492-139">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="4f492-140">После создания учетной записи выполните синхронизацию каталогов.</span><span class="sxs-lookup"><span data-stu-id="4f492-140">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="4f492-141">После этого перейдите на страницу пользователи в центре администрирования Microsoft 365 и убедитесь, что учетная запись, созданная на предыдущих шагах, была создана в Интернете.</span><span class="sxs-lookup"><span data-stu-id="4f492-141">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="4f492-142">Включите удаленный почтовый ящик и задайте его свойства.</span><span class="sxs-lookup"><span data-stu-id="4f492-142">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="4f492-143">[Откройте Exchange или](/powershell/exchange/exchange-server/open-the-exchange-management-shell) подключите его к серверу [Exchange с помощью удаленной оболочки PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)</span><span class="sxs-lookup"><span data-stu-id="4f492-143">[Open the Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="4f492-144">В Exchange PowerShell создайте почтовый ящик для этой учетной записи (в том числе включить учетную запись) с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="4f492-144">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="4f492-145">Подробные сведения о синтаксисе и параметрах см. в [описании Enable-Mailbox.](/powershell/module/exchange/mailboxes/enable-mailbox)</span><span class="sxs-lookup"><span data-stu-id="4f492-145">For detailed syntax and parameter information, see [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="4f492-146">В Exchange PowerShell настройте следующие параметры почтового ящика комнаты, чтобы улучшить собрание:</span><span class="sxs-lookup"><span data-stu-id="4f492-146">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="4f492-147">AutomateProcessing: autoAccept (организаторы собраний получают решение о резервировании помещений напрямую без участия человека: free = accept; busy = decline.)</span><span class="sxs-lookup"><span data-stu-id="4f492-147">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="4f492-148">AddOrganizerToSubject: $false (Организатор собрания не добавляется в тему запроса на собрание.)</span><span class="sxs-lookup"><span data-stu-id="4f492-148">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="4f492-149">DeleteComments: $false (Сохранить текст в тексте сообщения входящих запросов на собрание.)</span><span class="sxs-lookup"><span data-stu-id="4f492-149">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4f492-150">DeleteSubject: $false (Тема входящих запросов на собрания.)</span><span class="sxs-lookup"><span data-stu-id="4f492-150">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4f492-151">RemovePrivateProperty: $false (Гарантирует, что личный флажок, отправленный организатором собрания в исходном запросе на собрание, останется указанным.)</span><span class="sxs-lookup"><span data-stu-id="4f492-151">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="4f492-152">AddAdditionalResponse: $true (текст, заданный параметром AdditionalResponse, добавляется в запросы на собрания.)</span><span class="sxs-lookup"><span data-stu-id="4f492-152">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="4f492-153">AdditionalResponse: "Это Skype собрание!"</span><span class="sxs-lookup"><span data-stu-id="4f492-153">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="4f492-154">(Дополнительный текст, который нужно добавить в запрос на собрание.)</span><span class="sxs-lookup"><span data-stu-id="4f492-154">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="4f492-155">В этом примере эти параметры настраиваются для почтового ящика комнаты Project-Рубель-01.</span><span class="sxs-lookup"><span data-stu-id="4f492-155">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="4f492-156">Подробные сведения о синтаксисе и параметрах см. в описании [set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="4f492-156">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="4f492-157">Назначение лицензии Microsoft 365 или Office 365 лицензии</span><span class="sxs-lookup"><span data-stu-id="4f492-157">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="4f492-158">Подключение Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4f492-158">Connect to Azure Active Directory.</span></span> <span data-ttu-id="4f492-159">Подробные сведения об Active Directory см. в [azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="4f492-159">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="4f492-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4f492-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="4f492-161">У учетной записи устройства должна быть действительная Microsoft 365 лицензия Office 365 или Exchange и Microsoft Teams не будет работать.</span><span class="sxs-lookup"><span data-stu-id="4f492-161">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="4f492-162">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="4f492-162">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="4f492-163">Вы можете использовать `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="4f492-163">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="4f492-164">, чтобы получить список доступных skus.</span><span class="sxs-lookup"><span data-stu-id="4f492-164">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="4f492-165">Затем вы можете добавить лицензию с помощью `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="4f492-165">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="4f492-166">Командлет.</span><span class="sxs-lookup"><span data-stu-id="4f492-166">cmdlet.</span></span> <span data-ttu-id="4f492-167">В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="4f492-167">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   <span data-ttu-id="4f492-168">Подробные инструкции см. в описании назначения лицензий учетным записям пользователей с [помощью Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="4f492-168">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="4f492-169">Включить учетную запись устройства</span><span class="sxs-lookup"><span data-stu-id="4f492-169">Enable the device account</span></span>

<span data-ttu-id="4f492-170">Skype для бизнеса Online PowerShell используется для управления службами как для Microsoft Teams, так и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="4f492-170">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="4f492-171">Создайте удаленный сеанс Windows PowerShell на компьютере следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4f492-171">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="4f492-172">Skype для бизнеса В настоящее время Online Connector является частью последней версии Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f492-172">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="4f492-173">Если вы используете последний общедоступный [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Skype для бизнеса Online Connector.</span><span class="sxs-lookup"><span data-stu-id="4f492-173">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. <span data-ttu-id="4f492-174">Получить SIP-адрес учетной записи:</span><span class="sxs-lookup"><span data-stu-id="4f492-174">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="4f492-175">**Необязательный**.</span><span class="sxs-lookup"><span data-stu-id="4f492-175">**Optional.**</span></span> <span data-ttu-id="4f492-176">Если вы хотите назначить номер телефона учетной записи, необходимо выполнить операцию на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="4f492-176">If you want to assign a phone number to the account, the operation should be performed at this point.</span></span> <span data-ttu-id="4f492-177">Если вы хотите назначить номер телефона прямой маршрутии:</span><span class="sxs-lookup"><span data-stu-id="4f492-177">If you want to assign a Direct Routing phone number:</span></span>

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    <span data-ttu-id="4f492-178">Если вы назначаете номер телефона, предоставленный Корпорацией Майкрософт, воспользуйтесь приведенным ниже cmdlet после предоставления пользователю лицензии на план звонков:</span><span class="sxs-lookup"><span data-stu-id="4f492-178">If you're assigning a Microsoft provided phone number, use the cmdlet below after having provisioned the user with a Calling Plan license:</span></span>
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. <span data-ttu-id="4f492-179">Чтобы включить учетную запись Комнаты Microsoft Teams, с помощью этой команды:</span><span class="sxs-lookup"><span data-stu-id="4f492-179">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="4f492-180">Если вы не знаете, какое значение нужно использовать для параметра RegistrarPool в своей среде, вы можете получить это значение от существующего пользователя с помощью этой команды:</span><span class="sxs-lookup"><span data-stu-id="4f492-180">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="4f492-181">Назначение лицензии учетной записи Комнаты Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f492-181">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="4f492-182">Войдите в систему как администратор клиента, откройте центр администрирования Microsoft 365 и щелкните приложение Администратор.</span><span class="sxs-lookup"><span data-stu-id="4f492-182">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="4f492-183">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="4f492-183">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="4f492-184">Щелкните Комнаты Microsoft Teams учетной записи, а затем щелкните значок пера, чтобы изменить сведения об учетной записи.</span><span class="sxs-lookup"><span data-stu-id="4f492-184">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="4f492-185">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="4f492-185">Click **Licenses**.</span></span>
5. <span data-ttu-id="4f492-186">В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4f492-186">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="4f492-187">Если вы хотите использовать Корпоративная голосовая связь на сайте, необходимо использовать Комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f492-187">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="4f492-188">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4f492-188">Click **Save**.</span></span>

<span data-ttu-id="4f492-189">Для проверки вы сможете использовать любой клиент для входа в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="4f492-189">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4f492-190">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4f492-190">Related topics</span></span>

[<span data-ttu-id="4f492-191">Настройка учетных записей для Комнаты Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f492-191">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="4f492-192">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f492-192">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="4f492-193">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f492-193">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="4f492-194">Настройка консоли комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f492-194">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="4f492-195">Управление комнатами Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f492-195">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)