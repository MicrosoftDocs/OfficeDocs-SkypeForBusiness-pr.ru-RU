---
title: 'Lync Server 2013: сводка по DNS — обратный прокси-сервер'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13cecbc7e690302d9bc0fcad13a686f5514e3cf7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Сводка по DNS — обратный прокси-сервер в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-22_

Два сетевых адаптера на обратном прокси-сервере можно настроить следующим образом:

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Требования к сетевым адаптерам обратного прокси-сервера

  - **Сетевой адаптер 1 (внутренний интерфейс)** (пример)
    
    Назначенный внутренний интерфейс с 172.25.33.40.
    
    Шлюз по умолчанию не определен.
    
    Убедитесь, что существует маршрут от сети, содержащей внутренний интерфейс обратного прокси-сервера, в любые сети, содержащие серверы пула переднего плана Lync Server (например, из 172.25.33.0 в 192.168.10.0).

  - **Сетевой адаптер 2 (внешний интерфейс)** (пример)
    
    Как минимум один общедоступный IP-адрес назначен данному сетевому адаптеру.
    
    Шлюз определен так, что он указывает на маршрутизатор или интегрированный брандмауэр во внешнем периметре. (10.45.16.1 в примерах)

### <a name="dns-records-required-for-reverse-proxy"></a>Записи DNS, необходимые для обратного прокси-сервера

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Расположение/тип/порт</th>
<th>FQDN</th>
<th>IP-адрес</th>
<th>Сопоставляется с/комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внешняя запись DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Назначенный прослушиватель для внешних опубликованных ресурсов</p></td>
<td><p>Внешние веб-службы из внутреннего развертывания. Могут быть определены и созданы дополнительные записи для всех пулов и отдельных серверов для любого SIP-домена, который будет использовать это обратный прокси-сервер и на котором определены внешние веб-службы.</p></td>
</tr>
<tr class="even">
<td><p>Внешний DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Назначенный прослушиватель для внешних опубликованных ресурсов</p></td>
<td><p>Внешние веб-службы для директоров или пулов директоров в развертывании. Можно определить столько директоров, где есть разные директора, которые могут быть связаны с другими доменами SIP.</p>
<div>

> [!IMPORTANT]  
> Определение записей DNS для публикации директоров не является интерфейсным пулом или руководителем. При использовании директора необходимо определить и опубликовать внешние веб-службы директора и интерфейсного пула переднего плана. Конкретные типы трафика (для проверки подлинности и других применений) будут отправлены в директоре первыми, если она определена в топологии.


</div></td>
</tr>
<tr class="odd">
<td><p>Внешняя запись DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Назначенный прослушиватель для внешних опубликованных ресурсов</p></td>
<td><p>Ресурсы конференц-связи с телефонным подключением, опубликованные внешне</p></td>
</tr>
<tr class="even">
<td><p>Внешняя запись DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Назначенный прослушиватель для внешних опубликованных ресурсов</p></td>
<td><p>Конференции, опубликованные внешне</p></td>
</tr>
<tr class="odd">
<td><p>Внешняя запись DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Назначенный прослушиватель для сервера Office Web Apps</p></td>
<td><p>Сервер Office Web Apps, развернутый внутри или на периметре и опубликованный для внешнего клиентского доступа</p></td>
</tr>
<tr class="even">
<td><p>Внешний DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Назначенный прослушиватель для внешних опубликованных ресурсов</p></td>
<td><p>Внешняя запись Lync обнаружение для внешнего опубликованного автообнаружения и включение мобильности, Microsoft Lync Web App и веб-приложения планировщика</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

