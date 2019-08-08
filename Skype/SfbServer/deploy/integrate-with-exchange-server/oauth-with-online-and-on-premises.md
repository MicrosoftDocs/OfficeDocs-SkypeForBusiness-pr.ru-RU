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
ms.openlocfilehash: 3c896e8b430276e5bb48bc425425292a382a1021
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244223"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Настройка интеграции и OAuth между Skype для бизнеса Online и Exchange Server 

Настройка интеграции между Exchange Server и Skype для бизнеса Online включает возможности интеграции Skype для бизнеса и Exchange, описанные в разделе [Поддержка функций](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Эта статья относится к интеграции с Exchange Server 2013 – 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы?

- Предполагаемое время выполнения этой задачи: 15 минут

-  Перед выполнением этих процедур вы должны получить разрешения. Чтобы узнать, какие разрешения вам нужны, ознакомьтесь с разделом [разрешения для инфраструктуры Exchange и оболочки](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в разделе сочетания [клавиш в центре администрирования Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Сведения о совместимости можно найти [в разделе Совместимость Skype для бизнеса с приложениями Office](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Настройка интеграции между сервером Exchange Server и Office 365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Действие 1: Настройка проверки подлинности OAuth между Exchange Server и O365

Выполните действия, описанные в приведенной ниже статье.

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Действие 2: создание учетной записи пользователя для приложения-партнера Skype для бизнеса Online

Это действие выполняется на сервере Exchange Server. На этом шаге создается пользователь почты, которому назначаются соответствующие права роли управления. Затем эта учетная запись используется на следующем шаге.

Укажите проверенный домен для организации Exchange. Этот домен должен быть тем же доменом, который используется в качестве основного домена SMTP для локальных учетных записей Exchange. Этот домен называется \<проверяемым доменом\> в описанной ниже процедуре. Кроме того, \<домаинконтроллерфкдн\> должно быть полным доменным именем контроллера домена.

``` Powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Эта команда скрывает нового пользователя почты из списка адресов.

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Следующие две команды назначают новой учетной записи роль управления UserApplication и ArchiveApplication.

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Шаг 3: создание и включение приложения-партнера для Skype для бизнеса Online 

Создайте новое партнерское приложение и начните использовать созданную учетную запись. Выполните следующую команду в PowerShell Exchange в локальной организации Exchange.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Шаг 4: экспорт локального сертификата авторизации

Запустите сценарий PowerShell для экспорта локального сертификата авторизации, который вы будете импортировать в организацию Skype для бизнеса Online, на следующем этапе.

Сохраните следующий тест в файл сценария PowerShell, который можно назвать ExportAuthCert.ps1.

``` Powershell
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

В Exchange PowerShell в локальной организации Exchange выполните созданный сценарий PowerShell. Например: .\ExportAuthCert.ps1

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Шаг 6. Отправьте локальный сертификат авторизации в Azure Active Directory ACS

Далее, используя Windows PowerShell, отправьте локальный сертификат авторизации, экспортированный на предыдущем шаге, в службу управления доступом Azure Active Directory (ACS). Перед выполнением этого действия необходимо установить командлеты модуля Azure Active Directory Module для Windows PowerShell. Если он не установлен, перейдите в раздел [https://aka.ms/aadposh](https://aka.ms/aadposh) для установки модуля Azure Active Directory для Windows PowerShell. После установки модуля Azure Active Directory для Windows PowerShell выполните следующие действия.

1. Нажмите на ярлык **Модуль Azure Active Directory для Windows PowerShell**, чтобы открыть рабочую область Windows PowerShell с установленными командлетами Azure AD. Все команды на этом шаге должны быть выполнены с помощью консоли Windows PowerShell для Azure Active Directory.

2. Сохраните приведенный ниже текст в файле сценария PowerShell (например,) `UploadAuthCert.ps1`.

   ``` Powershell
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

3. Запустите сценарий PowerShell, созданный на предыдущем шаге. Например:`.\UploadAuthCert.ps1`

4. После запуска сценария появится диалоговое окно для ввода учетных данных. Введите данные учетной записи администратора клиента вашей организации Microsoft Online Azure AD. После выполнения сценария оставьте сеанс работы Windows PowerShell для Azure AD открытым. Он будет использоваться для запуска сценария PowerShell на следующем шаге.

### <a name="step-7-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Шаг 7: Проверка того, что сертификат передан участникам службы Skype для бизнеса
1. В PowerShell, который был открыт и прошел проверку подлинности в Azure Active Directory, выполните указанные ниже действия.
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. При появлении соответствующего запроса нажмите клавишу ВВОД Ретурнкэйвалуес
3. Убедитесь, что в списке указан ключ с датой начала и конечными данными, которые соответствуют датам начала и окончания сертификата в Exchange OAuth.

### <a name="verify-your-success"></a>Проверка успешности выполнения

Убедитесь в том, что конфигурация верна, проверьте, успешно ли работают некоторые функции. 

1. Убедитесь в том, что пользователи Skype для бизнеса с облачной службой голосовой почты в Организации с гибридной конфигурацией Exchange Server могут успешно изменить голосовую почту.

2. Убедитесь в том, что в папке "Журнал бесед" Outlook отображается журнал бесед для мобильных клиентов.

3. Убедитесь, что архивированные сообщения в чате помещены в почтовый ящик пользователя в локальной папке очистки с помощью [евседитор](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).

Кроме того, Взгляните на трафик. Трафик в подтверждении OAuth является весьма отличительным (и не рассматривается как обычная проверка подлинности), особенно вокруг сфер, где вы начнете просматривать трафик поставщика, выглядящий следующим образом: 00000004-0000-0ff1-ce00-000000000000 @ (иногда с a/Before знак "@") в токенах, которые передаются. Вы не увидите имя пользователя или пароль, который является точкой OAuth. Но вы увидите, что в этом случае это "4" — Skype для бизнеса — и сфера подписки.

Если вы хотите, чтобы вы успешно использовали OAuth, убедитесь, что вы знаете, что нужно ожидать и что нужно знать, как выглядит трафик. Итак, вот [что нужно ожидать](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34): Вот стандартный [пример трафика OAuth в приложении Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (это может оказаться полезным для чтения, но не использует маркеры обновления), и есть расширения Fiddler, позволяющие найти OAuth JWT (JSON). Веб-токен).

Ниже приведен [Пример настройки одного из них](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), но вы можете использовать любой сетевой инструмент трассировки, который вы хотите предпринять.

## <a name="related-topics"></a>Статьи по теме

[Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
