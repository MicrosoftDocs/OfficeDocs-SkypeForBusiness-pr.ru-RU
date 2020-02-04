---
title: 'Lync Server 2013: развертывание приложения Lync из Магазина Windows'
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
ms.openlocfilehash: 49fcea107a4613ca78661a21d492612f82d9775f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Развертывание приложения Lync из Магазина Windows в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-12-03_

Прежде чем сделать приложение Lync из Магазина Windows доступным для пользователей, убедитесь, что развертывание соответствует [требованиям приложения Lync из Магазина Windows для Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md). Дополнительные сведения о настройке Lync Server 2013 для поддержки приложения Lync из Магазина Windows можно найти в статье блогов для NextHop: "Автообнаружение Lync Server и приложение Lync из магазина [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)Windows". После правильной настройки серверной среды вы можете направлять пользователей для загрузки приложения Lync из Магазина Windows, выполнив поиск по слову "Lync".

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Включение многофакторной проверки подлинности для приложения Lync из Магазина Windows

Накопительные обновления для Lync Server 2013: Июнь 2013 добавляет поддержку многофакторной проверки подлинности для клиентов приложений Lync из Магазина Windows. Помимо имени пользователя и пароля, для проверки подлинности внешних пользователей при входе в собрания Lync можно использовать дополнительные методы проверки подлинности, например смарт-карты или контакты. Чтобы включить многофакторную проверку подлинности, вы можете развернуть сервер федерации служб федерации Active Directory (AD FS) и включить пассивную проверку подлинности в Lync Server 2013. После настройки AD FS внешние пользователи, пытающиеся присоединиться к собраниям Lync, будут представлены на веб-странице многофакторной проверки подлинности AD FS, которая содержит имя пользователя и пароль, а также любые дополнительные способы проверки подлинности, которые вы настроили. .

<div class=" ">


> [!IMPORTANT]  
> Ниже приведены важные моменты, которые следует учитывать при планировании настройки служб ADFS для многофакторной проверки подлинности в приложении Lync из Магазина Windows. 
> <UL>
> <LI>
> <P>Lync Server 2013 с накопительными обновлениями для Lync Server 2013: требуется не менее июня 2013. Пользователи Lync 2013 для настольных компьютеров не требуют накопительных обновлений для Lync Server 2013: Июнь 2013, поэтому может возникнуть ситуация, когда проверка подлинности в Lync 2013 клиенты смогут пройти проверку подлинности. Тем не менее, процесс проверки подлинности для клиентов приложения Lync из Магазина Windows не будет выполнен, но уведомления или сообщение об ошибке выводиться не будут.</P>
> <LI>
> <P>Сервер должен быть настроен таким образом, чтобы была доступна только для проверки подлинности.</P>
> <LI>
> <P>Если вы используете подсистемы балансировки нагрузки для оборудования, включите сохраняемость файлов cookie для подсистем балансировки нагрузки, чтобы все запросы из клиента приложения Магазина Windows для Lync обрабатывались на одном и том же внешнем сервере.</P>
> <LI>
> <P>Если вы устанавливаете отношение доверия проверяющей стороны между сервером Lync Server и серверами AD FS, назначьте жизненный цикл, достаточно длинный, чтобы занимать максимальную длину собраний Lync. Как правило, 240 минут бывает достаточно.</P></LI></UL>



</div>

**Настройка многофакторной проверки подлинности**

1.  Установите роль сервера федерации служб федерации Active Directory. Подробные сведения можно найти в руководстве по развертыванию служб федерации Active Directory <http://go.microsoft.com/fwlink/p/?linkid=267511>2,0 по адресу.

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

## <a name="known-issues-that-can-prevent-sign-in"></a>Известные проблемы, которые могут помешать входу

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>На устройстве с приложением Lync из магазина не задана точная дата и время.

Время, установленное на устройстве, должно быть синхронизировано с параметром Time (время) на сервере. Это особенно важно для устройств, таких как Microsoft Surface и других устройств под управлением Windows RT, которые не подключены к домену. Чтобы автоматически настроить время на этих устройствах с сервера времени, выполните в командной строке с повышенными привилегиями на устройстве следующую команду:
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Приложению Lync из Магазина Windows не удается получить доступ к серверу или службам Lync

Приложение Lync из Магазина Windows может не получить доступ к серверу Lync или службам через сетевые адаптеры, такие как 4G LTE USB-модемы, которые не регистрируются в Windows 8 как физические устройства. Приложение Lync из Магазина Windows может решить эту проблемы даже в том случае, если классические приложения и браузеры могут получить доступ к другим серверам и веб-сайтам.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Приложение Lync из Магазина Windows не может войти в составе Lync Server 2010 и Office Communications Server 2007 R2 Edge Server

Если ваша топология состоит из Lync Server 2010 с пограничным сервером Office Communications Server 2007 R2, вам потребуется запустить обновленную версию построителя топологии, которая доступна в накопительном обновлении для Lync Server 2010: Июль 2013. Более ранние версии построителя топологии не создают необходимое сопоставление для Office Communications Server 2007 Edge Server, поэтому пользователи приложения Lync из Магазина Windows не могут войти в службу. Необходимо выполнить указанные ниже действия.

1.  Установите накопительное обновление для Lync Server 2010: Июль 2013 для Lync Server 2010 Pools и режиссеров Lync Server 2010.

2.  Обновите конфигурацию автообнаружения Lync, чтобы указать, что внешняя точка входа SIP является адресом пограничного сервера, выполнив указанные ниже действия.
    
    1.  Откройте командную консоль Lync Server.
    
    2.  Выполните следующую команду.
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>Не удается войти в приложение Lync из Магазина Windows из-за ошибки проверки имени сертификата

Для пользователей Office 365, не использующих самую последнюю версию приложения Lync из Магазина Windows, может возникнуть ошибка входа. Эта проблема обычно возникает при использовании нескольких доменов (например, если URI SIP — **userA@domainZ.com** , но пограничный сервер — **SIP.domainX.com**). Чтобы устранить эту проблему, пользователи должны установить последнюю версию приложения Lync из Магазина Windows, в которой также требуется Windows 8,1.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Устранение проблем с использованием журналов приложений Lync из Магазина Windows

Вы можете использовать журналы, созданные на устройстве, для устранения неполадок. Журналы хранятся в следующей папке:

% LocalAppData%\\упаковывает\\Microsoft. линкмкс\_8wekyb3d8bbwe\\локалстате\\Tracing

Перед получением журналов от пользователя убедитесь в том, что ведение журнала включено, а затем посоветуйте ему сохранить журналы, чтобы все хранящиеся в памяти данные также сохранялись в файлах на жестком диске.

**Включение ведения журнала**

1.  Откройте приложение Lync из Магазина Windows на устройстве.

2.  Проведите пальцем от правого края экрана. Если вы используете мышь, наведите указатель мыши на правый верхний угол экрана, а затем наведите курсор на экран.

3.  Нажмите кнопку **Параметры**, выберите пункт **Параметры**, а затем установите для параметра **журналы диагностики** значение **вкл**.

4.  Если **журналы диагностики** были ранее отключены, необходимо перезапустить Lync. Чтобы перезапустить Lync, выполните одно из указанных ниже действий.
    
      - Перезапустите устройство.
    
      - Завершите задачу Lync и запустите приложение еще раз. Чтобы завершить задачу, откройте диспетчер задач Windows, выберите **Lync**и нажмите кнопку **завершить задачу**. Если Lync нет в списке, выберите **Дополнительные сведения** и найдите Lync в разделе **фоновые процессы**.

**Сохранение журналов**

1.  Откройте приложение Lync из Магазина Windows на устройстве.

2.  Попробуйте войти в программу.

3.  Проведите пальцем от правого края экрана. Если вы используете мышь, наведите указатель мыши на правый верхний угол экрана, а затем наведите курсор на экран.

4.  Нажмите кнопку **Параметры**, выберите пункт **о программе**, а затем — команду **сохранить журналы**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

