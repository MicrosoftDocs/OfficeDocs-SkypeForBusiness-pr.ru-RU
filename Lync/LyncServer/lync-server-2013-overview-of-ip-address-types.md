---
title: 'Lync Server 2013: Обзор типов IP-адресов'
description: 'Lync Server 2013: Обзор типов IP-адресов.'
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
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559225"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Обзор типов IP-адресов для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-29_

При настройке IP-адресов в Lync Server 2013 у вас есть три варианта. Вы можете настроить Lync Server 2013 для поддержки только протокола IP версии 4 (IPv4), только протокола IP версии 6 (IPv6) или их комбинации (это называется *двойным стеком*). Для каждого типа конфигурации существует некоторое количество проблем, которые необходимо принимать во внимание.

  - **Только IPv4**     IPv6 был создан, так как в мире не хватает IPv4-адресов. В конечном итоге IPv6 будет полностью поддерживаться во всем мире, но в настоящее время многие компании и устройства, с которыми, возможно, приходится иметь дело вашей организации, пока не поддерживают IPv6, и не будут поддерживать еще какое-то время. Конфигурация только с IPv4 поможет гарантировать, что реализация Lync Server сможет общаться с большинством существующих устройств.

  - **Только IPv6**     В настоящее время полная реализация IPv6 будет исключать связь с множеством существующих устройств.

  - **Двойной стек**     Dual Stack — это сеть, в которой включены IPv4-и IPv6-адреса. Эта конфигурация поддерживается в Lync Server 2013, так как в большинстве случаев переход с полной (IPv4) на полный IPv6 займет несколько лет.

В следующих разделах описывается совместимость между этими тремя конфигурациями для различных функций Lync Server.

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

## <a name="conferencing"></a>Конференции

Конференц-связь включает видеосвязь, общий доступ к приложениям и совместную работу с данными (работу на доске и общий доступ к файлам).


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

Lync Server 2013 не поддерживает обход сервера-посредника для вызовов телефонной сети общего пользования (PSTN), если трафик проходит через интерфейс IPv6. Если требуется обход сервера-посредника, то рекомендуется настроить шлюз ТСОП для IPv4.


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


\* Основной интерфейс — это интерфейс, который обменивается данными с компонентами Lync Server.

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

В следующей таблице показана матрица поддержки между пулом серверов переднего плана и внутренним пулом пограничных серверов.

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
<td><p>Да</p></td>
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


\* Используйте это сочетание только в лабораторной среде.

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
<td><p><strong>Пограничный пул (внутренний периметр): внутренний стек</strong></p></td>
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


\* Используйте это сочетание только в лабораторной среде.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>Улучшенная поддержка корпоративной голосовой связи для IPv6

Развертывания, включающие контроль допуска звонков (CAC), Enhanced 9-1-1 (E9-1-1) или обход сервера-посредника, должны настраиваться как реализация только IPv4 или реализация двойного стека.

<div>


> [!NOTE]  
> В развертывании с двойным стеком даже в том случае, если клиент Lync подключается к серверу Lync Server с помощью IPv6, Lync предоставит лучшие усилия для сопоставления соответствующего IPv4-адреса для поддержки E9-1-1.



</div>

Служба сведений о местоположении с IPv6-адресами не поддерживается.

Единая система обмена сообщениями Exchange не поддерживает IPv6. Для единой системы обмена сообщениями Exchange следует убедиться, что DNS-разрешение не возвращает IPv6-адрес. Использование IPv6 может привести к сбою при отправке вызовов в голосовую почту.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>Другая поддержка функций Lync Server 2013 для IPv6

В дополнение к функциям и компонентам, упомянутым выше, Lync Server 2013 поддерживает IPv6 для следующих функций:

  - **Сохраняемый чат**
    
    Вы можете настроить IPv6 для сохраняемого чата с помощью построителя топологий. Дополнительные сведения о настройке сохраняемого чата содержатся в документации развертывание сервера сохраняемого чата.

  - **Отчеты качества взаимодействия (QoE) и регистрации вызовов (CDR).**
    
    Отчеты мониторинга включают IP-адрес в том виде, в каком он хранится в базе данных сервера мониторинга, типа IPv4 или IPv6.

</div>

</div>

<span> </span>

</div>

</div>

</div>

