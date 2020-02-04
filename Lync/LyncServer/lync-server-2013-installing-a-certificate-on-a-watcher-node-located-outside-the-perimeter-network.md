---
title: 'Lync Server 2013: Установка сертификата на узле-наблюдателе, расположенном за пределами сети периметра'
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
ms.openlocfilehash: 10cd31639445fab6138ea77cb40a03d727ecce12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Установка сертификата на узле-наблюдателе, расположенном вне сети периметра Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-22_

Агенты System Center Operations Manager, работающие в демилитаризованной зоне (например, на сервере Lync Server EDGE), вне Организации (например, на внешнем узле наблюдения за транзакциями) или на границе доверенных доменных служб Active Directory, могут требуется Конфигурация сервера шлюза System Center Operations Manager. Эта роль сервера позволяет агентам, у которых нет отношения доверия с корневым сервером управления, создавать оповещения. Дополнительные сведения можно найти в разделе "Управление серверами шлюзов в Operations Manager 2007" в библиотеке TechNet System Center Operations Manager по адресу [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703).

Если вы развертываете агент в одном из этих местоположений, вам также потребуется запросить и настроить сертификат, который позволит узлу-наблюдателю отправлять оповещения в System Center Operations Manager. Для упрощения этого процесса группа Operations Manager создала набор служебных программ, которые позволят вам запросить и установить правильный тип сертификата на компьютере с узлом-наблюдателем. Сведения о том, как скачать эти служебные программы, можно найти в статье "получение сертификатов для агентов, не присоединенных к домену, с помощью [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)мастера создания сертификатов" на веб-странице блога.

</div>

<span> </span>

</div>

</div>

</div>

