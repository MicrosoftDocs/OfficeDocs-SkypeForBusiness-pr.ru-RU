---
title: Интеграция Между Skype для бизнеса Online и сервером Exchange Server
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Настройка проверки подлинности OAuth между локальной службой Exchange и Skype для бизнеса Online позволяет использовать функции интеграции Skype для бизнеса и Exchange, описанные в поддержке функций.
ms.openlocfilehash: ac8bfe2f30e813e47a0256a68e4e81852d5bae68
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833979"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="38260-103">Настройка интеграции и OAuth между Skype для бизнеса Online и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="38260-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="38260-104">Настройка интеграции между сервером Exchange и Skype для бизнеса Online позволяет использовать функции интеграции Skype для бизнеса и Exchange, описанные в поддержке [функций.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)</span><span class="sxs-lookup"><span data-stu-id="38260-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="38260-105">Этот раздел относится к интеграции с Exchange Server 2013-2019.</span><span class="sxs-lookup"><span data-stu-id="38260-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="38260-106">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="38260-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="38260-107">Предполагаемое время выполнения задачи: 15 минут.</span><span class="sxs-lookup"><span data-stu-id="38260-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="38260-108">Для выполнения этой процедуры (процедур) необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="38260-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="38260-109">Чтобы узнать, какие разрешения необходимы, см. раздел о разрешениях инфраструктуры [Exchange и оболочки.](https://go.microsoft.com/fwlink/p/?LinkId=746511)</span><span class="sxs-lookup"><span data-stu-id="38260-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="38260-110">Сочетания клавиш для процедур, описанных в этой статье, приведены в статье [Сочетания клавиш в Центре администрирования Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="38260-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="38260-111">Сведения о совместимости см. в сведениях о совместимости Skype для [бизнеса с приложениями Office.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)</span><span class="sxs-lookup"><span data-stu-id="38260-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="38260-112">Настройка интеграции между Exchange Server и O365</span><span class="sxs-lookup"><span data-stu-id="38260-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="38260-113">Шаг 1. Настройка проверки подлинности OAuth между Exchange Server и O365</span><span class="sxs-lookup"><span data-stu-id="38260-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="38260-114">Выполните действия, которые необходимо выполнить в следующей статье:</span><span class="sxs-lookup"><span data-stu-id="38260-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="38260-115">Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online</span><span class="sxs-lookup"><span data-stu-id="38260-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="38260-116">Шаг 2. Создание новой учетной записи пользователя почты для партнерского приложения Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="38260-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="38260-117">Это делается на сервере Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="38260-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="38260-118">Он создаст пользователя почты и назначит ему соответствующие права роли управления.</span><span class="sxs-lookup"><span data-stu-id="38260-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="38260-119">Эта учетная запись будет использоваться на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="38260-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="38260-120">Укажите проверенный домен для организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="38260-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="38260-121">Этот домен должен быть тем же доменом, который используется в качестве основного домена SMTP, используемого для учетных записей локальной exchange.</span><span class="sxs-lookup"><span data-stu-id="38260-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="38260-122">Этот домен называется в \<your Verified Domain\> следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="38260-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="38260-123">Кроме того, \<DomainControllerFQDN\> это должно быть FQDN контроллера домена.</span><span class="sxs-lookup"><span data-stu-id="38260-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="38260-124">Эта команда скрывает нового пользователя почты из списков адресов.</span><span class="sxs-lookup"><span data-stu-id="38260-124">This command will hide the new mail user from address lists.</span></span>

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="38260-125">Следующие две команды назначят роль управления UserApplication и ArchiveApplication этой новой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="38260-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="38260-126">Шаг 3. Создание и включить партнерского приложения для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="38260-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="38260-127">Создайте новое партнерского приложения и будет использовать только что созданную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="38260-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="38260-128">Выполните следующую команду в командной консоли Exchange в своей локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="38260-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="38260-129">Шаг 4. Экспорт локального сертификата авторизации</span><span class="sxs-lookup"><span data-stu-id="38260-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="38260-130">Запустите сценарий PowerShell, чтобы экспортировать сертификат локальной авторизации, который будет импортироваться в организацию Skype для бизнеса Online на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="38260-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="38260-131">Сохраните следующий текст в файл сценария PowerShell с именем ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="38260-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

```powershell
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

<span data-ttu-id="38260-132">В Exchange PowerShell в локальной организации Exchange запустите созданный сценарий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38260-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="38260-133">Например: .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="38260-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="38260-134">Шаг 5. Отправка локального сертификата авторизации в службу acS Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="38260-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="38260-135">Затем используйте Windows PowerShell для отправки локального сертификата авторизации, экспортируемого на предыдущем шаге, в службы контроля доступа Azure Active Directory (ACS).</span><span class="sxs-lookup"><span data-stu-id="38260-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="38260-136">Для этого необходимо установить модуль Azure Active Directory для Windows PowerShell командлетов.</span><span class="sxs-lookup"><span data-stu-id="38260-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="38260-137">Если он не установлен, перейдите на страницу [https://aka.ms/aadposh](https://aka.ms/aadposh), чтобы установить Модуль Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38260-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="38260-138">После установки Модуль Azure Active Directory для Windows PowerShell выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="38260-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="38260-p107">Щелкните ярлык **Модуль Azure Active Directory для Windows PowerShell**, чтобы открыть рабочее пространство Windows PowerShell с установленными командлетами Azure AD. Все команды на этом этапе выполняются с помощью Windows PowerShell для консоли Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38260-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="38260-141">Сохраните следующий текст в файл сценария PowerShell с именем,  `UploadAuthCert.ps1` например.</span><span class="sxs-lookup"><span data-stu-id="38260-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ```powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. <span data-ttu-id="38260-142">Выполните сценарий PowerShell, созданный на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="38260-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="38260-143">Например:  `.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="38260-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="38260-144">После запуска сценария откроется диалоговое окно учетных данных.</span><span class="sxs-lookup"><span data-stu-id="38260-144">After you start the script, a credentials dialog box is displayed.</span></span> <span data-ttu-id="38260-145">Введите учетные данные для учетной записи администратора клиента вашей организации Microsoft Online Azure AD.</span><span class="sxs-lookup"><span data-stu-id="38260-145">Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization.</span></span> <span data-ttu-id="38260-146">После выполнения сценария оставьте сеанс Windows PowerShell для Azure AD открытым.</span><span class="sxs-lookup"><span data-stu-id="38260-146">After running the script, leave the Windows PowerShell for Azure AD session open.</span></span> <span data-ttu-id="38260-147">Он понадобится для запуска сценария PowerShell на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="38260-147">You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="38260-148">Шаг 6. Убедитесь, что сертификат загружен в основное приложение-службу Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="38260-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="38260-149">В powerShell, открытой и с проверкой подлинности в Azure Active Directory, запустите следующую</span><span class="sxs-lookup"><span data-stu-id="38260-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="38260-150">Нажмите ввод при запросе returnKeyValues</span><span class="sxs-lookup"><span data-stu-id="38260-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="38260-151">Подтвердите, что в списке указан ключ с данными начала и окончания, которые совпадают с датой начала и окончания сертификата Oauth Exchange</span><span class="sxs-lookup"><span data-stu-id="38260-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="38260-152">Проверка успешности</span><span class="sxs-lookup"><span data-stu-id="38260-152">Verify your success</span></span>

<span data-ttu-id="38260-153">Проверьте правильность конфигурации, проверив, что некоторые функции работают успешно.</span><span class="sxs-lookup"><span data-stu-id="38260-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="38260-154">Подтвердим, что пользователи Skype для бизнеса со службой облачной голосовой почты в организации с гибридной конфигурацией Exchange Server могут успешно изменить приветствия голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="38260-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="38260-155">Подтвердим, что история бесед для мобильных клиентов отображается в папке "История бесед Outlook".</span><span class="sxs-lookup"><span data-stu-id="38260-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="38260-156">Подтвердим, что архивные сообщения чата находятся в локальном почтовом ящике пользователя в папке "Очистка" с помощью [EWSEditor.](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)</span><span class="sxs-lookup"><span data-stu-id="38260-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="38260-157">Кроме того, посмотрите на трафик.</span><span class="sxs-lookup"><span data-stu-id="38260-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="38260-158">Трафик при рукопожатии OAuth очень разнообразен (и не похож на базовую проверку подлинности), особенно вокруг областей, где вы увидите трафик, который будет выглядеть так: 000000004-0000-0ff1-ce00-000000000000@ (иногда со знаком /перед знаком @) в передаваемом маркере.</span><span class="sxs-lookup"><span data-stu-id="38260-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="38260-159">Вы не увидите имя пользователя или пароль, который является точкой OAuth.</span><span class="sxs-lookup"><span data-stu-id="38260-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="38260-160">But you will see the 'Office' issuer ( in this case '4' is Skype for Business ) and the realm of your subscription.</span><span class="sxs-lookup"><span data-stu-id="38260-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="38260-161">Если вы хотите убедиться, что вы успешно используете OAuth, убедитесь, что вы знаете, чего ожидать, и как должен выглядеть трафик.</span><span class="sxs-lookup"><span data-stu-id="38260-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="38260-162">Вот чего [ожидать.](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)Вот довольно стандартный пример трафика [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  в приложении Майкрософт (действительно полезно читать, хотя в нем не используются маркеры обновления), и существуют расширения Fiddler, которые будут позволять вам посмотреть на ваш OAuth JWT (веб-маркер JSON).</span><span class="sxs-lookup"><span data-stu-id="38260-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="38260-163">Вот пример [настройки,](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)но вы можете использовать любое средство сетевой трассиации, для этого необходимо.</span><span class="sxs-lookup"><span data-stu-id="38260-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="38260-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="38260-164">Related topics</span></span>

[<span data-ttu-id="38260-165">Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online</span><span class="sxs-lookup"><span data-stu-id="38260-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
