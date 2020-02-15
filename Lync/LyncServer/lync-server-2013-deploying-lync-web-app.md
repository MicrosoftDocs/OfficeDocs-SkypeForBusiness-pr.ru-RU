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
ms.openlocfilehash: d4508c9c499b0219f754bf9815063f4b1210b811
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Развертывание Lync Web App в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-07-18_

Lync Web App — это веб-клиент служб IIS, устанавливаемый с Lync Server 2013 и включенный по умолчанию. Для включения Lync Web App на сервере или развертывания веб-клиента для пользователей не требуется выполнять какие-либо дополнительные действия. Когда пользователь щелкает URL-адрес собрания, но на нем не установлен клиент Lync 2013, пользователю предоставляется возможность присоединиться к собранию с помощью последней версии Lync Web App.

Функции голосовых, видео и общего доступа в Lync Web App требуют наличия элемента управления Microsoft ActiveX. Вы можете либо установить элемент управления ActiveX заранее, либо разрешить пользователям устанавливать его при появлении соответствующего запроса, что происходит при первом использовании Lync Web App или при первом доступе к функции, требующей элемента управления ActiveX.

<div class=" ">


> [!NOTE]  
> В развертываниях пограничных серверов Lync Server 2013 для клиентского доступа Lync Web App необходимо использовать обратный прокси-сервер HTTPS в сети периметра. Вам также нужно опубликовать простые URL-адреса. Дополнительную информацию можно узнать в статье <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратных прокси-серверов для Lync server 2013</A> и <A href="lync-server-2013-planning-for-simple-urls.md">планирование простых URL-адресов в Lync Server 2013</A>.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Включение многофакторной проверки подлинности для Lync Web App

Lync Server 2013 версии Lync Web App поддерживает многофакторную проверку подлинности. Помимо имени пользователя и пароля, для проверки подлинности пользователей, присоединяющихся к собраниям Lync, могут потребоваться дополнительные методы проверки подлинности, такие как смарт-карты или ПИН-коды. Вы можете включить многофакторную проверку подлинности, развернув сервер федерации службы федерации Active Directory (AD FS) и включив пассивную проверку подлинности в Lync Server 2013. После настройки AD FS внешние пользователи, пытающиеся присоединиться к собраниям Lync, отображаются с помощью веб-страницы многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также дополнительные методы проверки подлинности, настроенные .

<div class=" ">


> [!IMPORTANT]  
> Если вы планируете настроить службу федерации Active Directory для многофакторной проверки подлинности, учтите следующие рекомендации. 
> <UL>
> <LI>
> <P>Многофакторная проверка подлинности в службах ADFS работает, если участник и организатор собрания одновременно находятся в одной организации или в федеративной организации AD FS. Многофакторная проверка подлинности ADFS не работает для федеративных пользователей Lync, так как веб-инфраструктура Lync Server в настоящее время не поддерживает эту службу.</P>
> <LI>
> <P>Если вы используете аппаратные средства балансировки нагрузки, включите сохранение файлов cookie в подсистемах балансировки нагрузки, чтобы все запросы от клиента Lync Web App обрабатывались одним сервером переднего плана.</P>
> <LI>
> <P>При установке отношения доверия с проверяющей стороной между Lync Server и серверами AD FS назначьте срок действия маркера, достаточного для достижения максимальной длины собраний Lync. Как правило, 240 минут бывает достаточно.</P>
> <LI>
> <P>Эта конфигурация не применяется к мобильным клиентам Lync.</P></LI></UL>



</div>

**Настройка многофакторной проверки подлинности**

1.  Установите роль сервера федерации службы федерации Active Directory. Подробные сведения см. в руководстве по развертыванию служб федерации Active Directory 2,0 в<http://go.microsoft.com/fwlink/p/?linkid=267511>

2.  Создайте сертификаты для AD FS. Для получения дополнительных сведений обратитесь к разделу "сертификаты сервера федерации" плана for Active Directory для использования с одним входом в [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)разделе "планирование и развертывание AD FS".

3.  В интерфейсе командной строки Windows PowerShell выполните следующую команду:
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  Установите отношение доверия, выполнив следующую команду.
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Настройте правила проверяющей стороны.
    
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

Функция BranchCache в Windows 7 и Windows Server 2008 R2 может повлиять на веб-компоненты Lync Web App. Чтобы предотвратить возникновение проблем для пользователей Lync Web App, убедитесь, что служба BranchCache отключена.

Дополнительные сведения об отключении BranchCache содержатся в руководстве по развертыванию BranchCache, доступном в формате Word в центре загрузки Майкрософт по [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) адресу и в формате HTML в технической библиотеке Windows Server 2008 R2 [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)по адресу.

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Проверка развертывания Lync Web App

С помощью командлета Test-CsUcwaConference вы можете проверить возможность участия двух тестовых пользователей в конференции с использованием веб-интерфейса API объединенных коммуникаций (UCWA). Подробнее об этом командлете можно узнать в статье [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) в документации по консоли управления Lync Server.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Устранение неполадок при установке подключаемого модуля в Windows Server 2008 R2

Если при установке подключаемого модуля произошел сбой на компьютере под управлением Windows Server 2008 R2, может потребоваться изменить параметр безопасности Internet Explorer или раздел реестра параметр DisableMSI.

**Изменение параметра безопасности в Internet Explorer**

1.  Откройте Internet Explorer.

2.  В меню **Сервис** выберите пункт **Свойства обозревателя** и перейдите на вкладку **Дополнительно**.

3.  Перейдите к разделу **Безопасность**.

4.  Снимите флажок **Не сохранять зашифрованные страницы на диск** и нажмите кнопку **ОК**.
    
    <div class=" ">
    

    > [!NOTE]  
    > Если этот параметр выбран, то при попытке скачать вложение из Lync Web App будет возникнет ошибка.

    
    </div>

5.  Присоединитесь к собранию повторно. Подключаемый модуль должен загрузиться без ошибок.

**Изменение параметра реестра DisableMSI**

1.  В меню **Пуск** выберите пункт **Выполнить**.

2.  Чтобы открыть редактор реестра, введите **regedit**.

3.  Перейдите в раздел\_hKey\_программное\\обеспечение\\локального\\компьютера\\\\, установщик Microsoft Windows.

4.  Измените или добавьте раздел реестра параметр DisableMSI типа REG\_DWORD и присвойте ему значение 0.

5.  Присоединитесь к собранию повторно.

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка страницы присоединения к собранию в Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Платформы, поддерживаемые в Lync Web App для Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

