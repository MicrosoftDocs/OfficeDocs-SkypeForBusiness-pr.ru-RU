---
title: 'Lync Server 2013: события UCWA'
description: 'Lync Server 2013: события UCWA.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548855"
---
# <a name="ucwa-events-in-lync-server-2013"></a>События UCWA в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 использует веб-API объединенных коммуникаций (UCWA) для выполнения различных задач, от доступа к Microsoft Exchange для поиска контактов для обновления сведений о присутствии для мобильных клиентов.

UCWA будет записывать записи оперативного поведения в виде информационных, предупреждений и ошибок типов событий. В следующей таблице описываются события, которые могут быть записаны компонентами UCWA.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Код события</th>
<th>Тип события</th>
<th>Аннотация</th>
<th>Причина и решение</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>Справоч</p></td>
<td><p>UCWA инициализировано</p></td>
<td><p>Н/Д</p>
<p>Н/Д</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Error</p></td>
<td><p>В UCWA возникло неожиданное исключение во время инициализации</p></td>
<td><p>Произошла непредвиденная ошибка во время инициализации</p>
<p>Изучите сведения об исключении в связанной записи журнала событий, чтобы определить возможную причину</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Error</p></td>
<td><p>В UCWA возникло необработанное исключение</p></td>
<td><p>Произошло необработанное исключение</p>
<p>Перезапустите сервер. Если проблема не исчезнет, обратитесь в службу технической поддержки</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Error</p></td>
<td><p>Не удается получить доступ к Exchange для фото в формате HD</p></td>
<td><p>Подключение к Exchange недоступно</p>
<p>Убедитесь, что подключение к Exchange доступно.</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>Справоч</p></td>
<td><p>Восстановление после отказа в доступе к Exchange для фотографии HD</p></td>
<td><p>Недоступно</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Error</p></td>
<td><p>Не удается получить доступ к Exchange для поиска контактов</p></td>
<td><p>Подключение к Exchange недоступно</p>
<p>Убедитесь, что подключение к Exchange доступно.</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>Справоч</p></td>
<td><p>Восстановление после отказа поиска контакта в Exchange</p></td>
<td><p>Недоступно</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>Предупреждение</p></td>
<td><p>Попытка подписки на приложение более чем разрешенных подписок на присутствие</p></td>
<td><p>Попытка подписки на приложение более чем разрешенных подписок на присутствие</p>
<p>Проверка клиентов на наличие ненужных подписок</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>Предупреждение</p></td>
<td><p>Попытка подписки на пакет больше чем разрешенных подписок на присутствие</p></td>
<td><p>Попытка подписки на пакет больше чем разрешенных подписок на присутствие</p>
<p>Проверка клиентов на наличие ненужных подписок</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Error</p></td>
<td><p>Не удается получить данные из диапазона</p></td>
<td><p>Не удается получить данные из диапазона</p>
<p>Если проблема не исчезнет, обратитесь в службу технической поддержки</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Error</p></td>
<td><p>Не удается подписать сведения о присутствии</p></td>
<td><p>Не удается подписать сведения о присутствии</p>
<p>Если проблема не исчезнет, обратитесь в службу технической поддержки</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Error</p></td>
<td><p>Не удалось зарегистрировать конечную точку</p></td>
<td><p>Не удалось зарегистрировать конечную точку</p>
<p>Если проблема не исчезнет, обратитесь в службу технической поддержки</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Error</p></td>
<td><p>MCU IM недоступен</p></td>
<td><p>MCU IM недоступен</p>
<p>Проверьте, запущена ли служба мгновенных сообщений MCU</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>Справоч</p></td>
<td><p>Восстановление после отказа к подключению к IM MCU</p></td>
<td><p>Недоступно</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Error</p></td>
<td><p>AV MCU недоступен</p></td>
<td><p>AV MCU недоступен</p>
<p>Проверьте, работает ли AV MCU</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>Справоч</p></td>
<td><p>Восстановление после отказа подключения к AV MCU</p></td>
<td><p>Недоступно</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Error</p></td>
<td><p>Так как MCU недоступен</p></td>
<td><p>Так как MCU недоступен</p>
<p>Проверьте, работает ли как MCU</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>Справоч</p></td>
<td><p>Восстановление после отказа к подключению в качестве MCU</p></td>
<td><p>Недоступно</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Error</p></td>
<td><p>MCU данных недоступен</p></td>
<td><p>MCU данных недоступен</p>
<p>Проверьте, работает ли MCU данных</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>Справоч</p></td>
<td><p>Восстановление после отказа подключения к данным MCU</p></td>
<td><p>Недоступно</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Error</p></td>
<td><p>Не удается присоединиться к IM MCU</p></td>
<td><p>Не удается присоединиться к IM MCU</p>
<p>Проверьте, запущена ли служба мгновенных сообщений MCU</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Error</p></td>
<td><p>Не удается присоединиться к AV MCU</p></td>
<td><p>Не удается присоединиться к AV MCU</p>
<p>Проверьте, работает ли AV MCU</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Error</p></td>
<td><p>Не удается присоединиться к MCU</p></td>
<td><p>Не удается присоединиться к MCU</p>
<p>Проверьте, работает ли как MCU</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Error</p></td>
<td><p>Не удается присоединиться к данным MCU</p></td>
<td><p>Не удается присоединиться к данным MCU</p>
<p>Проверьте, работает ли MCU данных</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Error</p></td>
<td><p>Не удается получить доступ к Active Directory для фото</p></td>
<td><p>Подключение к Active Directory недоступно</p>
<p>Убедитесь, что подключение к Active Directory доступно.</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>Справоч</p></td>
<td><p>Восстановление из строя доступа к Active Directory для фотографии</p></td>
<td><p>Недоступно</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>Предупреждение</p></td>
<td><p>Не удается десериализовать</p></td>
<td><p>Не удается десериализовать</p>
<p>Если проблема не исчезнет, обратитесь в службу технической поддержки</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

