---
title: Интеграция Skype для бизнеса Online и Exchange сервера
ms.reviewer: cbland
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Настройка проверки подлинности OAuth между Exchange и Skype для бизнеса Online позволяет использовать функции интеграции Skype для бизнеса и Exchange, описанные в службе поддержки компонентов.
ms.openlocfilehash: dfc1bf25b19779b6a568a70e2cf18287d2f95d18
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864236"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Настройка интеграции и OAuth между Skype для бизнеса Online и Exchange Server 

Настройка интеграции между сервером Exchange и Skype для бизнеса Online позволяет использовать функции интеграции Skype для бизнеса и Exchange, описанные в [службе поддержки компонентов.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)

Этот раздел относится к интеграции с Exchange Server 2013 по 2019 годы.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Предполагаемое время выполнения задачи: 15 минут.

-  Для выполнения этой процедуры (процедур) необходимы соответствующие разрешения. Чтобы узнать, какие разрешения вам нужны, см. в [разделе Exchange разрешений](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) инфраструктуры и инфраструктуры Shell.

- Сочетания клавиш для процедур, описанных в этой статье, приведены в статье [Сочетания клавиш в Центре администрирования Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Сведения о совместимости см. в [Skype для бизнеса совместимости с Office приложениями.](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)

## <a name="configure-integration-between-exchange-server-and-o365"></a>Настройка интеграции между Exchange Server и O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Шаг 1. Настройка проверки подлинности OAuth между Exchange Server и O365

Выполните действия в следующей статье:

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Шаг 2. Создание новой учетной записи пользователя почты для Skype для бизнеса партнерского приложения

Этот шаг делается на Exchange сервере. Он создаст пользователя почты и назначит ему соответствующие права на роль управления. Затем эта учетная запись будет использоваться на следующем шаге.

Укажите проверенный домен для Exchange организации. Этот домен должен быть тем же доменом, который используется в качестве основного домена SMTP, используемого для Exchange учетных записей. Этот домен называется в \<your Verified Domain\> следующей процедуре. Кроме того, \<DomainControllerFQDN\> должен быть FQDN контроллера домена.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Эта команда будет скрывать нового пользователя почты из списков адресов.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Следующие две команды назначят этой новой учетной записи роль управления UserApplication и ArchiveApplication.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Шаг 3. Создание и создание партнерского приложения для Skype для бизнеса Online 

Создайте новое партнерского приложения и будете использовать только что созданную учетную запись. Выполните следующую команду в командной консоли Exchange в своей локальной организации Exchange.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Шаг 4. Экспорт локального сертификата авторизации

Запустите сценарий PowerShell для экспорта локального сертификата авторизации, который будет импортироваться в организацию Skype для бизнеса Online на следующем шаге.

Сохраните следующий текст в файл сценария PowerShell с именем ExportAuthCert.ps1.

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

В Exchange PowerShell в локальной организации Exchange запустите только что созданный скрипт PowerShell. Например: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Шаг 5. Upload локального сертификата авторизации для Azure Active Directory ACS

Затем используйте Windows PowerShell для отправки локального сертификата авторизации, экспортируемого на предыдущем этапе, Azure Active Directory службы управления доступом (ACS). Для этого необходимо установить Azure Active Directory для Windows PowerShell командлетов. Если он не установлен, перейдите на страницу [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)), чтобы установить Модуль Azure Active Directory для Windows PowerShell. После установки Модуль Azure Active Directory для Windows PowerShell выполните следующие действия.

1. Щелкните ярлык **Модуль Azure Active Directory для Windows PowerShell**, чтобы открыть рабочее пространство Windows PowerShell с установленными командлетами Azure AD. Все команды на этом этапе выполняются с помощью Windows PowerShell для консоли Azure Active Directory.

2. Сохраните следующий текст в файле скрипта PowerShell с именем,  `UploadAuthCert.ps1` например.

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

3. Выполните сценарий PowerShell, созданный на предыдущем этапе. Например:  `.\UploadAuthCert.ps1`

4. После запуска сценария откроется диалоговое окно учетных данных. Введите учетные данные учетной записи администратора клиента в организации Microsoft Online Azure AD. После выполнения сценария оставьте сеанс Windows PowerShell для Azure AD открытым. Он понадобится для запуска сценария PowerShell на следующем этапе.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Шаг 6. Убедитесь, что сертификат был загружен в Skype для бизнеса службы
1. В powerShell, открываемой и Azure Active Directory проверке подлинности, запустите следующие
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Нажмите кнопку Ввод при запросе returnKeyValues
3. Подтвердите, что вы видите ключ, указанный с датами начала и конечными данными, которые совпадают с датами начала и окончания Exchange Oauth

### <a name="verify-your-success"></a>Проверка успеха

Убедитесь, что конфигурация является правильной, проверив успешное работу некоторых функций. 

1. Подтвердим, Skype для бизнеса пользователи с облачная голосовая почта службой в организации с гибридной конфигурацией Exchange Server могут успешно изменять приветствия голосовой почты.

2. Подтверждение истории бесед для мобильных клиентов отображается в папке Outlook истории бесед.

3. Подтверждение того, что архивные сообщения чата вложены в локальном почтовом ящике пользователя в папке Purges с помощью [EWSEditor.](/archive/blogs/webdav_101/where-to-get-ewseditor)

Поочередно посмотрите на трафик. Трафик в рукопожатии OAuth действительно отличается (и не похож на базовую проверку подлинности), особенно вокруг областей, где вы увидите трафик эмитента, который выглядит так: 000000004-0000-0ff1-ce00-00000000000000@ (иногда с / перед знаком @) в маркерах, которые передаются. Вы не увидите имя пользователя или пароль, который является точкой OAuth. Но вы увидите эмитент "Office" ( в данном случае Skype для бизнеса 4) и область подписки.

Если вы хотите убедиться, что вы успешно используете OAuth, убедитесь, что вы знаете, чего ожидать, и знаете, как должен выглядеть трафик. Вот что можно [ожидать,](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)вот довольно стандартный пример трафика [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  в приложении Майкрософт (действительно полезно читать, хотя он не использует маркеры обновления), и есть расширения Fiddler, которые позволит вам заглянуть в OAuth JWT (JSON Web Token).

Вот пример [настройки,](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)но вы можете использовать любой сетевой инструмент отслеживания, который вам нравится для этого процесса.

## <a name="related-topics"></a>Статьи по теме

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)