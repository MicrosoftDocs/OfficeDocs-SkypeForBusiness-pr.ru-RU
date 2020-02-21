---
title: 'Lync Server 2013: технические требования для сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75c5bd99e487aa596bdf3b32db77d8deb2cfab9e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Технические требования для сервера сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-06_

Каждый компьютер, на котором размещается сервер сохраняемого чата, должен иметь доступ к существующей топологии Lync Server 2013 со следующими компонентами:

  - **Lync Server 2013, сервер переднего плана.**  Сервер переднего плана является основой для маршрутизации SIP, обеспечивающей связь между компьютерами с сервером сохраняемого чата и функциями сохраняемого чата. Прежде чем приступить к развертыванию сервера сохраняемого чата, проверьте развертывание Lync Server 2013, Standard Edition или интерфейсный пул Lync Server и все остальные внутренние компьютеры, на которых работает Lync Server, в соответствии с вашей организацией.

В следующих разделах описываются конкретные требования для сервера сохраняемого чата и базы данных, в которых хранятся данные сохраняемого чата.

<div>

## <a name="persistent-chat-server-requirements"></a>Требования к серверу сохраняемого чата

Дополнительные сведения о рекомендуемом оборудовании для развертывания Lync Server и последней версии сервера сохраняемого чата приведены в статье [Server Hardware Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.

Подробные сведения о поддержке сервера и средств операционной системы для Lync Server и сервера сохраняемого чата приведены в статье [Поддержка серверов и средств операционной системы в Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.

Дополнительные сведения о дополнительном программном обеспечении, которое необходимо для развертывания сервера сохраняемого чата, приведено в следующей таблице.

### <a name="persistent-chat-server-software-prerequisites"></a>Необходимое программное обеспечение для сервера сохраняемого чата

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
<td><p>Очереди сообщений</p></td>
<td><p>Используется сервером сохраняемого чата и службой соответствия сохраняемого чата, если она развернута.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Требования к базе данных сервера сохраняемого чата

Сервер сохраняемого чата использует базу данных сохраняемого чата для хранения журнала чата, настройки и данных о подготовке пользователей. При необходимости для хранения данных соответствия используется база данных соответствия сохраняемого чата.

<div>


> [!IMPORTANT]  
> База данных сохраняемого чата (MGC) и база данных соответствия (mgccomp) могут находиться в том же экземпляре SQL Server или на разных серверах SQL Server.



</div>

Чтобы подготовить платформу сервера базы данных, убедитесь, что каждый компьютер соответствует требованиям к оборудованию, а затем установите все необходимые программные компоненты.

Серверная платформа для серверов базы данных сохраняемого чата требует того же оборудования, что и серверный сервер базы данных Lync Server. Дополнительные сведения: [аппаратные платформы сервера для Lync Server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.

Убедитесь, что на сервере базы данных установлено одно из следующих программных приложений:

  - Microsoft SQL Server 2012. Сведения о том, как установить Microsoft SQL Server 2012, можно найти в [https://go.microsoft.com/fwlink/p/?LinkID=248559](https://go.microsoft.com/fwlink/p/?linkid=248559)разделе "Установка SQL Server 2012".

  - Microsoft SQL Server 2008 R2. Сведения о том, как установить Microsoft SQL Server 2008 R2, можно найти в [https://go.microsoft.com/fwlink/?LinkId=275702](https://go.microsoft.com/fwlink/?linkid=275702)разделе "Установка SQL Server (sql Server 2008 R2)".

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Требования к сертификатам сервера сохраняемого чата

Для получения дополнительных сведений о получении сертификатов, создании базы данных SQL Server и создании хранилищ файлов ознакомьтесь со статьей [deploy Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.

</div>

</div>

<span> </span>

</div>

</div>

</div>

