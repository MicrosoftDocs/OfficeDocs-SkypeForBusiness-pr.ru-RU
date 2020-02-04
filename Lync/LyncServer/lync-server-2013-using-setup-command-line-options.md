---
title: 'Lync Server 2013: использование параметров командной строки для настройки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fcf3637ac0d334c2d22ef714891ea0544ee1a6d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Использование параметров командной строки программы установки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-03_

Командная строка программы установки используется для выполнения достаточно редких операций в процессе установки Office. Вместо использования параметров командной строки программы установки для установки продукта и настройки компонентов обычно используется центр развертывания Office и файл Config.xml.

Командная строка программы установки Office распознает параметры командной строки, описанные в следующей таблице.

### <a name="office-setup-command-line-options"></a>Параметры командной строки программы установки Office

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр командной строки программы установки</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Запускает центр развертывания Office для создания файла настройки программы установки (файла MSP).</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [путь]</p></td>
<td><p>Применяет к установке указанный файл настройки программы установки. Можно указать путь к конкретному MSP-файлу настройки или к папке файлов настройки.</p></td>
</tr>
<tr class="odd">
<td><p>/config [путь]</p></td>
<td><p>Указывает файл Config.xml, который программа установки использует во время установки. Используйте параметр/config для указания файла config. XML, настроенного для установки Lync 2013, например:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/модифи Lync</p></td>
<td><p>Используется с модифицированным файлом Config.xml для запуска программы установки в режиме обслуживания и изменения существующей установки Office. Например, можно использовать параметр/модифи для добавления и удаления функций Lync.</p></td>
</tr>
<tr class="odd">
<td><p>/репаир Lync</p></td>
<td><p>Запускает программу установки с компьютера пользователя, чтобы восстановить Lync.</p></td>
</tr>
<tr class="even">
<td><p>/Uninstall Lync</p></td>
<td><p>Запускает программу установки, чтобы удалить Lync с компьютера пользователя.</p></td>
</tr>
</tbody>
</table>


Подробнее об использовании параметров командной строки Setup можно узнать в разделе <http://go.microsoft.com/fwlink/p/?linkid=267515>.

</div>

<span> </span>

</div>

</div>

</div>

