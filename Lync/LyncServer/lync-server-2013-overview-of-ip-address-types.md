---
title: 'Lync Server 2013: обзор типов IP-адресов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1172fc7da9600de036312adb05548b51dea6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Обзор типов IP-адресов для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-29_

При настройке IP-адресов в Lync Server 2013 у вас есть три варианта. Вы можете настроить Lync Server 2013 таким образом, чтобы он поддерживал только IP версии 4 (IPv4), только IP версии 6 (IPv6) или сочетание обеих (называемых *двойных стеков*). Для каждого типа конфигурации существует некоторое количество проблем, которые необходимо принимать во внимание.

  - ****   Был создан только IPv4-адрес, так как в мире использующих IPv4-адреса. В конечном итоге IPv6 будет полностью поддерживаться во всем мире, но в настоящее время многие компании и устройства, с которыми, возможно, приходится иметь дело вашей организации, пока не поддерживают IPv6, и не будут поддерживать еще какое-то время. Конфигурация, поддерживающая только IPv4-адреса, гарантирует, что реализация Lync Server сможет взаимодействовать с самыми существующими устройствами.

  - **IPv6**   в настоящее время не поддерживает связь с большим количеством существующих устройств, а только в полной реализации IPv6.

  - ****   Двойная стопка стеков — сеть, в которой включены оба IPv4-и IPv6-адреса. Эта конфигурация поддерживается в Lync Server 2013, так как в большинстве случаев переход с полной-IPv4 на полный-IPv6 займет несколько лет.

В следующих разделах описаны вопросы, касающиеся этих трех конфигураций для различных функций Lync Server.

<div>


> [!NOTE]  
> Клиентская или серверная конфигурация только с IPv6 поддерживается только для целей проверки или обучения. Конфигурация только с IPv6 не поддерживается в рабочей среде.



</div>

<div>

## <a name="client-registration"></a>Регистрация клиентов


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Сеть конечной точки клиента</th>
<th>Сеть сервера</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Двойной стек</p></td>
</tr>
<tr class="odd">
<td><p>Двойной стек</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Двойной стек</p></td>
<td><p>Двойной стек</p></td>
</tr>
<tr class="odd">
<td><p>Двойной стек</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Двойной стек</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a>Одноранговый клиент

Одноранговые коммуникации включают звуковую связь, видеосвязь, общий доступ к приложениям и передачу файлов. После успешной регистрации обоих клиентов поддерживаются следующие комбинации.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Конечная точка клиента 1</th>
<th>Конечная точка клиента 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Двойной стек</p></td>
</tr>
<tr class="odd">
<td><p>Двойной стек</p></td>
<td><p>Двойной стек</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Двойной стек</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a>конференц-связь

Конференции включают звук и видео, общий доступ к приложениям и совместную работу с данными (доска и общий доступ к файлам).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Сеть конечной точки клиента</th>
<th>Сеть сервера</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Двойной стек</p></td>
</tr>
<tr class="odd">
<td><p>Двойной стек</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Двойной стек</p></td>
<td><p>Двойной стек</p></td>
</tr>
<tr class="odd">
<td><p>Двойной стек</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Двойной стек</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a>Сервер-посредник/ТСОП

Lync Server 2013 не поддерживает обмен мультимедийными звонками для коммутируемых коммутируемых телефонных сетей (PSTN), если трафик проходит через интерфейс IPv6. Если требуется обход сервера-посредника, то рекомендуется настроить шлюз ТСОП для IPv4.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Основной интерфейс*</th>
<th>Интерфейс ТСОП (на сервере-посреднике)</th>
<th>Настройка шлюза ТСОП</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>Двойной стек</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Двойной стек</p></td>
<td><p>Двойной стек</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Двойной стек</p></td>
<td><p>Двойной стек</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\*Основным интерфейсом является интерфейс, который взаимодействует с компонентами Lync Server.

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>Одноранговые коммуникации с удаленными пользователями

Одноранговые коммуникации с удаленными пользователями включают обмен мгновенными сообщениями, видеосвязь, общий доступ к приложениям и передачу файлов.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Сеть удаленного пользователя</th>
<th>Пограничный сервер (внешний периметр)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Двойной стек</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Двойной стек</p></td>
<td><p>Двойной стек</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Двойной стек</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>Конфигурация интерфейсного пула и пограничного пула

В таблице ниже показана матрица поддержки между пулом сервер переднего плана и внутренним пулом пограничного сервера.

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>Матрица интерфейсного пула и пограничного пула (внутренний периметр)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Пограничный пул: IPv4</strong></p></td>
<td><p><strong>Пограничный пул: двойной стек</strong></p></td>
<td><p><strong>Пограничный пул: IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Интерфейсный пул: IPv4</strong></p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p><strong>Интерфейсный пул: двойной стек</strong></p></td>
<td><p>Да </p></td>
<td><p>Да</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p><strong>Интерфейсный пул: IPv6</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да*</p></td>
</tr>
</tbody>
</table>


\*Используйте это сочетание только в лабораторной среде.

В следующей таблице представлена матрица поддерживаемых комбинаций интерфейсов внешнего и внутреннего периметра.

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Матрица пограничного пула внутреннего периметра и пограничного пула внешнего периметра

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Пограничный пул (внешний периметр): IPv4</strong></p></td>
<td><p><strong>Пограничный пул (внешний периметр): двойной стек</strong></p></td>
<td><p><strong>Пограничный пул (внешний периметр): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Пограничный пул (внутренний периметр): IPv4</strong></p></td>
<td><p>Да</p></td>
<td><p>Да</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="odd">
<td><p><strong>Пограничный пул (внутренний периметр): двойной стек</strong></p></td>
<td><p>Нет</p></td>
<td><p>Да</p></td>
<td><p>Нет</p></td>
</tr>
<tr class="even">
<td><p><strong>Пограничный пул (внутренний периметр): IPv6</strong></p></td>
<td><p>Нет</p></td>
<td><p>Нет</p></td>
<td><p>Да*</p></td>
</tr>
</tbody>
</table>


\*Используйте это сочетание только в лабораторной среде.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>Улучшенная поддержка корпоративной голосовой связи для IPv6

Развертывания, включающие контроль допуска звонков (CAC), Enhanced 9-1-1 (E9-1-1) или обход сервера-посредника, должны настраиваться как реализация только IPv4 или реализация двойного стека.

<div>


> [!NOTE]  
> В двухсерверной среде, даже если клиент Lync подключается к серверу Lync Server с помощью IPv6, Lync обеспечивает наилучший способ сопоставления соответствующего адреса IPv4 для поддержки E9-1-1.



</div>

Служба сведений о расположении с IPv6-адресами не поддерживается.

Единая система обмена сообщениями Exchange не поддерживает IPv6. Для единой системы обмена сообщениями Exchange следует убедиться, что DNS-разрешение не возвращает IPv6-адрес. Использование IPv6 может привести к сбою при отправке вызовов в голосовую почту.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>Другие поддерживаемые возможности Lync Server 2013 для IPv6

Помимо описанных выше функций и компонентов, Lync Server 2013 поддерживает IPv6 для следующих функций:

  - **Сохраняемый чат**
    
    Вы можете настроить IPv6 для сохраняемого чата с помощью построителя топологии. Сведения о настройке сохраняемого чата можно найти в документации развертывание сервера сохраняемого чата.

  - **Отчеты качества взаимодействия (QoE) и регистрации вызовов (CDR).**
    
    Отчеты мониторинга включают IP-адрес в том виде, в каком он хранится в базе данных сервера мониторинга, типа IPv4 или IPv6.

</div>

</div>

<span> </span>

</div>

</div>

</div>

