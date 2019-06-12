---
title: 'Lync Server 2013: технические требования для сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b84f1a2932b76c8030c907463e8f0f2e93bedda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Технические требования для постоянного сервера чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-06_

На каждом компьютере, на котором размещается сохраняемый сервер чата, должен быть доступ к существующей топологии Lync Server 2013 со следующими компонентами:

  - **Lync Server 2013, сервер переднего плана.**  Сервер переднего плана — это основа для МАРШРУТИЗАЦИИ протокола SIP, которая делает связь между компьютерами, на которых запущены сохраняемый сервер чата, и функциональность сохраняемого чата. Прежде чем приступить к развертыванию сервера сохраняемого чата, проверьте развертывание Lync Server 2013, Standard Edition или пула переднего плана сервера Lync Server и всех прочих внутренних компьютеров, работающих в Lync Server, в зависимости от вашей организации.

В следующих разделах описаны особые требования для сервера сохраняемого чата и базы данных, хранящей сохраняемые данные чата.

<div>

## <a name="persistent-chat-server-requirements"></a>Требования к серверу для сохраняемого чата

Подробные сведения о рекомендуемом оборудовании для развертывания Lync Server и последней версии сервера сохраняемого чата можно найти в документации [серверные платформы для Lync server 2013](lync-server-2013-server-hardware-platforms.md) в справочной системе по поддержке.

Подробные сведения о поддержке сервера и средств операционной системы для Lync Server и сервера сохраняемого чата можно найти в документации поддержка [серверов и средств операционной системы в Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) .

Сведения о дополнительном программном обеспечении, которое требуется для развертывания постоянного сервера чата, приведены в таблице ниже.

### <a name="persistent-chat-server-software-prerequisites"></a>Требования к серверному программному обеспечению для постоянного чата

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Программное обеспечение</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Очередь сообщений</p></td>
<td><p>Используется при развертывании на сервере сохраняемого чата и в постоянной службе соответствия чатов.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Требования к базам данных сервера в сохраняемом чате

Сервер сохраняемого чата использует базу данных сохраняемого чата для хранения истории чата, настройки и данных пользователей. При необходимости для хранения данных о соответствии требованиям используется база данных соответствия требованиям сохраняемого чата.

<div>


> [!IMPORTANT]  
> База данных сохраняемого чата (MGC) и база данных соответствия (мгккомп) могут находиться в одном и том же экземпляре SQL Server или на разных серверах SQL Server.



</div>

Для подготовки платформы базы данных необходимо обеспечить соответствие каждого компьютера требованиям к оборудованию и затем установить обязательное программное обеспечение.

Серверная платформа для серверов базы данных сохраняемого чата требует того же оборудования, что и серверная база данных Lync Server. Дополнительные сведения можно найти в документации [серверные платформы для Lync server 2013](lync-server-2013-server-hardware-platforms.md) .

На сервере базы данных убедитесь, что установлено одно из следующих приложений:

  - Microsoft SQL Server 2012. Подробнее о том, как установить Microsoft SQL Server 2012, можно найти в [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)разделе "Установка SQL Server 2012".

  - Microsoft SQL Server 2008 R2. Подробнее об установке Microsoft SQL Server 2008 R2 можно узнать в [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)разделе "Установка SQL Server (sql Server 2008 R2)".

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Требования к сертификату сервера для сохраняемого чата

Подробные сведения о получении сертификатов, создании базы данных SQL Server и создании хранилищ файлов можно найти в разделе [развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.

</div>

</div>

<span> </span>

</div>

</div>

</div>

