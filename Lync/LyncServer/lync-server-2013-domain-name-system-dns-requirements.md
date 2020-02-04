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
ms.openlocfilehash: 2eddf86c881875ebbe08fddd6ffa85403dda6b60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Требования к системе доменных имен (DNS) для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-18_

Для развертывания сервера Lync Server необходимо создать записи DNS, которые обеспечивают обнаружение клиентов и серверов и, при необходимости, поддержку автоматического входа в систему, если ваша организация хочет ее поддерживать.

Lync Server использует DNS в указанных ниже случаях.

  - Для выяснения внутренних серверов или пулов для обмена данными между серверами.

  - Для разрешения клиентам найти пул переднего плана или сервер Standard Edition, используемый для различных транзакций SIP.

  - Чтобы разрешить устройствам UC, которые не вошли в систему, найти пул переднего плана или сервер Standard Edition с веб-службой обновления устройств, получить обновления и отправить журналы.

  - Разрешить внешним серверам и клиентам подключаться к пограничным серверам или обратному прокси-серверу HTTP для обмена мгновенными сообщениями или конференц-связи.

  - Чтобы разрешить внешним устройствам UC подключаться к веб-службе обновления устройства через пограничные серверы или обратный прокси-сервер HTTP и получать обновления.

  - Чтобы разрешить мобильным клиентам автоматически определять ресурсы веб-служб без необходимости вручную вводить URL-адреса в окне "Параметры устройства".

<div>

## <a name="in-this-section"></a>Содержание

  - [Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Требования к DNS для пулов интерфейсов на сервере Lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Требования к DNS для серверов Standard Edition в Lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Требования DNS для простых URL-адресов в Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Требования DNS для автоматического входа клиента в Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Требования к DNS для мобильных устройств с помощью Lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [Балансировка нагрузки DNS в Lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

