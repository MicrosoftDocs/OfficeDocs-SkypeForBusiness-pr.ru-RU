---
title: Развертывание веб-клиентов, доступных для скачивания, в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Сводка: Развертывание Скайп для бизнеса Web App и использовать приложение Скайп собраний с Скайп для бизнеса.'
ms.openlocfilehash: e1cee2741e1538da1e4c5ed8e25509415cb16ac3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server-2015"></a>Развертывание веб-клиентов, доступных для скачивания, в Skype для бизнеса Server 2015
 
**Сводка:** Развертывание Скайп for Business Web App и использовать приложение Скайп собраний с Скайп для бизнеса.
  
Скайп для бизнеса Web App — это клиент web Internet Information Services (IIS), установленной на сервере с Скайп Business Server 2015 и по умолчанию при развертывании по запросу пользователям собрания, которые еще не Скайп для клиента Business. Эти пользователи собрания не чаще, чем не подключении за пределами вашей сети. Каждый раз, когда пользователь щелкает URL-адрес собрания, но не имеет Скайп для установки клиента Business, пользователю предоставляется возможность присоединения к собранию с помощью последней версии Скайп для бизнеса Web App.
  
Голосовой связи, видеозаписи и общего доступа компонентов в Скайп Business Web App требуется элемент управления Microsoft ActiveX, который используется в качестве подключаемый модуль, браузер пользователя. Можно установить элемент управления ActiveX заранее или запретить пользователям устанавливать его при получении запроса, что происходит при первом использовании Скайп для бизнеса Web App или первый раз, они получают доступ к компонента, который требуется элемент управления ActiveX.
  
> [!NOTE]
> В Скайп для развертываний пограничного сервера Business Server 2015 HTTPS обратного прокси-сервер в сети периметра необходим для Скайп для бизнес-приложение Web клиентского доступа. Помимо этого, необходимо опубликовать простые URL-адреса. Дополнительные сведения см [Параметр копирование обратного прокси-серверы](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) и [планированию для простых URL-адресов](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx). 
  
## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Включение многофакторной проверки подлинности для Скайп для бизнеса Web App
<a name="MFA"> </a>

Скайп Business Server 2015 версии Скайп для бизнеса Web App поддерживает многофакторной проверки подлинности. В дополнение к имени пользователя и пароля может потребовать дополнительную проверку подлинности методы, такие как смарт-карты или ПИН-коды, для проверки подлинности пользователей, у которых присоединение из внешних сетей, когда выполняют вход в систему Скайп для собраний Business. Можно включить многофакторной проверки подлинности, развертывания сервера федерации службы федерации Active Directory (AD FS), а также включение пассивной проверки подлинности в Скайп для Business Server 2015. После настройки AD FS внешние пользователи, попытались присоединиться к Скайп для деловых встреч, изучите AD FS многофакторной проверки подлинности веб-страница, содержащая имя пользователя и пароль вызов вместе с любые дополнительные методы проверки подлинности, которые вы настроены.
  
> [!IMPORTANT]
> Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации. 
  
- Многофакторная проверка подлинности службы федерации Active Directory действует в том случае, если как участник, так и организатор собрания относятся к одной организации (в том числе с федерацией AD FS). Многофакторная проверка подлинности службы федерации Active Directory не действует для федеративных пользователей Lync, так как веб-инфраструктура сервера Lync не поддерживает такую возможность в настоящий момент.
    
- Если вы используете аппаратных балансировщиков нагрузки, включите сохраняемость файлов cookie на подсистемы балансировки нагрузки, чтобы все запросы от Скайп для клиента Business Web App обрабатывались одним сервером переднего плана.
    
- При создании доверия с проверяющей стороной между Скайп для серверов Business Server и служб AD FS назначение маркеров жизненного, являющийся достаточно охватывать Максимальная длина вашей Скайп для деловых встреч. Как правило, 240 минут бывает достаточно.
    
- Эта конфигурация не действует для мобильных клиентов Lync.
    
### <a name="configure-multi-factor-authentication"></a>Настройка многофакторной проверки подлинности

1. Установите роль сервера федерации служб федерации Active Directory. Дополнительные сведения можно найти в [Active Directory Federation Services 2.0 руководство по развертыванию](https://go.microsoft.com/fwlink/p/?linkid=267511)
    
2. Создайте сертификаты для служб федерации Active Directory. Для получения дополнительных сведений см раздел [«Сертификаты сервера федерации»](https://go.microsoft.com/fwlink/p/?LinkId=285376) планирование для и развертывание службы федерации Active Directory для использования с разделом единого входа.
    
3. Интерфейс командной строки Windows PowerShell выполните следующую команду:
    
    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Установите партнерство, выполнив следующую команду:
    
    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Настройте следующие правила проверяющей стороны:
    
    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   ```
 
   ```
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   ```

   ```
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Отключить функцию BranchCache 
<a name="MFA"> </a>

Компонент BranchCache в Windows 7 и Windows Server 2008 R2 могут мешать Скайп для веб-компонентов Business Web App. Чтобы предотвратить проблемы для Скайп для пользователей Business Web App, убедитесь, что не включен компонент BranchCache. 
  
Дополнительные сведения об отключении BranchCache, содержатся в руководстве по развертыванию BranchCache, который входит в формате Word в центре загрузки Майкрософт по [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?LinkId=268788) и в формате HTML в Windows Server 2008 R2 технической библиотеки в [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?LinkId=268789).
  
## <a name="verifying-skype-for-business-web-app-deployment"></a>Проверка Скайп по развертыванию Web App
<a name="MFA"> </a>

С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-API объединенных коммуникаций (UCWA). Подробные сведения о этот командлет [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) в Скайп для документации по консоли управления Business Server см.
  
## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Устранение неполадок при установке подключаемого модуля на Windows Server 2008 R2
<a name="MFA"> </a>

Если не удается установить подключаемый модуль на компьютере под управлением Windows Server 2008 R2, может потребоваться изменить параметр безопасности Internet Explorer или реестра DisableMSI.
  
### <a name="modify-the-security-setting-in-internet-explorer"></a>Изменение параметра безопасности в Internet Explorer

1. Откройте Internet Explorer.
    
2. В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.
    
3. Перейдите к разделу **Безопасность**.
    
4. Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.
    
    > [!NOTE]
    > Если выбрано, этот параметр также приведет к ошибке при попытке загрузки вложения из Скайп для бизнеса Web App. 
  
5. Присоединитесь к собранию повторно. Подключаемый модуль должен загрузиться без ошибок.
    
### <a name="modify-the-disablemsi-registry-setting"></a>Изменение параметра реестра DisableMSI

1. В меню **Пуск** выберите пункт **Выполнить**.
    
2. Чтобы открыть редактор реестра, введите команду **regedit**.
    
3. Перейдите к разделу HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.
    
4. Измените или добавьте параметр реестра DisableMSI типа REG_DWORD и задайте для него значение 0.
    
5. Присоединитесь к собранию повторно.
    
## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional"></a>Включение приложения для собраний Skype с целью замены Skype для бизнеса Web App (необязательно)
<a name="SMA_Enable"> </a>

Эта процедура является необязательной. Если он не используется, для присоединения к собраниям с помощью Скайп для бизнеса Web App будет предоставляться внешних пользователей. 
  
### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Включение упрощенного присоединения к собранию и приложения для собраний Skype

1. При включении доступа для доставки содержимого сети (CDN), пользователи будут иметь возможность подключения к сети CDN Интернет-версия и получить приложение Скайп собраний и будет использовать упрощенный интерфейса присоединения к собранию. 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Разрешить клиенту со стороны ведение журнала телеметрии из собрания присоединиться к веб-страницу или приложение собраний Скайп отправку для серверов Microsoft (команду Параметры по умолчанию значение false). 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Данные отправляются в корпорацию Майкрософт — в строгом соответствии с [Скайп для коллекции данных бизнес-процессов](https://support.office.com/en-us/article/Skype-for-Business-data-collection-practices-c17e8ea6-b83b-4345-9401-47a6c8b13aad?ui=en-US&amp;rs=en-US&amp;ad=US).
    
3. Задайте время ожидания перед попадающих вернуться к локально размещаемого Скайп для бизнес-приложение Web программой Если CDN недоступен. По умолчанию установлено значение 6 с. Если установлено значение 0, никакого времени ожидания не будет.
    
   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.
<a name="SMA_Enable"> </a>

#### 

[Планирование для клиентов собрания (веб-приложения и приложения собрания)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
  
[Планирование для клиентов собрания (веб-приложения и приложения собрания)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
#### 

[Настройка страницы присоединения к собранию](http://technet.microsoft.com/library/45880423-47f4-49af-b825-cbd8e3fc1046.aspx)
  
[Заявление о конфиденциальности Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)
  
[Условия лицензионного соглашения и документация](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)

