---
title: Развертывание групп Майкрософт для предоставления сервера-концентратора
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Настройка параметров администрирования для групп Майкрософт для сервера-концентратора поверхности.
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192182"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="46d04-103">Развертывание групп Майкрософт для предоставления сервера-концентратора</span><span class="sxs-lookup"><span data-stu-id="46d04-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="46d04-104">Перед развертыванием группами Майкрософт для сервера-концентратора Microsoft Surface убедитесь, что удовлетворены оборудования, операционной системы и другие требования.</span><span class="sxs-lookup"><span data-stu-id="46d04-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="46d04-105">Дополнительные сведения можно найти в [руководстве администратора сервера-концентратора Microsoft Surface](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="46d04-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="46d04-106">Настройка учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="46d04-106">Set up user accounts</span></span>
 
<span data-ttu-id="46d04-107">Чтобы настроить учетные записи пользователей, которые могут использоваться с группами для сервера-концентратора поверхность, создайте учетную запись устройства, как и для поддержки Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="46d04-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="46d04-108">Учетная запись устройства должен иметь многофакторной проверки подлинности, этот параметр отключен (для включения автоматического входа) для следующие зависимые службы групп в Office 365:</span><span class="sxs-lookup"><span data-stu-id="46d04-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="46d04-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="46d04-109">Exchange</span></span> 
- <span data-ttu-id="46d04-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="46d04-110">SharePoint</span></span> 
- <span data-ttu-id="46d04-111">Приложения Office</span><span class="sxs-lookup"><span data-stu-id="46d04-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="46d04-112">Добавление учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="46d04-112">Add a device account</span></span> 

<span data-ttu-id="46d04-113">1\.</span><span class="sxs-lookup"><span data-stu-id="46d04-113">1\.</span></span> <span data-ttu-id="46d04-114">Для запуска удаленного сеанса Windows PowerShell на ПК и подключитесь к Exchange.</span><span class="sxs-lookup"><span data-stu-id="46d04-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="46d04-115">Убедитесь, что имеется правильные разрешения, установленные для запуска связанного командлеты.</span><span class="sxs-lookup"><span data-stu-id="46d04-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="46d04-116">Ниже приведен ряд примеров командлетов, которые можно использовать и изменять в своей среде.</span><span class="sxs-lookup"><span data-stu-id="46d04-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="46d04-117">2\.</span><span class="sxs-lookup"><span data-stu-id="46d04-117">2\.</span></span> <span data-ttu-id="46d04-118">После установления сеанса можно создать новый почтовый ящик и активировать его как RoomMailboxAccount или изменить настройки существующего почтового ящика комнаты.</span><span class="sxs-lookup"><span data-stu-id="46d04-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="46d04-119">Это позволит учетной записи для проверки подлинности для группы.</span><span class="sxs-lookup"><span data-stu-id="46d04-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="46d04-120">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="46d04-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="46d04-121">Создание нового почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="46d04-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="46d04-122">3\.</span><span class="sxs-lookup"><span data-stu-id="46d04-122">3\.</span></span> <span data-ttu-id="46d04-123">Чтобы оптимизировать интерфейс собрания, можно настроить различные свойства Exchange для учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="46d04-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="46d04-124">Описание необходимых настроек приводится в разделе "Свойства Exchange".</span><span class="sxs-lookup"><span data-stu-id="46d04-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="46d04-125">4\.</span><span class="sxs-lookup"><span data-stu-id="46d04-125">4\.</span></span> <span data-ttu-id="46d04-126">Для применения некоторых настроек учетной записи потребуется подключиться к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="46d04-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="46d04-127">Чтобы подключиться к Azure AD, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="46d04-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="46d04-128">5\.</span><span class="sxs-lookup"><span data-stu-id="46d04-128">5\.</span></span> <span data-ttu-id="46d04-129">	Чтобы использовать пароль с неограниченным сроком действия, выполните командлет Set-MsolUser с параметром PasswordNeverExpires.  </span><span class="sxs-lookup"><span data-stu-id="46d04-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="46d04-130">Вы также можете задать номер телефона для комнаты следующим образом.</span><span class="sxs-lookup"><span data-stu-id="46d04-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="46d04-131">6\.</span><span class="sxs-lookup"><span data-stu-id="46d04-131">6\.</span></span> <span data-ttu-id="46d04-132">Учетная запись устройства должна быть действительной лицензии Office 365 или Exchange и Скайп для бизнеса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="46d04-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="46d04-133">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="46d04-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="46d04-134">Get-MsolAccountSku можно использовать для получения списка доступных номеров SKU для клиента Office 365 следующим образом:</span><span class="sxs-lookup"><span data-stu-id="46d04-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="46d04-p109">Далее можно добавить лицензию с помощью командлета Set-MsolUserLicense. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="46d04-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="46d04-137">7\.</span><span class="sxs-lookup"><span data-stu-id="46d04-137">7\.</span></span> <span data-ttu-id="46d04-138">Затем необходимо включить запись устройства с группами для сервера-концентратора поверхности.</span><span class="sxs-lookup"><span data-stu-id="46d04-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="46d04-139">Убедитесь, что в вашей среде соответствует требованиям, определенным в [руководстве администратора Microsoft Surface сервера-концентратора](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="46d04-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="46d04-140">Для запуска удаленного сеанса Windows PowerShell следующим образом (не забудьте установить Скайп для компонентов Business Online PowerShell):</span><span class="sxs-lookup"><span data-stu-id="46d04-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="46d04-141">Затем включите ваших команд для сервера-концентратора поверхность учетной записи, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="46d04-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="46d04-142">Получите сведения о RegistrarPool из учетной записи пользователя, программа установки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="46d04-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="46d04-143">Новые учетные записи пользователей не могут быть созданы на тот же самый пул регистратора, как существующие учетные записи пользователей в клиентов.</span><span class="sxs-lookup"><span data-stu-id="46d04-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="46d04-144">Команды выше не позволит ошибок в учетной записи программы установки из-за этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="46d04-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="46d04-145">После выполнения предыдущего действия, чтобы включить группы для учетной записи контактной сервера-концентратора, им необходимо назначить лицензия на устройство v2 поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="46d04-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="46d04-146">Использование портала администрирования Office 365, назначение групп для сервера-концентратора поверхность лицензии на устройство.</span><span class="sxs-lookup"><span data-stu-id="46d04-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="46d04-147">Назначение лицензии для учетной записи</span><span class="sxs-lookup"><span data-stu-id="46d04-147">Assign a license to the account</span></span>

1. <span data-ttu-id="46d04-148">Войдите в систему как администратор клиента, откройте Центр администрирования Office 365 и щелкните приложения администрирования.</span><span class="sxs-lookup"><span data-stu-id="46d04-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="46d04-149">Щелкните **пользователи и группы**и нажмите кнопку **Добавить пользователей, сброс паролей и многое другое**.</span><span class="sxs-lookup"><span data-stu-id="46d04-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="46d04-150">Выберите группы для учетной записи контактной сервера-концентратора и щелкните или нажмите значок перо, который означает, что изменение.</span><span class="sxs-lookup"><span data-stu-id="46d04-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="46d04-151">Щелкните параметр **лицензий** .</span><span class="sxs-lookup"><span data-stu-id="46d04-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="46d04-152">В разделе **Назначение лицензий** необходимо выбрать план, в зависимости от вашей лицензирования.</span><span class="sxs-lookup"><span data-stu-id="46d04-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="46d04-153">Чтобы завершить задачу, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="46d04-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="46d04-154">Установка группы для предоставления концентратора из хранилища Microsoft</span><span class="sxs-lookup"><span data-stu-id="46d04-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="46d04-155">Эти инструкции: текущий обходные пути для установки группы для сервера-концентратора поверхность из хранилища Microsoft.</span><span class="sxs-lookup"><span data-stu-id="46d04-155">These instructions include the current workarounds for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="46d04-156">Запустите магазина Windows:</span><span class="sxs-lookup"><span data-stu-id="46d04-156">Start the Windows Store:</span></span><br>
   <span data-ttu-id="46d04-157">а.</span><span class="sxs-lookup"><span data-stu-id="46d04-157">a.</span></span> <span data-ttu-id="46d04-158">Коснитесь кнопки **Пуск** > **все приложения** > **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="46d04-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="46d04-159">б.</span><span class="sxs-lookup"><span data-stu-id="46d04-159">b.</span></span> <span data-ttu-id="46d04-160">Коснитесь **устройства сервера-концентратора поверхность учетная запись, управление**.</span><span class="sxs-lookup"><span data-stu-id="46d04-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="46d04-161">в.</span><span class="sxs-lookup"><span data-stu-id="46d04-161">c.</span></span> <span data-ttu-id="46d04-162">В левой части перейдите на вкладку **приложений и компонентов** .</span><span class="sxs-lookup"><span data-stu-id="46d04-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="46d04-163">г.</span><span class="sxs-lookup"><span data-stu-id="46d04-163">d.</span></span> <span data-ttu-id="46d04-164">В правой части окна нажмите кнопку **Открыть хранилище** .</span><span class="sxs-lookup"><span data-stu-id="46d04-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="46d04-165">Из магазина Microsoft поиск *Групп Майкрософт*.</span><span class="sxs-lookup"><span data-stu-id="46d04-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="46d04-166">Отображается **Группами Майкрософт для сервера-концентратора поверхности (Предварительная версия)** .</span><span class="sxs-lookup"><span data-stu-id="46d04-166">The **Microsoft Teams for Surface Hub (Preview)** will be displayed.</span></span> <span data-ttu-id="46d04-167">Нажмите кнопку **получить приложение** для установки.</span><span class="sxs-lookup"><span data-stu-id="46d04-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="46d04-168">После завершения установки перезапустите сервер-концентратор поверхности.</span><span class="sxs-lookup"><span data-stu-id="46d04-168">When the installation is complete, restart the Surface Hub.</span></span> 
4. <span data-ttu-id="46d04-169">После перезагрузки сервера-концентратора поверхность, должна появиться возможность запуска приложения команды из меню " **Пуск** " и присоединиться к собранию из календаря.</span><span class="sxs-lookup"><span data-stu-id="46d04-169">After the Surface Hub restarts, you should be able to start the Teams app from the **Start** menu and join a meeting from the calendar.</span></span> 

## <a name="make-teams-the-default-vtc-application"></a><span data-ttu-id="46d04-170">Выполнение команды VTC приложения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="46d04-170">Make Teams the default VTC application</span></span>

<span data-ttu-id="46d04-171">Группы можно задать до быть приложения по умолчанию VTC вместо Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="46d04-171">Teams can be set up to be the default VTC application instead of Skype for Business.</span></span> <span data-ttu-id="46d04-172">Политики управления Mobile Device (MDM) необходимо применить к устройству поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="46d04-172">A Mobile Device Management (MDM) policy needs to be applied to the Surface Hub device.</span></span> 
 
<span data-ttu-id="46d04-173">Существует два варианта для настройки политик MDM:</span><span class="sxs-lookup"><span data-stu-id="46d04-173">There are two options for configuring MDM policies:</span></span> 

- <span data-ttu-id="46d04-174">При наличии политику, настроенную, добавьте его в приложении управления устройства.</span><span class="sxs-lookup"><span data-stu-id="46d04-174">If you have a policy configured, add it via the Device management app.</span></span> 
- <span data-ttu-id="46d04-175">Если удаленный политику, настроенную отсутствует, у нас есть подготовленных пакетный файл, который можно загрузить на USB-ключ.</span><span class="sxs-lookup"><span data-stu-id="46d04-175">If you do not have a remote policy configured, we have a provisioned package file that you can load onto an USB key.</span></span>

### <a name="device-management-configuration"></a><span data-ttu-id="46d04-176">Настройка управления устройства</span><span class="sxs-lookup"><span data-stu-id="46d04-176">Device management configuration</span></span>

<span data-ttu-id="46d04-177">Ниже приведен пример добавления политику MDM, настроенных в центре сертификации MDM.</span><span class="sxs-lookup"><span data-stu-id="46d04-177">The following is an example of adding an MDM policy configured from a central MDM authority.</span></span> <span data-ttu-id="46d04-178">Если пользователь находится в корпоративной сети, можно использовать следующие инструкции подробное содержание, включая учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="46d04-178">If you are on the corporate network, you can use the following instructions verbatim, including user account.</span></span> 
 
1. <span data-ttu-id="46d04-179">В разделе **Управление устройствами** коснитесь **+**.</span><span class="sxs-lookup"><span data-stu-id="46d04-179">Under the **Device Management** section, tap **+**.</span></span><br>
   <span data-ttu-id="46d04-180">Откроется диалоговое окно **подключиться к работе или школы** .</span><span class="sxs-lookup"><span data-stu-id="46d04-180">The **Connect to work or school** dialog box will open.</span></span> 
2. <span data-ttu-id="46d04-181">Введите политики адресов электронной почты и пароль в ответ на запрос.</span><span class="sxs-lookup"><span data-stu-id="46d04-181">Enter the policy e-mail address and password when prompted.</span></span><br>
   <span data-ttu-id="46d04-182">**Примечание:**  Содержит ошибку в операционной системе, которая не автоматическое обновление пользовательского интерфейса после ввода учетной записи управления устройства.</span><span class="sxs-lookup"><span data-stu-id="46d04-182">**NOTE:**  There's a bug in the OS that doesn't automatically refresh the UI after you've entered your device management account.</span></span> <span data-ttu-id="46d04-183">Необходимо закрыть и повторно открыть параметры для просмотра учетной записи из списка.</span><span class="sxs-lookup"><span data-stu-id="46d04-183">You'll need to close and re-open settings in order to see the account listed.</span></span> 
3. <span data-ttu-id="46d04-184">Несколько минут для параметров политики MDM для синхронизации с задержкой. Если вы хотите, чтобы для принудительной синхронизации, нажмите кнопку «» **MDM учетной записи** и нажмите кнопку « **сведения** ».</span><span class="sxs-lookup"><span data-stu-id="46d04-184">It'll take a few minutes for the MDM policy settings to sync. If you want to force a sync, tap the **MDM account** button, and then tap the **Info** button.</span></span> <span data-ttu-id="46d04-185">Откроется диалоговое окно сведения, где затем коснитесь **синхронизации**.</span><span class="sxs-lookup"><span data-stu-id="46d04-185">This will bring up the Info window where you can then tap **Sync**.</span></span> 
4. <span data-ttu-id="46d04-186">Чтобы убедиться в том, что у вас есть, что вам нужно, вы можете проверить реестра.</span><span class="sxs-lookup"><span data-stu-id="46d04-186">To verify that you have what you need, you can check the registry.</span></span> <span data-ttu-id="46d04-187">Вы должны увидеть два ключа в разделе **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**.</span><span class="sxs-lookup"><span data-stu-id="46d04-187">You should see two keys under **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**.</span></span> <br><br>
   <span data-ttu-id="46d04-188">Значение DWORD **VtcAppMeetingHandlingMode** указывает, что команды приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="46d04-188">The **VtcAppMeetingHandlingMode** DWORD value indicates that Teams is the default app.</span></span> <span data-ttu-id="46d04-189">Распознаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="46d04-189">The following values are recognized.</span></span> <br><br>
    |<span data-ttu-id="46d04-190">Число</span><span class="sxs-lookup"><span data-stu-id="46d04-190">Number</span></span> | <span data-ttu-id="46d04-191">Значение</span><span class="sxs-lookup"><span data-stu-id="46d04-191">Value</span></span>   |
    |-------|---------|
    |<span data-ttu-id="46d04-192">0</span><span class="sxs-lookup"><span data-stu-id="46d04-192">0</span></span>      | <span data-ttu-id="46d04-193">SkypePreferred</span><span class="sxs-lookup"><span data-stu-id="46d04-193">SkypePreferred</span></span>            |
    |<span data-ttu-id="46d04-194">1</span><span class="sxs-lookup"><span data-stu-id="46d04-194">1</span></span>      | <span data-ttu-id="46d04-195">VtcPreferred (группы)</span><span class="sxs-lookup"><span data-stu-id="46d04-195">VtcPreferred (Teams)</span></span>      |
    |<span data-ttu-id="46d04-196">2</span><span class="sxs-lookup"><span data-stu-id="46d04-196">2</span></span>      | <span data-ttu-id="46d04-197">VtcExclusive (группы)</span><span class="sxs-lookup"><span data-stu-id="46d04-197">VtcExclusive (Teams only)</span></span> |

    <span data-ttu-id="46d04-198">**VtcCallAppPackageId** — это имя установленного пакета группами.</span><span class="sxs-lookup"><span data-stu-id="46d04-198">The **VtcCallAppPackageId** is the name of the installed Teams package.</span></span> <span data-ttu-id="46d04-199">Если это не отображается, убедитесь, что вы установили пакет групп и требуется синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="46d04-199">If this doesn't show up, make sure you've installed the Teams package, and re-sync.</span></span> 
 
### <a name="configure-mdm-via-usb-key"></a><span data-ttu-id="46d04-200">Настройка MDM с помощью USB-ключ</span><span class="sxs-lookup"><span data-stu-id="46d04-200">Configure MDM via USB key</span></span> 
 
<span data-ttu-id="46d04-201">Пакеты можно найти на этой [странице загрузки](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="46d04-201">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="46d04-202">Выберите один для пакета, который планируется установить и скопируйте его на USB.</span><span class="sxs-lookup"><span data-stu-id="46d04-202">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="46d04-203">Правильный .ppkg файл, используемый зависит от команды пакета, который будет установлен из хранилища и политики, чтобы применить (Скайп исключительных, Скайп предпочитаемое, предпочтительнее, группами монопольной группы).</span><span class="sxs-lookup"><span data-stu-id="46d04-203">The correct .ppkg file to use depends on the Teams package that has been installed from the store, and the policy you'd like to apply (Skype exclusive, Skype preferred, Teams preferred, Teams exclusive).</span></span> 
 
1. <span data-ttu-id="46d04-204">Присоедините USB-ключ устройство поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="46d04-204">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="46d04-205">Откройте **Параметры** приложения на устройстве поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="46d04-205">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="46d04-206">Откройте **Управление учетными записями устройства контактной сервера-концентратора**.</span><span class="sxs-lookup"><span data-stu-id="46d04-206">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="46d04-207">Откройте **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="46d04-207">Open **Device Management**.</span></span> 
5. <span data-ttu-id="46d04-208">Нажмите кнопку **Добавить или удалить подготовки пакета**.</span><span class="sxs-lookup"><span data-stu-id="46d04-208">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="46d04-209">Нажмите кнопку **добавить пакет**.</span><span class="sxs-lookup"><span data-stu-id="46d04-209">Click **Add Package**.</span></span>
7. <span data-ttu-id="46d04-210">В раскрывающемся меню выберите параметр **Съемный носитель** .</span><span class="sxs-lookup"><span data-stu-id="46d04-210">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="46d04-211">Добавить **Allowbuildspreview.ppkg**и выберите сервер-концентратор поверхность пакета, который вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="46d04-211">Add the **Allowbuildspreview.ppkg**, and then select the Surface Hub package you want to add.</span></span> 
9. <span data-ttu-id="46d04-212">Перезагрузите устройство поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="46d04-212">Restart the Surface Hub device.</span></span> 

> [!NOTE]
> <span data-ttu-id="46d04-213">Если ваше устройство или устройствах вашей организации не в настоящее время частью программы изнутри Windows и находятся в странах, затрагиваемых с нормы защиты общие данные (GDPR) (или вручную были изменены параметры телеметрии для базовой), необходимо повторно проверить что были разрешены полный телеметрии перед присоединением изнутри программы.</span><span class="sxs-lookup"><span data-stu-id="46d04-213">If your device or your organization's devices are not currently part of the Windows Insider Program and you are in countries covered by General Data Protection Regulation (GDPR) (or you have manually changed your telemetry settings to Basic), then you must re-check that you have permitted full telemetry before you join the Insider Program.</span></span> <span data-ttu-id="46d04-214">GDPR изменить поведение по умолчанию сервер-концентратор поверхность устройств в ЕС Установка телеметрии для базовой.</span><span class="sxs-lookup"><span data-stu-id="46d04-214">GDPR changed the default behavior of Surface Hub devices in the EU to set telemetry to Basic.</span></span>