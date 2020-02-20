---
title: 'Lync Server 2013: счетчики производительности мобильных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb5363ef31f44abdb9c8ea07938668f17b95c471
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a>Счетчики производительности мобильных устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-22_

В приведенных ниже таблицах перечислены имена и описания счетчиков производительности, которые можно использовать для мониторинга серверов, на которых работает веб-API объединенных коммуникаций (UCWA) и служба Mobility Server 2013 MCX Mobility Service.

Имя категории для счетчиков в таблице UCWA — **Ls: Web — UCWA**.

Имя категории для счетчиков в таблице MCX Mobility Service — **Ls: Web — Mobile Communication Service**.

<div>

## <a name="performance-counters-for-ucwa"></a>Счетчики производительности для UCWA


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Счетчик</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Число активных приложений</p></td>
<td><p>Текущее число приложений</p></td>
</tr>
<tr class="even">
<td><p>Число модальностей общего доступа к приложениям</p></td>
<td><p>Текущее число модальностей общего доступа к приложениям</p></td>
</tr>
<tr class="odd">
<td><p>Число модальностей активных аудио</p></td>
<td><p>Текущее число модальностей звука</p></td>
</tr>
<tr class="even">
<td><p>Число модальных модальностей совместной работы с данными</p></td>
<td><p>Текущее число модальностей совместной работы с данными</p></td>
</tr>
<tr class="odd">
<td><p>Задержка получения фотографий в службе Active Directory (МС)</p></td>
<td><p>Этот счетчик показывает среднее время (в миллисекундах), в течение которого извлекается фотография из Active Directory</p></td>
</tr>
<tr class="even">
<td><p>Число модальностей активных сообщений</p></td>
<td><p>Текущее число модальностей обмена сообщениями</p></td>
</tr>
<tr class="odd">
<td><p>Число модальных модальностей для активного панорамного изображения</p></td>
<td><p>Текущее число модальностей панорамного видео</p></td>
</tr>
<tr class="even">
<td><p>Число активных ожидающих операций получения</p></td>
<td><p>Число активных в настоящее время ожидающих обработки. долговременные подключения к серверу</p></td>
</tr>
<tr class="odd">
<td><p>Число активных сеансов</p></td>
<td><p>Текущее число конечных точек, зарегистрированных в UCWA для каждого приложения и всего</p></td>
</tr>
<tr class="even">
<td><p>Число активных экземпляров пользователей</p></td>
<td><p>Текущее число пользовательских экземпляров</p></td>
</tr>
<tr class="odd">
<td><p>Активные пользовательские экземпляры без приложения</p></td>
<td><p>Текущее число пользовательских экземпляров без приложения</p></td>
</tr>
<tr class="even">
<td><p>Число модальностей активного видео</p></td>
<td><p>Текущее число модальностей видео</p></td>
</tr>
<tr class="odd">
<td><p>Получено запросов на создание приложений/сек</p></td>
<td><p>Частота полученных запросов на создание приложений (в секунду)</p></td>
</tr>
<tr class="even">
<td><p>КАК ошибки присоединения к MCU</p></td>
<td><p>Количество неудачных попыток присоединения к MCU</p></td>
</tr>
<tr class="odd">
<td><p>Сбои при соединении с MCU AV</p></td>
<td><p>Количество сбоев присоединения к AV MCU</p></td>
</tr>
<tr class="even">
<td><p>Среднее время запуска приложения (МС)</p></td>
<td><p>Среднее время запуска приложения в миллисекундах</p></td>
</tr>
<tr class="odd">
<td><p>Среднее время жизни сеанса (МС)</p></td>
<td><p>Среднее время существования сеанса в миллисекундах (мс)</p></td>
</tr>
<tr class="even">
<td><p>Ошибки присоединения к данным MCU</p></td>
<td><p>Количество сбоев присоединения к данным MCU</p></td>
</tr>
<tr class="odd">
<td><p>Задержка поиска контактов Exchange (МС)</p></td>
<td><p>Этот счетчик показывает среднее время (в миллисекундах) для поиска контакта в Exchange</p></td>
</tr>
<tr class="even">
<td><p>Задержка получения фотографий в Exchange HD (МС)</p></td>
<td><p>Этот счетчик показывает среднее время (в миллисекундах), в течение которого извлекается фотография из Exchange</p></td>
</tr>
<tr class="odd">
<td><p>HTTP-ответов 4xx/сек</p></td>
<td><p>Частота ответов с кодом HTTP 4xx (в секунду)</p></td>
</tr>
<tr class="even">
<td><p>Ответов HTTP 5xx/сек</p></td>
<td><p>Частота ответов с кодом HTTP 5xx на секунду</p></td>
</tr>
<tr class="odd">
<td><p>Сбои при соединении с MCU мгновенными сообщениями</p></td>
<td><p>Количество сбоев присоединения к IM MCU</p></td>
</tr>
<tr class="even">
<td><p>Количество неудачных попыток получения фотографий Active Directory</p></td>
<td><p>Общее число неудачных попыток получения фотографий из Active Directory</p></td>
</tr>
<tr class="odd">
<td><p>Количество неудачных попыток поиска контактов</p></td>
<td><p>Общее число неудачных попыток поиска в контактах в Exchange</p></td>
</tr>
<tr class="even">
<td><p>Количество ошибок десериализации</p></td>
<td><p>Общее число неудачных попыток десериализации</p></td>
</tr>
<tr class="odd">
<td><p>Количество неудачных попыток получения фотографий в формате HD</p></td>
<td><p>Общее число неудачных попыток получения фотографий HD из Exchange</p></td>
</tr>
<tr class="even">
<td><p>Превышение максимального числа подписок для каждого приложения</p></td>
<td><p>Количество запросов на подписку, превышающих максимальное разрешенное для каждого приложения</p></td>
</tr>
<tr class="odd">
<td><p>Превышение максимального числа подписок на пакет</p></td>
<td><p>Количество запросов на подписку, превышающих максимально допустимое значение для пакета</p></td>
</tr>
<tr class="even">
<td><p>Ошибки подписки на присутствие</p></td>
<td><p>Количество неудачных попыток подписки на присутствие</p></td>
</tr>
<tr class="odd">
<td><p>Регистрация сбоев конечной точки</p></td>
<td><p>Количество неудачных попыток регистрации конечных точек</p></td>
</tr>
<tr class="even">
<td><p>Requests Received/Second (Полученных запросов/с)</p></td>
<td><p>Частота полученных запросов (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>Requests Succeeded/Second (Успешных запросов/с)</p></td>
<td><p>Частота успешных запросов (в секунду) (коды ответа HTTP 2xx и 3xx)</p></td>
</tr>
<tr class="even">
<td><p>Успешных запросов на создание приложений в секунду</p></td>
<td><p>Частота успешных запросов на создание приложений (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>Время ожидания получения счетчика ожидания получения</p></td>
<td><p>Число ожидающих операций по истечении времени ожидания</p></td>
</tr>
<tr class="even">
<td><p>Всего получено запросов на создание приложений</p></td>
<td><p>Общее количество запросов на создание приложений, полученных с момента запуска службы</p></td>
</tr>
<tr class="odd">
<td><p>Общее количество ответов HTTP 4xx</p></td>
<td><p>Общее число ответов HTTP 4xx</p></td>
</tr>
<tr class="even">
<td><p>Всего ответов HTTP 5xx</p></td>
<td><p>Общее число ответов HTTP 5xx</p></td>
</tr>
<tr class="odd">
<td><p>Общее количество запросов, полученных по каналу команд</p></td>
<td><p>Общее число запросов, полученных по каналу управления</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Succeeded (Всего успешных запросов)</p></td>
<td><p>Общее число успешно выполненных запросов</p></td>
</tr>
<tr class="odd">
<td><p>Общее число инициированных сеансов</p></td>
<td><p>Общее количество сеансов, инициированных с момента запуска службы</p></td>
</tr>
<tr class="even">
<td><p>Общее число сеансов, завершенных из-за превышения времени ожидания простоя</p></td>
<td><p>Общее число сеансов, которые были завершены из-за истечения времени ожидания в режиме бездействия пользователя</p></td>
</tr>
<tr class="odd">
<td><p>Общее количество регулируемых приложений</p></td>
<td><p>Количество регулируемых приложений</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Счетчики производительности для службы Mobility MCX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Счетчик</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Average Lifetime for a Session in Milliseconds
 (Среднее время существования сеанса в миллисекундах)</p></td>
<td><p>Среднее время существования сеанса в миллисекундах (мс)</p></td>
</tr>
<tr class="even">
<td><p>Current Push Notification Subscriptions (Текущие подписки на push-уведомления)</p></td>
<td><p>Текущее число подписок на push-уведомления. Это число в сочетании с числом текущих активных сеансов представляет подмножество текущих активных сеансов, зарегистрированных для устройств с Windows Mobile или iPhone.</p></td>
</tr>
<tr class="odd">
<td><p>Currently Active Network Timeout Poll Count (Число текущих активных опросов времени ожидания сети)</p></td>
<td><p>Число опросов сети с истекшим временем ожидания</p></td>
</tr>
<tr class="even">
<td><p>Currently Active Poll Count (Число активных опросов)</p></td>
<td><p>Число активных опросов (долгосрочные подключения к серверу)</p></td>
</tr>
<tr class="odd">
<td><p>Currently Active Session Count (Число текущих активных сеансов)</p></td>
<td><p>Текущее число конечных точек, зарегистрированных в службе Mobility Service</p></td>
</tr>
<tr class="even">
<td><p>Currently Active Session Count with Active Presence Subscriptions (Число текущих активных сеансов с активными подписками на сведения о присутствии)</p></td>
<td><p>Число текущих активных сеансов с активными подписками на сведения о присутствии</p></td>
</tr>
<tr class="odd">
<td><p>Push Notification Requests Failed/Second (Неудачных запросов на push-уведомления/с)</p></td>
<td><p>Частота push-уведомлений, завершившихся сбоем (в секунду)</p></td>
</tr>
<tr class="even">
<td><p>Push Notification Requests Succeeded/Second (Успешных запросов на push-уведомления/с)</p></td>
<td><p>Частота успешно выполненных push-уведомлений (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>Push Notification Requests Throttled/Second (Регулируемых запросов на push-уведомления/с)</p></td>
<td><p>Частота регулируемых push-уведомлений (в секунду)</p></td>
</tr>
<tr class="even">
<td><p>Push Notification Requests/Second (Запросов push-уведомлений/с)</p></td>
<td><p>Частота отправленных push-уведомлений (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>Requests Failed/Second (Неудачных запросов/с)</p></td>
<td><p>Частота запросов, завершившихся ошибками (в секунду)</p></td>
</tr>
<tr class="even">
<td><p>Requests Received/Second (Полученных запросов/с)</p></td>
<td><p>Частота полученных запросов (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>Requests Rejected/Second (Отклоненных запросов/с)</p></td>
<td><p>Частота отклоненных запросов (в секунду)</p></td>
</tr>
<tr class="even">
<td><p>Requests Succeeded/Second (Успешных запросов/с)</p></td>
<td><p>Частота успешных запросов (в секунду)</p></td>
</tr>
<tr class="odd">
<td><p>Succeeded Initiate Session Requests/Second (Успешных запросов на запуск сеанса/с)</p></td>
<td><p>Частота успешных запросов на получение расположения (в секунду). Запросы на запуск сеанса потребляют больше всего ресурсов ЦП на сервере. Поддерживаемая пиковая нагрузка составляет 12 сеансов в секунду. Устойчивость зависит от других нагрузок на сервере. Запуск сеанса, как правило, означает вход пользователя, с момента выхода которого из сеанса прошло довольно много времени.</p></td>
</tr>
<tr class="even">
<td><p>Total Declined Inbound Voice Calls (Всего отклоненных входящих голосовых звонков)</p></td>
<td><p>Общее число отклоненных входящих голосовых звонков</p></td>
</tr>
<tr class="odd">
<td><p>Total Failed Inbound Voice Calls (Всего неудачных входящих голосовых звонков)</p></td>
<td><p>Общее число входящих голосовых звонков, завершившихся сбоем</p></td>
</tr>
<tr class="even">
<td><p>Total Failed Outbound Voice Calls (Всего неудачных исходящих вызовов)</p></td>
<td><p>Общее число исходящих голосовых вызовов, завершившихся сбоем</p></td>
</tr>
<tr class="odd">
<td><p>Total number of sessions terminated by user (Общее число сеансов, завершенных пользователем)</p></td>
<td><p>Общее число сеансов, завершенных пользователями</p></td>
</tr>
<tr class="even">
<td><p>Total Push Notification Requests (Всего запросов на push-уведомления)</p></td>
<td><p>Общее число запросов на push-уведомления</p></td>
</tr>
<tr class="odd">
<td><p>Total Push Notification Requests Failed (Всего неудачных запросов на push-уведомления)</p></td>
<td><p>Общее число запросов на push-уведомления, завершившихся сбоем</p></td>
</tr>
<tr class="even">
<td><p>Total Push Notification Requests Succeeded (Всего успешных запросов на push-уведомления)</p></td>
<td><p>Общее число успешно выполненных запросов на push-уведомления</p></td>
</tr>
<tr class="odd">
<td><p>Total Push Notification Requests Throttled (Всего ограниченных запросов на push-уведомления)</p></td>
<td><p>Общее число запросов на push-уведомления, которые были ограничены</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Failed (Всего неудачных запросов)</p></td>
<td><p>Общее число запросов, завершившихся сбоем</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests received on the Command Channel (Всего запросов, полученных по каналу управления)</p></td>
<td><p>Общее число запросов, полученных по каналу управления</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Rejected (Всего отклоненных запросов)</p></td>
<td><p>Общее число отлоненных запросов</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests Succeeded (Всего успешных запросов)</p></td>
<td><p>ОБщее число запросов, поступивших в службу Mobility Service, которые были успешно выполнены</p></td>
</tr>
<tr class="even">
<td><p>Total Session Initiated Count (Всего запущенных сеансов)</p></td>
<td><p>Общее число сеансов, запущенных с момента запуска службы Mobility Service</p></td>
</tr>
<tr class="odd">
<td><p>Total Sessions Terminated Because of User Idle Timeout (Всего сеансов, завершенных из-за таймаута бездействия пользователя)</p></td>
<td><p>Общее число сеансов, которые были завершены из-за истечения времени ожидания в режиме бездействия пользователя</p></td>
</tr>
<tr class="even">
<td><p>Total Successful Inbound Voice Calls (Всего успешных входящих голосовых вызовов)</p></td>
<td><p>Общее число успешных входящих голосовых вызовов</p></td>
</tr>
<tr class="odd">
<td><p>Total Successful Outbound Voice Calls (Всего успешных исходящих голосовых вызовов)</p></td>
<td><p>Общее число успешных исходящих голосовых вызовов</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

