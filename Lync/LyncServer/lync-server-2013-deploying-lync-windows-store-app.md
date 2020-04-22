---
title: 'Lync Server 2013: развертывание приложения Lync Windows для магазина'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4478f60fc99304e7cf882ddec7951aa3625d74f2
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Развертывание приложения Lync Windows для магазина в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-12-03_

Прежде чем сделать приложение Lync Windows Store доступным для пользователей, убедитесь, что развертывание соответствует [требованиям к приложению для Магазина Windows Lync для Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md). Для получения дополнительных сведений о настройке Lync Server 2013 для поддержки приложения Lync Windows для магазина ознакомьтесь со статьей блогов "Автообнаружение Lync Server" и "Lync Windows Store [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966)" по адресу. После правильной настройки серверной среды можно направить пользователей на загрузку приложения Lync из Магазина Windows, выполнив поиск по словам "Lync".

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Включение многофакторной проверки подлинности для приложения Lync Windows для магазина

Накопительные пакеты обновления для Lync Server 2013: Июнь 2013 Добавление поддержки многофакторной проверки подлинности для клиентов приложений Магазина Windows для Lync. Помимо имени пользователя и пароля, для проверки подлинности внешних пользователей при входе в собрания Lync могут потребоваться дополнительные методы проверки подлинности, такие как смарт-карты или ПИН-коды. Чтобы включить многофакторную проверку подлинности, необходимо развернуть сервер федерации службы федерации Active Directory (AD FS) и включить пассивную проверку подлинности в Lync Server 2013. После настройки AD FS внешние пользователи, пытающиеся присоединиться к собраниям Lync, отображаются с помощью веб-страницы многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также дополнительные методы проверки подлинности, которые вы настроили.

<div class=" ">


> [!IMPORTANT]  
> Ниже приведены важные рекомендации по настройке служб федерации Active Directory для многофакторной проверки подлинности для приложения Lync Windows для магазина: 
> <UL>
> <LI>
> <P>Lync Server 2013 с накопительными пакетами обновления для Lync Server 2013: Июнь 2013 — обязательно по крайней мере. Для настольных клиентов Lync 2013 не требуется накопительный пакет обновления для Lync Server 2013: Июнь 2013, поэтому может показаться, что пассивная проверка подлинности работает, так как клиенты Lync 2013 могут пройти проверку подлинности. Однако процесс проверки подлинности для клиентов приложений Магазина Windows Lync не будет выполнен, и уведомления или сообщение об ошибке отображаться не будут.</P>
> <LI>
> <P>Сервер должен быть настроен таким образом, чтобы пассивная проверка подлинности — единственный предлагаемый тип проверки подлинности.</P>
> <LI>
> <P>Если вы используете аппаратные средства балансировки нагрузки, включите сохранение файлов cookie в подсистемах балансировки нагрузки, чтобы все запросы из клиента приложения Магазина Windows Lync обрабатывались одним сервером переднего плана.</P>
> <LI>
> <P>При установке отношения доверия с проверяющей стороной между Lync Server и серверами AD FS назначьте срок действия маркера, достаточного для достижения максимальной длины собраний Lync. Как правило, 240 минут бывает достаточно.</P></LI></UL>



</div>

**Настройка многофакторной проверки подлинности**

1.  Установите роль сервера федерации службы федерации Active Directory. Подробные сведения можно найти в руководстве по развертыванию служб федерации Active Directory <https://go.microsoft.com/fwlink/p/?linkid=267511>2,0 по адресу.

2.  Создайте сертификаты для AD FS. Для получения дополнительных сведений обратитесь к разделу "сертификаты сервера федерации" плана for Active Directory для использования с одним входом в [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376)разделе "планирование и развертывание AD FS".

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
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>Известные проблемы, которые могут препятствовать входу

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>Дата и время не заданы точно на устройстве, на котором работает приложение Магазина Windows в Lync

Параметр времени на устройстве должен быть синхронизирован с параметром Time на сервере. Это особенно важно для таких устройств, как Microsoft Surface, и других устройств под управлением Windows RT, которые не присоединены к домену. Чтобы автоматически настроить время для этих устройств с сервера времени, выполните следующую команду в командной строке с повышенными привилегиями на устройстве:
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Приложение Lync Windows Store не может получить доступ к серверу или службам Lync

Приложение Lync Windows Store может не иметь доступа к Lync Server или службам с помощью сетевых адаптеров, таких как USB-модемы 4G LTE, которые не регистрируются в Windows 8 как физические устройства. Приложение Lync Windows Store может столкнуться с этой ошибкой, даже если классические приложения и браузеры могут получать доступ к другим серверам и веб-сайтам.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Приложение Lync Windows Store не может войти в систему с помощью Lync Server 2010 и Office Communications Server 2007 R2 Edge Server

Если ваша топология состоит из Lync Server 2010 с пограничным сервером Office Communications Server 2007 R2, вам потребуется запустить обновленную версию построителя топологий, которая доступна в накопительном пакете обновления для Lync Server 2010: Июль 2013. Более ранние версии построителя топологий не создают необходимое сопоставление с пограничным сервером Office Communications Server 2007, поэтому не удается войти в Lync для клиентов приложений Магазина Windows. Необходимо выполнить следующие действия:

1.  Установите накопительный пакет обновления для Lync Server 2010:2013 июля в пулы Lync Server 2010 и Lync Server 2010 Директораs.

2.  Обновите конфигурацию автообнаружения Lync, чтобы указать, что внешняя точка входа SIP является адресом пограничного сервера, выполнив следующие действия:
    
    1.  Откройте консоль управления Lync Server.
    
    2.  Выполните следующую команду:
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>Приложение Lync Windows Store не может выполнить вход из-за ошибки проверки имени сертификата

Ошибка входа в систему для Microsoft 365 или Office 365 пользователи, которые не работают с последней версией Lync Windows App Store. Эта проблема обычно возникает при использовании нескольких доменов (например, когда URI SIP — **userA@domainZ.com** , но пограничный сервер — **SIP.domainX.com**). Чтобы устранить эту проблему, пользователи должны установить последнюю версию приложения Lync Windows для магазина, в которой также требуется Windows 8,1.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Устранение неполадок с помощью журналов приложений для Магазина Windows в Lync

Чтобы устранить неполадки, можно использовать журналы, созданные на устройстве. Журналы хранятся в следующей папке:

% Локалаппдата%\\пакетов\\, трассировка\_Microsoft\\.\\линкмкс 8wekyb3d8bbwe локалстате

Перед получением журналов от пользователя убедитесь, что ведение журнала включено, а затем попросите пользователя сохранить журналы, чтобы вся информация, хранящаяся в памяти, сохранялась в файлах на жестком диске.

**Включение ведения журнала**

1.  Откройте на устройстве приложение Lync Windows Store.

2.  Проведите пальцем с правой части экрана. Если вы используете мышь, наведите указатель мыши на правый верхний угол экрана, а затем наведите указатель мыши на экран.

3.  Выберите **Параметры**, выберите **Параметры**, а затем настройте **журналы диагностики** в **On**.

4.  Если **журналы диагностики** были ранее отключены, необходимо перезапустить Lync. Чтобы перезапустить Lync, выполните одно из следующих действий.
    
      - Перезапустите устройство.
    
      - Завершите задачу Lync и снова запустите приложение. Чтобы завершить задачу, откройте диспетчер задач Windows, выберите **Lync**, а затем нажмите кнопку **завершить задачу**. Если Lync отсутствует в списке, коснитесь пункта **Дополнительные сведения** и найдите Lync в разделе **фоновые процессы**.

**Сохранение журналов**

1.  Откройте на устройстве приложение Lync Windows Store.

2.  Попробуйте войти.

3.  Проведите пальцем с правой части экрана. Если вы используете мышь, наведите указатель мыши на правый верхний угол экрана, а затем наведите указатель мыши на экран.

4.  Выберите **Параметры**, выберите пункт **о программе**и нажмите кнопку **сохранить журналы**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

