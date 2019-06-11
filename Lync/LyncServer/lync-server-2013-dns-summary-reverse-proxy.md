---
title: 'Lync Server 2013: сводка по DNS — обратный прокси-сервер'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Сводка по DNS — обратный прокси-сервер в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-03-22_

Вы настраиваете на обратном прокси два сетевых адаптера, как описано ниже.

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Требования к обратной сети прокси-сервера

  - Пример **сетевого адаптера 1 (внутренний интерфейс)**
    
    Внутренний интерфейс с назначенным 172.25.33.40.
    
    Шлюз по умолчанию не определен.
    
    Убедитесь в том, что в сети есть маршрут, который содержит внутренний прокси-интерфейс обратной связи в любые сети, которые содержат серверы пула переднего плана Lync Server (например, с 172.25.33.0 на 192.168.10.0).

  - Пример **сетевого адаптера 2 (внешний интерфейс)**
    
    Этому сетевому адаптеру назначен минимум один общедоступный IP-адрес.
    
    Шлюз определен так, чтобы он указывал на маршрутизатор или интегрированный брандмауэр во внешнем периметре. (10.45.16.1 в примерах сценария)

### <a name="dns-records-required-for-reverse-proxy"></a>DNS-записи, необходимые для обратного прокси-сервера

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
<th>Полное доменное имя</th>
<th>IP-адрес</th>
<th>Карты и примечания</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внешние DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Назначенный прослушиватель для внешних опубликованных ресурсов</p></td>
<td><p>Внешние веб-службы из внутреннего развертывания. Дополнительные записи можно определять и создавать для всех пулов и отдельных серверов для любого домена SIP, который будет использовать этот прокси-сервер, а также с определенными внешними веб-службами.</p></td>
</tr>
<tr class="even">
<td><p>Внешние DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Назначенный прослушиватель для внешних опубликованных ресурсов</p></td>
<td><p>Внешние веб-службы для режиссеров и пулов режиссеров в развертывании. Вы можете определить любое количество режиссеров, для которых есть разные директора, которые могут быть связаны с другими доменами SIP.</p>
<div>

> [!IMPORTANT]  
> Определение DNS-записей для и публикации режиссеров не является ни интерфейсным пулом, ни решением режиссера. Если вы используете режиссеров, вы должны определить и опубликовать внешний веб-службы "режиссер" и "пул на стороне переднего плана". Конкретные типы трафика (для проверки подлинности и других применений) будут отправлены в директории сначала, если она определена в топологии.


</div></td>
</tr>
<tr class="odd">
<td><p>Внешние DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Назначенный прослушиватель для внешних опубликованных ресурсов</p></td>
<td><p>Внешний вход в Конференц-связь с телефонным подключением</p></td>
</tr>
<tr class="even">
<td><p>Внешние DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Назначенный прослушиватель для внешних опубликованных ресурсов</p></td>
<td><p>Конференции, опубликованные извне</p></td>
</tr>
<tr class="odd">
<td><p>Внешние DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Назначенный прослушиватель для сервера Office Web Apps</p></td>
<td><p>Сервер Office Web Apps, развернутый внутренне или на периметре, и опубликованный для внешнего клиентского доступа</p></td>
</tr>
<tr class="even">
<td><p>Внешние DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Назначенный прослушиватель для внешних опубликованных ресурсов</p></td>
<td><p>Lync обнаружение внешней записи для внешних опубликованных автообнаружения и включает мобильные и веб-приложения Microsoft Lync Web App и планировщик</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

