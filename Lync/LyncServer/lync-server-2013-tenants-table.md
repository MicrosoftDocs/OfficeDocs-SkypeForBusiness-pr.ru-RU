---
title: 'Lync Server 2013: таблица "клиенты"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 091a1db8f19e44277d71371aa14c14635e6fba6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521756"
---
# <a name="tenants-table-in-lync-server-2013"></a>Таблица клиентов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Таблица клиентов является вспомогательной таблицей, в которой хранится список различных клиентов. Каждая запись в таблице представляет одного клиента.

<div>


> [!NOTE]  
> В локальном развертывании CDR использует встроенный ИД клиента, чтобы показать различные типы проверки подлинности, такие как общедоступное подключение для обмена мгновенными сообщениями, федеративное подключение или анонимное подключение.



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Столбец</th>
<th>Тип данных</th>
<th>Ключ или индекс</th>
<th>Сведения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Уникальное число, определяющее ИД клиента.</p></td>
</tr>
<tr class="even">
<td><p><strong>тенанткэй</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Допустимые значения:</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000 — Корпоративное</p></li>
<li><p>00000000-0000-0000-0000-000000000001 — Федеративное</p></li>
<li><p>00000000-0000-0000-0000-000000000002 — Анонимное</p></li>
<li><p>00000000-0000-0000-0000-000000000003 — Общедоступное подключение для обмена мгновенными сообщениями</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

