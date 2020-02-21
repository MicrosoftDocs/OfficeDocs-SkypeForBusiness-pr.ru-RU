---
title: 'Lync Server 2013: требования к системе доменных имен (DNS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13fcb074ea5ce90bbe7097bf5c2f1f975de809c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Требования к системе доменных имен (DNS) для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-18_

Для развертывания Lync Server необходимо создать записи службы доменных имен (DNS), которые обеспечивают обнаружение клиентов и серверов, а также (при необходимости) поддержку автоматического входа клиента, если ваша организация хочет ее поддерживать.

Lync Server использует DNS следующим образом:

  - Для обнаружения внутренних серверов или пулов для межсерверной связи.

  - , Чтобы разрешить клиентам обнаруживать пул переднего плана или сервер Standard Edition, используемый для различных транзакций SIP.

  - Чтобы разрешить устройствам Объединенных коммуникаций, не вошедшим в систему, обнаруживать интерфейсный пул или сервер Standard Edition с веб-службой обновления устройств, получать обновления и отправлять журналы.

  - , Чтобы разрешить внешним серверам и клиентам подключаться к пограничным серверам или обратному прокси-серверу HTTP для обмена мгновенными сообщениями или конференц-связи.

  - Чтобы разрешить внешним устройствам UC подключаться к веб-службе обновления устройств через пограничные серверы или обратный прокси-сервер HTTP и получать обновления.

  - чтобы разрешить мобильным клиентам автоматически обнаруживать ресурсы веб-служб без того, чтобы пользователи вручную вводили URL-адреса в параметрах устройства.

<div>

## <a name="in-this-section"></a>Содержание

  - [Определение требований к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Требования DNS для пулов переднего плана в Lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Требования DNS для серверов Standard Edition в Lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Требования DNS для простых URL-адресов в Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Требования DNS для автоматического входа клиентов в Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Требования DNS для мобильных устройств с Lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [Балансировка нагрузки на DNS в Lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

