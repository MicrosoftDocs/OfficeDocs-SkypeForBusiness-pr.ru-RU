---
title: 'Lync Server 2013: Настройка маршрутизации на основе расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b88df8bf0b8362a09ea2e5b779b7fa9d789a0a48
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Настройка маршрутизации на основе расположения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-12_

Lync Server 2013 CU1, маршрутизация на основе расположения — это функция корпоративной голосовой связи. Маршрутизация на основе расположения — это функция управления звонками, которая управляет тем, как звонки направляются Lync Server 2013 CU1. Он применяет ограничения на то, могут ли звонки перенаправляться в адреса для УАТС или PSTN на основе расположения абонента Lync. Маршрутизация на основе расположения применяет правила авторизации вызовов к звонкам PSTN на основе расположения в сети вызывающего абонента. Местоположение вызывающего абонента определяется на основе сетевого сайта, связанного с сетевой подсетью, к которой подключен вызывающий абонент. Для настройки маршрутизации на основе расположения необходимо сначала развернуть корпоративную голосовую связь, а затем настроить области сети, сайты и подсети. При этом настраивается основа для активации маршрутизации на основе расположения.

Перед развертыванием маршрутизации на основе расположения необходимо сначала развернуть корпоративную голосовую связь, а также настроить регионы сети, сайты и связать сетевые подсети с сетевыми сайтами. После завершения можно настроить маршрутизацию на основе расположения. Инструкции по настройке областей сети, сайтов и подсетей см [в статье развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

В этом разделе описывается настройка маршрутизации на основе расположения с помощью следующего примера, как показано на рисунке.

![Пример маршрутизации на основе расположения корпоративной голосовой связи](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Пример маршрутизации на основе расположения корпоративной голосовой связи")

  
В следующей таблице представлены пользователи, определенные в этом примере.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Тип конечной точки</th>
<th>Расположение</th>
<th>Пользователи</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Корпоративный офис Нью Дели</p></td>
<td><p>DEL — LYNC — 1, DEL, LYNC — 2, DEL — LYNC — 3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Корпоративный офис Хидерабад</p></td>
<td><p>ХИД — LYNC — 1, ХИД – LYNC – 2, ХИД — LYNC — 3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Неизвестно (например, Гостиницы)</p></td>
<td><p>УНК — LYNC — 1</p></td>
</tr>
<tr class="even">
<td><p>ОФИС</p></td>
<td><p>Корпоративный офис Нью Дели</p></td>
<td><p>DEL — УАТС — 1, DEL, УАТС – 2</p></td>
</tr>
<tr class="odd">
<td><p>ОФИС</p></td>
<td><p>Корпоративный офис Хидерабад</p></td>
<td><p>ХИД — УАТС — 1, ХИД – УАТС – 2</p></td>
</tr>
<tr class="even">
<td><p>ТСОП</p></td>
<td><p>Unknown</p></td>
<td><p>PSTN – 1, PSTN – 2, PSTN – 3</p></td>
</tr>
</tbody>
</table>

  

В следующей таблице представлены системы, показанные в этом примере среды.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Системные</th>
<th>Расположение</th>
<th>Имя</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1 пул</p></td>
<td><p>любой</p></td>
<td><p>LS — PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, сервер-посредник</p></td>
<td><p>любой</p></td>
<td><p>MS — PL1</p></td>
</tr>
<tr class="odd">
<td><p>Шлюз PSTN 1</p></td>
<td><p>Дели</p></td>
<td><p>DEL (GW)</p></td>
</tr>
<tr class="even">
<td><p>Шлюз PSTN 2</p></td>
<td><p>хидерабад</p></td>
<td><p>ХИД — GW</p></td>
</tr>
<tr class="odd">
<td><p>УАТС 1</p></td>
<td><p>Дели</p></td>
<td><p>DEL — УАТС</p></td>
</tr>
<tr class="even">
<td><p>УАТС 2</p></td>
<td><p>хидерабад</p></td>
<td><p>КРАСНАЯ (УАТС)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка корпоративной голосовой связи в Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Развертывание областей сети, сайтов и подсетей в Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Включение маршрутизации на основе расположения в Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

