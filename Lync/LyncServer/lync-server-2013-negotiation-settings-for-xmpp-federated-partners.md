---
title: 'Lync Server 2013: параметры согласования для федеративных партнеров XMPP'
description: 'Lync Server 2013: параметры согласования для федеративных партнеров XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578645"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Параметры согласования для федеративных партнеров XMPP в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-21_

В конфигурации XMPP-партнера доступно значительное количество возможных комбинаций параметров для типов согласования. Но не все эти комбинации являются допустимыми. В приведенной здесь таблице подробно описывается, какие параметры являются допустимыми, а какие — нет. Распространенные конфигурации представлены в первой таблице, во второй таблице приведены все возможные комбинации. Обратите внимание на то, что вы не можете использовать *простую проверку подлинности и уровень безопасности* (SASL), **если** также не доступен протокол TLS ( *Transport Layer Security* ). Данные SASL отправляются в незашифрованном (пригодном для чтения) формате, поэтому при их передаче следует использовать другие средства защиты, такие как TLS.

### <a name="common-xmpp-federation-negotiation-methods"></a>Распространенные методы согласования федерации XMPP

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
<th>TLS (Transport Layer Security)</th>
<th>SASL (Simple Authentication and Security Layer)</th>
<th>Проверка подлинности с обратным вызовом</th>
<th>Ожидаемые методы проверки подлинности</th>
<th>Примечания</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Обязательный</p></td>
<td><p>Обязательный</p></td>
<td><p>False</p></td>
<td><p>SASL через TLS</p></td>
<td><p>Обязательное использование TLS и SASL помогает обеспечить безопасность потока сообщений SASL. Обратный вызов недоступен и не может применяться в качестве резервного метода, если федеративный XMPP-партнер не установил обязательное или необязательное использование TLS.</p></td>
</tr>
<tr class="even">
<td><p>Обязательна</p></td>
<td><p>Необязательный</p></td>
<td><p>Верно</p></td>
<td><p>SASL через TLS, обратный вызов TLS, обратный вызов TCP</p></td>
<td><p>Если федеративный XMPP-партнер установил обязательное или необязательное использование SASL, в случае обязательного использования TLS применяется SASL. Если SASL недоступен, используется обратный вызов через TLS.</p></td>
</tr>
<tr class="odd">
<td><p>Необязательный</p></td>
<td><p>Необязательна</p></td>
<td><p>Верно</p></td>
<td><p>SASL через TLS, обратный вызов TLS, обратный вызов TCP</p></td>
<td><p>Хотя эти параметры и обеспечивают гибкость с точки зрения доступных методов согласования, они основаны на параметрах XMPP-партнера федерации. Если партнер задает обязательное или необязательное использование TLS, но SASL не поддерживается, будет доступен обратный вызов через TLS. Если партнер задает обязательное или необязательное использование TLS и SASL, используется оптимальный вариант TLS через SASL.</p></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Верно</p></td>
<td><p>Обратный вызов TCP</p></td>
<td><p>Во многих случаях обратный вызов TCP является единственным возможным решением и обеспечивает некоторый уровень доверия, хотя желательно использовать другие варианты.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>Полная матрица методов согласования федерации XMPP

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
<th>TLS (Transport Layer Security)</th>
<th>SASL (Simple Authentication and Security Layer)</th>
<th>Проверка подлинности с обратным вызовом</th>
<th>Ожидаемый метод проверки подлинности</th>
<th>Примечания, предупреждение или ошибка для недействительной конфигурации</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Обязательный</p></td>
<td><p>Обязательный</p></td>
<td><p>Верно</p></td>
<td><p>SASL через TLS</p></td>
<td><div>

> [!WARNING]  
> Обратный вызов не будет работать, если требуется как SASL, так и TLS.


</div></td>
</tr>
<tr class="even">
<td><p>Обязательный</p></td>
<td><p>Обязательный</p></td>
<td><p>False</p></td>
<td><p>SASL через TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Необязательный</p></td>
<td><p>Обязательный</p></td>
<td><p>Верно</p></td>
<td><p>SASL через TLS, обратный вызов TLS, обратный вызов TCP</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.


</div></td>
</tr>
<tr class="even">
<td><p>Необязательный</p></td>
<td><p>Обязательный</p></td>
<td><p>False</p></td>
<td><p>SASL через TLS</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.


</div></td>
</tr>
<tr class="odd">
<td><p>Не поддерживается</p></td>
<td><p>Обязательный</p></td>
<td><p>Верно</p></td>
<td><p>Обратный вызов TCP</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.


</div></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Обязательный</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Недопустимая конфигурация


</div></td>
<td><div>

> [!WARNING]  
> Поскольку для SASL требуется TLS, который недоступен, комбинация SASL/TLS не работает. Для обратного вызова TCP устанавливается недопустимое состояние, и данный метод использовать нельзя.


</div></td>
</tr>
<tr class="odd">
<td><p>Обязательна</p></td>
<td><p>Необязательный</p></td>
<td><p>Верно</p></td>
<td><p>SASL через TLS, обратный вызов TLS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Обязательна</p></td>
<td><p>Необязательный</p></td>
<td><p>False</p></td>
<td><p>SASL через TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Необязательный</p></td>
<td><p>Необязательна</p></td>
<td><p>Верно</p></td>
<td><p>SASL через TLS, обратный вызов TLS, обратный вызов TCP</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.


</div></td>
</tr>
<tr class="even">
<td><p>Необязательный</p></td>
<td><p>Необязательна</p></td>
<td><p>False</p></td>
<td><p>SASL через TLS</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.


</div></td>
</tr>
<tr class="odd">
<td><p>Не поддерживается</p></td>
<td><p>Необязательный</p></td>
<td><p>Верно</p></td>
<td><p>Обратный вызов TCP</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.


</div></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Необязательный</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Недопустимая конфигурация


</div></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.


</div></td>
</tr>
<tr class="odd">
<td><p>Обязательный</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Верно</p></td>
<td><p>Обратный вызов TCP</p></td>
<td><p>Конфигурация допускает использование обратного вызова TLS.</p></td>
</tr>
<tr class="even">
<td><p>Обязательный</p></td>
<td><p>Не поддерживается</p></td>
<td><p>False</p></td>
<td><p>Недопустимая конфигурация</p></td>
<td><div>

> [!WARNING]  
> Необходимо включить SASL или обратный вызов.


</div></td>
</tr>
<tr class="odd">
<td><p>Необязательный</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Верно</p></td>
<td><p>Обратный вызов TLS, обратный вызов TCP</p></td>
<td><p>В соответствии с вариантами согласования, включенными для другой конечной точки, будет принят обратный вызов TCP или TLS.</p></td>
</tr>
<tr class="even">
<td><p>Необязательный</p></td>
<td><p>Не поддерживается</p></td>
<td><p>False</p></td>
<td><p>Недопустимая конфигурация</p></td>
<td><div>

> [!WARNING]  
> Необходимо включить SASL или обратный вызов.


</div></td>
</tr>
<tr class="odd">
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>Верно</p></td>
<td><p>Обратный вызов TCP</p></td>
<td><p>Обратный вызов TCP является единственным доступным методом согласования</p></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>False</p></td>
<td><p>Недопустимая конфигурация</p></td>
<td><div>

> [!WARNING]  
> Необходимо включить SASL или обратный вызов.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

