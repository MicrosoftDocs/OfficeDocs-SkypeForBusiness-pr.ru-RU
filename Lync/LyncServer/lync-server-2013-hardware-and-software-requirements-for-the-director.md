---
title: 'Lync Server 2013: требования к оборудованию и программному обеспечению для директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e0c75135d1ccfbb544c14c5cdc530b4e9a67b47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Требования к оборудованию и программному обеспечению для директора в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

В этом разделе описываются требования к оборудованию и программному обеспечению для директора и поддерживаемые сценарии совместного использования для директора.

<div>

## <a name="hardware-requirements-for-the-director"></a>Требования к оборудованию для Директора

В следующей таблице перечислены требования к оборудованию для директора:

### <a name="hardware-requirements-for-the-director"></a>Требования к оборудованию для Директора

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Компонент оборудования</th>
<th>Минимальное требование</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ЦП</p></td>
<td><ul>
<li><p>Четырехъядерный 64-разрядный процессор с частотой 2,0 ГГц или выше</p></li>
<li><p>Двухъядерный 64-разрядный процессор с частотой 2,0 ГГц или выше</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Память</p></td>
<td><p>4 гигабайта (ГБ)</p></td>
</tr>
<tr class="odd">
<td><p>Диск</p></td>
<td><ul>
<li><p>Жесткий диск со скоростью вращения 10000 об/мин</p></li>
<li><p>Высокопроизводительный твердотельный накопитель (SSD) со скоростью, равной или превышающей жесткий диск со скоростью вращения 10000 об/мин</p></li>
<li><p>2 диска RAID 10 (чередующихся и зеркальных) со скоростью вращения для файлов базы данных</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Сеть</p></td>
<td><ul>
<li><p>Двойные сетевые адаптеры со скоростью 1 гигабит в секунду (Гбит/с) (рекомендуется)</p></li>
<li><p>Один сетевой адаптер 1 Гбит/с (поддерживается)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Требования к программному обеспечению для директора

Роль Director можно развернуть только на серверах, на которых работает Lync Server 2013 Enterprise Edition.

Для директоров необходима одна из следующих операционных систем 64-bit:

  - Стандартная операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)

  - Операционная система Windows Server 2008 R2 Enterprise с пакетом обновления 1 (SP1)

  - Операционная система Windows Server 2008 R2 Datacenter с пакетом обновления 1 (SP1)

  - Операционная система Windows Server 2012 Standard

  - Операционная система Windows Server 2012 Datacenter

Для Lync Server 2013 также необходимо установить следующие программы и обновления, подробно описанные в разделе [Дополнительная поддержка серверов и требования в Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).

</div>

<div>

## <a name="supported-collocation"></a>Поддерживаемые режимы совместного размещения

Роль Director Server не может быть размещена с любой другой ролью сервера в Lync Server 2013. Однако если вы не развертываете директор, сервер переднего плана будет предполагать, что роль.

</div>

</div>

<span> </span>

</div>

</div>

</div>

