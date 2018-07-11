---
title: Развертывание групп Майкрософт для предоставления сервера-концентратора
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2018
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
ms.openlocfilehash: cfd9e5fd267de180907c2ea41c53541c08ff28b7
ms.sourcegitcommit: 8c3dcfc564c489f4d33bd5f391a5a66b99ded07e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "20266940"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="057b4-103">Развертывание групп Майкрософт для предоставления сервера-концентратора</span><span class="sxs-lookup"><span data-stu-id="057b4-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="057b4-104">Перед развертыванием группами Майкрософт для сервера-концентратора Microsoft Surface убедитесь, что удовлетворены оборудования, операционной системы и другие требования.</span><span class="sxs-lookup"><span data-stu-id="057b4-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="057b4-105">Дополнительные сведения можно найти в [руководстве администратора сервера-концентратора Microsoft Surface](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="057b4-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="057b4-106">Настройка учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="057b4-106">Set up user accounts</span></span>
 
<span data-ttu-id="057b4-107">Чтобы настроить учетные записи пользователей, которые могут использоваться с группами для сервера-концентратора поверхность, создайте учетную запись устройства, как и для поддержки Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="057b4-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="057b4-108">Учетная запись устройства должен иметь многофакторной проверки подлинности, этот параметр отключен (для включения автоматического входа) для следующие зависимые службы групп в Office 365:</span><span class="sxs-lookup"><span data-stu-id="057b4-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="057b4-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="057b4-109">Exchange</span></span> 
- <span data-ttu-id="057b4-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="057b4-110">SharePoint</span></span> 
- <span data-ttu-id="057b4-111">Приложения Office</span><span class="sxs-lookup"><span data-stu-id="057b4-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="057b4-112">Добавление учетной записи устройства</span><span class="sxs-lookup"><span data-stu-id="057b4-112">Add a device account</span></span> 

<span data-ttu-id="057b4-113">1\.</span><span class="sxs-lookup"><span data-stu-id="057b4-113">1\.</span></span> <span data-ttu-id="057b4-114">Для запуска удаленного сеанса Windows PowerShell на ПК и подключитесь к Exchange.</span><span class="sxs-lookup"><span data-stu-id="057b4-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="057b4-115">Убедитесь, что имеется правильные разрешения, установленные для запуска связанного командлеты.</span><span class="sxs-lookup"><span data-stu-id="057b4-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="057b4-116">Ниже приведен ряд примеров командлетов, которые можно использовать и изменять в своей среде.</span><span class="sxs-lookup"><span data-stu-id="057b4-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="057b4-117">2\.</span><span class="sxs-lookup"><span data-stu-id="057b4-117">2\.</span></span> <span data-ttu-id="057b4-118">После установления сеанса можно создать новый почтовый ящик и активировать его как RoomMailboxAccount или изменить настройки существующего почтового ящика комнаты.</span><span class="sxs-lookup"><span data-stu-id="057b4-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="057b4-119">Это позволит учетной записи для проверки подлинности для группы.</span><span class="sxs-lookup"><span data-stu-id="057b4-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="057b4-120">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="057b4-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="057b4-121">Создание нового почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="057b4-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="057b4-122">3\.</span><span class="sxs-lookup"><span data-stu-id="057b4-122">3\.</span></span> <span data-ttu-id="057b4-123">Чтобы оптимизировать интерфейс собрания, можно настроить различные свойства Exchange для учетной записи устройства.</span><span class="sxs-lookup"><span data-stu-id="057b4-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="057b4-124">Описание необходимых настроек приводится в разделе "Свойства Exchange".</span><span class="sxs-lookup"><span data-stu-id="057b4-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="057b4-125">4\.</span><span class="sxs-lookup"><span data-stu-id="057b4-125">4\.</span></span> <span data-ttu-id="057b4-126">Для применения некоторых настроек учетной записи потребуется подключиться к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="057b4-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="057b4-127">Чтобы подключиться к Azure AD, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="057b4-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="057b4-128">5\.</span><span class="sxs-lookup"><span data-stu-id="057b4-128">5\.</span></span> <span data-ttu-id="057b4-129">	Чтобы использовать пароль с неограниченным сроком действия, выполните командлет Set-MsolUser с параметром PasswordNeverExpires.  </span><span class="sxs-lookup"><span data-stu-id="057b4-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="057b4-130">Вы также можете задать номер телефона для комнаты следующим образом.</span><span class="sxs-lookup"><span data-stu-id="057b4-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="057b4-131">6\.</span><span class="sxs-lookup"><span data-stu-id="057b4-131">6\.</span></span> <span data-ttu-id="057b4-132">Учетная запись устройства должна быть действительной лицензии Office 365 или Exchange и Скайп для бизнеса не будут работать.</span><span class="sxs-lookup"><span data-stu-id="057b4-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="057b4-133">При наличии лицензии вам необходимо назначить учетной записи устройства место использования, которое определяет, какие номера SKU лицензий будут доступны вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="057b4-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="057b4-134">Get-MsolAccountSku можно использовать для получения списка доступных номеров SKU для клиента Office 365 следующим образом:</span><span class="sxs-lookup"><span data-stu-id="057b4-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="057b4-p109">Далее можно добавить лицензию с помощью командлета Set-MsolUserLicense. В этом случае будет отображаться код SKU $strLicense (например, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="057b4-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="057b4-137">7\.</span><span class="sxs-lookup"><span data-stu-id="057b4-137">7\.</span></span> <span data-ttu-id="057b4-138">Затем необходимо включить запись устройства с группами для сервера-концентратора поверхности.</span><span class="sxs-lookup"><span data-stu-id="057b4-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="057b4-139">Убедитесь, что в вашей среде соответствует требованиям, определенным в [руководстве администратора Microsoft Surface сервера-концентратора](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="057b4-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="057b4-140">Для запуска удаленного сеанса Windows PowerShell следующим образом (не забудьте установить Скайп для компонентов Business Online PowerShell):</span><span class="sxs-lookup"><span data-stu-id="057b4-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="057b4-141">Затем включите ваших команд для сервера-концентратора поверхность учетной записи, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="057b4-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="057b4-142">Получите сведения о RegistrarPool из учетной записи пользователя, программа установки, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="057b4-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="057b4-143">Новые учетные записи пользователей не могут быть созданы на тот же самый пул регистратора, как существующие учетные записи пользователей в клиентов.</span><span class="sxs-lookup"><span data-stu-id="057b4-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="057b4-144">Команды выше не позволит ошибок в учетной записи программы установки из-за этой ситуации.</span><span class="sxs-lookup"><span data-stu-id="057b4-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="057b4-145">После выполнения предыдущего действия, чтобы включить группы для учетной записи контактной сервера-концентратора, им необходимо назначить лицензия на устройство v2 поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="057b4-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="057b4-146">Использование портала администрирования Office 365, назначение групп для сервера-концентратора поверхность лицензии на устройство.</span><span class="sxs-lookup"><span data-stu-id="057b4-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="057b4-147">Назначение лицензии для учетной записи</span><span class="sxs-lookup"><span data-stu-id="057b4-147">Assign a license to the account</span></span>

1. <span data-ttu-id="057b4-148">Войдите в систему как администратор клиента, откройте Центр администрирования Office 365 и щелкните приложения администрирования.</span><span class="sxs-lookup"><span data-stu-id="057b4-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="057b4-149">Щелкните **пользователи и группы**и нажмите кнопку **Добавить пользователей, сброс паролей и многое другое**.</span><span class="sxs-lookup"><span data-stu-id="057b4-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="057b4-150">Выберите группы для учетной записи контактной сервера-концентратора и щелкните или нажмите значок перо, который означает, что изменение.</span><span class="sxs-lookup"><span data-stu-id="057b4-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="057b4-151">Щелкните параметр **лицензий** .</span><span class="sxs-lookup"><span data-stu-id="057b4-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="057b4-152">В разделе **Назначение лицензий** необходимо выбрать план, в зависимости от вашей лицензирования.</span><span class="sxs-lookup"><span data-stu-id="057b4-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="057b4-153">Чтобы завершить задачу, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="057b4-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="057b4-154">Установка группы для предоставления концентратора из хранилища Microsoft</span><span class="sxs-lookup"><span data-stu-id="057b4-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="057b4-155">Эти инструкции предназначены для установки групп для сервера-концентратора поверхность из хранилища Microsoft.</span><span class="sxs-lookup"><span data-stu-id="057b4-155">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="057b4-156">Запустите хранилища Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="057b4-156">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="057b4-157">а.</span><span class="sxs-lookup"><span data-stu-id="057b4-157">a.</span></span> <span data-ttu-id="057b4-158">Коснитесь кнопки **Пуск** > **все приложения** > **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="057b4-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="057b4-159">б.</span><span class="sxs-lookup"><span data-stu-id="057b4-159">b.</span></span> <span data-ttu-id="057b4-160">Коснитесь **устройства сервера-концентратора поверхность учетная запись, управление**.</span><span class="sxs-lookup"><span data-stu-id="057b4-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="057b4-161">в.</span><span class="sxs-lookup"><span data-stu-id="057b4-161">c.</span></span> <span data-ttu-id="057b4-162">В левой части перейдите на вкладку **приложений и компонентов** .</span><span class="sxs-lookup"><span data-stu-id="057b4-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="057b4-163">г.</span><span class="sxs-lookup"><span data-stu-id="057b4-163">d.</span></span> <span data-ttu-id="057b4-164">В правой части окна нажмите кнопку **Открыть хранилище** .</span><span class="sxs-lookup"><span data-stu-id="057b4-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="057b4-165">Из магазина Microsoft поиск *Групп Майкрософт*.</span><span class="sxs-lookup"><span data-stu-id="057b4-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="057b4-166">Отображается **Группами Майкрософт для сервера-концентратора поверхности** .</span><span class="sxs-lookup"><span data-stu-id="057b4-166">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="057b4-167">Нажмите кнопку **получить приложение** для установки.</span><span class="sxs-lookup"><span data-stu-id="057b4-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="057b4-168">После завершения установки перезапустите сервер-концентратор поверхности.</span><span class="sxs-lookup"><span data-stu-id="057b4-168">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="057b4-169">Не коснитесь на **Запуск** из магазина страницы.</span><span class="sxs-lookup"><span data-stu-id="057b4-169">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="057b4-170">Создание групп по умолчанию звонков и собраний приложения</span><span class="sxs-lookup"><span data-stu-id="057b4-170">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="057b4-171">Существует два варианта для настройки политики по умолчанию звонков и собраний приложения.</span><span class="sxs-lookup"><span data-stu-id="057b4-171">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="057b4-172">**Вариант 1**: настройте с помощью USB-ключ.</span><span class="sxs-lookup"><span data-stu-id="057b4-172">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="057b4-173">**Вариант 2**: настройка с помощью MDM, такие как InTune.</span><span class="sxs-lookup"><span data-stu-id="057b4-173">**Option 2**: Configure via MDM such as InTune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="057b4-174">Вариант 1: Настройте с помощью USB-ключ</span><span class="sxs-lookup"><span data-stu-id="057b4-174">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="057b4-175">Пакеты можно найти на этой [странице загрузки](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="057b4-175">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="057b4-176">Выберите один для пакета, который планируется установить и скопируйте его на USB.</span><span class="sxs-lookup"><span data-stu-id="057b4-176">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="057b4-177">Правильный .ppkg файл, используемый зависит от приложения политику по умолчанию, которое вы хотите применить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="057b4-177">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="057b4-178">Число</span><span class="sxs-lookup"><span data-stu-id="057b4-178">Number</span></span>  |<span data-ttu-id="057b4-179">Описание</span><span class="sxs-lookup"><span data-stu-id="057b4-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="057b4-180">0</span><span class="sxs-lookup"><span data-stu-id="057b4-180">0</span></span>     | <span data-ttu-id="057b4-181">Предпочитаемый приложения Скайп на начальном экране, доступные команды собраний</span><span class="sxs-lookup"><span data-stu-id="057b4-181">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="057b4-182">1</span><span class="sxs-lookup"><span data-stu-id="057b4-182">1</span></span>     | <span data-ttu-id="057b4-183">Предпочитаемый приложения группы на начальном экране, доступные Скайп собраний</span><span class="sxs-lookup"><span data-stu-id="057b4-183">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="057b4-184">2</span><span class="sxs-lookup"><span data-stu-id="057b4-184">2</span></span>     | <span data-ttu-id="057b4-185">Команды исключительных приложения на начальном экране (недоступно приложение Скайп)</span><span class="sxs-lookup"><span data-stu-id="057b4-185">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="057b4-186">Присоедините USB-ключ устройство поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="057b4-186">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="057b4-187">Откройте **Параметры** приложения на устройстве поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="057b4-187">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="057b4-188">Откройте **Управление учетными записями устройства контактной сервера-концентратора**.</span><span class="sxs-lookup"><span data-stu-id="057b4-188">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="057b4-189">Откройте **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="057b4-189">Open **Device Management**.</span></span> 
5. <span data-ttu-id="057b4-190">Нажмите кнопку **Добавить или удалить подготовки пакета**.</span><span class="sxs-lookup"><span data-stu-id="057b4-190">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="057b4-191">Нажмите кнопку **добавить пакет**.</span><span class="sxs-lookup"><span data-stu-id="057b4-191">Click **Add Package**.</span></span>
7. <span data-ttu-id="057b4-192">В раскрывающемся меню выберите параметр **Съемный носитель** .</span><span class="sxs-lookup"><span data-stu-id="057b4-192">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="057b4-193">Добавьте соответствующие **TeamsRTMMode\*.ppkg** пакет, который ранее был скопирован на ключ USB.</span><span class="sxs-lookup"><span data-stu-id="057b4-193">Add the appropriate **TeamsRTMMode\*.ppkg** package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="057b4-194">Перезагрузите устройство поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="057b4-194">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="057b4-195">После перезагрузки устройства, должна появиться возможность запуска приложения группы на начальном экране и присоединиться к собранию из календаря.</span><span class="sxs-lookup"><span data-stu-id="057b4-195">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="057b4-196">Вариант 2: Настройка с помощью MDM, такие как InTune</span><span class="sxs-lookup"><span data-stu-id="057b4-196">Option 2: Configure via MDM such as InTune</span></span> 

<span data-ttu-id="057b4-197">Используйте следующие для настройки политики по умолчанию звонков и собраний приложения с помощью InTune.</span><span class="sxs-lookup"><span data-stu-id="057b4-197">Use the following to configure the default calling and meetings application policy via InTune.</span></span>

|<span data-ttu-id="057b4-198">Параметр</span><span class="sxs-lookup"><span data-stu-id="057b4-198">Setting</span></span>   |<span data-ttu-id="057b4-199">Значение</span><span class="sxs-lookup"><span data-stu-id="057b4-199">Value</span></span>    |<span data-ttu-id="057b4-200">Описание</span><span class="sxs-lookup"><span data-stu-id="057b4-200">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="057b4-201">Путь</span><span class="sxs-lookup"><span data-stu-id="057b4-201">Path</span></span>      | <span data-ttu-id="057b4-202">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="057b4-202">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="057b4-203">Тип данных</span><span class="sxs-lookup"><span data-stu-id="057b4-203">Data Type</span></span> | <span data-ttu-id="057b4-204">целое число (0-2)</span><span class="sxs-lookup"><span data-stu-id="057b4-204">integer (0-2)</span></span>   |<span data-ttu-id="057b4-205">0 — Скайп предпочитаемый приложения на начальном экране, доступные команды собраний</span><span class="sxs-lookup"><span data-stu-id="057b4-205">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="057b4-206">1 - предпочитаемый приложения группы на начальном экране, доступные Скайп собраний</span><span class="sxs-lookup"><span data-stu-id="057b4-206">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="057b4-207">2 - группам исключительных приложения на начальном экране (недоступно приложение Скайп)</span><span class="sxs-lookup"><span data-stu-id="057b4-207">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="057b4-208">Операции</span><span class="sxs-lookup"><span data-stu-id="057b4-208">Operations</span></span>| <span data-ttu-id="057b4-209">Получение, установка</span><span class="sxs-lookup"><span data-stu-id="057b4-209">Get, Set</span></span>        |

|<span data-ttu-id="057b4-210">Параметр</span><span class="sxs-lookup"><span data-stu-id="057b4-210">Setting</span></span>   |<span data-ttu-id="057b4-211">Значение</span><span class="sxs-lookup"><span data-stu-id="057b4-211">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="057b4-212">Путь</span><span class="sxs-lookup"><span data-stu-id="057b4-212">Path</span></span>      | <span data-ttu-id="057b4-213">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="057b4-213">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="057b4-214">Тип данных</span><span class="sxs-lookup"><span data-stu-id="057b4-214">Data Type</span></span> | <span data-ttu-id="057b4-215">String (строка набора для групп код пакета приложения как - **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Команды**)</span><span class="sxs-lookup"><span data-stu-id="057b4-215">string (set string to Teams application package ID as - **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**)</span></span> |
|<span data-ttu-id="057b4-216">Операции</span><span class="sxs-lookup"><span data-stu-id="057b4-216">Operations</span></span>| <span data-ttu-id="057b4-217">Получение, установка</span><span class="sxs-lookup"><span data-stu-id="057b4-217">Get, Set</span></span>        |

<span data-ttu-id="057b4-218">Перезагрузите устройство поверхность сервера-концентратора.</span><span class="sxs-lookup"><span data-stu-id="057b4-218">Restart the Surface Hub device.</span></span> <span data-ttu-id="057b4-219">После перезагрузки устройства, должна появиться возможность запуска приложения группы на начальном экране и присоединиться к собранию из календаря.</span><span class="sxs-lookup"><span data-stu-id="057b4-219">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

> [!NOTE]
> <span data-ttu-id="057b4-220">Если ваше устройство или устройствах вашей организации не в настоящее время частью программы изнутри Windows и находятся в странах, затрагиваемых с нормы защиты общие данные (GDPR) (или вручную были изменены параметры телеметрии для базовой), необходимо повторно проверить что были разрешены полный телеметрии перед присоединением изнутри программы.</span><span class="sxs-lookup"><span data-stu-id="057b4-220">If your device or your organization's devices are not currently part of the Windows Insider Program and you are in countries covered by General Data Protection Regulation (GDPR) (or you have manually changed your telemetry settings to Basic), then you must re-check that you have permitted full telemetry before you join the Insider Program.</span></span> <span data-ttu-id="057b4-221">GDPR изменить поведение по умолчанию сервер-концентратор поверхность устройств в ЕС Установка телеметрии для базовой.</span><span class="sxs-lookup"><span data-stu-id="057b4-221">GDPR changed the default behavior of Surface Hub devices in the EU to set telemetry to Basic.</span></span>