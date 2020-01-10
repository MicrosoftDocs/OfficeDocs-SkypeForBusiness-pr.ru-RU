---
title: Интеграция Skype для бизнеса Online и Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Настройка проверки подлинности OAuth между Exchange на локальном и Skype для бизнеса Online включает возможности интеграции Skype для бизнеса и Exchange, описанные в разделе Поддержка функций.
ms.openlocfilehash: 35dc8777ddf5c7102e99d726f916f9b8f8bb4aae
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002899"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="6163c-103">Настройка интеграции и OAuth между Skype для бизнеса Online и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6163c-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="6163c-104">Настройка интеграции между Exchange Server и Skype для бизнеса Online включает возможности интеграции Skype для бизнеса и Exchange, описанные в разделе [Поддержка функций](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="6163c-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="6163c-105">Эта статья относится к интеграции с Exchange Server 2013 – 2019.</span><span class="sxs-lookup"><span data-stu-id="6163c-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6163c-106">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="6163c-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6163c-107">Предполагаемое время выполнения этой задачи: 15 минут</span><span class="sxs-lookup"><span data-stu-id="6163c-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="6163c-108">Перед выполнением этих процедур вы должны получить разрешения.</span><span class="sxs-lookup"><span data-stu-id="6163c-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="6163c-109">Чтобы узнать, какие разрешения вам нужны, ознакомьтесь с разделом [разрешения для инфраструктуры Exchange и оболочки](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="6163c-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="6163c-110">Сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в разделе сочетания [клавиш в центре администрирования Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="6163c-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="6163c-111">Сведения о совместимости можно найти [в разделе Совместимость Skype для бизнеса с приложениями Office](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span><span class="sxs-lookup"><span data-stu-id="6163c-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="6163c-112">Настройка интеграции между сервером Exchange Server и Office 365</span><span class="sxs-lookup"><span data-stu-id="6163c-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="6163c-113">Действие 1: Настройка проверки подлинности OAuth между Exchange Server и O365</span><span class="sxs-lookup"><span data-stu-id="6163c-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="6163c-114">Выполните действия, описанные в приведенной ниже статье.</span><span class="sxs-lookup"><span data-stu-id="6163c-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="6163c-115">Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6163c-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="6163c-116">Действие 2: создание учетной записи пользователя для приложения-партнера Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6163c-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="6163c-117">Это действие выполняется на сервере Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="6163c-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="6163c-118">На этом шаге создается пользователь почты, которому назначаются соответствующие права роли управления.</span><span class="sxs-lookup"><span data-stu-id="6163c-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="6163c-119">Затем эта учетная запись используется на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="6163c-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="6163c-120">Укажите проверенный домен для организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="6163c-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="6163c-121">Этот домен должен быть тем же доменом, который используется в качестве основного домена SMTP для локальных учетных записей Exchange.</span><span class="sxs-lookup"><span data-stu-id="6163c-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="6163c-122">Этот домен называется \<проверяемым доменом\> в описанной ниже процедуре.</span><span class="sxs-lookup"><span data-stu-id="6163c-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="6163c-123">Кроме того, \<домаинконтроллерфкдн\> должно быть полным доменным именем контроллера домена.</span><span class="sxs-lookup"><span data-stu-id="6163c-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="6163c-124">Эта команда скрывает нового пользователя почты из списка адресов.</span><span class="sxs-lookup"><span data-stu-id="6163c-124">This command will hide the new mail user from address lists.</span></span>

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="6163c-125">Следующие две команды назначают новой учетной записи роль управления UserApplication и ArchiveApplication.</span><span class="sxs-lookup"><span data-stu-id="6163c-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="6163c-126">Шаг 3: создание и включение приложения-партнера для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6163c-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="6163c-127">Создайте новое партнерское приложение и начните использовать созданную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="6163c-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="6163c-128">Выполните следующую команду в PowerShell Exchange в локальной организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="6163c-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="6163c-129">Шаг 4: экспорт локального сертификата авторизации</span><span class="sxs-lookup"><span data-stu-id="6163c-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="6163c-130">Запустите сценарий PowerShell для экспорта локального сертификата авторизации, который вы будете импортировать в организацию Skype для бизнеса Online, на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="6163c-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="6163c-131">Сохраните следующий тест в файл сценария PowerShell, который можно назвать ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="6163c-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

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

<span data-ttu-id="6163c-132">В Exchange PowerShell в локальной организации Exchange выполните созданный сценарий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6163c-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="6163c-133">Например: .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="6163c-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="6163c-134">Шаг 5: отправка локального сертификата авторизации в Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="6163c-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="6163c-135">Далее, используя Windows PowerShell, отправьте локальный сертификат авторизации, экспортированный на предыдущем шаге, в службу управления доступом Azure Active Directory (ACS).</span><span class="sxs-lookup"><span data-stu-id="6163c-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="6163c-136">Перед выполнением этого действия необходимо установить командлеты модуля Azure Active Directory Module для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6163c-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="6163c-137">Если он не установлен, перейдите в раздел [https://aka.ms/aadposh](https://aka.ms/aadposh) для установки модуля Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6163c-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="6163c-138">После установки модуля Azure Active Directory для Windows PowerShell выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6163c-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="6163c-p107">Нажмите на ярлык **Модуль Azure Active Directory для Windows PowerShell**, чтобы открыть рабочую область Windows PowerShell с установленными командлетами Azure AD. Все команды на этом шаге должны быть выполнены с помощью консоли Windows PowerShell для Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6163c-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="6163c-141">Сохраните приведенный ниже текст в файле сценария PowerShell (например,) `UploadAuthCert.ps1`.</span><span class="sxs-lookup"><span data-stu-id="6163c-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

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

3. <span data-ttu-id="6163c-142">Запустите сценарий PowerShell, созданный на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="6163c-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="6163c-143">Например:`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="6163c-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="6163c-p109">После запуска сценария появится диалоговое окно для ввода учетных данных. Введите данные учетной записи администратора клиента вашей организации Microsoft Online Azure AD. После выполнения сценария оставьте сеанс работы Windows PowerShell для Azure AD открытым. Он будет использоваться для запуска сценария PowerShell на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="6163c-p109">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="6163c-148">Шаг 6: Проверка того, что сертификат передан участникам службы Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6163c-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="6163c-149">В PowerShell, который был открыт и прошел проверку подлинности в Azure Active Directory, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6163c-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="6163c-150">При появлении соответствующего запроса нажмите клавишу ВВОД Ретурнкэйвалуес</span><span class="sxs-lookup"><span data-stu-id="6163c-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="6163c-151">Убедитесь, что в списке указан ключ с датой начала и конечными данными, которые соответствуют датам начала и окончания сертификата в Exchange OAuth.</span><span class="sxs-lookup"><span data-stu-id="6163c-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="6163c-152">Проверка успешности выполнения</span><span class="sxs-lookup"><span data-stu-id="6163c-152">Verify your success</span></span>

<span data-ttu-id="6163c-153">Убедитесь в том, что конфигурация верна, проверьте, успешно ли работают некоторые функции.</span><span class="sxs-lookup"><span data-stu-id="6163c-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="6163c-154">Убедитесь в том, что пользователи Skype для бизнеса с облачной службой голосовой почты в Организации с гибридной конфигурацией Exchange Server могут успешно изменить голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="6163c-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="6163c-155">Убедитесь в том, что в папке "Журнал бесед" Outlook отображается журнал бесед для мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="6163c-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="6163c-156">Убедитесь в том, что архивированные сообщения в чате хранятся в локальном почтовом ящике пользователя в папке очистки с помощью [евседитор](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span><span class="sxs-lookup"><span data-stu-id="6163c-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="6163c-157">Кроме того, Взгляните на трафик.</span><span class="sxs-lookup"><span data-stu-id="6163c-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="6163c-158">Трафик в подтверждении OAuth является весьма отличительным (и не рассматривается как обычная проверка подлинности), особенно вокруг сфер, где вы начнете просматривать трафик поставщика, выглядящий следующим образом: 00000004-0000-0ff1-ce00-000000000000 @ (иногда — перед знаком @ и до него) в передаваемых маркерах.</span><span class="sxs-lookup"><span data-stu-id="6163c-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="6163c-159">Вы не увидите имя пользователя или пароль, который является точкой OAuth.</span><span class="sxs-lookup"><span data-stu-id="6163c-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="6163c-160">Но вы увидите, что в этом случае это "4" — Skype для бизнеса — и сфера подписки.</span><span class="sxs-lookup"><span data-stu-id="6163c-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="6163c-161">Если вы хотите, чтобы вы успешно использовали OAuth, убедитесь, что вы знаете, что нужно ожидать и что нужно знать, как выглядит трафик.</span><span class="sxs-lookup"><span data-stu-id="6163c-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="6163c-162">Итак, вот [что нужно ожидать](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)— вот Стандартный [пример трафика OAuth в приложении Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (это может оказаться полезным для чтения, но не использует маркеры обновления), и есть расширения Fiddler, позволяющие найти OAuth JWT (веб-маркер JSON).</span><span class="sxs-lookup"><span data-stu-id="6163c-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="6163c-163">Ниже приведен [Пример настройки одного из них](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), но вы можете использовать любой сетевой инструмент трассировки, который вы хотите предпринять.</span><span class="sxs-lookup"><span data-stu-id="6163c-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6163c-164">См. также</span><span class="sxs-lookup"><span data-stu-id="6163c-164">Related topics</span></span>

[<span data-ttu-id="6163c-165">Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6163c-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
