---
title: 'Lync Server 2013: развертывание Lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7415be2210e6c791434ced8af8f309b49603e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Развертывание Lync Web App в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-07-18_

Lync Web App — это веб-клиент служб IIS, который устанавливается вместе с Lync Server 2013 и включен по умолчанию. Чтобы включить Lync Web App на сервере или развернуть веб-клиент для пользователей, никаких дополнительных действий не требуется. Каждый раз, когда пользователь щелкает URL-адрес собрания, но на нем не установлен клиент Lync 2013, пользователю предоставляется возможность присоединиться к собранию с помощью последней версии Lync Web App.

Для использования функций голосового и видеозвонков в Lync Web App требуется элемент управления Microsoft ActiveX. Вы можете установить элемент ActiveX заранее или разрешить пользователям устанавливать его при появлении соответствующего запроса, что происходит при первом использовании Lync Web App или при первом доступе к функции, для которой требуется элемент ActiveX.

<div class=" ">


> [!NOTE]  
> В Lync Server 2013 развертывание пограничного сервера — обратный прокси-сервер HTTPS в демилитаризованной зоне требуется для доступа клиентов Lync Web App. Помимо этого, необходимо опубликовать простые URL-адреса. Подробнее: <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратного прокси-серверов для Lync server 2013</A> и <A href="lync-server-2013-planning-for-simple-urls.md">планирование простых URL-адресов в Lync Server 2013</A>.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Включение многофакторной проверки подлинности для Lync Web App

В версии Lync Server 2013 для Lync Web App поддерживается многофакторная проверка подлинности. Помимо имени пользователя и пароля, для проверки подлинности пользователей, присоединяющихся к собраниям Lync, вы можете потребовать дополнительные методы проверки подлинности, например смарт-карты или контакты. Вы можете включить многофакторную проверку подлинности, развернув сервер федерации служб федерации Active Directory (AD FS) и включив пассивную проверку подлинности в Lync Server 2013. После настройки AD FS внешние пользователи, пытающиеся присоединиться к собраниям Lync, будут представлены на веб-странице многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также любые дополнительные способы проверки подлинности, которые вы настроили. .

<div class=" ">


> [!IMPORTANT]  
> Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации. 
> <UL>
> <LI>
> <P>Многофакторная проверка подлинности службы федерации Active Directory действует в том случае, если как участник, так и организатор собрания относятся к одной организации (в том числе с федерацией AD FS). Многофакторная проверка подлинности службы федерации Active Directory не действует для федеративных пользователей Lync, так как веб-инфраструктура сервера Lync не поддерживает такую возможность в настоящий момент.</P>
> <LI>
> <P>Если вы используете подсистемы балансировки нагрузки для оборудования, включите сохраняемость файлов cookie в подсистемах балансировки нагрузки, чтобы все запросы из клиента Lync Web App обрабатывались на одном и том же внешнем сервере.</P>
> <LI>
> <P>Если вы устанавливаете отношение доверия проверяющей стороны между сервером Lync Server и серверами AD FS, назначьте жизненный цикл, достаточно длинный, чтобы занимать максимальную длину собраний Lync. Как правило, 240 минут бывает достаточно.</P>
> <LI>
> <P>Эта конфигурация не действует для мобильных клиентов Lync.</P></LI></UL>



</div>

**Настройка многофакторной проверки подлинности**

1.  Установите роль сервера федерации служб федерации Active Directory. Подробные сведения можно найти в руководстве по развертыванию служб федерации Active Directory 2,0 на странице<http://go.microsoft.com/fwlink/p/?linkid=267511>

2.  Создайте сертификаты для служб федерации Active Directory. Для получения дополнительных сведений ознакомьтесь с разделом "сертификаты серверов федерации" плана и развертывания AD FS для использования с темой единого входа [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).

3.  В интерфейсе командной строки Windows PowerShell выполните следующую команду:
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  Установите партнерство, выполнив следующую команду:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Настройте следующие правила проверяющей стороны:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a>Настройка BranchCache

Функция BranchCache в Windows 7 и Windows Server 2008 R2 может повлиять на веб-компоненты Lync Web App. Чтобы не допустить проблем для пользователей Lync Web App, убедитесь, что служба BranchCache не включена.

Подробнее об отключении BranchCache можно узнать в руководстве по развертыванию BranchCache, которое доступно в формате Word в центре загрузки Майкрософт по [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) адресу и в формате HTML в технической библиотеке Windows Server 2008 R2 [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)по адресу.

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Проверка развертывания Lync Web App

С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-API объединенных коммуникаций (UCWA). Подробнее об этом командлете можно найти в разделе [Test-ксукваконференце](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) в документации по среде управления Lync Server.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Устранение неполадок при установке модулей в Windows Server 2008 R2

Если установка надстройки завершается сбоем на компьютере под управлением Windows Server 2008 R2, возможно, потребуется изменить параметр безопасности Internet Explorer или параметр раздела реестра Дисаблемси.

**Изменение параметров безопасности в Internet Explorer**

1.  Откройте Internet Explorer.

2.  В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.

3.  Перейдите к разделу **Безопасность**.

4.  Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.
    
    <div class=" ">
    

    > [!NOTE]  
    > Если флажок установлен, этот параметр также приведет к ошибке при попытке загрузить вложение из Lync Web App.

    
    </div>

5.  Присоединитесь к собранию повторно. Подключаемый модуль должен загрузиться без ошибок.

**Изменение параметра реестра Дисаблемси**

1.  В меню **Пуск** выберите пункт **Выполнить**.

2.  Чтобы открыть редактор реестра, введите команду **regedit**.

3.  \_Перейдите к политикам\_\\\\\\программного обеспечения локального\\компьютера\\(hKey) установщика Microsoft Windows.

4.  Измените или добавьте раздел реестра Дисаблемси для типа REG\_(DWORD) и установите для него значение 0.

5.  Присоединитесь к собранию повторно.

</div>

<div>

## <a name="see-also"></a>См. также


[Конфигурация страницы присоединения к собранию в Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Платформы, поддерживаемые Lync Web App для Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

