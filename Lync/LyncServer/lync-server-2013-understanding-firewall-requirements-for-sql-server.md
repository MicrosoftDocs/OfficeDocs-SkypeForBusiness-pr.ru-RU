---
title: 'Lync Server 2013: обзор требований к брандмауэру для SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dba3296ee01f997857660d2a3f328f663d32cf99
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Обзор требований к брандмауэру для SQL Server с Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Для развертывания в стандартном выпуске исключения брандмауэра создаются автоматически во время установки Lync Server 2013. Тем не менее, для развертывания выпуска Enterprise Edition необходимо вручную настроить исключения брандмауэра на сервере SQL Server. Протокол TCP/IP позволяет использовать конкретный порт для определенного IP-адреса. Это означает, что для сервера SQL Server вы можете назначить экземпляру базы данных по умолчанию порт 1433 по умолчанию. Для всех других экземпляров вам потребуется использовать диспетчер конфигурации SQL Server для назначения уникальных и неиспользуемых портов. В этой статье рассматриваются следующие вопросы:

  - Требования к исключению брандмауэра при использовании экземпляра по умолчанию

  - Требования к исключению межсетевого экрана для службы браузера SQL Server

  - Требования к статическим портам для прослушивания при использовании именованных экземпляров

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>Требования к исключению брандмауэра при использовании экземпляра по умолчанию

Если вы используете экземпляр SQL Server по умолчанию для любой базы данных при развертывании Lync Server 2013, для обеспечения взаимодействия из пула переднего плана с экземпляром SQL Server по умолчанию используются следующие требования правил брандмауэра.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Протокол</th>
<th>Порт</th>
<th>Направление</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>Входящий на сервер SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>Требования к исключению межсетевого экрана для службы браузера SQL Server

Служба "Обозреватель SQL Server" обнаружит экземпляры базы данных и настроит порт, для которого настроен экземпляр (с именем или по умолчанию).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Протокол</th>
<th>Порт</th>
<th>Направление</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>443</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>Требования к статическим портам для прослушивания при использовании именованных экземпляров

При использовании именованных экземпляров в конфигурации SQL Server для баз данных, поддерживающих Lync Server 2013, вы конфигурируете статические порты с помощью диспетчера конфигурации SQL Server. После того как статические порты будут назначены каждому именованному экземпляру, вы создаете исключения для каждого статического порта в брандмауэре.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Протокол</th>
<th>Порт</th>
<th>Направление</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>Статическое определение</p></td>
<td><p>443</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>Документация по SQL Server

Документация по Microsoft SQL Server 2012 содержит подробные инструкции по настройке доступа к межсетевому экрану для баз данных. Подробные сведения о Microsoft SQL Server 2012 можно найти в [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)разделе "Настройка брандмауэра Windows для обеспечения доступа к SQL Server".

</div>

</div>

<span> </span>

</div>

</div>

</div>

