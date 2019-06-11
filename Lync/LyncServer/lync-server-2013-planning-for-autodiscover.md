---
title: 'Lync Server 2013: планирование автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1d0ce7a775bc73c5f3afa10d1f9c148395b0eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Планирование автообнаружения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-16_

Средство автообнаружения было представлено для Lync Server в накопительном обновлении для Lync Server 2010: Ноябрь 2011. Основным предназначением для этой первоначальной реализации автообнаружения было предоставление средств Lync Mobile поиска службы Mobility Service (МККС). Служба автообнаружения в Lync Server 2013 теперь является службой, используемой всеми клиентами для поиска серверных и пользовательских служб. Служба автообнаружения Microsoft Lync Server 2013 работает на директориях и серверах переднего плана.

<div>


> [!TIP]  
> Дополнительные сведения о автообнаружения и возможностях, которые передается клиентам, приведены в разделе <A href="lync-server-2013-understanding-autodiscover.md">Общие сведения о автообнаружения в Lync Server 2013</A>.<BR>Мобильность по-прежнему является особым сценарием, а для служб Mobility по-прежнему требуется специальное планирование. Дополнительные сведения можно найти <A href="lync-server-2013-planning-for-mobility.md">в разделе Планирование мобильных устройств в Lync Server 2013</A>.



</div>

При вводе автообнаружения в Lync Server 2010 для реализации службы, требующей потенциальных изменений сертификатов на существующем сервере, находились нарушения, которые необходимо было сделать. Функцию автообнаружения можно использовать для порта TCP 443 для HTTPS или порта TCP 80 для HTTP. Если вы принимаете решение использовать HTTPS, сертификаты на обратных прокси-серверах, режиссерах и серверах переднего плана должны быть повторно выпущены для размещения необходимых `lyncdiscover.<domain>` и `lyncdiscoverinternal.<domain>` DNS-записей. Если вы хотите использовать HTTP, повторные выдаче сертификатов могут быть невозможны с помощью записей CNAME DNS (или псевдонима) для использования существующих имен в сертификатах. Использование HTTP означает, что начальные соединения не были зашифрованы.

Поскольку Lync Server 2013 использует функцию автообнаружения для всех клиентов, основным сценарием является использование HTTPS исключительно и создание сертификатов с помощью lyncdiscover. \<домен\> в рамках настройки обратных прокси, режиссеров и серверов переднего плана. Если вы реализуете автообнаружение в обновленном развертывании с Lync Server 2010, вам может потребоваться использовать HTTP, чтобы избежать повторной сертификации сертификатов. Руководство по обоим сценариям приведено в следующих разделах.

<div>


> [!IMPORTANT]  
> Список альтернативных имен субъектов в сертификатах, используемых внешним правилом публикации веб-служб, должен содержать <EM>lyncdiscover.&lt; сипдомаин&gt; </EM> запись для каждого домена SIP в Организации. Дополнительные сведения об элементах альтернативных имен тем, которые требуются для режиссеров, серверов переднего плана и обратного доступа, приведены <A href="lync-server-2013-certificate-summary-autodiscover.md">в разделе сведения о сертификате: автообнаружение в Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Сведения о сертификате: обнаружение автообнаружения в Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Сводка порта: автообнаружения в Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [Сводка DNS: обнаружение автообнаружения в Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Гибридная и Разделяемая доменные возможности автообнаружения в Lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

