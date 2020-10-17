---
title: 'Lync Server 2013: Общие сведения о требованиях к брандмауэру для SQL Server'
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
ms.openlocfilehash: f836c71023defd6c826ab763d36e395a1240d3da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527746"
---
# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Общие сведения о требованиях к брандмауэру для SQL Server с Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Для развертывания Standard Edition исключения брандмауэра создаются автоматически во время установки Lync Server 2013. Тем не менее, для развертываний Enterprise Edition необходимо вручную настроить исключения брандмауэра на внутреннем сервере SQL Server. Протокол TCP/IP допускает использование определенного порта только для одного IP-адреса. Это означает, что для сервера SQL Server вы можете назначить экземпляру базы данных по умолчанию стандартный TCP-порт 1433. Для других экземпляров необходимо назначить уникальные свободные порты с помощью диспетчера конфигурации SQL Server. В этом разделе рассматриваются следующие вопросы:

  - требования к исключению брандмауэра для экземпляра по умолчанию;

  - требования к исключению брандмауэра для службы обозревателя SQL Server;

  - требования к статическим прослушивающим портам при использовании именованных экземпляров.

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>Требования к исключению брандмауэра при использовании экземпляра по умолчанию

Если при развертывании Lync Server 2013 используется экземпляр SQL Server по умолчанию для любой базы данных, то для обеспечения связи между интерфейсным пулом и экземпляром SQL Server по умолчанию используются следующие требования к правилу брандмауэра.


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
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>Входящий трафик SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>Требования к исключению брандмауэра для службы обозревателя SQL Server

Служба обозревателя SQL Server обнаруживает экземпляры базы данных (именованные или экземпляры по умолчанию) и определяет настроенные для них порты.


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
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ПРОТОКОЛА</p></td>
<td><p>1434</p></td>
<td><p>Получение</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>Требования к статическим прослушивающим портам при использовании именованных экземпляров

При использовании именованных экземпляров в конфигурации SQL Server для баз данных, поддерживающих Lync Server 2013, вы настраиваете статические порты с помощью диспетчера конфигураций SQL Server. Назначив статические порты каждому именованному экземпляру, нужно создать в брандмауэре исключение для каждого из этих портов.


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
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>Статический</p></td>
<td><p>Получение</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>Документация по SQL Server

В документации по Microsoft SQL Server 2012 содержатся подробные инструкции по настройке доступа к базам данных через брандмауэр. Дополнительные сведения о Microsoft SQL Server 2012 содержатся в разделе "Настройка брандмауэра Windows для разрешения доступа к SQL Server" [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

