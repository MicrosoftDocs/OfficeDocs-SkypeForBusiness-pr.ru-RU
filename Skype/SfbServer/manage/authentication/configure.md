---
title: Настройка двухфакторной проверки подлинности в Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Summary: Configure two-factor authentication in Skype for Business Server 2015.'
ms.openlocfilehash: edd32559a136573e7b3cf1fe5dc3a153ce0eb61c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server-2015"></a>Настройка двухфакторной проверки подлинности в Skype для бизнеса Server 2015
 
**Summary:** Configure two-factor authentication in Skype for Business Server 2015.
  
В следующих разделах приведена пошаговая процедура настройки двухфакторной проверки подлинности для развертывания. For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).
  
## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Настройка корневого центра сертификации на предприятии для проверки подлинности с помощью смарт-карт

Ниже описан порядок действий по настройке корневого ЦС предприятия для проверки подлинности с помощью смарт-карт.
  
For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).
  
1. Войдите на компьютер ЦС предприятия с учетной записью администратора домена.
    
2. Запустите приложение System Manager и убедитесь в том, что установлена роль регистрации сертификатов через Интернет.
    
3. В меню **Администрирование** откройте консоль управления **Центр сертификации**.
    
4. В области навигации разверните элемент **Центр сертификации**.
    
5. Щелкните правой кнопкой **Шаблоны сертификатов** и выберите **Создать**, затем **Выдаваемый шаблон сертификата**.
    
6. Выберите **Агент подачи заявок**, **Пользователь со смарт-картой** и **Вход со смарт-картой**.
    
7. Нажмите **ОК**.
    
8. Щелкните **Шаблоны сертификатов** правой кнопкой мыши.
    
9. Выберите **Управление**.
    
10. Откройте свойства шаблона пользователя смарт-карты.
    
11. Перейдите на вкладку **Безопасность**.
    
12. Задайте указанные ниже разрешения.
    
    - Добавьте учетные записи отдельных пользователей Active Directory с разрешениями на чтение и подачу заявок (разрешить).
    
    - Добавьте группу безопасности с пользователями смарт-карт, обладающую разрешениями на чтение и подачу заявок (разрешить).
    
    - Добавьте группу пользователей домена с разрешениями на чтение и подачу заявок (разрешить).
    
## <a name="configure-windows-8-for-virtual-smart-cards"></a>Настройка Windows 8 для виртуальных смарт-карт

Одним их факторов, которые следует учитывать при развертывании двухфакторной проверки подлинности и технологии смарт-карт, является его стоимость. Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.
  
Если компьютеры оборудованы микросхемами доверенного платформенного модуля (TPM), соответствующими спецификации версии 1.2, организации могут пользоваться преимуществами регистрации по смарт-картам без дополнительных капиталовложений в оборудование. For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).
  
### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Настройка конфигурации Windows 8 для виртуальных смарт-карт

1. Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.
    
2. На начальном экране Windows 8 переместите курсор в нижний правый угол.
    
3. Select the **Search** option, and then search forCommand Prompt.
    
4. Щелкните **Командная строка** правой кнопкой мыши, затем выберите **Запуск от имени администратора**.
    
5. Откройте консоль управления TPM, выполнив следующую команду:
    
  ```
  Tpm.msc
  ```

6. Убедитесь в том, что спецификация вашего TPM имеет версию 1.2 или выше.
    
    > [!NOTE]
    > При появлении диалогового окна с сообщением, что совместимый TPM не найден, убедитесь в том, что ваш компьютер имеет совместимый модуль TPM и что он включен в BIOS компьютера. 
  
7. Закройте консоль управления TPM
    
8. Создайте новую виртуальную смарт-карту, введя в командную строку следующую команду:
    
  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Чтобы сообщить настраиваемое значение ПИН-кода, используйте ключ командной строки /pin. 
  
9. Откройте консоль управления компьютером, введя в командную строку следующую команду:
    
  ```
  CompMgmt.msc
  ```

10. В консоли управления компьютером выберите **Управление устройствами**.
    
11. Разверните элемент **Устройства чтения смарт-карт**.
    
12. Убедитесь в том, что создание нового устройства для чтения виртуальной смарт-карты успешно завершено.
    
## <a name="enroll-users-for-smart-card-authentication"></a>Регистрация пользователей для проверки подлинности по смарт-карте

Зарегистрировать пользователей для проверки подлинности с помощью смарт-карты можно двумя способами. Простой вариант — поручить пользователям самостоятельно зарегистрироваться с помощью функции регистрации через Интернет, в то время как сложный связан с использованием агента регистрации. В этом разделе рассматривается процедура самостоятельной регистрации для использования сертификатов смарт-карт.
  
For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).
  
### <a name="to-enroll-users-for-smart-card-authentication"></a>Порядок регистрации пользователей для проверки подлинности с помощью смарт-карты

1. Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.
    
2. Запустите браузер Internet Explorer.
    
3. Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).
    
    > [!NOTE]
    > В браузере Internet Explorer 10 эту страницу, возможно, потребуется открыть в режиме совместимости. 
  
4. На странице **приветствия** выберите **Запросить сертификат**.
    
5. Затем выберите **Расширенный запрос**.
    
6. Выберите **Создать и выдать запрос к этому ЦС**.
    
7. В разделе **Шаблон сертификата** выберите **Пользователь смарт-карты** и введите в полях расширенного запроса сертификата следующие значения.
    
  - В разделе **Параметры ключа** задайте следующие значения.
    
    - Установите переключатель в положение **Создать новый набор ключей**.
    
    - Для параметра **Поставщик служб шифрования** выберите значение **Базовый поставщик криптографии смарт-карт (Microsoft)**.
    
    - Для параметра **Использование ключа** выберите значение **Обмен** (единственное доступное значение).
    
    - For **Key Size**, enter 2048
    
    - Убедитесь в том, что флажок **Автоматическое имя контейнера ключа** установлен.
    
    - Оставьте остальные флажки снятыми.
    
  - В разделе **Дополнительные параметры** задайте следующие значения.
    
    - Для параметра **Формат запроса** выберите значение **CMC**.
    
    - Для параметра **Алгоритм хэширования** выберите значение **sha1**.
    
    - For **Friendly Name** enterSmardcard Certificate.
    
8. Если используется физическое устройство считывания смарт-карт, вставьте смарт-карту в устройство.
    
9. Нажмите кнопку **Отправить** для отправки запроса сертификата.
    
10. Когда будет предложено, введите ПИН-код, использовавшийся при создании виртуальной смарт-карты.
    
    > [!NOTE]
    > The default virtual smart card PIN value is '12345678'. 
  
11. После выдачи сертификата щелкните **Установить этот сертификат** для завершения процедуры регистрации.
    
    > [!NOTE]
    >  If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:
  
        a. Enable Compatibility View in Internet Explorer 
        b. Enable the Turn on Intranet settings option in Internet Explorer 
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.
  
## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Настройка служб федерации Active Directory (AD FS 2.0)

В этом разделе рассматривается настройка служб федерации Active Directory (AD FS 2.0) для поддержки многофакторной проверки подлинности. For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).
  
> [!NOTE]
> При установке AD FS 2.0 не добавляйте роль службы федерации Active Directory с помощью диспетчера серверов Windows. Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375). 
  
### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Настройка AD FS для двухфакторной проверки подлинности

1. Войдите в систему на компьютере с AD FS 2.0 с помощью учетной записи администратора домена.
    
2. Запустите Windows PowerShell.
    
3. Введите в командной строке Windows PowerShell следующую команду:
    
  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Установите партнерское отношение с каждым сервером, на котором будет разрешена пассивная проверка подлинности; для этого выполните следующую команду, указав имя сервера в конкретном развертывании:
    
  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Запустите консоль управления AD FS 2.0 в меню "Средства администрирования".
    
6. Expand **Trust Relationships** > **Relying Party Trusts**.
    
7. Verify that a new trust has been created for your Skype for Business Server.
    
8. С помощью Windows PowerShell и следующих команд создайте и назначьте для отношения доверия с проверяющей стороны правило утверждения авторизации:
    
  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth 
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. С помощью Windows PowerShell и следующих команд создайте и назначьте для отношения доверия с проверяющей стороны правило утверждения преобразования:
    
  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. В консоли управления AD FS 2.0 щелкните отношение доверия с проверяющей стороной правой кнопкой мыши и выберите команду **редактирования правил утверждений**.
    
11. Перейдите на вкладку **правил разрешения выпуска** и убедитесь в том, что новое правило разрешения успешно создано.
    
12. Перейдите на вкладку **правил преобразования выпуска** и убедитесь в том, что новое правило преобразования успешно создано.
    
## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Настройка AD FS 2.0 для поддержки проверки подлинности клиента

Чтобы разрешить в AD FS 2.0 поддержку проверки подлинности с использованием смарт-карт, можно настроить два указанных ниже типа проверки подлинности.
  
- Проверка подлинности на основе форм
    
- Проверка подлинности клиента по протоколу TLS
    
На основе проверки подлинности по формам можно разработать веб-страницу, где подлинность пользователей будет проверяться по имени и паролю или по смарт-карте и PIN‑коду. В этой статье рассматривается преимущественно реализация проверки подлинности клиента по протоколу TLS с помощью AD FS 2.0. For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).
  
### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Настройка AD FS 2.0 для поддержки проверки подлинности клиента

1. Войдите в систему на компьютере с AD FS 2.0 с помощью учетной записи администратора домена.
    
2. Запустите проводник.
    
3. Перейдите в папку C:\inetpub\adfs\ls
    
4. Сделайте резервную копию файла web.config.
    
5. Откройте файл web.config с помощью Блокнота.
    
6. В строке меню выберите **Правка**, затем **Найти**.
    
7. Search for \<localAuthenticationTypes\>.
    
    Обратите внимание, что здесь будут перечислены четыре типа проверки подлинности, по одному на строку.
    
8. Переместите строку, содержащую тип проверки подлинности TLSClient, в начало списка в разделе.
    
9. Сохраните и закройте файл web.config.
    
10. Запустите командную строку с повышенными привилегиями.
    
11. Перезапустите службу IIS, выполнив следующую команду:
    
  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Настройка пассивной проверки подлинности в Skype для бизнеса Server

The following section describes how to configure Skype for Business Server 2015 to support passive authentication. Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.
  
> [!NOTE]
> Заказчикам настоятельно рекомендуется включить пассивную проверку подлинности для регистратора и веб-служб на уровне служб. Включение пассивной проверки подлинности включена для регистратора и веб-служб на глобальном уровне с большой вероятностью приводит к сбоям проверки подлинности пользователей, входящих не с поддерживаемых клиентов для настольных компьютеров, во всей организации. 
  
### <a name="web-service-configuration"></a>Конфигурация веб-служб

Ниже описана процедура создания настраиваемой конфигурации веб-служб для директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.
  
### <a name="to-create-a-custom-web-service-configuration"></a>Порядок создания настраиваемой конфигурации веб-служб

1. Log in to your Skype for Business Server 2015 Front End server using a Skype for Business administrator account.
    
2. Launch the Skype for Business Server Management Shell.
    
3. From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:
    
  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > Значением полного доменного имени WsFedPassiveMetadataUri является имя службы федерации сервера AD FS 2.0. Значение имени службы федерации можно найти в консоли управления AD FS 2.0, щелкнув **Служба** в области навигации правой кнопкой мыши и затем выбрав **Изменить свойства службы федерации**. 
  
4. Проверьте правильность значений UseWsFedPassiveAuth и WsFedPassiveMetadataUri, выполнив следующую команду:
    
  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Для клиентов пассивная проверка подлинности является наименее предпочтительным способом проверки подлинности WebTicket. For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:
    
  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Убедитесь в том, что все остальные типы проверки подлинности успешно отключены, выполнив следующую команду:
    
  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Конфигурация прокси-сервера

When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service. Проверка подлинности по сертификату и в этом случае необходима для извлечения WebTicket клиентом, однако для службы регистратора необходимо отключить Kerberos и NTLM.
  
Ниже описана процедура создания настраиваемой конфигурации прокси-сервера для пограничных пулов, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.
  
### <a name="to-create-a-custom-proxy-configuration"></a>Порядок создания настраиваемой конфигурации прокси-сервера

1. From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server 2015 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:
    
  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
-UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" 
-UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Убедитесь, что все остальные типы проверки подлинности прокси-сервера успешно отключены, выполнив следующую команду:
    
  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com"
 | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>См. также

#### 

[Manage two-factor authentication in Skype for Business Server 2015](two-factor-authentication.md)
  
[Use two-factor authentication with Skype for Business client and Skype for Business Server 2015](use.md)

