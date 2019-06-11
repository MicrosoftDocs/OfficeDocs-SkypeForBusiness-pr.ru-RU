---
title: 'Lync Server 2013: требования к оборудованию и программному обеспечению для директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3b1b2a3f642c01d3a4743281554834e9ddda55f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Требования к оборудованию и программному обеспечению для директора в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

В этом разделе описаны требования к оборудованию и программному обеспечению для режиссера, а также поддерживаемые сценарии расвыровнения для режиссера.

<div>

## <a name="hardware-requirements-for-the-director"></a>Требования к оборудованию для режиссера

В таблице ниже перечислены требования к оборудованию для режиссера.

### <a name="hardware-requirements-for-the-director"></a>Требования к оборудованию для режиссера

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Аппаратный компонент</th>
<th>Минимальное требование</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ЦП</p></td>
<td><ul>
<li><p>64-разрядный процессор с тактовой частотой от 1 до двухъядерных, 2,0 ГГц или выше.</p></li>
<li><p>64-разрядный двухъядерный процессор с тактовой частотой от двухъядерного процессора, 2,0 ГГц или выше.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Память</p></td>
<td><p>4 гигабайта (ГБ)</p></td>
</tr>
<tr class="odd">
<td><p>Диск</p></td>
<td><ul>
<li><p>жесткий диск 10000 об/мин (HDD)</p></li>
<li><p>Высокопроизводительный твердотельный накопитель (SSD) с производительностью не менее 10 000 RPM</p></li>
<li><p>2x RAID 10 (чередующиеся и зеркальные): 15 000 RPM для файлов данных базы данных</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Сеть</p></td>
<td><ul>
<li><p>Двухканальные сетевые адаптеры (рекомендуется): 1 Гбит/с</p></li>
<li><p>Один сетевой адаптер 1 Гбит/с (поддерживается)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Требования к программному обеспечению для режиссера

Роль режиссера можно развернуть только на серверах, на которых работает Lync Server 2013 Enterprise Edition.

Для режиссеров требуется одна из следующих 64-разрядных операционных систем:

  - Стандартная операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)

  - Операционная система Windows Server 2008 R2 Enterprise с пакетом обновления 1 (SP1)

  - Операционная система Windows Server 2008 R2 Datacenter с пакетом обновления 1 (SP1)

  - Операционная система Windows Server 2012 Standard

  - Операционная система Windows Server 2012 Datacenter

Для Lync Server 2013 также необходимо установить следующие программы и обновления, описанные в разделе [Дополнительные сведения о серверной поддержке и требованиях в Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).

</div>

<div>

## <a name="supported-collocation"></a>Поддерживаемое расвыровнение

Роль Director Server не может быть размещена с другой ролью сервера в Lync Server 2013. Однако если вы не разворачиваете директорию, сервер переднего плана считает роль.

</div>

</div>

<span> </span>

</div>

</div>

</div>

