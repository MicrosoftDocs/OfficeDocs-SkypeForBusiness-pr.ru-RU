---
title: 'Lync Server 2013: использование параметров командной строки программы установки'
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
ms.openlocfilehash: db24139be4c80b66cc03ff20d2155a00681111dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Использование параметров командной строки программы установки в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-03_

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
<td><p>/Admin</p></td>
<td><p>Запускает центр развертывания Office для создания файла настройки программы установки (файла MSP).</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [путь]</p></td>
<td><p>Применяет к установке указанный файл настройки программы установки. Можно указать путь к конкретному MSP-файлу настройки или к папке файлов настройки.</p></td>
</tr>
<tr class="odd">
<td><p>/config [путь]</p></td>
<td><p>Задает файл Config.xml, который программа установки использует во время установки. Используйте параметр/config, чтобы указать файл config. XML, который вы настроили для установок Lync 2013, например:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>Используется с модифицированным файлом Config.xml для запуска программы установки в режиме обслуживания и изменения существующей установки Office. Например, можно использовать параметр /modify для добавления или удаления компонентов Lync.</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>Запускает программу установки на компьютере пользователя для восстановления Lync.</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>Запускает программу установки для удаления Lync с компьютера пользователя.</p></td>
</tr>
</tbody>
</table>


Сведения об использовании параметров командной строки программы установки приведены в разделе <https://go.microsoft.com/fwlink/p/?linkid=267515>.

</div>

<span> </span>

</div>

</div>

</div>

