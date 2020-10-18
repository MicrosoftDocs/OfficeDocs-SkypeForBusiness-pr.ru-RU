---
title: 'Lync Server 2013: необходимые условия для интеграции с Exchange Server 2013'
description: 'Lync Server 2013: необходимые условия для интеграции с Exchange Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5872fe3ec546997cd0633383fdda7e0549bec83f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579855"
---
# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Необходимые условия для интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-04-22_

Перед интеграцией Microsoft Lync Server 2013 и Microsoft Exchange Server 2013 необходимо убедиться, что все необходимые действия выполнены. Как вы можете ожидать, интеграция не может быть выполнена, пока не будут полностью установлены и запущены Exchange 2013 и Lync Server 2013. Более подробную информацию об установке Exchange можно найти в документации по планированию и развертыванию Exchange 2013 на сайте [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539) . Подробные сведения об установке Lync Server 2013 можно найти в документации по планированию и развертыванию [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806) .

После установки и запуска серверов необходимо назначить сертификаты проверки подлинности "сервер – сервер" для Lync Server 2013 и Exchange 2013. Эти сертификаты позволяют Lync Server и Exchange обмениваться информацией и общаться друг с другом. При установке Exchange 2013 создается самозаверяющий сертификат с именем сертификата проверки подлинности Microsoft Exchange Server. Этот сертификат, который можно найти в хранилище сертификатов локального компьютера, должен использоваться для межсерверной проверки подлинности на сервере Exchange 2013. Подробные сведения о назначении сертификатов в Exchange 2013 приведены в разделе "Настройка почтового ящика и клиентского доступа" [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540) .

Для Lync Server 2013 вы можете использовать существующий сертификат Lync Server в качестве сертификата проверки подлинности "сервер – сервер"; Например, сертификат по умолчанию также можно использовать в качестве сертификата OAuthTokenIssuer. Lync Server 2013 позволяет использовать любой сертификат веб-сервера в качестве сертификата для проверки подлинности "сервер-сервер" при условии, что:

  - этот сертификат содержит имя домена SIP в поле "Тема";

  - тот же сертификат настроен как сертификат OAuthTokenIssuer на всех интерфейсных серверах;

  - длина сертификата составляет не менее 2048 бит.

Сведения о сертификатах проверки подлинности "сервер – сервер" для Microsoft Lync Server 2013 приведены в [статье назначение сертификата проверки подлинности между серверами в Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

После назначения сертификатов необходимо настроить службу автообнаружения в Exchange 2013. В Exchange 2013 служба автообнаружения настраивает профили пользователей и предоставляет доступ к службам Exchange при входе пользователей в систему. Пользователи предоставляют службе автообнаружения свой адрес электронной почты и пароль; в свою очередь службы предоставляют пользователю следующую информацию:

  - Сведения о подключении как для внутреннего, так и для внешнего подключения к Exchange 2013.

  - расположение сервера почтовых ящиков пользователя;

  - URL-адреса для компонентов Outlook, таких как сведения о доступности, единой системе обмена сообщениями, а также автономной адресной книге;

  - параметры сервера мобильного Outlook.

Для интеграции Lync Server 2013 и Exchange 2013 необходимо настроить службу автообнаружения. Вы можете проверить, настроена ли служба автообнаружения, выполнив следующую команду в командной консоли Exchange и проверив значение свойства AutoDiscoverServiceInternalUri:

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Если это значение пусто, необходимо назначить URI службе автообнаружения. Обычно этот URI выглядит следующим образом:

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

URI автообнаружения можно назначить с помощью следующей команды:

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Подробные сведения о службе автообнаружения содержатся в разделе "Общие сведения о службе автообнаружения" [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542) .

После настройки службы автообнаружения необходимо изменить параметры конфигурации OAuth для Lync Server; Это гарантирует, что Lync Server будет знать, где найти службу автообнаружения. Чтобы изменить параметры конфигурации OAuth в Lync Server 2013, выполните следующую команду в командной консоли Lync Server. При выполнении этой команды необходимо указать URI для службы автообнаружения, запущенной на сервере Exchange Server, а также использовать службу **автообнаружения. svc** для указания расположения службы, а не **autodiscover.xml** (что указывает на XML-файл, используемый службой):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> Параметр Identity в предыдущей команде является необязательным; Это связано с тем, что Lync Server позволяет использовать только одну глобальную коллекцию параметров конфигурации OAuth. Помимо прочего, это означает, что вы можете настроить URL-адрес автообнаружения, используя немного более простую команду:<BR>Set-CsOAuthConfiguration – Ексчанжеаутодисковерурл " https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc "<BR>Если вы не знакомы с этой технологией, OAuth — это стандартный протокол авторизации, который применяется на различных крупных веб-сайтах. При использовании OAuth учетные данные и пароли пользователей не переносятся с одного компьютера на другой. Вместо этого проверка подлинности и авторизация основаны на обмене маркерами безопасности, которые предоставляют доступ к определенному набору ресурсов в течение определенного промежутка времени.



</div>

В дополнение к настройке службы автообнаружения необходимо также создать запись DNS для службы, указывающей на сервер Exchange. Например, если служба автообнаружения расположена по адресу autodiscover.litwareinc.com, необходимо создать запись DNS для autodiscover.litwareinc.com, которая разрешается в полное доменное имя сервера Exchange (например, atl-exchange-001.litwareinc.com).

</div>

<span> </span>

</div>

</div>

</div>

