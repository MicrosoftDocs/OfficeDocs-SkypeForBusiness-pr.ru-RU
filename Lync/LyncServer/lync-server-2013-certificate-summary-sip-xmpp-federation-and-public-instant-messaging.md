---
title: 'Сводка по сертификатам: SIP, Федерация XMPP и общедоступная служба обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 284a633a2c5ce820009c6672058837bbecb7ecd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517876"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Сводка по сертификатам: SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-15_

Сертификаты, которые необходимы для Федерации с Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server, обычно соответствуют сертификатам, которые вы настраиваете, запрашиваете и назначаете пограничный сервер.

Требования к сертификатам для поддержки и установления связи с партнерами по протоколу XMPP (Extensible Messaging and Presence Protocol) требуют добавления записей для доменов XMPP. Запись, включаемая в сертификат в виде альтернативного имени субъекта (SAN), содержит имя домена, который может участвовать в обмене данными по протоколу XMPP. Домен может представлять собой домен корневого уровня (например, contoso.com), если вы хотите включить протокол XMPP для всего домена, или набор дочерних доменов (например, corp.contoso.com, finance.contoso.com), если включаете протокол XMPP для подмножества пользователей.

Чтобы настроить сертификаты для подключения к общедоступным службам обмена мгновенными сообщениями, обратите внимание на то, что ничто не отличается от других типов Федерации SIP или даже стандартных сертификатов пограничного сервера, за исключением того, что в America Online (AOL) требуется, чтобы сертификат или сертификаты (в случае пограничного пула) также содержали клиентское EKU. Клиентское EKU является дополнением к сертификату и является частью внешнего общедоступного сертификата, назначенного пограничного сервера.

Чтобы убедиться в том, что соблюдены правильные требования к сертификатам для развертывания пограничного сервера, ознакомьтесь со статьями, приведенными в разделе, озаглавленном **также**.

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Компонент</th>
<th>Имя субъекта</th>
<th>Альтернативные имена субъектов</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внешний/пограничный доступ</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> Поддержка пространства имен contoso.com XMPP


<p>sip.fabrikam.com</p>



> [!NOTE]
> Поддержка пространства имен SIP fabrikam.com


<p>fabrikam.com</p>



> [!NOTE]
> Поддержка пространства имен fabrikam.com XMPP

</td>
<td><p>Сертификат должен относиться к общедоступному центру сертификации и иметь EKU для сервера и клиента, если необходимо развернуть общедоступную службу обмена мгновенными сообщениями с AOL. Сертификат назначается интерфейсам внешних пограничных серверов для:</p>
<ul>
<li><p>Пограничная служба доступа</p></li>
<li><p>Служба пограничного сервера веб-конференций</p></li>
<li><p>Пограничная служба аудио- и видеоконференций</p></li>
</ul>



> [!NOTE]
> Технически сертификат не назначается для пограничного сервера аудио-и видеоданных. Безопасная связь и проверка подлинности управляются службой проверки подлинности Media Relay (MRAS). MRAS использует сертификат, назначенный внутреннему интерфейсу пограничного сервера.


<p>Обратите внимание, что альтернативные имена субъекта автоматически добавляются в сертификат на основе определений в построителе топологий. Записи альтернативных имен необходимы для дополнительных доменов SIP и прочих записей, которые должны поддерживаться. Имя субъекта копируется в одно из альтернативных имен, что необходимо для правильного выполнения операций.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Пример конфигурации XMPP в Lync Server 2013 – XMPP Федерация с Google говорите](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Планирование сертификатов пограничного сервера в Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Сводка по сертификатам — единая консолидированная пограничная с частными IP-адресами с использованием NAT в Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Сводка по сертификатам — единая Объединенная пограничная с общедоступными IP-адресами в Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Сводка по сертификатам — масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами с использованием NAT в Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Сводка по сертификатам — масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Сводка по сертификатам — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

