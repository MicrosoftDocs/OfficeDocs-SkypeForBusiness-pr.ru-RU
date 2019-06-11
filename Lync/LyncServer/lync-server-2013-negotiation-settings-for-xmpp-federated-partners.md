---
title: 'Lync Server 2013: параметры согласования для федеративных XMPP-партнеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d72870e4060be6aa4ec428159af7ab19cb68b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Параметры согласования для федеративных XMPP-партнеров в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-21_

Параметры типов согласования в конфигурации КСМПП партнера имеют широкий спектр возможных комбинаций. Не все из этих сочетаний являются допустимыми. В таблице, подробно описанной в этом разделе, определяются допустимые и недопустимые параметры. Общие конфигурации представлены в первой таблице, во второй — на всех возможных комбинациях. Обратите внимание на то, что вы не можете использовать *простую проверку подлинности и уровень безопасности* (SASL), **если** также не доступен TLS- *Безопасность* . SASL отправляется в незашифрованном (читаемом) формате, и его не следует передавать, если только они не защищены другим способом, например TLS.

### <a name="common-xmpp-federation-negotiation-methods"></a>Распространенные методы согласования КСМПП Федерации

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
<th>Безопасность уровня транспорта (TLS)</th>
<th>Простая проверка подлинности и уровень безопасности (SASL)</th>
<th>Проверка подлинности диалбакк</th>
<th>Ожидаемый метод проверки подлинности (-ов)</th>
<th>Примечания</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p> Обязательно</p></td>
<td><p>Обязательно</p></td>
<td><p>False</p></td>
<td><p>SASL по протоколу TLS</p></td>
<td><p>TLS и SASL должны обеспечивать безопасность потока сообщений SASL. Диалбакк недоступен и не может использоваться для резервного метода в том случае, если для федеративного партнера КСМПП не задано обязательное или необязательное значение TLS.</p></td>
</tr>
<tr class="even">
<td><p>Обязательно</p></td>
<td><p>Необязательно </p></td>
<td><p>True</p></td>
<td><p>SASL over TLS, TLS Диалбакк, TCP Диалбакк</p></td>
<td><p>Если для федеративного партнера КСМПП задано значение SASL для необязательного или требуемого SASL, используется TLS. Если SASL недоступен, будет использоваться Диалбакк по TLS.</p></td>
</tr>
<tr class="odd">
<td><p>Необязательно </p></td>
<td><p>Необязательно</p></td>
<td><p>True</p></td>
<td><p>SASL over TLS, TLS Диалбакк, TCP Диалбакк</p></td>
<td><p>Несмотря на то, что предлагаемые методы согласования очень гибки, эти параметры основываются на параметрах партнера КСМПП Федерации. Если у партнера есть TLS, необязательный или обязательный, но SASL не поддерживается, TLS Диалбакк будет доступен. Если у партнера есть TLS и SASL, для которых установлен необязательный или обязательный вариант, используется оптимальный выбор TLS более SASL.</p></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>True</p></td>
<td><p>TCP Диалбакк</p></td>
<td><p>Во многих случаях TCP Диалбакк является единственным возможным решением. Менее предпочтительнее, чем другие параметры, она обеспечивает некоторый уровень доверия.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>Матрица методов согласования КСМПП Федерации — завершено

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
<th>Безопасность уровня транспорта (TLS)</th>
<th>Простая проверка подлинности и уровень безопасности (SASL)</th>
<th>Проверка подлинности диалбакк</th>
<th>Ожидаемый метод проверки подлинности</th>
<th>Заметки, предупреждение или ошибка для недействительной конфигурации</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p> Обязательно</p></td>
<td><p>Обязательно</p></td>
<td><p>True</p></td>
<td><p>SASL по протоколу TLS</p></td>
<td><div>

> [!WARNING]  
> Диалбакк не будет работать, если требуются оба SASL и TLS.


</div></td>
</tr>
<tr class="even">
<td><p> Обязательно</p></td>
<td><p>Обязательно</p></td>
<td><p>False</p></td>
<td><p>SASL по протоколу TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Необязательно </p></td>
<td><p>Обязательно</p></td>
<td><p>True</p></td>
<td><p>SASL over TLS, TLS Диалбакк, TCP Диалбакк</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.


</div></td>
</tr>
<tr class="even">
<td><p>Необязательно </p></td>
<td><p>Обязательно</p></td>
<td><p>False</p></td>
<td><p>SASL по протоколу TLS</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.


</div></td>
</tr>
<tr class="odd">
<td><p>Не поддерживается</p></td>
<td><p>Обязательно</p></td>
<td><p>True</p></td>
<td><p>TCP Диалбакк</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.


</div></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Обязательно</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Недействительная конфигурация


</div></td>
<td><div>

> [!WARNING]  
> Так как для SASL требуется протокол TLS, а протокол TLS недоступен, SASL/TLS выполнить не удастся. Для TCP Диалбакк задано значение false, и его нельзя использовать.


</div></td>
</tr>
<tr class="odd">
<td><p>Обязательно</p></td>
<td><p>Необязательно </p></td>
<td><p>True</p></td>
<td><p>SASL over TLS, Диалбакк TLS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Обязательно</p></td>
<td><p>Необязательно </p></td>
<td><p>False</p></td>
<td><p>SASL по протоколу TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Необязательно </p></td>
<td><p>Необязательно</p></td>
<td><p>True</p></td>
<td><p>SASL over TLS, TLS Диалбакк, TCP Диалбакк</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.


</div></td>
</tr>
<tr class="even">
<td><p>Необязательно </p></td>
<td><p>Необязательно</p></td>
<td><p>False</p></td>
<td><p>SASL по протоколу TLS</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.


</div></td>
</tr>
<tr class="odd">
<td><p>Не поддерживается</p></td>
<td><p>Необязательно </p></td>
<td><p>True</p></td>
<td><p>TCP Диалбакк</p></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.


</div></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Необязательно </p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Недействительная конфигурация


</div></td>
<td><div>

> [!WARNING]  
> Для SASL требуется TLS. Если вы разрешаете использовать TLS, может возникнуть сбой согласования сеанса.


</div></td>
</tr>
<tr class="odd">
<td><p>Обязательно</p></td>
<td><p>Не поддерживается</p></td>
<td><p>True</p></td>
<td><p>TLS Диалбакк</p></td>
<td><p>Настройка позволяет TLS Диалбакк.</p></td>
</tr>
<tr class="even">
<td><p>Обязательно</p></td>
<td><p>Не поддерживается</p></td>
<td><p>False</p></td>
<td><p>Недействительная конфигурация</p></td>
<td><div>

> [!WARNING]  
> Необходимо включить SASL или Диалбакк.


</div></td>
</tr>
<tr class="odd">
<td><p>Необязательно </p></td>
<td><p>Не поддерживается</p></td>
<td><p>True</p></td>
<td><p>TLS Диалбакк, TCP Диалбакк</p></td>
<td><p>На основе вариантов согласования для другой конечной точки, TCP или TLS Диалбакк будут приняты.</p></td>
</tr>
<tr class="even">
<td><p>Необязательно </p></td>
<td><p>Не поддерживается</p></td>
<td><p>False</p></td>
<td><p>Недействительная конфигурация</p></td>
<td><div>

> [!WARNING]  
> Необходимо включить SASL или Диалбакк.


</div></td>
</tr>
<tr class="odd">
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>True</p></td>
<td><p>TCP Диалбакк</p></td>
<td><p>Протокол TCP Диалбакк является единственным доступным способом согласования</p></td>
</tr>
<tr class="even">
<td><p>Не поддерживается</p></td>
<td><p>Не поддерживается</p></td>
<td><p>False</p></td>
<td><p>Недействительная конфигурация</p></td>
<td><div>

> [!WARNING]  
> Необходимо включить SASL или Диалбакк.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

