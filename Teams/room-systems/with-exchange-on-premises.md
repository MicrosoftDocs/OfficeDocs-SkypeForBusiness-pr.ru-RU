---
title: Развертывание комнаты Microsoft Teams в локальной среде Exchange
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams в гибридной среде с локальным сервером Exchange.
ms.openlocfilehash: 3dd749e14acabae40da444894dfb89aea97f9e38
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774971"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="529b5-103">Развертывание комнаты Microsoft Teams в локальной среде Exchange</span><span class="sxs-lookup"><span data-stu-id="529b5-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="529b5-104">В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams в гибридной среде с Exchange для локальных и Microsoft Teams или Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="529b5-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="529b5-105">Если в вашей организации есть смесь служб, а некоторые размещены в локальной сети, а некоторые — в Интернете, ваша конфигурация будет зависеть от того, где размещена каждая служба.</span><span class="sxs-lookup"><span data-stu-id="529b5-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="529b5-106">В этой статье рассказывается о гибридных развертываниях комнат Microsoft Teams с размещенным на локальном сервере Exchange.</span><span class="sxs-lookup"><span data-stu-id="529b5-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="529b5-107">Так как в этом типе развертывания существует множество различных вариантов, невозможно предоставить подробные инструкции для всех.</span><span class="sxs-lookup"><span data-stu-id="529b5-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="529b5-108">Для многих конфигураций будет работать следующий процесс.</span><span class="sxs-lookup"><span data-stu-id="529b5-108">The following process will work for many configurations.</span></span> <span data-ttu-id="529b5-109">Если вы не можете выполнить процесс настройки, мы рекомендуем использовать Windows PowerShell, чтобы получить тот же самый конечный результат, который вы описывали здесь, и для других вариантов развертывания.</span><span class="sxs-lookup"><span data-stu-id="529b5-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="529b5-110">Корпорация Майкрософт предоставляет [скиперумпровисионингскрипт. ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или проверить имеющиеся учетные записи ресурсов, чтобы их можно было превратить в совместимые учетные записи Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="529b5-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="529b5-111">Если вы предпочитаете, выполните указанные ниже действия, чтобы настроить учетные записи, которые будут использоваться на устройстве комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="529b5-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="529b5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="529b5-112">Requirements</span></span>

<span data-ttu-id="529b5-113">Перед развертыванием комнат Microsoft Teams на локальном сервере Exchange убедитесь, что вы удовлетворены требованиями.</span><span class="sxs-lookup"><span data-stu-id="529b5-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="529b5-114">Дополнительные сведения можно найти в разделе [требования к комнатам Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="529b5-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="529b5-115">При развертывании комнат Microsoft Teams на локальном сервере Exchange вы будете использовать средства администрирования Active Directory для добавления адреса электронной почты для локальной учетной записи домена.</span><span class="sxs-lookup"><span data-stu-id="529b5-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="529b5-116">Эта учетная запись будет синхронизирована с Office 365.</span><span class="sxs-lookup"><span data-stu-id="529b5-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="529b5-117">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="529b5-117">You will need to:</span></span>
  
- <span data-ttu-id="529b5-118">Создайте учетную запись и синхронизируйте ее с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="529b5-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="529b5-119">Включите удаленный почтовый ящик и задайте его свойства.</span><span class="sxs-lookup"><span data-stu-id="529b5-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="529b5-120">Назначение лицензии на Office 365.</span><span class="sxs-lookup"><span data-stu-id="529b5-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="529b5-121">Включите учетную запись устройства в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="529b5-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="529b5-122">Для включения учетной записи устройства в вашей среде должны выполняться указанные ниже предварительные требования.</span><span class="sxs-lookup"><span data-stu-id="529b5-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="529b5-123">Вам потребуется Skype для бизнеса Online (план 2) или более позднюю версию в плане Office 365.</span><span class="sxs-lookup"><span data-stu-id="529b5-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="529b5-124">План должен поддерживать функции конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="529b5-124">The plan needs to support conferencing capability.</span></span>
  
  - - <span data-ttu-id="529b5-125">Если вам нужна Корпоративная голосовая связь (PSTN-телефония) с помощью поставщиков услуг телефонии для комнат Microsoft Teams, которым нужен Skype для бизнеса Online (план 3).</span><span class="sxs-lookup"><span data-stu-id="529b5-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - - <span data-ttu-id="529b5-126">Ваши пользователи клиента должны иметь почтовые ящики Exchange.</span><span class="sxs-lookup"><span data-stu-id="529b5-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - - <span data-ttu-id="529b5-127">Для вашей учетной записи Microsoft Team комнат требуется лицензия Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3), но для нее не требуется лицензия на Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="529b5-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="529b5-128">Назначьте лицензию Skype для бизнеса Server учетной записи комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="529b5-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="529b5-129">Создание учетной записи и ее синхронизация с Active Directory</span><span class="sxs-lookup"><span data-stu-id="529b5-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="529b5-130">В средстве " **Пользователи и компьютеры Active Directory** " щелкните правой кнопкой мыши папку или подразделение, в котором будут создаваться учетные записи Microsoft Teams, и нажмите кнопку " **создать**", а затем выберите пункт " **пользователь**".</span><span class="sxs-lookup"><span data-stu-id="529b5-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="529b5-p107">Введите отображаемое имя из предыдущего командлета в поле **Полное имя**, а затем псевдоним в поле **Имя входа пользователя**. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="529b5-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="529b5-p108">Введите пароль учетной записи. Подтвердите пароль. Убедитесь, что выбран только параметр **Срок действия пароля не ограничен**.</span><span class="sxs-lookup"><span data-stu-id="529b5-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="529b5-136">Выбор **срока действия пароля неограничен** — требование для сервера Skype для бизнеса в комнатах Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="529b5-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="529b5-137">В некоторых случаях пароли с неограниченным сроком действия могут быть запрещены правилами домена.</span><span class="sxs-lookup"><span data-stu-id="529b5-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="529b5-138">Если это так, вам потребуется создать исключение для каждой учетной записи устройства Microsoft Teams в комнатах.</span><span class="sxs-lookup"><span data-stu-id="529b5-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="529b5-139">После создания учетной записи выполните синхронизацию каталогов.</span><span class="sxs-lookup"><span data-stu-id="529b5-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="529b5-140">По завершении перейдите на страницу пользователи в центре администрирования Microsoft 365 и убедитесь, что учетная запись, созданная в предыдущих шагах, объединена в Интернет.</span><span class="sxs-lookup"><span data-stu-id="529b5-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="529b5-141">Включите удаленный почтовый ящик и задайте его свойства.</span><span class="sxs-lookup"><span data-stu-id="529b5-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="529b5-142">[Откройте консоль управления Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) или [подключитесь к серверу Exchange с помощью удаленной оболочки PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span><span class="sxs-lookup"><span data-stu-id="529b5-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="529b5-143">В Exchange PowerShell можно создать почтовый ящик для учетной записи (почтовый ящик — включение учетной записи), выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="529b5-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="529b5-144">Подробные сведения о синтаксисе и параметрах можно найти в разделе [Включение и использование почтового ящика](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="529b5-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="529b5-145">В Exchange PowerShell настройте следующие параметры в почтовом ящике комнаты, чтобы улучшить процесс собрания:</span><span class="sxs-lookup"><span data-stu-id="529b5-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="529b5-146">Аутоматепроцессинг: с помощью автопринятия (организаторов собраний) получайте решение о резервировании комнаты непосредственно без вмешательства человека: бесплатное = принять; занято = отклонить.)</span><span class="sxs-lookup"><span data-stu-id="529b5-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="529b5-147">Аддорганизертосубжект: $false (Организатор собрания не добавляется в тему приглашения на собрание.)</span><span class="sxs-lookup"><span data-stu-id="529b5-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="529b5-148">Делетекомментс: $false (Храните текст в тексте сообщения для входящих приглашений на собрания.)</span><span class="sxs-lookup"><span data-stu-id="529b5-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="529b5-149">Делетесубжект: $false (сохранить тему приглашений на входящие собрания).</span><span class="sxs-lookup"><span data-stu-id="529b5-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="529b5-150">Ремовеприватепроперти: $false (гарантируется, что частный флаг, отправленный организатором собрания в исходном приглашении на собрание, будет установлен.)</span><span class="sxs-lookup"><span data-stu-id="529b5-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="529b5-151">Аддаддитионалреспонсе: $true (текст, указанный в параметре Аддитионалреспонсе, добавляется в приглашения на собрание.)</span><span class="sxs-lookup"><span data-stu-id="529b5-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="529b5-152">Аддитионалреспонсе: "это комната для собраний Skype!"</span><span class="sxs-lookup"><span data-stu-id="529b5-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="529b5-153">(Дополнительный текст, добавляемый в приглашение на собрание.)</span><span class="sxs-lookup"><span data-stu-id="529b5-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="529b5-154">Этот пример настраивает эти параметры в почтовом ящике комнаты с именем Project-Рижел-01.</span><span class="sxs-lookup"><span data-stu-id="529b5-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="529b5-155">Подробные сведения о синтаксисе и параметрах можно найти в разделе [Set-календарпроцессинг](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="529b5-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="529b5-156">Назначение лицензии Office 365</span><span class="sxs-lookup"><span data-stu-id="529b5-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="529b5-157">Подключитесь к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="529b5-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="529b5-158">Подробнее об Active Directory можно узнать в [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="529b5-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="529b5-159">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="529b5-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="529b5-160">Учетная запись устройства должна иметь действительную лицензию на Office 365, или Exchange и Microsoft Teams не будут работать.</span><span class="sxs-lookup"><span data-stu-id="529b5-160">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="529b5-161">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="529b5-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="529b5-162">Вы можете использовать`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="529b5-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="529b5-163">Получение списка доступных SKU.</span><span class="sxs-lookup"><span data-stu-id="529b5-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="529b5-164">Затем вы можете добавить лицензию с помощью`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="529b5-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="529b5-165">Командлет.</span><span class="sxs-lookup"><span data-stu-id="529b5-165">cmdlet.</span></span> <span data-ttu-id="529b5-166">В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="529b5-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="529b5-167">Подробные инструкции приведены в разделе [Назначение лицензий учетным записям пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="529b5-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="529b5-168">Включение учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="529b5-168">Enable the device account</span></span>

<span data-ttu-id="529b5-169">Skype для бизнеса Online PowerShell используется для управления службами как в Microsoft Teams, так и в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="529b5-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="529b5-170">Создайте удаленный сеанс Windows PowerShell на компьютере, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="529b5-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="529b5-171">Получите SIP Address для учетной записи:</span><span class="sxs-lookup"><span data-stu-id="529b5-171">Obtain SIP address of the account:</span></span>

  ``` Powershell
   $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
   ```

3. <span data-ttu-id="529b5-172">Чтобы включить учетную запись комнаты Microsoft Teams, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="529b5-172">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="529b5-173">Если вы не знаете, какое значение использовать для параметра Регистрарпул в вашей среде, вы можете получить значение от существующего пользователя с помощью этой команды:</span><span class="sxs-lookup"><span data-stu-id="529b5-173">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="529b5-174">Назначение лицензии для учетной записи комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="529b5-174">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="529b5-175">Войдите в систему как администратор клиента, откройте административный портал Office 365 и щелкните Приложение администратор.</span><span class="sxs-lookup"><span data-stu-id="529b5-175">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="529b5-176">Выберите **Пользователи и группы**, после чего щелкните **Добавление пользователей, сброс паролей и другие действия**.</span><span class="sxs-lookup"><span data-stu-id="529b5-176">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="529b5-177">Щелкните учетную запись комнаты Microsoft Teams, а затем щелкните значок пера, чтобы изменить данные учетной записи.</span><span class="sxs-lookup"><span data-stu-id="529b5-177">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="529b5-178">Щелкните **Лицензии**.</span><span class="sxs-lookup"><span data-stu-id="529b5-178">Click **Licenses**.</span></span>
5. <span data-ttu-id="529b5-179">В разделе **Назначение лицензий** выберите Skype для бизнеса (план 2) или Skype для бизнеса (план 3), в зависимости от требований к лицензированию и Корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="529b5-179">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="529b5-180">Если вы хотите использовать корпоративную голосовую связь в комнатах Microsoft Teams, вам придется использовать лицензию на план 3.</span><span class="sxs-lookup"><span data-stu-id="529b5-180">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="529b5-181">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="529b5-181">Click **Save**.</span></span>

<span data-ttu-id="529b5-182">Для проверки подлинности вы можете использовать любой клиент для входа в эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="529b5-182">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="529b5-183">См. также</span><span class="sxs-lookup"><span data-stu-id="529b5-183">See also</span></span>

[<span data-ttu-id="529b5-184">Настройка учетных записей для комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="529b5-184">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="529b5-185">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="529b5-185">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="529b5-186">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="529b5-186">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="529b5-187">Настройка консоли Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="529b5-187">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="529b5-188">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="529b5-188">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
