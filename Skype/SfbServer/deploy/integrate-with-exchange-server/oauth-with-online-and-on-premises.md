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
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Настройка интеграции и OAuth между Skype для бизнеса Online и Exchange Server 

Настройка интеграции между сервером Exchange и Skype для бизнеса Online позволяет использовать функции интеграции Skype для бизнеса и Exchange, описанные в поддержке [функций.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)

Этот раздел относится к интеграции с Exchange Server 2013-2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Предполагаемое время выполнения задачи: 15 минут.

-  Для выполнения этой процедуры (процедур) необходимы соответствующие разрешения. Чтобы узнать, какие разрешения необходимы, см. раздел о разрешениях инфраструктуры [Exchange и оболочки.](https://go.microsoft.com/fwlink/p/?LinkId=746511)

- Сочетания клавиш для процедур, описанных в этой статье, приведены в статье [Сочетания клавиш в Центре администрирования Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Сведения о совместимости см. в сведениях о совместимости Skype для [бизнеса с приложениями Office.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)

## <a name="configure-integration-between-exchange-server-and-o365"></a>Настройка интеграции между Exchange Server и O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Шаг 1. Настройка проверки подлинности OAuth между Exchange Server и O365

Выполните действия, которые необходимо выполнить в следующей статье:

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Шаг 2. Создание новой учетной записи пользователя почты для партнерского приложения Skype для бизнеса Online

Это делается на сервере Exchange Server. Он создаст пользователя почты и назначит ему соответствующие права роли управления. Эта учетная запись будет использоваться на следующем этапе.

Укажите проверенный домен для организации Exchange. Этот домен должен быть тем же доменом, который используется в качестве основного домена SMTP, используемого для учетных записей локальной exchange. Этот домен называется в \<your Verified Domain\> следующей процедуре. Кроме того, \<DomainControllerFQDN\> это должно быть FQDN контроллера домена.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Эта команда скрывает нового пользователя почты из списков адресов.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Следующие две команды назначят роль управления UserApplication и ArchiveApplication этой новой учетной записи.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Шаг 3. Создание и включить партнерского приложения для Skype для бизнеса Online 

Создайте новое партнерского приложения и будет использовать только что созданную учетную запись. Выполните следующую команду в командной консоли Exchange в своей локальной организации Exchange.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Шаг 4. Экспорт локального сертификата авторизации

Запустите сценарий PowerShell, чтобы экспортировать сертификат локальной авторизации, который будет импортироваться в организацию Skype для бизнеса Online на следующем шаге.

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

В Exchange PowerShell в локальной организации Exchange запустите созданный сценарий PowerShell. Например: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Шаг 5. Отправка локального сертификата авторизации в службу acS Azure Active Directory

Затем используйте Windows PowerShell для отправки локального сертификата авторизации, экспортируемого на предыдущем шаге, в службы контроля доступа Azure Active Directory (ACS). Для этого необходимо установить модуль Azure Active Directory для Windows PowerShell командлетов. Если он не установлен, перейдите на страницу [https://aka.ms/aadposh](https://aka.ms/aadposh), чтобы установить Модуль Azure Active Directory для Windows PowerShell. После установки Модуль Azure Active Directory для Windows PowerShell выполните следующие действия.

1. Щелкните ярлык **Модуль Azure Active Directory для Windows PowerShell**, чтобы открыть рабочее пространство Windows PowerShell с установленными командлетами Azure AD. Все команды на этом этапе выполняются с помощью Windows PowerShell для консоли Azure Active Directory.

2. Сохраните следующий текст в файл сценария PowerShell с именем,  `UploadAuthCert.ps1` например.

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

4. После запуска сценария откроется диалоговое окно учетных данных. Введите учетные данные для учетной записи администратора клиента вашей организации Microsoft Online Azure AD. После выполнения сценария оставьте сеанс Windows PowerShell для Azure AD открытым. Он понадобится для запуска сценария PowerShell на следующем этапе.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Шаг 6. Убедитесь, что сертификат загружен в основное приложение-службу Skype для бизнеса
1. В powerShell, открытой и с проверкой подлинности в Azure Active Directory, запустите следующую
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Нажмите ввод при запросе returnKeyValues
3. Подтвердите, что в списке указан ключ с данными начала и окончания, которые совпадают с датой начала и окончания сертификата Oauth Exchange

### <a name="verify-your-success"></a>Проверка успешности

Проверьте правильность конфигурации, проверив, что некоторые функции работают успешно. 

1. Подтвердим, что пользователи Skype для бизнеса со службой облачной голосовой почты в организации с гибридной конфигурацией Exchange Server могут успешно изменить приветствия голосовой почты.

2. Подтвердим, что история бесед для мобильных клиентов отображается в папке "История бесед Outlook".

3. Подтвердим, что архивные сообщения чата находятся в локальном почтовом ящике пользователя в папке "Очистка" с помощью [EWSEditor.](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)

Кроме того, посмотрите на трафик. Трафик при рукопожатии OAuth очень разнообразен (и не похож на базовую проверку подлинности), особенно вокруг областей, где вы увидите трафик, который будет выглядеть так: 000000004-0000-0ff1-ce00-000000000000@ (иногда со знаком /перед знаком @) в передаваемом маркере. Вы не увидите имя пользователя или пароль, который является точкой OAuth. But you will see the 'Office' issuer ( in this case '4' is Skype for Business ) and the realm of your subscription.

Если вы хотите убедиться, что вы успешно используете OAuth, убедитесь, что вы знаете, чего ожидать, и как должен выглядеть трафик. Вот чего [ожидать.](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)Вот довольно стандартный пример трафика [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  в приложении Майкрософт (действительно полезно читать, хотя в нем не используются маркеры обновления), и существуют расширения Fiddler, которые будут позволять вам посмотреть на ваш OAuth JWT (веб-маркер JSON).

Вот пример [настройки,](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)но вы можете использовать любое средство сетевой трассиации, для этого необходимо.

## <a name="related-topics"></a>Статьи по теме

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
