---
title: Интеграция Skype для бизнеса Online и Exchange Server
ms.reviewer: cbland
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/17/2022
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Настройка проверки подлинности OAuth между локальной службой Exchange и Skype для бизнеса Online позволяет использовать функции интеграции Skype для бизнеса и Exchange, описанные в разделе поддержки функций.
ms.openlocfilehash: 0b312dfde144f12a9c2db523ce4526153b445d59
ms.sourcegitcommit: e3931446943684db155bb3edf7d7e52d41775013
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2022
ms.locfileid: "65886646"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Настройка интеграции и OAuth между Skype для бизнеса Online и Exchange Server 

Настройка интеграции между Exchange Server и Skype для бизнеса Online позволяет использовать функции интеграции Skype для бизнеса и Exchange, описанные в разделе поддержки [компонентов](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Этот раздел относится к интеграции с Exchange Server 2013–2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Предполагаемое время выполнения задачи: 15 минут.

-  Для выполнения этой процедуры (процедур) необходимы соответствующие разрешения. Сведения о необходимых разрешениях см. в разделе о разрешениях [инфраструктуры Exchange и Оболочки](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) .

- Сочетания клавиш для процедур, описанных в этой статье, приведены в статье [Сочетания клавиш в Центре администрирования Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Сведения о совместимости см. в статье о совместимости [Skype для бизнеса с приложениями Office](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Настройка интеграции между Exchange Server и O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Шаг 1. Настройка проверки подлинности OAuth между Exchange Server и O365

Выполните действия, описанные в следующей статье:

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Шаг 2. Создание учетной записи почтового пользователя для партнерского приложения Skype для бизнеса Online

Этот шаг выполняется на сервере Exchange Server. Он создаст почтового пользователя и назначит ему соответствующие права роли управления. Эта учетная запись будет использоваться на следующем шаге.

Укажите проверенный домен для организации Exchange. Этот домен должен быть тем же доменом, который используется в качестве основного домена SMTP, используемого для локальных учетных записей Exchange. Этот домен называется в \<your Verified Domain\> следующей процедуре. Кроме того, должно \<DomainControllerFQDN\> быть полное доменное имя контроллера домена.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Эта команда скрывает нового почтового пользователя из списков адресов.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Следующие две команды назначит роль управления UserApplication и ArchiveApplication этой новой учетной записи.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Шаг 3. Создание и включение партнерского приложения для Skype для бизнеса Online 

Создайте новое партнерское приложение и будете использовать только что созданную учетную запись. Выполните следующую команду в командной консоли Exchange в своей локальной организации Exchange.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Шаг 4. Экспорт локального сертификата авторизации

Запустите сценарий PowerShell, чтобы экспортировать локальный сертификат авторизации, который будет импортирован в организацию Skype для бизнеса Online на следующем шаге.

Сохраните следующий текст в файл сценария PowerShell с именем ExportAuthCert.ps1.

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false) {
    md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

В Exchange PowerShell в локальной организации Exchange запустите только что созданный сценарий PowerShell. Например, .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Шаг 5. Отправка локального сертификата авторизации в Azure Active Directory ACS

Затем используйте Windows PowerShell для отправки локального сертификата авторизации, экспортированного на предыдущем шаге, в службы контроля доступа Azure Active Directory (ACS). Для этого необходимо установить модуль Azure Active Directory для Windows PowerShell. Если он не установлен, перейдите на страницу [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)), чтобы установить Модуль Azure Active Directory для Windows PowerShell. После установки Модуль Azure Active Directory для Windows PowerShell выполните следующие действия.

1. Щелкните ярлык **Модуль Azure Active Directory для Windows PowerShell**, чтобы открыть рабочее пространство Windows PowerShell с установленными командлетами Azure AD. Все команды на этом этапе выполняются с помощью Windows PowerShell для консоли Azure Active Directory.

2. Сохраните следующий текст в файл скрипта PowerShell с именем,  `UploadAuthCert.ps1`например.

   ```powershell
   Connect-MsolService
   Import-Module MSOnline
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile)
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert)
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000"
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. Выполните сценарий PowerShell, созданный на предыдущем этапе. Например:  `.\UploadAuthCert.ps1`

4. После запуска сценария откроется диалоговое окно учетных данных. Введите учетные данные для учетной записи администратора клиента организации Microsoft Online Azure AD. После выполнения сценария оставьте сеанс Windows PowerShell для Azure AD открытым. Он понадобится для запуска сценария PowerShell на следующем этапе.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Шаг 6. Проверка отправки сертификата в субъект-службу Skype для бизнеса
1. В powerShell, открытом и прошедшем проверку подлинности в Azure Active Directory, выполните следующую команду:

   ```powershell
   Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
   ```
2. Нажмите клавишу ВВОД при появлении запроса returnKeyValues
3. Убедитесь, что в списке указан ключ с датой начала и окончания, который соответствует дате начала и окончания сертификата Oauth Exchange.

### <a name="verify-your-success"></a>Проверка успешности

Убедитесь, что конфигурация правильная, проверив, что некоторые функции работают успешно. 

1. Убедитесь, что пользователи Skype для бизнеса со службой облачной голосовой почты в организации с гибридной конфигурацией Exchange Server могут успешно изменять приветствия голосовой почты.

2. Убедитесь, что журнал бесед для мобильных клиентов отображается в папке "Журнал бесед Outlook".

3. Убедитесь, что архивированные сообщения чата помещаются в локальный почтовый ящик пользователя в папке Purges с помощью [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).

Кроме того, просмотрите свой трафик. Трафик в подтверждении OAuth действительно отличается (и не похож на обычную проверку подлинности), особенно вокруг областей, где вы начнете видеть трафик издателя, который выглядит следующим образом: 000000004-0000-0ff1-ce00-000000000000@ (иногда с /перед знаком @) в передаваемых маркерах. Вы не увидите имя пользователя или пароль, который является точкой OAuth. Но вы увидите издателя Office ( в данном случае "4" — Skype для бизнеса) и область вашей подписки.

Если вы хотите убедиться, что вы успешно используете OAuth, убедитесь, что знаете, что ожидать и как должен выглядеть трафик. Вот что следует [ожидать. Ниже](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34) приведен довольно стандартный пример трафика [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  в приложении Майкрософт (который очень полезен для чтения, хотя он не использует маркеры обновления), и существуют расширения Fiddler, которые позволяют просмотреть веб-маркер OAuth JWT (JSON Web Token).

Ниже приведен пример [настройки](/archive/blogs/kaevans/updated-fiddler-oauth-inspector), но вы можете использовать любое средство трассировки сети, которое вы хотите выполнить.

## <a name="related-topics"></a>Статьи по теме

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
