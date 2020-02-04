---
title: 'Lync Server 2013: настройка маршрутизации на основе расположения'
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
ms.openlocfilehash: a0e82ae8a0dd9961bfeb9d2a513cb77b0affb2c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Настройка маршрутизации на основе расположения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-03-12_

Lync Server 2013 CU1, маршрутизация на основе местоположения — это функция корпоративной голосовой связи. Маршрутизация на основе местоположения — это функция управления звонками, определяющая способ маршрутизации звонков Lync Server 2013 CU1. Она обеспечивает ограничения на то, могут ли звонки перенаправляться в адреса для АТС или PSTN, основываясь на расположении вызывающего абонента Lync. Маршрутизация на основе местоположения применяет правила авторизации вызовов к КОММУТИРУЕМым звонкам с учетом расположения в сети вызывающего абонента. Расположение вызывающего абонента определяется на основе сетевого сайта, связанного с сетевой подсетью, в которой подключен вызывающий абонент. Для настройки маршрутизации на основе местоположения сначала необходимо предварительно развернуть корпоративный голос, а затем настроить регионы сети, сайты и подсети. Таким образом, вы настраиваете основу для включения маршрутизации на основе местоположения.

Перед развертыванием маршрутизации на основе местоположения необходимо предварительно развернуть корпоративный голос и настроить регионы сети, сайты и связать сетевые подсети с сетевыми сайтами. После завершения настройки можно настроить маршрутизацию на основе местоположения. Инструкции по настройке регионов сети, сайтов и подсетей можно найти [в статье развертывание расширенных функций голосовой связи для предприятий в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

В этом разделе рассказывается, как настроить маршрутизацию на основе местоположения, выполнив приведенный ниже пример в качестве иллюстрации.

![Пример маршрутизации на основе расположения голоса в корпоративной среде](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Пример маршрутизации на основе расположения голоса в корпоративной среде")

  
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
<th>Местоположение</th>
<th>Пользователи</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Корпоративный офис Делхи</p></td>
<td><p>DEL — LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Корпоративный офис Хидерабад</p></td>
<td><p>ХИД-LYNC-1, ХИД-LYNC-2, ХИД-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Неизвестно (например, Гостиницы)</p></td>
<td><p>УНК-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>АТС</p></td>
<td><p>Корпоративный офис Делхи</p></td>
<td><p>DEL-УАТС-1, DEL-УАТС-2</p></td>
</tr>
<tr class="odd">
<td><p>АТС</p></td>
<td><p>Корпоративный офис Хидерабад</p></td>
<td><p>ХИД-УАТС-1, ХИД-УАТС-2</p></td>
</tr>
<tr class="even">
<td><p>ТСОП</p></td>
<td><p>Неожиданно</p></td>
<td><p>PSTN-1, PSTN-2, КТСОП-3</p></td>
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
<th>Администратор</th>
<th>Местоположение</th>
<th>Имя</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Пул Lync Server 2013 CU1</p></td>
<td><p>любой</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, сервер для устранения проблем</p></td>
<td><p>любой</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>Шлюз PSTN 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>Шлюз PSTN 2</p></td>
<td><p>хидерабад</p></td>
<td><p>ХИД-GW</p></td>
</tr>
<tr class="odd">
<td><p>АТС 1</p></td>
<td><p>Delhi</p></td>
<td><p>DELETE-УАТС</p></td>
</tr>
<tr class="even">
<td><p>АТС 2</p></td>
<td><p>хидерабад</p></td>
<td><p>КРАСНАЯ-УАТС</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка корпоративной голосовой связи в Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Развертывание регионов сети, сайтов и подсетей в Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Включение маршрутизации на основе местоположения в Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Развертывание улучшенных функций голосовой связи в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

