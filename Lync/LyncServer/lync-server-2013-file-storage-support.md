---
title: 'Lync Server 2013: поддержка хранения файлов'
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
ms.openlocfilehash: 000f3357c8b30b83a2d2cecf74bdbec44d867d96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Поддержка хранения файлов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-16_

Lync Server 2013 использует одно и то же хранилище файлов для хранения всех файлов. Поддержка хранения файлов включает следующие возможности:

  - Файловый общий доступ на запоминающем устройстве (DAS) или в сети хранения данных (SAN), включая распределенную файловую систему (DFS), а также на резервный массив независимых дисков (RAID) для хранения файлов. Сведения о требованиях к хранению можно найти в статьях [технические требования к серверам переднего плана, мгновенным сообщениям и сведениям о присутствии в Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) , а также [о требованиях к оборудованию и программному обеспечению для директора в Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) Подробные сведения о DFS для операционной системы Windows Server 2008 можно найти в пошаговом руководстве по DFS для Windows Server 2008 по адресу [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).

  - Общий кластер для общего доступа к файлам. Если вы пользуетесь общим кластером, вы должны использовать кластерные серверы под управлением Windows Server 2008 или Windows Server 2008 R2. Использование серверов кластера, работающих под управлением более ранней версии Windows, может привести к проблемам с разрешениями, которые не позволяют получить доступ к некоторым функциям. Для создания общих файловых ресурсов используйте администратор кластеров. Подробнее об использовании администратора кластера можно найти в [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)статье 284838 базы знаний Майкрософт, посвященной созданию общего файлового файла кластера сервера с помощью Cluster. exe.

</div>

<span> </span>

</div>

</div>

</div>

