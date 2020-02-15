---
title: 'Lync Server 2013: Настройка корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76105b9bee5ce35801196b5a4cd20b2a1feed3e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Настройка корпоративной голосовой связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-12_

Для развертывания корпоративной голосовой связи необходимо настроить следующие параметры.

  - Создание магистрали

  - Определение политики голосовой связи

  - Определение маршрута голосовой связи

  - Включение корпоративной голосовой связи для пользователей

<div>

## <a name="create-a-trunk"></a>Создание магистрали

Необходимо определить магистрали в развертывании корпоративной голосовой связи. Для маршрутизации на основе расположения необходимо создать конфигурацию магистрали для каждой магистрали. Используйте построитель топологий Lync Server, чтобы определить магистрали, и используйте командную консоль Windows PowerShell Lync Server, New — CsTrunkConfiguration или панель управления Lync Server, чтобы определить соответствующие конфигурации магистрали. Дополнительные сведения о включении маршрутизации на основе расположения в конфигурациях магистрали можно найти в разделе Включение маршрутизации на основе расположения в магистрали, а также [Включение маршрутизации на основе расположения в Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). В этом примере в приведенной ниже таблице показаны магистральные линии, используемые в этом сценарии.

Дополнительные сведения см в разделе [Определение дополнительных магистральных линий в построителе топологий в Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


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
<th>Расположение</th>
<th>Mediation Server (Сервер-посредник);</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Магистраль 1 DEL — GW</p></td>
<td><p>шлюз ТСОП;</p></td>
<td><p>DEL (GW)</p></td>
<td><p>Дели</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Магистраль 2 ХИД (GW)</p></td>
<td><p>шлюз ТСОП;</p></td>
<td><p>ХИД — GW</p></td>
<td><p>хидерабад</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Магистраль 3 DEL — УАТС</p></td>
<td><p>ОФИС</p></td>
<td><p>DEL — УАТС</p></td>
<td><p>Дели</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Магистраль 4 ХИД — УАТС</p></td>
<td><p>ОФИС</p></td>
<td><p>ХИД — УАТС</p></td>
<td><p>хидерабад</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>Определяет политики голосовой связи

Необходимо определить политики голосовой связи для развертывания корпоративной голосовой связи. Определение политики голосовой связи для применения ограничений маршрутизации на основе расположения к подмножеству пользователей, если для использования маршрутизации на основе расположения требуется только подмножество этих пользователей. В этом примере в следующей таблице показаны политики голосовой связи, используемые в этом сценарии. Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.

Дополнительную информацию можно узнать [в статье Настройка политик голосовой связи и сети PSTN для авторизации функций звонков и привилегий в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


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
<td><p>Политика голосовой связи Нью Дели</p></td>
<td><p>Политика голосовой связи Хидерабад</p></td>
</tr>
<tr class="even">
<td><p>Использование PSTN</p></td>
<td><p>Использование Нью Дели, использование УАТС Del, использование Хид УАТС</p></td>
<td><p>Использование Хидерабад, использование Хид УАТС, использование УАТС del</p></td>
</tr>
<tr class="odd">
<td><p>превентпстнтоллбипасс</p></td>
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

Необходимо определить маршруты голосовой связи для развертывания корпоративной голосовой связи. В этом примере в следующей таблице показаны маршруты голосовых вызовов, используемые в этом сценарии. Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.

Для получения дополнительных сведений см [Настройка маршрутов голосовой связи для исходящих вызовов в Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


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
<th>Маршрут голосовых вызовов 1</th>
<th>Маршрут голосовых вызовов 2</th>
<th>Маршрут голосовых вызовов 3</th>
<th>Маршрут голосовых вызовов 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Имя</p></td>
<td><p>Маршрут Нью Дели</p></td>
<td><p>Маршрут Хидерабад</p></td>
<td><p>Маршрут УАТС del</p></td>
<td><p>Маршрут Хид УАТС</p></td>
</tr>
<tr class="even">
<td><p>Использование PSTN</p></td>
<td><p>Использование Нью Дели</p></td>
<td><p>Использование Хидерабад</p></td>
<td><p>Использование УАТС del</p></td>
<td><p>Использование Хид УАТС</p></td>
</tr>
<tr class="odd">
<td><p>Магистрали</p></td>
<td><p>Магистраль 1 DEL — GW</p></td>
<td><p>Магистраль 2 ХИД (GW)</p></td>
<td><p>Магистраль 3 DEL — УАТС</p></td>
<td><p>Магистраль 4 ХИД — УАТС</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>Включение корпоративной голосовой связи для пользователей

Разрешить пользователям использовать корпоративную голосовую связь и назначить им политику голосовой связи, которую вы определили ранее. В этом примере показано назначение, используемое в этом сценарии, в приведенной ниже таблице. Только те параметры, которые относятся к маршрутизации на основе расположения, включены в таблицу для целей иллюстрации.

Дополнительные сведения приведены в статье [Включение поддержки корпоративной голосовой связи для пользователей в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Пользователи, размещенные в Нью Дели</th>
<th>Пользователи, размещенные в Хидерабад</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Связанная политика голосовой связи</p></td>
<td><p>Политика голосовой связи Нью Дели</p></td>
<td><p>Политика голосовой связи Хидерабад</p></td>
</tr>
<tr class="even">
<td><p>Примеры пользователей</p></td>
<td><p>DEL — LYNC — 1, DEL, LYNC — 2, DEL — LYNC — 3</p></td>
<td><p>ХИД — LYNC — 1, ХИД – LYNC – 2, ХИД — LYNC — 3</p></td>
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

