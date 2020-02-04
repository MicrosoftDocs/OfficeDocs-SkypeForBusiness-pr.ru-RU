---
title: 'Lync Server 2013: резервное копирование и восстановление сервера Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a96f47bfe9d28fdbc37eea0ae62ef6cd763098
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>Резервное копирование и восстановление Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

В этом разделе вы найдете рекомендации по резервному созданию данных Lync Server 2013 и их восстановления в случае сбоя. Эти рекомендации относятся к следующим ситуациям:

  - Весь пул серверов Lync Server любого типа (сервер переднего плана, пограничный сервер, сервер-посредник, сервер, на котором сохранен чат или режиссер) или отдельный сервер в одном из этих пулов.

  - Центральный сервер управления

  - Сервер стандартных выпусков

  - Сервер заднего выпуска Enterprise Edition

  - Хранилище файлов

  - База данных для архивации, база данных мониторинга или сохраняемая база данных чата

Этот раздел не содержит сведений о восстановлении сайта целиком или для разработки резервного сайта. Сведения о разработке решения аварийного восстановления с подключенными внешними пулами можно найти [в разделе Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Это рекомендуемый способ планирования аварийного восстановления.

Если вы развернули Объединенные пулы интерфейсных элементов, то если один из этих пулов завершается сбоем и становится невосстанавливаемым, вы можете восстановить его с помощью нового полного доменного имени (FQDN) из его парного пула. Подробнее о том, как выполнить это восстановление, можно найти [в статье отказ пула в Lync Server 2013](lync-server-2013-failing-over-a-pool.md). Кроме того, если позже вам потребуется повторно создать Невосстановленный пул, который являлся частью пары интерфейсов, вы можете выполнить действия, описанные в разделе [выполнение отработки отказа в пуле для интерфейса ABC на Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).

В описанной в этом документе методологии используются специальные моменты на этапе планирования. Подробные сведения можно найти [в разделе Создание резервной копии и плана восстановления для Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

<div>

## <a name="in-this-section"></a>Содержание

  - [Подготовка к резервному копированию и восстановлению для Lync Server 2013](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Резервное копирование данных и параметров в Lync Server 2013](lync-server-2013-backing-up-data-and-settings.md)

  - [Восстановление данных и параметров в Lync Server 2013](lync-server-2013-restoring-data-and-settings.md)

  - [Журналы резервного копирования и восстановления для Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

