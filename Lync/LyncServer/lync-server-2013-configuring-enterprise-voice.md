---
title: 'Lync Server 2013: Настройка корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e46bd64efd8aa2eb6e1aead17083aa8593c8544
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Настройка корпоративной голосовой связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-03-12_

Для развертывания корпоративной голосовой связи необходимо настроить указанные ниже параметры.

  - Создание магистрали

  - Определение политики голосовой связи

  - Определение голосового маршрута

  - Enable Users for Enterprise Voice

<div>

## <a name="create-a-trunk"></a>Создание магистрали

Вы должны определить в развертывании своей корпоративной голосовой сети магистральные магистрали. Для маршрутизации на основе местоположения необходимо создать конфигурацию магистрали для каждой магистрали. Используйте построитель топологии Lync Server для определения ваших каналов и используйте команду Lync Server Windows PowerShell New-CsTrunkConfiguration или панель управления Lync Server для определения соответствующих конфигураций магистрали. Дополнительные сведения о включении маршрутизации на основе местоположения на магистральных конфигурациях можно найти в разделе Включение маршрутизации с помощью местоположения на Магистральы в разделе Создание [маршрутизации на основе местоположения в Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). В этом примере в следующей таблице показаны магистральные линии, используемые в этом сценарии.

Дополнительные сведения можно найти [в разделе Определение дополнительных каналов в построителе топологии в Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Название магистрали</th>
<th>Тип системы</th>
<th>Имя</th>
<th>Местоположение</th>
<th>посредник</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Магистраль 1 DEL-GW</p></td>
<td><p>Шлюз ТСОП</p></td>
<td><p>DEL-GW</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Магистраль 2 ХИД-GW</p></td>
<td><p>Шлюз ТСОП</p></td>
<td><p>ХИД-GW</p></td>
<td><p>Хидерабад</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Магистрали 3, DEL и АТС</p></td>
<td><p>АТС</p></td>
<td><p>DELETE-УАТС</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Магистральная ХИД 4-УАТС</p></td>
<td><p>АТС</p></td>
<td><p>ХИД-УАТС</p></td>
<td><p>Хидерабад</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>Определяет политики голосовой связи

Вы должны определить политики голосовой связи для своего корпоративного развертывания. Определение политики голосовой связи для обеспечения ограничений маршрутизации на основе местоположения для подмножества пользователей, если для работы с маршрутизацией на основе местоположения требуется только подмножество. В этом примере в следующей таблице показаны политики голосовой связи, используемые в этом сценарии. В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.

Дополнительные сведения можно найти в разделе [Настройка политик голосовой связи и использование PSTN для авторизации функций и привилегий для звонков в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Политика голосовой связи 1</th>
<th>Политика голосовой связи 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Идентификатор политики голосовой связи</p></td>
<td><p>Политика голосовой связи Делхи</p></td>
<td><p>Политика голосовой связи Хидерабад</p></td>
</tr>
<tr class="even">
<td><p>Использование PSTN</p></td>
<td><p>Использование Делхи, использование АТС DELETE, использование Хид УАТС</p></td>
<td><p>Использование Хидерабад, Хид УАТС, использование АТС Delete</p></td>
</tr>
<tr class="odd">
<td><p>Превентпстнтоллбипасс</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>Определение маршрутов голосовой связи

Вы должны определить Голосовые маршруты для своего корпоративного развертывания. В этом примере в приведенной ниже таблице показаны маршруты голосовой связи, используемые в этом сценарии. В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.

Дополнительные сведения можно найти [в разделе Настройка голосовых маршрутов для исходящих звонков в Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Маршрут к голосовой связи 1</th>
<th>Маршрут к голосовой связи 2</th>
<th>Маршрут голоса 3</th>
<th>Маршрут голосовой связи 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Имя</p></td>
<td><p>Маршрут Делхи</p></td>
<td><p>Маршрут Хидерабад</p></td>
<td><p>Маршрут для УАТС Delete</p></td>
<td><p>Маршрут Хид УАТС</p></td>
</tr>
<tr class="even">
<td><p>Использование PSTN</p></td>
<td><p>Использование Делхи</p></td>
<td><p>Использование Хидерабад</p></td>
<td><p>Использование DELETE для АТС</p></td>
<td><p>Использование Хид УАТС</p></td>
</tr>
<tr class="odd">
<td><p>Линия связи</p></td>
<td><p>Магистраль 1 DEL-GW</p></td>
<td><p>Магистраль 2 ХИД-GW</p></td>
<td><p>Магистрали 3, DEL и АТС</p></td>
<td><p>Магистральная ХИД 4-УАТС</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>Enable Users for Enterprise Voice

Включите пользователей для корпоративного голоса и назначьте им политику голосовой связи, которую вы определили ранее. В этом примере в приведенной ниже таблице показано назначение, используемое в этом сценарии. В таблице ниже приведены только те параметры, которые относятся к маршрутизации на основе местоположения.

Дополнительные сведения можно найти [в разделе Включение пользователей для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Пользователи, находящиеся в Делхи</th>
<th>Пользователи, находящиеся в Хидерабад</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Соответствующая политика голосовой связи</p></td>
<td><p>Политика голосовой связи Делхи</p></td>
<td><p>Политика голосовой связи Хидерабад</p></td>
</tr>
<tr class="even">
<td><p>Примеры пользователей</p></td>
<td><p>DEL — LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
<td><p>ХИД-LYNC-1, ХИД-LYNC-2, ХИД-LYNC-3</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка маршрутизации на основе расположения в Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

