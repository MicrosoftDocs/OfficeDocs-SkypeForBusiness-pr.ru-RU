---
title: Поддержка хранения файлов в Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c424693b71f516b1fcb27523fbcb27b3a514176
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507285"
---
# <a name="file-storage-support-in-lync-server-2013"></a>Поддержка хранения файлов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-16_

Lync Server 2013 использует одно и то же хранилище файлов для всех хранилищ файлов. Поддержка хранения файлов включает следующее.

  - Файловый ресурс общего доступа либо в непосредственно подключенной системе хранения (DAS — direct attached storage), либо в сети хранения данных (SAN), включая распределенную файловую систему (DFS) и массив RAID для хранения файлов. Дополнительные сведения о требованиях к хранению приведены [в статье технические требования к серверам переднего плана, обмену мгновенными сообщениями и сведениям о присутствии в Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) , а [также требованиях к оборудованию и программному обеспечению для директора в Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) Подробнее о распределенной файловой системе для Windows Server 2008 можно узнать в статье Пошаговое руководство по DFS для Windows Server 2008 по адресу [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) .

  - Общий кластер для этого файлового ресурса общего доступа. Если используется общий кластер, то серверы кластера должны работать под управлением Windows Server 2008 или Windows Server 2008 R2. Использование серверов кластера, работающих под управлением более ранней версии Windows, может привести к проблемам с разрешениями, которые не позволяют получить доступ к некоторым функциям. Создавать файловые ресурсы общего доступа можно с помощью администратора кластера. Сведения об использовании администратора кластера содержатся в статье базы знаний Майкрософт 284838, "как создать файловый ресурс кластера серверов с Cluster.exe" по адресу [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899) .

</div>

<span> </span>

</div>

</div>

</div>

