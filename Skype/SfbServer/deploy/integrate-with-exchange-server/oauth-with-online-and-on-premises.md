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
ms.openlocfilehash: ff7b45f3fcdbaaf752817d1705acb047a4c71f12
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568903"
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a>Настройка подключения по протоколу OAuth между Skype для бизнеса Online и локальной системой Exchange
 
Настройка OAuth проверки подлинности между Exchange при локальном и Скайп для бизнеса в Интернет позволяет Скайп для бизнеса и интеграция с Exchange, описанными в [функции поддержки](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).
  
Данный раздел относится к Exchange Server 2016 и Exchange Server 2013.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы?

- Предполагаемое время выполнения этой задачи: 15 минут
    
-  Перед выполнением этих процедур вы должны получить разрешения. Какие нужны разрешения см в разделе [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .
    
- Сведения о сочетаниях клавиш, которые могут относиться к процедур, описанных в этом разделе содержатся [сочетаний клавиш в центре администрирования Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).
    
## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a>Настройка проверки подлинности OAuth между локальным Exchange и организациями Skype для бизнеса

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a>Шаг 1. Создайте объект сервера авторизации для организации Skype для бизнеса Online

Укажите подтвержденным доменом вашей Скайп для бизнеса сети организации. Это должен быть тот же домен, который использовался в качестве основного домена SIP для облачных учетных записей. В этом домене называется \<домена проверены\> в следующей процедуре.
  
Выполните следующую команду в консоль управления Exchange (Exchange PowerShell) в своей локальной организации Exchange.
  
```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1" 
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a>Шаг 2. Включите партнерское приложение для организации Skype для бизнеса Online

Выполните следующую команду в Exchange PowerShell в своей локальной организации Exchange.
  
```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Шаг 3. Создайте новую учетную запись пользователя почты для партнерского приложения Skype для бизнеса Online

Этот шаг выполняется локально. На этом шаге создается пользователь почты, которому назначаются соответствующие права роли управления. Затем эта учетная запись используется на следующем шаге.
  
Укажите подтвержденным доменом в организации Exchange. Этот домен должен быть того же домена, используется в качестве основного домена SMTP, используемый для учетных записей Exchange в локальной. В этом домене называется \<домена проверены\> в следующей процедуре. Кроме того \<DomainControllerFQDN\> должно быть полное доменное имя контроллера домена. 
  
```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN> 
```

Эта команда скрывает нового пользователя почты из списка адресов.
  
```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN> 
```

Следующие две команды назначают новой учетной записи роль управления UserApplication и ArchiveApplication.
  
```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Шаг 4. Создайте и активируйте партнерское приложение для Skype для бизнеса Online

Создайте новое партнерское приложение и начните использовать созданную учетную запись. Выполните следующую команду в Exchange PowerShell в своей локальной организации Exchange. 
  
```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a>Шаг 5. Экспортируйте локальный сертификат авторизации

Выполнение скрипта PowerShell, чтобы экспортировать сертификат проверки подлинности в локальной, который импортируется на вашей Скайп для бизнеса в Интернет организации на следующем шаге.
  
Сохраните следующий тест в файл сценария PowerShell, который можно назвать ExportAuthCert.ps1.
  
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

В Exchange PowerShell в вашей локальной организации Exchange, выполнение скрипта PowerShell, который вы только что создали. Например:.\ExportAuthCert.ps1
  
### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Шаг 6. Отправьте локальный сертификат авторизации в Azure Active Directory ACS

Далее, используя Windows PowerShell, отправьте локальный сертификат авторизации, экспортированный на предыдущем шаге, в службу управления доступом Azure Active Directory (ACS). Перед выполнением этого действия необходимо установить командлеты модуля Azure Active Directory Module для Windows PowerShell. Если он не установлен, перейдите к разделу [https://aka.ms/aadposh](https://aka.ms/aadposh) Установка Azure модуль Active Directory для Windows PowerShell. После установки модуля Azure Active Directory для Windows PowerShell выполните следующие действия.
  
1. Нажмите на ярлык **Модуль Azure Active Directory для Windows PowerShell**, чтобы открыть рабочую область Windows PowerShell с установленными командлетами Azure AD. Все команды на этом шаге должны быть выполнены с помощью консоли Windows PowerShell для Azure Active Directory.
    
2. Сохраните следующий текст в файл сценария PowerShell с именем, например, `UploadAuthCert.ps1`.
    
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

3. Запустите сценарий PowerShell, созданный на предыдущем шаге. Например:`.\UploadAuthCert.ps1`
    
4. После запуска сценария появится диалоговое окно для ввода учетных данных. Введите данные учетной записи администратора клиента вашей организации Microsoft Online Azure AD. После выполнения сценария оставьте сеанс работы Windows PowerShell для Azure AD открытым. Он будет использоваться для запуска сценария PowerShell на следующем шаге.
    
### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a>Шаг 7. Зарегистрируйте источник имени хоста для домена SMTP

Укажите подтвержденным доменом в организации Exchange. Этот домен должен быть того же домена, используется в качестве основного домена SMTP, используемый для учетных записей Exchange в локальной. В этом домене называется \<домена проверены\> в следующей процедуре.
  
> [!NOTE]
> Для успешного выполнения следующего сценария требуется подключить Windows PowerShell для Azure Active Directory к клиенту Microsoft Online Azure AD, как описано на шаге 4 предыдущего раздела. 
  
1. Сохраните следующий тест в файл сценария PowerShell, который можно назвать RegisterEndpoints.ps1. В этом примере используется подстановочный знак для регистрации всех конечных точек contoso.com. Замените contoso.com сертификации имя узла для своей локальной организации Exchange
    
  ```
  $externalAuthority="*.<your Verified Domain>" 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName; 
$spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority); 
$p.ServicePrincipalNames.Add($spn); 
Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames; 
  ```

2.  В Windows PowerShell для Azure Active Directory выполните сценарий Windows PowerShell, созданный на предыдущем шаге. Например: `.\RegisterEndpoints.ps1`
    
### <a name="verify-your-success"></a>Проверка успешности выполнения

Проверьте правильность конфигурации OAuth, проверив работу отдельных функций, например, отображение журнала бесед для мобильных клиентов в папке журнала бесед Outlook.
  
1. Запустите Скайп для мобильных устройств бизнес-приложения на Windows Phone или устройства iOS и войдите в качестве Скайп для бизнеса в Интернет пользователя с помощью Exchange 2016 или локального почтового ящика Exchange 2013.
    
2. Иметь сеанс обмена мгновенными сообщениями с другой Скайп для бизнеса в Интернет пользователя.
    
3. Закройте окно беседы.
    
4. Запустите Outlook от имени этого пользователя и убедитесь, что беседа отображается в папке журнала бесед Outlook.
    

