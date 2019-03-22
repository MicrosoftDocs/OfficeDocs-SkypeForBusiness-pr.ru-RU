---
title: Развертывание Систем комнат Skype версии 2 в локальной среде Exchange
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 в гибридной среде с сервером Exchange при локальном.
ms.openlocfilehash: 9ebd7463465d8b2fbf11e95d71c8fcb557666b3a
ms.sourcegitcommit: cad74f2546a6384747b1280c3d9244aa13fd0989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2019
ms.locfileid: "30737796"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="ed5c4-103">Развертывание Систем комнат Skype версии 2 в локальной среде Exchange</span><span class="sxs-lookup"><span data-stu-id="ed5c4-103">Deploy Skype Room Systems v2 with Exchange on premises</span></span>

<span data-ttu-id="ed5c4-104">В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 в гибридной среде с Exchange при локальном и Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-104">Read this topic for information on how to deploy Skype Room Systems v2 in a hybrid environment with Exchange on premises and Skype for Business Online.</span></span>
  
<span data-ttu-id="ed5c4-105">Если в организации имеется набор служб, с некоторыми размещенных в локальную организацию и некоторые размещаются в сети, конфигурации будут зависеть от размещение каждой службы.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="ed5c4-106">В этом разделе рассматриваются гибридного развертывания в системах комнаты Скайп версии 2 с Exchange hosted локально.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span></span> <span data-ttu-id="ed5c4-107">Из-за слишком большом числе различные варианты в этом типе развертывания, не поддерживается представлены подробные инструкции по их все.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="ed5c4-108">Процесс будет работать для многих конфигураций.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-108">The following process will work for many configurations.</span></span> <span data-ttu-id="ed5c4-109">Если процесс не подходит для вашей установки, мы рекомендуем использовать Windows PowerShell для достижения же конечный результат, как описано ниже, а также другие параметры развертывания.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="ed5c4-110">Корпорация Майкрософт предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или validate существующие учетные записи ресурсов, что у вас есть помогающих перевод их в совместимые учетных записей пользователей системы комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="ed5c4-111">При необходимости можно выполните следующие действия, чтобы настроить учетные записи, используемые устройства версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-111">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ed5c4-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ed5c4-112">Requirements</span></span>

<span data-ttu-id="ed5c4-113">Перед развертыванием системы комнаты Скайп версии 2 с сервером Exchange при локальном убедитесь, что удовлетворены требования.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-113">Before you deploy Skype Room Systems v2 with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="ed5c4-114">Дополнительные сведения см. в разделе [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="ed5c4-115">При развертывании системы комнаты Скайп версии 2 с сервером Exchange при локальном использовании средств администрирования Active Directory для добавления адрес электронной почты для учетной записи домена в локальной.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-115">If you are deploying Skype Room Systems v2 with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="ed5c4-116">Эта учетная запись будет синхронизирован с Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="ed5c4-117">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-117">You will need to:</span></span>
  
- <span data-ttu-id="ed5c4-118">Создайте учетную запись и синхронизируйте ее с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="ed5c4-119">Включите удаленный почтовый ящик и задайте его свойства.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="ed5c4-120">Назначение лицензии Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="ed5c4-121">Включение учетной записи устройства с Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="ed5c4-122">Для включения учетной записи устройства в вашей среде должны выполняться указанные ниже предварительные требования.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="ed5c4-123">Необходимо иметь Скайп для бизнеса Online (план 2) или более поздней версии в плане Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="ed5c4-124">План должен поддерживать функции конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-124">The plan needs to support conferencing capability.</span></span>
  
  - - <span data-ttu-id="ed5c4-125">Если вам требуется корпоративной голосовой связи (телефонии PSTN) с помощью службы телефонии для систем комнаты Скайп версии 2 необходимо Скайп для бизнеса Online (план 3).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
  
  - - <span data-ttu-id="ed5c4-126">Клиент пользователи должны иметь почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - - <span data-ttu-id="ed5c4-127">Вашей системы комнаты Скайп версии 2 для учетной записи требуются Скайп для бизнеса Online (план 2) или Скайп для бизнеса в Интернет (план 3) лицензии, но не требует лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="ed5c4-128">Назначьте Скайп лицензию Business Server для учетной записи системы комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-128">Assign a Skype for Business Server license to your Skype Room Systems v2 account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="ed5c4-129">Создание учетной записи и ее синхронизация с Active Directory</span><span class="sxs-lookup"><span data-stu-id="ed5c4-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="ed5c4-130">Средства **Active Directory — пользователи и компьютеры AD** щелкните правой кнопкой мыши папку или подразделение, что систем комнаты Скайп v2 учетные записи будут создаваться в, нажмите кнопку **Создать**и выберите пункт **пользователь**.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-130">In the **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="ed5c4-p107">Введите отображаемое имя из предыдущего командлета в поле **Полное имя**, а затем псевдоним в поле **Имя входа пользователя**. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="ed5c4-p108">Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ed5c4-136">Выбор **Срок действия пароля не ограничен** является обязательным требованием для Скайп для Business Server на Скайп комнаты систем версии 2.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="ed5c4-137">В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="ed5c4-138">Если Да, необходимо создать исключение для каждой учетной записи системы комнаты Скайп версии 2 устройства.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-138">If so, you'll need to create an exception for each Skype Room Systems v2 device account.</span></span>
  
4. <span data-ttu-id="ed5c4-139">После создания учетной записи выполните синхронизацию каталогов.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="ed5c4-140">После завершения перейдите на страницу пользователей в центре администрирования Office 365 и убедитесь, что учетной записи, созданной на предыдущих шагах содержащей объединенные в Интернете.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-140">When it's complete, go to the users page in your Office 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="ed5c4-141">Включите удаленный почтовый ящик и задайте его свойства.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="ed5c4-142">[Откройте командную консоль Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) или [подключиться к серверу Exchange server с помощью удаленной оболочки PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="ed5c4-143">В Exchange PowerShell создавать почтового ящика для учетной записи (почтового ящика включения учетной записи), выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ed5c4-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="ed5c4-144">Подробный синтаксис и сведений о параметрах в разделе [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="ed5c4-145">В Exchange PowerShell настройте следующие параметры на почтовый ящик помещения, чтобы улучшить работу в собрание:</span><span class="sxs-lookup"><span data-stu-id="ed5c4-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="ed5c4-146">AutomateProcessing: AutoAccept (организаторам собрания принимать решение резервирования помещений напрямую без участия: свободен = принять; занят = отклонить.)</span><span class="sxs-lookup"><span data-stu-id="ed5c4-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="ed5c4-147">AddOrganizerToSubject: $false (организатор собрания не добавляется к теме запроса на проведение собрания).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="ed5c4-148">DeleteComments: $false (сохранения любого текста в теле сообщения входящих приглашений на собрания).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="ed5c4-149">DeleteSubject: $false (Keep темы входящих приглашений на собрания).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="ed5c4-150">RemovePrivateProperty: $false (гарантирует пометку "частное", которые были отправлены организатором собрания в исходное приглашение на собрание запросить остается как указано).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="ed5c4-151">AddAdditionalResponse: $true (текста, указанного с помощью параметра AdditionalResponse добавляется для приглашений на собрания).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="ed5c4-152">AdditionalResponse: «это Скайп конференц-зала!»</span><span class="sxs-lookup"><span data-stu-id="ed5c4-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="ed5c4-153">(Дополнительный текст для добавления в запрос на собрание.)</span><span class="sxs-lookup"><span data-stu-id="ed5c4-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="ed5c4-154">В этом примере настраивается эти параметры в почтовый ящик помещения, с именем Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="ed5c4-155">Подробный синтаксис и сведений о параметрах в разделе [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="ed5c4-156">Назначение лицензии Office 365</span><span class="sxs-lookup"><span data-stu-id="ed5c4-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="ed5c4-157">Подключитесь к PowerShell Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-157">Connect to Azure Active Directory PowerShell.</span></span> <span data-ttu-id="ed5c4-158">Сведения содержатся в разделе [подключение с помощью Azure Active Directory PowerShell для модуля "график"](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ed5c4-158">For instructions, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span></span>

2. <span data-ttu-id="ed5c4-159">Учетная запись устройства должна быть действительной лицензии Office 365 или Exchange и Скайп для бизнеса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-159">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="ed5c4-160">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-160">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="ed5c4-161">Вы можете использовать`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="ed5c4-161">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="ed5c4-162">Чтобы получить список доступных номеров SKU.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-162">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="ed5c4-163">Теперь можно добавить лицензии с помощью`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="ed5c4-163">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="ed5c4-164">командлет.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-164">cmdlet.</span></span> <span data-ttu-id="ed5c4-165">В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-165">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="ed5c4-166">Подробные сведения содержатся в разделе [Назначение лицензий для учетных записей пользователей с Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ed5c4-166">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="ed5c4-167">Включение учетной записи устройства со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ed5c4-167">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="ed5c4-168">Создайте удаленного сеанса Windows PowerShell с ПК, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="ed5c4-168">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="ed5c4-169">Включение учетной записи системы комнаты Скайп версии 2 для Скайп для Business Server, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-169">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="ed5c4-170">Если вы не уверены, используйте для параметра RegistrarPool в вашей среде, можно получить значение из существующего Скайп для пользователя Business Server, с помощью этой команды</span><span class="sxs-lookup"><span data-stu-id="ed5c4-170">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="ed5c4-171">Назначение лицензии Skype для бизнеса своей учетной записи Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="ed5c4-171">Assign a Skype for Business license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="ed5c4-172">Выполните вход в качестве администратора клиента, откройте административного портала Office 365 и щелкните приложения администрирования.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-172">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="ed5c4-173">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-173">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="ed5c4-174">Щелкните учетную запись комнаты систем Скайп версии 2 и нажмите кнопку перо значок, чтобы изменить сведения об учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-174">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="ed5c4-175">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-175">Click **Licenses**.</span></span>
5. <span data-ttu-id="ed5c4-176">В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-176">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="ed5c4-177">Вам потребуется использовать лицензии планирование 3, если вы хотите использовать корпоративной голосовой связи на вашей версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-177">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
6. <span data-ttu-id="ed5c4-178">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-178">Click **Save**.</span></span>

<span data-ttu-id="ed5c4-179">Для проверки можно использовать любой Скайп для бизнеса клиента для входа в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="ed5c4-179">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ed5c4-180">См. также</span><span class="sxs-lookup"><span data-stu-id="ed5c4-180">See also</span></span>

[<span data-ttu-id="ed5c4-181">Настройка учетных записей для систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="ed5c4-181">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="ed5c4-182">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="ed5c4-182">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="ed5c4-183">Развертывание Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="ed5c4-183">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="ed5c4-184">Настройка консоли для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="ed5c4-184">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="ed5c4-185">Управление Системами комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="ed5c4-185">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)