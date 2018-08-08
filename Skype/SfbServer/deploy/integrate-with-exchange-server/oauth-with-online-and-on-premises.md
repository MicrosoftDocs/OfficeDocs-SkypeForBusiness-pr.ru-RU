---
title: Настройка подключения по протоколу OAuth между Skype для бизнеса Online и локальной системой Exchange
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Настройка OAuth проверки подлинности между Exchange при локальном и Скайп для бизнеса в Интернет позволяет Скайп для бизнеса и интеграция с Exchange, описанными в поддержка функции.
ms.openlocfilehash: cb822dd183e913fd1b3258cc136572380592733f
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "22138611"
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a><span data-ttu-id="cc8b8-103">Настройка подключения по протоколу OAuth между Skype для бизнеса Online и локальной системой Exchange</span><span class="sxs-lookup"><span data-stu-id="cc8b8-103">Configure OAuth between Skype for Business Online and Exchange on premises</span></span>
 
<span data-ttu-id="cc8b8-104">Настройка OAuth проверки подлинности между Exchange при локальном и Скайп для бизнеса в Интернет позволяет Скайп для бизнеса и интеграция с Exchange, описанными в [функции поддержки](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="cc8b8-104">Configuring OAuth authentication between Exchange on premises and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>
  
<span data-ttu-id="cc8b8-105">Данный раздел относится к Exchange Server 2016 и Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-105">This topic applies to Exchange Server 2016 and Exchange Server 2013.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cc8b8-106">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="cc8b8-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cc8b8-107">Предполагаемое время выполнения этой задачи: 15 минут</span><span class="sxs-lookup"><span data-stu-id="cc8b8-107">Estimated time to complete this task: 15 minutes</span></span>
    
-  <span data-ttu-id="cc8b8-108">Перед выполнением этих процедур вы должны получить разрешения.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="cc8b8-109">Какие нужны разрешения см в разделе [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="cc8b8-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>
    
- <span data-ttu-id="cc8b8-110">Сведения о сочетаниях клавиш, которые могут относиться к процедур, описанных в этом разделе содержатся [сочетаний клавиш в центре администрирования Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="cc8b8-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>
    
## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a><span data-ttu-id="cc8b8-111">Настройка проверки подлинности OAuth между локальным Exchange и организациями Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cc8b8-111">Configure OAuth authentication between your on-premises Exchange and Skype for Business organizations</span></span>

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a><span data-ttu-id="cc8b8-112">Шаг 1. Создайте объект сервера авторизации для организации Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cc8b8-112">Step 1: Create an authorization server object for your Skype for Business Online organization</span></span>

<span data-ttu-id="cc8b8-113">Укажите подтвержденным доменом вашей Скайп для бизнеса сети организации.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-113">Specify a verified domain for your Skype for Business Online organization.</span></span> <span data-ttu-id="cc8b8-114">Это должен быть тот же домен, который использовался в качестве основного домена SIP для облачных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-114">This domain should be the same domain used as the primary SIP domain used for the cloud-based accounts.</span></span> <span data-ttu-id="cc8b8-115">В этом домене называется \<домена проверены\> в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-115">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>
  
<span data-ttu-id="cc8b8-116">Выполните следующую команду в консоль управления Exchange (Exchange PowerShell) в своей локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-116">Run the following command in the Exchange Management Shell (the Exchange PowerShell) in your on-premises Exchange organization.</span></span>
  
```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1" 
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a><span data-ttu-id="cc8b8-117">Шаг 2. Включите партнерское приложение для организации Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cc8b8-117">Step 2: Enable the partner application for your Skype for Business Online organization</span></span>

<span data-ttu-id="cc8b8-118">Выполните следующую команду в Exchange PowerShell в своей локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-118">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>
  
```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="cc8b8-119">Шаг 3. Создайте новую учетную запись пользователя почты для партнерского приложения Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cc8b8-119">Step 3: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="cc8b8-p103">Этот шаг выполняется локально. На этом шаге создается пользователь почты, которому назначаются соответствующие права роли управления. Затем эта учетная запись используется на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-p103">This step is done on-premises. It will create a mail user and assign it the appropriate management role rights. This account will then be used in the next step.</span></span>
  
<span data-ttu-id="cc8b8-123">Укажите подтвержденным доменом в организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-123">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="cc8b8-124">Этот домен должен быть того же домена, используется в качестве основного домена SMTP, используемый для учетных записей Exchange в локальной.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-124">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="cc8b8-125">В этом домене называется \<домена проверены\> в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-125">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="cc8b8-126">Кроме того \<DomainControllerFQDN\> должно быть полное доменное имя контроллера домена.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-126">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span> 
  
```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN> 
```

<span data-ttu-id="cc8b8-127">Эта команда скрывает нового пользователя почты из списка адресов.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-127">This command will hide the new mail user from address lists.</span></span>
  
```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN> 
```

<span data-ttu-id="cc8b8-128">Следующие две команды назначают новой учетной записи роль управления UserApplication и ArchiveApplication.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-128">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>
  
```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="cc8b8-129">Шаг 4. Создайте и активируйте партнерское приложение для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cc8b8-129">Step 4: Create and enable a Partner Application for Skype for Business Online</span></span>

<span data-ttu-id="cc8b8-130">Создайте новое партнерское приложение и начните использовать созданную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-130">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="cc8b8-131">Выполните следующую команду в Exchange PowerShell в своей локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-131">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span> 
  
```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="cc8b8-132">Шаг 5. Экспортируйте локальный сертификат авторизации</span><span class="sxs-lookup"><span data-stu-id="cc8b8-132">Step 5: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="cc8b8-133">Выполнение скрипта PowerShell, чтобы экспортировать сертификат проверки подлинности в локальной, который импортируется на вашей Скайп для бизнеса в Интернет организации на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-133">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>
  
<span data-ttu-id="cc8b8-134">Сохраните следующий тест в файл сценария PowerShell, который можно назвать ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-134">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>
  
```
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint 
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false) 
{ 
md $env:SYSTEMDRIVE\OAuthConfig 
} 
cd $env:SYSTEMDRIVE\OAuthConfig 
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint} 
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert 
$certBytes = $oAuthCert.Export($certType) 
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer" 
[System.IO.File]::WriteAllBytes($CertFile, $certBytes) 
```

<span data-ttu-id="cc8b8-135">В Exchange PowerShell в вашей локальной организации Exchange, выполнение скрипта PowerShell, который вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-135">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="cc8b8-136">Например:.\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="cc8b8-136">For example: .\ExportAuthCert.ps1</span></span>
  
### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="cc8b8-137">Шаг 6. Отправьте локальный сертификат авторизации в Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="cc8b8-137">Step 6: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="cc8b8-138">Далее, используя Windows PowerShell, отправьте локальный сертификат авторизации, экспортированный на предыдущем шаге, в службу управления доступом Azure Active Directory (ACS).</span><span class="sxs-lookup"><span data-stu-id="cc8b8-138">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="cc8b8-139">Перед выполнением этого действия необходимо установить командлеты модуля Azure Active Directory Module для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-139">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="cc8b8-140">Если он не установлен, перейдите к разделу [https://aka.ms/aadposh](https://aka.ms/aadposh) Установка Azure модуль Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-140">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="cc8b8-141">После установки модуля Azure Active Directory для Windows PowerShell выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-141">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>
  
1. <span data-ttu-id="cc8b8-p108">Нажмите на ярлык **Модуль Azure Active Directory для Windows PowerShell**, чтобы открыть рабочую область Windows PowerShell с установленными командлетами Azure AD. Все команды на этом шаге должны быть выполнены с помощью консоли Windows PowerShell для Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-p108">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>
    
2. <span data-ttu-id="cc8b8-144">Сохраните следующий текст в файл сценария PowerShell с именем, например, `UploadAuthCert.ps1`.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-144">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>
    
  ```
  Connect-MsolService; 
Import-Module msonlineextended; 
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer" 
$objFSO = New-Object -ComObject Scripting.FileSystemObject; 
$CertFile = $objFSO.GetAbsolutePathName($CertFile); 
$cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate 
$cer.Import($CertFile); 
$binCert = $cer.GetRawCertData(); 
$credValue = [System.Convert]::ToBase64String($binCert); 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName 
New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue 
  ```

3. <span data-ttu-id="cc8b8-145">Запустите сценарий PowerShell, созданный на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-145">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="cc8b8-146">Например:`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="cc8b8-146">For example:  `.\UploadAuthCert.ps1`</span></span>
    
4. <span data-ttu-id="cc8b8-p110">После запуска сценария появится диалоговое окно для ввода учетных данных. Введите данные учетной записи администратора клиента вашей организации Microsoft Online Azure AD. После выполнения сценария оставьте сеанс работы Windows PowerShell для Azure AD открытым. Он будет использоваться для запуска сценария PowerShell на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-p110">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>
    
### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a><span data-ttu-id="cc8b8-151">Шаг 7. Зарегистрируйте источник имени хоста для домена SMTP</span><span class="sxs-lookup"><span data-stu-id="cc8b8-151">Step 7: Register the hostname authorities for the SMTP domain</span></span>

<span data-ttu-id="cc8b8-152">Укажите подтвержденным доменом в организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-152">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="cc8b8-153">Этот домен должен быть того же домена, используется в качестве основного домена SMTP, используемый для учетных записей Exchange в локальной.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-153">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="cc8b8-154">В этом домене называется \<домена проверены\> в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-154">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc8b8-155">Для успешного выполнения следующего сценария требуется подключить Windows PowerShell для Azure Active Directory к клиенту Microsoft Online Azure AD, как описано на шаге 4 предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-155">Successfully running the following script requires that the Windows PowerShell for Azure Active Directory is connected to your Microsoft Online Azure AD tenant, as explained in step 4 in the previous section.</span></span> 
  
1. <span data-ttu-id="cc8b8-156">Сохраните следующий тест в файл сценария PowerShell, который можно назвать RegisterEndpoints.ps1.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-156">Save the following text to a PowerShell script file named, for example, RegisterEndpoints.ps1.</span></span> <span data-ttu-id="cc8b8-157">В этом примере используется подстановочный знак для регистрации всех конечных точек contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-157">This example uses a wildcard to register all endpoints for contoso.com.</span></span> <span data-ttu-id="cc8b8-158">Замените contoso.com сертификации имя узла для своей локальной организации Exchange</span><span class="sxs-lookup"><span data-stu-id="cc8b8-158">Replace contoso.com with a hostname authority for your on-premises Exchange organization</span></span>
    
  ```
  $externalAuthority="*.<your Verified Domain>" 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName; 
$spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority); 
$p.ServicePrincipalNames.Add($spn); 
Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames; 
  ```

2.  <span data-ttu-id="cc8b8-159">В Windows PowerShell для Azure Active Directory выполните сценарий Windows PowerShell, созданный на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-159">In Windows PowerShell for Azure Active Directory, run the Windows PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="cc8b8-160">Например: `.\RegisterEndpoints.ps1`</span><span class="sxs-lookup"><span data-stu-id="cc8b8-160">For example: `.\RegisterEndpoints.ps1`</span></span>
    
### <a name="verify-your-success"></a><span data-ttu-id="cc8b8-161">Проверка успешности выполнения</span><span class="sxs-lookup"><span data-stu-id="cc8b8-161">Verify your success</span></span>

<span data-ttu-id="cc8b8-162">Проверьте правильность конфигурации OAuth, проверив работу отдельных функций, например, отображение журнала бесед для мобильных клиентов в папке журнала бесед Outlook.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-162">Verify that the OAuth configuration is correct by verifying some of the features are working successfully, such as having conversation history for mobile clients visible in the Outlook Conversation History folder.</span></span>
  
1. <span data-ttu-id="cc8b8-163">Запустите Скайп для мобильных устройств бизнес-приложения на Windows Phone или устройства iOS и войдите в качестве Скайп для бизнеса в Интернет пользователя с помощью Exchange 2016 или локального почтового ящика Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-163">Start the Skype for Business mobile app on your Windows Phone or iOS device and sign in as a Skype for Business Online user with an Exchange 2016 or Exchange 2013 on-premises mailbox.</span></span>
    
2. <span data-ttu-id="cc8b8-164">Иметь сеанс обмена мгновенными сообщениями с другой Скайп для бизнеса в Интернет пользователя.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-164">Have an instant messaging conversation with another Skype for Business Online user.</span></span>
    
3. <span data-ttu-id="cc8b8-165">Закройте окно беседы.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-165">Close the IM conversation window.</span></span>
    
4. <span data-ttu-id="cc8b8-166">Запустите Outlook от имени этого пользователя и убедитесь, что беседа отображается в папке журнала бесед Outlook.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-166">Start Outlook for this user and verify that the conversation is visible in the Outlook Conversation history folder.</span></span>
    
<span data-ttu-id="cc8b8-167">Кроме того Обратите внимание на трафик.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-167">Alternately, look at your traffic.</span></span> <span data-ttu-id="cc8b8-168">Трафик в подтверждении OAuth действительно особый (и не выглядит как обычная проверка подлинности), особенно вокруг сфер, где вы начнете видеть трафика издателя, которая выглядит следующим образом: 00000004-0000-0ff1-ce00-000000000000 @ (иногда с аудио- и перед знак @), в маркеры, которые передаются.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-168">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="cc8b8-169">Вы не увидите имя пользователя или пароль, который является точка OAuth.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-169">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="cc8b8-170">Но вы увидите издателя «Office» — в данном случае является Скайп для бизнеса – и область действия подписки "4".</span><span class="sxs-lookup"><span data-stu-id="cc8b8-170">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="cc8b8-171">Если необходимо, чтобы что успешно вы используете OAuth, убедитесь, что вы знаете, что следует ожидать и знать, как должны выглядеть трафика.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-171">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="cc8b8-172">Да, [Вот, что следует ожидать](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), вот стандартный [Пример трафика OAuth в приложении Microsoft](http://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (действительно полезен для чтения, хотя он не использует маркеры обновления) и существуют Fiddler расширения, которые можно найти в вашей OAuth JWT (JSON Веб-маркера).</span><span class="sxs-lookup"><span data-stu-id="cc8b8-172">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](http://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span> 

<span data-ttu-id="cc8b8-173">Ниже приведен [Пример настройки один](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), но можно использовать любое средство сетевой трассировки, как для выполнения этого процесса.</span><span class="sxs-lookup"><span data-stu-id="cc8b8-173">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>
