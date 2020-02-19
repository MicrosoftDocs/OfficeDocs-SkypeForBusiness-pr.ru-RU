---
title: 'Lync Server 2013: планирование автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8115cb68638e2db1db93c1afb96d12d96d2ed78
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Планирование автообнаружения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-16_

Служба автообнаружения была добавлена для Lync Server в накопительном пакете обновления для Lync Server 2010: Ноябрь 2011. Основной целью этой первоначальной реализации автообнаружения было предоставление средству Lync Mobile возможность обнаружения службы Mobility Service (MCX). Служба автообнаружения в Lync Server 2013 теперь является службой, используемой всеми клиентами для обнаружения серверных и пользовательских служб. Служба автообнаружения Microsoft Lync Server 2013 работает на директориях и серверах переднего плана.

<div>


> [!TIP]  
> Более подробную техническую информацию о службе автообнаружения и о том, что происходит с клиентами, можно узнать <A href="lync-server-2013-understanding-autodiscover.md">в статье Общие сведения о службе автообнаружения в Lync Server 2013</A>.<BR>Мобильность по-прежнему является отдельным сценарием, а службам Mobility по-прежнему требуется специальное планирование. Дополнительные сведения см в статье <A href="lync-server-2013-planning-for-mobility.md">планирование мобильных устройств в Lync Server 2013</A>.



</div>

Когда служба автообнаружения появилась в Lync Server 2010, существуют компромиссы, которые необходимо выполнить, чтобы реализовать службу, требующую потенциальных изменений сертификатов для существующих развертываний серверов. Службу автообнаружения можно использовать через порт TCP 443 для HTTPS или через порт TCP 80 для HTTP. Если было принято решение использовать HTTPS, сертификаты на обратных прокси-серверах, директориях и серверах переднего плана должны быть повторно выдаваться для размещения необходимых `lyncdiscover.<domain>` и `lyncdiscoverinternal.<domain>` DNS-записей. Если было принято решение об использовании протокола HTTP, можно избежать повторной выпуска сертификатов с помощью записей CNAME DNS (или псевдонимов) для использования существующих имен в сертификатах. При использовании HTTP имелось в виду, что начальные сообщения не были зашифрованы.

Так как Lync Server 2013 использует функцию автообнаружения для всех клиентов, основной сценарий состоит в том, чтобы использовать только HTTPS и создавать сертификаты с помощью lyncdiscover. \<домен\> в составе конфигурации обратных прокси-серверов, директоров и серверов переднего плана. Если вы реализуете автообнаружение в обновленном развертывании с Lync Server 2010, вам может потребоваться использовать HTTP, чтобы избежать повторной выдачи сертификатов. Руководство по обоим сценариям представлено в следующих разделах.

<div>


> [!IMPORTANT]  
> Список альтернативных имен субъектов в сертификатах, используемых правилом публикации внешних веб-служб, должен содержать <EM>lyncdiscover.&lt; запись&gt; sipdomain</EM> для каждого домена SIP в Организации. Для получения сведений о записях альтернативного имени субъекта, необходимых для директоров, серверов переднего плана и обратных прокси-серверов, ознакомьтесь со статьей <A href="lync-server-2013-certificate-summary-autodiscover.md">Сводка по сертификатам — автообнаружение в Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Сводка по сертификатам — автообнаружение в Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Сводка по портам — автообнаружение в Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [Сводка по DNS — автообнаружение в Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Гибридное и комбинированное доменное обнаружение в Lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

