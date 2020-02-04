---
title: 'Lync Server 2013: Проверка параметров системы доменных имен для балансировки нагрузки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0178d179a9684cf07450cdee839af1c8c1ebc22d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Проверка параметров системы доменных имен для балансировки нагрузки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-05-02_

Для поддержки полного доменного имени, используемого службой балансировки нагрузки DNS, необходимо подготовить DNS для разрешения полного доменного имени пула (например, pool01.contoso.com) в IP-адреса всех серверов в пуле (например, 192.168.1.1, 192.168.1.2 и т. д.). Вы должны включать только IP-адреса серверов, которые развернут в данный момент.

Кроме того, при использовании балансировки нагрузки DNS для пулов Edge требуются следующие записи DNS:

  - Для службы пограничного доступа Lync Server вы должны иметь одну запись для каждого сервера в пуле. Каждая запись должна разрешать полное доменное имя службы пограничного доступа Lync Server (например, sip.contoso.com) к IP-адресу службы пограничного доступа Lync Server на одном из пограничных серверов в пуле.

  - Для службы Edge для веб-конференций Lync Server необходимо иметь одну запись для каждого сервера в пуле. Каждая запись должна разрешать полное доменное имя службы Microsoft Edge для веб-конференций Lync Server (например, webconf.contoso.com) в IP-адрес службы Edge веб-конференций Lync Server на одном из пограничных серверов пула.

  - Для службы звука и видео в Lync Server необходимо иметь одну запись для каждого сервера в пуле. Каждая запись должна разрешать полное доменное имя (например, av.contoso.com) в качестве FQDN для службы "звук и видео" в Lync Server, а также в IP-адресе службы на одном из пограничных серверов в пуле.

  - Если вы хотите использовать балансировку нагрузки DNS на внутреннем интерфейсе пула EDGE, необходимо добавить одну запись DNS, которая будет разрешать внутреннее полное доменное имя пула Edge с IP-адресом каждого сервера в пуле.

Чтобы убедиться в том, что DNS возвращает правильные значения для балансировки нагрузки DNS, следует использовать средство nslookup. Чтобы вернуть все значения для записи DNS с помощью nslookup, выполните команду:

`nslookup <FQDN >`

Эта команда запускается для всех полных доменных имен, используемых в конфигурации балансировки нагрузки DNS, чтобы убедиться, что каждый набор записей для балансировки нагрузки DNS вернул все необходимые записи.

</div>

<span> </span>

</div>

</div>

</div>

