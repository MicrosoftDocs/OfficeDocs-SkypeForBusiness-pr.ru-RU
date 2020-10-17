---
title: 'Lync Server 2013: сводка по сертификатам — общедоступная служба обмена мгновенными сообщениями'
description: 'Lync Server 2013: сводка по сертификатам — общедоступная служба обмена мгновенными сообщениями.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abf5a01bdeb03da158e221c623417a1b42cc82f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572335"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Сводка по сертификатам: общедоступная служба обмена мгновенными сообщениями в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-19_

Чтобы настроить сертификаты для подключения к общедоступным службам обмена мгновенными сообщениями, необходимо сначала обратить внимание на то, что ничего не отличается от других типов Федерации SIP или даже стандартных сертификатов пограничного сервера, за исключением того, что для America Online (AOL) требуется уникальная конфигурация сертификата. В дополнение к обычному расширенному использованию ключей сервера (EKU) для America Online необходимо, чтобы сертификаты или сертификаты (в случае пограничного пула) также содержали клиентское EKU. Клиентское EKU является дополнением к сертификату и является частью внешнего общедоступного сертификата, назначенного пограничного сервера.

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Сводка по сертификату– подключение к общедоступным системам обмена мгновенными сообщениями


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
<th>Альтернативные имена субъекта (SAN)/порядок</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внешний/пограничный доступ</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Сертификат должен относиться к общедоступному центру сертификации и иметь EKU для сервера и клиента, если необходимо развернуть общедоступную службу обмена мгновенными сообщениями с AOL. Сертификат назначается интерфейсам внешних пограничных серверов для:</p>
<ul>
<li><p>Пограничная служба доступа</p></li>
<li><p>Служба пограничного сервера веб-конференций</p></li>
<li><p>Пограничная служба аудио- и видеоконференций</p></li>
</ul>
<p>Обратите внимание, что альтернативные имена субъекта автоматически добавляются в сертификат на основе определений в построителе топологий. Записи альтернативных имен необходимы для дополнительных доменов SIP и прочих записей, которые должны поддерживаться. Имя субъекта копируется в одно из альтернативных имен, что необходимо для правильного выполнения операций.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

