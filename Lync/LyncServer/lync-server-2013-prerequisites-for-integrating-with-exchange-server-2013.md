---
title: 'Lync Server 2013: предварительные требования для интеграции с Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51bc3ce48756f746b2f2f5c0ce65d08567fea74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Необходимые условия для интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-04-22_

Прежде чем приступить к интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013, необходимо убедиться, что выполнены все необходимые меры. Как и раньше, интеграция не может быть выполнена, пока не будут полностью установлены и запущены Exchange 2013 и Lync Server 2013. Подробнее об установке Exchange можно найти в документации по планированию и развертыванию Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)2013. Подробные сведения об установке Lync Server 2013 можно найти в документации по планированию и [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)развертыванию.

После того как серверы будут установлены и запущены, необходимо назначить сертификаты проверки подлинности серверов для Lync Server 2013 и Exchange 2013; Эти сертификаты позволяют Lync Server и Exchange обмениваться информацией и взаимодействовать друг с другом. При установке Exchange 2013 создается самозаверяющий сертификат с именем сертификата для проверки подлинности сервера Microsoft Exchange Server. Этот сертификат, который можно найти в хранилище сертификатов локального компьютера, должен использоваться для проверки подлинности серверов на сервере Exchange 2013. Сведения о назначении сертификатов в Exchange 2013 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)разделе "Настройка потока обработки почты и доступа клиентов".

Для Lync Server 2013 вы можете использовать существующий сертификат сервера Lync Server в качестве сертификата для проверки подлинности сервера. Например, сертификат по умолчанию также можно использовать в качестве сертификата Оаустокениссуер. Lync Server 2013 позволяет использовать любой сертификат веб-сервера в качестве сертификата для проверки подлинности серверов и серверов, если:

  - этот сертификат содержит имя домена SIP в поле "Тема";

  - тот же сертификат настроен как сертификат OAuthTokenIssuer на всех интерфейсных серверах;

  - длина сертификата составляет не менее 2048 бит.

Подробнее о сертификатах проверки подлинности серверов для Microsoft Lync Server 2013: [назначение сертификата проверки подлинности серверов и серверов для Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

После назначения сертификатов необходимо настроить службу автообнаружения в Exchange 2013. В Exchange 2013 служба автообнаружения настраивает профили пользователей и предоставляет доступ к службам Exchange при входе пользователя в систему. Пользователи предоставляют службе автообнаружения свой адрес электронной почты и пароль; в свою очередь службы предоставляют пользователям следующую информацию:

  - Сведения о соединении как внутренних, так и внешних подключений к Exchange 2013.

  - расположение сервера почтовых ящиков пользователя;

  - URL-адреса для компонентов Outlook, таких как сведения о доступности, единой системе обмена сообщениями, а также автономной адресной книге;

  - параметры сервера мобильного Outlook.

Для интеграции Lync Server 2013 и Exchange 2013 необходимо настроить службу автообнаружения. Вы можете проверить, настроена ли служба автообнаружения, выполнив следующую команду в командной консоли Exchange и установив значение свойства Аутодисковерсервицеинтерналури:

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Если это значение пусто, необходимо назначить URI службе автообнаружения. Обычно этот URI выглядит следующим образом:

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

URI автообнаружения можно назначить с помощью следующей команды:

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Подробные сведения о службе автообнаружения можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)разделе Общие сведения о службе автообнаружения.

После настройки службы автообнаружения необходимо изменить параметры конфигурации OAuth сервера Lync. Это гарантирует, что Lync Server знает, где найти службу автообнаружения. Чтобы изменить параметры конфигурации OAuth в Lync Server 2013, выполните следующую команду в командной консоли Lync Server Management Shell. При выполнении этой команды убедитесь, что вы указали универсальный код ресурса (URI) для службы автообнаружения, запущенной на сервере Exchange, и что вы используете функцию **автообнаружения. svc** , чтобы указать расположение службы вместо **автообнаружения. XML** (указывающий на XML-файл). используется службой):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> Параметр Identity в предыдущей команде является необязательным; Это связано с тем, что Lync Server позволяет только использовать единственную глобальную коллекцию параметров конфигурации OAuth. Помимо прочего, это означает, что вы можете настроить URL-адрес автообнаружения, используя это немного более простую команду:<BR>Set-Ксоаусконфигуратион – Ексчанжеаутодисковерурл "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>Если вы не знакомы с этой технологией, OAuth — это стандартный протокол авторизации, который применяется на различных крупных веб-сайтах. При использовании OAuth учетные данные и пароли пользователей не переносятся с одного компьютера на другой. Вместо этого проверка подлинности и авторизация основаны на обмене маркерами безопасности, которые предоставляют доступ к определенному набору ресурсов в течение определенного промежутка времени.



</div>

Помимо настройки службы автообнаружения, необходимо также создать DNS-запись для службы, указывающей на сервер Exchange. Например, если служба автообнаружения находится на autodiscover.litwareinc.com, вам потребуется создать запись DNS для autodiscover.litwareinc.com, которая разрешается в полное доменное имя сервера Exchange (например, atl-exchange-001.litwareinc.com).

</div>

<span> </span>

</div>

</div>

</div>

