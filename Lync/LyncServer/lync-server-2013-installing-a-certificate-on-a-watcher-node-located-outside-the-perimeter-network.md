---
title: 'Lync Server 2013: Установка сертификата на узел-наблюдатель, расположенный снаружи сети периметра'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d89b14b783e2b78050b2db8e71a1009c974384
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Установка сертификата на узел-наблюдатель, расположенный вне сети периметра Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-22_

Агенты System Center Operations Manager, работающие в сети периметра (например, на пограничном сервере Lync Server), вне Организации (например, узла-наблюдателя внешней искусственной транзакции) или на границе доверия доменных служб Active Directory, могут необходимо настроить сервер шлюза System Center Operations Manager. Эта роль сервера позволяет агентам без отношения доверия с корневым сервером управления создавать предупреждения. Дополнительные сведения см. в разделе "Управление серверами шлюза в Operations Manager 2007" в библиотеке TechNet System Center [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)Operations Manager по адресу.

Если вы развертываете агент в одном из этих расположений, вам также потребуется запросить и настроить сертификат, который позволяет узлу-наблюдателю отправлять оповещения в System Center Operations Manager. Чтобы упростить этот процесс, группа разработчиков Operations Manager создала набор вспомогательных программ, позволяющих запрашивать и устанавливать нужный тип сертификата на компьютера узла-наблюдателя. Для получения дополнительных сведений и загрузки этих служебных программ просмотрите статью "получение сертификатов для агентов, не присоединенных к домену", с помощью мастера создания [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)сертификатов, по адресу.

</div>

<span> </span>

</div>

</div>

</div>

