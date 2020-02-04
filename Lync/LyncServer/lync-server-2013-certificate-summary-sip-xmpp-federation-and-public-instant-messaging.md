---
title: 'Общие сведения о сертификате: SIP, Федерация КСМПП и общедоступная служба обмена мгновенными сообщениями'
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
ms.openlocfilehash: 0fc3b7a1745d045954fb06403dbb3359fb699a29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Общие сведения о сертификате: SIP, Федерация КСМПП и общедоступная служба обмена мгновенными сообщениями в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-03-15_

Сертификаты, необходимые для Федерации с Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server, обычно удовлетворяют требованиям для настройки, запроса и назначения серверу пограничного сервера.

Требования к сертификатам для включения и установления связи с партнерами по протоколу расширенного обмена сообщениями (КСМПП) требуют добавления записей для доменов КСМПП. Запись, включенная в сертификат в качестве дополнительного имени субъекта (SAN), будет являться доменом, который может принимать участие в КСМПП обмене сообщениями. Домен может быть доменом корневого уровня (например, contoso.com), если вы хотите включить КСМПП для всего домена или выбрать его дочерние домены (например, corp.contoso.com, finance.contoso.com), если вы включаете КСМПП для подмножества пользователей.

Чтобы настроить сертификаты для общедоступной службы обмена мгновенными сообщениями, обратите внимание на то, что ничего не отличается от других типов Федерации SIP или даже стандартных сертификатов пограничного сервера, за исключением того, что для America Online (AOL) требуется сертификат или сертификаты (в корпус пограничного пула) также должен содержать клиентское EKU. Клиентское EKU является дополнением к сертификату и является частью внешнего общедоступного сертификата, назначенного пограничного сервера.

Чтобы убедиться в том, что требования к сертификату для развертывания пограничного сервера выполнены правильно, ознакомьтесь с разделами, приведенными в разделе, озаглавленном **также**.

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
<th>Дополнительные имена субъектов (SAN)</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внешний край и доступ</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> Поддержка пространства имен contoso.com КСМПП


<p>sip.fabrikam.com</p>



> [!NOTE]
> Поддержка пространства имен SIP fabrikam.com


<p>fabrikam.com</p>



> [!NOTE]
> Поддержка пространства имен fabrikam.com КСМПП

</td>
<td><p>Сертификат должен находиться в общедоступном центре сертификации, а также в том случае, если вы разворачиваете общедоступную службу обмена мгновенными сообщениями с AOL, и у вас должен быть серверный EKU Сертификат назначается внешним интерфейсам пограничного сервера для следующих параметров:</p>
<ul>
<li><p>доступа</p></li>
<li><p>веб-конференций</p></li>
<li><p>передачи аудио- и видеоданных</p></li>
</ul>



> [!NOTE]
> Технически сертификат не назначается для A/V Edge. Безопасная связь и проверка подлинности управляются службой проверки подлинности в Media Relay (МРАС). МРАС использует сертификат, назначенный внутреннему интерфейсу пограничного сервера.


<p>Обратите внимание, что сети SAN автоматически добавляются к сертификату на основе определений в построителе топологии. Вы добавляете записи SAN по мере необходимости для дополнительных доменов SIP и других элементов, которые необходимо поддерживать. Имя субъекта реплицируется в сети SAN и должно быть представлено для правильной работы.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Пример конфигурации XMPP в Lync Server 2013 — федерация XMPP с Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Планирование сертификатов пограничного сервера в Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Сводка по сертификатам — единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Сводка по сертификатам — единая консолидированная пограничная топология с общедоступными IP-адресами в Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Сводка по сертификатам — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Сводка по сертификатам — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Сводка по сертификатам — масштабируемая консолидированная пограничная топология с аппаратными балансировщиками нагрузки в Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

